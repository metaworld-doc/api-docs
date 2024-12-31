[界面](../groups/界面.界面.md) / UIService

# UIService <Badge type="tip" text="Class" /> <Score text="UIService" />

UI 管理类

1. 关于 UI 的一些名词解释

- UIPrefab/世界 UI/屏幕 UI/UI 脚本

2. 屏幕 UI 是如何使用并启动的呢？

你有三种方式使用并启动你游戏中的屏幕 UI：

- :cactus: 通过 UIService 来控制继承自 UIScript 的脚本，来管理你的屏幕 UI。

<span style="font-size: 14px;">
使用示例: 创建一个名为 NewScript 的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，会在场景中生成一个屏幕 UI - 按钮。
</span>

```ts
 @Component
 export default class NewScript extends Script {

     protected onStart(): void {
         if(SystemUtil.isClient()){
             UIService.show(NewUIScript);
         }
     }
 }

 class NewUIScript extends UIScript {

     button:StaleButton;

     protected onStart() {
         //设置能否每帧触发onUpdate
         this.canUpdate = false;
         this.layer = UILayerMiddle;

         this.button = StaleButton.newObject(this.rootCanvas);

         this.button.text = "按下变红";
         this.button.transitionEnable = true;
         this.button.pressedImagColor = LinearColor.red;
         this.button.visibility = SlateVisibility.Visible;
         this.button.onClicked.add(() => {
             console.log("click");
         })
     }
 }
```

当然如果 UIPrefab 挂载了某一个继承自 UIScript 的脚本，也是可以用 UIService 管理。不用手动挂载在对象管理器中。

- :cactus: 对象管理器挂载 UIPrefab 启动屏幕 UI。

- :cactus: 使用 UserWidget 和代码自定义创建屏幕 UI。

<span style="font-size: 14px;">
使用示例:创建一个名为 NewExample 的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，按下F键，可以将按钮移动到玩家所在位置
</span>

```ts
@Component
export default class NewExample extends Script {

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        this.test();
    }

    private async test(): Promise<void> {
        let btn = new ButtonUI();
        InputUtil.onKeyDown(Keys.F, async () => {
            let playerPos = Player.localPlayer.character.worldTransform.position;
            let result = InputUtil.projectWorldPositionToWidgetPosition(playerPos);
            if (result) {
                btn.button.position = result.screenPosition;
            }
        })
    }

}

class ButtonUI {
    public button: StaleButton;

    constructor(fun: Function = null) {
        this.creatUI(fun);
    }

    private creatUI(fun: Function = null) {
        // 创建一个UI对象
        let ui = UserWidget.newObject();
        // 将UI添加到屏幕上
        ui.addToViewport(1);
        // 创建一个画布组件
        let rootCanvas = Canvas.newObject();
        rootCanvas.size = new Vector2(1920, 1080);
        rootCanvas.position = Vector2.zero;
        // 将Ui的根画布设置为rootCanvas
        ui.rootContent = rootCanvas;
        // 创建一个按钮
        this.button = StaleButton.newObject(rootCanvas);
        this.button.position = new Vector2(1700, 310);
        this.button.size = new Vector2(150, 50);
        this.button.text = "按下变红";
        this.button.transitionEnable = true;
        this.button.pressedImagColor = LinearColor.red;
        this.button.visibility = SlateVisibility.Visible;

        this.button.onClicked.add(() => {
            if (fun) {
                fun();
            }
        })

    }
}
```

不论你是用 UIPrefab 创建了一个屏幕 UI，还是使用代码动态编辑了一个屏幕 UI，都可以达到你想要的效果。

可以继承此类，自带一个全局 UI 作为 UI 的总节点。需要在全局调用，否则会自动在第一个 UI 生成时自动生成一个默认的管理类。

## Table of contents

