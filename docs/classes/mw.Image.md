[界面](../groups/界面.界面.md) / Image

# Image <Badge type="tip" text="Class" /> <Score text="Image" />

图片

## Hierarchy

- [`Widget`](mw.Widget.md)

  ↳ **`Image`**

## Table of contents

### Properties <Score text="Properties" /> 


::: details click
### Properties <Score text="Properties" /> 
| **[onCustomPropertyChange](mw.Widget.md#oncustompropertychange)**: `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> <Badge type="tip" text="client" />  |
| :-----|
| 监听自定义属性同步事件|
:::


### Accessors <Score text="Accessors" /> 
| **[currentCamera](mw.Image.md#currentcamera)**(): [`Camera`](mw.Camera.md) <Badge type="tip" text="client" />  |
| :-----|
| 获取当前渲染的摄像机|
| **[imageColor](mw.Image.md#imagecolor)**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />  |
| 获取图片的颜色|
| **[imageDrawType](mw.Image.md#imagedrawtype)**(): `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> <Badge type="tip" text="client" />  |
| 获取图片绘制类型|
| **[imageGuid](mw.Image.md#imageguid)**(): `string` <Badge type="tip" text="client" />  |
| 获取图片id|
| **[imageInfo](mw.Image.md#imageinfo)**(): [`ImageInfo`](mw.ImageInfo.md)  |
| 图片资源信息|
| **[imageSize](mw.Image.md#imagesize)**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />  |
| 获取图片大小|
| **[margin](mw.Image.md#margin)**(): `Readonly`<[`Margin`](mw.Margin.md)\>  |
| 获取图片边距|


::: details click
### Accessors <Score text="Accessors" /> 
| **[alignPosition](mw.Widget.md#alignposition)**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />  |
| :-----|
| 获取控件的对齐位置,在对齐方式为靠右对齐、靠下对齐、中心对齐时，alignPosition的值与positon不同；|
| **[autoSizeHorizontalEnable](mw.Widget.md#autosizehorizontalenable)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取是否自动水平设置大小|
| **[autoSizeVerticalEnable](mw.Widget.md#autosizeverticalenable)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取是否自动垂直设置大小|
| **[cachedGeometry](mw.Widget.md#cachedgeometry)**(): [`Geometry`](mw.Geometry.md) <Badge type="tip" text="client" />  |
| 获取上一次的GetTickSpaceGeometry|
| **[constraints](mw.Widget.md#constraints)**(): `Readonly`<[`UIConstraintAnchors`](mw.UIConstraintAnchors.md)\> <Badge type="tip" text="client" />  |
| 获取控件的布局|
| **[desiredSize](mw.Widget.md#desiredsize)**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />  |
| 获取期望大小|
| **[enable](mw.Widget.md#enable)**(): `boolean` <Badge type="tip" text="client" />  |
| 是否可用|
| **[guid](mw.Widget.md#guid)**(): `string` <Badge type="tip" text="client" />  |
| 获取控件GUID|
| **[isHovered](mw.Widget.md#ishovered)**(): `boolean` <Badge type="tip" text="client" />  |
| 是否是hovered|
| **[mouseCursor](mw.Widget.md#mousecursor)**(): [`MouseCursor`](../enums/mw.MouseCursor.md) <Badge type="tip" text="client" />  |
| 获取控件上光标类型|
| **[name](mw.Widget.md#name)**(): `string` <Badge type="tip" text="client" />  |
| 获取名字|
| **[paintSpaceGeometry](mw.Widget.md#paintspacegeometry)**(): [`Geometry`](mw.Geometry.md) <Badge type="tip" text="client" />  |
| 获取最后一次用于渲染Widget的几何信息|
| **[parent](mw.Widget.md#parent)**(): [`Widget`](mw.Widget.md) <Badge type="tip" text="client" />  |
| 获取父节点|
| **[pivot](mw.Widget.md#pivot)**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />  |
| 获取控件锚点位置,这个属性决定了控件图形与锚点的相对位置；(0,0)时，锚点位于控件左上角；(0.5,0.5)时，锚点位于控件正中心|
| **[position](mw.Widget.md#position)**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />  |
| 获取控件的位置|
| **[renderOpacity](mw.Widget.md#renderopacity)**(): `number` <Badge type="tip" text="client" />  |
| 获取渲染透明度|
| **[renderScale](mw.Widget.md#renderscale)**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />  |
| 获取渲染缩放|
| **[renderShear](mw.Widget.md#rendershear)**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />  |
| 获取渲染错切形变|
| **[renderTransformAngle](mw.Widget.md#rendertransformangle)**(): `number` <Badge type="tip" text="client" />  |
| 获取渲染的角度|
| **[renderTransformPivot](mw.Widget.md#rendertransformpivot)**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />  |
| 获取渲染锚点|
| **[size](mw.Widget.md#size)**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />  |
| 获取大小|
| **[tickSpaceGeometry](mw.Widget.md#tickspacegeometry)**(): [`Geometry`](mw.Geometry.md) <Badge type="tip" text="client" />  |
| 获取最后一次用于驱动Widget Tick的几何信息|
| **[transform](mw.Widget.md#transform)**(): `Readonly`<[`UITransform`](mw.UITransform.md)\> <Badge type="tip" text="client" />  |
| 得到控件的大小和位置|
| **[visibility](mw.Widget.md#visibility)**(): [`SlateVisibility`](../enums/mw.SlateVisibility.md) <Badge type="tip" text="client" />  |
| 获取可见性|
| **[visible](mw.Widget.md#visible)**(): `boolean` <Badge type="tip" text="client" />  |
| 是否可见|
| **[zOrder](mw.Widget.md#zorder)**(): `number` <Badge type="tip" text="client" />  |
| 获取zorder|
:::


### Methods <Score text="Methods" /> 
| **[asyncExportBlendBrush](mw.Image.md#asyncexportblendbrush)**(): `Promise`<`string`\> <Badge type="tip" text="client" />  |
| :-----|
| 将融合的图片导出为一张|
| **[getImageAssetIconData](mw.Image.md#getimageasseticondata)**(): `Readonly`<[`AssetIconData`](mw.AssetIconData.md)\> <Badge type="tip" text="client" />  |
| 获取显示资源的ICON|
| **[setImageByBlendMode](mw.Image.md#setimagebyblendmode)**(`backgroundPic`: `string`, `foregroundPic`: `string`): `void` <Badge type="tip" text="client" />  |
| 将两张图片融合叠加显示在图片组件上|
| **[setImageByBlendModeWithGUID](mw.Image.md#setimagebyblendmodewithguid)**(`GUID`: `string`, `foregroundPic`: `string`): `void` <Badge type="tip" text="client" />  |
| 将两张图片融合叠加显示在图片组件上|
| **[setImageByFile](mw.Image.md#setimagebyfile)**(`absPath`: `string`, `bRefreshCache?`: `boolean`): `void` <Badge type="tip" text="client" />  |
| 设置图片样式为本地图片文件|
| **[setImageColorByHex](mw.Image.md#setimagecolorbyhex)**(`inHexString`: `string`): `void` <Badge type="tip" text="client" />  |
| 设置图片颜色。|
| **[setImageColorDecimal](mw.Image.md#setimagecolordecimal)**(`R`: `number`, `G`: `number`, `B`: `number`, `A`: `number`): `void` <Badge type="tip" text="client" />  |
| 设置图片颜色|
| **[newObject](mw.Image.md#newobject)**(`parent?`: [`Canvas`](mw.Canvas.md), `inName?`: `string`): [`Image`](mw.Image.md) <Badge type="tip" text="client" />  |
| 创建 Image 控件|


::: details click
### Methods <Score text="Methods" /> 
| **[addChild](mw.Widget.md#addchild)**(`child`: [`Widget`](mw.Widget.md)): `void` <Badge type="tip" text="client" />  |
| :-----|
| 添加子节点|
| **[clone](mw.Widget.md#clone)**(`position`: [`Vector2`](mw.Vector2.md), `Parent?`: [`Widget`](mw.Widget.md)): [`Widget`](mw.Widget.md) <Badge type="tip" text="client" />  |
| 克隆UI控件及其子节点到指定父控件位置（默认到其父节点）|
| **[destroyObject](mw.Widget.md#destroyobject)**(): `void` <Badge type="tip" text="client" />  |
| 立刻移除并销毁 不可以在使用|
| **[equal](mw.Widget.md#equal)**(`that`: [`Widget`](mw.Widget.md)): `boolean` <Badge type="tip" text="client" />  |
| 判断是不是同一个对象|
| **[findChildByPath](mw.Widget.md#findchildbypath)**(`inPath`: `string`): [`Widget`](mw.Widget.md) <Badge type="tip" text="client" />  |
| 通过相对路径查找节点|
| **[getChildAt](mw.Widget.md#getchildat)**(`index`: `number`): [`Widget`](mw.Widget.md) <Badge type="tip" text="client" />  |
| 获取第几位子节点|
| **[getChildByName](mw.Widget.md#getchildbyname)**<`T`: extends [`Widget`](mw.Widget.md)<`T`\>\>(`name`: `string`): `T`: extends [`Widget`](mw.Widget.md)<`T`\> <Badge type="tip" text="client" />  |
| 通过名字查找节点|
| **[getChildrenCount](mw.Widget.md#getchildrencount)**(): `number` <Badge type="tip" text="client" />  |
| 获取子节点数量|
| **[getCustomProperties](mw.Widget.md#getcustomproperties)**(): `string`[] <Badge type="tip" text="client" />  |
| 获取所有自定义属性|
| **[getCustomProperty](mw.Widget.md#getcustomproperty)**<`T`: extends [`CustomPropertyType`](../modules/Core.mw.md#custompropertytype)\>(`propertyName`: `string`): `T`: extends [`CustomPropertyType`](../modules/Core.mw.md#custompropertytype) <Badge type="tip" text="client" />  |
| 获取自定义属性|
| **[getCustomPropertyChangeDelegate](mw.Widget.md#getcustompropertychangedelegate)**(`property`): `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> <Badge type="tip" text="client" />  |
| 给定对象属性修改时触发的事件代理|
| **[invalidateLayoutAndVolatility](mw.Widget.md#invalidatelayoutandvolatility)**(): `void` <Badge type="tip" text="client" />  |
| 立刻触发重新渲染的和排布计算|
| **[isValid](mw.Widget.md#isvalid)**(): `boolean` <Badge type="tip" text="client" />  |
| 判断控件有没有被销毁，是否是有效的控件|
| **[removeAllChildren](mw.Widget.md#removeallchildren)**(): `void` <Badge type="tip" text="client" />  |
| 清除所有子节点,会销毁UI无法再使用|
| **[removeChild](mw.Widget.md#removechild)**(`child`: [`Widget`](mw.Widget.md)): `void` <Badge type="tip" text="client" />  |
| 移除节点,会销毁UI无法在使用|
| **[removeChildAt](mw.Widget.md#removechildat)**(`index`: `number`): `void` <Badge type="tip" text="client" />  |
| 移除第几个节点,会销毁UI无法再使用|
| **[removeObject](mw.Widget.md#removeobject)**(): `void` <Badge type="tip" text="client" />  |
| 立刻移除并添加到根节点 可以再使用|
| **[serialize](mw.Widget.md#serialize)**(): `string` <Badge type="tip" text="client" />  |
| 序列化UI控件|
| **[setCustomProperty](mw.Widget.md#setcustomproperty)**(`propertyName`: `string`, `value`: `undefined`  [`CustomPropertyType`](../modules/Core.mw.md#custompropertytype)): `void` <Badge type="tip" text="client" />  |
| 设置自定义属性|
| **[deserialize](mw.Widget.md#deserialize)**(`Data`: `string`, `Parent?`: [`Widget`](mw.Widget.md)): [`Widget`](mw.Widget.md) <Badge type="tip" text="client" />  |
| 反序列化UI|
:::


## Properties

## Accessors

___

### currentCamera <Score text="currentCamera" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **currentCamera**(): [`Camera`](mw.Camera.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **currentCamera**(`camera`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取当前渲染的摄像机

#### Returns

| [`Camera`](mw.Camera.md) | 新的摄像机对象 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置当前渲染的摄像机

#### Parameters

| `camera` `string`  [`Camera`](mw.Camera.md) | 新的摄像机对象 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### imageColor <Score text="imageColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **imageColor**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **imageColor**(`inColor`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取图片的颜色

#### Returns

| `Readonly`<[`LinearColor`](mw.LinearColor.md)\> | 图片的颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置图片颜色

#### Parameters

| `inColor` [`LinearColor`](mw.LinearColor.md) | 图片颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |


颜色


</td>
</tr></tbody>
</table>

___

### imageDrawType <Score text="imageDrawType" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **imageDrawType**(): `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **imageDrawType**(`inDrawType`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取图片绘制类型

#### Returns

| `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> | 图片绘制类型 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置图片绘制类型

#### Parameters

| `inDrawType` [`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md) | 绘制类型 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### imageGuid <Score text="imageGuid" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **imageGuid**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **imageGuid**(`inGUID`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取图片id

#### Returns

| `string` | 图片id |
| :------ | :------ |


</td>
<td style="text-align: left">


设置图片id

#### Parameters

| `inGUID` `string` | 新的图片样式 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### imageInfo <Score text="imageInfo" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **imageInfo**(): [`ImageInfo`](mw.ImageInfo.md)

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


图片资源信息
@effect只在客户端调用生效

#### Returns

| [`ImageInfo`](mw.ImageInfo.md) |  |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### imageSize <Score text="imageSize" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **imageSize**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **imageSize**(`inSize`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取图片大小

#### Returns

| `Readonly`<[`Vector2`](mw.Vector2.md)\> | 图片大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置图片大小
@effect只在客户端调用生效

#### Parameters

| `inSize` [`Vector2`](mw.Vector2.md) | size |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### margin <Score text="margin" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **margin**(): `Readonly`<[`Margin`](mw.Margin.md)\>

</th>
<th style="text-align: left">

• `set` **margin**(`inMargin`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取图片边距
@effect只在客户端调用生效

#### Returns

| `Readonly`<[`Margin`](mw.Margin.md)\> | 图片边距 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置图片的边距
@effect只在客户端调用生效

#### Parameters

| `inMargin` [`Margin`](mw.Margin.md) | 图片边距 |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods

___

### asyncExportBlendBrush <Score text="asyncExportBlendBrush" /> 

• **asyncExportBlendBrush**(): `Promise`<`string`\> <Badge type="tip" text="client" />

将融合的图片导出为一张

#### Returns

| `Promise`<`string`\> | 导出的图片的本地路径 |
| :------ | :------ |

::: warning Precautions

必须调用过 setImageByBlendMode 后才会生效，高消耗操作注意

:::

___

### getImageAssetIconData <Score text="getImageAssetIconData" /> 

• **getImageAssetIconData**(): `Readonly`<[`AssetIconData`](mw.AssetIconData.md)\> <Badge type="tip" text="client" />

获取显示资源的ICON

#### Returns

| `Readonly`<[`AssetIconData`](mw.AssetIconData.md)\> | 资源的ICON信息 |
| :------ | :------ |

___

### setImageByBlendMode <Score text="setImageByBlendMode" /> 

• **setImageByBlendMode**(`backgroundPic`, `foregroundPic`): `void` <Badge type="tip" text="client" />

将两张图片融合叠加显示在图片组件上

#### Parameters

| `backgroundPic` `string` | 背景图片绝对路径 range:路径长度 |
| :------ | :------ |
| `foregroundPic` `string` | 前景图片绝对路径 range:路径长度 |


___

### setImageByBlendModeWithGUID <Score text="setImageByBlendModeWithGUID" /> 

• **setImageByBlendModeWithGUID**(`GUID`, `foregroundPic`): `void` <Badge type="tip" text="client" />

将两张图片融合叠加显示在图片组件上

#### Parameters

| `GUID` `string` | 背景图片 GUID range: 依据资源 ID 长度而定 |
| :------ | :------ |
| `foregroundPic` `string` | 前景图片绝对路径 range: 路径长度 |


___

### setImageByFile <Score text="setImageByFile" /> 

• **setImageByFile**(`absPath`, `bRefreshCache?`): `void` <Badge type="tip" text="client" />

设置图片样式为本地图片文件

#### Parameters

| `absPath` `string` |  图片绝对路径 range: 路径长度 |
| :------ | :------ |
| `bRefreshCache?` `boolean` |  默认为 true 将重新创建并刷新缓存，为 false 则使用缓存 <br> default: true |


::: warning Precautions

1. 建议设置 bRefreshCache = false 以提升性能  2. 该接口主要配合 setImageByBlendMode 和 asyncExportBlendBrush 来为移动编辑器服务的

:::

___

### setImageColorByHex <Score text="setImageColorByHex" /> 

• **setImageColorByHex**(`inHexString`): `void` <Badge type="tip" text="client" />

设置图片颜色。

#### Parameters

| `inHexString` `string` |  Hex 颜色字符串。 <br> range: 符合 Hex 特点的字符串类型 |
| :------ | :------ |


指定 Hex 的颜色文本设定颜色 例如: #05050505

___

### setImageColorDecimal <Score text="setImageColorDecimal" /> 

• **setImageColorDecimal**(`R`, `G`, `B`, `A`): `void` <Badge type="tip" text="client" />

设置图片颜色

#### Parameters

| `R` `number` | 图片 R 值。 <br> range:[0, 255] type: 整形 |
| :------ | :------ |
| `G` `number` | 图片 G 值。 <br> range:[0, 255] type: 整形 |
| `B` `number` | 图片 B 值。 <br> range:[0, 255] type: 整形 |
| `A` `number` | 图片 透明度。 <br> range:[0, 255] type: 整形 |


___

### newObject <Score text="newObject" /> 

• `Static` **newObject**(`parent?`, `inName?`): [`Image`](mw.Image.md) <Badge type="tip" text="client" />

创建 Image 控件

#### Parameters

| `parent?` [`Canvas`](mw.Canvas.md) | 创建控件的外parent对象 default:null |
| :------ | :------ |
| `inName?` `string` | 创建控件的名称 default:null range:设置合理的名称即可 |

#### Returns

| [`Image`](mw.Image.md) | 返回创建的对象 |
| :------ | :------ |

当parent和inName与已有的对象相同时，旧的对象会被销毁
