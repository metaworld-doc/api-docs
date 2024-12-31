[玩法](../groups/玩法.玩法.md) / WaterVolume

# WaterVolume <Badge type="tip" text="Class" /> <Score text="WaterVolume" />

水体区域

----------------------------------

拖入 WaterVolume 调整水体区域的大小，角色进入水体区域会切换成游泳状态。

<span style="font-size: 14px;">
使用示例:创建一个名为"WaterVolumeExample"的脚本，放置在对象栏中，打开脚本，输入以下代码，替换GUID保存，运行游戏，你将可以通过F1键获取角色是否处于该GUID对应的游泳区。
</span>

```ts
@Component
export default class WaterVolumeExample extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected async onStart(): Promise<void> {
        // GUID根据实际情况填写，可在编辑器对象管理器内右键复制对象ID
        let WaterVolume = await GameObject.asyncFindGameObjectById(`GUID`) as WaterVolume;
        if(SystemUtil.isClient())
        {
            InputUtil.onKeyDown(Keys.F1,()=>{
                // F1键 通知获取流体摩擦力
                console.log("当前游泳区流体摩擦力为：" + WaterVolume.fluidFriction);
            });
            InputUtil.onKeyDown(Keys.F2,()=>{
                // F2键 通知获取当前是否开启浮力
                if (WaterVolume.buoyancyEnabled) {
                    console.log("当前游泳区已开启浮力");
                } else {
                    console.log("当前游泳区未开启浮力");
                }
            });
            InputUtil.onKeyDown(Keys.F3,()=>{
                // F3键 通知获取液体密度（用于计算浮力）
                console.log("当前游泳区密度为：" + WaterVolume.density);
            });
        }
    }
}
```

## Hierarchy

- [`GameObject`](mw.GameObject.md)

  ↳ **`WaterVolume`**

## Table of contents

