[玩法](../groups/玩法.玩法.md) / Model

# Model <Badge type="tip" text="Class" /> <Score text="Model" />

物理模拟与材质设置

-------------------------

在游戏中添加物理效果有助于提升场景的沉浸感，因为这能促使玩家相信他们的确在与模拟内容进行交互，并且能以某种方式得到反馈。

物理模拟 如何工作呢？

Model的属性定义了静态模型具有物理特性，其中较为重要的是：

- 静态模型实例 physicsEnabled 属性为 True 可开启物理模拟。

- mass 属性表示重力的大小。

- friction 属性表示摩擦力的大小。

- restitution 属性表示弹力。

- lockPosition 属性表示约束，约束哪个轴指在这个轴向不会发生变动。

材质如何自定义设置呢？

材质 是可以应用到网格物体静态模型上的资源，用它可控制场景的可视外观。

- setMaterial 方法更换静态模型材质，传入左侧材质资源ID。

- setStaticMeshAsset 方法更换静态模型，传入左侧静态模型资源ID。

::: warning Precautions

物理相关接口目前版本不支持证多端同步

:::

<span style="font-size: 14px;">
使用示例:创建一个名为"ModelExample"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你可以通过F1键，在场景中动态生成模型并模拟物理。代码如下：
</span>

```ts
@Component
export default class ModelExample extends Script {
    //当脚本被实例后，会在第一帧更新前调用此函数
    protected async onStart(): Promise<void> {
        if(SystemUtil.isClient())
            {
                InputUtil.onKeyDown(Keys.F1,()=>{
                    // F1键 通知服务器执行事件
                    mw.Event.dispatchToServer("Model");
                });
            }
        if(SystemUtil.isServer()){
            mw.Event.addClientListener("Model",()=>{
                let box = GameObject.spawn("197386",{
                    transform:new Transform(new Vector(500,0,100),new Rotation(0,0,0),new Vector(1,1,1)),
                    replicates:true
                }) as Model;
                // 控制质量
                box.massEnabled = true;
                // 设置质量
                box.mass = 200;
                // 使用质量
                box.gravityEnabled = true;
                // 设置摩擦力
                box.friction = 0.1;
                // 设置弹力
                box.restitution = 1;
                // 开启物理模拟
                box.physicsEnabled = true;
                // 开关闭阴影投射
                box.castShadow = false;
            });
        }
    }
}
```

## Hierarchy

