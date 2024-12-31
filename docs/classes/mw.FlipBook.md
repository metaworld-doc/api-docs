[界面](../groups/界面.界面.md) / FlipBook

# FlipBook <Badge type="tip" text="Class" /> <Score text="FlipBook" />

帧动画控件

## Hierarchy

- [`Widget`](mw.Widget.md)

  ↳ **`FlipBook`**

## Table of contents

### Properties <Score text="Properties" /> 


::: details click
### Properties <Score text="Properties" /> 
| **[onCustomPropertyChange](mw.Widget.md#oncustompropertychange)**: `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> <Badge type="tip" text="client" />  |
| :-----|
| 监听自定义属性同步事件|
:::


### Accessors <Score text="Accessors" /> 
| **[columns](mw.FlipBook.md#columns)**(): `number` <Badge type="tip" text="client" />  |
| :-----|
| 帧图片有效分割列数 >=1|
| **[currentFrameIndex](mw.FlipBook.md#currentframeindex)**(): `number` <Badge type="tip" text="client" />  |
| 帧动画当前播放到第几帧|
| **[framesPerSecond](mw.FlipBook.md#framespersecond)**(): `number` <Badge type="tip" text="client" />  |
| 帧动画每秒播放多少张帧图片 >0|
| **[imageInfo](mw.FlipBook.md#imageinfo)**(): [`ImageInfo`](mw.ImageInfo.md) <Badge type="tip" text="client" />  |
| 图片资源信息|
| **[isLoop](mw.FlipBook.md#isloop)**(): `boolean` <Badge type="tip" text="client" />  |
| 帧动画是否循环播放|
| **[onFinish](mw.FlipBook.md#onfinish)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />  |
| 帧动画完整播放完回调，触发条件，播放到最后一帧，并且播放状态是Playing|
| **[rows](mw.FlipBook.md#rows)**(): `number` <Badge type="tip" text="client" />  |
| 帧图片有效分割行数 >=1|
| **[status](mw.FlipBook.md#status)**(): [`PlayStatus`](../enums/mw.PlayStatus.md) <Badge type="tip" text="client" />  |
| 帧动画播放状态|
| **[totalFrames](mw.FlipBook.md#totalframes)**(): `number` <Badge type="tip" text="client" />  |
| 帧图片最大分割的有效播放帧数,大于0并且小于（行数X列数）|


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
| **[pause](mw.FlipBook.md#pause)**(): `void` <Badge type="tip" text="client" />  |
| :-----|
| 帧动画播放暂停|
| **[play](mw.FlipBook.md#play)**(): `void` <Badge type="tip" text="client" />  |
| 帧动画播放|
| **[resume](mw.FlipBook.md#resume)**(): `void` <Badge type="tip" text="client" />  |
| 帧动画播放恢复暂停，继续播放|
| **[stop](mw.FlipBook.md#stop)**(): `void` <Badge type="tip" text="client" />  |
| 帧动画播放停止|
| **[newObject](mw.FlipBook.md#newobject)**(`parent?`: [`Canvas`](mw.Canvas.md), `inName?`: `string`): [`FlipBook`](mw.FlipBook.md) <Badge type="tip" text="client" />  |
| 创建 FlipBook 控件|


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

### columns <Score text="columns" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **columns**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **columns**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


帧图片有效分割列数 >=1

#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


帧图片有效分割列数 >=1

#### Parameters

| `value` | `number` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### currentFrameIndex <Score text="currentFrameIndex" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **currentFrameIndex**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **currentFrameIndex**(`index`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


帧动画当前播放到第几帧

#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


设置帧动画当前播放到第几帧,小于最大有效帧图片数

#### Parameters

| `index` | `number` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### framesPerSecond <Score text="framesPerSecond" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **framesPerSecond**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **framesPerSecond**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


帧动画每秒播放多少张帧图片 >0

#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


帧动画每秒播放多少张帧图片 > 0

#### Parameters

| `value` | `number` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### imageInfo <Score text="imageInfo" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **imageInfo**(): [`ImageInfo`](mw.ImageInfo.md) <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


图片资源信息

#### Returns

| [`ImageInfo`](mw.ImageInfo.md) |  |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### isLoop <Score text="isLoop" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **isLoop**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **isLoop**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


帧动画是否循环播放

#### Returns

| `boolean` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


帧动画是否循环播放

#### Parameters

| `value` | `boolean` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### onFinish <Score text="onFinish" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onFinish**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


帧动画完整播放完回调，触发条件，播放到最后一帧，并且播放状态是Playing

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> |  |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### rows <Score text="rows" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **rows**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **rows**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


帧图片有效分割行数 >=1

#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


帧图片有效分割行数 >=1

#### Parameters

| `value` | `number` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### status <Score text="status" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **status**(): [`PlayStatus`](../enums/mw.PlayStatus.md) <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


帧动画播放状态

#### Returns

| [`PlayStatus`](../enums/mw.PlayStatus.md) |  |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### totalFrames <Score text="totalFrames" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **totalFrames**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **totalFrames**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


帧图片最大分割的有效播放帧数,大于0并且小于（行数X列数）

#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


帧图片最大分割的有效播放帧数,大于0并且小于（行数X列数）

#### Parameters

| `value` | `number` |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods

___

### pause <Score text="pause" /> 

• **pause**(): `void` <Badge type="tip" text="client" />

帧动画播放暂停


___

### play <Score text="play" /> 

• **play**(): `void` <Badge type="tip" text="client" />

帧动画播放


___

### resume <Score text="resume" /> 

• **resume**(): `void` <Badge type="tip" text="client" />

帧动画播放恢复暂停，继续播放


___

### stop <Score text="stop" /> 

• **stop**(): `void` <Badge type="tip" text="client" />

帧动画播放停止


___

### newObject <Score text="newObject" /> 

• `Static` **newObject**(`parent?`, `inName?`): [`FlipBook`](mw.FlipBook.md) <Badge type="tip" text="client" />

创建 FlipBook 控件

#### Parameters

| `parent?` [`Canvas`](mw.Canvas.md) | 创建控件的外parent对象 default:null |
| :------ | :------ |
| `inName?` `string` | 创建控件的名称 default:null range:无 |

#### Returns

| [`FlipBook`](mw.FlipBook.md) | 返回创建的对象 |
| :------ | :------ |

当parent和inName与已有的对象相同时，旧的对象会被销毁
