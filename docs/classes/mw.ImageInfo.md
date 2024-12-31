[界面](../groups/界面.界面.md) / ImageInfo

# ImageInfo <Badge type="tip" text="Class" /> <Score text="ImageInfo" />

图片信息类

## Table of contents

### Accessors <Score text="Accessors" /> 
| **[assetICON](mw.ImageInfo.md#asseticon)**(): [`AssetIconData`](mw.AssetIconData.md) <Badge type="tip" text="client" />  |
| :-----|
| 获取ImageInfo的图标数据|
| **[color](mw.ImageInfo.md#color)**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />  |
| 获取ImageInfo的颜色|
| **[drawType](mw.ImageInfo.md#drawtype)**(): [`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md) <Badge type="tip" text="client" />  |
| 获取ImageInfo的绘制类型|
| **[id](mw.ImageInfo.md#id)**(): `string` <Badge type="tip" text="client" />  |
| 获取ImageInfo的id|
| **[margin](mw.ImageInfo.md#margin)**(): `Readonly`<[`Margin`](mw.Margin.md)\> <Badge type="tip" text="client" />  |
| 获取ImageInfo的margin|
| **[size](mw.ImageInfo.md#size)**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />  |
| 获取ImageInfo的size大小|

### Methods <Score text="Methods" /> 
| **[asyncSetByID](mw.ImageInfo.md#asyncsetbyid)**(`id`: `string`, `bUseSRGB?`: `boolean`): `Promise`<`boolean`\> <Badge type="tip" text="client" />  |
| :-----|
| 通过 Id 设置图片信息|
| **[setByAssetIcon](mw.ImageInfo.md#setbyasseticon)**(`assetId`: `string`, `size`: [`AssetIconSize`](../enums/mw.AssetIconSize.md), `bUseSRGB?`: `boolean`): `Promise`<`boolean`\> <Badge type="tip" text="client" />  |
| 用指定的 id 和分辨率，设置图标|

## Accessors

### assetICON <Score text="assetICON" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **assetICON**(): [`AssetIconData`](mw.AssetIconData.md) <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取ImageInfo的图标数据

#### Returns

| [`AssetIconData`](mw.AssetIconData.md) | 图标数据结构 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### color <Score text="color" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **color**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **color**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取ImageInfo的颜色

#### Returns

| `Readonly`<[`LinearColor`](mw.LinearColor.md)\> | 返回Type.LinearColor颜色值 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置ImageInfo的颜色

#### Parameters

| `value` `Readonly`<[`LinearColor`](mw.LinearColor.md)\> | mw.LinearColor颜色值 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### drawType <Score text="drawType" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **drawType**(): [`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **drawType**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取ImageInfo的绘制类型

#### Returns

| [`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md) | 绘制类型 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置ImageInfo的绘制类型

#### Parameters

| `value` [`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md) | 绘制类型 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### id <Score text="id" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **id**(): `string` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取ImageInfo的id

#### Returns

| `string` | ImageInfo的id |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### margin <Score text="margin" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **margin**(): `Readonly`<[`Margin`](mw.Margin.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **margin**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取ImageInfo的margin

#### Returns

| `Readonly`<[`Margin`](mw.Margin.md)\> | margin |
| :------ | :------ |


</td>
<td style="text-align: left">


设置ImageInfo的margin

#### Parameters

| `value` `Readonly`<[`Margin`](mw.Margin.md)\> | 指定的margin |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### size <Score text="size" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **size**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **size**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取ImageInfo的size大小

#### Returns

| `Readonly`<[`Vector2`](mw.Vector2.md)\> | ImageInfo的size |
| :------ | :------ |


</td>
<td style="text-align: left">


设置ImageInfo的size大小

#### Parameters

| `value` `Readonly`<[`Vector2`](mw.Vector2.md)\> | 指定的size |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods

___

### asyncSetByID <Score text="asyncSetByID" /> 

• **asyncSetByID**(`id`, `bUseSRGB?`): `Promise`<`boolean`\> <Badge type="tip" text="client" />

通过 Id 设置图片信息

#### Parameters

| `id` `string` | 图片Id <br> range: 依据 ID 长度而定 |
| :------ | :------ |
| `bUseSRGB?` `boolean` | 是否贴图使用SRGB模式 default: true range: [true, false] |

#### Returns

| `Promise`<`boolean`\> | 是否设置成功 |
| :------ | :------ |

___

### setByAssetIcon <Score text="setByAssetIcon" /> 

• **setByAssetIcon**(`assetId`, `size`, `bUseSRGB?`): `Promise`<`boolean`\> <Badge type="tip" text="client" />

用指定的 id 和分辨率，设置图标

#### Parameters

| `assetId` `string` |  传入图标的资源 id range: 无 |
| :------ | :------ |
| `size` [`AssetIconSize`](../enums/mw.AssetIconSize.md) |  传入图标的分辨率枚举 |
| `bUseSRGB?` `boolean` |  是否使用SRGB default: true range: [true, false] |

#### Returns

| `Promise`<`boolean`\> | 设置的结果 |
| :------ | :------ |
