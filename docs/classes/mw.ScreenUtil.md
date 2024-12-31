[工具](../groups/工具.工具.md) / ScreenUtil

# ScreenUtil <Badge type="tip" text="Class" /> <Score text="ScreenUtil" />

屏幕视口工具

## Table of contents

### Methods <Score text="Methods" /> 
| **[checkWidgetAt](mw.ScreenUtil.md#checkwidgetat)**(`screenPosition`: [`Vector2`](mw.Vector2.md)): `boolean` <Badge type="tip" text="client" />  |
| :-----|
| 获取屏幕坐标点处是否有UI，注意该方法性能过差，不要频繁调用|
| **[getGameObjectByScreenPosition](mw.ScreenUtil.md#getgameobjectbyscreenposition)**(`sceneX`: `number`, `sceneY`: `number`, `distance?`: `number`, `multiTrace?`: `boolean`, `onRay?`: `boolean`): [`HitResult`](mw.HitResult.md)[] <Badge type="tip" text="client" />  |
| 获取视口相应位置的物体|
| **[getSightBeadPosition](mw.ScreenUtil.md#getsightbeadposition)**(): [`Vector`](mw.Vector.md) <Badge type="tip" text="client" />  |
| 获取相机中心点所瞄准的世界位置|
| **[getWidgetAt](mw.ScreenUtil.md#getwidgetat)**(`screenPosition`: [`Vector2`](mw.Vector2.md)): [`Widget`](mw.Widget.md) <Badge type="tip" text="client" />  |
| 获取屏幕坐标点处的UI，注意该方法性能过差，不要频繁调用|
| **[projectWorldPositionToWidgetPosition](mw.ScreenUtil.md#projectworldpositiontowidgetposition)**(`player`: [`Player`](mw.Player.md), `worldLocation`: [`Vector`](mw.Vector.md), `outScreenPosition`: [`Vector2`](mw.Vector2.md), `isPlayerViewportRelative`: `boolean`): `boolean` <Badge type="tip" text="client" />  |
| 获取投影世界到播放器的屏幕位置，然后将其转换为控件位置，考虑任何质量缩放。|

## Methods

### checkWidgetAt <Score text="checkWidgetAt" /> 

• `Static` **checkWidgetAt**(`screenPosition`): `boolean` <Badge type="tip" text="client" />

获取屏幕坐标点处是否有UI，注意该方法性能过差，不要频繁调用

#### Parameters

| `screenPosition` [`Vector2`](mw.Vector2.md) | 屏幕坐标点 |
| :------ | :------ |

#### Returns

| `boolean` | 是否有UI在这个位置 |
| :------ | :------ |

___

### getGameObjectByScreenPosition <Score text="getGameObjectByScreenPosition" /> 

• `Static` **getGameObjectByScreenPosition**(`sceneX`, `sceneY`, `distance?`, `multiTrace?`, `onRay?`): [`HitResult`](mw.HitResult.md)[] <Badge type="tip" text="client" />

获取视口相应位置的物体

#### Parameters

| `sceneX` `number` | 视口坐标 X range:不超过屏幕坐标，关于屏幕坐标详情请看 class Vector2 type: 浮点数 |
| :------ | :------ |
| `sceneY` `number` | 视口坐标 Y range:不超过屏幕坐标，关于屏幕坐标详情请看 class Vector2 type: 浮点数 |
| `distance?` `number` | 检测距离 default:100000 range: 不做限制，type: 浮点数 |
| `multiTrace?` `boolean` | 是否获取多个GameObject default:false |
| `onRay?` `boolean` | 是否开启射线显示效果 default:false |

#### Returns

| [`HitResult`](mw.HitResult.md)[] | 点击位置的物体 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为ScreenExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，获取触摸位置所对应的世界Object
</span>

```ts
@Component
export default class ScreenExample extends Script {
    touch: TouchInput;
    async onStart() {
        this.touch = new TouchInput();
        this.touch.onTouch.add((index, location, type) => {
            console.log("ontouch", index, location, type);
            if (type == TouchInputType.TouchBegin) {
                console.log("触摸的GameObject名字是：" + this.onTouchBegin(index, location).name);
            }
        })
    }

    // 开始触摸屏幕，从此位置
    private onTouchBegin(index: number, location: Vector2): mw.GameObject{
       return ScreenUtil.getGameObjectByScreenPosition(location.x, location.y)[0].gameObject;
    }
}
```

___

### getSightBeadPosition <Score text="getSightBeadPosition" /> 

• `Static` **getSightBeadPosition**(): [`Vector`](mw.Vector.md) <Badge type="tip" text="client" />

获取相机中心点所瞄准的世界位置

#### Returns

| [`Vector`](mw.Vector.md) | 目标点世界位置 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为ScreenExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，手指移动时获取视口中心点所对应的世界位置
</span>

```ts
@Component
export default class ScreenExample extends Script {
    touch: TouchInput;
    async onStart() {
        this.touch = new TouchInput();
        this.touch.onTouchMove.add((index, location, type) => {
            console.log("ontouch", index, location, type);
            if (type == TouchInputType.TouchMove) {
                console.log("视口中心点所对应的世界位置是：" + getSightBeadPosition());
            }
        })
    }
```

___

### getWidgetAt <Score text="getWidgetAt" /> 

• `Static` **getWidgetAt**(`screenPosition`): [`Widget`](mw.Widget.md) <Badge type="tip" text="client" />

获取屏幕坐标点处的UI，注意该方法性能过差，不要频繁调用

#### Parameters

| `screenPosition` [`Vector2`](mw.Vector2.md) | 屏幕坐标点 |
| :------ | :------ |

#### Returns

| [`Widget`](mw.Widget.md) | 返回这个点的UI，如果没有返回空 |
| :------ | :------ |

___

### projectWorldPositionToWidgetPosition <Score text="projectWorldPositionToWidgetPosition" /> 

• `Static` **projectWorldPositionToWidgetPosition**(`player`, `worldLocation`, `outScreenPosition`, `isPlayerViewportRelative`): `boolean` <Badge type="tip" text="client" />

获取投影世界到播放器的屏幕位置，然后将其转换为控件位置，考虑任何质量缩放。

#### Parameters

| `player` [`Player`](mw.Player.md) | 玩家在游戏世界中的位置投射到屏幕上的控制器 |
| :------ | :------ |
| `worldLocation` [`Vector`](mw.Vector.md) | 要投射的世界位置 |
| `outScreenPosition` [`Vector2`](mw.Vector2.md) | 在视口的位置 |
| `isPlayerViewportRelative` `boolean` | 是否与玩家视口子区域相关(当在分屏中使用玩家附加的小部件或当宽度比受限时有用)如果位置投射到屏幕上，返回true |

#### Returns

| `boolean` | boolean |
| :------ | :------ |
