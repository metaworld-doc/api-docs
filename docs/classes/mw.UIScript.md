[界面](../groups/界面.界面.md) / UIScript

# UIScript <Badge type="tip" text="Class" /> <Score text="UIScript" />

UI 的驱动脚本基类

-----------------------

1. UIScript 是如何工作的？

当你想要使用编辑器的 UI 功能时，便很大几率要接触 UIScript，除非使用 UserWidget 自定义创建界面。

继承自 UIScript 与继承自 Script 的脚本有所不同，继承自 Script 的脚本挂载在对象管理器中，编辑器会自动帮你调用生命周期函数。但是继承自 UIScript 的脚本放置在对象管理器中，编辑器是不会自动帮你调用生命周期函数的。

他需要依赖 UIService 或 UIPrefab。

2. 继承自 UIScript 脚本享受的生命周期有哪些？

:cactus: 这里有详细的描述

[LifeCycleandEventDescriptionofUIScripts](https://docs.ark.online/UI/LifeCycleandEventDescriptionofUIScripts.html)

3. 什么时候编辑器会帮你调用 UI 的生命周期呢？

有两种方式：

- 使用 UIService 帮你管理此脚本，当 UIService.create 并 show 时，会启动脚本的生命周期。

- 使用 UIPrefab。脚本挂载在 UIPrefab 上，并把 UIPrefab 放在对象管理器中。

## Hierarchy

- **`UIScript`**

  ↳ [`BagItemUI`](mwext.BagItemUI.md)

  ↳ [`BagUI`](mwext.BagUI.md)

  ↳ [`ItemDeleteUI`](mwext.ItemDeleteUI.md)

  ↳ [`IBagItemSkin`](../interfaces/mwext.IBagItemSkin.md)

  ↳ [`ILeaderboardItemView`](../interfaces/mwext.ILeaderboardItemView.md)

  ↳ [`ILeaderboardPanelView`](../interfaces/mwext.ILeaderboardPanelView.md)

  ↳ [`BaseView`](mwext.BaseView.md)

## Table of contents

### Accessors <Score text="Accessors" /> 
| **[canUpdate](mw.UIScript.md#canupdate)**(): `boolean` <Badge type="tip" text="client" />  |
| :-----|
| 获取是否能触发 UI 中 onUpdate 生命周期函数|
| **[fullScreen](mw.UIScript.md#fullscreen)**(`inFull`: `boolean`): `void` <Badge type="tip" text="client" />  |
| 设置随父节点全屏适配,会验证父节点大小以保证跟随父节点的大小|
| **[layer](mw.UIScript.md#layer)**(): `number` <Badge type="tip" text="client" />  |
| 获取 UI 的 Layer 层级|
| **[rootCanvas](mw.UIScript.md#rootcanvas)**(): [`Canvas`](mw.Canvas.md) <Badge type="tip" text="client" />  |
| 获取 UI 的根 Canvas 节点|
| **[uiObject](mw.UIScript.md#uiobject)**(): [`Widget`](mw.Widget.md)  |
| 获取 UI 顶层控件对象|
| **[uiWidgetBase](mw.UIScript.md#uiwidgetbase)**(): [`UserWidget`](mw.UserWidget.md) <Badge type="tip" text="client" />  |
| 获取 UI 顶层控件对象|
| **[visible](mw.UIScript.md#visible)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取 UI 是否显示|

### Methods <Score text="Methods" /> 
| **[destroy](mw.UIScript.md#destroy)**(): `void` <Badge type="tip" text="client" />  |
| :-----|
| 销毁 UI 对象|
| **[detectDrag](mw.UIScript.md#detectdrag)**(`dragKey`: [`Keys`](../enums/mw.Keys.md)): [`EventReply`](mw.EventReply.md) <Badge type="tip" text="client" />  |
| 触发 DragDrop 事件的检测|
| **[detectDragIfPressed](mw.UIScript.md#detectdragifpressed)**(`inPointEvent`: [`PointerEvent`](mw.PointerEvent.md), `dragKey`: [`Keys`](../enums/mw.Keys.md)): [`EventReply`](mw.EventReply.md) <Badge type="tip" text="client" />  |
| 事件检测通过，触发 DragDrop 事件的回复。|
| **[newDragDrop](mw.UIScript.md#newdragdrop)**(`inVisualWidget`: [`Widget`](mw.Widget.md), `inTag?`: `string`, `inPayLoad?`: `any`, `inPivot?`: [`DragPivot`](../enums/mw.DragPivot.md), `inOffset?`: [`Vector2`](mw.Vector2.md)): [`DragDropOperation`](mw.DragDropOperation.md) <Badge type="tip" text="client" />  |
| 创建 DragDrop 事件|
| **[remove](mw.UIScript.md#remove)**(): `void` <Badge type="tip" text="client" />  |
| 移除 UI 对象|
| **[setVisible](mw.UIScript.md#setvisible)**(`inVisible`: `boolean`  [`SlateVisibility`](../enums/mw.SlateVisibility.md), `...params`: `any`[]): `void` <Badge type="tip" text="client" />  |
| 设置 UI 是否显示|
| **[addBehavior](mw.UIScript.md#addbehavior)**(`key`: `string`, `value`: `any`): `void` <Badge type="tip" text="client" />  |
| 添加一个全局行为|
| **[clearBehavior](mw.UIScript.md#clearbehavior)**(): `void` <Badge type="tip" text="client" />  |
| 清空全局一个行为|
| **[getBehavior](mw.UIScript.md#getbehavior)**(`key`: `string`): `any` <Badge type="tip" text="client" />  |
| 执行一个全局的行为|
| **[removeBehavior](mw.UIScript.md#removebehavior)**(`key`: `string`): `void` <Badge type="tip" text="client" />  |
| 移除全局一个行为|

## Accessors

### canUpdate <Score text="canUpdate" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **canUpdate**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **canUpdate**(`bCanUpdate`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否能触发 UI 中 onUpdate 生命周期函数

默认是 false

#### Returns

| `boolean` | 返回能否触发 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否能触发 UI 中 onUpdate 生命周期函数

#### Parameters

| `bCanUpdate` `boolean` |  能否触发 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### fullScreen <Score text="fullScreen" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `set` **fullScreen**(`inFull`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


设置随父节点全屏适配,会验证父节点大小以保证跟随父节点的大小

#### Parameters

| `inFull` `boolean` |  设置为随父节点大小全屏适配 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### layer <Score text="layer" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **layer**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **layer**(`inLayer`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取 UI 的 Layer 层级


#### Returns

| `number` | Layer层级 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置 UI 的所在的 Layer 层级

显示可能会影响到 zOrder，使用 UIService 显示 UI 时，会根据 Layer 层级动态设置 zOrder，每一次调用都会重新计算当前 layer 的新 zOrder，确保 UI 位于当前层级的顶端。

#### Parameters

| `inLayer` `number` |  设置Layer层级 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 一般来说，可以使用内置定义好的，也可以是自定义拓展层级
</span>

```ts
// @description 场景 zOrder开始于0
const UILayerScene: typeof mw.UILayerScene;
// @description 底层 zOrder开始于100000
const UILayerBottom: typeof mw.UILayerBottom;
// @description 中层 zOrder开始于200000
const UILayerMiddle: typeof mw.UILayerMiddle;
// @description 独享层(调用此层会自动隐藏Bottom和Middle层) zOrder开始于300000
const UILayerOwn: typeof mw.UILayerOwn;
// @description 顶层 zOrder开始于400000
const UILayerTop: typeof mw.UILayerTop;
// @description 对话 zOrder开始于500000
const UILayerDialog: typeof mw.UILayerDialog;
// @description 系统 zOrder开始于600000
const UILayerSystem: typeof mw.UILayerSystem;
// @description 错误 这个层级不可以使用，需要增加层级可以使用addUILayerMap zOrder开始于700000
const UILayerError: typeof mw.UILayerError;
```
___

### rootCanvas <Score text="rootCanvas" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **rootCanvas**(): [`Canvas`](mw.Canvas.md) <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取 UI 的根 Canvas 节点


#### Returns

| [`Canvas`](mw.Canvas.md) | 返回canvas节点 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 创建一个名为 NewScript 的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，此示例中 this.rootCanvas.name 为空，因为没有给这个界面添加 Canvas。
</span>

```ts
@Component
export default class NewScript extends Script {
    protected onStart(): void {
        if(SystemUtil.isClient()){
            UIService.show(newUI);
        }
    }
}

class newUI extends UIScript{
    button:StaleButton;
    protected onStart() {

        this.canUpdate = false;
        this.layer = UILayerScene;

        console.log(this.uiObject.name);
        console.log(this.uiWidgetBase.name);
        console.log(this.rootCanvas.name);

        this.button = StaleButton.newObject(this.rootCanvas);
        this.button.text = "button";
        this.button.visibility = SlateVisibility.Visible;
    }
}
```
___

### uiObject <Score text="uiObject" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **uiObject**(): [`Widget`](mw.Widget.md)

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取 UI 顶层控件对象


#### Returns

| [`Widget`](mw.Widget.md) | 脚本挂载的UI对象 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 创建一个名为 NewScript 的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，编辑器会动态生成一个 UserWidget，可以看到 UserWidget 控件的名字。
</span>

```ts
@Component
export default class NewScript extends Script {
    protected onStart(): void {
        if(SystemUtil.isClient()){
            UIService.show(newUI);
        }
    }
}

class newUI extends UIScript{
    button:StaleButton;
    protected onStart() {

        this.canUpdate = false;
        this.layer = UILayerScene;

        console.log(this.uiObject.name);
        console.log(this.uiWidgetBase.name);
        console.log(this.rootCanvas.name);

        this.button = StaleButton.newObject(this.rootCanvas);
        this.button.text = "button";
        this.button.visibility = SlateVisibility.Visible;
    }
}
```
___

### uiWidgetBase <Score text="uiWidgetBase" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **uiWidgetBase**(): [`UserWidget`](mw.UserWidget.md) <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取 UI 顶层控件对象


#### Returns

| [`UserWidget`](mw.UserWidget.md) | 返回转化指定UserWidget对象 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 创建一个名为 NewScript 的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，编辑器会动态生成一个 UserWidget，可以看到 UserWidget 控件的名字。
</span>

```ts
@Component
export default class NewScript extends Script {
    protected onStart(): void {
        if(SystemUtil.isClient()){
            UIService.show(newUI);
        }
    }
}

class newUI extends UIScript{
    button:StaleButton;
    protected onStart() {

        this.canUpdate = false;
        this.layer = UILayerScene;

        console.log(this.uiObject.name);
        console.log(this.uiWidgetBase.name);
        console.log(this.rootCanvas.name);

        this.button = StaleButton.newObject(this.rootCanvas);
        this.button.text = "button";
        this.button.visibility = SlateVisibility.Visible;
    }
}
```
___

### visible <Score text="visible" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **visible**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **visible**(`inVisible`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取 UI 是否显示

#### Returns

| `boolean` | 返回是否可见 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置 UI 是否显示

会触发绑定的脚本生命周期中 OnShow/OnHide 事件，需要传递参数的可以使用 setVisible 方法。

#### Parameters

| `inVisible` `boolean` |  设置是否可见 可见设置为SelfHitTestInvisible,不可见设置为Collapsed |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods

### destroy <Score text="destroy" /> 

• **destroy**(): `void` <Badge type="tip" text="client" />

销毁 UI 对象


___

### detectDrag <Score text="detectDrag" /> 

• **detectDrag**(`dragKey`): [`EventReply`](mw.EventReply.md) <Badge type="tip" text="client" />

触发 DragDrop 事件的检测

#### Parameters

| `dragKey` [`Keys`](../enums/mw.Keys.md) | 触发按键 default:mw.Keys |
| :------ | :------ |

#### Returns

| [`EventReply`](mw.EventReply.md) | 返回触发的事件回复 |
| :------ | :------ |

___

### detectDragIfPressed <Score text="detectDragIfPressed" /> 

• **detectDragIfPressed**(`inPointEvent`, `dragKey`): [`EventReply`](mw.EventReply.md) <Badge type="tip" text="client" />

事件检测通过，触发 DragDrop 事件的回复。

#### Parameters

| `inPointEvent` [`PointerEvent`](mw.PointerEvent.md) | 传递触发的事件信息 |
| :------ | :------ |
| `dragKey` [`Keys`](../enums/mw.Keys.md) | 触发按键 |

#### Returns

| [`EventReply`](mw.EventReply.md) | 返回触发的事件回复 |
| :------ | :------ |

___

### newDragDrop <Score text="newDragDrop" /> 

• **newDragDrop**(`inVisualWidget`, `inTag?`, `inPayLoad?`, `inPivot?`, `inOffset?`): [`DragDropOperation`](mw.DragDropOperation.md) <Badge type="tip" text="client" />

创建 DragDrop 事件

#### Parameters

| `inVisualWidget` [`Widget`](mw.Widget.md) | 拖拽显示的UI控件 |
| :------ | :------ |
| `inTag?` `string` | 标签文本 default:"" range:不做限制 |
| `inPayLoad?` `any` | 拖拽事件数据信息 default:null |
| `inPivot?` [`DragPivot`](../enums/mw.DragPivot.md) | 拖拽显示UI的锚点 default:UIType.DragPivot.TopLeft |
| `inOffset?` [`Vector2`](mw.Vector2.md) | 拖拽显示UI相对于锚点的偏移的百分比 default:vector2(0,0) |

#### Returns

| [`DragDropOperation`](mw.DragDropOperation.md) | 返回触发的事件回复 |
| :------ | :------ |

___

### remove <Score text="remove" /> 

• **remove**(): `void` <Badge type="tip" text="client" />

移除 UI 对象


___

### setVisible <Score text="setVisible" /> 

• **setVisible**(`inVisible`, `...params`): `void` <Badge type="tip" text="client" />

设置 UI 是否显示

#### Parameters

| `inVisible` `boolean`  [`SlateVisibility`](../enums/mw.SlateVisibility.md) |  设置是否可见，如果是 boolean 类型设置为 SelfHitTestInvisible ，不可见设置为 Collapsed， 否则为按照枚举拉设置具体的显示类型。 |
| :------ | :------ |
| `...params` `any`[] |  传递给onShow的参数 |


会触发绑定的脚本的 OnShow/OnHide 事件，可以传递参数。

___

### addBehavior <Score text="addBehavior" /> 

• `Static` **addBehavior**(`key`, `value`): `void` <Badge type="tip" text="client" />

添加一个全局行为

#### Parameters

| `key` `string` |  行为标记 range:字符串长度不受限制，合理即可 |
| :------ | :------ |
| `value` `any` |  行为值 |


UI 事件通信的一种更加简便的方式。

<span style="font-size: 14px;">
使用示例: 创建一个名为 NewScript 的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，会在场景中生成一个屏幕 UI - 按钮，按下P键，按钮文字发生改变。
</span>

```ts
@Component
export default class NewScript extends Script {
    protected onStart(): void {
        if(SystemUtil.isClient()){
            //UIService.create(newUI);
            UIService.show(newUI);
            UIScript.addBehavior("UI",(ui:StaleButton)=>{
                ui.text = "change";
            });
        }
    }
}

class newUI extends UIScript{
    button:StaleButton;
    protected onStart() {
        //设置能否每帧触发onUpdate
        this.canUpdate = false;
        this.layer = UILayerMiddle;

        this.button = StaleButton.newObject(this.rootCanvas);

        this.button.text = "Press to turn red";
        this.button.transitionEnable = true;
        this.button.pressedImagColor = LinearColor.red;
        this.button.visibility = SlateVisibility.Visible;
        this.button.onClicked.add(() => {
            console.log("click");
        })
        InputUtil.onKeyDown(Keys.P,()=>{
            let ui = UIScript.getBehavior("UI");
            ui(this.button);
        });
    }
}
```

___

### clearBehavior <Score text="clearBehavior" /> 

• `Static` **clearBehavior**(): `void` <Badge type="tip" text="client" />

清空全局一个行为


___

### getBehavior <Score text="getBehavior" /> 

• `Static` **getBehavior**(`key`): `any` <Badge type="tip" text="client" />

执行一个全局的行为

#### Parameters

| `key` `string` |  行为标记 range:字符串长度不受限制，合理即可 |
| :------ | :------ |

#### Returns

| `any` | 返回一个行为 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例: 创建一个名为 NewScript 的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，会在场景中生成一个屏幕 UI - 按钮，按下P键，按钮文字发生改变。
</span>

```ts
@Component
export default class NewScript extends Script {
    protected onStart(): void {
        if(SystemUtil.isClient()){
            //UIService.create(newUI);
            UIService.show(newUI);
            UIScript.addBehavior("UI",(ui:StaleButton)=>{
                ui.text = "change";
            });
        }
    }
}

class newUI extends UIScript{
    button:StaleButton;
    protected onStart() {
        //设置能否每帧触发onUpdate
        this.canUpdate = false;
        this.layer = UILayerMiddle;

        this.button = StaleButton.newObject(this.rootCanvas);

        this.button.text = "Press to turn red";
        this.button.transitionEnable = true;
        this.button.pressedImagColor = LinearColor.red;
        this.button.visibility = SlateVisibility.Visible;
        this.button.onClicked.add(() => {
            console.log("click");
        })
        InputUtil.onKeyDown(Keys.P,()=>{
            let ui = UIScript.getBehavior("UI");
            ui(this.button);
        });
    }
}
```

___

### removeBehavior <Score text="removeBehavior" /> 

• `Static` **removeBehavior**(`key`): `void` <Badge type="tip" text="client" />

移除全局一个行为

#### Parameters

| `key` `string` |  行为标记 range:字符串长度不受限制，合理即可 |
| :------ | :------ |

