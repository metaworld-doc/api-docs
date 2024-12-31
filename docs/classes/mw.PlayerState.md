[角色系统](../groups/角色系统.角色系统.md) / PlayerState

# PlayerState <Badge type="tip" text="Class" /> <Score text="PlayerState" />

PlayerState基类

<span style="font-size: 14px;">
使用示例: 创建一个名为"PlayerStateExample"的脚本，放置在对象栏中，打开脚本，输入以下代码保存。把启动参数的玩家数量改为2，运行游戏按下R键将看到其中一个客户端收到test同步。按下P键将打印客户端的test值.
</span>

```ts
  // 服务端每个玩家进入游戏时会自动创建一个实例
  export class GamePlayerState extends mw.PlayerState {

      @Property({replicated: true, onChanged: "onRepTest"})
      test = "";

      onRepTest(path: string[], value: string, oldVal: string) {
          console.log(`onRepTest path: ${path} value: ${value} oldVal: ${oldVal}`);
      }
  }

  @Component
  export default class PlayerStateExample extends mw.Script {

      protected onStart(): void {

          // 按下R建在服务端随机一个玩家修改GamePlayerState的test属性
          InputUtil.onKeyDown(Keys.R, () => this.random());

          // 按下P建打印主控端玩家GamePlayState的test属性
          InputUtil.onKeyDown(Keys.P, () => {
              const playerState = Player.localPlayer.getPlayerState(GamePlayerState);
              console.log(`test: ${playerState.test}`);
          });

      }

      @RemoteFunction(Server)
      random() {
          const players = Player.getAllPlayers();
          // 随机一个玩家
          const luckPlayer = players[Math.floor(Math.random() * players.length)];
          // 获取到GamePlayerState实例
          const playerState = luckPlayer.getPlayerState(GamePlayerState);
          playerState.test = `random: ${ Math.floor(Math.random() * 100)}`;
      }
  }
```

## Hierarchy

- [`Script`](mw.Script.md)

  ↳ **`PlayerState`**

## Table of contents

### Properties <Score text="Properties" /> 

### Accessors <Score text="Accessors" /> 


::: details click
### Accessors <Score text="Accessors" /> 
| **[gameObject](mw.Script.md#gameobject)**(): [`GameObject`](mw.GameObject.md)   |
| :-----|
| 获取脚本挂载的 gameobject|
| **[useUpdate](mw.Script.md#useupdate)**(): `boolean`   |
| 获取脚本是否启用 onUpdate 生命周期函数|
:::


### Methods <Score text="Methods" /> 


::: details click
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
:::


## Properties

## Accessors

## Methods