### Properties <Score text="Properties" /> 
| **[allPanels](mw.UIService.md#allpanels)**: [`UIScript`](mw.UIScript.md)[]  |
| :-----|
| 所有创建过的Panel|
| **[createPanelMap](mw.UIService.md#createpanelmap)**: `Map`<`string`, [`UIScript`](mw.UIScript.md)[]\>  |
| 所有创建过的管理好的 panels|
| **[logUIInfo](mw.UIService.md#loguiinfo)**: `boolean`  |
| 是否dump GameUI Log 信息|
| **[uniquePanel](mw.UIService.md#uniquepanel)**: [`UIScript`](mw.UIScript.md)  |
| 独占Panel|

### Accessors <Score text="Accessors" /> 
| **[canvas](mw.UIService.md#canvas)**(): [`Canvas`](mw.Canvas.md) <Badge type="tip" text="client" />  |
| :-----|
| 全局所有UI的根canvas|
| **[uiLogInfoEnable](mw.UIService.md#uiloginfoenable)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取允许定时输出 UIService 中管理到的 UI 的信息|

### Methods <Score text="Methods" /> 
| **[dumpUIData](mw.UIService.md#dumpuidata)**(): `void` <Badge type="tip" text="client" />  |
| :-----|
| 打印所有管理到的UI信息|
| **[init](mw.UIService.md#init)**(): `void` <Badge type="tip" text="client" />  |
| 初始化UIManger|
| **[addUILayerMap](mw.UIService.md#adduilayermap)**(`layer`: `number`, `startZOrder`: `number`): `void` <Badge type="tip" text="client" />  |
| 添加 UI 的管理层|
| **[asyncCreate](mw.UIService.md#asynccreate)**<`T`: extends [`UIScript`](mw.UIScript.md)<`T`\>\>(`PanelClass`: () => `T`: extends [`UIScript`](mw.UIScript.md)<`T`\>): `Promise`<`T`: extends [`UIScript`](mw.UIScript.md)<`T`\>\> <Badge type="tip" text="client" />  |
| 异步创建一个界面,失败返回空|
| **[asyncShow](mw.UIService.md#asyncshow)**<`T`: extends [`UIScript`](mw.UIScript.md)<`T`\>\>(`PanelClass`: () => `T`: extends [`UIScript`](mw.UIScript.md)<`T`\>, `...params`: `any`[]): `Promise`<`T`: extends [`UIScript`](mw.UIScript.md)<`T`\>\> <Badge type="tip" text="client" />  |
| 异步显示一个界面，会把界面添加到界面上，从原有父节点移除，失败返回空|
| **[create](mw.UIService.md#create)**<`T`: extends [`UIScript`](mw.UIScript.md)<`T`\>\>(`PanelClass`: () => `T`: extends [`UIScript`](mw.UIScript.md)<`T`\>): `T`: extends [`UIScript`](mw.UIScript.md)<`T`\> <Badge type="tip" text="client" />  |
| 创建一个界面|
| **[destroy](mw.UIService.md#destroy)**(): `void` <Badge type="tip" text="client" />  |
| 销毁该服务，也会销毁所有的UI,再次使用该服务器会重新初始化|
| **[destroyUI](mw.UIService.md#destroyui)**<`T`: extends [`UIScript`](mw.UIScript.md)<`T`\>\>(`PanelClass`: () => `T`: extends [`UIScript`](mw.UIScript.md)<`T`\>): `void` <Badge type="tip" text="client" />  |
| 销毁一个界面,相当于DestroyObject|
| **[getAllUI](mw.UIService.md#getallui)**<`T`: extends [`UIScript`](mw.UIScript.md)<`T`\>\>(`PanelClass`: () => `T`: extends [`UIScript`](mw.UIScript.md)<`T`\>): `T`: extends [`UIScript`](mw.UIScript.md)<`T`\>[] <Badge type="tip" text="client" />  |
| 根据界面类获取界面的所有对象|
| **[getUI](mw.UIService.md#getui)**<`T`: extends [`UIScript`](mw.UIScript.md)<`T`\>\>(`PanelClass`: () => `T`: extends [`UIScript`](mw.UIScript.md)<`T`\>, `bNeedNew?`: `boolean`): `T`: extends [`UIScript`](mw.UIScript.md)<`T`\> <Badge type="tip" text="client" />  |
| 根据界面类获取界面的对象|
| **[getUILayer](mw.UIService.md#getuilayer)**(`panel`: [`UIScript`](mw.UIScript.md)): `number` <Badge type="tip" text="client" />  |
| 获取一个UI的层级|
| **[hide](mw.UIService.md#hide)**<`T`: extends [`UIScript`](mw.UIScript.md)<`T`\>\>(`PanelClass`: () => `T`: extends [`UIScript`](mw.UIScript.md)<`T`\>): `T`: extends [`UIScript`](mw.UIScript.md)<`T`\> <Badge type="tip" text="client" />  |
| 隐藏一个界面，只是隐藏界面设置为Collapsed|
| **[hideUI](mw.UIService.md#hideui)**(`panel`: [`UIScript`](mw.UIScript.md)): `boolean` <Badge type="tip" text="client" />  |
| 移除一个显示的界面,只是隐藏界面设置为Collapsed|
| **[isShown](mw.UIService.md#isshown)**(`panel`: [`UIScript`](mw.UIScript.md)): `boolean` <Badge type="tip" text="other" />  |
| 判断界面是否处于显示状态,需要位于层类显示并且是可见的|
| **[setAllMiddleAndBottomPanelVisible](mw.UIService.md#setallmiddleandbottompanelvisible)**(`value`: `boolean`): `void` <Badge type="tip" text="client" />  |
| 设置Middle和Bottom层所有Panel的可见性|
| **[show](mw.UIService.md#show)**<`T`: extends [`UIScript`](mw.UIScript.md)<`T`\>\>(`PanelClass`: () => `T`: extends [`UIScript`](mw.UIScript.md)<`T`\>, `...params`: `any`[]): `T`: extends [`UIScript`](mw.UIScript.md)<`T`\> <Badge type="tip" text="client" />  |
| 显示一个界面，会把界面添加到界面上，从原有父节点移除|
| **[showUI](mw.UIService.md#showui)**(`panel`: [`UIScript`](mw.UIScript.md), `layer?`: `number`, `...params`: `any`[]): [`UIScript`](mw.UIScript.md) <Badge type="tip" text="client" />  |
| 显示一个界面,会把界面添加到界面上，从原有父节点移除|

## Properties

### allPanels <Score text="allPanels" /> 

• `Protected` **allPanels**: [`UIScript`](mw.UIScript.md)[]

所有创建过的Panel

___

### createPanelMap <Score text="createPanelMap" /> 

• `Protected` **createPanelMap**: `Map`<`string`, [`UIScript`](mw.UIScript.md)[]\>

所有创建过的管理好的 panels

___

### logUIInfo <Score text="logUIInfo" /> 

• `Protected` **logUIInfo**: `boolean`

是否dump GameUI Log 信息

___

### uniquePanel <Score text="uniquePanel" /> 

• `Protected` **uniquePanel**: [`UIScript`](mw.UIScript.md)

独占Panel

## Accessors

### canvas <Score text="canvas" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **canvas**(): [`Canvas`](mw.Canvas.md) <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


全局所有UI的根canvas

#### Returns

| [`Canvas`](mw.Canvas.md) | 根canvas |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### uiLogInfoEnable <Score text="uiLogInfoEnable" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **uiLogInfoEnable**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **uiLogInfoEnable**(`enable`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取允许定时输出 UIService 中管理到的 UI 的信息

#### Returns

| `boolean` | 是否允许 |
| :------ | :------ |


</td>
<td style="text-align: left">


允许定时输出 UIService 中管理到的 UI 的信息

#### Parameters

| `enable` `boolean` | 运行与否 |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods

### dumpUIData <Score text="dumpUIData" /> 

• **dumpUIData**(): `void` <Badge type="tip" text="client" />

打印所有管理到的UI信息


___

### init <Score text="init" /> 

• `Protected` **init**(): `void` <Badge type="tip" text="client" />

初始化UIManger


___

### addUILayerMap <Score text="addUILayerMap" /> 

• `Static` `Protected` **addUILayerMap**(`layer`, `startZOrder`): `void` <Badge type="tip" text="client" />

添加 UI 的管理层

#### Parameters

| `layer` `number` | layer 的序列号 range: 不做限制 type:整数 |
| :------ | :------ |
| `startZOrder` `number` | 该层开始的 zOrder range: 不做限制 type:整数 |


___

### asyncCreate <Score text="asyncCreate" /> 

• `Static` **asyncCreate**<`T`\>(`PanelClass`): `Promise`<`T`\> <Badge type="tip" text="client" />

异步创建一个界面,失败返回空

#### Parameters

| `PanelClass` () => `T` | 界面的类 |
| :------ | :------ |

#### Returns

| `Promise`<`T`\> | 返回创建的UI行为脚本 |
| :------ | :------ |

#### Type parameters

| `T` | extends [`UIScript`](mw.UIScript.md)<`T`\> |
| :------ | :------ |

___

### asyncShow <Score text="asyncShow" /> 

• `Static` **asyncShow**<`T`\>(`PanelClass`, `...params`): `Promise`<`T`\> <Badge type="tip" text="client" />

异步显示一个界面，会把界面添加到界面上，从原有父节点移除，失败返回空

#### Parameters

| `PanelClass` () => `T` | 界面的类如果类没有UI绑定，会创建一个默认的空UI |
| :------ | :------ |
| `...params` `any`[] | 显示参数(这个参数可以传递给界面的onShow方法) |

#### Returns

| `Promise`<`T`\> | 显示的界面 |
| :------ | :------ |

#### Type parameters

| `T` | extends [`UIScript`](mw.UIScript.md)<`T`\> |
| :------ | :------ |

___

### create <Score text="create" /> 

• `Static` **create**<`T`\>(`PanelClass`): `T` <Badge type="tip" text="client" />

创建一个界面

#### Parameters

| `PanelClass` () => `T` | 界面的类 |
| :------ | :------ |

#### Returns

| `T` | 返回创建的UI行为脚本 |
| :------ | :------ |

#### Type parameters

| `T` | extends [`UIScript`](mw.UIScript.md)<`T`\> |
| :------ | :------ |

___

### destroy <Score text="destroy" /> 

• `Static` **destroy**(): `void` <Badge type="tip" text="client" />

销毁该服务，也会销毁所有的UI,再次使用该服务器会重新初始化


___

### destroyUI <Score text="destroyUI" /> 

• `Static` **destroyUI**<`T`\>(`PanelClass`): `void` <Badge type="tip" text="client" />

销毁一个界面,相当于DestroyObject

#### Parameters

| `PanelClass` () => `T` | 销毁界面 |
| :------ | :------ |


#### Type parameters

| `T` | extends [`UIScript`](mw.UIScript.md)<`T`\> |
| :------ | :------ |

___

### getAllUI <Score text="getAllUI" /> 

• `Static` **getAllUI**<`T`\>(`PanelClass`): `T`[] <Badge type="tip" text="client" />

根据界面类获取界面的所有对象

#### Parameters

| `PanelClass` () => `T` | 界面类型 |
| :------ | :------ |

#### Returns

| `T`[] | 界面对象数组,没有的话返回空 |
| :------ | :------ |

#### Type parameters

| `T` | extends [`UIScript`](mw.UIScript.md)<`T`\> |
| :------ | :------ |

___

### getUI <Score text="getUI" /> 

• `Static` **getUI**<`T`\>(`PanelClass`, `bNeedNew?`): `T` <Badge type="tip" text="client" />

根据界面类获取界面的对象

#### Parameters

| `PanelClass` () => `T` | 界面类型 |
| :------ | :------ |
| `bNeedNew?` `boolean` | 没有找到的有缓存的UI界面时，是否需要新建一个 default:true |

#### Returns

| `T` | 界面对象 |
| :------ | :------ |

#### Type parameters

| `T` | extends [`UIScript`](mw.UIScript.md)<`T`\> |
| :------ | :------ |

___

### getUILayer <Score text="getUILayer" /> 

• `Static` **getUILayer**(`panel`): `number` <Badge type="tip" text="client" />

获取一个UI的层级

#### Parameters

| `panel` [`UIScript`](mw.UIScript.md) | GameUI |
| :------ | :------ |

#### Returns

| `number` | UI的层级 |
| :------ | :------ |

___

### hide <Score text="hide" /> 

• `Static` **hide**<`T`\>(`PanelClass`): `T` <Badge type="tip" text="client" />

隐藏一个界面，只是隐藏界面设置为Collapsed

#### Parameters

| `PanelClass` () => `T` | 界面的类 |
| :------ | :------ |

#### Returns

| `T` | 返回隐藏的UI行为类(这个参数可以传递给界面的onHide方法) |
| :------ | :------ |

#### Type parameters

| `T` | extends [`UIScript`](mw.UIScript.md)<`T`\> |
| :------ | :------ |

___

### hideUI <Score text="hideUI" /> 

• `Static` **hideUI**(`panel`): `boolean` <Badge type="tip" text="client" />

移除一个显示的界面,只是隐藏界面设置为Collapsed

#### Parameters

| `panel` [`UIScript`](mw.UIScript.md) | 界面 |
| :------ | :------ |

#### Returns

| `boolean` | 是否移除成功 |
| :------ | :------ |

___

### isShown <Score text="isShown" /> 

• `Static` `Protected` **isShown**(`panel`): `boolean` <Badge type="tip" text="other" />

判断界面是否处于显示状态,需要位于层类显示并且是可见的

#### Parameters

| `panel` [`UIScript`](mw.UIScript.md) | 界面 |
| :------ | :------ |

#### Returns

| `boolean` | 是否显示 |
| :------ | :------ |

___

### setAllMiddleAndBottomPanelVisible <Score text="setAllMiddleAndBottomPanelVisible" /> 

• `Static` **setAllMiddleAndBottomPanelVisible**(`value`): `void` <Badge type="tip" text="client" />

设置Middle和Bottom层所有Panel的可见性

#### Parameters

| `value` `boolean` | 显隐值 |
| :------ | :------ |


___

### show <Score text="show" /> 

• `Static` **show**<`T`\>(`PanelClass`, `...params`): `T` <Badge type="tip" text="client" />

显示一个界面，会把界面添加到界面上，从原有父节点移除

#### Parameters

| `PanelClass` () => `T` | 界面的类如果类没有UI绑定，会创建一个默认的空UI |
| :------ | :------ |
| `...params` `any`[] | 显示参数(这个参数可以传递给界面的onShow方法) |

#### Returns

| `T` | 显示的界面 |
| :------ | :------ |

#### Type parameters

| `T` | extends [`UIScript`](mw.UIScript.md)<`T`\> |
| :------ | :------ |

___

### showUI <Score text="showUI" /> 

• `Static` **showUI**(`panel`, `layer?`, `...params`): [`UIScript`](mw.UIScript.md) <Badge type="tip" text="client" />

显示一个界面,会把界面添加到界面上，从原有父节点移除

#### Parameters

| `panel` [`UIScript`](mw.UIScript.md) | 界面 |
| :------ | :------ |
| `layer?` `number` | 图层 default:UILayer.UILayerMiddle range:不做限制，可使用 UILayerMiddle 类型枚举 type: 整形 |
| `...params` `any`[] | 显示参数(这个参数可以传递给界面的onShow方法) |

#### Returns

| [`UIScript`](mw.UIScript.md) | 显示的界面 |
| :------ | :------ |
