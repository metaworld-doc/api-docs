[动画](../groups/动画.动画.md) / SubStance

# SubStance <Badge type="tip" text="Class" /> <Score text="SubStance" />

二级姿态

-------------------------

二级姿态是动画系统的拓展, 用于实现独立于基础姿态外的复杂动画逻辑(如持枪, 攀爬等)。

基二级姿态资源同基础姿态（Stance）也是一个外部的资源，打包后生成的文件被上传到资源服务器, 你可以在本地资源库中的基础姿态分类下查找并下载它们。

- 同样拥有 loadSubStance 、play、stop等功能

- 还有额外出色的混合模式，详见 StanceBlendMode 。

## Hierarchy

- `StanceBase`

  ↳ **`SubStance`**

## Table of contents

### Accessors <Score text="Accessors" /> 
| **[assetId](mw.SubStance.md#assetid)**(): `string`  |
| :-----|
| 资源GUID|
| **[blendMode](mw.SubStance.md#blendmode)**(): [`StanceBlendMode`](../enums/mw.StanceBlendMode.md)   |
| 姿态的混合模式|

### Methods <Score text="Methods" /> 
| **[play](mw.SubStance.md#play)**(): `boolean`   |
| :-----|
| 播放姿态|
| **[stop](mw.SubStance.md#stop)**(): `boolean`   |
| 停止这个姿态对象, 并返回执行结果|

## Accessors

### assetId <Score text="assetId" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **assetId**(): `string`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


资源GUID


#### Returns

| `string` |  |
| :------ | :------ |

</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"94261,14520"拖入优先加载栏。创建一个名为"Example_SubStance_AssetId"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，在玩家角色上加载一个仅上半身的瞄准姿态和一个仅下半身的踢腿姿态，按下键盘“1”， 切换播放瞄准姿态和踢腿姿态。你将在场景中看到角色不同姿态的效果。按下键盘“2”， 停止播放姿态。代码如下：
</span>

```ts
@Component
export default class Example_SubStance_AssetId extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端玩家
            let myPlayer = Player.localPlayer;
            // 获取玩家控制角色
            let myCharacter = myPlayer.character;
            // 给角色加载仅上半身瞄准姿态
            let aimStance = myCharacter.loadSubStance("94261");
            aimStance.blendMode = StanceBlendMode.BlendUpper;
            console.log("aimStance assetId " + aimStance.assetId);
            // 给角色加载仅下半身踢腿姿态
            let kickStance = myCharacter.loadSubStance("14520");
            kickStance.blendMode = StanceBlendMode.BlendLower;
            console.log("kickStance assetId " + kickStance.assetId);
            // 添加一个按键方法:按下键盘“1”，切换播放瞄准姿态和踢腿姿态
            InputUtil.onKeyDown(Keys.One, () => {
                if(myCharacter.currentSubStance == aimStance) {
                    kickStance.play();
                } else {
                    aimStance.play();
                }
            });
            // 添加一个按键方法:按下键盘“2”，停止播放姿态
            InputUtil.onKeyDown(Keys.Two, () => {
                if(myCharacter.currentSubStance) {
                    myCharacter.currentSubStance.stop();
                }
            });
        }
    }
}
```
___

### blendMode <Score text="blendMode" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **blendMode**(): [`StanceBlendMode`](../enums/mw.StanceBlendMode.md) 

</th>
<th style="text-align: left">

• `set` **blendMode**(`newBlendMode`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


姿态的混合模式

::: warning Precautions

姿态的播放位置(上半身, 下半身, 全身), 对正在播放的姿态修改时无效.
如果这个姿态是通过预制姿态资源GUID创建的, 那么它的默认值会自动从资源上获取;
如果是通过动画资源GUID创建的, 那么它的默认值为StanceBlendMode.WholeBody.

:::

#### Returns

| [`StanceBlendMode`](../enums/mw.StanceBlendMode.md) |  |
| :------ | :------ |


</td>
<td style="text-align: left">


姿态的混合模式

::: warning Precautions

姿态的播放位置(上半身, 下半身, 全身), 对正在播放的姿态修改时无效.
如果这个姿态是通过预制姿态资源GUID创建的, 那么它的默认值会自动从资源上获取;
如果是通过动画资源GUID创建的, 那么它的默认值为StanceBlendMode.WholeBody.

:::


#### Parameters

| `newBlendMode` | [`StanceBlendMode`](../enums/mw.StanceBlendMode.md) |
| :------ | :------ |

</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"94261,14520"拖入优先加载栏。创建一个名为"Example_SubStance_BlendMode"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，在玩家角色上加载一个仅上半身的瞄准姿态和一个仅下半身的踢腿姿态，按下键盘“1”， 切换播放瞄准姿态和踢腿姿态。你将在场景中看到角色不同姿态的效果。按下键盘“2”， 停止播放姿态。代码如下：
</span>

```ts
@Component
export default class Example_SubStance_BlendMode extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端玩家
            let myPlayer = Player.localPlayer;
            // 获取玩家控制角色
            let myCharacter = myPlayer.character;
            // 给角色加载仅上半身瞄准姿态
            let aimStance = myCharacter.loadSubStance("94261");
            aimStance.blendMode = StanceBlendMode.BlendUpper;
            console.log("aimStance assetId " + aimStance.assetId);
            // 给角色加载仅下半身踢腿姿态
            let kickStance = myCharacter.loadSubStance("14520");
            kickStance.blendMode = StanceBlendMode.BlendLower;
            console.log("kickStance assetId " + kickStance.assetId);
            // 添加一个按键方法:按下键盘“1”，切换播放瞄准姿态和踢腿姿态
            InputUtil.onKeyDown(Keys.One, () => {
                if(myCharacter.currentSubStance == aimStance) {
                    kickStance.play();
                } else {
                    aimStance.play();
                }
            });
            // 添加一个按键方法:按下键盘“2”，停止播放姿态
            InputUtil.onKeyDown(Keys.Two, () => {
                if(myCharacter.currentSubStance) {
                    myCharacter.currentSubStance.stop();
                }
            });
        }
    }
}
```


## Methods

### play <Score text="play" /> 

• **play**(): `boolean` 

播放姿态

#### Returns

| `boolean` | 播放结果，当未进行资源加载时，会返回false，但内部会进行资源异步加载，并在完成后播放。 |
| :------ | :------ |

::: warning Precautions

播放这个姿态对象, 并返回执行结果. 这个操作是否会自动同步多端, 取决于调用端，服务端广播生效，客户端本地生效。

:::

<span style="font-size: 14px;">
使用示例:将使用到的资源:"94261,14520"拖入优先加载栏。创建一个名为"Example_SubStance_Play"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，在玩家角色上加载一个仅上半身的瞄准姿态和一个仅下半身的踢腿姿态，按下键盘“1”， 切换播放瞄准姿态和踢腿姿态。你将在场景中看到角色不同姿态的效果。按下键盘“2”， 停止播放姿态。代码如下：
</span>

```ts
@Component
export default class Example_SubStance_Play extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端玩家
            let myPlayer = Player.localPlayer;
            // 获取玩家控制角色
            let myCharacter = myPlayer.character;
            // 给角色加载仅上半身瞄准姿态
            let aimStance = myCharacter.loadSubStance("94261");
            aimStance.blendMode = StanceBlendMode.BlendUpper;
            console.log("aimStance assetId " + aimStance.assetId);
            // 给角色加载仅下半身踢腿姿态
            let kickStance = myCharacter.loadSubStance("14520");
            kickStance.blendMode = StanceBlendMode.BlendLower;
            console.log("kickStance assetId " + kickStance.assetId);
            // 添加一个按键方法:按下键盘“1”，切换播放瞄准姿态和踢腿姿态
            InputUtil.onKeyDown(Keys.One, () => {
                if(myCharacter.currentSubStance == aimStance) {
                    kickStance.play();
                } else {
                    aimStance.play();
                }
            });
            // 添加一个按键方法:按下键盘“2”，停止播放姿态
            InputUtil.onKeyDown(Keys.Two, () => {
                if(myCharacter.currentSubStance) {
                    myCharacter.currentSubStance.stop();
                }
            });
        }
    }
}
```

___

### stop <Score text="stop" /> 

• **stop**(): `boolean` 

停止这个姿态对象, 并返回执行结果

#### Returns

| `boolean` | 停止结果 |
| :------ | :------ |

::: warning Precautions

停止这个姿态对象, 并返回执行结果. 这个操作是否会自动同步多端, 取决于调用端，服务端广播生效，客户端本地生效。

:::

<span style="font-size: 14px;">
使用示例:将使用到的资源:"94261,14520"拖入优先加载栏。创建一个名为"Example_SubStance_Stop"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，在玩家角色上加载一个仅上半身的瞄准姿态和一个仅下半身的踢腿姿态，按下键盘“1”， 切换播放瞄准姿态和踢腿姿态。你将在场景中看到角色不同姿态的效果。按下键盘“2”， 停止播放姿态。代码如下：
</span>

```ts
@Component
export default class Example_SubStance_Stop extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端玩家
            let myPlayer = Player.localPlayer;
            // 获取玩家控制角色
            let myCharacter = myPlayer.character;
            // 给角色加载仅上半身瞄准姿态
            let aimStance = myCharacter.loadSubStance("94261");
            aimStance.blendMode = StanceBlendMode.BlendUpper;
            console.log("aimStance assetId " + aimStance.assetId);
            // 给角色加载仅下半身踢腿姿态
            let kickStance = myCharacter.loadSubStance("14520");
            kickStance.blendMode = StanceBlendMode.BlendLower;
            console.log("kickStance assetId " + kickStance.assetId);
            // 添加一个按键方法:按下键盘“1”，切换播放瞄准姿态和踢腿姿态
            InputUtil.onKeyDown(Keys.One, () => {
                if(myCharacter.currentSubStance == aimStance) {
                    kickStance.play();
                } else {
                    aimStance.play();
                }
            });
            // 添加一个按键方法:按下键盘“2”，停止播放姿态
            InputUtil.onKeyDown(Keys.Two, () => {
                if(myCharacter.currentSubStance) {
                    myCharacter.currentSubStance.stop();
                }
            });
        }
    }
}
```