- [`GameObject`](mw.GameObject.md)

  ↳ **`Model`**

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
| **[angularDamping](mw.Model.md#angulardamping)**(): `number`   |
| :-----|
| 角阻尼|
| **[canAffectNavigation](mw.Model.md#canaffectnavigation)**(): `boolean`  |
| 获取模型碰撞是否影响动态寻路的导航数据|
| **[castShadow](mw.Model.md#castshadow)**(): `boolean`   |
| 获取是否开启阴影|
| **[centerOfMass](mw.Model.md#centerofmass)**(): [`Vector`](mw.Vector.md)   |
| 获取质心偏移|
| **[collisionEnabled](mw.Model.md#collisionenabled)**(): `boolean`   |
| 是否开启碰撞|
| **[collisionGroup](mw.Model.md#collisiongroup)**(): `string`   |
| 获取对应的碰撞组|
| **[color](mw.Model.md#color)**(): [`LinearColor`](mw.LinearColor.md)   |
| Model颜色|
| **[density](mw.Model.md#density)**(): `number`   |
| 获取密度大小|
| **[friction](mw.Model.md#friction)**(): `number`   |
| 获取摩擦力大小|
| **[gravityEnabled](mw.Model.md#gravityenabled)**(): `boolean`   |
| 获取是否启用重力|
| **[linerDamping](mw.Model.md#linerdamping)**(): `number`   |
| 获取线性阻尼|
| **[lockPositionX](mw.Model.md#lockpositionx)**(): `boolean`   |
| 获取是否约束位置X|
| **[lockPositionY](mw.Model.md#lockpositiony)**(): `boolean`   |
| 获取是否约束位置Y|
| **[lockPositionZ](mw.Model.md#lockpositionz)**(): `boolean`   |
| 获取是否约束位置Z|
| **[lockRotationX](mw.Model.md#lockrotationx)**(): `boolean`   |
| 获取是否约束旋转X|
| **[lockRotationY](mw.Model.md#lockrotationy)**(): `boolean`   |
| 获取是否约束旋转Y|
| **[lockRotationZ](mw.Model.md#lockrotationz)**(): `boolean`   |
| 获取是否约束旋转Z|
| **[mass](mw.Model.md#mass)**(): `number`   |
| 获取质量大小|
| **[massEnabled](mw.Model.md#massenabled)**(): `boolean`   |
| 获取是否使用质量|
| **[onTouch](mw.Model.md#ontouch)**(): [`MulticastGameObjectDelegate`](mw.MulticastGameObjectDelegate.md)  |
| 进入Model事件|
| **[onTouchEnd](mw.Model.md#ontouchend)**(): [`MulticastGameObjectDelegate`](mw.MulticastGameObjectDelegate.md)  |
| 离开Model事件|
| **[opacity](mw.Model.md#opacity)**(): `number`   |
| 获取模型单层透明度|
| **[physicsAngularVelocity](mw.Model.md#physicsangularvelocity)**(): [`Vector`](mw.Vector.md)   |
| 获取角速度(仅开启模拟时生效)|
| **[physicsEnabled](mw.Model.md#physicsenabled)**(): `boolean`   |
| 获取是否模拟物理|
| **[physicsLinearVelocity](mw.Model.md#physicslinearvelocity)**(): [`Vector`](mw.Vector.md)   |
| 获取线性速度(仅开启模拟时生效)|
| **[physicsMaterial](mw.Model.md#physicsmaterial)**(): `boolean`   |
| 获取物理材质启用状态|
| **[queryEnabled](mw.Model.md#queryenabled)**(): `boolean`   |
| 是否开启空间查询|
| **[restitution](mw.Model.md#restitution)**(): `number`   |
| 获取弹力大小|
| **[touchEnabled](mw.Model.md#touchenabled)**(): `boolean`   |
| Touched和TouchEnded事件是否在模型上触发。|


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
| **[addAngularImpulse](mw.Model.md#addangularimpulse)**(`impulse`: [`Vector`](mw.Vector.md), `velChange?`: `boolean`): `void`   |
| :-----|
| 给开启物理模拟的模型添加一个角冲量|
| **[addForce](mw.Model.md#addforce)**(`force`: [`Vector`](mw.Vector.md), `velChange?`: `boolean`): `void`   |
| 给开启物理模拟的模型添加一个力|
| **[addImpulse](mw.Model.md#addimpulse)**(`impulse`: [`Vector`](mw.Vector.md), `velChange?`: `boolean`): `void`   |
| 给开启物理模拟的模型添加一个冲量力|
| **[addTorque](mw.Model.md#addtorque)**(`torque`: [`Vector`](mw.Vector.md), `velChange?`: `boolean`): `void`   |
| 给开启物理模拟的模型添加一个扭力|
| **[createMaterialInstance](mw.Model.md#creatematerialinstance)**(`Index`: `number`): `void`   |
| 创建材质实例|
| **[getAllMaterialSlots](mw.Model.md#getallmaterialslots)**(): [`MaterialSlot`](mw.MaterialSlot.md)[]   |
| 获取所有材质插槽|
| **[getMaterialInstance](mw.Model.md#getmaterialinstance)**(): [`MaterialInstance`](mw.MaterialInstance.md)[]   |
| 返回当前拥有的材质实例|
| **[getMaterialSlot](mw.Model.md#getmaterialslot)**(`index`: `number`): [`MaterialSlot`](mw.MaterialSlot.md)   |
| 获取指定索引的材质插槽|
| **[resetMaterial](mw.Model.md#resetmaterial)**(`index?`: `number`): `void`   |
| 还原物体材质|
| **[setCullDistance](mw.Model.md#setculldistance)**(`inCullDistance`: `number`): `void` <Badge type="tip" text="client" />  |
| 与玩家之间超出此距离的对象将被剪裁|
| **[setMaterial](mw.Model.md#setmaterial)**(`MaterialGUID`: `string`): `void`   |
| 设置物体材质|
| **[setOutline](mw.Model.md#setoutline)**(`enabled`: `boolean`, `color?`: [`LinearColor`](mw.LinearColor.md), `width?`: `number`): `void`   |
| 设置对象描边及描边颜色|
| **[setPostProcessOutline](mw.Model.md#setpostprocessoutline)**(`enabled`: `boolean`, `color?`: [`LinearColor`](mw.LinearColor.md), `width?`: `number`): `void`   |
| 设置对象描边及描边颜色。|
| **[setStaticMeshAsset](mw.Model.md#setstaticmeshasset)**(`InAssetGuid`: `string`): `void`   |
| 设置静态网格资源|


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

### angularDamping <Score text="angularDamping" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **angularDamping**(): `number` 

</th>
<th style="text-align: left">

• `set` **angularDamping**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


角阻尼

#### Returns

| `number` | 角阻尼大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角阻尼

#### Parameters

| `value` `number` | 角阻尼大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### canAffectNavigation <Score text="canAffectNavigation" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **canAffectNavigation**(): `boolean`

</th>
<th style="text-align: left">

• `set` **canAffectNavigation**(`bInStatus`): `void` <Badge type="tip" text="other" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取模型碰撞是否影响动态寻路的导航数据

#### Returns

| `boolean` | 是否影响导航数据 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置模型碰撞是否影响动态寻路的导航数据

#### Parameters

| `bInStatus` `boolean` | 是否影响导航数据 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### castShadow <Score text="castShadow" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **castShadow**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **castShadow**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否开启阴影

#### Returns

| `boolean` | 阴影开启状态 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置阴影开启状态

#### Parameters

| `value` `boolean` | 阴影开启状态 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### centerOfMass <Score text="centerOfMass" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **centerOfMass**(): [`Vector`](mw.Vector.md) 

</th>
<th style="text-align: left">

• `set` **centerOfMass**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取质心偏移

质心是物体质量的中心，对质心进行偏移时，会影响物体在运动时的形态，但不会影响物体自身的变换

#### Returns

| [`Vector`](mw.Vector.md) | 质心偏移 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置质心偏移

质心是物体质量的中心，对质心进行偏移时，会影响物体在运动时的形态，但不会影响物体自身的变换

#### Parameters

| `value` [`Vector`](mw.Vector.md) | 质心偏移 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### collisionEnabled <Score text="collisionEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **collisionEnabled**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **collisionEnabled**(`status`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


是否开启碰撞

#### Returns

| `boolean` | 是否开启碰撞 |
| :------ | :------ |


</td>
<td style="text-align: left">


模型是否与其它对象进行碰撞交互。当值为false时，其它对象可以穿过模型而不被其阻挡。

::: warning Precautions

建议双端物体设置碰撞，单端物体设置碰撞可能会导致拉扯的情况

:::


#### Parameters

| `status` `boolean` |  是否与其它对象进行碰撞交互 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:
</span>

在场景中拖入一个方块，并创建一个名为Collision的脚本挂载在该方块下，并复制以下代码进入脚本。
预期效果：进入游戏按1键，角色可以穿过方块，再按1键，角色无法穿过方块。
```ts
@Component
export default class Collision extends Script {
    protected onStart(): void {

        if ( SystemUtil.isClient() ) {

            InputUtil.onKeyDown(Keys.One, () => {
                this.serverSetCollisionEnabled();
            })

        }
    }

    @RemoteFunction(Server)
    serverSetCollisionEnabled() {
        let model = this.gameObject as Model;
        model.collisionEnabled = !model.collisionEnabled;
    }
}
```
___

### collisionGroup <Score text="collisionGroup" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **collisionGroup**(): `string` 

</th>
<th style="text-align: left">

• `set` **collisionGroup**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取对应的碰撞组

#### Returns

| `string` | 对应碰撞组 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置碰撞组

#### Parameters

| `value` `string` | 碰撞组 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### color <Score text="color" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **color**(): [`LinearColor`](mw.LinearColor.md) 

</th>
<th style="text-align: left">

• `set` **color**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


Model颜色

#### Returns

| [`LinearColor`](mw.LinearColor.md) | Model颜色 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置Model的颜色

#### Parameters

| `value` [`LinearColor`](mw.LinearColor.md) | Model颜色 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### density <Score text="density" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **density**(): `number` 

</th>
<th style="text-align: left">

• `set` **density**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取密度大小

#### Returns

| `number` | 密度大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置密度大小

#### Parameters

| `value` `number` | 密度大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### friction <Score text="friction" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **friction**(): `number` 

</th>
<th style="text-align: left">

• `set` **friction**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取摩擦力大小

#### Returns

| `number` | 摩擦力大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置摩擦力大小

#### Parameters

| `value` `number` | 摩擦力大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### gravityEnabled <Score text="gravityEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **gravityEnabled**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **gravityEnabled**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否启用重力

#### Returns

| `boolean` | 重力是否启用 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否启用重力

#### Parameters

| `value` `boolean` | 重力是否启用 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### linerDamping <Score text="linerDamping" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **linerDamping**(): `number` 

</th>
<th style="text-align: left">

• `set` **linerDamping**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取线性阻尼

#### Returns

| `number` | 线性阻尼大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置线性阻尼

#### Parameters

| `value` `number` | 线性阻尼大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### lockPositionX <Score text="lockPositionX" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **lockPositionX**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **lockPositionX**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否约束位置X

#### Returns

| `boolean` | 是否约束位置X |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否约束位置X

#### Parameters

| `value` `boolean` | 是否约束位置X |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### lockPositionY <Score text="lockPositionY" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **lockPositionY**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **lockPositionY**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否约束位置Y

#### Returns

| `boolean` | 是否约束位置Y |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否约束位置Y

#### Parameters

| `value` `boolean` | 是否约束位置Y |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### lockPositionZ <Score text="lockPositionZ" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **lockPositionZ**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **lockPositionZ**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否约束位置Z

#### Returns

| `boolean` | 是否约束位置Z |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否约束位置Z

#### Parameters

| `value` `boolean` | 是否约束位置Z |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### lockRotationX <Score text="lockRotationX" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **lockRotationX**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **lockRotationX**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否约束旋转X

#### Returns

| `boolean` | 是否约束旋转X |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否约束旋转X

#### Parameters

| `value` `boolean` | 是否约束旋转X |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### lockRotationY <Score text="lockRotationY" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **lockRotationY**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **lockRotationY**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否约束旋转Y

#### Returns

| `boolean` | 是否约束旋转Y |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否约束旋转Y

#### Parameters

| `value` `boolean` | 是否约束旋转Y |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### lockRotationZ <Score text="lockRotationZ" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **lockRotationZ**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **lockRotationZ**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否约束旋转Z

#### Returns

| `boolean` | 是否约束旋转Z |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否约束旋转Z

#### Parameters

| `value` `boolean` | 是否约束旋转Z |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### mass <Score text="mass" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **mass**(): `number` 

</th>
<th style="text-align: left">

• `set` **mass**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取质量大小

#### Returns

| `number` | 质量大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置质量大小

#### Parameters

| `value` `number` | 质量大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### massEnabled <Score text="massEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **massEnabled**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **massEnabled**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否使用质量

#### Returns

| `boolean` | 是否使用质量 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否启用质量

#### Parameters

| `value` `boolean` | 是否启用质量 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### onTouch <Score text="onTouch" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onTouch**(): [`MulticastGameObjectDelegate`](mw.MulticastGameObjectDelegate.md)

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


进入Model事件

#### Returns

| [`MulticastGameObjectDelegate`](mw.MulticastGameObjectDelegate.md) |  |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onTouchEnd <Score text="onTouchEnd" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onTouchEnd**(): [`MulticastGameObjectDelegate`](mw.MulticastGameObjectDelegate.md)

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


离开Model事件

#### Returns

| [`MulticastGameObjectDelegate`](mw.MulticastGameObjectDelegate.md) |  |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### opacity <Score text="opacity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **opacity**(): `number` 

</th>
<th style="text-align: left">

• `set` **opacity**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取模型单层透明度

#### Returns

| `number` | 获取透明度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置模型单层透明度

#### Parameters

| `value` `number` | 透明度[0,1] |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### physicsAngularVelocity <Score text="physicsAngularVelocity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **physicsAngularVelocity**(): [`Vector`](mw.Vector.md) 

</th>
<th style="text-align: left">

• `set` **physicsAngularVelocity**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角速度(仅开启模拟时生效)

#### Returns

| [`Vector`](mw.Vector.md) | 物理角速度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置需要叠加的角速度(仅开启模拟时生效)

#### Parameters

| `value` [`Vector`](mw.Vector.md) | 物理角速度大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### physicsEnabled <Score text="physicsEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **physicsEnabled**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **physicsEnabled**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否模拟物理

#### Returns

| `boolean` | 物理模拟启用状态 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置模拟物理状态

#### Parameters

| `value` `boolean` | 物理模拟状态 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### physicsLinearVelocity <Score text="physicsLinearVelocity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **physicsLinearVelocity**(): [`Vector`](mw.Vector.md) 

</th>
<th style="text-align: left">

• `set` **physicsLinearVelocity**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取线性速度(仅开启模拟时生效)

#### Returns

| [`Vector`](mw.Vector.md) | 物理线速度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置需要叠加的线性速度(仅开启模拟时生效)

#### Parameters

| `value` [`Vector`](mw.Vector.md) | 物理线速度大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### physicsMaterial <Score text="physicsMaterial" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **physicsMaterial**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **physicsMaterial**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取物理材质启用状态

#### Returns

| `boolean` | 物理材质启用状态 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置物理材质启用状态

#### Parameters

| `value` `boolean` | 物理材质启用状态 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### queryEnabled <Score text="queryEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **queryEnabled**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **queryEnabled**(`status`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


是否开启空间查询

#### Returns

| `boolean` | 是否开启空间查询 |
| :------ | :------ |


</td>
<td style="text-align: left">


在空间查询模型是否纳入检测范围。当值为false时，不会被空间查询检测到。


#### Parameters

| `status` `boolean` |  在空间查询模型是否纳入检测范围。 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:
</span>

在场景中拖入一个方块，并创建一个名为Query的脚本挂载在该方块下，并复制以下代码进入脚本。
预期效果：按下1生成特效，被空间查询检测到，再按下1，特效被删除，没有被空间查询检测到。
```ts
@Component
export default class Query extends Script {
    effect : Effect

    protected onStart(): void {
        if ( SystemUtil.isClient() ) {
            InputUtil.onKeyDown(Keys.One, () => {
                this.serverSetQueryEnabled();
            })
        }
    }

    @RemoteFunction(Server)
    async serverSetQueryEnabled() {
        let model = this.gameObject as Model;

        let hitGameObjects = PhysicsService.sphereOverlap(this.gameObject.worldTransform.position, 30, {}, {});
        if (hitGameObjects.length > 0) {
            const success = await AssetUtil.asyncDownloadAsset("4391");
            if (success) {
                const transform = model.worldTransform.clone();
                transform.position.add(new Vector(0, 0, 150));

                GameObject.asyncSpawn("4391", {
                    replicates: true,
                    transform: transform
                }).then((effect : Effect) => {
                    this.effect = effect
                    // 播放特效
                    effect.play();
                });
            }
        }
        else {
            this.effect.destroy();
            this.effect = undefined;
        }

        model.queryEnabled = !model.queryEnabled;
    }
}
```
___

### restitution <Score text="restitution" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **restitution**(): `number` 

</th>
<th style="text-align: left">

• `set` **restitution**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取弹力大小

#### Returns

| `number` | 弹力大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置弹力大小

#### Parameters

| `value` `number` | 弹力大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### touchEnabled <Score text="touchEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **touchEnabled**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **touchEnabled**(`status`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


Touched和TouchEnded事件是否在模型上触发。

#### Returns

| `boolean` | Touched和TouchEnded事件是否在模型上触发。 |
| :------ | :------ |


</td>
<td style="text-align: left">


Touched和TouchEnded事件是否在模型上触发。当值为false时，对象在进行交互时不会抛出touch事件。


#### Parameters

| `status` `boolean` |  Touched和TouchEnded事件是否在模型上触发。 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:
</span>

在场景中拖入一个方块，并创建一个名为Touch的脚本挂载在该方块下，并复制以下代码进入脚本。
预期效果：角色走入方块，生成特效，走出方块，特效消失。按下1，角色走入走出方块无任何变化。
```ts
@Component
export default class Touch extends Script {
    effect : Effect

    protected onStart(): void {
        if ( SystemUtil.isClient() ) {
            InputUtil.onKeyDown(Keys.One, () => {
                this.serverSetTouchEnabled();
            })
        }

        if ( SystemUtil.isServer() ) {
            let model = this.gameObject as Model;
            model.collisionEnabled = false;
            model.onTouch.add(async () => {
                const success = await AssetUtil.asyncDownloadAsset("4391");
                if (success) {
                    const transform = model.worldTransform.clone();
                    transform.position.add(new Vector(0, 0, 150));

                    GameObject.asyncSpawn("4391", {
                        replicates: true,
                        transform: transform
                    }).then((effect : Effect) => {
                        this.effect = effect
                        // 播放特效
                        effect.play();
                    });
                }
            });
            model.onTouchEnd.add(() => {
                if (this.effect != undefined) {
                    this.effect.destroy();
                    this.effect = undefined;
                }
            });
        }
    }

    @RemoteFunction(Server)
    async serverSetTouchEnabled() {
        let model = this.gameObject as Model;
        model.touchEnabled = !model.touchEnabled;
    }
}
```


## Methods

### addAngularImpulse <Score text="addAngularImpulse" /> 

• **addAngularImpulse**(`impulse`, `velChange?`): `void` 

给开启物理模拟的模型添加一个角冲量

#### Parameters

| `impulse` [`Vector`](mw.Vector.md) | 设置角冲量大小和方向 |
| :------ | :------ |
| `velChange?` `boolean` | 是否忽视模型自身质量的影响 default:false 使用示例: 如下示例展示添加角冲量方法 ```ts if (model.physicsEnabled) `{ // 确保开启物理模拟 model.addAngularImpulse(new Vector(200,0,0), true); }` ``` |


___

### addForce <Score text="addForce" /> 

• **addForce**(`force`, `velChange?`): `void` 

给开启物理模拟的模型添加一个力

#### Parameters

| `force` [`Vector`](mw.Vector.md) | 设置力大小和方向 <br> default: null |
| :------ | :------ |
| `velChange?` `boolean` | 是否忽视模型自身质量的影响 <br> default:false 使用示例: 如下示例展示添加力方法 ```ts if (model.physicsEnabled) `{ // 确保开启物理模拟 model.addForce(new Vector(200,0,0), true); }` ``` |


___

### addImpulse <Score text="addImpulse" /> 

• **addImpulse**(`impulse`, `velChange?`): `void` 

给开启物理模拟的模型添加一个冲量力

#### Parameters

| `impulse` [`Vector`](mw.Vector.md) | 设置冲量力大小和方向 |
| :------ | :------ |
| `velChange?` `boolean` | 是否忽视模型自身质量的影响 default:false |


<span style="font-size: 14px;">
使用示例: 如下示例展示添加冲量力方法
</span>

```ts
if (model.physicsEnabled) {
     // 确保开启物理模拟
     model.addImpulse(new Vector(200,0,0), true);
}
```

___

### addTorque <Score text="addTorque" /> 

• **addTorque**(`torque`, `velChange?`): `void` 

给开启物理模拟的模型添加一个扭力

#### Parameters

| `torque` [`Vector`](mw.Vector.md) | 设置扭力大小和方向 <br> default: null |
| :------ | :------ |
| `velChange?` `boolean` | 是否忽视模型自身质量的影响 <br> default:false 使用示例: 如下示例展示添加扭力方法 ```ts if (model.physicsEnabled) `{ // 确保开启物理模拟 model.addTorque(new Vector(200,0,0), true); }` ``` |


___

### createMaterialInstance <Score text="createMaterialInstance" /> 

• **createMaterialInstance**(`Index`): `void` 

创建材质实例

#### Parameters

| `Index` `number` | 第几个材质 <br> range: 不超过材质数 type: 整形 |
| :------ | :------ |


___

### getAllMaterialSlots <Score text="getAllMaterialSlots" /> 

• **getAllMaterialSlots**(): [`MaterialSlot`](mw.MaterialSlot.md)[] 

获取所有材质插槽

#### Returns

| [`MaterialSlot`](mw.MaterialSlot.md)[] | 返回材质插槽数组 |
| :------ | :------ |

___

### getMaterialInstance <Score text="getMaterialInstance" /> 

• **getMaterialInstance**(): [`MaterialInstance`](mw.MaterialInstance.md)[] 

返回当前拥有的材质实例

#### Returns

| [`MaterialInstance`](mw.MaterialInstance.md)[] | 材质实例数组 |
| :------ | :------ |

该材质资源若未加载过，返回的材质实例无法立即取到材质属性，材质资源加载完成后即可通过材质实例获取正确的材质属性

___

### getMaterialSlot <Score text="getMaterialSlot" /> 

• **getMaterialSlot**(`index`): [`MaterialSlot`](mw.MaterialSlot.md) 

获取指定索引的材质插槽

#### Parameters

| `index` `number` | 材质插槽索引 type: Integer usage: 索引 range: 无 |
| :------ | :------ |

#### Returns

| [`MaterialSlot`](mw.MaterialSlot.md) | 返回指定索引的材质插槽 |
| :------ | :------ |

___

### resetMaterial <Score text="resetMaterial" /> 

• **resetMaterial**(`index?`): `void` 

还原物体材质

#### Parameters

| `index?` `number` |  材质索引序号 type: Integer default: undefined range: 无 |
| :------ | :------ |


___

### setCullDistance <Score text="setCullDistance" /> 

• **setCullDistance**(`inCullDistance`): `void` <Badge type="tip" text="client" />

与玩家之间超出此距离的对象将被剪裁

#### Parameters

| `inCullDistance` `number` | 裁剪距离 range: 建议 (2000, 4000) type: 浮点数 |
| :------ | :------ |


最终的裁剪距离会和画质等级有关；修改此属性 ≤0 时，裁剪距离会根据对象尺寸自动调整 (自动启用 CullDistanceVolume 功能)

::: warning Precautions

最终的裁剪距离会和画质等级有关

:::

___

### setMaterial <Score text="setMaterial" /> 

• **setMaterial**(`MaterialGUID`): `void` 

设置物体材质

#### Parameters

| `MaterialGUID` `string` |  材质 ID default: null range: 字符串长度依据材质资源 ID 长度而定 |
| :------ | :------ |


• **setMaterial**(`MaterialGUID`, `index`): `void` 

设置物体材质

#### Parameters

| `MaterialGUID` `string` |  材质 ID range: 字符串长度依据材质资源 ID 长度而定 |
| :------ | :------ |
| `index` `number` |  材质下标 range: 依据材质 ID 长度而定 type:整数 |


___

### setOutline <Score text="setOutline" /> 

• **setOutline**(`enabled`, `color?`, `width?`): `void` 

设置对象描边及描边颜色

#### Parameters

| `enabled` `boolean` |  是否开启描边 |
| :------ | :------ |
| `color?` [`LinearColor`](mw.LinearColor.md) |  设置描边颜色，与后处理中颜色 Index 对应，-1为无颜色。 default: mw.LinearColor.black |
| `width?` `number` |  设置描边宽度 default:2 range:[0, 100] type: 浮点数 |


需要场景中存在后处理对象。

___

### setPostProcessOutline <Score text="setPostProcessOutline" /> 

• **setPostProcessOutline**(`enabled`, `color?`, `width?`): `void` 

设置对象描边及描边颜色。

#### Parameters

| `enabled` `boolean` |  是否开启描边 |
| :------ | :------ |
| `color?` [`LinearColor`](mw.LinearColor.md) |  设置描边颜色，与后处理中颜色Index对应，-1为无颜色 default:mw.LinearColor.black |
| `width?` `number` |  设置描边宽度 default:2 range: [0, 4] type: 浮点数 |


___

### setStaticMeshAsset <Score text="setStaticMeshAsset" /> 

• **setStaticMeshAsset**(`InAssetGuid`): `void` 

设置静态网格资源

#### Parameters

| `InAssetGuid` `string` |  资源GUID range: 字符串长度依据资源 ID 长度而定 |
| :------ | :------ |

