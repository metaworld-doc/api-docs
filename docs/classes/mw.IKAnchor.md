[玩法](../groups/玩法.玩法.md) / IKAnchor

# IKAnchor <Badge type="tip" text="Class" /> <Score text="IKAnchor" />

IK锚点

## Hierarchy

- [`GameObject`](mw.GameObject.md)

  ↳ **`IKAnchor`**

## Table of contents

### Properties <Score text="Properties" /> 
| **[onActivate](mw.IKAnchor.md#onactivate)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\>  |
| :-----|
| IK启用完成委托|
| **[onDeactivate](mw.IKAnchor.md#ondeactivate)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\>  |
| IK关闭完成委托|


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
| **[anchorType](mw.IKAnchor.md#anchortype)**(): [`IKPart`](../enums/mw.IKPart.md)   |
| :-----|
| 获取IK锚点类型|
| **[blendInTime](mw.IKAnchor.md#blendintime)**(): `number`   |
| 获取混入时间|
| **[blendOutTime](mw.IKAnchor.md#blendouttime)**(): `number`   |
| 获取混出时间|
| **[jointTarget](mw.IKAnchor.md#jointtarget)**(): [`Vector`](mw.Vector.md)   |
| 获取关节朝向|
| **[target](mw.IKAnchor.md#target)**(): `MWSysCharacter`   |
| 获取IK锚点激活的对象|
| **[weight](mw.IKAnchor.md#weight)**(): `number`   |
| 获取权重|


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
| **[active](mw.IKAnchor.md#active)**(`target`: [`Character`](mw.Character.md)): `void`   |
| :-----|
| 给指定用户激活IK功能|
| **[deactivate](mw.IKAnchor.md#deactivate)**(): `void`   |
| 关闭IK功能|
| **[autoEnableIK](mw.IKAnchor.md#autoenableik)**(`target`: [`Character`](mw.Character.md), `value`: `boolean`): `void`   |
| 设置指定角色对象自动IK状态|


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

### onActivate <Score text="onActivate" /> 

• **onActivate**: [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\>

IK启用完成委托

___

### onDeactivate <Score text="onDeactivate" /> 

• **onDeactivate**: [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\>

IK关闭完成委托

## Accessors

___

### anchorType <Score text="anchorType" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **anchorType**(): [`IKPart`](../enums/mw.IKPart.md) 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取IK锚点类型

#### Returns

| [`IKPart`](../enums/mw.IKPart.md) | IK锚点类型 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### blendInTime <Score text="blendInTime" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **blendInTime**(): `number` 

</th>
<th style="text-align: left">

• `set` **blendInTime**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取混入时间

#### Returns

| `number` | 混入时间 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置混入时间

#### Parameters

| `value` `number` | 混入时间 range: [0,99999] type:浮点数 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### blendOutTime <Score text="blendOutTime" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **blendOutTime**(): `number` 

</th>
<th style="text-align: left">

• `set` **blendOutTime**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取混出时间

#### Returns

| `number` | 混出时间 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置混入时间

#### Parameters

| `value` `number` | 混入时间 range: [0,99999] type:浮点数 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### jointTarget <Score text="jointTarget" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **jointTarget**(): [`Vector`](mw.Vector.md) 

</th>
<th style="text-align: left">

• `set` **jointTarget**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取关节朝向

#### Returns

| [`Vector`](mw.Vector.md) | 关节朝向 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置关节朝向

#### Parameters

| `value` [`Vector`](mw.Vector.md) | 关节朝向 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### target <Score text="target" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **target**(): `MWSysCharacter` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取IK锚点激活的对象

**`Retuns`**

IK锚点激活的对象

#### Returns

| `MWSysCharacter` |  |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### weight <Score text="weight" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **weight**(): `number` 

</th>
<th style="text-align: left">

• `set` **weight**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取权重

#### Returns

| `number` | 权重 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置权重

#### Parameters

| `value` `number` | 权重 range: [0,1] type:浮点数 |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods

### active <Score text="active" /> 

• **active**(`target`): `void` 

给指定用户激活IK功能

#### Parameters

| `target` [`Character`](mw.Character.md) | IK指定角色对象 |
| :------ | :------ |


___

### deactivate <Score text="deactivate" /> 

• **deactivate**(): `void` 

关闭IK功能


___

### autoEnableIK <Score text="autoEnableIK" /> 

• `Static` **autoEnableIK**(`target`, `value`): `void` 

设置指定角色对象自动IK状态

#### Parameters

| `target` [`Character`](mw.Character.md) | 指定角色对象 |
| :------ | :------ |
| `value` `boolean` | 自动IK激活状态 |

