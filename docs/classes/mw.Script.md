[基类](../groups/基类.基类.md) / Script

# Script <Badge type="tip" text="Class" /> <Score text="Script" />

脚本的基类

-----------------------------

1. 脚本是什么？

挂载的脚本就像是给游戏对象赋予了特殊能力或行为。正如灵魂赋予人类生命和个性一样，脚本赋予游戏对象生命和行为。它们定义了游戏对象的特殊能力、动作模式、智能决策和与玩家的互动方式。

你可以编写脚本来实现角色的控制逻辑，敌人的行为模式，道具的效果，关卡的触发条件等等。通过挂载不同的脚本，你可以赋予对象不同的行为和能力，创造出各种有趣和多样化的游戏。

2. 脚本的分类

可以大致分为两类：

- :mushroom: 继承自 Script 的脚本类，享受编辑器赋予的默认生命周期。

当在编辑器中点击新建脚本时，会默认生成一个继承自 Script 的脚本类：

<span style="font-size: 14px;">
使用示例: 默认脚本格式
</span>

```ts
@Component
export default class GameStart extends Script {

    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {

    }

    // 周期函数 每帧执行
    // 此函数执行需要将this.useUpdate赋值为true
    // @param dt 当前帧与上一帧的延迟 / 秒
    protected onUpdate(dt: number): void {

    }

    // 脚本被销毁时最后一帧执行完调用此函数
    protected onDestroy(): void {

    }
}
```

- :mushroom: 不继承 Script 的其他类。

例如

<span style="font-size: 14px;">
使用示例: 普通类脚本格式
</span>

```ts
export default class PlayerModS extends ModuleS<PlayerModC,null> {

    public net_appleChange(player:Player){

    }
}
export class Person {

}

class Student extends Person {

}
```

3. 脚本是如何工作的？

- :mushroom: 继承自 Script 的脚本类。

继承自 Script 的脚本类可以复写 onStart(), onUpdate(), 和 onDestroy() 方法。当你的脚本放在对象管理器中之后，编辑器会自动帮你调用这些函数。

脚本的生命周期中的 onStart、onUpdate 和 onDestroy 方法可以比喻为一个植物的生长过程：

onStart 为植物的种子开始发芽的过程。当继承自 Script 的脚本放置在游戏对象中，脚本被创建并启动时，onStart 方法会在脚本加载后立即执行。

onUpdate 植物的生长和成熟阶段。在游戏运行期间，onUpdate 方法会在每一帧都被调用，在这个阶段，可以编写逻辑代码来控制游戏对象的行为、状态和与其他对象的交互。

onDestroy 植物的凋谢和结束阶段。当游戏对象被销毁或从场景中移除时，onDestroy 方法会被调用，这个阶段可以用来进行清理工作、释放资源和保存数据，以确保游戏对象的退出过程是正确和完整的。

注：onUpdate函数是在每一帧中调用的，而不是以固定的时间间隔调用。每一帧代表游戏编辑器更新一次的时间单位，其频率取决于游戏的帧率（FPS）。

帧率是指每秒钟渲染的帧数，通常以FPS（Frames Per Second）为单位表示。常见的帧率为60 FPS或30 FPS。如果游戏以60 FPS运行，那么 onUpdate 函数会每帧调用一次，即每秒钟调用60次。同理，如果游戏以30 FPS运行，onUpdate 函数会每秒钟调用30次。

需要注意的是，帧率可能受到游戏的复杂度、场景中的物体数量、图形效果和计算负荷等因素的影响。如果游戏性能下降，帧率可能会下降，从而导致 onUpdate 函数的调用频率减少。因此，不能假设 onUpdate 函数在固定时间间隔内调用，而应该将其视为每帧都会被调用的函数。

- :mushroom: 不继承 Script 的其他类。

## Hierarchy

- [`Base`](mw.Base.md)

  ↳ **`Script`**

  ↳↳ [`PlayerState`](mw.PlayerState.md)

## Table of contents

### Properties <Score text="Properties" /> 


