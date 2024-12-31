[界面](../groups/界面.界面.md) / TreeView

# TreeView <Badge type="tip" text="Class" /> <Score text="TreeView" />

树状视图

## Hierarchy

- [`Widget`](mw.Widget.md)

  ↳ **`TreeView`**

## Table of contents

### Properties <Score text="Properties" /> 


::: details click
### Properties <Score text="Properties" /> 
| **[onCustomPropertyChange](mw.Widget.md#oncustompropertychange)**: `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> <Badge type="tip" text="client" />  |
| :-----|
| 监听自定义属性同步事件|
:::


### Accessors <Score text="Accessors" /> 
| **[clearSelectionOnClick](mw.TreeView.md#clearselectiononclick)**(`clearSelection`: `boolean`): `void` <Badge type="tip" text="client" />  |
| :-----|
| 设置是否在点击空白后清除选中项（仅初始化时设置有效）|
| **[itemIndentAmount](mw.TreeView.md#itemindentamount)**(): `number` <Badge type="tip" text="client" />  |
| 获取子项缩进距离|
| **[itemPadding](mw.TreeView.md#itempadding)**(): [`Margin`](mw.Margin.md)  |
| 获取视图节点边距|
| **[listItems](mw.TreeView.md#listitems)**(): readonly [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)[] <Badge type="tip" text="client" />  |
| 获取列表数据|
| **[onItemClicked](mw.TreeView.md#onitemclicked)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`clickedItem`: [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md), `doubleClick`: `boolean`) => `void`\> <Badge type="tip" text="client" />  |
| 返回点击代理|
| **[onItemExpansionChanged](mw.TreeView.md#onitemexpansionchanged)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`targetItem`: [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md), `expanded`: `boolean`) => `void`\> <Badge type="tip" text="client" />  |
| 展开状态修改代理|
| **[onItemHoverChanged](mw.TreeView.md#onitemhoverchanged)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`targetItem`: [`Widget`](mw.Widget.md), `hovered`: `boolean`) => `void`\> <Badge type="tip" text="client" />  |
| 返回悬停状态改变代理|
| **[onItemRefreshed](mw.TreeView.md#onitemrefreshed)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`rowDatas`: [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)[]) => `void`\> <Badge type="tip" text="client" />  |
| 返回UI刷新生成同步代理|
| **[onItemReleaseShow](mw.TreeView.md#onitemreleaseshow)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`targetItem`: [`Widget`](mw.Widget.md)) => `void`\> <Badge type="tip" text="client" />  |
| 子控件移除显示时调用，等待复用前|
| **[onItemSelected](mw.TreeView.md#onitemselected)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`selectedItem`: [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md), `selectType`: [`SelectInfo`](../enums/mw.SelectInfo.md)) => `void`\> <Badge type="tip" text="client" />  |
| 返回选择修改代理,取消选中/清空也会触发选中修改，返回参数selectedItem == null, 请注意判断|
| **[scrollBarStyle](mw.TreeView.md#scrollbarstyle)**(): [`ScrollbarStyle`](mw.ScrollbarStyle.md) <Badge type="tip" text="other" />  |
| 滚动条样式|
| **[scrollBarVisible](mw.TreeView.md#scrollbarvisible)**(): `boolean` <Badge type="tip" text="other" />  |
| 滚动条可见性|
| **[scrollOffset](mw.TreeView.md#scrolloffset)**(): `number` <Badge type="tip" text="client" />  |
| 获取当前滚动条偏移位置|
| **[selectionMode](mw.TreeView.md#selectionmode)**(): [`SelectionMode`](../enums/mw.SelectionMode.md) <Badge type="tip" text="client" />  |
| 获取选中模式|
| **[tableRowStyle](mw.TreeView.md#tablerowstyle)**(): [`ListItemStyle`](mw.ListItemStyle.md) <Badge type="tip" text="other" />  |
| Item项目节点样式设置|


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
| **[addItems](mw.TreeView.md#additems)**(`newListItems`: [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)[]): `void` <Badge type="tip" text="client" />  |
| :-----|
| 添加项目节点数据|
| **[clearItems](mw.TreeView.md#clearitems)**(): `void` <Badge type="tip" text="client" />  |
| 清理数据组|
| **[clearSelection](mw.TreeView.md#clearselection)**(): `void` <Badge type="tip" text="client" />  |
| 清空列表的选中|
| **[getExpandedItems](mw.TreeView.md#getexpandeditems)**(): [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)[] <Badge type="tip" text="client" />  |
| 获取所有展开的节点|
| **[getItemExpansion](mw.TreeView.md#getitemexpansion)**(`targetItem`: [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)): `boolean` <Badge type="tip" text="client" />  |
| 获取节点的展开状态|
| **[getSelectionItems](mw.TreeView.md#getselectionitems)**(): [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)[] <Badge type="tip" text="client" />  |
| 获取选中节点的数据|
| **[getShowItemsCount](mw.TreeView.md#getshowitemscount)**(): `number` <Badge type="tip" text="client" />  |
| 获取当前展示的条目的数量|
| **[getTouchCanControlThisScroll](mw.TreeView.md#gettouchcancontrolthisscroll)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取是否受Touch事件影响滚动|
| **[insertItem](mw.TreeView.md#insertitem)**(`newItem`: [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md), `index`: `number`): `void` <Badge type="tip" text="client" />  |
| 插入项目节点数据，如果位置越界，则自动插入最后|
| **[regenerateTreeData](mw.TreeView.md#regeneratetreedata)**(`regenItems`: [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)[]): `void` <Badge type="tip" text="client" />  |
| 重新生成树刷新数据|
| **[removeItem](mw.TreeView.md#removeitem)**(`delItem`: [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)): `void` <Badge type="tip" text="client" />  |
| 移除项目节点数据|
| **[requestRefresh](mw.TreeView.md#requestrefresh)**(): `void` <Badge type="tip" text="client" />  |
| 刷新数据|
| **[resetListItems](mw.TreeView.md#resetlistitems)**(`newListItems`: [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)[]): `void` <Badge type="tip" text="client" />  |
| 重新设置项目节点数据组|
| **[scrollIntoView](mw.TreeView.md#scrollintoview)**(`targetItem`: [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)): `void` <Badge type="tip" text="client" />  |
| 滚动条定位到对应项目的位置|
| **[setItemExpansion](mw.TreeView.md#setitemexpansion)**(`targetItem`: [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md), `expandItem`: `boolean`): `void` <Badge type="tip" text="client" />  |
| 设置节点的展开状态|
| **[setSelectionItem](mw.TreeView.md#setselectionitem)**(`selectedItems`: [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)  [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)[], `selected`: `boolean`, `selectInfo?`: [`SelectInfo`](../enums/mw.SelectInfo.md)): `void` <Badge type="tip" text="client" />  |
| 设置节点选中|
| **[setTouchCanControlThisScroll](mw.TreeView.md#settouchcancontrolthisscroll)**(`bCanControl`: `boolean`): `void` <Badge type="tip" text="client" />  |
| 设置是否受Touch事件影响滚动|
| **[toggleItemExpansion](mw.TreeView.md#toggleitemexpansion)**(`targetItem`: [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)): `void` <Badge type="tip" text="client" />  |
| 修改节点的展开状态|
| **[newObject](mw.TreeView.md#newobject)**(`uiAssetGUID`: `string`, `parent?`: [`Canvas`](mw.Canvas.md), `inName?`: `string`): [`TreeView`](mw.TreeView.md) <Badge type="tip" text="client" />  |
| 创建 TreeView 控件，当parent和inName与已有的对象相同时，旧的对象会被销毁|


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

### clearSelectionOnClick <Score text="clearSelectionOnClick" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `set` **clearSelectionOnClick**(`clearSelection`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


设置是否在点击空白后清除选中项（仅初始化时设置有效）

#### Parameters

| `clearSelection` | `boolean` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### itemIndentAmount <Score text="itemIndentAmount" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **itemIndentAmount**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **itemIndentAmount**(`itemIndentAmount`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取子项缩进距离

#### Returns

| `number` | 返回子项缩进距离 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置子项缩进距离

#### Parameters

| `itemIndentAmount` `number` | 偏移量, 具体值需>=0, 负数无效果 range: [0, Inf) type: 整形 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### itemPadding <Score text="itemPadding" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **itemPadding**(): [`Margin`](mw.Margin.md)

</th>
<th style="text-align: left">

• `set` **itemPadding**(`padding`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取视图节点边距

#### Returns

| [`Margin`](mw.Margin.md) | 边距数据 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置视图节点边距

#### Parameters

| `padding` [`Margin`](mw.Margin.md) |  设置的边距数据 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### listItems <Score text="listItems" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **listItems**(): readonly [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)[] <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取列表数据

#### Returns

| readonly [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)[] | 返回列表数据 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onItemClicked <Score text="onItemClicked" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onItemClicked**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`clickedItem`: [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md), `doubleClick`: `boolean`) => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


返回点击代理

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<(`clickedItem`: [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md), `doubleClick`: `boolean`) => `void`\> | 返回点击代理 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onItemExpansionChanged <Score text="onItemExpansionChanged" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onItemExpansionChanged**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`targetItem`: [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md), `expanded`: `boolean`) => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


展开状态修改代理

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<(`targetItem`: [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md), `expanded`: `boolean`) => `void`\> | 返回展开状态修改代理 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onItemHoverChanged <Score text="onItemHoverChanged" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onItemHoverChanged**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`targetItem`: [`Widget`](mw.Widget.md), `hovered`: `boolean`) => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


返回悬停状态改变代理

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<(`targetItem`: [`Widget`](mw.Widget.md), `hovered`: `boolean`) => `void`\> | 返回选择修改代理 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onItemRefreshed <Score text="onItemRefreshed" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onItemRefreshed**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`rowDatas`: [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)[]) => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


返回UI刷新生成同步代理

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<(`rowDatas`: [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)[]) => `void`\> | 返回UI刷新生成同步代理 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onItemReleaseShow <Score text="onItemReleaseShow" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onItemReleaseShow**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`targetItem`: [`Widget`](mw.Widget.md)) => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


子控件移除显示时调用，等待复用前

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<(`targetItem`: [`Widget`](mw.Widget.md)) => `void`\> | 返回选择修改代理 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onItemSelected <Score text="onItemSelected" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onItemSelected**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`selectedItem`: [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md), `selectType`: [`SelectInfo`](../enums/mw.SelectInfo.md)) => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


返回选择修改代理,取消选中/清空也会触发选中修改，返回参数selectedItem == null, 请注意判断

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<(`selectedItem`: [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md), `selectType`: [`SelectInfo`](../enums/mw.SelectInfo.md)) => `void`\> | 返回选择修改代理 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### scrollBarStyle <Score text="scrollBarStyle" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **scrollBarStyle**(): [`ScrollbarStyle`](mw.ScrollbarStyle.md) <Badge type="tip" text="other" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


滚动条样式

#### Returns

| [`ScrollbarStyle`](mw.ScrollbarStyle.md) |  |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### scrollBarVisible <Score text="scrollBarVisible" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **scrollBarVisible**(): `boolean` <Badge type="tip" text="other" />

</th>
<th style="text-align: left">

• `set` **scrollBarVisible**(`bVisible`): `void` <Badge type="tip" text="other" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


滚动条可见性

#### Returns

| `boolean` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


滚动条可见性

#### Parameters

| `bVisible` | `boolean` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### scrollOffset <Score text="scrollOffset" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **scrollOffset**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **scrollOffset**(`scrollOffset`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取当前滚动条偏移位置

#### Returns

| `number` | 返回当前滚动条偏移位置 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置当前滚动条偏移位置

#### Parameters

| `scrollOffset` `number` | 偏移量，0为初始，1为最后 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### selectionMode <Score text="selectionMode" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **selectionMode**(): [`SelectionMode`](../enums/mw.SelectionMode.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **selectionMode**(`newSelectionMode`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取选中模式

#### Returns

| [`SelectionMode`](../enums/mw.SelectionMode.md) | 返回选中模式 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置选中模式

#### Parameters

| `newSelectionMode` [`SelectionMode`](../enums/mw.SelectionMode.md) | 选中模式 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### tableRowStyle <Score text="tableRowStyle" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **tableRowStyle**(): [`ListItemStyle`](mw.ListItemStyle.md) <Badge type="tip" text="other" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


Item项目节点样式设置

#### Returns

</td>
</tr></tbody>
</table>

| [`ListItemStyle`](mw.ListItemStyle.md) |  |
| :------ | :------ |

## Methods

___

### addItems <Score text="addItems" /> 

• **addItems**(`newListItems`): `void` <Badge type="tip" text="client" />

添加项目节点数据

#### Parameters

| `newListItems` [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)[] | 新的数据组 |
| :------ | :------ |


___

### clearItems <Score text="clearItems" /> 

• **clearItems**(): `void` <Badge type="tip" text="client" />

清理数据组


___

### clearSelection <Score text="clearSelection" /> 

• **clearSelection**(): `void` <Badge type="tip" text="client" />

清空列表的选中


___

### getExpandedItems <Score text="getExpandedItems" /> 

• **getExpandedItems**(): [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)[] <Badge type="tip" text="client" />

获取所有展开的节点

#### Returns

| [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)[] | 返回所有展开的节点 |
| :------ | :------ |

___

### getItemExpansion <Score text="getItemExpansion" /> 

• **getItemExpansion**(`targetItem`): `boolean` <Badge type="tip" text="client" />

获取节点的展开状态

#### Parameters

| `targetItem` [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md) | 目标数据 |
| :------ | :------ |

#### Returns

| `boolean` | 返回节点是否展开 |
| :------ | :------ |

___

### getSelectionItems <Score text="getSelectionItems" /> 

• **getSelectionItems**(): [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)[] <Badge type="tip" text="client" />

获取选中节点的数据

#### Returns

| [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)[] | 返回选中节点的数据 |
| :------ | :------ |

___

### getShowItemsCount <Score text="getShowItemsCount" /> 

• **getShowItemsCount**(): `number` <Badge type="tip" text="client" />

获取当前展示的条目的数量

#### Returns

| `number` | 当前展示的条目的数量 |
| :------ | :------ |

___

### getTouchCanControlThisScroll <Score text="getTouchCanControlThisScroll" /> 

• **getTouchCanControlThisScroll**(): `boolean` <Badge type="tip" text="client" />

获取是否受Touch事件影响滚动

#### Returns

| `boolean` | 能否touch能控制滚动 |
| :------ | :------ |

___

### insertItem <Score text="insertItem" /> 

• **insertItem**(`newItem`, `index`): `void` <Badge type="tip" text="client" />

插入项目节点数据，如果位置越界，则自动插入最后

#### Parameters

| `newItem` [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md) | 需要插入的新数据 |
| :------ | :------ |
| `index` `number` | 插入的位置 range: 无 type: 整形 |


___

### regenerateTreeData <Score text="regenerateTreeData" /> 

• **regenerateTreeData**(`regenItems`): `void` <Badge type="tip" text="client" />

重新生成树刷新数据

#### Parameters

| `regenItems` [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)[] | 刷新数据 |
| :------ | :------ |


___

### removeItem <Score text="removeItem" /> 

• **removeItem**(`delItem`): `void` <Badge type="tip" text="client" />

移除项目节点数据

#### Parameters

| `delItem` [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md) | 需要移除的数据 |
| :------ | :------ |


___

### requestRefresh <Score text="requestRefresh" /> 

• **requestRefresh**(): `void` <Badge type="tip" text="client" />

刷新数据


___

### resetListItems <Score text="resetListItems" /> 

• **resetListItems**(`newListItems`): `void` <Badge type="tip" text="client" />

重新设置项目节点数据组

#### Parameters

| `newListItems` [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)[] | 用于替换的新数据组 |
| :------ | :------ |


___

### scrollIntoView <Score text="scrollIntoView" /> 

• **scrollIntoView**(`targetItem`): `void` <Badge type="tip" text="client" />

滚动条定位到对应项目的位置

#### Parameters

| `targetItem` [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md) | 目标定位项目 |
| :------ | :------ |


___

### setItemExpansion <Score text="setItemExpansion" /> 

• **setItemExpansion**(`targetItem`, `expandItem`): `void` <Badge type="tip" text="client" />

设置节点的展开状态

#### Parameters

| `targetItem` [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md) | 目标数据 |
| :------ | :------ |
| `expandItem` `boolean` | 是否展开 |


___

### setSelectionItem <Score text="setSelectionItem" /> 

• **setSelectionItem**(`selectedItems`, `selected`, `selectInfo?`): `void` <Badge type="tip" text="client" />

设置节点选中

#### Parameters

| `selectedItems` [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)  [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md)[] | 需要修改选中的节点数据 |
| :------ | :------ |
| `selected` `boolean` | 确定修改目标：选中/不选中 range:[true, false] |
| `selectInfo?` [`SelectInfo`](../enums/mw.SelectInfo.md) | 选中方式：键盘/导航/鼠标/直接选中 default: SelectInfo.Direct |


___

### setTouchCanControlThisScroll <Score text="setTouchCanControlThisScroll" /> 

• **setTouchCanControlThisScroll**(`bCanControl`): `void` <Badge type="tip" text="client" />

设置是否受Touch事件影响滚动

#### Parameters

| `bCanControl` `boolean` | 能否touch控制滚动 |
| :------ | :------ |


___

### toggleItemExpansion <Score text="toggleItemExpansion" /> 

• **toggleItemExpansion**(`targetItem`): `void` <Badge type="tip" text="client" />

修改节点的展开状态

#### Parameters

| `targetItem` [`TreeViewItemDataBase`](mw.TreeViewItemDataBase.md) | 目标数据 |
| :------ | :------ |


___

### newObject <Score text="newObject" /> 

• `Static` **newObject**(`uiAssetGUID`, `parent?`, `inName?`): [`TreeView`](mw.TreeView.md) <Badge type="tip" text="client" />

创建 TreeView 控件，当parent和inName与已有的对象相同时，旧的对象会被销毁

#### Parameters

| `uiAssetGUID` `string` |  设置视图绑定的节点UI range: 无 |
| :------ | :------ |
| `parent?` [`Canvas`](mw.Canvas.md) | 创建控件的外parent对象 default:null |
| `inName?` `string` | 创建控件的名称 default:null range: 无 |

#### Returns

| [`TreeView`](mw.TreeView.md) | 创建的对象 |
| :------ | :------ |
