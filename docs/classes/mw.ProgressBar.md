[界面](../groups/界面.界面.md) / ProgressBar

# ProgressBar <Badge type="tip" text="Class" /> <Score text="ProgressBar" />

进度条

## Hierarchy

- [`Widget`](mw.Widget.md)

  ↳ **`ProgressBar`**

## Table of contents

### Properties <Score text="Properties" /> 


::: details click
### Properties <Score text="Properties" /> 
| **[onCustomPropertyChange](mw.Widget.md#oncustompropertychange)**: `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> <Badge type="tip" text="client" />  |
| :-----|
| 监听自定义属性同步事件|
:::


### Accessors <Score text="Accessors" /> 
| **[backgroundImageColor](mw.ProgressBar.md#backgroundimagecolor)**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />  |
| :-----|
| 获取背景图片颜色|
| **[backgroundImageDrawType](mw.ProgressBar.md#backgroundimagedrawtype)**(): `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> <Badge type="tip" text="client" />  |
| 获取背景图片绘制类型|
| **[backgroundImageGuid](mw.ProgressBar.md#backgroundimageguid)**(): `string` <Badge type="tip" text="client" />  |
| 获取背景图片id|
| **[backgroundImageMargin](mw.ProgressBar.md#backgroundimagemargin)**(): `Readonly`<[`Margin`](mw.Margin.md)\> <Badge type="tip" text="client" />  |
| 获取进度条背景图片边距|
| **[backgroundImageSize](mw.ProgressBar.md#backgroundimagesize)**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />  |
| 获取背景图片大小|
| **[barThickness](mw.ProgressBar.md#barthickness)**(): `number` <Badge type="tip" text="client" />  |
| 获取进度条厚度|
| **[currentValue](mw.ProgressBar.md#currentvalue)**(): `number` <Badge type="tip" text="client" />  |
| 获取当前值|
| **[fillImageColor](mw.ProgressBar.md#fillimagecolor)**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />  |
| 获取填充图片颜色|
| **[fillImageDrawType](mw.ProgressBar.md#fillimagedrawtype)**(): `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> <Badge type="tip" text="client" />  |
| 获取填充图片绘制类型|
| **[fillImageGuid](mw.ProgressBar.md#fillimageguid)**(): `string` <Badge type="tip" text="client" />  |
| 获取填充区图片id|
| **[fillImageMargin](mw.ProgressBar.md#fillimagemargin)**(): `Readonly`<[`Margin`](mw.Margin.md)\> <Badge type="tip" text="client" />  |
| 获取进度条图片边距|
| **[fillImageSize](mw.ProgressBar.md#fillimagesize)**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />  |
| 获取填充图片大小|
| **[fillType](mw.ProgressBar.md#filltype)**(): [`ProgressBarFillType`](../enums/mw.ProgressBarFillType.md) <Badge type="tip" text="client" />  |
| 获取进度条填充的方式|
| **[isRoundedToInt](mw.ProgressBar.md#isroundedtoint)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取当前数值是否取整|
| **[onSliderValueChanged](mw.ProgressBar.md#onslidervaluechanged)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`CurrentValue`: `number`) => `void`\> <Badge type="tip" text="client" />  |
| Slider值变化事件|
| **[percent](mw.ProgressBar.md#percent)**(): `number` <Badge type="tip" text="client" />  |
| 获取当前百分比|
| **[slideMethod](mw.ProgressBar.md#slidemethod)**(): [`SlideMethod`](../enums/mw.SlideMethod.md) <Badge type="tip" text="client" />  |
| 获取进度条的滑动方式|
| **[sliderButtonPressDelegate](mw.ProgressBar.md#sliderbuttonpressdelegate)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`CurrentValue`: `number`) => `void`\> <Badge type="tip" text="client" />  |
| Slider按下事件|
| **[sliderButtonReleaseDelegate](mw.ProgressBar.md#sliderbuttonreleasedelegate)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`CurrentValue`: `number`) => `void`\> <Badge type="tip" text="client" />  |
| Slider抬起事件|
| **[sliderMaxValue](mw.ProgressBar.md#slidermaxvalue)**(): `number` <Badge type="tip" text="client" />  |
| 获取拖动条最大值|
| **[sliderMinValue](mw.ProgressBar.md#sliderminvalue)**(): `number` <Badge type="tip" text="client" />  |
| 获取拖动条最小值|
| **[thumbImageColor](mw.ProgressBar.md#thumbimagecolor)**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />  |
| 获取滑块图片颜色|
| **[thumbImageDrawType](mw.ProgressBar.md#thumbimagedrawtype)**(): `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> <Badge type="tip" text="client" />  |
| 获取滑块图片绘制类型|
| **[thumbImageGuid](mw.ProgressBar.md#thumbimageguid)**(): `string` <Badge type="tip" text="client" />  |
| 获取填充区图片id|
| **[thumbImageMargin](mw.ProgressBar.md#thumbimagemargin)**(): `Readonly`<[`Margin`](mw.Margin.md)\> <Badge type="tip" text="client" />  |
| 获取拖动条图片边距|
| **[thumbImageSize](mw.ProgressBar.md#thumbimagesize)**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />  |
| 获取滑块图片大小|


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
| **[newObject](mw.ProgressBar.md#newobject)**(`parent?`: [`Canvas`](mw.Canvas.md), `inName?`: `string`): [`ProgressBar`](mw.ProgressBar.md) <Badge type="tip" text="client" />  |
| :-----|
| 创建 ProgressBar 控件|


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

### backgroundImageColor <Score text="backgroundImageColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **backgroundImageColor**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **backgroundImageColor**(`inColor`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取背景图片颜色

#### Returns

| `Readonly`<[`LinearColor`](mw.LinearColor.md)\> | 背景图片颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置背景图片颜色

#### Parameters

| `inColor` [`LinearColor`](mw.LinearColor.md) | 背景颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### backgroundImageDrawType <Score text="backgroundImageDrawType" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **backgroundImageDrawType**(): `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **backgroundImageDrawType**(`InDrawType`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取背景图片绘制类型

#### Returns

| `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> | 背景图片绘制类型 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置背景图片绘制类型

#### Parameters

| `InDrawType` [`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md) | Brush类型 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### backgroundImageGuid <Score text="backgroundImageGuid" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **backgroundImageGuid**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **backgroundImageGuid**(`inGUID`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取背景图片id

#### Returns

| `string` | 背景图片id |
| :------ | :------ |


</td>
<td style="text-align: left">


设置进度条背景图片

#### Parameters

| `inGUID` `string` | 图片GUID |
| :------ | :------ |


void


</td>
</tr></tbody>
</table>

___

### backgroundImageMargin <Score text="backgroundImageMargin" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **backgroundImageMargin**(): `Readonly`<[`Margin`](mw.Margin.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **backgroundImageMargin**(`inMargin`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取进度条背景图片边距

#### Returns

| `Readonly`<[`Margin`](mw.Margin.md)\> | 进度条背景图片边距 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置进度条背景图片边距

#### Parameters

| `inMargin` [`Margin`](mw.Margin.md) | 进度条背景图片边距 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### backgroundImageSize <Score text="backgroundImageSize" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **backgroundImageSize**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **backgroundImageSize**(`inSize`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取背景图片大小

#### Returns

| `Readonly`<[`Vector2`](mw.Vector2.md)\> | 图片大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置背景图片大小

#### Parameters

| `inSize` [`Vector2`](mw.Vector2.md) | 图片大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### barThickness <Score text="barThickness" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **barThickness**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **barThickness**(`inputBarThickness`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取进度条厚度

#### Returns

| `number` | 厚度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置进度条厚度

#### Parameters

| `inputBarThickness` `number` | 厚度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### currentValue <Score text="currentValue" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **currentValue**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **currentValue**(`inValue`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取当前值

#### Returns

| `number` | 当前值 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置当前值

#### Parameters

| `inValue` `number` | 当前值 |
| :------ | :------ |


void


</td>
</tr></tbody>
</table>

___

### fillImageColor <Score text="fillImageColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **fillImageColor**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **fillImageColor**(`inColor`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取填充图片颜色

#### Returns

| `Readonly`<[`LinearColor`](mw.LinearColor.md)\> | 填充图片颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置填充图片颜色

#### Parameters

| `inColor` [`LinearColor`](mw.LinearColor.md) | 设置的颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### fillImageDrawType <Score text="fillImageDrawType" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **fillImageDrawType**(): `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **fillImageDrawType**(`inDrawType`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取填充图片绘制类型

#### Returns

| `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> | 填充图片绘制类型 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置填充图片绘制类型

#### Parameters

| `inDrawType` [`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md) | 填充类型 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### fillImageGuid <Score text="fillImageGuid" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **fillImageGuid**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **fillImageGuid**(`inGUID`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取填充区图片id

#### Returns

| `string` | 填充区图片id |
| :------ | :------ |


</td>
<td style="text-align: left">


设置进度条图片

#### Parameters

| `inGUID` `string` | 图片GUID |
| :------ | :------ |


void


</td>
</tr></tbody>
</table>

___

### fillImageMargin <Score text="fillImageMargin" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **fillImageMargin**(): `Readonly`<[`Margin`](mw.Margin.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **fillImageMargin**(`inMargin`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取进度条图片边距

#### Returns

| `Readonly`<[`Margin`](mw.Margin.md)\> | 进度条图片边距 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置进度条图片边距

#### Parameters

| `inMargin` [`Margin`](mw.Margin.md) | 进度条图片边距 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### fillImageSize <Score text="fillImageSize" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **fillImageSize**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **fillImageSize**(`inSize`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取填充图片大小

#### Returns

| `Readonly`<[`Vector2`](mw.Vector2.md)\> | 图片大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置填充图片大小

#### Parameters

| `inSize` [`Vector2`](mw.Vector2.md) | 大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### fillType <Score text="fillType" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **fillType**(): [`ProgressBarFillType`](../enums/mw.ProgressBarFillType.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **fillType**(`inType`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取进度条填充的方式

#### Returns

| [`ProgressBarFillType`](../enums/mw.ProgressBarFillType.md) | 进度条填充 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置进度条填充的方式

#### Parameters

| `inType` [`ProgressBarFillType`](../enums/mw.ProgressBarFillType.md) | `{ 从左到右,从右到左,从上到下,从下到上 }` |
| :------ | :------ |


void


</td>
</tr></tbody>
</table>

___

### isRoundedToInt <Score text="isRoundedToInt" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **isRoundedToInt**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **isRoundedToInt**(`inToInt`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取当前数值是否取整

#### Returns

| `boolean` | 当前数值是否取整 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置当前数值是否取整

#### Parameters

| `inToInt` `boolean` | 是否取整 |
| :------ | :------ |


void


</td>
</tr></tbody>
</table>

___

### onSliderValueChanged <Score text="onSliderValueChanged" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onSliderValueChanged**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`CurrentValue`: `number`) => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


Slider值变化事件

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<(`CurrentValue`: `number`) => `void`\> | 变化事件 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### percent <Score text="percent" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **percent**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **percent**(`inPercent`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取当前百分比

#### Returns

| `number` | 当前百分比 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置当前百分比

#### Parameters

| `inPercent` `number` | 百分比 |
| :------ | :------ |


void


</td>
</tr></tbody>
</table>

___

### slideMethod <Score text="slideMethod" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **slideMethod**(): [`SlideMethod`](../enums/mw.SlideMethod.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **slideMethod**(`inSlideMethod`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取进度条的滑动方式

#### Returns

| [`SlideMethod`](../enums/mw.SlideMethod.md) |  |
| :------ | :------ |


</td>
<td style="text-align: left">


设置进度条的滑动方式

#### Parameters

| `inSlideMethod` | [`SlideMethod`](../enums/mw.SlideMethod.md) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### sliderButtonPressDelegate <Score text="sliderButtonPressDelegate" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **sliderButtonPressDelegate**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`CurrentValue`: `number`) => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


Slider按下事件

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<(`CurrentValue`: `number`) => `void`\> | 按下事件 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### sliderButtonReleaseDelegate <Score text="sliderButtonReleaseDelegate" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **sliderButtonReleaseDelegate**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`CurrentValue`: `number`) => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


Slider抬起事件

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<(`CurrentValue`: `number`) => `void`\> | 抬起事件 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### sliderMaxValue <Score text="sliderMaxValue" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **sliderMaxValue**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **sliderMaxValue**(`inValue`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取拖动条最大值

#### Returns

| `number` | 拖动条最大值 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置拖动条的最大值

#### Parameters

| `inValue` `number` | 拖动条最大值 |
| :------ | :------ |


void


</td>
</tr></tbody>
</table>

___

### sliderMinValue <Score text="sliderMinValue" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **sliderMinValue**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **sliderMinValue**(`inValue`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取拖动条最小值

#### Returns

| `number` | 拖动条最小值 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置拖动条的最小值

#### Parameters

| `inValue` `number` | 拖动条最小值 |
| :------ | :------ |


void


</td>
</tr></tbody>
</table>

___

### thumbImageColor <Score text="thumbImageColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **thumbImageColor**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **thumbImageColor**(`inColor`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取滑块图片颜色

#### Returns

| `Readonly`<[`LinearColor`](mw.LinearColor.md)\> | 滑块图片颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置滑块图片颜色

#### Parameters

| `inColor` [`LinearColor`](mw.LinearColor.md) | 设置的颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### thumbImageDrawType <Score text="thumbImageDrawType" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **thumbImageDrawType**(): `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **thumbImageDrawType**(`inDrawType`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取滑块图片绘制类型

#### Returns

| `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> | 滑块图片绘制类型 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置滑块图片绘制类型

#### Parameters

| `inDrawType` [`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md) | 绘制类型 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### thumbImageGuid <Score text="thumbImageGuid" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **thumbImageGuid**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **thumbImageGuid**(`inGUID`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取填充区图片id

#### Returns

| `string` | 填充区图片id |
| :------ | :------ |


</td>
<td style="text-align: left">


设置拖动条的样式

#### Parameters

| `inGUID` `string` | 拖动条样式GUID |
| :------ | :------ |


void


</td>
</tr></tbody>
</table>

___

### thumbImageMargin <Score text="thumbImageMargin" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **thumbImageMargin**(): `Readonly`<[`Margin`](mw.Margin.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **thumbImageMargin**(`inMargin`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取拖动条图片边距

#### Returns

| `Readonly`<[`Margin`](mw.Margin.md)\> | 拖动条图片边距 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置拖动条图片边距

#### Parameters

| `inMargin` [`Margin`](mw.Margin.md) | 拖动条图片边距 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### thumbImageSize <Score text="thumbImageSize" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **thumbImageSize**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **thumbImageSize**(`inSize`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取滑块图片大小

#### Returns

| `Readonly`<[`Vector2`](mw.Vector2.md)\> | 图片大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置滑块图片大小

#### Parameters

| `inSize` [`Vector2`](mw.Vector2.md) | 滑块图片大小 |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods

___

### newObject <Score text="newObject" /> 

• `Static` **newObject**(`parent?`, `inName?`): [`ProgressBar`](mw.ProgressBar.md) <Badge type="tip" text="client" />

创建 ProgressBar 控件

#### Parameters

| `parent?` [`Canvas`](mw.Canvas.md) | 创建控件的外parent对象 default:null |
| :------ | :------ |
| `inName?` `string` | 创建控件的名称 default:null range:设置合理的名称即可 |

#### Returns

| [`ProgressBar`](mw.ProgressBar.md) | 创建的对象 |
| :------ | :------ |

当parent和inName与已有的对象相同时，旧的对象会被销毁