::: details click
### Properties <Score text="Properties" /> 
| **[onPropertyChange](mw.Base.md#onpropertychange)**: `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\>  |
| :-----|
| 监听系统属性同步事件|
:::


### Accessors <Score text="Accessors" /> 
| **[gameObject](mw.Script.md#gameobject)**(): [`GameObject`](mw.GameObject.md)   |
| :-----|
| 获取脚本挂载的 gameobject|
| **[useUpdate](mw.Script.md#useupdate)**(): `boolean`   |
| 获取脚本是否启用 onUpdate 生命周期函数|

### Methods <Score text="Methods" /> 
| **[destroy](mw.Script.md#destroy)**(): `void` <Badge type="tip" text="server" />  |
| :-----|
| 销毁组件对象|
| **[onActivate](mw.Script.md#onactivate)**(): `void`   |
| 生命周期函数 - target 激活时调用|
| **[onDeactivate](mw.Script.md#ondeactivate)**(): `void`   |
| 生命周期函数 - target 禁用时调用|
| **[onDestroy](mw.Script.md#ondestroy)**(): `void`   |
| 生命周期函数 - 被销毁时调用|
| **[onReplicated](mw.Script.md#onreplicated)**(`path`: `string`, `value`: `unknown`, `oldVal`: `unknown`): `boolean`  `void`   |
| 属性被同步事件 ClientOnly|
| **[onStart](mw.Script.md#onstart)**(): `void`   |
| 生命周期函数 - 脚本开始执行时调用|
| **[onUpdate](mw.Script.md#onupdate)**(`dt`: `number`): `void`   |
| 生命周期函数 - 每帧执行函数|


::: details click
### Methods <Score text="Methods" /> 
| **[getPropertyChangeDelegate](mw.Base.md#getpropertychangedelegate)**(`property`): `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> <Badge type="tip" text="client" />  |
| :-----|
| 获取给定对象属性修改时触发的事件代理。|
:::


## Properties

## Accessors

### gameObject <Score text="gameObject" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **gameObject**(): [`GameObject`](mw.GameObject.md) 

</th>
<th style="text-align: left">

• `set` **gameObject**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取脚本挂载的 gameobject

#### Returns

| [`GameObject`](mw.GameObject.md) | 挂载游戏对象 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置脚本挂载的 gameobject 对象

#### Parameters

| `value` [`GameObject`](mw.GameObject.md) | 传入挂载对象 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### useUpdate <Score text="useUpdate" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **useUpdate**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **useUpdate**(`v`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取脚本是否启用 onUpdate 生命周期函数

#### Returns

| `boolean` | 默认为关闭状态，需要手动开启 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置脚本是否启用 onUpdate 生命周期函数

#### Parameters

| `v` `boolean` |  true 开启 false 关闭 |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods

### destroy <Score text="destroy" /> 

• **destroy**(): `void` <Badge type="tip" text="server" />

销毁组件对象


___

### onActivate <Score text="onActivate" /> 

• `Protected` **onActivate**(): `void` 

生命周期函数 - target 激活时调用


___

### onDeactivate <Score text="onDeactivate" /> 

• `Protected` **onDeactivate**(): `void` 

生命周期函数 - target 禁用时调用


___

### onDestroy <Score text="onDestroy" /> 

• `Protected` **onDestroy**(): `void` 

生命周期函数 - 被销毁时调用


___

### onReplicated <Score text="onReplicated" /> 

• `Protected` **onReplicated**(`path`, `value`, `oldVal`): `boolean`  `void` 

属性被同步事件 ClientOnly

#### Parameters

| `path` `string` | 属性路径 range: 依据路径长度而定 |
| :------ | :------ |
| `value` `unknown` | 属性值 |
| `oldVal` `unknown` | 同步前的值 |

#### Returns

| `boolean`  `void` | 同步结果 |
| :------ | :------ |

___

### onStart <Score text="onStart" /> 

• `Protected` **onStart**(): `void` 

生命周期函数 - 脚本开始执行时调用


___

### onUpdate <Score text="onUpdate" /> 

• `Protected` **onUpdate**(`dt`): `void` 

生命周期函数 - 每帧执行函数

#### Parameters

| `dt` `number` | 与上一帧的延迟 单位:秒 <br> range: dt 的大小会根据游戏性能发生变化，游戏性能下降，帧率可能会下降，从而导致 onUpdate 函数的调用频率减少。（详情请看类开头描述） type:浮点类型数值 |
| :------ | :------ |


setUpdate 设置为 true 后，每帧被执行，设置为false，不会执行
