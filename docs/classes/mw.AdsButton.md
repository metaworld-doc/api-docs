[界面](../groups/界面.界面.md) / AdsButton

# AdsButton <Badge type="tip" text="Class" /> <Score text="AdsButton" />

广告按钮，请注意广告按钮不允许被遮挡

需要在游戏中使用 onshow/onclose 才能播放广告

当其上方有任何非隐藏/折叠的UI时，广告按钮将无法生效

## Hierarchy

- [`Widget`](mw.Widget.md)

  ↳ **`AdsButton`**

## Table of contents

### Properties <Score text="Properties" /> 


::: details click
### Properties <Score text="Properties" /> 
| **[onCustomPropertyChange](mw.Widget.md#oncustompropertychange)**: `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> <Badge type="tip" text="client" />  |
| :-----|
| 监听自定义属性同步事件|
:::


### Accessors <Score text="Accessors" /> 
| **[autoAdjust](mw.AdsButton.md#autoadjust)**(): `boolean` <Badge type="tip" text="client" />  |
| :-----|
| 获取字体是否自适应调整大小:boolean(为True时，文本内容字体大小将自动改变，尽可能大的充满整个文本框，而文本框大小不会变化)|
| **[defaultFont](mw.AdsButton.md#defaultfont)**(): `string`  [`UIFontFamily`](../enums/mw.UIFontFamily.md) <Badge type="tip" text="client" />  |
| 获取默认字体|
| **[fallbackFont](mw.AdsButton.md#fallbackfont)**(): `string`  [`UIFontFamily`](../enums/mw.UIFontFamily.md) <Badge type="tip" text="client" />  |
| 获取退却字体|
| **[fontColor](mw.AdsButton.md#fontcolor)**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />  |
| 获取字体颜色|
| **[fontLetterSpace](mw.AdsButton.md#fontletterspace)**(): `number` <Badge type="tip" text="client" />  |
| 获取字体间距|
| **[fontSize](mw.AdsButton.md#fontsize)**(): `number` <Badge type="tip" text="client" />  |
| 获取字体大小|
| **[glyph](mw.AdsButton.md#glyph)**(): [`UIFontGlyph`](../enums/mw.UIFontGlyph.md) <Badge type="tip" text="client" />  |
| 获取字体字形|
| **[onClose](mw.AdsButton.md#onclose)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`isSuccess`: `boolean`) => `void`\> <Badge type="tip" text="client" />  |
| 用户手动关闭广告的回调|
| **[onShow](mw.AdsButton.md#onshow)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`isReady`: `boolean`) => `void`\> <Badge type="tip" text="client" />  |
| 点击按钮的回调，播放广告前执行|
| **[outlineColor](mw.AdsButton.md#outlinecolor)**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />  |
| 获取字体描边颜色|
| **[outlineSize](mw.AdsButton.md#outlinesize)**(): `number` <Badge type="tip" text="client" />  |
| 获取字体描边宽度|
| **[shadowColor](mw.AdsButton.md#shadowcolor)**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />  |
| 获取字体阴影颜色|
| **[shadowOffset](mw.AdsButton.md#shadowoffset)**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />  |
| 获取字体阴影偏移|
| **[strikethroughEnable](mw.AdsButton.md#strikethroughenable)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取是否开启字体删除线|
| **[text](mw.AdsButton.md#text)**(): `string` <Badge type="tip" [text](mw.AdsButton.md#text)="client" />  |
| 获取按钮文字|
| **[textAlign](mw.AdsButton.md#textalign)**(): [`TextJustify`](../enums/mw.TextJustify.md) <Badge type="tip" text="client" />  |
| 获取字体对齐方式|
| **[textVerticalAlign](mw.AdsButton.md#textverticalalign)**(): [`TextVerticalJustify`](../enums/mw.TextVerticalJustify.md) <Badge type="tip" text="client" />  |
| 获取字体垂直对齐方式|
| **[underlineEnable](mw.AdsButton.md#underlineenable)**(): `boolean` <Badge type="tip" text="client" />  |
| 返回是否开启字体下划线|


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
| **[addKey](mw.AdsButton.md#addkey)**(`key`: [`Keys`](../enums/mw.Keys.md)): `void` <Badge type="tip" text="client" />  |
| :-----|
| 同一按键同时只能操控一个UI控件，最新绑定的UI控件会覆盖之前的绑定；脚本中添加的绑定无法覆盖编辑器按键绑定菜单中绑定相同按键的UI控件，但当两个UI控件分别通过代码和菜单绑定到同一按键时，使用代码绑定的优先级更高|
| **[getKeys](mw.AdsButton.md#getkeys)**(): [`Keys`](../enums/mw.Keys.md)[] <Badge type="tip" text="client" />  |
| 获取当前UI控件绑定的所有键盘按键，包括编辑器按键绑定菜单和用代码绑定的按键|
| **[removeKey](mw.AdsButton.md#removekey)**(`key`: [`Keys`](../enums/mw.Keys.md)): `void` <Badge type="tip" text="client" />  |
| 此操作只会解绑动态绑定的按键无法解除编辑器按键绑定菜单中绑定的按键|
| **[newObject](mw.AdsButton.md#newobject)**(`parent?`: [`Canvas`](mw.Canvas.md), `inName?`: `string`): [`AdsButton`](mw.AdsButton.md) <Badge type="tip" text="client" />  |
| 创建 Button 控件|


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

### autoAdjust <Score text="autoAdjust" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **autoAdjust**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **autoAdjust**(`isAdjust`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取字体是否自适应调整大小:boolean(为True时，文本内容字体大小将自动改变，尽可能大的充满整个文本框，而文本框大小不会变化)

#### Returns

| `boolean` | 字体是否自适应调整大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置字体是否自适应调整大小:boolean(为True时，文本内容字体大小将自动改变，尽可能大的充满整个文本框，而文本框大小不会变化)

#### Parameters

| `isAdjust` `boolean` | 字体是否自适应调整大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### defaultFont <Score text="defaultFont" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **defaultFont**(): `string`  [`UIFontFamily`](../enums/mw.UIFontFamily.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **defaultFont**(`inFont`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取默认字体

#### Returns

| `string`  [`UIFontFamily`](../enums/mw.UIFontFamily.md) | 默认字体 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置默认字体

#### Parameters

| `inFont` `string`  [`UIFontFamily`](../enums/mw.UIFontFamily.md) | 需设置的默认字体 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### fallbackFont <Score text="fallbackFont" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **fallbackFont**(): `string`  [`UIFontFamily`](../enums/mw.UIFontFamily.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **fallbackFont**(`inFont`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取退却字体

#### Returns

| `string`  [`UIFontFamily`](../enums/mw.UIFontFamily.md) | 退却字体 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置退却字体

#### Parameters

| `inFont` `string`  [`UIFontFamily`](../enums/mw.UIFontFamily.md) | 需设置的退却字体 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### fontColor <Score text="fontColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **fontColor**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **fontColor**(`inColor`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取字体颜色

#### Returns

| [`LinearColor`](mw.LinearColor.md) | 字体颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置字体颜色

#### Parameters

| `inColor` [`LinearColor`](mw.LinearColor.md) | 字体颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### fontLetterSpace <Score text="fontLetterSpace" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **fontLetterSpace**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **fontLetterSpace**(`fontLetterSpace`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取字体间距

#### Returns

| `number` | 字体间距 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置字体间距

#### Parameters

| `fontLetterSpace` `number` | 间距 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### fontSize <Score text="fontSize" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **fontSize**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **fontSize**(`FontSize`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取字体大小

#### Returns

| `number` | 字体大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置字体大小

#### Parameters

| `FontSize` `number` | 大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### glyph <Score text="glyph" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **glyph**(): [`UIFontGlyph`](../enums/mw.UIFontGlyph.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **glyph**(`inGlyph`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取字体字形

#### Returns

| [`UIFontGlyph`](../enums/mw.UIFontGlyph.md) | 字体字形 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置字体字形

#### Parameters

| `inGlyph` [`UIFontGlyph`](../enums/mw.UIFontGlyph.md) | 字体字形的类型 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### onClose <Score text="onClose" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onClose**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`isSuccess`: `boolean`) => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


用户手动关闭广告的回调

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<(`isSuccess`: `boolean`) => `void`\> | 返回事件的代理 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onShow <Score text="onShow" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onShow**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`isReady`: `boolean`) => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


点击按钮的回调，播放广告前执行

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<(`isReady`: `boolean`) => `void`\> | 返回事件的代理 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### outlineColor <Score text="outlineColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **outlineColor**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **outlineColor**(`inOutlineColor`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取字体描边颜色

#### Returns

| [`LinearColor`](mw.LinearColor.md) | 字体描边颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置字体描边颜色

#### Parameters

| `inOutlineColor` [`LinearColor`](mw.LinearColor.md) | 描边颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### outlineSize <Score text="outlineSize" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **outlineSize**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **outlineSize**(`inOutlineSize`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取字体描边宽度

#### Returns

| `number` | 字体描边宽度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置字体描边宽度

#### Parameters

| `inOutlineSize` `number` | 设置的大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### shadowColor <Score text="shadowColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **shadowColor**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **shadowColor**(`inShadowColor`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取字体阴影颜色

#### Returns

| [`LinearColor`](mw.LinearColor.md) | 字体阴影颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置字体阴影颜色

#### Parameters

| `inShadowColor` [`LinearColor`](mw.LinearColor.md) | 输入的颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### shadowOffset <Score text="shadowOffset" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **shadowOffset**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **shadowOffset**(`inOffset`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取字体阴影偏移

#### Returns

| [`Vector2`](mw.Vector2.md) | 字体阴影偏移 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置字体阴影偏移

#### Parameters

| `inOffset` [`Vector2`](mw.Vector2.md) | 阴影偏移量 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### strikethroughEnable <Score text="strikethroughEnable" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **strikethroughEnable**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **strikethroughEnable**(`inEnableStrikethrough`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否开启字体删除线

#### Returns

| `boolean` | 是否开启字体删除线 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否开启字体删除线

#### Parameters

| `inEnableStrikethrough` `boolean` | 是否开启 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### text <Score text="text" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **text**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **text**(`InString`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取按钮文字

#### Returns

| `string` | 返回文字 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置按钮文字

#### Parameters

| `InString` `string` | 文字 |
| :------ | :------ |


新文本


</td>
</tr></tbody>
</table>

___

### textAlign <Score text="textAlign" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **textAlign**(): [`TextJustify`](../enums/mw.TextJustify.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **textAlign**(`InTextJustify`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取字体对齐方式

#### Returns

| [`TextJustify`](../enums/mw.TextJustify.md) | 字体对齐方式 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置字体对齐方式

#### Parameters

| `InTextJustify` [`TextJustify`](../enums/mw.TextJustify.md) | 对齐方式的枚举 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### textVerticalAlign <Score text="textVerticalAlign" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **textVerticalAlign**(): [`TextVerticalJustify`](../enums/mw.TextVerticalJustify.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **textVerticalAlign**(`inTextVerticalJustify`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取字体垂直对齐方式

#### Returns

| [`TextVerticalJustify`](../enums/mw.TextVerticalJustify.md) | 字体垂直对齐方式 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置字体垂直对齐方式

#### Parameters

| `inTextVerticalJustify` [`TextVerticalJustify`](../enums/mw.TextVerticalJustify.md) | 对齐方式 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### underlineEnable <Score text="underlineEnable" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **underlineEnable**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **underlineEnable**(`inEnableUnderline`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


返回是否开启字体下划线

#### Returns

| `boolean` | 获取是否开启字体下划线 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否开启字体下划线

#### Parameters

| `inEnableUnderline` `boolean` | 设置是否开启下划线 |
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

| `key` [`Keys`](../enums/mw.Keys.md) | 按键 |
| :------ | :------ |


___

### getKeys <Score text="getKeys" /> 

• **getKeys**(): [`Keys`](../enums/mw.Keys.md)[] <Badge type="tip" text="client" />

获取当前UI控件绑定的所有键盘按键，包括编辑器按键绑定菜单和用代码绑定的按键

#### Returns

| [`Keys`](../enums/mw.Keys.md)[] | 返回当前控件绑定的按键,可能为空 |
| :------ | :------ |

___

### removeKey <Score text="removeKey" /> 

• **removeKey**(`key`): `void` <Badge type="tip" text="client" />

此操作只会解绑动态绑定的按键无法解除编辑器按键绑定菜单中绑定的按键

#### Parameters

| `key` [`Keys`](../enums/mw.Keys.md) | 按键 |
| :------ | :------ |


___

### newObject <Score text="newObject" /> 

• `Static` **newObject**(`parent?`, `inName?`): [`AdsButton`](mw.AdsButton.md) <Badge type="tip" text="client" />

创建 Button 控件

#### Parameters

| `parent?` [`Canvas`](mw.Canvas.md) | 创建控件的外parent对象 default: null |
| :------ | :------ |
| `inName?` `string` | 创建控件的名称 default:null range:无 |

#### Returns

| [`AdsButton`](mw.AdsButton.md) | 返回创建的对象 |
| :------ | :------ |

当parent和inName与已有的对象相同时，旧的对象会被销毁
