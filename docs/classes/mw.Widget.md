[界面](../groups/界面.界面.md) / Widget

# Widget <Badge type="tip" text="Class" /> <Score text="Widget" />

控件的基类

---------------

可挂载叶子节点的根节点，以及提供各种自动布局功能。

放置控件需要的通用属性与方法。

## Hierarchy

- **`Widget`**

  ↳ [`AdsButton`](mw.AdsButton.md)

  ↳ [`Checkbox`](mw.Checkbox.md)

  ↳ [`ColorPick`](mw.ColorPick.md)

  ↳ [`DrawCanvas`](mw.DrawCanvas.md)

  ↳ [`Dropdown`](mw.Dropdown.md)

  ↳ [`FlipBook`](mw.FlipBook.md)

  ↳ [`Image`](mw.Image.md)

  ↳ [`InputBox`](mw.InputBox.md)

  ↳ [`ListView`](mw.ListView.md)

  ↳ [`MaskButton`](mw.MaskButton.md)

  ↳ [`Mask`](mw.Mask.md)

  ↳ [`MenuAnchor`](mw.MenuAnchor.md)

  ↳ [`PanelWidget`](Core.mw.PanelWidget.md)

  ↳ [`ProgressBar`](mw.ProgressBar.md)

  ↳ [`StaleButton`](mw.StaleButton.md)

  ↳ [`TextBlock`](mw.TextBlock.md)

  ↳ [`TouchPad`](mw.TouchPad.md)

  ↳ [`TreeView`](mw.TreeView.md)

  ↳ [`UserWidget`](mw.UserWidget.md)

  ↳ [`VirtualJoystickPanel`](mw.VirtualJoystickPanel.md)

## Table of contents

