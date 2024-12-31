[角色系统](../groups/角色系统.角色系统.md) / Pawn

# Pawn <Badge type="tip" text="Class" /> <Score text="Pawn" />

Pawn作为玩家角色和非对象玩家角色的基类，是一个可以通过玩家控制器或者逻辑脚本控制的游戏对象。

## Hierarchy

- [`GameObject`](mw.GameObject.md)

  ↳ **`Pawn`**

  ↳↳ [`Character`](mw.Character.md)

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
| **[customTimeDilation](mw.Pawn.md#customtimedilation)**(): `number`   |
| :-----|
| 膨胀时间速度|
| **[player](mw.Pawn.md#player)**(): [`Player`](mw.Player.md)   |
| 玩家对象|


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
| **[setOutline](mw.Pawn.md#setoutline)**(`enabled`: `boolean`, `color?`: [`LinearColor`](mw.LinearColor.md), `width?`: `number`): `void` <Badge type="tip" text="client" />  |
| :-----|
| 添加描边效果|
| **[setPostProcessOutline](mw.Pawn.md#setpostprocessoutline)**(`enabled`: `boolean`, `color?`: [`LinearColor`](mw.LinearColor.md), `width?`: `number`): `void` <Badge type="tip" text="client" />  |
| 添加后处理描边|


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

### customTimeDilation <Score text="customTimeDilation" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **customTimeDilation**(): `number` 

</th>
<th style="text-align: left">

• `set` **customTimeDilation**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


膨胀时间速度

::: warning Precautions

Pawn对象的膨胀时间速度，修改后自身时间流速是该值乘世界时间流速。默认值是1。单机模式可以将膨胀设置为0达到时间暂停的效果，联机模式最低设置为0.1

:::


#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


膨胀时间速度

::: warning Precautions

Pawn对象的膨胀时间速度，修改后自身时间流速是该值乘世界时间流速。默认值是1。单机模式可以将膨胀设置为0达到时间暂停的效果，联机模式最低设置为0.1

:::


#### Parameters

| `value` | `number` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"Example_Pawn_CustomTimeDilation"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中修改玩家的时间膨胀速度为原来的0.5倍后看到跳跃的延迟效果。代码如下：
</span>

```ts
@Component
export default class Example_Pawn_CustomTimeDilation extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
         // 当前修改时间膨胀后角色动画不会受到影响，关闭角色相关优化后即可
         Player.asyncGetLocalPlayer().then((player) => {
             console.warn("client close setOptimization")
             mw.AvatarSettings.setOptimization(player.character, false, false);
         })
         // 下列代码仅在客户端执行
         if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 添加一个按键方法：按下键盘“1”，将玩家的时间膨胀速度修改为原来的0.5倍，并跳跃
            InputUtil.onKeyDown(Keys.One, () => {
                myPlayer.character.customTimeDilation = 0.5;
                console.log("My pawn customTimeDilation: " + myPlayer.character.customTimeDilation);
                // 使玩家角色进行跳跃
                (myPlayer.character as Character).jump();
            });
        }
    }
}
```
<span style="font-size: 14px;">
使用示例:创建一个名为"Example_Pawn_CustomTimeDilation"的脚本,放置在对象栏中,打开脚本,输入以下代码保存,运行游戏,你将在场景中修改玩家的时间膨胀速度为原来的0.5倍后看到跳跃的延迟效果.代码如下:
</span>

```ts
@Component
export default class Example_Pawn_CustomTimeDilation extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
         // 当前修改时间膨胀后角色动画不会受到影响，关闭角色相关优化后即可
         Player.asyncGetLocalPlayer().then((player) => {
             console.warn("client close setOptimization")
             mw.AvatarSettings.setOptimization(player.character, false, false);
         })
         // 下列代码仅在客户端执行
         if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 添加一个按键方法：按下键盘“1”，将玩家的时间膨胀速度修改为原来的0.5倍，并跳跃
            InputUtil.onKeyDown(Keys.One, () => {
                myPlayer.character.customTimeDilation = 0.5;
                console.log("My pawn customTimeDilation: " + myPlayer.character.customTimeDilation);
                // 使玩家角色进行跳跃
                (myPlayer.character as Character).jump();
            });
        }
    }
}
```
___

### player <Score text="player" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **player**(): [`Player`](mw.Player.md) 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


玩家对象

::: warning Precautions

控制当前Pawn对象的玩家，只读。

:::


#### Returns

</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"Example_Pawn_Player"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，通过player获取玩家，你将在控制台中看到打印的userId和instanceId。代码如下：
</span>

```ts
@Component
export default class Example_Pawn_Player extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
         // 下列代码仅在客户端执行
         if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 打印玩家(自己)userId和instanceId并对比
            console.log("My userId: " + myPlayer.userId);
            // 通过owner获取玩家(自己)并打印userId和instanceId并对比
            let myCharacter = myPlayer.character;
            let mmyPlayer_2 = myCharacter.player;
            console.log("My userId: " + mmyPlayer_2.userId);
        }
    }
}
```
| [`Player`](mw.Player.md) |  |
| :------ | :------ |

## Methods

___

### setOutline <Score text="setOutline" /> 

• **setOutline**(`enabled`, `color?`, `width?`): `void` <Badge type="tip" text="client" />

添加描边效果

#### Parameters

| `enabled` `boolean` | 是否开启描边 |
| :------ | :------ |
| `color?` [`LinearColor`](mw.LinearColor.md) | 描边颜色 default:LinearColor.black |
| `width?` `number` | 描边宽度 default:2 range: [0, 10] type: 浮点数 |


::: warning Precautions

为Pawn对象添加描边效果，描边效果会被其他物体遮挡。

:::

<span style="font-size: 14px;">
使用示例:将使用到的资源:“197386”拖入优先加载栏。创建一个名为"Example_Pawn_Outline"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“1”，给玩家Pawn添加或移除普通描边（会被遮挡），：按下键盘“2”，给玩家Pawn添加或移除后处理描边（不会被遮挡）。代码如下：
</span>

```ts
@Component
export default class Example_Pawn_Outline extends Script {
    // 声明变量
    flag: boolean;
    flag_advance: boolean;
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 设置当前描边状态
        this.flag = false;
        this.flag_advance = false;
        // 下列代码仅在服务端执行
        if(SystemUtil.isServer()) {
            // 创建一个立方体
            let cube = GameObject.spawn("197386",{ transform: new Transform(new Vector(200, 0, 0), Rotation.zero, new Vector(1, 1, 2))}) as Model;
            cube.setCollision(CollisionStatus.Off);
        }
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 添加一个按键方法：按下键盘“1”，给玩家Pawn添加或移除普通描边（会被遮挡）
            InputUtil.onKeyDown(Keys.One, () => {
                if(this.flag) {
                    myPlayer.character.setOutline(false);
                } else {
                    myPlayer.character.setOutline(true, LinearColor.red, 1);
                }
                this.flag = !this.flag;
            });
            // 添加一个按键方法：按下键盘“2”，给玩家Pawn添加或移除后处理描边（不会被遮挡）
            InputUtil.onKeyDown(Keys.Two, () => {
                if(this.flag_advance) {
                    myPlayer.character.setPostProcessOutline(false);
                } else {
                    myPlayer.character.setPostProcessOutline(true, LinearColor.red, 1);
                }
                this.flag_advance = !this.flag_advance;
            });
        }
    }
}
```

___

### setPostProcessOutline <Score text="setPostProcessOutline" /> 

• **setPostProcessOutline**(`enabled`, `color?`, `width?`): `void` <Badge type="tip" text="client" />

添加后处理描边

#### Parameters

| `enabled` `boolean` | 是否开启描边 |
| :------ | :------ |
| `color?` [`LinearColor`](mw.LinearColor.md) | 描边颜色 default:LinearColor.red |
| `width?` `number` | 描边宽度 default:1 range: [0, 10] type: 浮点数 |


::: warning Precautions

为Pawn对象添加高级描边效果，描边效果不会被其他物体遮挡。

:::

<span style="font-size: 14px;">
使用示例:将使用到的资源:“197386”拖入优先加载栏。创建一个名为"Example_Pawn_PostProcessOutline"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中创建一个立方体，按下键盘“2”可以给本地玩家添加或移除不被立方体遮挡的红色描边效果。代码如下：
</span>

```ts
@Component
export default class Example_Pawn_PostProcessOutline extends Script {
    // 声明变量
    flag: boolean;
    flag_advance: boolean;
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 设置当前描边状态
        this.flag = false;
        this.flag_advance = false;
        // 下列代码仅在服务端执行
        if(SystemUtil.isServer()) {
            // 创建一个立方体
            let cube = GameObject.spawn("197386",{ transform: new Transform(new Vector(200, 0, 0), Rotation.zero, new Vector(1, 1, 2))}) as Model;
            cube.setCollision(CollisionStatus.Off);
        }
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 添加一个按键方法：按下键盘“1”，给玩家Pawn添加或移除普通描边（会被遮挡）
            InputUtil.onKeyDown(Keys.One, () => {
                if(this.flag) {
                    myPlayer.character.setOutline(false);
                } else {
                    myPlayer.character.setOutline(true, LinearColor.red, 1);
                }
                this.flag = !this.flag;
            });
            // 添加一个按键方法：按下键盘“2”，给玩家Pawn添加或移除后处理描边（不会被遮挡）
            InputUtil.onKeyDown(Keys.Two, () => {
                if(this.flag_advance) {
                    myPlayer.character.setPostProcessOutline(false);
                } else {
                    myPlayer.character.setPostProcessOutline(true, LinearColor.red, 1);
                }
                this.flag_advance = !this.flag_advance;
            });
        }
    }
}
```
