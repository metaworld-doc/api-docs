[界面](../groups/界面.界面.md) / ColorPick

# ColorPick <Badge type="tip" text="Class" /> <Score text="ColorPick" />

调色板

## Hierarchy

- [`Widget`](mw.Widget.md)

  ↳ **`ColorPick`**

## Table of contents

### Properties <Score text="Properties" /> 


::: details click
### Properties <Score text="Properties" /> 
| **[onCustomPropertyChange](mw.Widget.md#oncustompropertychange)**: `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> <Badge type="tip" text="client" />  |
| :-----|
| 监听自定义属性同步事件|
:::


### Accessors <Score text="Accessors" /> 
| **[color](mw.ColorPick.md#color)**(`inColor`: [`LinearColor`](mw.LinearColor.md)): `void` <Badge type="tip" text="client" />  |
| :-----|
| 设置color picker的颜色|
| **[imageGuid](mw.ColorPick.md#imageguid)**(`inGuid`: `string`): `void` <Badge type="tip" text="client" />  |
| 设置color picker 的图片|
| **[onColorChangeFinished](mw.ColorPick.md#oncolorchangefinished)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`Content`: [`LinearColor`](mw.LinearColor.md)) => `void`\> <Badge type="tip" text="client" />  |
| 颜色改变完成时触发的函数代理|
| **[onColorChanged](mw.ColorPick.md#oncolorchanged)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`Content`: [`LinearColor`](mw.LinearColor.md)) => `void`\> <Badge type="tip" text="client" />  |
| 颜色改变时触发的代理|
| **[onTouchFinished](mw.ColorPick.md#ontouchfinished)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`Content`: [`LinearColor`](mw.LinearColor.md)) => `void`\> <Badge type="tip" text="client" />  |
| 点击完成时触发的代理函数|
| **[onTouchStart](mw.ColorPick.md#ontouchstart)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`Content`: [`LinearColor`](mw.LinearColor.md)) => `void`\> <Badge type="tip" text="client" />  |
| 点击时触发的代理|


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
| **[newObject](mw.ColorPick.md#newobject)**(`parent?`: [`Canvas`](mw.Canvas.md), `inName?`: `string`): [`ColorPick`](mw.ColorPick.md) <Badge type="tip" text="client" />  |
| :-----|
| 创建 ColorPick 控件|


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

### color <Score text="color" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `set` **color**(`inColor`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


设置color picker的颜色

#### Parameters

| `inColor` [`LinearColor`](mw.LinearColor.md) | 输入的颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### imageGuid <Score text="imageGuid" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `set` **imageGuid**(`inGuid`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


设置color picker 的图片

#### Parameters

| `inGuid` | `string` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### onColorChangeFinished <Score text="onColorChangeFinished" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onColorChangeFinished**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`Content`: [`LinearColor`](mw.LinearColor.md)) => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


颜色改变完成时触发的函数代理

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<(`Content`: [`LinearColor`](mw.LinearColor.md)) => `void`\> | 返回事件的代理 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onColorChanged <Score text="onColorChanged" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onColorChanged**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`Content`: [`LinearColor`](mw.LinearColor.md)) => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


颜色改变时触发的代理

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<(`Content`: [`LinearColor`](mw.LinearColor.md)) => `void`\> | 返回事件的代理 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onTouchFinished <Score text="onTouchFinished" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onTouchFinished**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`Content`: [`LinearColor`](mw.LinearColor.md)) => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


点击完成时触发的代理函数

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<(`Content`: [`LinearColor`](mw.LinearColor.md)) => `void`\> | 返回事件的代理 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onTouchStart <Score text="onTouchStart" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onTouchStart**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`Content`: [`LinearColor`](mw.LinearColor.md)) => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


点击时触发的代理

#### Returns

</td>
</tr></tbody>
</table>

| [`MulticastDelegate`](mw.MulticastDelegate.md)<(`Content`: [`LinearColor`](mw.LinearColor.md)) => `void`\> | 返回事件的代理 |
| :------ | :------ |

## Methods

___

### newObject <Score text="newObject" /> 

• `Static` **newObject**(`parent?`, `inName?`): [`ColorPick`](mw.ColorPick.md) <Badge type="tip" text="client" />

创建 ColorPick 控件

#### Parameters

| `parent?` [`Canvas`](mw.Canvas.md) | 创建控件的parent对象 default:null |
| :------ | :------ |
| `inName?` `string` | 创建控件的名称 default:null range:设置合理的名称即可 |

#### Returns

| [`ColorPick`](mw.ColorPick.md) | 返回创建的对象 |
| :------ | :------ |

当parent和inName与已有的对象相同时，旧的对象会被销毁
