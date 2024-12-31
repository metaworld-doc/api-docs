[玩法](../groups/玩法.玩法.md) / Impulse

# Impulse <Badge type="tip" text="Class" /> <Score text="Impulse" />

冲量

-------------------------

冲量是一个瞬间爆发力，为对象提供单一且即时的电源，是一种将力集中在一帧上的感觉。

冲量对象是如何工作的呢 ？

- 创建一个冲量对象。可手动将左侧栏中逻辑对象中的冲量拖入场景中，在属性面板中调整参数；也可以在脚本中动态创建冲量对象。

- 设置冲量对象属性 enable 为 true ，才可触发冲量效果。

- impulseVector 属性表示力的方向。

- impulseRadialForce 属性表示力的大小。

<span style="font-size: 14px;">
使用示例:创建一个名为"ImpulseSample"的脚本，放置在对象管理器中冲量对象的子级，将冲量对象相对缩放改为（5.00,5.00,0.50），放置在合适的位置，可以在与冲量对象重叠区域放置一个Cube，Cube大小缩放与冲量对象相同。打开脚本，输入以下代码保存，运行游戏，你将在场景中看到人物在Cube上蹦床的效果，代码如下：
</span>

（示例代码中impulseId = "1602E908"中的1602E908替换方式为右键冲量对象，复制对象ID。更换为你的冲量对象ID即可）
```ts
@Component
export default class ImpulseSample extends Script {
    impulseId = "1602E908";
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected async onStart(): Promise<void> {
        const impulse = (await GameObject.findGameObjectById(this.impulseId)) as Impulse;
        // 先设置为 false，玩家进入范围后再设置为 true，会有玩家突然凭空被弹开的效果
        impulse.enable = true;
        // 绝对冲量应用时会先清空物体自身速度，相对冲量会将冲量和物体当前速度叠加
        impulse.impulseType = ImpulseType.Absolute;
        // 只有为矢量力的情况下，impulseVector 属性才有意义
        impulse.impulseForceType = ImpulseForceType.VectorForce;
        // 设置为自定义的带方向的冲量值
        impulse.impulseVector = new Vector(0, 0, 2000);
        impulse.onImpulseEnter.add(()=>{
             console.log("Impulse onImpulseEnter")
        })
    }
}
```

## Hierarchy

- [`GameObject`](mw.GameObject.md)

  ↳ **`Impulse`**

## Table of contents

