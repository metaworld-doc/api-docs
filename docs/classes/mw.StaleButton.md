[界面](../groups/界面.界面.md) / StaleButton

# StaleButton <Badge type="tip" text="Class" /> <Score text="StaleButton" />

文本按钮

<span style="font-size: 14px;">
使用示例:创建一个名为"NewScript"的脚本，放置在对象管理器对象子级中，打开脚本，输入以下代码保存，运行游戏，屏幕显示一个按钮。
</span>

```ts
@Component
export default class NewScript extends Script {

    protected onStart(): void {
        if(SystemUtil.isClient()){
            if(SystemUtil.isClient()){
                let mainui = UIService.create(UI_Main);
                UIService.showUI(mainui);
                UIService.canvas.addChild(mainui.button);
            }
        }
    }
}
class UI_Main extends UIScript {

    button: StaleButton = undefined;

    public onAwake() {
        let size = WindowUtil.getViewportSize();

        this.button = StaleButton.newObject();
        this.button.transform = new UITransform(size.x/2,size.y/2,size.x / 14, size.y / 20);

        this.button.size = new Vector2(size.x / 14, size.y / 20);
        this.button.text = "StaleButton";
        this.button.fontSize = 18;
        this.button.transitionEnable = true;
        InputUtil.bindButton(Keys.X, this.button);
        this.button.setPressedImageColorDecimal(200, 200, 200, 255);
        this.button.onClicked.add(() => {
            // 当按下按钮执行以下逻辑
            console.log("The \"StaleButton\" button was pressed ~");
        });
    }
}
```

## Hierarchy

- [`Widget`](mw.Widget.md)

  ↳ **`StaleButton`**

## Table of contents

### Properties <Score text="Properties" /> 


::: details click
### Properties <Score text="Properties" /> 
| **[onCustomPropertyChange](mw.Widget.md#oncustompropertychange)**: `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> <Badge type="tip" text="client" />  |
| :-----|
| 监听自定义属性同步事件|
:::


### Accessors <Score text="Accessors" /> 
| **[autoAdjust](mw.StaleButton.md#autoadjust)**(): `boolean` <Badge type="tip" text="client" />  |
| :-----|
| 获取字体是否自适应调整大小:boolean(为True时，文本内容字体大小将自动改变，尽可能大的充满整个文本框，而文本框大小不会变化)|
| **[contentColor](mw.StaleButton.md#contentcolor)**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />  |
| 设置字体内容颜色|
| **[defaultFont](mw.StaleButton.md#defaultfont)**(): `string`  [`UIFontFamily`](../enums/mw.UIFontFamily.md) <Badge type="tip" text="client" />  |
| 获取默认字体|
| **[disableImageColor](mw.StaleButton.md#disableimagecolor)**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />  |
| 获取禁用图片颜色|
| **[disableImageDrawType](mw.StaleButton.md#disableimagedrawtype)**(): `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> <Badge type="tip" text="client" />  |
| 获取禁用图片绘制类型|
| **[disableImageGuid](mw.StaleButton.md#disableimageguid)**(): `string` <Badge type="tip" text="client" />  |
| 获取禁用图片ID|
| **[disableImageInfo](mw.StaleButton.md#disableimageinfo)**(): [`ImageInfo`](mw.ImageInfo.md) <Badge type="tip" text="client" />  |
| 获取按钮Disable图片的ImageInfo|
| **[disableImageMargin](mw.StaleButton.md#disableimagemargin)**(): `Readonly`<[`Margin`](mw.Margin.md)\> <Badge type="tip" text="client" />  |
| 获取禁用图片边距|
| **[disableImageSize](mw.StaleButton.md#disableimagesize)**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />  |
| 获取禁用图片大小|
| **[fallbackFont](mw.StaleButton.md#fallbackfont)**(): `string`  [`UIFontFamily`](../enums/mw.UIFontFamily.md) <Badge type="tip" text="client" />  |
| 获取退却字体|
| **[focusable](mw.StaleButton.md#focusable)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取是否获取输入焦点|
| **[fontColor](mw.StaleButton.md#fontcolor)**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />  |
| 获取字体颜色|
| **[fontLetterSpace](mw.StaleButton.md#fontletterspace)**(): `number` <Badge type="tip" text="client" />  |
| 获取字体间距|
| **[fontSize](mw.StaleButton.md#fontsize)**(): `number` <Badge type="tip" text="client" />  |
| 获取字体大小|
| **[glyph](mw.StaleButton.md#glyph)**(): [`UIFontGlyph`](../enums/mw.UIFontGlyph.md) <Badge type="tip" text="client" />  |
| 获取字体字形|
| **[isRichText](mw.StaleButton.md#isrichtext)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取是否为富文本|
| **[lineHeightPercentage](mw.StaleButton.md#lineheightpercentage)**(): `number` <Badge type="tip" text="client" />  |
| 获取行高系数|
| **[maxSize](mw.StaleButton.md#maxsize)**(): `number` <Badge type="tip" text="client" />  |
| 获取自适应最大字体大小|
| **[minSize](mw.StaleButton.md#minsize)**(): `number` <Badge type="tip" text="client" />  |
| 获取自适应最小字体大小|
| **[normalImageColor](mw.StaleButton.md#normalimagecolor)**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />  |
| 获取普通图片颜色|
| **[normalImageDrawType](mw.StaleButton.md#normalimagedrawtype)**(): `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> <Badge type="tip" text="client" />  |
| 获取普通图片绘制类型|
| **[normalImageGuid](mw.StaleButton.md#normalimageguid)**(): `string` <Badge type="tip" text="client" />  |
| 获取普通图片ID|
| **[normalImageInfo](mw.StaleButton.md#normalimageinfo)**(): [`ImageInfo`](mw.ImageInfo.md) <Badge type="tip" text="client" />  |
| 获取按钮normal图片的ImageInfo|
| **[normalImageMargin](mw.StaleButton.md#normalimagemargin)**(): `Readonly`<[`Margin`](mw.Margin.md)\> <Badge type="tip" text="client" />  |
| 获取普通图片边距|
| **[normalImageSize](mw.StaleButton.md#normalimagesize)**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />  |
| 获取图片大小|
| **[onClicked](mw.StaleButton.md#onclicked)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />  |
| 点击事件|
| **[onHovered](mw.StaleButton.md#onhovered)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="other" />  |
| 悬浮事件|
| **[onPressed](mw.StaleButton.md#onpressed)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />  |
| 按下事件|
| **[onReleased](mw.StaleButton.md#onreleased)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />  |
| 释放事件|
| **[onUnhovered](mw.StaleButton.md#onunhovered)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />  |
| 未悬浮事件|
| **[outlineColor](mw.StaleButton.md#outlinecolor)**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />  |
| 获取字体描边颜色|
| **[outlineSize](mw.StaleButton.md#outlinesize)**(): `number` <Badge type="tip" text="client" />  |
| 获取字体描边宽度|
| **[pressMethod](mw.StaleButton.md#pressmethod)**(`inPressMethod`: [`ButtonPressMethod`](../enums/mw.ButtonPressMethod.md)): `void` <Badge type="tip" text="client" />  |
| 设置按压模式|
| **[pressedImagColor](mw.StaleButton.md#pressedimagcolor)**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />  |
| 获取按压图片颜色|
| **[pressedImageDrawType](mw.StaleButton.md#pressedimagedrawtype)**(): `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> <Badge type="tip" text="client" />  |
| 获取按压图片绘制类型|
| **[pressedImageGuid](mw.StaleButton.md#pressedimageguid)**(): `string` <Badge type="tip" text="client" />  |
| 获取按下图片ID|
| **[pressedImageInfo](mw.StaleButton.md#pressedimageinfo)**(): [`ImageInfo`](mw.ImageInfo.md) <Badge type="tip" text="client" />  |
| 获取按钮Pressed图片的ImageInfo|
| **[pressedImageMargin](mw.StaleButton.md#pressedimagemargin)**(): `Readonly`<[`Margin`](mw.Margin.md)\> <Badge type="tip" text="client" />  |
| 获取按压图片边距|
| **[pressedImageSize](mw.StaleButton.md#pressedimagesize)**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />  |
| 获取按压图片大小|
| **[shadowColor](mw.StaleButton.md#shadowcolor)**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />  |
| 获取字体阴影颜色|
| **[shadowOffset](mw.StaleButton.md#shadowoffset)**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />  |
| 获取字体阴影偏移|
| **[strikethroughEnable](mw.StaleButton.md#strikethroughenable)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取是否开启字体删除线|
| **[text](mw.StaleButton.md#text)**(): `string` <Badge type="tip" [text](mw.StaleButton.md#text)="client" />  |
| 获取按钮文字|
| **[textAlign](mw.StaleButton.md#textalign)**(): [`TextJustify`](../enums/mw.TextJustify.md) <Badge type="tip" text="client" />  |
| 获取字体对齐方式|
| **[textHorizontalLayout](mw.StaleButton.md#texthorizontallayout)**(): [`UITextHorizontalLayout`](../enums/mw.UITextHorizontalLayout.md) <Badge type="tip" text="client" />  |
| 获取当前字体的水平显示方式|
| **[textVerticalAlign](mw.StaleButton.md#textverticalalign)**(): [`TextVerticalJustify`](../enums/mw.TextVerticalJustify.md) <Badge type="tip" text="client" />  |
| 获取字体垂直对齐方式|
| **[touchMethod](mw.StaleButton.md#touchmethod)**(`inTouchMethod`: [`ButtonTouchMethod`](../enums/mw.ButtonTouchMethod.md)): `void` <Badge type="tip" text="client" />  |
| 设置触摸模式|
| **[transitionEnable](mw.StaleButton.md#transitionenable)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取按钮是否启用过度模式,按下是否有效果|
| **[underlineEnable](mw.StaleButton.md#underlineenable)**(): `boolean` <Badge type="tip" text="client" />  |
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
| **[addKey](mw.StaleButton.md#addkey)**(`key`: [`Keys`](../enums/mw.Keys.md)): `void` <Badge type="tip" text="client" />  |
| :-----|
| 同一按键同时只能操控一个UI控件，最新绑定的UI控件会覆盖之前的绑定；脚本中添加的绑定无法覆盖编辑器按键绑定菜单中绑定相同按键的UI控件，但当两个UI控件分别通过代码和菜单绑定到同一按键时，使用代码绑定的优先级更高|
| **[getKeys](mw.StaleButton.md#getkeys)**(): [`Keys`](../enums/mw.Keys.md)[] <Badge type="tip" text="client" />  |
| 获取当前UI控件绑定的所有键盘按键，包括编辑器按键绑定菜单和用代码绑定的按键|
| **[isPressed](mw.StaleButton.md#ispressed)**(): `boolean` <Badge type="tip" text="client" />  |
| 是否按下|
| **[removeKey](mw.StaleButton.md#removekey)**(`key`: [`Keys`](../enums/mw.Keys.md)): `void` <Badge type="tip" text="client" />  |
| 此操作只会解绑动态绑定的按键无法解除编辑器按键绑定菜单中绑定的按键|
| **[setButtonDisableByFile](mw.StaleButton.md#setbuttondisablebyfile)**(`absPath`: `string`, `bRefreshCache?`: `boolean`): `void` <Badge type="tip" text="client" />  |
| 设置不可用图片|
| **[setButtonNormalByFile](mw.StaleButton.md#setbuttonnormalbyfile)**(`absPath`: `string`, `bRefreshCache?`: `boolean`): `void` <Badge type="tip" text="client" />  |
| 设置正常图片|
| **[setButtonPressedByFile](mw.StaleButton.md#setbuttonpressedbyfile)**(`absPath`: `string`, `bRefreshCache?`: `boolean`): `void` <Badge type="tip" text="client" />  |
| 设置按下图片|
| **[setDisableImageColorByHex](mw.StaleButton.md#setdisableimagecolorbyhex)**(`inHexString`: `string`): `void` <Badge type="tip" text="client" />  |
| 设置不可用颜色指定Hex的颜色文本设定颜色 #05050505|
| **[setDisableImageColorDecimal](mw.StaleButton.md#setdisableimagecolordecimal)**(`R`: `number`, `G`: `number`, `B`: `number`, `A`: `number`): `void` <Badge type="tip" text="client" />  |
| 设置不可用颜色|
| **[setFontColorByHex](mw.StaleButton.md#setfontcolorbyhex)**(`inHexString`: `string`): `void` <Badge type="tip" text="client" />  |
| 设置字体颜色,指定Hex的颜色文本设定颜色 #05050505|
| **[setFontColorDecimal](mw.StaleButton.md#setfontcolordecimal)**(`R`: `number`, `G`: `number`, `B`: `number`, `A`: `number`): `void` <Badge type="tip" text="client" />  |
| 设置字体颜色|
| **[setNormalImageColorByHex](mw.StaleButton.md#setnormalimagecolorbyhex)**(`inHexString`: `string`): `void` <Badge type="tip" text="client" />  |
| 设置正常颜色指定Hex的颜色文本设定颜色 #05050505|
| **[setNormalImageColorDecimal](mw.StaleButton.md#setnormalimagecolordecimal)**(`R`: `number`, `G`: `number`, `B`: `number`, `A`: `number`): `void` <Badge type="tip" text="client" />  |
| 设置正常颜色|
| **[setPressedImageColorByHex](mw.StaleButton.md#setpressedimagecolorbyhex)**(`inHexString`: `string`): `void` <Badge type="tip" text="client" />  |
| 设置按下颜色指定Hex的颜色文本设定颜色 #05050505|
| **[setPressedImageColorDecimal](mw.StaleButton.md#setpressedimagecolordecimal)**(`R`: `number`, `G`: `number`, `B`: `number`, `A`: `number`): `void` <Badge type="tip" text="client" />  |
| 设置按下颜色|
| **[newObject](mw.StaleButton.md#newobject)**(`parent?`: [`Canvas`](mw.Canvas.md), `inName?`: `string`): [`StaleButton`](mw.StaleButton.md) <Badge type="tip" text="client" />  |
| 创建 StaleButton 控件|


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

### contentColor <Score text="contentColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **contentColor**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **contentColor**(`inContentColor`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


设置字体内容颜色

#### Returns

| [`LinearColor`](mw.LinearColor.md) | 字体内容颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置字体内容颜色

#### Parameters

| `inContentColor` [`LinearColor`](mw.LinearColor.md) | 颜色，Type.LinearColor类型，数据范围0~1 |
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

### disableImageColor <Score text="disableImageColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **disableImageColor**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **disableImageColor**(`inColor`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取禁用图片颜色

#### Returns

| `Readonly`<[`LinearColor`](mw.LinearColor.md)\> | 禁用图片颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置禁用图片颜色

#### Parameters

| `inColor` [`LinearColor`](mw.LinearColor.md) | 颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### disableImageDrawType <Score text="disableImageDrawType" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **disableImageDrawType**(): `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **disableImageDrawType**(`inDrawTYpe`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取禁用图片绘制类型

#### Returns

| `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> | 禁用图片绘制类型 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置禁用图片绘制类型

#### Parameters

| `inDrawTYpe` [`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md) | 类型 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### disableImageGuid <Score text="disableImageGuid" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **disableImageGuid**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **disableImageGuid**(`inGUID`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取禁用图片ID

#### Returns

| `string` | 禁用图片ID |
| :------ | :------ |


</td>
<td style="text-align: left">


设置不可用图片ID

#### Parameters

| `inGUID` `string` | 图片id |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### disableImageInfo <Score text="disableImageInfo" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **disableImageInfo**(): [`ImageInfo`](mw.ImageInfo.md) <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取按钮Disable图片的ImageInfo

#### Returns

| [`ImageInfo`](mw.ImageInfo.md) | 返回ImageInfo对象 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### disableImageMargin <Score text="disableImageMargin" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **disableImageMargin**(): `Readonly`<[`Margin`](mw.Margin.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **disableImageMargin**(`inMargin`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取禁用图片边距

#### Returns

| `Readonly`<[`Margin`](mw.Margin.md)\> | 禁用图片边距 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置禁用图片边距

#### Parameters

| `inMargin` [`Margin`](mw.Margin.md) | 禁用图片边距 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### disableImageSize <Score text="disableImageSize" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **disableImageSize**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **disableImageSize**(`inSize`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取禁用图片大小

#### Returns

| `Readonly`<[`Vector2`](mw.Vector2.md)\> | 禁用图片大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置禁用图片大小

#### Parameters

| `inSize` [`Vector2`](mw.Vector2.md) | 大小 |
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

### isRichText <Score text="isRichText" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **isRichText**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **isRichText**(`isRichText`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否为富文本

#### Returns

| `boolean` | 是否为富文本 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置富文本

#### Parameters

| `isRichText` | `boolean` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### lineHeightPercentage <Score text="lineHeightPercentage" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **lineHeightPercentage**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **lineHeightPercentage**(`inValue`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取行高系数

#### Returns

| `number` | 行高系数 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置行高系数

#### Parameters

| `inValue` `number` | 系数 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### maxSize <Score text="maxSize" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **maxSize**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **maxSize**(`inText`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取自适应最大字体大小

#### Returns

| `number` | 返回当前的文本内容 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置自适应最大字体大小

#### Parameters

| `inText` `number` | 文本内容 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### minSize <Score text="minSize" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **minSize**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **minSize**(`inText`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取自适应最小字体大小

#### Returns

| `number` | 返回当前的文本内容 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置自适应最小字体大小

#### Parameters

| `inText` `number` | 文本内容 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### normalImageColor <Score text="normalImageColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **normalImageColor**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **normalImageColor**(`inNormalColor`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取普通图片颜色

#### Returns

| `Readonly`<[`LinearColor`](mw.LinearColor.md)\> | 普通图片颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置普通图片颜色

#### Parameters

| `inNormalColor` [`LinearColor`](mw.LinearColor.md) | 颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### normalImageDrawType <Score text="normalImageDrawType" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **normalImageDrawType**(): `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **normalImageDrawType**(`inDrawType`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取普通图片绘制类型

#### Returns

| `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> | 普通图片绘制类型 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置普通图片绘制类型

#### Parameters

| `inDrawType` [`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md) | 类型 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### normalImageGuid <Score text="normalImageGuid" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **normalImageGuid**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **normalImageGuid**(`inGUID`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取普通图片ID

#### Returns

| `string` | 普通图片ID |
| :------ | :------ |


</td>
<td style="text-align: left">


设置正常图片ID

#### Parameters

| `inGUID` `string` | 图片id |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### normalImageInfo <Score text="normalImageInfo" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **normalImageInfo**(): [`ImageInfo`](mw.ImageInfo.md) <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取按钮normal图片的ImageInfo

#### Returns

| [`ImageInfo`](mw.ImageInfo.md) | 返回ImageInfo对象 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### normalImageMargin <Score text="normalImageMargin" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **normalImageMargin**(): `Readonly`<[`Margin`](mw.Margin.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **normalImageMargin**(`inMargin`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取普通图片边距

#### Returns

| `Readonly`<[`Margin`](mw.Margin.md)\> | 普通图片边距 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置普通图片边距

#### Parameters

| `inMargin` [`Margin`](mw.Margin.md) | 普通图片边距 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### normalImageSize <Score text="normalImageSize" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **normalImageSize**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **normalImageSize**(`inSize`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取图片大小

#### Returns

| `Readonly`<[`Vector2`](mw.Vector2.md)\> | 普通图片大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置图片大小

#### Parameters

| `inSize` [`Vector2`](mw.Vector2.md) | 大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### onClicked <Score text="onClicked" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onClicked**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


点击事件

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> | 返回事件的代理 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onHovered <Score text="onHovered" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onHovered**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="other" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


悬浮事件

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> | 返回事件的代理 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onPressed <Score text="onPressed" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onPressed**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


按下事件

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> | 返回事件的代理 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onReleased <Score text="onReleased" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onReleased**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


释放事件

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> | 返回事件的代理 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onUnhovered <Score text="onUnhovered" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **onUnhovered**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


未悬浮事件

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> | 返回事件的代理 |
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

### pressMethod <Score text="pressMethod" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `set` **pressMethod**(`inPressMethod`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


设置按压模式

#### Parameters

| `inPressMethod` [`ButtonPressMethod`](../enums/mw.ButtonPressMethod.md) | 按压模式 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### pressedImagColor <Score text="pressedImagColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **pressedImagColor**(): `Readonly`<[`LinearColor`](mw.LinearColor.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **pressedImagColor**(`inColor`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取按压图片颜色

#### Returns

| `Readonly`<[`LinearColor`](mw.LinearColor.md)\> | 按压图片颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置按压图片颜色

#### Parameters

| `inColor` [`LinearColor`](mw.LinearColor.md) | 颜色，Type.LinearColor类型，数据范围0~1 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### pressedImageDrawType <Score text="pressedImageDrawType" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **pressedImageDrawType**(): `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **pressedImageDrawType**(`inDrawType`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取按压图片绘制类型

#### Returns

| `Readonly`<[`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md)\> | 按压图片绘制类型 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置按压图片绘制类型

#### Parameters

| `inDrawType` [`SlateBrushDrawType`](../enums/mw.SlateBrushDrawType.md) | 类型 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### pressedImageGuid <Score text="pressedImageGuid" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **pressedImageGuid**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **pressedImageGuid**(`inGUID`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取按下图片ID

#### Returns

| `string` | 按下图片ID |
| :------ | :------ |


</td>
<td style="text-align: left">


设置按下图片ID

#### Parameters

| `inGUID` `string` | 图片id |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### pressedImageInfo <Score text="pressedImageInfo" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **pressedImageInfo**(): [`ImageInfo`](mw.ImageInfo.md) <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取按钮Pressed图片的ImageInfo

#### Returns

| [`ImageInfo`](mw.ImageInfo.md) | 返回ImageInfo对象 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### pressedImageMargin <Score text="pressedImageMargin" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **pressedImageMargin**(): `Readonly`<[`Margin`](mw.Margin.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **pressedImageMargin**(`inMargin`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取按压图片边距

#### Returns

| `Readonly`<[`Margin`](mw.Margin.md)\> | 按压图片边距 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置按压图片边距

#### Parameters

| `inMargin` [`Margin`](mw.Margin.md) | 按压图片边距 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### pressedImageSize <Score text="pressedImageSize" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **pressedImageSize**(): `Readonly`<[`Vector2`](mw.Vector2.md)\> <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **pressedImageSize**(`inSize`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取按压图片大小

#### Returns

| `Readonly`<[`Vector2`](mw.Vector2.md)\> | 按压图片大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置按压图片大小

#### Parameters

| `inSize` [`Vector2`](mw.Vector2.md) | 大小 |
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

### textHorizontalLayout <Score text="textHorizontalLayout" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **textHorizontalLayout**(): [`UITextHorizontalLayout`](../enums/mw.UITextHorizontalLayout.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **textHorizontalLayout**(`inTextHorizontalLayout`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取当前字体的水平显示方式

#### Returns

| [`UITextHorizontalLayout`](../enums/mw.UITextHorizontalLayout.md) | 返回字体的水平显示方式 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置字体的水平显示方式

#### Parameters

| `inTextHorizontalLayout` [`UITextHorizontalLayout`](../enums/mw.UITextHorizontalLayout.md) | 水平显示方式 |
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

### touchMethod <Score text="touchMethod" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `set` **touchMethod**(`inTouchMethod`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


设置触摸模式

#### Parameters

| `inTouchMethod` [`ButtonTouchMethod`](../enums/mw.ButtonTouchMethod.md) | Touch模式选择 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### transitionEnable <Score text="transitionEnable" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **transitionEnable**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **transitionEnable**(`inBoolean`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取按钮是否启用过度模式,按下是否有效果

#### Returns

| `boolean` | 按钮是否启用过度模式 |
| :------ | :------ |


</td>
<td style="text-align: left">


是否套用不同的按下方案

#### Parameters

| `inBoolean` `boolean` | 是否套用不同的按下方案 |
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

### isPressed <Score text="isPressed" /> 

• **isPressed**(): `boolean` <Badge type="tip" text="client" />

是否按下

#### Returns

| `boolean` | 返回按钮是否按下 |
| :------ | :------ |

___

### removeKey <Score text="removeKey" /> 

• **removeKey**(`key`): `void` <Badge type="tip" text="client" />

此操作只会解绑动态绑定的按键无法解除编辑器按键绑定菜单中绑定的按键

#### Parameters

| `key` [`Keys`](../enums/mw.Keys.md) | 按键 |
| :------ | :------ |


___

### setButtonDisableByFile <Score text="setButtonDisableByFile" /> 

• **setButtonDisableByFile**(`absPath`, `bRefreshCache?`): `void` <Badge type="tip" text="client" />

设置不可用图片

#### Parameters

| `absPath` `string` | 图片文件路径 <br> range: 路径长度 |
| :------ | :------ |
| `bRefreshCache?` `boolean` | 默认为 true 将重新创建并刷新缓存，为 false 则使用缓存 <br> default: true |


::: warning Precautions

建议设置 bRefreshCache = false 以提升性能

:::

___

### setButtonNormalByFile <Score text="setButtonNormalByFile" /> 

• **setButtonNormalByFile**(`absPath`, `bRefreshCache?`): `void` <Badge type="tip" text="client" />

设置正常图片

#### Parameters

| `absPath` `string` |  图片文件路径 range: 路径长度 |
| :------ | :------ |
| `bRefreshCache?` `boolean` | 为 true 则重新创建并刷新缓存，为 false 则使用缓存。 <br> default: true |


::: warning Precautions

建议设置 bRefreshCache = false 以提升性能

:::

___

### setButtonPressedByFile <Score text="setButtonPressedByFile" /> 

• **setButtonPressedByFile**(`absPath`, `bRefreshCache?`): `void` <Badge type="tip" text="client" />

设置按下图片

#### Parameters

| `absPath` `string` | 图片文件路径 range: 路径长度 |
| :------ | :------ |
| `bRefreshCache?` `boolean` | 默认为 true 将重新创建并刷新缓存，为 false 则使用缓存 <br> default: true |


::: warning Precautions

建议设置 bRefreshCache = false 以提升性能

:::

___

### setDisableImageColorByHex <Score text="setDisableImageColorByHex" /> 

• **setDisableImageColorByHex**(`inHexString`): `void` <Badge type="tip" text="client" />

设置不可用颜色指定Hex的颜色文本设定颜色 #05050505

#### Parameters

| `inHexString` `string` | 颜色字符串 range: 符合 Hex 特点的字符串类型 |
| :------ | :------ |


___

### setDisableImageColorDecimal <Score text="setDisableImageColorDecimal" /> 

• **setDisableImageColorDecimal**(`R`, `G`, `B`, `A`): `void` <Badge type="tip" text="client" />

设置不可用颜色

#### Parameters

| `R` `number` | 颜色 R 值。 <br> range:[0, 255] type: 整形 |
| :------ | :------ |
| `G` `number` | 颜色 G 值。 <br> range:[0, 255] type: 整形 |
| `B` `number` | 颜色 B 值。 <br> range:[0, 255] type: 整形 |
| `A` `number` | 颜色 透明度。 <br> range:[0, 255] type: 整形 |


___

### setFontColorByHex <Score text="setFontColorByHex" /> 

• **setFontColorByHex**(`inHexString`): `void` <Badge type="tip" text="client" />

设置字体颜色,指定Hex的颜色文本设定颜色 #05050505

#### Parameters

| `inHexString` `string` | Hex颜色字符串 range: 符合 Hex 特点的字符串类型 |
| :------ | :------ |


___

### setFontColorDecimal <Score text="setFontColorDecimal" /> 

• **setFontColorDecimal**(`R`, `G`, `B`, `A`): `void` <Badge type="tip" text="client" />

设置字体颜色

#### Parameters

| `R` `number` | 字体 R 值。 <br> range:[0, 255] type: 整形 |
| :------ | :------ |
| `G` `number` | 字体 G 值。 <br> range:[0, 255] type: 整形 |
| `B` `number` | 字体 B 值。 <br> range:[0, 255] type: 整形 |
| `A` `number` | 字体 透明度。 <br> range:[0, 255] type: 整形 |


___

### setNormalImageColorByHex <Score text="setNormalImageColorByHex" /> 

• **setNormalImageColorByHex**(`inHexString`): `void` <Badge type="tip" text="client" />

设置正常颜色指定Hex的颜色文本设定颜色 #05050505

#### Parameters

| `inHexString` `string` | 颜色字符串 range: 符合 Hex 特点的字符串类型 |
| :------ | :------ |


___

### setNormalImageColorDecimal <Score text="setNormalImageColorDecimal" /> 

• **setNormalImageColorDecimal**(`R`, `G`, `B`, `A`): `void` <Badge type="tip" text="client" />

设置正常颜色

#### Parameters

| `R` `number` | 颜色 R 值。 <br> range:[0, 255] type: 整形 |
| :------ | :------ |
| `G` `number` | 颜色 G 值。 <br> range:[0, 255] type: 整形 |
| `B` `number` | 颜色 B 值。 <br> range:[0, 255] type: 整形 |
| `A` `number` | 颜色 透明度。 <br> range:[0, 255] type: 整形 |


___

### setPressedImageColorByHex <Score text="setPressedImageColorByHex" /> 

• **setPressedImageColorByHex**(`inHexString`): `void` <Badge type="tip" text="client" />

设置按下颜色指定Hex的颜色文本设定颜色 #05050505

#### Parameters

| `inHexString` `string` | 颜色字符串 range: 符合 Hex 特点的字符串类型 |
| :------ | :------ |


___

### setPressedImageColorDecimal <Score text="setPressedImageColorDecimal" /> 

• **setPressedImageColorDecimal**(`R`, `G`, `B`, `A`): `void` <Badge type="tip" text="client" />

设置按下颜色

#### Parameters

| `R` `number` | 颜色 R 值。 <br> range:[0, 255] type: 整形 |
| :------ | :------ |
| `G` `number` | 颜色 G 值。 <br> range:[0, 255] type: 整形 |
| `B` `number` | 颜色 B 值。 <br> range:[0, 255] type: 整形 |
| `A` `number` | 颜色 透明度。 <br> range:[0, 255] type: 整形 |


___

### newObject <Score text="newObject" /> 

• `Static` **newObject**(`parent?`, `inName?`): [`StaleButton`](mw.StaleButton.md) <Badge type="tip" text="client" />

创建 StaleButton 控件

#### Parameters

| `parent?` [`Canvas`](mw.Canvas.md) | 创建控件的父级 Canvas 对象 default:null |
| :------ | :------ |
| `inName?` `string` | 创建控件的名称 default:null range:设置合理的名称即可 |

#### Returns

| [`StaleButton`](mw.StaleButton.md) | 返回创建的对象 |
| :------ | :------ |

当 parent 和 inName 与已有的对象相同时，旧的对象会被销毁
