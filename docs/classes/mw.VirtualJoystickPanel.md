[界面](../groups/界面.界面.md) / VirtualJoystickPanel

# VirtualJoystickPanel <Badge type="tip" text="Class" /> <Score text="VirtualJoystickPanel" />

摇杆

## Hierarchy

- [`Widget`](mw.Widget.md)

  ↳ **`VirtualJoystickPanel`**

## Table of contents

### Properties <Score text="Properties" /> 


::: details click
### Properties <Score text="Properties" /> 
| **[onCustomPropertyChange](mw.Widget.md#oncustompropertychange)**: `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> <Badge type="tip" text="client" />  |
| :-----|
| 监听自定义属性同步事件|
:::


### Accessors <Score text="Accessors" /> 
| **[activeOpacity](mw.VirtualJoystickPanel.md#activeopacity)**(): `number` <Badge type="tip" text="client" />  |
| :-----|
| 返回激活时的透明度|
| **[backgroundDisabledImageId](mw.VirtualJoystickPanel.md#backgrounddisabledimageid)**(): `string` <Badge type="tip" text="client" />  |
| 返回背景图片禁用状态图片id|
| **[backgroundImageDesigner](mw.VirtualJoystickPanel.md#backgroundimagedesigner)**(): [`JoystickStyleDesigner`](mw.JoystickStyleDesigner.md) <Badge type="tip" text="client" />  |
| 返回输入的背景贴图设置，包括 普通的 点击的  不启用的|
| **[backgroundImageId](mw.VirtualJoystickPanel.md#backgroundimageid)**(): `string` <Badge type="tip" text="client" />  |
| 返回中心图片普通状态图片id|
| **[backgroundImageSize](mw.VirtualJoystickPanel.md#backgroundimagesize)**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />  |
| 摇杆背景图片大小|
| **[backgroundTouchImageId](mw.VirtualJoystickPanel.md#backgroundtouchimageid)**(): `string` <Badge type="tip" text="client" />  |
| 返回背景图片按压状态图片id|
| **[center](mw.VirtualJoystickPanel.md#center)**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />  |
| 返回输入的是摇杆中心位置，  不符合预期会返回默认值|
| **[centerDisableImageId](mw.VirtualJoystickPanel.md#centerdisableimageid)**(): `string` <Badge type="tip" text="client" />  |
| 返回中心图片禁用状态图片id|
| **[centerImageDesigner](mw.VirtualJoystickPanel.md#centerimagedesigner)**(): [`JoystickStyleDesigner`](mw.JoystickStyleDesigner.md) <Badge type="tip" text="client" />  |
| 返回输入的中心贴图设置，包括 普通的 点击的  不启用的|
| **[centerImageId](mw.VirtualJoystickPanel.md#centerimageid)**(): `string` <Badge type="tip" text="client" />  |
| 返回中心图片普通状态图片id|
| **[centerImageSize](mw.VirtualJoystickPanel.md#centerimagesize)**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />  |
| 摇杆按钮图片大小|
| **[centerTouchImage](mw.VirtualJoystickPanel.md#centertouchimage)**(): `string` <Badge type="tip" text="client" />  |
| 返回中心图片按压状态图片id|
| **[controlByMouseEnable](mw.VirtualJoystickPanel.md#controlbymouseenable)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取是否被鼠标控制，只作用于PC端|
| **[controlType](mw.VirtualJoystickPanel.md#controltype)**(): [`CameraControlType`](../enums/mw.CameraControlType.md) <Badge type="tip" text="client" />  |
| 返回输入的是摇杆类型，  不符合预期会返回默认值|
| **[inActiveOpacity](mw.VirtualJoystickPanel.md#inactiveopacity)**(): `number` <Badge type="tip" text="client" />  |
| 返回未激活时的透明度|
| **[inputScale](mw.VirtualJoystickPanel.md#inputscale)**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />  |
| 返回输入的输入比例|
| **[isLocationFixed](mw.VirtualJoystickPanel.md#islocationfixed)**(): `boolean` <Badge type="tip" text="client" />  |
| 拖动后，是否固定摇杆位置|
| **[onInputDir](mw.VirtualJoystickPanel.md#oninputdir)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`vec`: [`Vector2`](mw.Vector2.md)) => `void`\> <Badge type="tip" text="client" />  |
| 输入移动事件|
| **[onJoyStickDown](mw.VirtualJoystickPanel.md#onjoystickdown)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />  |
| 摇杆按下事件的代理|
| **[onJoyStickUp](mw.VirtualJoystickPanel.md#onjoystickup)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />  |
| 摇杆抬起事件的代理|
| **[timeUntilInactive](mw.VirtualJoystickPanel.md#timeuntilinactive)**(): `number` <Badge type="tip" text="client" />  |
| 进入未激活状态的时间|
| **[timeUntilReset](mw.VirtualJoystickPanel.md#timeuntilreset)**(): `number` <Badge type="tip" text="client" />  |
| 释放摇杆后的复位时间|


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
| **[addKey](mw.VirtualJoystickPanel.md#addkey)**(`key`: [`JoystickBindKeyType`](mw.JoystickBindKeyType.md)): `void` <Badge type="tip" text="client" />  |
| :-----|
| 同一按键同时只能操控一个UI控件，最新绑定的UI控件会覆盖之前的绑定；脚本中添加的绑定无法覆盖编辑器按键绑定菜单中绑定相同按键的UI控件，但当两个UI控件分别通过代码和菜单绑定到同一按键时，使用代码绑定的优先级更高|
| **[getKeys](mw.VirtualJoystickPanel.md#getkeys)**(): [`JoystickBindKeyType`](mw.JoystickBindKeyType.md)[] <Badge type="tip" text="client" />  |
| 获取当前UI控件绑定的所有键盘按键，包括编辑器按键绑定菜单和用代码绑定的按键|
| **[removeKey](mw.VirtualJoystickPanel.md#removekey)**(`key`: [`JoystickBindKeyType`](mw.JoystickBindKeyType.md)): `void` <Badge type="tip" text="client" />  |
| 此操作只会解绑动态绑定的按键无法解除编辑器按键绑定菜单中绑定的按键|
| **[resetJoyStick](mw.VirtualJoystickPanel.md#resetjoystick)**(): `void` <Badge type="tip" text="client" />  |
| 强制重置摇杆 - 例如在操控摇杆的时候隐藏其父类节点,这时候摇杆重新显示后无法成功重置|
| **[setVisibility](mw.VirtualJoystickPanel.md#setvisibility)**(`Visibility`: [`SlateVisibility`](../enums/mw.SlateVisibility.md)): `void` <Badge type="tip" text="client" />  |
| 设置可见性|
| **[newObject](mw.VirtualJoystickPanel.md#newobject)**(`Outer?`: [`Widget`](mw.Widget.md), `InName?`: `string`): [`VirtualJoystickPanel`](mw.VirtualJoystickPanel.md) <Badge type="tip" text="client" />  |
| 创建 VirtualJoystickPanelDesigner 控件|
| **[newObjectAndAdd](mw.VirtualJoystickPanel.md#newobjectandadd)**(`InCanvas?`: [`Canvas`](mw.Canvas.md), `Outer?`: [`Widget`](mw.Widget.md), `InName?`: `string`): [`VirtualJoystickPanel`](mw.VirtualJoystickPanel.md) <Badge type="tip" text="client" />  |
| 创建 TouchPad 控件|


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

### activeOpacity <Score text="activeOpacity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **activeOpacity**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **activeOpacity**(`Value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


返回激活时的透明度

#### Returns

| `number` | 返回激活时的透明度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置激活时的透明度

#### Parameters

| `Value` `number` | 透明度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### backgroundDisabledImageId <Score text="backgroundDisabledImageId" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **backgroundDisabledImageId**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **backgroundDisabledImageId**(`id`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


返回背景图片禁用状态图片id

#### Returns

| `string` | 返回背景图片禁用状态图片id |
| :------ | :------ |


</td>
<td style="text-align: left">


设置背景图片禁用状态图片id

#### Parameters

| `id` `string` | 资源id |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### backgroundImageDesigner <Score text="backgroundImageDesigner" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **backgroundImageDesigner**(): [`JoystickStyleDesigner`](mw.JoystickStyleDesigner.md) <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


返回输入的背景贴图设置，包括 普通的 点击的  不启用的

#### Returns

| [`JoystickStyleDesigner`](mw.JoystickStyleDesigner.md) | 返回输入的背景贴图设置，包括 普通的 点击的  不启用的 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### backgroundImageId <Score text="backgroundImageId" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **backgroundImageId**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **backgroundImageId**(`id`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


返回中心图片普通状态图片id

#### Returns

| `string` | 返回中心图片普通状态图片id |
| :------ | :------ |


</td>
<td style="text-align: left">


设置背景图片普通状态图片id

#### Parameters

| `id` `string` | 资源id |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### backgroundImageSize <Score text="backgroundImageSize" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **backgroundImageSize**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **backgroundImageSize**(`inSize`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


摇杆背景图片大小

#### Returns

| [`Vector2`](mw.Vector2.md) | 摇杆背景图片大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


摇杆背景图片大小

#### Parameters

| `inSize` [`Vector2`](mw.Vector2.md) | 摇杆背景图片大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### backgroundTouchImageId <Score text="backgroundTouchImageId" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **backgroundTouchImageId**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **backgroundTouchImageId**(`id`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


返回背景图片按压状态图片id

#### Returns

| `string` | 返回背景图片按压状态图片id |
| :------ | :------ |


</td>
<td style="text-align: left">


设置背景图片按压状态图片id

#### Parameters

| `id` `string` | 资源id |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### center <Score text="center" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **center**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **center**(`inValue`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


返回输入的是摇杆中心位置，  不符合预期会返回默认值

#### Returns

| [`Vector2`](mw.Vector2.md) | 回输入的是摇杆中心位置，  不符合预期会返回默认值 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置输入的中心位置

#### Parameters

| `inValue` [`Vector2`](mw.Vector2.md) | 新的中心位置 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### centerDisableImageId <Score text="centerDisableImageId" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **centerDisableImageId**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **centerDisableImageId**(`id`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


返回中心图片禁用状态图片id

#### Returns

| `string` | 返回中心图片禁用状态图片id |
| :------ | :------ |


</td>
<td style="text-align: left">


设置中心图片禁用状态图片id

#### Parameters

| `id` `string` | 资源id |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### centerImageDesigner <Score text="centerImageDesigner" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **centerImageDesigner**(): [`JoystickStyleDesigner`](mw.JoystickStyleDesigner.md) <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


返回输入的中心贴图设置，包括 普通的 点击的  不启用的

#### Returns

| [`JoystickStyleDesigner`](mw.JoystickStyleDesigner.md) | 返回中心贴图设置 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### centerImageId <Score text="centerImageId" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **centerImageId**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **centerImageId**(`id`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


返回中心图片普通状态图片id

#### Returns

| `string` | 返回中心图片普通状态图片id |
| :------ | :------ |


</td>
<td style="text-align: left">


设置中心图片普通状态图片id

#### Parameters

| `id` `string` | 资源id |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### centerImageSize <Score text="centerImageSize" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **centerImageSize**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **centerImageSize**(`inSize`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


摇杆按钮图片大小

#### Returns

| [`Vector2`](mw.Vector2.md) | 摇杆按钮图片大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


摇杆按钮图片大小

#### Parameters

| `inSize` [`Vector2`](mw.Vector2.md) | 摇杆按钮图片大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### centerTouchImage <Score text="centerTouchImage" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **centerTouchImage**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **centerTouchImage**(`id`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


返回中心图片按压状态图片id

#### Returns

| `string` | 返回中心图片按压状态图片id |
| :------ | :------ |


</td>
<td style="text-align: left">


置中心图片按压状态图片id

#### Parameters

| `id` `string` | 资源id |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### controlByMouseEnable <Score text="controlByMouseEnable" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **controlByMouseEnable**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **controlByMouseEnable**(`controlByMouse`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否被鼠标控制，只作用于PC端

#### Returns

| `boolean` | 是否被鼠标控制 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否被鼠标控制，只作用于PC端

#### Parameters

| `controlByMouse` `boolean` |  是否被鼠标控制 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### controlType <Score text="controlType" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **controlType**(): [`CameraControlType`](../enums/mw.CameraControlType.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **controlType**(`NewControlType`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


返回输入的是摇杆类型，  不符合预期会返回默认值

#### Returns

| [`CameraControlType`](../enums/mw.CameraControlType.md) | 返回输入的摇杆类型 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置输入的摇杆类型，人物的移动和技能摇杆的移动类型

#### Parameters

| `NewControlType` [`CameraControlType`](../enums/mw.CameraControlType.md) | 摇杆类型 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### inActiveOpacity <Score text="inActiveOpacity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **inActiveOpacity**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **inActiveOpacity**(`Value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


返回未激活时的透明度

#### Returns

| `number` | 返回未激活时的透明度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置未激活时的透明度

#### Parameters

| `Value` `number` | 透明度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### inputScale <Score text="inputScale" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **inputScale**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **inputScale**(`inScale`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


返回输入的输入比例

#### Returns

| [`Vector2`](mw.Vector2.md) | 返回输入的输入比例 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置输入的输入比例

#### Parameters

| `inScale` [`Vector2`](mw.Vector2.md) | 新的输入比例 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### isLocationFixed <Score text="isLocationFixed" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **isLocationFixed**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **isLocationFixed**(`enable`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


拖动后，是否固定摇杆位置

#### Returns

| `boolean` | boolean |
| :------ | :------ |


</td>
<td style="text-align: left">


拖动后，是否固定摇杆位置

#### Parameters

| `enable` `boolean` | 是否固定摇杆位置 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### onInputDir <Score text="onInputDir" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onInputDir**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`vec`: [`Vector2`](mw.Vector2.md)) => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


输入移动事件

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<(`vec`: [`Vector2`](mw.Vector2.md)) => `void`\> | 输入移动事件 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onJoyStickDown <Score text="onJoyStickDown" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onJoyStickDown**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


摇杆按下事件的代理

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> | 按下摇杆事件的代理 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onJoyStickUp <Score text="onJoyStickUp" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onJoyStickUp**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


摇杆抬起事件的代理

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> | 抬起摇杆事件的代理 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### timeUntilInactive <Score text="timeUntilInactive" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **timeUntilInactive**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **timeUntilInactive**(`Value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


进入未激活状态的时间

#### Returns

| `number` | 进入未激活状态的时间，以秒为单位 |
| :------ | :------ |


</td>
<td style="text-align: left">


进入未激活状态的时间

#### Parameters

| `Value` `number` | 进入未激活状态的时间，以秒为单位 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### timeUntilReset <Score text="timeUntilReset" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **timeUntilReset**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **timeUntilReset**(`Value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


释放摇杆后的复位时间

#### Returns

| `number` | 复位时间  以秒为单位 |
| :------ | :------ |


</td>
<td style="text-align: left">


释放摇杆后的复位时间

#### Parameters

| `Value` `number` | 复位时间 以秒为单位 |
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

| `key` [`JoystickBindKeyType`](mw.JoystickBindKeyType.md) | 按键 |
| :------ | :------ |


___

### getKeys <Score text="getKeys" /> 

• **getKeys**(): [`JoystickBindKeyType`](mw.JoystickBindKeyType.md)[] <Badge type="tip" text="client" />

获取当前UI控件绑定的所有键盘按键，包括编辑器按键绑定菜单和用代码绑定的按键

#### Returns

| [`JoystickBindKeyType`](mw.JoystickBindKeyType.md)[] | 返回当前控件绑定的按键,可能为空 |
| :------ | :------ |

___

### removeKey <Score text="removeKey" /> 

• **removeKey**(`key`): `void` <Badge type="tip" text="client" />

此操作只会解绑动态绑定的按键无法解除编辑器按键绑定菜单中绑定的按键

#### Parameters

| `key` [`JoystickBindKeyType`](mw.JoystickBindKeyType.md) | 按键 |
| :------ | :------ |


___

### resetJoyStick <Score text="resetJoyStick" /> 

• **resetJoyStick**(): `void` <Badge type="tip" text="client" />

强制重置摇杆 - 例如在操控摇杆的时候隐藏其父类节点,这时候摇杆重新显示后无法成功重置


___

### setVisibility <Score text="setVisibility" /> 

• **setVisibility**(`Visibility`): `void` <Badge type="tip" text="client" />

设置可见性

#### Parameters

| `Visibility` [`SlateVisibility`](../enums/mw.SlateVisibility.md) | 可见性 |
| :------ | :------ |


___

### newObject <Score text="newObject" /> 

• `Static` **newObject**(`Outer?`, `InName?`): [`VirtualJoystickPanel`](mw.VirtualJoystickPanel.md) <Badge type="tip" text="client" />

创建 VirtualJoystickPanelDesigner 控件

#### Parameters

| `Outer?` [`Widget`](mw.Widget.md) | 创建控件的外 Outer 对象 default:null |
| :------ | :------ |
| `InName?` `string` | 创建控件的名称 default:null range:设置合理的名称即可 |

#### Returns

| [`VirtualJoystickPanel`](mw.VirtualJoystickPanel.md) | 返回创建的控件 |
| :------ | :------ |

___

### newObjectAndAdd <Score text="newObjectAndAdd" /> 

• `Static` **newObjectAndAdd**(`InCanvas?`, `Outer?`, `InName?`): [`VirtualJoystickPanel`](mw.VirtualJoystickPanel.md) <Badge type="tip" text="client" />

创建 TouchPad 控件

#### Parameters

| `InCanvas?` [`Canvas`](mw.Canvas.md) | 父节点 default:null |
| :------ | :------ |
| `Outer?` [`Widget`](mw.Widget.md) | 创建控件的外 Outer 对象 default:null |
| `InName?` `string` |  创建控件的名称 default: null range:设置合理的名称即可 |

#### Returns

| [`VirtualJoystickPanel`](mw.VirtualJoystickPanel.md) | 返回创建的对象 |
| :------ | :------ |

当 Outer 和 InName 与已有的对象相同时，旧的对象会被销毁