### Properties <Score text="Properties" /> 
| **[onImpulseEnter](mw.Impulse.md#onimpulseenter)**: [`MulticastGameObjectDelegate`](mw.MulticastGameObjectDelegate.md)  |
| :-----|
| 发生冲量碰撞后的回调函数|


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
| **[enable](mw.Impulse.md#enable)**(): `boolean`   |
| :-----|
| 获取是否启用冲量|
| **[impulseForceType](mw.Impulse.md#impulseforcetype)**(): [`ImpulseForceType`](../enums/mw.ImpulseForceType.md)   |
| 获取当前冲量力类型|
| **[impulseRadialForce](mw.Impulse.md#impulseradialforce)**(): `number`   |
| 获取径向力的冲量值|
| **[impulseType](mw.Impulse.md#impulsetype)**(): [`ImpulseType`](../enums/mw.ImpulseType.md)   |
| 获取冲量应用方式，绝对或相对|
| **[impulseVector](mw.Impulse.md#impulsevector)**(): [`Vector`](mw.Vector.md)   |
| 获取矢量力的冲量向量|


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

### onImpulseEnter <Score text="onImpulseEnter" /> 

• **onImpulseEnter**: [`MulticastGameObjectDelegate`](mw.MulticastGameObjectDelegate.md)

发生冲量碰撞后的回调函数

<span style="font-size: 14px;">
使用示例:创建一个名为"ImpulseOnEnterSample"的脚本，放置在对象管理器中，打开脚本，输入以下代码保存，运行游戏，你将在场景中看到一个蹦床的效果，代码如下：
</span>

```ts
@Component
export default class ImpulseOnEnterSample extends Script {
    impulseId = "1602E908";
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected async onStart(): Promise<void> {
        const impulse = (await GameObject.findGameObjectById(this.impulseId)) as Impulse;
        impulse.onImpulseEnter.add(()=>{
             console.log("Impulse onImpulseEnter")
        })
    }
}
```

## Accessors

___

### enable <Score text="enable" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **enable**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **enable**(`impulseEnabled`): `void` <Badge type="tip" text="other" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否启用冲量

#### Returns

| `boolean` | 是否启用冲量 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否启用冲量，禁用状态下，不会应用冲量到物体上


#### Parameters

| `impulseEnabled` `boolean` |  是否启用冲量的应用，设置为 false 后依然会有碰撞事件，但不会应用冲量 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"ImpulseSample"的脚本，放置在对象管理器中，打开脚本，输入以下代码保存，运行游戏，你将在场景中看到一个蹦床的效果，代码如下：
</span>

```ts
@Component
export default class ImpulseSample extends Script {
    impulseId = "1602E908";
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected async onStart(): Promise<void> {
        const impulse = (await GameObject.findGameObjectById(this.impulseId)) as Impulse;
        // 先设置为 false，玩家进入范围后再设置为 true，会有玩家突然凭空被弹开的效果
        impulse.enable = true;
    }
}
```
___

### impulseForceType <Score text="impulseForceType" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **impulseForceType**(): [`ImpulseForceType`](../enums/mw.ImpulseForceType.md) 

</th>
<th style="text-align: left">

• `set` **impulseForceType**(`impulseCollisionType`): `void` <Badge type="tip" text="other" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取当前冲量力类型

#### Returns

| [`ImpulseForceType`](../enums/mw.ImpulseForceType.md) | 冲量力类型 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置冲量力类型。使用示例详见属性 impulseRadialForce 和 impulseVector 中示例代码。

#### Parameters

| `impulseCollisionType` [`ImpulseForceType`](../enums/mw.ImpulseForceType.md) |  冲量力类型 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### impulseRadialForce <Score text="impulseRadialForce" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **impulseRadialForce**(): `number` 

</th>
<th style="text-align: left">

• `set` **impulseRadialForce**(`value`): `void` <Badge type="tip" text="other" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取径向力的冲量值

#### Returns

| `number` | 径向力时的冲量值 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置径向力的冲量值


#### Parameters

| `value` | `number` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"ImpulseRadialForceSample"的脚本，放置在对象管理器中，打开脚本，输入以下代码保存，运行游戏，你将在场景中看到一个蹦床的效果，玩家走到蹦床上被飞的距离相比默认情况时有变化，代码如下：
</span>

```ts
@Component
export default class ImpulseRadialForceSample extends Script {
    // 场景中冲量对象的 id
    impulseId = "1602E908";
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected async onStart(): Promise<void> {
        const impulse = (await GameObject.findGameObjectById(this.impulseId)) as Impulse;
        // 只有为径向力的情况下，impulseRadialForce 属性才有意义
        impulse.impulseForceType = ImpulseForceType.RadialForce;
        impulse.impulseRadialForce = 500;
    }
}
```
___

### impulseType <Score text="impulseType" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **impulseType**(): [`ImpulseType`](../enums/mw.ImpulseType.md) 

</th>
<th style="text-align: left">

• `set` **impulseType**(`impulseType`): `void` <Badge type="tip" text="other" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取冲量应用方式，绝对或相对

#### Returns

| [`ImpulseType`](../enums/mw.ImpulseType.md) | 当前冲量应用方式 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置冲量应用方式

::: warning Precautions

在编辑器中使用会自动更新箭头方向

:::


#### Parameters

| `impulseType` [`ImpulseType`](../enums/mw.ImpulseType.md) |  冲量应用方式 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"ImpulseTypeSample"的脚本，放置在对象管理器中，打开脚本，输入以下代码保存，运行游戏，你将在场景中看到一个蹦床的效果，玩家走到蹦床上被弹起的高度有变化，代码如下：
</span>

```ts
@Component
export default class ImpulseTypeSample extends Script {
    // 场景中冲量对象的 id
    impulseId = "1602E908";
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected async onStart(): Promise<void> {
        const impulse = (await GameObject.findGameObjectById(this.impulseId)) as Impulse;
        // 绝对冲量应用时会先清空物体自身速度，相对冲量会将冲量和物体当前速度叠加
        impulse.impulseType = ImpulseType.Absolute;
    }
}
```
___

### impulseVector <Score text="impulseVector" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **impulseVector**(): [`Vector`](mw.Vector.md) 

</th>
<th style="text-align: left">

• `set` **impulseVector**(`vec`): `void` <Badge type="tip" text="other" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取矢量力的冲量向量

#### Returns

| [`Vector`](mw.Vector.md) | 当前冲量类型 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置矢量力的冲量向量


#### Parameters

| `vec` [`Vector`](mw.Vector.md) |  冲量力向量 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"ImpulseVectorSample"的脚本，放置在对象管理器中，打开脚本，输入以下代码保存，运行游戏，你将在场景中看到一个蹦床的效果，玩家走到蹦床上被弹起的高度有变化，代码如下：
</span>

```ts
@Component
export default class ImpulseVectorSample extends Script {
    // 场景中冲量对象的 id
    impulseId = "1602E908";
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected async onStart(): Promise<void> {
        const impulse = (await GameObject.findGameObjectById(this.impulseId)) as Impulse;
        // 只有为矢量力的情况下，impulseVector 属性才有意义
        impulse.impulseForceType = ImpulseForceType.VectorForce;
        // 设置为自定义的带方向的冲量值
        impulse.impulseVector = new Vector(0, 0, 2000);
    }
}
```


## Methods
