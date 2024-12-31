[玩法](../groups/玩法.玩法.md) / NavLink

# NavLink <Badge type="tip" text="Class" /> <Score text="NavLink" />

寻路链接

-------------------------

寻路链接能将导航网格体内没有直接路径的区域链接起来

如何使用寻路链接：

- 创建一个寻路链接对象。可手动将左侧栏中逻辑对象中的寻路链接拖入场景中，在编辑器属性面板中调整参数；也可以在脚本中动态创建寻路链接。

- 设置寻路链接对象属性 左点右点位置分别表示链接在寻路区域中的两个点，链接建立后AI会从一个点沿直线前往另一个点

- 需要注意的是，链接并不保证指定线路的“可到达性”，即如果链接线上存在AI无法跨越或者无法行走的区域，寻路有可能失效

<span style="font-size: 14px;">
使用示例:创建一个名为"NavLinkSample"的脚本，复制以下代码后将脚本挂载于地板上，接着在场景中拖入一个寻路区域，相对位置设置为(1200, 0, 0)，相对缩放设置为(20, 20, 10)，再开启世界设置中的 动态构建寻路导航数据
</span>

进入游戏后，按 N 控制NPC开始寻路；按 R 重置NPC位置；按 1 切换寻路链接的区域类型；按 2 切换寻路链接的连通方式。可以测试NPC在不同情景下的寻路表现。
代码如下：
```ts
@Component
export default class NavLinkSample extends Script {
    platform1 = null as Model;
    platform2 = null as Model;
    bridge = null as Model;
    target = null as Model;
    npc = null as Character;
    navLink = null as NavLink;

    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        if (SystemUtil.isServer()) {
            // 创建平台1
            this.platform1 = GameObject.spawn("197386", {
                replicates: true,
                transform: new Transform(new Vector(2000, 0, 0), new Rotation(0, 0, 0), new Vector(4, 20, 1))
            });

            // 创建平台2
            this.platform1 = GameObject.spawn("197386", {
                replicates: true,
                transform: new Transform(new Vector(700, 0, 0), new Rotation(0, 0, 0), new Vector(10, 20, 1))
            });

            // 创建连接桥
            this.platform1 = GameObject.spawn("197386", {
                replicates: true,
                transform: new Transform(new Vector(1500, 600, 80), new Rotation(0, 0, 0), new Vector(6, 0.5, 0.2))
            });

            // 创建目标点
            this.target = GameObject.spawn("197388", {
                replicates: true,
                transform: new Transform(new Vector(500, -500, 100), new Rotation(0, 0, 0), new Vector(1, 1, 1))
            });
            // 关闭目标点碰撞
            setTimeout(() => {
                this.target.collisionEnabled = false;
            }, 2000);

            // 创建寻路链接
            this.navLink = GameObject.spawn("NavigationLink", {
                replicates: true,
                transform: new Transform(new Vector(1500, 600, 100), new Rotation(0, 0, 0), new Vector(1, 1, 1))
            });
            // 设置寻路链接
            setTimeout(() => {
                this.navLink.leftPosition = new Vector(400, 0, 0);
                this.navLink.rightPosition = new Vector(-400, 0, 0);
                this.navLink.navLinkArea = LinkClassType.Default;
                this.navLink.direction = DirectionType.BothWays;
            }, 2000);

            // 创建npc
            this.npc = GameObject.spawn("Character", {
                replicates: true,
                transform: new Transform(new Vector(2000, -600, 500), new Rotation(0, 0, 0), new Vector(1, 1, 1))
            });

            // 接收 npc向target寻路 事件，执行逻辑
            Event.addClientListener("NPCNavigateToTarget", ()=>{
                Navigation.navigateTo(this.npc, this.target.worldTransform.position);
            });

            // 接收 重置npc位置 事件，执行逻辑
            Event.addClientListener("ResetNPC", ()=>{
                this.npc.worldTransform.position = new Vector(2000, -600, 500);
            });

            // 接收 切换寻路链接区域类型 事件（ Default 与 Null 切换）
            Event.addClientListener("SwitchLinkClassType", ()=>{
                if (this.navLink.navLinkArea == LinkClassType.Default) {
                    this.navLink.navLinkArea = LinkClassType.Null;
                } else {
                    this.navLink.navLinkArea = LinkClassType.Default;
                }
            });

            // 接收 切换寻路链接通行方向 事件（ Bothways 与 RightToLeft 切换）
            Event.addClientListener("SwitchDirectionType", ()=>{
                if (this.navLink.direction == DirectionType.BothWays) {
                    this.navLink.direction = DirectionType.RightToLeft;
                } else {
                    this.navLink.direction = DirectionType.BothWays;
                }
            });
        }

        if (SystemUtil.isClient()) {
            // 按 N 发送 npc向target寻路 事件
            InputUtil.onKeyDown(Keys.N, ()=>{
                Event.dispatchToServer("NPCNavigateToTarget");
            });

            // 按 R 发送 重置npc位置 事件
            InputUtil.onKeyDown(Keys.R, ()=>{
                Event.dispatchToServer("ResetNPC");
            });

            // 按 1 发送 切换寻路链接区域类型 事件（ Default 与 Null 切换）
            InputUtil.onKeyDown(Keys.One, ()=>{
                Event.dispatchToServer("SwitchLinkClassType");
            });

            // 按 2 发送 切换寻路链接通行方向 事件（ Bothways 与 RightToLeft 切换）
            InputUtil.onKeyDown(Keys.Two, ()=>{
                Event.dispatchToServer("SwitchDirectionType");
            });
        }
    }
}
```

## Hierarchy

- [`GameObject`](mw.GameObject.md)

  ↳ **`NavLink`**

## Table of contents

### Properties <Score text="Properties" /> 


::: details click
### Properties <Score text="Properties" /> 
| **[onBeforeDestroyDelegate](mw.GameObject.md#onbeforedestroydelegate)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\>   |
| :-----|
| 物体销毁前事件回调|
| **[onCustomPropertyChange](mw.GameObject.md#oncustompropertychange)**: `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> <Badge type="tip" text="other" />  |
| 监听自定义属性同步事件|
| **[onDestroyDelegate](mw.GameObject.md#ondestroydelegate)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\>   |
| 物体销毁后事件回调|
:::


### Accessors <Score text="Accessors" /> 
| **[direction](mw.NavLink.md#direction)**(): [`DirectionType`](../enums/mw.DirectionType.md)  |
| :-----|
| 获取链接线的通行方向|
| **[leftPosition](mw.NavLink.md#leftposition)**(): [`Vector`](mw.Vector.md)  |
| 获取左点位置|
| **[navLinkArea](mw.NavLink.md#navlinkarea)**(): [`LinkClassType`](../enums/mw.LinkClassType.md)  |
| 获取链接区域的寻路类型|
| **[rightPosition](mw.NavLink.md#rightposition)**(): [`Vector`](mw.Vector.md)  |
| 获取右点位置|


::: details click
### Accessors <Score text="Accessors" /> 
| **[actorLevel](mw.GameObject.md#actorlevel)**(): `number` <Badge type="tip" text="other" />  |
| :-----|
| 获取Actor等级|
| **[assetId](mw.GameObject.md#assetid)**(): `string`   |
| 获取当前物体使用资源的GUID|
| **[gameObjectId](mw.GameObject.md#gameobjectid)**(): `string`   |
| 获取物体的唯一标识（唯一标识一个对象的字符串）。|
| **[isDestroyed](mw.GameObject.md#isdestroyed)**(): `boolean`   |
| 当前物体是否被销毁|
| **[isReady](mw.GameObject.md#isready)**(): `boolean`   |
| 当前物体状态|
| **[localTransform](mw.GameObject.md#localtransform)**(): [`Transform`](mw.Transform.md)   |
| 当前物体本地变换|
| **[name](mw.GameObject.md#name)**(): `string`   |
| 返回当前物体名称|
| **[netStatus](mw.GameObject.md#netstatus)**(): [`NetStatus`](../enums/mw.NetStatus.md)   |
| 获取当前物体同步状态|
| **[parent](mw.GameObject.md#parent)**(): [`GameObject`](mw.GameObject.md)   |
| 获取当前父物体|
| **[sceneCaptureTag](mw.GameObject.md#scenecapturetag)**(): `string`   |
| 获取当前物体的捕捉标签|
| **[tag](mw.GameObject.md#tag)**(): `string`   |
| 获取当前物体的标签|
| **[worldTransform](mw.GameObject.md#worldtransform)**(): [`Transform`](mw.Transform.md)   |
| 当前物体世界变换|
:::


### Methods <Score text="Methods" /> 


::: details click
### Methods <Score text="Methods" /> 
| **[addComponent](mw.GameObject.md#addcomponent)**<`T`: extends [`Script`](mw.Script.md)<`T`\>\>(`constructor`: (...`args`: `unknown`[]) => `T`: extends [`Script`](mw.Script.md)<`T`\>, `bInReplicates?`: `boolean`): `T`: extends [`Script`](mw.Script.md)<`T`\>   |
| :-----|
| 添加一个脚本组件|
| **[asyncGetChildByName](mw.GameObject.md#asyncgetchildbyname)**(`name`: `string`): `Promise`<[`GameObject`](mw.GameObject.md)\>   |
| 异步根据名称查找子物体|
| **[asyncReady](mw.GameObject.md#asyncready)**(): `Promise`<[`GameObject`](mw.GameObject.md)\>   |
| 物体准备好后返回|
| **[clone](mw.GameObject.md#clone)**(`gameObjectInfo?`: [`GameObjectInfo`](../interfaces/mw.GameObjectInfo.md)): [`GameObject`](mw.GameObject.md)   |
| 复制对象|
| **[destroy](mw.GameObject.md#destroy)**(): `void`   |
| 删除对象|
| **[getBoundingBox](mw.GameObject.md#getboundingbox)**(`nonColliding?`: `boolean`, `includeFromChild?`: `boolean`, `outer?`: [`Vector`](mw.Vector.md)): [`Vector`](mw.Vector.md)   |
| 获取物体包围盒大小|
| **[getBounds](mw.GameObject.md#getbounds)**(`onlyCollidingComponents`: `boolean`, `originOuter`: [`Vector`](mw.Vector.md), `boxExtentOuter`: [`Vector`](mw.Vector.md), `includeFromChild?`: `boolean`): `void`   |
| 获取物体边界|
| **[getChildByGameObjectId](mw.GameObject.md#getchildbygameobjectid)**(`gameObjectId`: `string`): [`GameObject`](mw.GameObject.md)   |
| 根据 gameObjectId 查找子物体|
| **[getChildByName](mw.GameObject.md#getchildbyname)**(`name`: `string`): [`GameObject`](mw.GameObject.md)   |
| 根据名称查找子物体|
| **[getChildByPath](mw.GameObject.md#getchildbypath)**(`path`: `string`): [`GameObject`](mw.GameObject.md)   |
| 根据路径查找子物体|
| **[getChildren](mw.GameObject.md#getchildren)**(): [`GameObject`](mw.GameObject.md)[]   |
| 获取子物体|
| **[getChildrenByName](mw.GameObject.md#getchildrenbyname)**(`name`: `string`): [`GameObject`](mw.GameObject.md)[]   |
| 通过名字查找所有的子物体|
| **[getComponent](mw.GameObject.md#getcomponent)**<`T`: extends [`Script`](mw.Script.md)<`T`\>\>(`constructor?`: (...`args`: `unknown`[]) => `T`: extends [`Script`](mw.Script.md)<`T`\>): `T`: extends [`Script`](mw.Script.md)<`T`\>   |
| 获取指定类型的组件|
| **[getComponentPropertys](mw.GameObject.md#getcomponentpropertys)**<`T`: extends [`Script`](mw.Script.md)<`T`\>\>(`constructor`: (...`args`: `unknown`[]) => `T`: extends [`Script`](mw.Script.md)<`T`\>): `Map`<`string`, `IPropertyOptions`\>   |
| 获取脚本组件属性|
| **[getComponents](mw.GameObject.md#getcomponents)**<`T`: extends [`Script`](mw.Script.md)<`T`\>\>(`constructor?`: (...`args`: `unknown`[]) => `T`: extends [`Script`](mw.Script.md)<`T`\>): `T`: extends [`Script`](mw.Script.md)<`T`\>[]   |
| 获取指定类型的所有组件|
| **[getCustomProperties](mw.GameObject.md#getcustomproperties)**(): `string`[]   |
| 获取自定义属性名字数组，返回对象所有自定义属性。|
| **[getCustomProperty](mw.GameObject.md#getcustomproperty)**<`T`: extends [`CustomPropertyType`](../modules/Core.mw.md#custompropertytype)\>(`propertyName`: `string`): `T`: extends [`CustomPropertyType`](../modules/Core.mw.md#custompropertytype)   |
| 获取自定义属性的值，服务器客户端均可调用，客户端调用需注意属性同步的延迟。|
| **[getCustomPropertyChangeDelegate](mw.GameObject.md#getcustompropertychangedelegate)**(`property`): `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> <Badge type="tip" text="client" />  |
| 获取给定自定义属性修改时触发的事件代理。双端对象在服务器修改自定义属性后，双端均会触发事件并执行绑定函数。|
| **[getVisibility](mw.GameObject.md#getvisibility)**(): `boolean`   |
| 获取物体是否被显示|
| **[isPrefabActor](mw.GameObject.md#isprefabactor)**(): `boolean`   |
| 返回当前物体是否为预制体|
| **[moveBy](mw.GameObject.md#moveby)**(`velocity`: [`Vector`](mw.Vector.md), `isLocal?`: `boolean`): `void` <Badge type="tip" text="other" />  |
| 按给定的速度矢量随时间平滑地移动对象|
| **[moveTo](mw.GameObject.md#moveto)**(`targetPosition`: [`Vector`](mw.Vector.md), `time`: `number`, `isLocal?`: `boolean`, `onComplete?`: () => `void`): `void` <Badge type="tip" text="other" />  |
| 在指定时间内从当前位置平滑移动至目标位置|
| **[rotateBy](mw.GameObject.md#rotateby)**(`rotation`: [`Quaternion`](mw.Quaternion.md)  [`Rotation`](mw.Rotation.md), `multiplier`: `number`, `isLocal?`: `boolean`): `void` <Badge type="tip" text="other" />  |
| 按给定的旋转量随时间平滑地旋转对象|
| **[rotateTo](mw.GameObject.md#rotateto)**(`targetRotation`: [`Quaternion`](mw.Quaternion.md)  [`Rotation`](mw.Rotation.md), `time`: `number`, `isLocal?`: `boolean`, `onComplete?`: () => `void`): `void` <Badge type="tip" text="other" />  |
| 在指定时间内从当前旋转平滑变化至目标旋转|
| **[scaleBy](mw.GameObject.md#scaleby)**(`scale`: [`Vector`](mw.Vector.md), `isLocal?`: `boolean`): `void` <Badge type="tip" text="other" />  |
| 按每秒给定的缩放矢量随时间平滑缩放对象|
| **[scaleTo](mw.GameObject.md#scaleto)**(`targetScale`: [`Vector`](mw.Vector.md), `time`: `number`, `isLocal?`: `boolean`, `onComplete?`: () => `void`): `void` <Badge type="tip" text="other" />  |
| 在指定时间内从当前缩放平滑变化至目标缩放|
| **[setAbsolute](mw.GameObject.md#setabsolute)**(`absolutePosition?`: `boolean`, `absoluteRotation?`: `boolean`, `absoluteScale?`: `boolean`): `void`   |
| 设置物体localTransform是相对于父物体或者世界|
| **[setCustomProperty](mw.GameObject.md#setcustomproperty)**(`propertyName`: `string`, `value`: `undefined`  [`CustomPropertyType`](../modules/Core.mw.md#custompropertytype)): `void` <Badge type="tip" text="server" />  |
| 设置自定义属性的值，双端对象需在服务器调用。当设置的属性不存在时会新增自定义属性。|
| **[setVisibility](mw.GameObject.md#setvisibility)**(`status`: `boolean`  [`PropertyStatus`](../enums/mw.PropertyStatus.md), `propagateToChildren?`: `boolean`): `void`   |
| 设置物体是否被显示|
| **[stopMove](mw.GameObject.md#stopmove)**(): `void` <Badge type="tip" text="other" />  |
| 中断moveTo()、moveBy()的进一步移动|
| **[stopRotate](mw.GameObject.md#stoprotate)**(): `void` <Badge type="tip" text="other" />  |
| 中断从rotateTo()或rotateBy()的进一步旋转|
| **[stopScale](mw.GameObject.md#stopscale)**(): `void` <Badge type="tip" text="other" />  |
| 中断从ScaleTo()或ScaleBy()的进一步缩放|
| **[asyncFindGameObjectById](mw.GameObject.md#asyncfindgameobjectbyid)**(`gameObjectId`: `string`): `Promise`<[`GameObject`](mw.GameObject.md)\>   |
| 通过 gameObjectId 异步查找 GameObject|
| **[asyncGetGameObjectByPath](mw.GameObject.md#asyncgetgameobjectbypath)**(`path`: `string`): `Promise`<[`GameObject`](mw.GameObject.md)\>   |
| 通过路径异步查找物体|
| **[asyncSpawn](mw.GameObject.md#asyncspawn)**<`T`: extends [`GameObject`](mw.GameObject.md)<`T`\>\>(`assetId`: `string`, `gameObjectInfo?`: [`GameObjectInfo`](../interfaces/mw.GameObjectInfo.md)): `Promise`<`T`: extends [`GameObject`](mw.GameObject.md)<`T`\>\>   |
| 异步构造一个物体|
| **[bulkPivotTo](mw.GameObject.md#bulkpivotto)**(`gameObjects`: [`GameObject`](mw.GameObject.md)[], `transforms`: [`Transform`](mw.Transform.md)[]): `void`   |
| 批量设置位置|
| **[findGameObjectById](mw.GameObject.md#findgameobjectbyid)**(`gameObjectId`: `string`): [`GameObject`](mw.GameObject.md)   |
| 通过 gameObjectId 查找物体|
| **[findGameObjectByName](mw.GameObject.md#findgameobjectbyname)**(`name`: `string`): [`GameObject`](mw.GameObject.md)   |
| 通过名字查找物体|
| **[findGameObjectsByName](mw.GameObject.md#findgameobjectsbyname)**(`name`: `string`): [`GameObject`](mw.GameObject.md)[]   |
| 通过名字查找物体|
| **[findGameObjectsByTag](mw.GameObject.md#findgameobjectsbytag)**(`tag`: `string`): [`GameObject`](mw.GameObject.md)[]   |
| 通过自定义标签获取物体|
| **[getGameObjectByPath](mw.GameObject.md#getgameobjectbypath)**(`path`: `string`): [`GameObject`](mw.GameObject.md)   |
| 通过路径查找物体|
| **[spawn](mw.GameObject.md#spawn)**<`T`: extends [`GameObject`](mw.GameObject.md)<`T`\>\>(`assetId`: `string`, `gameObjectInfo?`: [`GameObjectInfo`](../interfaces/mw.GameObjectInfo.md)): `T`: extends [`GameObject`](mw.GameObject.md)<`T`\>   |
| 构造一个物体|
:::


## Properties

## Accessors

___

### direction <Score text="direction" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **direction**(): [`DirectionType`](../enums/mw.DirectionType.md)

</th>
<th style="text-align: left">

• `set` **direction**(`newDirectionType`): `void` <Badge type="tip" text="other" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取链接线的通行方向

#### Returns

| [`DirectionType`](../enums/mw.DirectionType.md) | 当前通行方向 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置链接线的通行方向

#### Parameters

| `newDirectionType` [`DirectionType`](../enums/mw.DirectionType.md) |  新通行方向 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### leftPosition <Score text="leftPosition" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **leftPosition**(): [`Vector`](mw.Vector.md)

</th>
<th style="text-align: left">

• `set` **leftPosition**(`newPosition`): `void` <Badge type="tip" text="other" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取左点位置

#### Returns

| [`Vector`](mw.Vector.md) | 当前左点位置 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置左点位置

#### Parameters

| `newPosition` [`Vector`](mw.Vector.md) |  新左点位置 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### navLinkArea <Score text="navLinkArea" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **navLinkArea**(): [`LinkClassType`](../enums/mw.LinkClassType.md)

</th>
<th style="text-align: left">

• `set` **navLinkArea**(`newClassType`): `void` <Badge type="tip" text="other" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取链接区域的寻路类型

#### Returns

| [`LinkClassType`](../enums/mw.LinkClassType.md) | 当前寻路类型 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置链接区域的寻路类型

#### Parameters

| `newClassType` [`LinkClassType`](../enums/mw.LinkClassType.md) |  新寻路类型 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### rightPosition <Score text="rightPosition" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **rightPosition**(): [`Vector`](mw.Vector.md)

</th>
<th style="text-align: left">

• `set` **rightPosition**(`newPosition`): `void` <Badge type="tip" text="other" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取右点位置

#### Returns

| [`Vector`](mw.Vector.md) | 当前右点位置 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置右点位置

#### Parameters

| `newPosition` [`Vector`](mw.Vector.md) |  新右点位置 |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods
