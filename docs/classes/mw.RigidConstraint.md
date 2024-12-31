[玩法](../groups/玩法.玩法.md) / RigidConstraint

# RigidConstraint <Badge type="tip" text="Class" /> <Score text="RigidConstraint" />

物理链接组件

::: warning Precautions

服务器设置，双端自动同步

:::

<span style="font-size: 14px;">
使用示例: 创建一个名为"RigidTest"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中看到一个正方体和一个球体，将设置绳子约束启用，进行绞盘效果。代码如下:
</span>

```ts
@Component
export default class RigidTest extends Script {
    box:mw.Model;
    ball:mw.Model;
    rigid:mw.RigidConstraint;
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        if(SystemUtil.isServer()) {

            GameObject.asyncSpawn("197386",{replicates:true}).then((obj)=>{
                this.box = obj as mw.Model;
                this.box.worldTransform.position = new Vector(200,0,1200);
            });
            GameObject.asyncSpawn("197388",{replicates:true}).then((obj)=>{
                this.ball = obj as mw.Model;
                this.ball.worldTransform.position = new Vector(100,0,100);
                // 使用链接组件的一方必须开启物理模拟
                this.ball.physicsEnabled = true;
            })
            // 创建链接组件链接Box与ball
            setTimeout(()=>{
                GameObject.asyncSpawn("RigidConstraint",{replicates:true}).then((obj)=>{
                    this.rigid = obj as mw.RigidConstraint;
                    this.rigid.constraint1 = this.box;
                    this.rigid.constraint2 = this.ball;
                    this.rigid.softConstraintEnabled = true;
                    this.rigid.length = 800;
                    this.rigid.autoEnable = true;
                    // 开启铰链拉到ball到target位置
                    setTimeout(() => {
                        this.rigid.winchEnabled = true;
                        this.rigid.winchForce = 10000;
                        this.rigid.winchSpeed = 150;
                        this.rigid.winchTarget = 200;
                    }, 5000);
                })
            }, 10000);
        }
    }
}
```

## Hierarchy

- [`GameObject`](mw.GameObject.md)

  ↳ **`RigidConstraint`**

## Table of contents

### Properties <Score text="Properties" /> 
| **[onWinchComplete](mw.RigidConstraint.md#onwinchcomplete)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\>  |
| :-----|
| 绞盘达到目标时触发回调函数|


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
| **[autoEnable](mw.RigidConstraint.md#autoenable)**(): `boolean`  |
| :-----|
| 在运行时自动启用约束效果|
| **[constraint1](mw.RigidConstraint.md#constraint1)**(): [`GameObject`](mw.GameObject.md)  |
| 被约束对象1，当前可约束类型为模型、角色、NPC、载具，其他对象约束无效|
| **[constraint2](mw.RigidConstraint.md#constraint2)**(): [`GameObject`](mw.GameObject.md)  |
| 被约束对象2，当前可约束类型为模型、角色、NPC、载具，其他对象约束无效|
| **[currentDistance](mw.RigidConstraint.md#currentdistance)**(): `number`  |
| 两个被约束对象的间隔距离|
| **[isVisible](mw.RigidConstraint.md#isvisible)**(): `boolean`  |
| 显示连接线|
| **[length](mw.RigidConstraint.md#length)**(): `number`  |
| 设置两个被约束对象的最大连接距离，当两个被约束对象的当前距离大于连接长度时，会自动收缩物理连接，接两个被约束对象拉进到设定距离|
| **[softConstraintEnabled](mw.RigidConstraint.md#softconstraintenabled)**(): `boolean`  |
| 开启软连接后，两个被约束的对象间隔距离不可超过连接长度的限制，可以短于连接长度并自由旋转。开启软连接后可以使用铰盘功能|
| **[winchEnabled](mw.RigidConstraint.md#winchenabled)**(): `boolean`  |
| 开启后，软连接自动执行铰盘效果|
| **[winchForce](mw.RigidConstraint.md#winchforce)**(): `number`  |
| 设置绞盘的拉力，拉动的目标质量越大，所需要的拉力越大|
| **[winchSpeed](mw.RigidConstraint.md#winchspeed)**(): `number`  |
| 设置绞盘运动速度（cm/s）|
| **[winchTarget](mw.RigidConstraint.md#winchtarget)**(): `number`  |
| 设置绞盘运动的目标距离，当被约束的两个对象间隔距离达到绞盘目标时，停止运动|


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

___

### onWinchComplete <Score text="onWinchComplete" /> 

• **onWinchComplete**: [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\>

绞盘达到目标时触发回调函数

## Accessors

___

### autoEnable <Score text="autoEnable" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **autoEnable**(): `boolean`

</th>
<th style="text-align: left">

• `set` **autoEnable**(`newEnable`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


在运行时自动启用约束效果

#### Returns

| `boolean` | 启用状态 |
| :------ | :------ |


</td>
<td style="text-align: left">


在运行时自动启用约束效果

#### Parameters

| `newEnable` `boolean` | 启用状态 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### constraint1 <Score text="constraint" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **constraint1**(): [`GameObject`](mw.GameObject.md)

</th>
<th style="text-align: left">

• `set` **constraint1**(`constraintObject`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


被约束对象1，当前可约束类型为模型、角色、NPC、载具，其他对象约束无效

#### Returns

| [`GameObject`](mw.GameObject.md) | 约束对象1 |
| :------ | :------ |


</td>
<td style="text-align: left">


被约束对象1，当前可约束类型为模型、角色、NPC、载具，其他对象约束无效

#### Parameters

| `constraintObject` [`GameObject`](mw.GameObject.md) | 约束对象1 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### constraint2 <Score text="constraint" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **constraint2**(): [`GameObject`](mw.GameObject.md)

</th>
<th style="text-align: left">

• `set` **constraint2**(`constraintObject`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


被约束对象2，当前可约束类型为模型、角色、NPC、载具，其他对象约束无效

#### Returns

| [`GameObject`](mw.GameObject.md) | 约束对象2 |
| :------ | :------ |


</td>
<td style="text-align: left">


被约束对象2，当前可约束类型为模型、角色、NPC、载具，其他对象约束无效

#### Parameters

| `constraintObject` [`GameObject`](mw.GameObject.md) | 约束对象2 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### currentDistance <Score text="currentDistance" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **currentDistance**(): `number`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


两个被约束对象的间隔距离

#### Returns

| `number` | 两约束对象的间隔距离 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### isVisible <Score text="isVisible" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **isVisible**(): `boolean`

</th>
<th style="text-align: left">

• `set` **isVisible**(`visible`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


显示连接线

#### Returns

| `boolean` | 显示状态 |
| :------ | :------ |


</td>
<td style="text-align: left">


显示连接线

#### Parameters

| `visible` | `boolean` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### length <Score text="length" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **length**(): `number`

</th>
<th style="text-align: left">

• `set` **length**(`maxLength`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


设置两个被约束对象的最大连接距离，当两个被约束对象的当前距离大于连接长度时，会自动收缩物理连接，接两个被约束对象拉进到设定距离

#### Returns

| `number` | 最大连接距离 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置两个被约束对象的最大连接距离，当两个被约束对象的当前距离大于连接长度时，会自动收缩物理连接，接两个被约束对象拉进到设定距离

#### Parameters

| `maxLength` `number` | 最大连接距离 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### softConstraintEnabled <Score text="softConstraintEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **softConstraintEnabled**(): `boolean`

</th>
<th style="text-align: left">

• `set` **softConstraintEnabled**(`newEnable`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


开启软连接后，两个被约束的对象间隔距离不可超过连接长度的限制，可以短于连接长度并自由旋转。开启软连接后可以使用铰盘功能

#### Returns

| `boolean` | 软链接启用状态 |
| :------ | :------ |


</td>
<td style="text-align: left">


开启软连接后，两个被约束的对象间隔距离不可超过连接长度的限制，可以短于连接长度并自由旋转。开启软连接后可以使用铰盘功能

#### Parameters

| `newEnable` `boolean` | 软链接启用状态 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### winchEnabled <Score text="winchEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **winchEnabled**(): `boolean`

</th>
<th style="text-align: left">

• `set` **winchEnabled**(`newEnable`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


开启后，软连接自动执行铰盘效果

#### Returns

| `boolean` | 绞盘启用状态 |
| :------ | :------ |


</td>
<td style="text-align: left">


开启后，软连接自动执行铰盘效果

#### Parameters

| `newEnable` `boolean` | 绞盘启用状态 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### winchForce <Score text="winchForce" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **winchForce**(): `number`

</th>
<th style="text-align: left">

• `set` **winchForce**(`force`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


设置绞盘的拉力，拉动的目标质量越大，所需要的拉力越大

#### Returns

| `number` | 绞盘力大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置绞盘的拉力，拉动的目标质量越大，所需要的拉力越大

#### Parameters

| `force` `number` | 绞盘力大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### winchSpeed <Score text="winchSpeed" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **winchSpeed**(): `number`

</th>
<th style="text-align: left">

• `set` **winchSpeed**(`speed`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


设置绞盘运动速度（cm/s）

#### Returns

| `number` | 绞盘运动速度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置绞盘运动速度（cm/s）

#### Parameters

| `speed` `number` | 绞盘运动速度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### winchTarget <Score text="winchTarget" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **winchTarget**(): `number`

</th>
<th style="text-align: left">

• `set` **winchTarget**(`targetLength`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


设置绞盘运动的目标距离，当被约束的两个对象间隔距离达到绞盘目标时，停止运动

#### Returns

| `number` | 绞盘目标距离 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置绞盘运动的目标距离，当被约束的两个对象间隔距离达到绞盘目标时，停止运动

#### Parameters

| `targetLength` `number` | 绞盘目标距离 |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods
