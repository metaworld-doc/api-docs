[界面](../groups/界面.界面.md) / Dropdown

# Dropdown <Badge type="tip" text="Class" /> <Score text="Dropdown" />

Dropdown

## Hierarchy

- [`Widget`](mw.Widget.md)

  ↳ **`Dropdown`**

## Table of contents

### Properties <Score text="Properties" /> 


::: details click
### Properties <Score text="Properties" /> 
| **[onCustomPropertyChange](mw.Widget.md#oncustompropertychange)**: `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> <Badge type="tip" text="client" />  |
| :-----|
| 监听自定义属性同步事件|
:::


### Accessors <Score text="Accessors" /> 
| **[defaultFont](mw.Dropdown.md#defaultfont)**(): `string`  [`UIFontFamily`](../enums/mw.UIFontFamily.md) <Badge type="tip" text="client" />  |
| :-----|
| 获取默认字体|
| **[dropdownStyle](mw.Dropdown.md#dropdownstyle)**(): [`DropdownStyle`](mw.DropdownStyle.md) <Badge type="tip" text="client" />  |
| 菜单样式|
| **[fallbackFont](mw.Dropdown.md#fallbackfont)**(): `string`  [`UIFontFamily`](../enums/mw.UIFontFamily.md) <Badge type="tip" text="client" />  |
| 获取退却字体|
| **[glyph](mw.Dropdown.md#glyph)**(): [`UIFontGlyph`](../enums/mw.UIFontGlyph.md) <Badge type="tip" text="client" />  |
| 获取字体字形|
| **[isOpened](mw.Dropdown.md#isopened)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取菜单是否打开|
| **[menuRowStyle](mw.Dropdown.md#menurowstyle)**(): [`ListItemStyle`](mw.ListItemStyle.md) <Badge type="tip" text="client" />  |
| ListItemStyle样式|
| **[onOpeningEvent](mw.Dropdown.md#onopeningevent)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />  |
| 打开下拉菜单前触发事件|
| **[onSelectionChangedEvent](mw.Dropdown.md#onselectionchangedevent)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`item`: `string`, `select`: [`SelectInfo`](../enums/mw.SelectInfo.md)) => `void`\> <Badge type="tip" text="client" />  |
| 选中改动事件|
| **[optionCount](mw.Dropdown.md#optioncount)**(): `number` <Badge type="tip" text="client" />  |
| 获取菜单项数量|
| **[options](mw.Dropdown.md#options)**(): `string`[] <Badge type="tip" text="client" />  |
| 获取所有菜单项|
| **[scrollbarStyle](mw.Dropdown.md#scrollbarstyle)**(): [`ScrollbarStyle`](mw.ScrollbarStyle.md) <Badge type="tip" text="client" />  |
| 滚动条样式|
| **[selectedOption](mw.Dropdown.md#selectedoption)**(): `string` <Badge type="tip" text="client" />  |
| 获取当前选中项|
| **[selectedOptionIndex](mw.Dropdown.md#selectedoptionindex)**(): `number` <Badge type="tip" text="client" />  |
| 获取选中项下拉索引|
| **[textStyle](mw.Dropdown.md#textstyle)**(): [`TextStyle`](mw.TextStyle.md) <Badge type="tip" text="client" />  |
| 文本样式|


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
| **[addOption](mw.Dropdown.md#addoption)**(`option`: `string`): `void` <Badge type="tip" text="client" />  |
| :-----|
| 添加菜单项|
| **[clearOptions](mw.Dropdown.md#clearoptions)**(): `void` <Badge type="tip" text="client" />  |
| 清空所有菜单项|
| **[clearSelection](mw.Dropdown.md#clearselection)**(): `void` <Badge type="tip" text="client" />  |
| 清空所有选中|
| **[findOptionIndex](mw.Dropdown.md#findoptionindex)**(`option`: `string`): `number` <Badge type="tip" text="client" />  |
| 获取下拉顺序坐标|
| **[getOptionByIndex](mw.Dropdown.md#getoptionbyindex)**(`index`: `number`): `string` <Badge type="tip" text="client" />  |
| 菜单项内容|
| **[getShowTextVisible](mw.Dropdown.md#getshowtextvisible)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取显示的选中文本的可见性|
| **[removeOption](mw.Dropdown.md#removeoption)**(`option`: `string`): `void` <Badge type="tip" text="client" />  |
| 移除菜单项|
| **[setOptionByIndex](mw.Dropdown.md#setoptionbyindex)**(`index`: `number`, `value`: `string`): `void` <Badge type="tip" text="client" />  |
| 修改索引处的值|
| **[setShowTextVisible](mw.Dropdown.md#setshowtextvisible)**(`bVisible`: `boolean`): `void` <Badge type="tip" text="client" />  |
| 设置显示的选中文本的可见性|
| **[newObject](mw.Dropdown.md#newobject)**(`parent?`: [`Canvas`](mw.Canvas.md), `inName?`: `string`): [`Dropdown`](mw.Dropdown.md) <Badge type="tip" text="client" />  |
| 创建Canvas控件 当parent和inName与已有的对象相同时，旧的对象会被销毁|


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

### dropdownStyle <Score text="dropdownStyle" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **dropdownStyle**(): [`DropdownStyle`](mw.DropdownStyle.md) <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


菜单样式

#### Returns

| [`DropdownStyle`](mw.DropdownStyle.md) | 返回菜单样式 |
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

### isOpened <Score text="isOpened" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **isOpened**(): `boolean` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取菜单是否打开

#### Returns

| `boolean` | 菜单是否打开 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### menuRowStyle <Score text="menuRowStyle" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **menuRowStyle**(): [`ListItemStyle`](mw.ListItemStyle.md) <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


ListItemStyle样式

#### Returns

| [`ListItemStyle`](mw.ListItemStyle.md) | 返回ListItemStyle样式 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onOpeningEvent <Score text="onOpeningEvent" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onOpeningEvent**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


打开下拉菜单前触发事件

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> | 返回事件 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onSelectionChangedEvent <Score text="onSelectionChangedEvent" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onSelectionChangedEvent**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`item`: `string`, `select`: [`SelectInfo`](../enums/mw.SelectInfo.md)) => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


选中改动事件

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<(`item`: `string`, `select`: [`SelectInfo`](../enums/mw.SelectInfo.md)) => `void`\> | 返回选中改动事件 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### optionCount <Score text="optionCount" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **optionCount**(): `number` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取菜单项数量

#### Returns

| `number` | 菜单项数量 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### options <Score text="options" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **options**(): `string`[] <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **options**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取所有菜单项

#### Returns

| `string`[] | 所有菜单项 |
| :------ | :------ |


</td>
<td style="text-align: left">


获取所有菜单项

#### Parameters

| `value` `string`[] |  传进来的字符串数组 <br> range: 无 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### scrollbarStyle <Score text="scrollbarStyle" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **scrollbarStyle**(): [`ScrollbarStyle`](mw.ScrollbarStyle.md) <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


滚动条样式

#### Returns

| [`ScrollbarStyle`](mw.ScrollbarStyle.md) | 返回滚动条样式 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### selectedOption <Score text="selectedOption" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **selectedOption**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **selectedOption**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取当前选中项

#### Returns

| `string` | 当前选中项 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置前选中项

#### Parameters

| `value` `string` | 传进来的文本 range: 无 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### selectedOptionIndex <Score text="selectedOptionIndex" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **selectedOptionIndex**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **selectedOptionIndex**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取选中项下拉索引

#### Returns

| `number` | 选中项下拉索引 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置选中项下拉索引

#### Parameters

| `value` `number` | 设置的索引值 range: 无 type: 整形 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### textStyle <Score text="textStyle" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **textStyle**(): [`TextStyle`](mw.TextStyle.md) <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


文本样式

#### Returns

</td>
</tr></tbody>
</table>

| [`TextStyle`](mw.TextStyle.md) | 返回文本样式 |
| :------ | :------ |

## Methods

___

### addOption <Score text="addOption" /> 

• **addOption**(`option`): `void` <Badge type="tip" text="client" />

添加菜单项

#### Parameters

| `option` `string` | 菜单项 <br> range: 无 |
| :------ | :------ |


___

### clearOptions <Score text="clearOptions" /> 

• **clearOptions**(): `void` <Badge type="tip" text="client" />

清空所有菜单项


___

### clearSelection <Score text="clearSelection" /> 

• **clearSelection**(): `void` <Badge type="tip" text="client" />

清空所有选中


___

### findOptionIndex <Score text="findOptionIndex" /> 

• **findOptionIndex**(`option`): `number` <Badge type="tip" text="client" />

获取下拉顺序坐标

#### Parameters

| `option` `string` | 菜单项 <br> range: 无 |
| :------ | :------ |

#### Returns

| `number` | 下拉顺序坐标 |
| :------ | :------ |

___

### getOptionByIndex <Score text="getOptionByIndex" /> 

• **getOptionByIndex**(`index`): `string` <Badge type="tip" text="client" />

菜单项内容

#### Parameters

| `index` `number` | 下拉顺序坐标 <br> range: 无 type: 整形 |
| :------ | :------ |

#### Returns

| `string` | 获取菜单项内容 |
| :------ | :------ |

___

### getShowTextVisible <Score text="getShowTextVisible" /> 

• **getShowTextVisible**(): `boolean` <Badge type="tip" text="client" />

获取显示的选中文本的可见性

#### Returns

| `boolean` | 文本的可见性 |
| :------ | :------ |

___

### removeOption <Score text="removeOption" /> 

• **removeOption**(`option`): `void` <Badge type="tip" text="client" />

移除菜单项

#### Parameters

| `option` `string` | 菜单项 <br> range: 无 |
| :------ | :------ |


___

### setOptionByIndex <Score text="setOptionByIndex" /> 

• **setOptionByIndex**(`index`, `value`): `void` <Badge type="tip" text="client" />

修改索引处的值

#### Parameters

| `index` `number` |  索引 <br> range: 对应的索引值，不做限制。 <br> type: 整形 |
| :------ | :------ |
| `value` `string` |  值 <br> range: 无 |


___

### setShowTextVisible <Score text="setShowTextVisible" /> 

• **setShowTextVisible**(`bVisible`): `void` <Badge type="tip" text="client" />

设置显示的选中文本的可见性

#### Parameters

| `bVisible` `boolean` |  自定义UI的GUID range: [true,false] |
| :------ | :------ |


___

### newObject <Score text="newObject" /> 

• `Static` **newObject**(`parent?`, `inName?`): [`Dropdown`](mw.Dropdown.md) <Badge type="tip" text="client" />

创建Canvas控件 当parent和inName与已有的对象相同时，旧的对象会被销毁

#### Parameters

| `parent?` [`Canvas`](mw.Canvas.md) | 创建控件的外parent对象 default:null |
| :------ | :------ |
| `inName?` `string` | 创建控件的名称 default:null <br> range: 无 |

#### Returns

| [`Dropdown`](mw.Dropdown.md) | 返回创建的对象 |
| :------ | :------ |