### Properties <Score text="Properties" /> 
| **[onCustomPropertyChange](mw.Widget.md#oncustompropertychange)**: `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> <Badge type="tip" text="client" />  |
| :-----|
| 监听自定义属性同步事件|

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

## Properties

### onCustomPropertyChange <Score text="onCustomPropertyChange" /> 

• **onCustomPropertyChange**: `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> <Badge type="tip" text="client" />

监听自定义属性同步事件

<span style="font-size: 14px;">
使用示例:监听自定义属性变化
</span>

```ts
this.onCustomPropertyChange.add((path, value, oldValue) => {
    console.log(`属性 ${path} 改变了，新值为 ${value}，旧值为 ${oldValue}`);
});
```

## Accessors

### alignPosition <Score text="alignPosition" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **alignPosition**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **alignPosition**(`inFigmaPosition`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取控件的对齐位置,在对齐方式为靠右对齐、靠下对齐、中心对齐时，alignPosition的值与positon不同；

此时，两套位置计算的坐标系不同，例如设置为右下对齐时，该控件的alignPosition以父级右下角为原点来计算

#### Returns

| `Readonly`<[`Vector2`](mw.Vector2.md)\> | 控件的对齐位置 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置控件的对齐位置,在对齐方式为靠右对齐、靠下对齐、中心对齐时，alignPosition的值与positon不同；

此时，两套位置计算的坐标系不同，例如设置为右下对齐时，该控件的alignPosition以父级右下角为原点来计算

#### Parameters

| `inFigmaPosition` [`Vector2`](mw.Vector2.md) | 控件的对齐位置 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### autoSizeHorizontalEnable <Score text="autoSizeHorizontalEnable" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **autoSizeHorizontalEnable**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **autoSizeHorizontalEnable**(`bEnabled`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否自动水平设置大小

#### Returns

| `boolean` | 是否自动水平设置大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


获取是否自动水平设置大小

#### Parameters

| `bEnabled` | `boolean` |
| :------ | :------ |


是否自动水平设置大小


</td>
</tr></tbody>
</table>

___

### autoSizeVerticalEnable <Score text="autoSizeVerticalEnable" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **autoSizeVerticalEnable**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **autoSizeVerticalEnable**(`bEnabled`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否自动垂直设置大小

#### Returns

| `boolean` | 是否自动垂直设置大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


获取是否自动垂直设置大小

#### Parameters

| `bEnabled` | `boolean` |
| :------ | :------ |


是否自动垂直设置大小


</td>
</tr></tbody>
</table>

___

### cachedGeometry <Score text="cachedGeometry" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **cachedGeometry**(): [`Geometry`](mw.Geometry.md) <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取上一次的GetTickSpaceGeometry

#### Returns

| [`Geometry`](mw.Geometry.md) | 返回上一次的 GetTickSpaceGeometry |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### constraints <Score text="constraints" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **constraints**(): `Readonly`<[`UIConstraintAnchors`](mw.UIConstraintAnchors.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **constraints**(`ininconstraints`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取控件的布局

#### Returns

| `Readonly`<[`UIConstraintAnchors`](mw.UIConstraintAnchors.md)\> | 控件的布局 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置控件的布局

#### Parameters

| `ininconstraints` [`UIConstraintAnchors`](mw.UIConstraintAnchors.md) | 控件的布局 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### desiredSize <Score text="desiredSize" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **desiredSize**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取期望大小

#### Returns

| [`Vector2`](mw.Vector2.md) | 返回期望大小 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### enable <Score text="enable" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **enable**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **enable**(`isEnable`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


是否可用

#### Returns

| `boolean` | boolean |
| :------ | :------ |


</td>
<td style="text-align: left">


设置可用性

#### Parameters

| `isEnable` `boolean` | 可用性boolean |
| :------ | :------ |


返回设置结果


</td>
</tr></tbody>
</table>

___

### guid <Score text="guid" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **guid**(): `string` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取控件GUID

#### Returns

| `string` | 控件GUID |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### isHovered <Score text="isHovered" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **isHovered**(): `boolean` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


是否是hovered

#### Returns

| `boolean` | boolean |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### mouseCursor <Score text="mouseCursor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **mouseCursor**(): [`MouseCursor`](../enums/mw.MouseCursor.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **mouseCursor**(`type`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取控件上光标类型

#### Returns

| [`MouseCursor`](../enums/mw.MouseCursor.md) | 光标类型 |
| :------ | :------ |


</td>
<td style="text-align: left">


将光标类型设置到控件上

#### Parameters

| `type` | [`MouseCursor`](../enums/mw.MouseCursor.md) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### name <Score text="name" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **name**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **name**(`name`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取名字

#### Returns

| `string` | 返回名字 |
| :------ | :------ |


</td>
<td style="text-align: left">


设定名字

#### Parameters

| `name` `string` | 名字 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### paintSpaceGeometry <Score text="paintSpaceGeometry" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **paintSpaceGeometry**(): [`Geometry`](mw.Geometry.md) <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取最后一次用于渲染Widget的几何信息

#### Returns

| [`Geometry`](mw.Geometry.md) | 返回最后一次用于渲染Widget的几何信息 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### parent <Score text="parent" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **parent**(): [`Widget`](mw.Widget.md) <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取父节点

#### Returns

| [`Widget`](mw.Widget.md) | 返回父节点 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### pivot <Score text="pivot" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **pivot**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **pivot**(`inPivot`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取控件锚点位置,这个属性决定了控件图形与锚点的相对位置；(0,0)时，锚点位于控件左上角；(0.5,0.5)时，锚点位于控件正中心

锚点本身的位置由positon或alignPosition决定

#### Returns

| [`Vector2`](mw.Vector2.md) | 控件的锚点位置 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置控件锚点位置,这个属性决定了控件图形与锚点的相对位置；(0,0)时，锚点位于控件左上角；(0.5,0.5)时，锚点位于控件正中心;

锚点本身的位置由positon或alignPosition决定

#### Parameters

| `inPivot` [`Vector2`](mw.Vector2.md) | 输入的锚点位置 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### position <Score text="position" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **position**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **position**(`inFigmaPosition`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取控件的位置

#### Returns

| `Readonly`<[`Vector2`](mw.Vector2.md)\> | 控件的位置 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置控件的位置

#### Parameters

| `inFigmaPosition` [`Vector2`](mw.Vector2.md) | 控件的位置 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### renderOpacity <Score text="renderOpacity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **renderOpacity**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **renderOpacity**(`InOpacity`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取渲染透明度

#### Returns

| `number` | 返回渲染透明度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置渲染透明度 0 ~ 1

#### Parameters

| `InOpacity` `number` | 透明度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### renderScale <Score text="renderScale" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **renderScale**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **renderScale**(`scale`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取渲染缩放

#### Returns

| [`Vector2`](mw.Vector2.md) | 返回渲染缩放 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置渲染缩放

#### Parameters

| `scale` [`Vector2`](mw.Vector2.md) | 渲染缩放 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### renderShear <Score text="renderShear" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **renderShear**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **renderShear**(`shear`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取渲染错切形变

#### Returns

| [`Vector2`](mw.Vector2.md) | 返回渲染错切形变 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置渲染错切形变

#### Parameters

| `shear` [`Vector2`](mw.Vector2.md) | 渲染错切形变 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### renderTransformAngle <Score text="renderTransformAngle" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **renderTransformAngle**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **renderTransformAngle**(`o`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取渲染的角度

#### Returns

| `number` | 返回渲染角度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置渲染的角度

#### Parameters

| `o` `number` | 渲染角度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### renderTransformPivot <Score text="renderTransformPivot" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **renderTransformPivot**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **renderTransformPivot**(`Pivot`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取渲染锚点

#### Returns

| [`Vector2`](mw.Vector2.md) | 返回渲染锚点 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置渲染锚点

#### Parameters

| `Pivot` [`Vector2`](mw.Vector2.md) | 渲染锚点 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### size <Score text="size" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **size**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **size**(`inSize`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取大小

#### Returns

| [`Vector2`](mw.Vector2.md) | FVector2D |
| :------ | :------ |


</td>
<td style="text-align: left">


设置控件的大小

#### Parameters

| `inSize` [`Vector2`](mw.Vector2.md) | 输入大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### tickSpaceGeometry <Score text="tickSpaceGeometry" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **tickSpaceGeometry**(): [`Geometry`](mw.Geometry.md) <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取最后一次用于驱动Widget Tick的几何信息

#### Returns

| [`Geometry`](mw.Geometry.md) | 返回最后一次用于驱动Widget Tick的几何信息 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### transform <Score text="transform" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **transform**(): `Readonly`<[`UITransform`](mw.UITransform.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **transform**(`inTransform`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


得到控件的大小和位置

#### Returns

| `Readonly`<[`UITransform`](mw.UITransform.md)\> | 控件的大小和位置 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置控件的大小和位置

#### Parameters

| `inTransform` [`UITransform`](mw.UITransform.md) | 大小位置 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### visibility <Score text="visibility" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **visibility**(): [`SlateVisibility`](../enums/mw.SlateVisibility.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **visibility**(`Visibility`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取可见性

#### Returns

| [`SlateVisibility`](../enums/mw.SlateVisibility.md) | 返回可见性 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置可见性

#### Parameters

| `Visibility` [`SlateVisibility`](../enums/mw.SlateVisibility.md) | 可见性 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### visible <Score text="visible" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **visible**(): `boolean` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


是否可见

#### Returns

| `boolean` | boolean |
| :------ | :------ |

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

• `set` **zOrder**(`InZOrder`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取zorder

#### Returns

| `number` | zorder |
| :------ | :------ |


</td>
<td style="text-align: left">


设置zoder

#### Parameters

| `InZOrder` `number` | 值越大在越上层 |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods

### addChild <Score text="addChild" /> 

• **addChild**(`child`): `void` <Badge type="tip" text="client" />

添加子节点

#### Parameters

| `child` [`Widget`](mw.Widget.md) | 子控件 |
| :------ | :------ |


___

### clone <Score text="clone" /> 

• **clone**(`position`, `Parent?`): [`Widget`](mw.Widget.md) <Badge type="tip" text="client" />

克隆UI控件及其子节点到指定父控件位置（默认到其父节点）

#### Parameters

| `position` [`Vector2`](mw.Vector2.md) | 克隆后控件生成的位置 |
| :------ | :------ |
| `Parent?` [`Widget`](mw.Widget.md) | 克隆后的控件需要在该控件下生成 default: undefined |

#### Returns

| [`Widget`](mw.Widget.md) | 克隆生成的UI控件 |
| :------ | :------ |

___

### destroyObject <Score text="destroyObject" /> 

• **destroyObject**(): `void` <Badge type="tip" text="client" />

立刻移除并销毁 不可以在使用


___

### equal <Score text="equal" /> 

• **equal**(`that`): `boolean` <Badge type="tip" text="client" />

判断是不是同一个对象

#### Parameters

| `that` [`Widget`](mw.Widget.md) | 需要比较的另外一个对象 |
| :------ | :------ |

#### Returns

| `boolean` | boolean |
| :------ | :------ |

___

### findChildByPath <Score text="findChildByPath" /> 

• **findChildByPath**(`inPath`): [`Widget`](mw.Widget.md) <Badge type="tip" text="client" />

通过相对路径查找节点

#### Parameters

| `inPath` `string` | 路径 range: 不限制 |
| :------ | :------ |

#### Returns

| [`Widget`](mw.Widget.md) | 返回查找节点结果 |
| :------ | :------ |

___

### getChildAt <Score text="getChildAt" /> 

• **getChildAt**(`index`): [`Widget`](mw.Widget.md) <Badge type="tip" text="client" />

获取第几位子节点

#### Parameters

| `index` `number` | 下标 range:大于等于0 type: 整形 |
| :------ | :------ |

#### Returns

| [`Widget`](mw.Widget.md) | 找到的控件 |
| :------ | :------ |

___

### getChildByName <Score text="getChildByName" /> 

• **getChildByName**<`T`\>(`name`): `T` <Badge type="tip" text="client" />

通过名字查找节点

#### Parameters

| `name` `string` | 名字 <br> range: 不限制 |
| :------ | :------ |

#### Returns

| `T` | 找到的控件 |
| :------ | :------ |

#### Type parameters

| `T` | extends [`Widget`](mw.Widget.md)<`T`\> |
| :------ | :------ |

___

### getChildrenCount <Score text="getChildrenCount" /> 

• **getChildrenCount**(): `number` <Badge type="tip" text="client" />

获取子节点数量

#### Returns

| `number` | 子节点数量 |
| :------ | :------ |

___

### getCustomProperties <Score text="getCustomProperties" /> 

• **getCustomProperties**(): `string`[] <Badge type="tip" text="client" />

获取所有自定义属性

#### Returns

| `string`[] | 属性名列表 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:获取所有自定义属性
</span>

```ts
const attributes = this.getAttributes();
console.log(attributes);
// ["name", "age"]
```

___

### getCustomProperty <Score text="getCustomProperty" /> 

• **getCustomProperty**<`T`\>(`propertyName`): `T` <Badge type="tip" text="client" />

获取自定义属性

#### Parameters

| `propertyName` `string` | 对象属性名字 range: 无 |
| :------ | :------ |

#### Returns

| `T` | 属性值 |
| :------ | :------ |

#### Type parameters

| `T` | extends [`CustomPropertyType`](../modules/Core.mw.md#custompropertytype) |
| :------ | :------ |

___

### getCustomPropertyChangeDelegate <Score text="getCustomPropertyChangeDelegate" /> 

• **getCustomPropertyChangeDelegate**(`property`): `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> <Badge type="tip" text="client" />

给定对象属性修改时触发的事件代理

#### Parameters

| `property` `string` | 对象属性名字 range: 无 |
| :------ | :------ |

#### Returns

| `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> | 代理对象 |
| :------ | :------ |

___

### invalidateLayoutAndVolatility <Score text="invalidateLayoutAndVolatility" /> 

• **invalidateLayoutAndVolatility**(): `void` <Badge type="tip" text="client" />

立刻触发重新渲染的和排布计算


___

### isValid <Score text="isValid" /> 

• **isValid**(): `boolean` <Badge type="tip" text="client" />

判断控件有没有被销毁，是否是有效的控件

#### Returns

| `boolean` | boolean 是否还有效，判定有没有被销毁 |
| :------ | :------ |

___

### removeAllChildren <Score text="removeAllChildren" /> 

• **removeAllChildren**(): `void` <Badge type="tip" text="client" />

清除所有子节点,会销毁UI无法再使用


___

### removeChild <Score text="removeChild" /> 

• **removeChild**(`child`): `void` <Badge type="tip" text="client" />

移除节点,会销毁UI无法在使用

#### Parameters

| `child` [`Widget`](mw.Widget.md) | 需要移除的子控件 |
| :------ | :------ |


___

### removeChildAt <Score text="removeChildAt" /> 

• **removeChildAt**(`index`): `void` <Badge type="tip" text="client" />

移除第几个节点,会销毁UI无法再使用

#### Parameters

| `index` `number` | 下标 range: 大于 0 type: 整形 |
| :------ | :------ |


___

### removeObject <Score text="removeObject" /> 

• **removeObject**(): `void` <Badge type="tip" text="client" />

立刻移除并添加到根节点 可以再使用


___

### serialize <Score text="serialize" /> 

• **serialize**(): `string` <Badge type="tip" text="client" />

序列化UI控件

#### Returns

| `string` | 返回传入控件序列化后的JSON字符串 |
| :------ | :------ |

___

### setCustomProperty <Score text="setCustomProperty" /> 

• **setCustomProperty**(`propertyName`, `value`): `void` <Badge type="tip" text="client" />

设置自定义属性

#### Parameters

| `propertyName` `string` | 对象属性名字 range: 无 |
| :------ | :------ |
| `value` `undefined`  [`CustomPropertyType`](../modules/Core.mw.md#custompropertytype) | 属性值 |


___

### deserialize <Score text="deserialize" /> 

• `Static` **deserialize**(`Data`, `Parent?`): [`Widget`](mw.Widget.md) <Badge type="tip" text="client" />

反序列化UI

#### Parameters

| `Data` `string` | 需要反序列化的JSON字符串 range: 无 |
| :------ | :------ |
| `Parent?` [`Widget`](mw.Widget.md) | 生成的UI控件的父节点 default: undefined |

#### Returns

| [`Widget`](mw.Widget.md) | 返回传入JSON字符串反序列化后得到的UI |
| :------ | :------ |
