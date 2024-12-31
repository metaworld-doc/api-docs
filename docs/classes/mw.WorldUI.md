[界面](../groups/界面.界面.md) / WorldUI

# WorldUI <Badge type="tip" text="Class" /> <Score text="WorldUI" />

世界 UI

----------------------

1. UI 界面分为两种：屏幕 UI 和世界 UI。

WorldUI 是专门用来制作世界 UI 的。屏幕 UI 的详细制作方式请参考 UIService 或 UserWidget。

2. WorldUI 有两种方式制作世界 UI ：

- :cactus: 动态加载（只使用代码动态创建一个世界 UI）

<span style="font-size: 14px;">
使用示例: 创建一个名为 WorldUI 的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，会在场景中生成一个世界 UI - 滑动条
</span>

```ts
@Component
export default class WorldUI extends Script {

    user:UserWidget;
    widget:WorldUI;
    progressBar:ProgressBar;

    protected onStart(): void {
        if(SystemUtil.isClient()){
            this.creatUI();
            this.widget = GameObject.spawn<WorldUI>("WorldUI",{replicates:false});
            this.widget.worldTransform.position = new Vector(0,0,100);
            this.widget.setTargetUIWidget(this.user);
        }
    }

    public creatUI(){
        this.user = UserWidget.newObject();

        let rootCanvas = Canvas.newObject();
        rootCanvas.position = Vector2.zero;
        this.user.rootContent = rootCanvas;

        this.progressBar = ProgressBar.newObject(rootCanvas);
    }
}
```

- :cactus: 在对象管理器中提前在物体上挂载世界 UI 逻辑对象，在属性面板中放置对应的 UIPrefab。

## Hierarchy

