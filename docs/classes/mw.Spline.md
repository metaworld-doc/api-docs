[玩法](../groups/玩法.玩法.md) / Spline

# Spline <Badge type="tip" text="Class" /> <Score text="Spline" />

样条线

## Hierarchy

- [`GameObject`](mw.GameObject.md)

  ↳ **`Spline`**

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
| **[color](mw.Spline.md#color)**(): [`LinearColor`](mw.LinearColor.md)   |
| :-----|
| 获取样条线颜色|
| **[loop](mw.Spline.md#loop)**(): `boolean`   |
| 获取是否自动闭合，起点和终点生成一条连接线|
| **[pointCount](mw.Spline.md#pointcount)**(): `number`   |
| 获取样条线点的数量|
| **[width](mw.Spline.md#width)**(): `number`   |
| 获取样条线的宽度|


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
| **[clearLinePoints](mw.Spline.md#clearlinepoints)**(): `void`   |
| :-----|
| 清空线条点|
| **[getArriveTangent](mw.Spline.md#getarrivetangent)**(`index`: `number`): [`Vector`](mw.Vector.md)   |
| 获取到达切线|
| **[getLeaveTangent](mw.Spline.md#getleavetangent)**(`index`: `number`): [`Vector`](mw.Vector.md)   |
| 获取离开切线|
| **[getPointPosition](mw.Spline.md#getpointposition)**(`index`: `number`): [`Vector`](mw.Vector.md)   |
| 获取线条中指定索引处的顶点位置|
| **[getPointRotation](mw.Spline.md#getpointrotation)**(`index`: `number`): [`Rotation`](mw.Rotation.md)   |
| 获取线条中指定索引处的顶点旋转|
| **[getPointType](mw.Spline.md#getpointtype)**(`index`: `number`): [`PointType`](../enums/mw.PointType.md)   |
| 获取线条类型|
| **[getPointXScale](mw.Spline.md#getpointxscale)**(`index`: `number`): `number`   |
| 获取线条中指定索引处的顶点X轴缩放|
| **[setArriveTangent](mw.Spline.md#setarrivetangent)**(`index`: `number`, `tangent`: [`Vector`](mw.Vector.md)): `void`   |
| 设置到达切线|
| **[setLeaveTangent](mw.Spline.md#setleavetangent)**(`index`: `number`, `tangent`: [`Vector`](mw.Vector.md)): `void`   |
| 设置离开切线|
| **[setPointPosition](mw.Spline.md#setpointposition)**(`index`: `number`, `position`: [`Vector`](mw.Vector.md)): `void`   |
| 设置线条中指定索引处的顶点位置|
| **[setPointRotation](mw.Spline.md#setpointrotation)**(`index`: `number`, `rotation`: [`Rotation`](mw.Rotation.md)): `void`   |
| 设置线条中指定索引处的顶点旋转|
| **[setPointType](mw.Spline.md#setpointtype)**(`index`: `number`, `type`: [`PointType`](../enums/mw.PointType.md)): `void`   |
| 设置线条类型|
| **[setPointXScale](mw.Spline.md#setpointxscale)**(`index`: `number`, `xScale`: `number`): `void`   |
| 设置线条中指定索引处的顶点X轴缩放|
| **[drawBox](mw.Spline.md#drawbox)**(`center`: [`Vector`](mw.Vector.md), `extent`: [`Vector`](mw.Vector.md), `color`: [`LinearColor`](mw.LinearColor.md), `rotation`: [`Rotation`](mw.Rotation.md), `duration`: `number`, `thickness`: `number`): `void` <Badge type="tip" text="client" />  |
| 绘制盒体|
| **[drawCapsule](mw.Spline.md#drawcapsule)**(`center`: [`Vector`](mw.Vector.md), `halfHeight`: `number`, `radius`: `number`, `rotation`: [`Rotation`](mw.Rotation.md), `color`: [`LinearColor`](mw.LinearColor.md), `duration`: `number`, `thickness`: `number`): `void` <Badge type="tip" text="client" />  |
| 绘制胶囊体|
| **[drawCircle](mw.Spline.md#drawcircle)**(`center`: [`Vector`](mw.Vector.md), `radius`: `number`, `segments`: `number`, `color`: [`LinearColor`](mw.LinearColor.md), `duration`: `number`, `thickness`: `number`, `yAxis?`: [`Vector`](mw.Vector.md), `zAxis?`: [`Vector`](mw.Vector.md), `drawAxis?`: `boolean`): `void` <Badge type="tip" text="client" />  |
| 绘制圆圈|
| **[drawLine](mw.Spline.md#drawline)**(`start`: [`Vector`](mw.Vector.md), `end`: [`Vector`](mw.Vector.md), `color`: [`LinearColor`](mw.LinearColor.md), `duration`: `number`, `thickness`: `number`): `void` <Badge type="tip" text="client" />  |
| 绘制线段|
| **[drawPoint](mw.Spline.md#drawpoint)**(`position`: [`Vector`](mw.Vector.md), `size`: `number`, `color`: [`LinearColor`](mw.LinearColor.md), `duration`: `number`): `void` <Badge type="tip" text="client" />  |
| 绘制点|
| **[drawSphere](mw.Spline.md#drawsphere)**(`center`: [`Vector`](mw.Vector.md), `radius`: `number`, `segments`: `number`, `color`: [`LinearColor`](mw.LinearColor.md), `duration`: `number`, `thickness`: `number`): `void` <Badge type="tip" text="client" />  |
| 绘制球体|


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


获取样条线颜色

#### Returns

| [`LinearColor`](mw.LinearColor.md) | 样条线颜色 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置样条线颜色

#### Parameters

| `value` [`LinearColor`](mw.LinearColor.md) | 样条线颜色 range: 无 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### loop <Score text="loop" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **loop**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **loop**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否自动闭合，起点和终点生成一条连接线

#### Returns

| `boolean` | 是否自动闭合 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否自动闭合，起点和终点生成一条连接线

#### Parameters

| `value` `boolean` | 是否自动闭合 range:[true,false] |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### pointCount <Score text="pointCount" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **pointCount**(): `number` 

</th>
<th style="text-align: left">

• `set` **pointCount**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取样条线点的数量

#### Returns

| `number` | 样条线点的数量 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置样条线点的数量

#### Parameters

| `value` `number` | 样条线点的数量 type: 整型 range: 无 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### width <Score text="width" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **width**(): `number` 

</th>
<th style="text-align: left">

• `set` **width**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取样条线的宽度

#### Returns

| `number` | 样条线宽度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置样样条线的宽度

#### Parameters

| `value` `number` | 样条线宽度 type: 浮点型 range: 无 |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods

___

### clearLinePoints <Score text="clearLinePoints" /> 

• **clearLinePoints**(): `void` 

清空线条点


___

### getArriveTangent <Score text="getArriveTangent" /> 

• **getArriveTangent**(`index`): [`Vector`](mw.Vector.md) 

获取到达切线

#### Parameters

| `index` `number` | 索引 type: 整型 range: 无 |
| :------ | :------ |

#### Returns

| [`Vector`](mw.Vector.md) | 到达切线 |
| :------ | :------ |

___

### getLeaveTangent <Score text="getLeaveTangent" /> 

• **getLeaveTangent**(`index`): [`Vector`](mw.Vector.md) 

获取离开切线

#### Parameters

| `index` `number` | 索引 type: 整型 range: 无 |
| :------ | :------ |

#### Returns

| [`Vector`](mw.Vector.md) | 离开切线 |
| :------ | :------ |

___

### getPointPosition <Score text="getPointPosition" /> 

• **getPointPosition**(`index`): [`Vector`](mw.Vector.md) 

获取线条中指定索引处的顶点位置

#### Parameters

| `index` `number` | 索引 type: 整型 range: 无 |
| :------ | :------ |

#### Returns

| [`Vector`](mw.Vector.md) | 顶点位置 |
| :------ | :------ |

___

### getPointRotation <Score text="getPointRotation" /> 

• **getPointRotation**(`index`): [`Rotation`](mw.Rotation.md) 

获取线条中指定索引处的顶点旋转

#### Parameters

| `index` `number` | 索引 type: 整型 range: 无 |
| :------ | :------ |

#### Returns

| [`Rotation`](mw.Rotation.md) | 顶点旋转 |
| :------ | :------ |

___

### getPointType <Score text="getPointType" /> 

• **getPointType**(`index`): [`PointType`](../enums/mw.PointType.md) 

获取线条类型

#### Parameters

| `index` `number` | 索引 type: 整型 range: 无 |
| :------ | :------ |

#### Returns

| [`PointType`](../enums/mw.PointType.md) | 顶点线条类型 |
| :------ | :------ |

___

### getPointXScale <Score text="getPointXScale" /> 

• **getPointXScale**(`index`): `number` 

获取线条中指定索引处的顶点X轴缩放

#### Parameters

| `index` `number` | 索引 type: 整型 range: 无 |
| :------ | :------ |

#### Returns

| `number` | 顶点X轴缩放 |
| :------ | :------ |

___

### setArriveTangent <Score text="setArriveTangent" /> 

• **setArriveTangent**(`index`, `tangent`): `void` 

设置到达切线

#### Parameters

| `index` `number` | 索引 type: 整型 range: 无 |
| :------ | :------ |
| `tangent` [`Vector`](mw.Vector.md) | 到达切线 |


___

### setLeaveTangent <Score text="setLeaveTangent" /> 

• **setLeaveTangent**(`index`, `tangent`): `void` 

设置离开切线

#### Parameters

| `index` `number` | 索引 type: 整型 range: 无 |
| :------ | :------ |
| `tangent` [`Vector`](mw.Vector.md) | 离开切线 |


___

### setPointPosition <Score text="setPointPosition" /> 

• **setPointPosition**(`index`, `position`): `void` 

设置线条中指定索引处的顶点位置

#### Parameters

| `index` `number` | 索引 type: 整型 range: 无 |
| :------ | :------ |
| `position` [`Vector`](mw.Vector.md) | 顶点位置 |


___

### setPointRotation <Score text="setPointRotation" /> 

• **setPointRotation**(`index`, `rotation`): `void` 

设置线条中指定索引处的顶点旋转

#### Parameters

| `index` `number` | 索引 type: 整型 range: 无 |
| :------ | :------ |
| `rotation` [`Rotation`](mw.Rotation.md) | 顶点旋转 |


___

### setPointType <Score text="setPointType" /> 

• **setPointType**(`index`, `type`): `void` 

设置线条类型

#### Parameters

| `index` `number` | 索引 type: 整型 range: 无 |
| :------ | :------ |
| `type` [`PointType`](../enums/mw.PointType.md) | 顶点线条类型 |


___

### setPointXScale <Score text="setPointXScale" /> 

• **setPointXScale**(`index`, `xScale`): `void` 

设置线条中指定索引处的顶点X轴缩放

#### Parameters

| `index` `number` | 索引 type: 整型 range: 无 |
| :------ | :------ |
| `xScale` `number` | 顶点X轴缩放 default:1 range: [0.01, 1000] type: 浮点型 |


___

### drawBox <Score text="drawBox" /> 

• `Static` **drawBox**(`center`, `extent`, `color`, `rotation`, `duration`, `thickness`): `void` <Badge type="tip" text="client" />

绘制盒体

#### Parameters

| `center` [`Vector`](mw.Vector.md) | 中心位置 |
| :------ | :------ |
| `extent` [`Vector`](mw.Vector.md) | 盒体范围 |
| `color` [`LinearColor`](mw.LinearColor.md) | 颜色 |
| `rotation` [`Rotation`](mw.Rotation.md) | 盒体朝向 |
| `duration` `number` | 持续时间 range: 无 type: 浮点型 |
| `thickness` `number` | 厚度 range: 无 type: 浮点型 |


<span style="font-size: 14px;">
使用示例: 可按如下操作控制编辑器后处理实时效果。创建一个名为"SplineExample"的脚本，放置在对象栏中，打开脚本，输入以下代码，运行游戏
</span>

```ts
@Component
export default class SplineExample extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected async onStart(): Promise<void> {
        if (SystemUtil.isClient()) {
            InputUtil.onKeyDown(Keys.One, () => {
                // 绘制点
                Spline.drawBox(Vector.zero, Vector.one, LinearColor.white, Rotation.zero, 1, 1);
            });
        }
    }
}
```

___

### drawCapsule <Score text="drawCapsule" /> 

• `Static` **drawCapsule**(`center`, `halfHeight`, `radius`, `rotation`, `color`, `duration`, `thickness`): `void` <Badge type="tip" text="client" />

绘制胶囊体

#### Parameters

| `center` [`Vector`](mw.Vector.md) | 中心位置 |
| :------ | :------ |
| `halfHeight` `number` | 胶囊体半高 range: 无 type: 浮点型 |
| `radius` `number` | 胶囊体半径 range: 无 type: 浮点型 |
| `rotation` [`Rotation`](mw.Rotation.md) | 胶囊体朝向 |
| `color` [`LinearColor`](mw.LinearColor.md) | 颜色 |
| `duration` `number` | 持续时间 range: 无 type: 浮点型 |
| `thickness` `number` | 厚度 range: 无 type: 浮点型 |


<span style="font-size: 14px;">
使用示例: 可按如下操作控制编辑器后处理实时效果。创建一个名为"SplineExample"的脚本，放置在对象栏中，打开脚本，输入以下代码，运行游戏
</span>

```ts
@Component
export default class SplineExample extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected async onStart(): Promise<void> {
        if (SystemUtil.isClient()) {
            InputUtil.onKeyDown(Keys.One, () => {
                // 绘制点
                Spline.drawCapsule(Vector.zero, 20, 10, Rotation.zero, LinearColor.white, 1, 1);
            });
        }
    }
}
```

___

### drawCircle <Score text="drawCircle" /> 

• `Static` **drawCircle**(`center`, `radius`, `segments`, `color`, `duration`, `thickness`, `yAxis?`, `zAxis?`, `drawAxis?`): `void` <Badge type="tip" text="client" />

绘制圆圈

#### Parameters

| `center` [`Vector`](mw.Vector.md) | 中心位置 |
| :------ | :------ |
| `radius` `number` | 半径 range: 无 type: 浮点型 |
| `segments` `number` | 段数 range: 无 type: 整形 |
| `color` [`LinearColor`](mw.LinearColor.md) | 颜色 default: |
| `duration` `number` | 持续时间 range: 无 type: 浮点型 |
| `thickness` `number` | 厚度 range: 无 type: 浮点型 |
| `yAxis?` [`Vector`](mw.Vector.md) | Y轴方向 default: undefined |
| `zAxis?` [`Vector`](mw.Vector.md) | Z轴方向 default: undefined |
| `drawAxis?` `boolean` | 是否绘制轴 range:[true,false] default: undefined |


<span style="font-size: 14px;">
使用示例: 可按如下操作控制编辑器后处理实时效果。创建一个名为"SplineExample"的脚本，放置在对象栏中，打开脚本，输入以下代码，运行游戏
</span>

```ts
@Component
export default class SplineExample extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected async onStart(): Promise<void> {
        if (SystemUtil.isClient()) {
            InputUtil.onKeyDown(Keys.One, () => {
                // 绘制点
                Spline.drawCircle(Vector.zero, 1, 4, LinearColor.white, 1, 1);
            });
        }
    }
}
```

___

### drawLine <Score text="drawLine" /> 

• `Static` **drawLine**(`start`, `end`, `color`, `duration`, `thickness`): `void` <Badge type="tip" text="client" />

绘制线段

#### Parameters

| `start` [`Vector`](mw.Vector.md) | 开始位置 |
| :------ | :------ |
| `end` [`Vector`](mw.Vector.md) | 结束位置 |
| `color` [`LinearColor`](mw.LinearColor.md) | 颜色 |
| `duration` `number` | 持续时间 range: 无 type: 浮点型 |
| `thickness` `number` | 厚度 range: 无 type: 浮点型 |


<span style="font-size: 14px;">
使用示例: 可按如下操作控制编辑器后处理实时效果。创建一个名为"SplineExample"的脚本，放置在对象栏中，打开脚本，输入以下代码，运行游戏
</span>

```ts
@Component
export default class SplineExample extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected async onStart(): Promise<void> {
        if (SystemUtil.isClient()) {
            InputUtil.onKeyDown(Keys.One, () => {
                // 绘制点
                Spline.drawLine(Vector.zero, Vector.one, LinearColor.white, 1, 1);
            });
        }
    }
}
```

___

### drawPoint <Score text="drawPoint" /> 

• `Static` **drawPoint**(`position`, `size`, `color`, `duration`): `void` <Badge type="tip" text="client" />

绘制点

#### Parameters

| `position` [`Vector`](mw.Vector.md) | 位置 |
| :------ | :------ |
| `size` `number` | 尺寸 range: 无 type: 浮点型 |
| `color` [`LinearColor`](mw.LinearColor.md) | 颜色 |
| `duration` `number` | 持续时间 range: 无 type: 浮点型 |


<span style="font-size: 14px;">
使用示例: 可按如下操作控制编辑器后处理实时效果。创建一个名为"SplineExample"的脚本，放置在对象栏中，打开脚本，输入以下代码，运行游戏
</span>

```ts
@Component
export default class SplineExample extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected async onStart(): Promise<void> {
        if (SystemUtil.isClient()) {
            InputUtil.onKeyDown(Keys.One, () => {
                // 绘制点
                Spline.drawPoint(Vector.zero, 1, LinearColor.white, 1);
            });
        }
    }
}
```

___

### drawSphere <Score text="drawSphere" /> 

• `Static` **drawSphere**(`center`, `radius`, `segments`, `color`, `duration`, `thickness`): `void` <Badge type="tip" text="client" />

绘制球体

#### Parameters

| `center` [`Vector`](mw.Vector.md) | 中心位置 |
| :------ | :------ |
| `radius` `number` | 半径 range: 无 type: 浮点型 |
| `segments` `number` | 段数 range: 无 type: 整形 |
| `color` [`LinearColor`](mw.LinearColor.md) | 颜色 |
| `duration` `number` | 持续时间 range: 无 type: 浮点型 |
| `thickness` `number` | 厚度 range: 无 type: 浮点型 |


<span style="font-size: 14px;">
使用示例: 可按如下操作控制编辑器后处理实时效果。创建一个名为"SplineExample"的脚本，放置在对象栏中，打开脚本，输入以下代码，运行游戏
</span>

```ts
@Component
export default class SplineExample extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected async onStart(): Promise<void> {
        if (SystemUtil.isClient()) {
            InputUtil.onKeyDown(Keys.One, () => {
                // 绘制点
                Spline.drawSphere(Vector.zero, 1, 4, LinearColor.white, 1, 1);
            });
        }
    }
}
```
