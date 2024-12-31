[界面](../groups/界面.界面.md) / TileView

# TileView <Badge type="tip" text="Class" /> <Score text="TileView" />

平铺视图

## Hierarchy

- [`ListView`](mw.ListView.md)

  ↳ **`TileView`**

## Table of contents

### Properties <Score text="Properties" /> 

### Accessors <Score text="Accessors" /> 
| **[itemHeight](mw.TileView.md#itemheight)**(`[itemHeight](mw.TileView.md#itemheight)`): `void` <Badge type="tip" text="client" />  |
| :-----|
| 设置子节点高度，对于TileView来说，必须有一个设定好的子节点高度，默认值为16|
| **[itemWidth](mw.TileView.md#itemwidth)**(`[itemWidth](mw.TileView.md#itemwidth)`): `void` <Badge type="tip" text="client" />  |
| 设置子节点宽度，对于TileView来说，必须有一个设定好的子节点宽度，默认值为16|


::: details click
### Accessors <Score text="Accessors" /> 
| **[clearSelectionOnClick](mw.ListView.md#clearselectiononclick)**(`clearSelection`: `boolean`): `void` <Badge type="tip" text="client" />  |
| :-----|
| 设置是否在点击空白后清除选中项（仅初始化时设置有效）|
| **[itemPadding](mw.ListView.md#itempadding)**(): [`Margin`](mw.Margin.md)  |
| 获取视图节点边距|
| **[listItems](mw.ListView.md#listitems)**(): [`ListViewItemDataBase`](mw.ListViewItemDataBase.md)[] <Badge type="tip" text="client" />  |
| 获取列表数据|
| **[onItemClicked](mw.ListView.md#onitemclicked)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`clickedItem`: [`ListViewItemDataBase`](mw.ListViewItemDataBase.md), `doubleClick`: `boolean`) => `void`\>  |
| 返回点击代理|
| **[onItemHoverChanged](mw.ListView.md#onitemhoverchanged)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`targetItem`: [`Widget`](mw.Widget.md), `hovered`: `boolean`) => `void`\>  |
| 返回悬停状态改变代理|
| **[onItemRefreshed](mw.ListView.md#onitemrefreshed)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`rowDatas`: [`ListViewItemDataBase`](mw.ListViewItemDataBase.md)[]) => `void`\> <Badge type="tip" text="client" />  |
| 返回UI刷新生成同步代理|
| **[onItemReleaseShow](mw.ListView.md#onitemreleaseshow)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`targetItem`: [`Widget`](mw.Widget.md)) => `void`\>  |
| 子控件移除显示时调用，等待复用前|
| **[onItemSelected](mw.ListView.md#onitemselected)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`selectedItem`: [`ListViewItemDataBase`](mw.ListViewItemDataBase.md), `selectType`: [`SelectInfo`](../enums/mw.SelectInfo.md)) => `void`\> <Badge type="tip" text="client" />  |
| 返回选择修改代理,取消选中/清空也会触发选中修改，返回参数selectedItem == null, 请注意判断|
| **[scrollBarStyle](mw.ListView.md#scrollbarstyle)**(): [`ScrollbarStyle`](mw.ScrollbarStyle.md) <Badge type="tip" text="other" />  |
| 滚动条样式|
| **[scrollBarVisible](mw.ListView.md#scrollbarvisible)**(): `boolean` <Badge type="tip" text="other" />  |
| 滚动条可见性|
| **[scrollOffset](mw.ListView.md#scrolloffset)**(): `number` <Badge type="tip" text="client" />  |
| 获取当前滚动条偏移位置|
| **[selectionMode](mw.ListView.md#selectionmode)**(): [`SelectionMode`](../enums/mw.SelectionMode.md) <Badge type="tip" text="client" />  |
| 获取选中模式|
| **[tableRowStyle](mw.ListView.md#tablerowstyle)**(): [`ListItemStyle`](mw.ListItemStyle.md) <Badge type="tip" text="other" />  |
| Item项目节点样式设置|
:::


### Methods <Score text="Methods" /> 


::: details click
### Methods <Score text="Methods" /> 
| **[addItems](mw.ListView.md#additems)**(`newListItems`: [`ListViewItemDataBase`](mw.ListViewItemDataBase.md)[]): `void` <Badge type="tip" text="client" />  |
| :-----|
| 添加项目节点数据|
| **[clearItems](mw.ListView.md#clearitems)**(): `void` <Badge type="tip" text="client" />  |
| 清理数据组|
| **[clearSelection](mw.ListView.md#clearselection)**(): `void` <Badge type="tip" text="client" />  |
| 清空列表的选中|
| **[findItemByIndex](mw.ListView.md#finditembyindex)**(`index`: `number`): [`ListViewItemDataBase`](mw.ListViewItemDataBase.md) <Badge type="tip" text="client" />  |
| 根据索引查找对应的项目节点数据，如果位置越界，则返回空|
| **[getSelectionIndexs](mw.ListView.md#getselectionindexs)**(): `number`[] <Badge type="tip" text="client" />  |
| 获取选中节点的索引|
| **[getSelectionItems](mw.ListView.md#getselectionitems)**(): [`ListViewItemDataBase`](mw.ListViewItemDataBase.md)[] <Badge type="tip" text="client" />  |
| 获取选中节点的数据|
| **[getTouchCanControlThisScroll](mw.ListView.md#gettouchcancontrolthisscroll)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取是否受Touch事件影响滚动|
| **[insertItem](mw.ListView.md#insertitem)**(`newItem`: [`ListViewItemDataBase`](mw.ListViewItemDataBase.md), `index`: `number`): `void` <Badge type="tip" text="client" />  |
| 插入项目节点数据，如果位置越界，则自动插入最后|
| **[removeItem](mw.ListView.md#removeitem)**(`delItem`: [`ListViewItemDataBase`](mw.ListViewItemDataBase.md)): `void` <Badge type="tip" text="client" />  |
| 移除项目节点数据|
| **[removeItemByIndex](mw.ListView.md#removeitembyindex)**(`delIndex`: `number`): `void` <Badge type="tip" text="client" />  |
| 根据索引移除项目节点数据，如果位置越界，则移除失败|
| **[requestRefresh](mw.ListView.md#requestrefresh)**(): `void` <Badge type="tip" text="client" />  |
| 刷新数据|
| **[resetListItems](mw.ListView.md#resetlistitems)**(`newListItems`: [`ListViewItemDataBase`](mw.ListViewItemDataBase.md)[]): `void` <Badge type="tip" text="client" />  |
| 重新设置项目节点数据组|
| **[scrollIntoView](mw.ListView.md#scrollintoview)**(`targetItem`: [`ListViewItemDataBase`](mw.ListViewItemDataBase.md)): `void` <Badge type="tip" text="client" />  |
| 滚动条定位到对应项目的位置|
| **[setSelectionItem](mw.ListView.md#setselectionitem)**(`selectedItems`: [`ListViewItemDataBase`](mw.ListViewItemDataBase.md)  [`ListViewItemDataBase`](mw.ListViewItemDataBase.md)[], `selected`: `boolean`, `selectInfo?`: [`SelectInfo`](../enums/mw.SelectInfo.md)): `void` <Badge type="tip" text="client" />  |
| 设置节点选中|
| **[setSelectionItemByIndex](mw.ListView.md#setselectionitembyindex)**(`selectedIndexs`: `number`  `number`[], `selected`: `boolean`, `selectInfo?`: [`SelectInfo`](../enums/mw.SelectInfo.md)): `void` <Badge type="tip" text="client" />  |
| 根据索引设置节点选中，如果位置越界，则越界对应的操作无效|
| **[setTouchCanControlThisScroll](mw.ListView.md#settouchcancontrolthisscroll)**(`bCanControl`: `boolean`): `void` <Badge type="tip" text="client" />  |
| 设置是否受Touch事件影响滚动|
| **[newObject](mw.ListView.md#newobject)**(`orientation`: [`Orientation`](../enums/mw.Orientation.md), `uiAssetGUID`: `string`, `parent?`: [`Canvas`](mw.Canvas.md), `inName?`: `string`): [`ListView`](mw.ListView.md) <Badge type="tip" text="client" />  |
| 创建 ListView 控件，当parent和inName与已有的对象相同时，旧的对象会被销毁|
:::


## Properties

## Accessors

___

### itemHeight <Score text="itemHeight" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `set` **itemHeight**(`itemHeight`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


设置子节点高度，对于TileView来说，必须有一个设定好的子节点高度，默认值为16

#### Parameters

| `itemHeight` `number` | 子节点高度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### itemWidth <Score text="itemWidth" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `set` **itemWidth**(`itemWidth`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


设置子节点宽度，对于TileView来说，必须有一个设定好的子节点宽度，默认值为16

#### Parameters

| `itemWidth` `number` | 子节点宽度 |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods
