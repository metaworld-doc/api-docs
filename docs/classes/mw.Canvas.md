[界面](../groups/界面.界面.md) / Canvas

# Canvas <Badge type="tip" text="Class" /> <Score text="Canvas" />

容器

----------------------

可挂载叶子节点的根节点，以及提供各种自动布局功能

## Hierarchy

- [`PanelWidget`](Core.mw.PanelWidget.md)

  ↳ **`Canvas`**

## Table of contents

### Properties <Score text="Properties" /> 

### Accessors <Score text="Accessors" /> 
| **[autoLayoutContainerRule](mw.Canvas.md#autolayoutcontainerrule)**(): [`UILayoutType`](../enums/mw.UILayoutType.md) <Badge type="tip" text="client" />  |
| :-----|
| 获取自动布局排版规则-容器类型|
| **[autoLayoutEnable](mw.Canvas.md#autolayoutenable)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取是否时自动布局|
| **[autoLayoutPacketRule](mw.Canvas.md#autolayoutpacketrule)**(): [`UILayoutPacket`](../enums/mw.UILayoutPacket.md) <Badge type="tip" text="client" />  |
| 获取自动布局排版规则-排列规则|
| **[autoLayoutPadding](mw.Canvas.md#autolayoutpadding)**(): [`Margin`](mw.Margin.md) <Badge type="tip" text="client" />  |
| 获取边缘间距|
| **[autoLayoutRule](mw.Canvas.md#autolayoutrule)**(): [`UILayout`](mw.UILayout.md) <Badge type="tip" text="client" />  |
| 获取完整的布局规则|
| **[autoLayoutSpacing](mw.Canvas.md#autolayoutspacing)**(): `number` <Badge type="tip" text="client" />  |
| 获取自动布局间隔|
| **[clipEnable](mw.Canvas.md#clipenable)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取是否裁剪|
| **[focusable](mw.Canvas.md#focusable)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取是否获取输入焦点|

### Methods <Score text="Methods" /> 
| **[newObject](mw.Canvas.md#newobject)**(`parent?`: [`Canvas`](mw.Canvas.md), `inName?`: `string`): [`Canvas`](mw.Canvas.md) <Badge type="tip" text="client" />  |
| :-----|
| 创建Canvas控件|

## Properties

## Accessors

___

### autoLayoutContainerRule <Score text="autoLayoutContainerRule" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **autoLayoutContainerRule**(): [`UILayoutType`](../enums/mw.UILayoutType.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **autoLayoutContainerRule**(`inRule`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取自动布局排版规则-容器类型

#### Returns

| [`UILayoutType`](../enums/mw.UILayoutType.md) | 自动布局排版规则-容器类型 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置自动布局排版规则-容器类型

#### Parameters

| `inRule` [`UILayoutType`](../enums/mw.UILayoutType.md) | 自动布局排版规则-容器类型 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### autoLayoutEnable <Score text="autoLayoutEnable" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **autoLayoutEnable**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **autoLayoutEnable**(`inAutoLayout`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否时自动布局

#### Returns

| `boolean` | 是否自动布局 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否自动布局

#### Parameters

| `inAutoLayout` `boolean` | 是否自动布局 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### autoLayoutPacketRule <Score text="autoLayoutPacketRule" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **autoLayoutPacketRule**(): [`UILayoutPacket`](../enums/mw.UILayoutPacket.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **autoLayoutPacketRule**(`inRule`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取自动布局排版规则-排列规则

#### Returns

| [`UILayoutPacket`](../enums/mw.UILayoutPacket.md) | 自动布局排版规则-排列规则 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置自动布局排版规则-排列规则

#### Parameters

| `inRule` [`UILayoutPacket`](../enums/mw.UILayoutPacket.md) | 自动布局排版规则-排列规则 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### autoLayoutPadding <Score text="autoLayoutPadding" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **autoLayoutPadding**(): [`Margin`](mw.Margin.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **autoLayoutPadding**(`inPadding`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取边缘间距

#### Returns

| [`Margin`](mw.Margin.md) | 获取填充 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置边缘间距

#### Parameters

| `inPadding` [`Margin`](mw.Margin.md) | 填充 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### autoLayoutRule <Score text="autoLayoutRule" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **autoLayoutRule**(): [`UILayout`](mw.UILayout.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **autoLayoutRule**(`layout`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取完整的布局规则

#### Returns

| [`UILayout`](mw.UILayout.md) | 布局规则 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置完整的布局规则

#### Parameters

| `layout` [`UILayout`](mw.UILayout.md) | 布局规则 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### autoLayoutSpacing <Score text="autoLayoutSpacing" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **autoLayoutSpacing**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **autoLayoutSpacing**(`inSpaceInItem`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取自动布局间隔

#### Returns

| `number` | 自动布局间隔 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置自动布局间隔

#### Parameters

| `inSpaceInItem` `number` | 自动布局间隔 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### clipEnable <Score text="clipEnable" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **clipEnable**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **clipEnable**(`clip`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否裁剪

#### Returns

| `boolean` | 是否裁剪 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否裁剪

#### Parameters

| `clip` `boolean` | 是否裁剪 |
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



## Methods

___

### newObject <Score text="newObject" /> 

• `Static` **newObject**(`parent?`, `inName?`): [`Canvas`](mw.Canvas.md) <Badge type="tip" text="client" />

创建Canvas控件

#### Parameters

| `parent?` [`Canvas`](mw.Canvas.md) | 创建控件的外parent对象 default:null |
| :------ | :------ |
| `inName?` `string` | 创建控件的名称 default:null range:设置合理的名称即可 |

#### Returns

| [`Canvas`](mw.Canvas.md) | 返回创建的对象 |
| :------ | :------ |

当parent和inName与已有的对象相同时，旧的对象会被销毁