- [`GameObject`](mw.GameObject.md)

  ↳ **`WorldUI`**

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
| **[alwaysFaceCamera](mw.WorldUI.md#alwaysfacecamera)**(): `boolean` <Badge type="tip" text="client" />  |
| :-----|
| 获取是否保持朝向相机|
| **[alwaysOnTop](mw.WorldUI.md#alwaysontop)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取是否保持最上显示|
| **[brightness](mw.WorldUI.md#brightness)**(): `number` <Badge type="tip" text="client" />  |
| 获取亮度值|
| **[distanceScaleEnabled](mw.WorldUI.md#distancescaleenabled)**(): `boolean`  |
| 获取是否开启近大远小|
| **[distanceScaleFactor](mw.WorldUI.md#distancescalefactor)**(): `number`  |
| 获取缩放距离系数|
| **[lightInfluence](mw.WorldUI.md#lightinfluence)**(): `number` <Badge type="tip" text="client" />  |
| 获取光照影响|
| **[maxVisibleDistance](mw.WorldUI.md#maxvisibledistance)**(): `number`  |
| 获取最大UI可见距离|
| **[maxVisibleDistanceEnabled](mw.WorldUI.md#maxvisibledistanceenabled)**(): `boolean`  |
| 获取是否启用最大可见距离|
| **[occlusionEnable](mw.WorldUI.md#occlusionenable)**(): `boolean`  |
| 获取是否可被遮挡|
| **[pivot](mw.WorldUI.md#pivot)**(): [`Vector2`](mw.Vector2.md)  |
| 获取锚点位置|
| **[spaceMode](mw.WorldUI.md#spacemode)**(): [`SpaceMode`](../enums/mw.SpaceMode.md)  |
| 获取显示方式|
| **[touchEnable](mw.WorldUI.md#touchenable)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取世界UI交互状态|
| **[zOrder](mw.WorldUI.md#zorder)**(): `number` <Badge type="tip" text="client" />  |
| 获取渲染层级，较高渲染层级的对象会优先显示在离视线较近的地方|


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
| **[getTargetUIWidget](mw.WorldUI.md#gettargetuiwidget)**(): [`UserWidget`](mw.UserWidget.md) <Badge type="tip" text="client" />  |
| :-----|
| 获取UI对象资源|
| **[refresh](mw.WorldUI.md#refresh)**(): `void` <Badge type="tip" text="client" />  |
| 请求重新绘制|
| **[setTargetUIWidget](mw.WorldUI.md#settargetuiwidget)**(`uiUserWidget`: [`UserWidget`](mw.UserWidget.md)): `void` <Badge type="tip" text="client" />  |
| 设置UI，可以对当前的UI设置UI资源，UI资源可以从路径获取或直接取其他UI组件引用的资源|
| **[setUIbyID](mw.WorldUI.md#setuibyid)**(`ID`: `string`): `void` <Badge type="tip" text="client" />  |
| 通过 GUID 设置 UI|


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

### alwaysFaceCamera <Score text="alwaysFaceCamera" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **alwaysFaceCamera**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **alwaysFaceCamera**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否保持朝向相机

::: warning Precautions

请在客户端调用，世界空间类型专用

:::

#### Returns

| `boolean` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否保持朝向相机

::: warning Precautions

请在客户端调用，世界空间类型专用

:::

#### Parameters

| `value` `boolean` |  UI是否保持朝向相机 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### alwaysOnTop <Score text="alwaysOnTop" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **alwaysOnTop**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **alwaysOnTop**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否保持最上显示

::: warning Precautions

请在客户端调用，世界空间类型专用

:::

#### Returns

| `boolean` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否保持最上显示

::: warning Precautions

请在客户端调用，世界空间类型专用

:::

#### Parameters

| `value` `boolean` |  UI是否保持最上显示 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### brightness <Score text="brightness" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **brightness**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **brightness**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取亮度值

::: warning Precautions

请在客户端调用，世界空间类型专用

:::

#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


设置亮度

::: warning Precautions

请在客户端调用，世界空间类型专用

:::

#### Parameters

| `value` `number` |  UI亮度，值范围为 [0, 10] |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### distanceScaleEnabled <Score text="distanceScaleEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **distanceScaleEnabled**(): `boolean`

</th>
<th style="text-align: left">

• `set` **distanceScaleEnabled**(`Value`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否开启近大远小

::: warning Precautions

请在客户端调用，屏幕空间类型专用

:::

#### Returns

| `boolean` | true：开启 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否开启近大远小

::: warning Precautions

请在客户端调用，屏幕空间类型专用

:::

#### Parameters

| `Value` `boolean` | 布尔值 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### distanceScaleFactor <Score text="distanceScaleFactor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **distanceScaleFactor**(): `number`

</th>
<th style="text-align: left">

• `set` **distanceScaleFactor**(`Value`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取缩放距离系数

::: warning Precautions

请在客户端调用，屏幕空间类型专用

:::

#### Returns

| `number` | 距离系数 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置缩放距离系数

::: warning Precautions

请在客户端调用，屏幕空间类型专用

:::

#### Parameters

| `Value` `number` | 距离系数 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### lightInfluence <Score text="lightInfluence" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **lightInfluence**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **lightInfluence**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取光照影响

::: warning Precautions

请在客户端调用，世界空间类型专用

:::

#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


设置光照影响

::: warning Precautions

请在客户端调用，世界空间类型专用

:::

#### Parameters

| `value` `number` |  UI光照影响度，值范围为 [0, 1] |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### maxVisibleDistance <Score text="maxVisibleDistance" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **maxVisibleDistance**(): `number`

</th>
<th style="text-align: left">

• `set` **maxVisibleDistance**(`Value`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取最大UI可见距离

#### Returns

| `number` | 可见距离 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置最大UI可见距离

#### Parameters

| `Value` `number` | 可见距离 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### maxVisibleDistanceEnabled <Score text="maxVisibleDistanceEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **maxVisibleDistanceEnabled**(): `boolean`

</th>
<th style="text-align: left">

• `set` **maxVisibleDistanceEnabled**(`Value`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否启用最大可见距离

#### Returns

| `boolean` | true：开启 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否启用最大可见距离

#### Parameters

| `Value` `boolean` | 布尔值 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### occlusionEnable <Score text="occlusionEnable" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **occlusionEnable**(): `boolean`

</th>
<th style="text-align: left">

• `set` **occlusionEnable**(`Value`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否可被遮挡

::: warning Precautions

请在客户端调用，屏幕空间类型专用

:::

#### Returns

| `boolean` | true：可被遮挡 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否可被遮挡

::: warning Precautions

请在客户端调用，屏幕空间类型专用

:::

#### Parameters

| `Value` `boolean` | 布尔值 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### pivot <Score text="pivot" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **pivot**(): [`Vector2`](mw.Vector2.md)

</th>
<th style="text-align: left">

• `set` **pivot**(`position`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取锚点位置

#### Returns

| [`Vector2`](mw.Vector2.md) | 位置信息 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置锚点位置

#### Parameters

| `position` [`Vector2`](mw.Vector2.md) | 位置信息 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### spaceMode <Score text="spaceMode" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **spaceMode**(): [`SpaceMode`](../enums/mw.SpaceMode.md)

</th>
<th style="text-align: left">

• `set` **spaceMode**(`spaceMode`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取显示方式

#### Returns

| [`SpaceMode`](../enums/mw.SpaceMode.md) | 显示方式枚举 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置显示方式

#### Parameters

| `spaceMode` | [`SpaceMode`](../enums/mw.SpaceMode.md) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### touchEnable <Score text="touchEnable" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **touchEnable**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **touchEnable**(`touchEnable`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取世界UI交互状态

::: warning Precautions

对世界UI，头顶UI生效

:::

#### Returns

| `boolean` | 是否可交互 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置世界UI交互状态

::: warning Precautions

对世界UI，头顶UI生效

:::

#### Parameters

| `touchEnable` `boolean` | 是否可交互 |
| :------ | :------ |


是否设置成功


</td>
</tr></tbody>
</table>

___

### zOrder <Score text="zOrder" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **zOrder**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **zOrder**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取渲染层级，较高渲染层级的对象会优先显示在离视线较近的地方

::: warning Precautions

请在客户端调用

:::

#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


设置渲染层级，较高渲染层级的对象会优先显示在离视线较近的地方

::: warning Precautions

请在客户端调用

:::

#### Parameters

| `value` `number` |  新的渲染层级，值范围为 [0, 31] |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods

___

### getTargetUIWidget <Score text="getTargetUIWidget" /> 

• **getTargetUIWidget**(): [`UserWidget`](mw.UserWidget.md) <Badge type="tip" text="client" />

获取UI对象资源

#### Returns

| [`UserWidget`](mw.UserWidget.md) | UI对象资源 |
| :------ | :------ |

___

### refresh <Score text="refresh" /> 

• **refresh**(): `void` <Badge type="tip" text="client" />

请求重新绘制


___

### setTargetUIWidget <Score text="setTargetUIWidget" /> 

• **setTargetUIWidget**(`uiUserWidget`): `void` <Badge type="tip" text="client" />

设置UI，可以对当前的UI设置UI资源，UI资源可以从路径获取或直接取其他UI组件引用的资源

#### Parameters

| `uiUserWidget` [`UserWidget`](mw.UserWidget.md) | UI资源对象 |
| :------ | :------ |


___

### setUIbyID <Score text="setUIbyID" /> 

• **setUIbyID**(`ID`): `void` <Badge type="tip" text="client" />

通过 GUID 设置 UI

#### Parameters

| `ID` `string` | UI 的 ID range: 依据资源 Id 长度决定 |
| :------ | :------ |