### Properties <Score text="Properties" /> 
| **[onEnter](mw.WaterVolume.md#onenter)**: [`MulticastGameObjectDelegate`](mw.MulticastGameObjectDelegate.md)  |
| :-----|
| 进入水体区域事件|
| **[onLeave](mw.WaterVolume.md#onleave)**: [`MulticastGameObjectDelegate`](mw.MulticastGameObjectDelegate.md)  |
| 离开水体区域事件|


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
| **[buoyancyEnabled](mw.WaterVolume.md#buoyancyenabled)**(): `boolean`   |
| :-----|
| 获取是否启用水体浮力|
| **[deepColor](mw.WaterVolume.md#deepcolor)**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="other" />  |
| 获取水体深层颜色|
| **[density](mw.WaterVolume.md#density)**(): `number`   |
| 获取水体密度（用于计算浮力大小）|
| **[divingEnabled](mw.WaterVolume.md#divingenabled)**(): `boolean`   |
| 获取潜水|
| **[flowAngle](mw.WaterVolume.md#flowangle)**(): `number` <Badge type="tip" text="client" />  |
| 获取水波角度|
| **[flowSpeed](mw.WaterVolume.md#flowspeed)**(): `number` <Badge type="tip" text="client" />  |
| 获取水波速度|
| **[flowTile](mw.WaterVolume.md#flowtile)**(): `number` <Badge type="tip" text="client" />  |
| 获取水波密度|
| **[fluidFriction](mw.WaterVolume.md#fluidfriction)**(): `number`   |
| 获取流体摩擦力|
| **[normalFlat](mw.WaterVolume.md#normalflat)**(): `number` <Badge type="tip" text="client" />  |
| 获取水波强度|
| **[preset](mw.WaterVolume.md#preset)**(): [`WaterPreset`](../enums/mw.WaterPreset.md) <Badge type="tip" text="client" />  |
| 获取预设,仅对面板值生效|
| **[surfaceColor](mw.WaterVolume.md#surfacecolor)**(): [`LinearColor`](mw.LinearColor.md)   |
| 获取水体浅层颜色|
| **[transmittance](mw.WaterVolume.md#transmittance)**(): `number` <Badge type="tip" text="client" />  |
| 获取水体透明度|


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

### onEnter <Score text="onEnter" /> 

• **onEnter**: [`MulticastGameObjectDelegate`](mw.MulticastGameObjectDelegate.md)

进入水体区域事件

___

### onLeave <Score text="onLeave" /> 

• **onLeave**: [`MulticastGameObjectDelegate`](mw.MulticastGameObjectDelegate.md)

离开水体区域事件

## Accessors

___

### buoyancyEnabled <Score text="buoyancyEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **buoyancyEnabled**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **buoyancyEnabled**(`newStatus`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否启用水体浮力

**`Default`**

false

#### Returns

| `boolean` | 当前游泳区是否启用水体浮力 |
| :------ | :------ |


</td>
<td style="text-align: left">


开启/关闭区域的浮力效果，在关闭时区域将不再提供"浮力"的物理模拟计算，以节省性能。

#### Parameters

| `newStatus` `boolean` | 设置游泳区是否启用水体浮力 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### deepColor <Score text="deepColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **deepColor**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="other" />

</th>
<th style="text-align: left">

• `set` **deepColor**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取水体深层颜色

#### Returns

| [`LinearColor`](mw.LinearColor.md) | 当前游泳区深层颜色 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置水体深层颜色

#### Parameters

| `value` [`LinearColor`](mw.LinearColor.md) | 设置游泳区深层颜色 |
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

• `set` **density**(`newDensity`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取水体密度（用于计算浮力大小）

**`Default`**

10

#### Returns

| `number` | 当前水体密度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置水体密度（用于计算浮力大小），密度越大，浮力越大。

取值范围 [0 - 10000]

#### Parameters

| `newDensity` `number` | 新的水体密度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### divingEnabled <Score text="divingEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **divingEnabled**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **divingEnabled**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取潜水

#### Returns

| `boolean` | 当前游泳区是否启用潜水 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置潜水

#### Parameters

| `value` `boolean` | 设置游泳区是否启用潜水 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### flowAngle <Score text="flowAngle" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **flowAngle**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **flowAngle**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取水波角度

#### Returns

| `number` | 当前游泳区水波角度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置水波角度

#### Parameters

| `value` `number` | 设置游泳区水波角度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### flowSpeed <Score text="flowSpeed" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **flowSpeed**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **flowSpeed**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取水波速度

#### Returns

| `number` | 当前游泳区水波速度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置水波速度

#### Parameters

| `value` `number` | 设置游泳区水波速度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### flowTile <Score text="flowTile" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **flowTile**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **flowTile**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取水波密度

#### Returns

| `number` | 当前游泳区水波密度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置水波密度

#### Parameters

| `value` `number` | 设置游泳区水波密度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### fluidFriction <Score text="fluidFriction" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **fluidFriction**(): `number` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取流体摩擦力

#### Returns

| `number` | 当前游泳区流体摩擦力 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### normalFlat <Score text="normalFlat" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **normalFlat**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **normalFlat**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取水波强度

#### Returns

| `number` | 当前游泳区水波强度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置水波强度

#### Parameters

| `value` `number` | 设置游泳区水波强度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### preset <Score text="preset" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **preset**(): [`WaterPreset`](../enums/mw.WaterPreset.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **preset**(`NewPreset`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取预设,仅对面板值生效

#### Returns

| [`WaterPreset`](../enums/mw.WaterPreset.md) | 返回预设 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置预设

#### Parameters

| `NewPreset` [`WaterPreset`](../enums/mw.WaterPreset.md) | 预设枚举 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### surfaceColor <Score text="surfaceColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **surfaceColor**(): [`LinearColor`](mw.LinearColor.md) 

</th>
<th style="text-align: left">

• `set` **surfaceColor**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取水体浅层颜色

#### Returns

| [`LinearColor`](mw.LinearColor.md) | 当前游泳区浅层颜色 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置水体浅层颜色

#### Parameters

| `value` [`LinearColor`](mw.LinearColor.md) | 设置游泳区浅层颜色 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### transmittance <Score text="transmittance" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **transmittance**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **transmittance**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取水体透明度

#### Returns

| `number` | 当前游泳区水体透明度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置水体透明度

#### Parameters

| `value` `number` | 设置游泳区水体透明度 |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods
