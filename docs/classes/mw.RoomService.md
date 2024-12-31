[服务](../groups/服务.服务.md) / RoomService

# RoomService <Badge type="tip" text="Class" /> <Score text="RoomService" />

MGS以及玩家信息、数据、头像等相关API。
MGS = Meta Game Service, 是编辑器提供给开发者的一些原生服务，如发布游戏后的左上角聊天、好友相关信息服务。

## Table of contents

### Methods <Score text="Methods" /> 
| **[kick](mw.RoomService.md#kick)**(`player`: `number`  [`Player`](mw.Player.md), `message?`: `string`): `void` <Badge type="tip" text="server" />  |
| :-----|
| 将某一玩家踢下线|

## Methods

___

### kick <Score text="kick" /> 

• `Static` **kick**(`player`, `message?`): `void` <Badge type="tip" text="server" />

将某一玩家踢下线

#### Parameters

| `player` `number`  [`Player`](mw.Player.md) |  踢下线的 Player |
| :------ | :------ |
| `message?` `string` |  踢出玩家时触发退出 UI 弹出的信息 default:null range: 提示适合长度的信息即可 |


<span style="font-size: 14px;">
使用示例: 创建一个名为 NewScript 的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，按下 G 键，踢出角色。
</span>

```ts
@Component
export default class NewScript extends Script {

    protected onStart(): void {
        if(SystemUtil.isServer()) {
            Player.spawnDefaultCharacter();
        }

       let player = await mw.Player.asyncGetLocalPlayer();

        if(SystemUtil.isClient()) {
           mw.InputUtil.onKeyDown(Keys.G,()=>{
             mw.Event.dispatchToServer(`AddPlayerPassable`,player);
           })
        }
       if(SystemUtil.isServer()) {
           mw.Event.addClientListener(`AddPlayerPassable`,(player : Player)=>{
              RoomService.kick(player);
           })
        }
   }
}
```
