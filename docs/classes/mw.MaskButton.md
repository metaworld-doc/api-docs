[界面](../groups/界面.界面.md) / MaskButton

# MaskButton <Badge type="tip" text="Class" /> <Score text="MaskButton" />

遮罩按钮

## Hierarchy

- [`Widget`](mw.Widget.md)

  ↳ **`MaskButton`**

## Table of contents

### Properties <Score text="Properties" /> 


::: details click
### Properties <Score text="Properties" /> 
| **[onCustomPropertyChange](mw.Widget.md#oncustompropertychange)**: `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> <Badge type="tip" text="client" />  |
| :-----|
| 监听自定义属性同步事件|
:::


### Accessors <Score text="Accessors" /> 
| **[circleCenter](mw.MaskButton.md#circlecenter)**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />  |
| :-----|
| 获取圆形遮罩的中心旋转点|
| **[circleValue](mw.MaskButton.md#circlevalue)**(): `number` <Badge type="tip" text="client" />  |
| 获取圆形遮罩的遮挡百分值|
| **[clickedDelegate](mw.MaskButton.md#clickeddelegate)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />  |
| 点击事件|
| **[disableImageColor](mw.MaskButton.md#disableimagecolor)**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />  |
| 获取禁用图片颜色|
| **[disableImageDrawType](mw.MaskButton.md#disableimagedrawtype)**(): `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> <Badge type="tip" text="client" />  |
| 获取禁用图片绘制类型|
| **[disableImageGuid](mw.MaskButton.md#disableimageguid)**(): `string` <Badge type="tip" text="client" />  |
| 获取禁用图片ID|
| **[disableImageMargin](mw.MaskButton.md#disableimagemargin)**(): `Readonly`<[`Margin`](mw.Margin.md)\> <Badge type="tip" text="client" />  |
| 获取禁用图片边距|
| **[disableImageSize](mw.MaskButton.md#disableimagesize)**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />  |
| 获取禁用图片大小|
| **[enableTransition](mw.MaskButton.md#enabletransition)**(`inBoolean`: `boolean`): `void` <Badge type="tip" text="client" />  |
| 是否套用不同的按下方案|
| **[fanShapedRotated](mw.MaskButton.md#fanshapedrotated)**(): `number` <Badge type="tip" text="client" />  |
| 获取扇形遮罩的旋转|
| **[fanShapedRotatedCenter](mw.MaskButton.md#fanshapedrotatedcenter)**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />  |
| 获取扇形遮罩的中心旋转点|
| **[fanShapedValue](mw.MaskButton.md#fanshapedvalue)**(): `number` <Badge type="tip" text="client" />  |
| 获取扇形遮罩的遮罩进度|
| **[focusable](mw.MaskButton.md#focusable)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取是否获取输入焦点|
| **[hoveredDelegate](mw.MaskButton.md#hovereddelegate)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />  |
| 悬浮事件|
| **[inverseOpacity](mw.MaskButton.md#inverseopacity)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取反转透明度权重|
| **[isTransitionEnable](mw.MaskButton.md#istransitionenable)**(): `boolean` <Badge type="tip" text="client" />  |
| 按钮是否启用过度模式,按下是否有效果|
| **[maskImageColor](mw.MaskButton.md#maskimagecolor)**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />  |
| 获取遮罩图片颜色|
| **[maskImageGuid](mw.MaskButton.md#maskimageguid)**(): `string` <Badge type="tip" text="client" />  |
| 获取设置遮罩图片ID|
| **[maskOpacity](mw.MaskButton.md#maskopacity)**(): `number` <Badge type="tip" text="client" />  |
| 获取遮挡处的底图的透明度|
| **[maskTextureOpacity](mw.MaskButton.md#masktextureopacity)**(): `number` <Badge type="tip" text="client" />  |
| 获取遮挡处的遮挡图的透明度|
| **[maskType](mw.MaskButton.md#masktype)**(): [`MaskButtonType`](../enums/mw.MaskButtonType.md) <Badge type="tip" text="client" />  |
| 获取遮罩裁剪类型|
| **[normalImageColor](mw.MaskButton.md#normalimagecolor)**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />  |
| 获取普通图片颜色|
| **[normalImageDrawType](mw.MaskButton.md#normalimagedrawtype)**(): `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> <Badge type="tip" text="client" />  |
| 获取普通图片绘制类型|
| **[normalImageGuid](mw.MaskButton.md#normalimageguid)**(): `string` <Badge type="tip" text="client" />  |
| 获取普通图片ID|
| **[normalImageMargin](mw.MaskButton.md#normalimagemargin)**(): `Readonly`<[`Margin`](mw.Margin.md)\> <Badge type="tip" text="client" />  |
| 获取普通图片边距|
| **[normalImageSize](mw.MaskButton.md#normalimagesize)**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />  |
| 获取图片大小|
| **[pressedDelegate](mw.MaskButton.md#presseddelegate)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />  |
| 按下事件|
| **[pressedImageColor](mw.MaskButton.md#pressedimagecolor)**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />  |
| 获取按压图片颜色|
| **[pressedImageDrawType](mw.MaskButton.md#pressedimagedrawtype)**(): `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> <Badge type="tip" text="client" />  |
| 获取按压图片绘制类型|
| **[pressedImageGuid](mw.MaskButton.md#pressedimageguid)**(): `string` <Badge type="tip" text="client" />  |
| 获取按下图片ID|
| **[pressedImageMargin](mw.MaskButton.md#pressedimagemargin)**(): `Readonly`<[`Margin`](mw.Margin.md)\> <Badge type="tip" text="client" />  |
| 获取按压图片边距|
| **[pressedImageSize](mw.MaskButton.md#pressedimagesize)**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />  |
| 获取按压图片大小|
| **[pressedMethod](mw.MaskButton.md#pressedmethod)**(): [`ButtonPressMethod`](../enums/mw.ButtonPressMethod.md) <Badge type="tip" text="client" />  |
| 获取按压模式|
| **[releasedDelegate](mw.MaskButton.md#releaseddelegate)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />  |
| 释放事件|
| **[roundBoxPercentOffset](mw.MaskButton.md#roundboxpercentoffset)**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />  |
| 获取矩形百分比大小边距偏移|
| **[roundBoxRadius](mw.MaskButton.md#roundboxradius)**(): `number`  |
| 获取设置的角半径|
| **[roundBoxSharpness](mw.MaskButton.md#roundboxsharpness)**(): `number`  |
| 获取设置的圆角锐化度|
| **[roundBoxUVRatio](mw.MaskButton.md#roundboxuvratio)**(): `number`  |
| 获取圆角调节大小|
| **[touchMethod](mw.MaskButton.md#touchmethod)**(): [`ButtonTouchMethod`](../enums/mw.ButtonTouchMethod.md) <Badge type="tip" text="client" />  |
| 获取触摸模式|
| **[unHoveredDelegate](mw.MaskButton.md#unhovereddelegate)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />  |
| 未悬浮事件|
| **[useMaskTextureOpacity](mw.MaskButton.md#usemasktextureopacity)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取遮罩轮廓是否裁剪底图|


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
| **[addKey](mw.MaskButton.md#addkey)**(`key`: [`Keys`](../enums/mw.Keys.md)): `void` <Badge type="tip" text="client" />  |
| :-----|
| 同一按键同时只能操控一个UI控件，最新绑定的UI控件会覆盖之前的绑定；脚本中添加的绑定无法覆盖编辑器按键绑定菜单中绑定相同按键的UI控件，但当两个UI控件分别通过代码和菜单绑定到同一按键时，使用代码绑定的优先级更高|
| **[getKeys](mw.MaskButton.md#getkeys)**(): [`Keys`](../enums/mw.Keys.md)[] <Badge type="tip" text="client" />  |
| 获取当前UI控件绑定的所有键盘按键，包括编辑器按键绑定菜单和用代码绑定的按键|
| **[isPressed](mw.MaskButton.md#ispressed)**(): `boolean` <Badge type="tip" text="client" />  |
| 是否按下|
| **[removeKey](mw.MaskButton.md#removekey)**(`key`: [`Keys`](../enums/mw.Keys.md)): `void` <Badge type="tip" text="client" />  |
| 此操作只会解绑动态绑定的按键无法解除编辑器按键绑定菜单中绑定的按键|
| **[setDisableImageColorByHex](mw.MaskButton.md#setdisableimagecolorbyhex)**(`inHexString`: `string`): `void` <Badge type="tip" text="client" />  |
| 设置不可用颜色指定Hex的颜色文本设定颜色 #05050505|
| **[setDisableImageColorDecimal](mw.MaskButton.md#setdisableimagecolordecimal)**(`R`: `number`, `G`: `number`, `B`: `number`, `A`: `number`): `void` <Badge type="tip" text="client" />  |
| 设置禁用颜色|
| **[setMaskImageColorByHex](mw.MaskButton.md#setmaskimagecolorbyhex)**(`inHexString`: `string`): `void` <Badge type="tip" text="client" />  |
| 设置遮罩图片颜色指定Hex的颜色文本设定颜色 #05050505|
| **[setMaskImageColorDecimal](mw.MaskButton.md#setmaskimagecolordecimal)**(`R`: `number`, `G`: `number`, `B`: `number`, `A`: `number`): `void` <Badge type="tip" text="client" />  |
| 设置遮罩图片颜色|
| **[setNormalImageColorByHex](mw.MaskButton.md#setnormalimagecolorbyhex)**(`inHexString`: `string`): `void` <Badge type="tip" text="client" />  |
| 设置普通图片颜色指定Hex的颜色文本设定颜色 #05050505|
| **[setNormalImageColorDecimal](mw.MaskButton.md#setnormalimagecolordecimal)**(`R`: `number`, `G`: `number`, `B`: `number`, `A`: `number`): `void` <Badge type="tip" text="client" />  |
| 设置普通图片颜色|
| **[setPressedImageColorByHex](mw.MaskButton.md#setpressedimagecolorbyhex)**(`inHexString`: `string`): `void` <Badge type="tip" text="client" />  |
| 设置按压图片颜色指定Hex的颜色文本设定颜色 #05050505|
| **[setPressedImageColorDecimal](mw.MaskButton.md#setpressedimagecolordecimal)**(`R`: `number`, `G`: `number`, `B`: `number`, `A`: `number`): `void` <Badge type="tip" text="client" />  |
| 设置按压图片颜色|
| **[newObject](mw.MaskButton.md#newobject)**(`parent?`: [`Canvas`](mw.Canvas.md), `inName?`: `string`): [`MaskButton`](mw.MaskButton.md) <Badge type="tip" text="client" />  |
| 创建 Mask 控件|


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

### circleCenter <Score text="circleCenter" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **circleCenter**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **circleCenter**(`center`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取圆形遮罩的中心旋转点

#### Returns

| [`Vector2`](mw.Vector2.md) | 中心百分点 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置圆形遮罩的中心旋转点

#### Parameters

| `center` [`Vector2`](mw.Vector2.md) | 中心点百分比 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### circleValue <Score text="circleValue" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **circleValue**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **circleValue**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取圆形遮罩的遮挡百分值

#### Returns

| `number` | 进度值,0~1 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置圆形遮罩的遮挡百分值

#### Parameters

| `value` `number` | 百分进度值,0~1 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### clickedDelegate <Score text="clickedDelegate" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **clickedDelegate**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


点击事件

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> | 返回事件的代理 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### disableImageColor <Score text="disableImageColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **disableImageColor**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **disableImageColor**(`inColor`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取禁用图片颜色

#### Returns

| `Readonly`<[`LinearColor`](mw.LinearColor.md)\> | 禁用图片颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置禁用图片颜色

#### Parameters

| `inColor` [`LinearColor`](mw.LinearColor.md) | 颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### disableImageDrawType <Score text="disableImageDrawType" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **disableImageDrawType**(): `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **disableImageDrawType**(`inDrawType`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取禁用图片绘制类型

#### Returns

| `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> | 禁用图片绘制类型 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置禁用图片绘制类型

#### Parameters

| `inDrawType` | [`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md) |
| :------ | :------ |


禁用图片绘制类型


</td>
</tr></tbody>
</table>

___

### disableImageGuid <Score text="disableImageGuid" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **disableImageGuid**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **disableImageGuid**(`inGuid`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取禁用图片ID

#### Returns

| `string` | 禁用图片ID |
| :------ | :------ |


</td>
<td style="text-align: left">


设置不可用图片ID

#### Parameters

| `inGuid` `string` | 图片id |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### disableImageMargin <Score text="disableImageMargin" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **disableImageMargin**(): `Readonly`<[`Margin`](mw.Margin.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **disableImageMargin**(`inMargin`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取禁用图片边距

#### Returns

| `Readonly`<[`Margin`](mw.Margin.md)\> | 禁用图片边距 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置禁用图片边距

#### Parameters

| `inMargin` [`Margin`](mw.Margin.md) | 禁用图片边距 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### disableImageSize <Score text="disableImageSize" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **disableImageSize**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **disableImageSize**(`inSize`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取禁用图片大小

#### Returns

| `Readonly`<[`Vector2`](mw.Vector2.md)\> | 禁用图片大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置禁用图片大小

#### Parameters

| `inSize` [`Vector2`](mw.Vector2.md) | 大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### enableTransition <Score text="enableTransition" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `set` **enableTransition**(`inBoolean`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


是否套用不同的按下方案

#### Parameters

| `inBoolean` `boolean` | 是否套用不同的按下方案 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### fanShapedRotated <Score text="fanShapedRotated" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **fanShapedRotated**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **fanShapedRotated**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取扇形遮罩的旋转

#### Returns

| `number` | 旋转角度 0~1 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置扇形遮罩的旋转

#### Parameters

| `value` `number` | 旋转角度 0 ~ 1 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### fanShapedRotatedCenter <Score text="fanShapedRotatedCenter" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **fanShapedRotatedCenter**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **fanShapedRotatedCenter**(`center`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取扇形遮罩的中心旋转点

#### Returns

| [`Vector2`](mw.Vector2.md) | 旋转中心百分点 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置扇形遮罩的中心旋转点

#### Parameters

| `center` [`Vector2`](mw.Vector2.md) | 中心点百分比 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### fanShapedValue <Score text="fanShapedValue" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **fanShapedValue**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **fanShapedValue**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取扇形遮罩的遮罩进度

#### Returns

| `number` | 进度值 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置扇形遮罩的遮罩进度

#### Parameters

| `value` `number` | 百分进度值 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### focusable <Score text="focusable" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **focusable**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **focusable**(`inFocus`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否获取输入焦点

#### Returns

| `boolean` | 是否获取输入焦点 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否获取输入焦点

#### Parameters

| `inFocus` `boolean` | 是否获取输入焦点 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### hoveredDelegate <Score text="hoveredDelegate" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **hoveredDelegate**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


悬浮事件

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> | 返回事件的代理 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### inverseOpacity <Score text="inverseOpacity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **inverseOpacity**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **inverseOpacity**(`inverseOpacityWeight`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取反转透明度权重

#### Returns

| `boolean` | 权重 |
| :------ | :------ |


</td>
<td style="text-align: left">


反转透明度权重

#### Parameters

| `inverseOpacityWeight` `boolean` | 权重 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### isTransitionEnable <Score text="isTransitionEnable" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **isTransitionEnable**(): `boolean` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


按钮是否启用过度模式,按下是否有效果

#### Returns

| `boolean` | 按钮是否启用过度模式 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### maskImageColor <Score text="maskImageColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **maskImageColor**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **maskImageColor**(`inColor`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取遮罩图片颜色

#### Returns

| `Readonly`<[`LinearColor`](mw.LinearColor.md)\> | 图片的颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置遮罩图片颜色

#### Parameters

| `inColor` `Readonly`<[`LinearColor`](mw.LinearColor.md)\> | 颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### maskImageGuid <Score text="maskImageGuid" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **maskImageGuid**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **maskImageGuid**(`InGuid`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取设置遮罩图片ID

#### Returns

| `string` | 遮罩图片ID |
| :------ | :------ |


</td>
<td style="text-align: left">


设置遮罩图片ID

#### Parameters

| `InGuid` | `string` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### maskOpacity <Score text="maskOpacity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **maskOpacity**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **maskOpacity**(`o`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取遮挡处的底图的透明度

#### Returns

| `number` | 透明度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置遮挡处的底图的透明度

#### Parameters

| `o` `number` | 透明度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### maskTextureOpacity <Score text="maskTextureOpacity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **maskTextureOpacity**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **maskTextureOpacity**(`o`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取遮挡处的遮挡图的透明度

#### Returns

| `number` | 透明度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置遮挡处的遮挡图的透明度

#### Parameters

| `o` `number` | 透明度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### maskType <Score text="maskType" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **maskType**(): [`MaskButtonType`](../enums/mw.MaskButtonType.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **maskType**(`inType`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取遮罩裁剪类型

#### Returns

| [`MaskButtonType`](../enums/mw.MaskButtonType.md) | 裁剪类型 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置遮罩裁剪类型

#### Parameters

| `inType` [`MaskButtonType`](../enums/mw.MaskButtonType.md) | 裁剪类型 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### normalImageColor <Score text="normalImageColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **normalImageColor**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **normalImageColor**(`inNormalColor`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取普通图片颜色

#### Returns

| `Readonly`<[`LinearColor`](mw.LinearColor.md)\> | 普通图片颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置普通图片颜色

#### Parameters

| `inNormalColor` [`LinearColor`](mw.LinearColor.md) | 颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### normalImageDrawType <Score text="normalImageDrawType" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **normalImageDrawType**(): `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **normalImageDrawType**(`inDrawType`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取普通图片绘制类型

#### Returns

| `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> | 普通图片绘制类型 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置普通图片绘制类型

#### Parameters

| `inDrawType` [`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md) | 类型 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### normalImageGuid <Score text="normalImageGuid" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **normalImageGuid**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **normalImageGuid**(`inGuid`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取普通图片ID

#### Returns

| `string` | 普通图片ID |
| :------ | :------ |


</td>
<td style="text-align: left">


设置普通图片ID

#### Parameters

| `inGuid` `string` | 图片id |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### normalImageMargin <Score text="normalImageMargin" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **normalImageMargin**(): `Readonly`<[`Margin`](mw.Margin.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **normalImageMargin**(`inMargin`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取普通图片边距

#### Returns

| `Readonly`<[`Margin`](mw.Margin.md)\> | 普通图片边距 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置普通图片边距

#### Parameters

| `inMargin` [`Margin`](mw.Margin.md) | 普通图片边距 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### normalImageSize <Score text="normalImageSize" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **normalImageSize**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **normalImageSize**(`inSize`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取图片大小

#### Returns

| `Readonly`<[`Vector2`](mw.Vector2.md)\> | 普通图片大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置图片大小

#### Parameters

| `inSize` [`Vector2`](mw.Vector2.md) | 大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### pressedDelegate <Score text="pressedDelegate" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **pressedDelegate**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


按下事件

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> | 返回事件的代理 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### pressedImageColor <Score text="pressedImageColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **pressedImageColor**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **pressedImageColor**(`inColor`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取按压图片颜色

#### Returns

| `Readonly`<[`LinearColor`](mw.LinearColor.md)\> | 按压图片颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置按压图片颜色

#### Parameters

| `inColor` [`LinearColor`](mw.LinearColor.md) | 颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### pressedImageDrawType <Score text="pressedImageDrawType" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **pressedImageDrawType**(): `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **pressedImageDrawType**(`inDrawType`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取按压图片绘制类型

#### Returns

| `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> | 按压图片绘制类型 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置按压图片绘制类型

#### Parameters

| `inDrawType` [`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md) | 类型 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### pressedImageGuid <Score text="pressedImageGuid" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **pressedImageGuid**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **pressedImageGuid**(`inGuid`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取按下图片ID

#### Returns

| `string` | 按下图片ID |
| :------ | :------ |


</td>
<td style="text-align: left">


设置按下图片ID

#### Parameters

| `inGuid` `string` | 图片id |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### pressedImageMargin <Score text="pressedImageMargin" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **pressedImageMargin**(): `Readonly`<[`Margin`](mw.Margin.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **pressedImageMargin**(`inMargin`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取按压图片边距

#### Returns

| `Readonly`<[`Margin`](mw.Margin.md)\> | 按压图片边距 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置按压图片边距

#### Parameters

| `inMargin` [`Margin`](mw.Margin.md) | 按压图片边距 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### pressedImageSize <Score text="pressedImageSize" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **pressedImageSize**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **pressedImageSize**(`inSize`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取按压图片大小

#### Returns

| `Readonly`<[`Vector2`](mw.Vector2.md)\> | 按压图片大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置按压图片大小

#### Parameters

| `inSize` [`Vector2`](mw.Vector2.md) | 大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### pressedMethod <Score text="pressedMethod" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **pressedMethod**(): [`ButtonPressMethod`](../enums/mw.ButtonPressMethod.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **pressedMethod**(`inPressedMethod`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取按压模式

#### Returns

| [`ButtonPressMethod`](../enums/mw.ButtonPressMethod.md) | 按压模式 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置按压模式

#### Parameters

| `inPressedMethod` [`ButtonPressMethod`](../enums/mw.ButtonPressMethod.md) | Press模式选择 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### releasedDelegate <Score text="releasedDelegate" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **releasedDelegate**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


释放事件

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> | 返回事件的代理 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### roundBoxPercentOffset <Score text="roundBoxPercentOffset" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **roundBoxPercentOffset**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **roundBoxPercentOffset**(`percent`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取矩形百分比大小边距偏移

#### Returns

| [`Vector2`](mw.Vector2.md) | 矩形大小边距偏移的百分比占据，0~0.5 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置矩形大小边距偏移

#### Parameters

| `percent` [`Vector2`](mw.Vector2.md) | 矩形大小百分比，0~0.5 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### roundBoxRadius <Score text="roundBoxRadius" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **roundBoxRadius**(): `number`

</th>
<th style="text-align: left">

• `set` **roundBoxRadius**(`value`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取设置的角半径

#### Returns

| `number` | 角半径百分比 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角半径

#### Parameters

| `value` `number` | 角半径百分比 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### roundBoxSharpness <Score text="roundBoxSharpness" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **roundBoxSharpness**(): `number`

</th>
<th style="text-align: left">

• `set` **roundBoxSharpness**(`v`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取设置的圆角锐化度

#### Returns

| `number` | 锐化度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置的圆角锐化度

#### Parameters

| `v` `number` | 锐化度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### roundBoxUVRatio <Score text="roundBoxUVRatio" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **roundBoxUVRatio**(): `number`

</th>
<th style="text-align: left">

• `set` **roundBoxUVRatio**(`v`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取圆角调节大小

#### Returns

| `number` | 圆角调节大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置圆角调节大小

#### Parameters

| `v` `number` | 圆角调节大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### touchMethod <Score text="touchMethod" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **touchMethod**(): [`ButtonTouchMethod`](../enums/mw.ButtonTouchMethod.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **touchMethod**(`inTouchMethod`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取触摸模式

#### Returns

| [`ButtonTouchMethod`](../enums/mw.ButtonTouchMethod.md) | 触摸模式 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置触摸模式

#### Parameters

| `inTouchMethod` [`ButtonTouchMethod`](../enums/mw.ButtonTouchMethod.md) | Touch模式选择 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### unHoveredDelegate <Score text="unHoveredDelegate" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **unHoveredDelegate**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


未悬浮事件

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> | 返回事件的代理 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### useMaskTextureOpacity <Score text="useMaskTextureOpacity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **useMaskTextureOpacity**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **useMaskTextureOpacity**(`inUseWeight`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取遮罩轮廓是否裁剪底图

#### Returns

| `boolean` | 权重 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置遮罩轮廓是否裁剪底图

#### Parameters

| `inUseWeight` `boolean` | 是否裁剪 |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods

___

### addKey <Score text="addKey" /> 

• **addKey**(`key`): `void` <Badge type="tip" text="client" />

同一按键同时只能操控一个UI控件，最新绑定的UI控件会覆盖之前的绑定；脚本中添加的绑定无法覆盖编辑器按键绑定菜单中绑定相同按键的UI控件，但当两个UI控件分别通过代码和菜单绑定到同一按键时，使用代码绑定的优先级更高

#### Parameters

| `key` [`Keys`](../enums/mw.Keys.md) | 绑定的按键 |
| :------ | :------ |


___

### getKeys <Score text="getKeys" /> 

• **getKeys**(): [`Keys`](../enums/mw.Keys.md)[] <Badge type="tip" text="client" />

获取当前UI控件绑定的所有键盘按键，包括编辑器按键绑定菜单和用代码绑定的按键

#### Returns

| [`Keys`](../enums/mw.Keys.md)[] | 返回当前控件绑定的所有按键,可能为空 |
| :------ | :------ |

___

### isPressed <Score text="isPressed" /> 

• **isPressed**(): `boolean` <Badge type="tip" text="client" />

是否按下

#### Returns

| `boolean` | 返回按钮是否按下 |
| :------ | :------ |

___

### removeKey <Score text="removeKey" /> 

• **removeKey**(`key`): `void` <Badge type="tip" text="client" />

此操作只会解绑动态绑定的按键无法解除编辑器按键绑定菜单中绑定的按键

#### Parameters

| `key` [`Keys`](../enums/mw.Keys.md) | 解除绑定的按键 |
| :------ | :------ |


___

### setDisableImageColorByHex <Score text="setDisableImageColorByHex" /> 

• **setDisableImageColorByHex**(`inHexString`): `void` <Badge type="tip" text="client" />

设置不可用颜色指定Hex的颜色文本设定颜色 #05050505

#### Parameters

| `inHexString` `string` | 颜色字符串 range: 符合 Hex 特点的字符串类型 |
| :------ | :------ |


___

### setDisableImageColorDecimal <Score text="setDisableImageColorDecimal" /> 

• **setDisableImageColorDecimal**(`R`, `G`, `B`, `A`): `void` <Badge type="tip" text="client" />

设置禁用颜色

#### Parameters

| `R` `number` | 颜色 R 值。 <br> range:[0, 255] type: 整形 |
| :------ | :------ |
| `G` `number` | 颜色 G 值。 <br> range:[0, 255] type: 整形 |
| `B` `number` | 颜色 B 值。 <br> range:[0, 255] type: 整形 |
| `A` `number` | 颜色 透明度。 <br> range:[0, 255] type: 整形 |


___

### setMaskImageColorByHex <Score text="setMaskImageColorByHex" /> 

• **setMaskImageColorByHex**(`inHexString`): `void` <Badge type="tip" text="client" />

设置遮罩图片颜色指定Hex的颜色文本设定颜色 #05050505

#### Parameters

| `inHexString` `string` | 颜色字符串 range: 符合 Hex 特点的字符串类型 |
| :------ | :------ |


___

### setMaskImageColorDecimal <Score text="setMaskImageColorDecimal" /> 

• **setMaskImageColorDecimal**(`R`, `G`, `B`, `A`): `void` <Badge type="tip" text="client" />

设置遮罩图片颜色

#### Parameters

| `R` `number` | 颜色 R 值。 <br> range:[0, 255] type: 整形 |
| :------ | :------ |
| `G` `number` | 颜色 G 值。 <br> range:[0, 255] type: 整形 |
| `B` `number` | 颜色 B 值。 <br> range:[0, 255] type: 整形 |
| `A` `number` | 颜色 透明度。 <br> range:[0, 255] type: 整形 |


___

### setNormalImageColorByHex <Score text="setNormalImageColorByHex" /> 

• **setNormalImageColorByHex**(`inHexString`): `void` <Badge type="tip" text="client" />

设置普通图片颜色指定Hex的颜色文本设定颜色 #05050505

#### Parameters

| `inHexString` `string` | 颜色字符串 range: 符合 Hex 特点的字符串类型 |
| :------ | :------ |


___

### setNormalImageColorDecimal <Score text="setNormalImageColorDecimal" /> 

• **setNormalImageColorDecimal**(`R`, `G`, `B`, `A`): `void` <Badge type="tip" text="client" />

设置普通图片颜色

#### Parameters

| `R` `number` | 颜色 R 值。 <br> range:[0, 255] type: 整形 |
| :------ | :------ |
| `G` `number` | 颜色 G 值。 <br> range:[0, 255] type: 整形 |
| `B` `number` | 颜色 B 值。 <br> range:[0, 255] type: 整形 |
| `A` `number` | 颜色 透明度。 <br> range:[0, 255] type: 整形 |


___

### setPressedImageColorByHex <Score text="setPressedImageColorByHex" /> 

• **setPressedImageColorByHex**(`inHexString`): `void` <Badge type="tip" text="client" />

设置按压图片颜色指定Hex的颜色文本设定颜色 #05050505

#### Parameters

| `inHexString` `string` | 颜色字符串 range: 符合 Hex 特点的字符串类型 |
| :------ | :------ |


___

### setPressedImageColorDecimal <Score text="setPressedImageColorDecimal" /> 

• **setPressedImageColorDecimal**(`R`, `G`, `B`, `A`): `void` <Badge type="tip" text="client" />

设置按压图片颜色

#### Parameters

| `R` `number` | 颜色 R 值。 <br> range:[0, 255] type: 整形 |
| :------ | :------ |
| `G` `number` | 颜色 G 值。 <br> range:[0, 255] type: 整形 |
| `B` `number` | 颜色 B 值。 <br> range:[0, 255] type: 整形 |
| `A` `number` | 颜色 透明度。 <br> range:[0, 255] type: 整形 |


___

### newObject <Score text="newObject" /> 

• `Static` **newObject**(`parent?`, `inName?`): [`MaskButton`](mw.MaskButton.md) <Badge type="tip" text="client" />

创建 Mask 控件

#### Parameters

| `parent?` [`Canvas`](mw.Canvas.md) | 创建控件的外parent对象 default: null |
| :------ | :------ |
| `inName?` `string` | 创建控件的名称 default:null range:设置合理的名称即可 |

#### Returns

| [`MaskButton`](mw.MaskButton.md) | 返回创建的对象 |
| :------ | :------ |

当 parent 和 InName 与已有的对象相同时，旧的对象会被销毁
