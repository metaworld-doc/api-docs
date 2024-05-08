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
    protected async onStart(): `Promise`<`void`\> {
        // GUID根据实际情况填写，可在编辑器对象管理器内右键复制对象ID
        let WaterVolume = await GameObject.asyncFindGameObjectById(`GUID`) as WaterVolume;
        if(SystemUtil.isClient())
        {
            InputUtil.onKeyDown(Keys.F1,()=>{
                // F1键 通知获取流体摩擦力
                console.log("当前游泳区流体摩擦力为：" + WaterVolume.fluidFriction);
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
| **[onDestroyDelegate](mw.GameObject.md#ondestroydelegate)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\>   |
| :-----|
| 物体销毁后事件回调|
:::


### Accessors <Score text="Accessors" /> 
| **[divingEnabled](mw.WaterVolume.md#divingenabled)**(): `boolean`   |
| :-----|
| 获取潜水|
| **[flowAngle](mw.WaterVolume.md#flowangle)**(): `number`   |
| 获取水波角度|
| **[flowSpeed](mw.WaterVolume.md#flowspeed)**(): `number`   |
| 获取水波速度|
| **[flowTile](mw.WaterVolume.md#flowtile)**(): `number`   |
| 获取水波密度|
| **[fluidFriction](mw.WaterVolume.md#fluidfriction)**(): `number`   |
| 获取流体摩擦力|
| **[normalFlat](mw.WaterVolume.md#normalflat)**(): `number`   |
| 获取水波强度|
| **[surfaceColor](mw.WaterVolume.md#surfacecolor)**(): [`LinearColor`](mw.LinearColor.md)   |
| 获取水面颜色|
| **[transmittance](mw.WaterVolume.md#transmittance)**(): `number`   |
| 获取水体透明度|
| **[waterColor](mw.WaterVolume.md#watercolor)**(): [`LinearColor`](mw.LinearColor.md)   |
| 获取水体颜色|


::: details click
### Accessors <Score text="Accessors" /> 
| **[assetId](mw.GameObject.md#assetid)**(): `string`   |
| :-----|
| 获取当前物体使用资源的GUID|
| **[gameObjectId](mw.GameObject.md#gameobjectid)**(): `string`   |
| 获取物体的唯一标识（唯一标识一个对象的字符串）。|
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
| **[getBoundingBoxExtent](mw.GameObject.md#getboundingboxextent)**(`nonColliding?`: `boolean`, `includeFromChild?`: `boolean`, `outer?`: [`Vector`](mw.Vector.md)): [`Vector`](mw.Vector.md)   |
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
| **[getChildrenBoundingBoxCenter](mw.GameObject.md#getchildrenboundingboxcenter)**(`outer?`: [`Vector`](mw.Vector.md)): [`Vector`](mw.Vector.md)   |
| 获取所有子对象包围盒中心点(不包含父对象,父对象不可用返回[0,0,0])|
| **[getChildrenByName](mw.GameObject.md#getchildrenbyname)**(`name`: `string`): [`GameObject`](mw.GameObject.md)[]   |
| 通过名字查找所有的子物体|
| **[getComponent](mw.GameObject.md#getcomponent)**<`T`: extends [`Script`](mw.Script.md)<`T`\>\>(`constructor?`: (...`args`: `unknown`[]) => `T`: extends [`Script`](mw.Script.md)<`T`\>): `T`: extends [`Script`](mw.Script.md)<`T`\>   |
| 获取指定类型的组件|
| **[getComponentPropertys](mw.GameObject.md#getcomponentpropertys)**<`T`: extends [`Script`](mw.Script.md)<`T`\>\>(`constructor`: (...`args`: `unknown`[]) => `T`: extends [`Script`](mw.Script.md)<`T`\>): `Map`<`string`, `IPropertyOptions`\>   |
| 获取脚本组件属性|
| **[getComponents](mw.GameObject.md#getcomponents)**<`T`: extends [`Script`](mw.Script.md)<`T`\>\>(`constructor?`: (...`args`: `unknown`[]) => `T`: extends [`Script`](mw.Script.md)<`T`\>): `T`: extends [`Script`](mw.Script.md)<`T`\>[]   |
| 获取指定类型的所有组件|
| **[getVisibility](mw.GameObject.md#getvisibility)**(): `boolean`   |
| 获取物体是否被显示|
| **[setAbsolute](mw.GameObject.md#setabsolute)**(`absolutePosition?`: `boolean`, `absoluteRotation?`: `boolean`, `absoluteScale?`: `boolean`): `void`   |
| 设置物体localTransform是相对于父物体或者世界|
| **[setVisibility](mw.GameObject.md#setvisibility)**(`status`: `boolean`  [`PropertyStatus`](../enums/mw.PropertyStatus.md), `propagateToChildren?`: `boolean`): `void`   |
| 设置物体是否被显示|
| **[asyncFindGameObjectById](mw.GameObject.md#asyncfindgameobjectbyid)**(`gameObjectId`: `string`): `Promise`<[`GameObject`](mw.GameObject.md)\>   |
| 通过 gameObjectId 异步查找 GameObject|
| **[asyncGetGameObjectByPath](mw.GameObject.md#asyncgetgameobjectbypath)**(`path`: `string`): `Promise`<[`GameObject`](mw.GameObject.md)\>   |
| 通过路径异步查找物体|
| **[asyncSpawn](mw.GameObject.md#asyncspawn)**<`T`: extends [`GameObject`](mw.GameObject.md)<`T`\>\>(`assetId`: `string`, `gameObjectInfo?`: [`GameObjectInfo`](../interfaces/mw.GameObjectInfo.md)): `Promise`<`T`: extends [`GameObject`](mw.GameObject.md)<`T`\>\>   |
| 异步构造一个物体|
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

• `get` **flowAngle**(): `number` 

</th>
<th style="text-align: left">

• `set` **flowAngle**(`value`): `void` 

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

• `get` **flowSpeed**(): `number` 

</th>
<th style="text-align: left">

• `set` **flowSpeed**(`value`): `void` 

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

• `get` **flowTile**(): `number` 

</th>
<th style="text-align: left">

• `set` **flowTile**(`value`): `void` 

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

• `get` **normalFlat**(): `number` 

</th>
<th style="text-align: left">

• `set` **normalFlat**(`value`): `void` 

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


获取水面颜色

#### Returns

| [`LinearColor`](mw.LinearColor.md) | 当前游泳区水面颜色 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置水面颜色

#### Parameters

| `value` [`LinearColor`](mw.LinearColor.md) | 设置游泳区水面颜色 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### transmittance <Score text="transmittance" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **transmittance**(): `number` 

</th>
<th style="text-align: left">

• `set` **transmittance**(`value`): `void` 

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

___

### waterColor <Score text="waterColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **waterColor**(): [`LinearColor`](mw.LinearColor.md) 

</th>
<th style="text-align: left">

• `set` **waterColor**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取水体颜色

#### Returns

| [`LinearColor`](mw.LinearColor.md) | 当前游泳区水体颜色 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置水体颜色

#### Parameters

| `value` [`LinearColor`](mw.LinearColor.md) | 设置游泳区水体颜色 |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods