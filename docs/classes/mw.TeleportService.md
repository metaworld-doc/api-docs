[服务](../groups/服务.服务.md) / TeleportService

# TeleportService <Badge type="tip" text="Class" /> <Score text="TeleportService" />

多场景和传送服务

## Table of contents

### Methods <Score text="Methods" /> 
| **[asyncGetPlayerRoomInfo](mw.TeleportService.md#asyncgetplayerroominfo)**(`userId`: `string`): `Promise`<[`RoomInfo`](../interfaces/mw.RoomInfo.md)\>   |
| :-----|
| 获取指定玩家所在的房间信息|
| **[asyncTeleportToRoom](mw.TeleportService.md#asyncteleporttoroom)**(`roomId`: `string`, `userIds`: `string`[], `options?`: [`TeleportOptions`](../interfaces/mw.TeleportOptions.md)): `Promise`<[`TeleportResult`](../interfaces/mw.TeleportResult.md)\> <Badge type="tip" text="server" />  |
| 异步传送到指定房间|
| **[asyncTeleportToScene](mw.TeleportService.md#asyncteleporttoscene)**(`sceneName`: `string`, `userIds`: `string`[], `options?`: [`TeleportOptions`](../interfaces/mw.TeleportOptions.md)): `Promise`<[`TeleportResult`](../interfaces/mw.TeleportResult.md)\> <Badge type="tip" text="server" />  |
| 异步传送到当前游戏的指定场景|
| **[getSourceInfo](mw.TeleportService.md#getsourceinfo)**(`teleportId`: `string`): [`RoomInfo`](../interfaces/mw.RoomInfo.md) <Badge type="tip" text="server" />  |
| 获取传送的来源信息|
| **[getTeleportData](mw.TeleportService.md#getteleportdata)**(`teleportId`: `string`): [`TeleportData`](../modules/Core.mw.md#teleportdata) <Badge type="tip" text="server" />  |
| 获取调用传送接口时在TeleportOptions中设置的数据|

## Methods

### asyncGetPlayerRoomInfo <Score text="asyncGetPlayerRoomInfo" /> 

• `Static` **asyncGetPlayerRoomInfo**(`userId`): `Promise`<[`RoomInfo`](../interfaces/mw.RoomInfo.md)\> 

获取指定玩家所在的房间信息

#### Parameters

| `userId` `string` | 目标玩家的userId range: 无 |
| :------ | :------ |

#### Returns

| `Promise`<[`RoomInfo`](../interfaces/mw.RoomInfo.md)\> | 指定玩家所在的房间信息 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为"ServerScript"的脚本，放在场景中。代码如下：
</span>

```ts
@Component
export default class Server extends Script {
    protected onStart(): void {
        // 传送功能需要在服务端发起，在客户端使用会报错
        if (SystemUtil.isServer()) {
            Player.onPlayerJoin.add((player: Player) => {
                // 当玩家加入时，倒计时5s后发起传送
                setTimeout(() => {
                    // 假定我们想传送到UserId为"123456"的玩家所在房间一起游玩
                    const targetUserId: string = "123456";
                    // 先用asyncGetPlayerRoomInfo获取玩家所在的房间信息
                    TeleportService.asyncGetPlayerRoomInfo(targetUserId).then((roomInfo) => {
                        // 拿到RoomId
                        const roomId: string = roomInfo.roomId;
                        // 将要传送到新场景的玩家加入数组
                        const playerToTeleport: string[] = [player.userId];
                        // 可以填充要携带的额外数据
                        const opt: TeleportOptions = {
                            teleportData: "This is test data."
                        }
                        // 调用接口传送到目标房间
                        TeleportService.asyncTeleportToRoom(roomId, playerToTeleport, opt);
                    });
                }, 5 * 1000);
            });
        }
    }
}
```

___

### asyncTeleportToRoom <Score text="asyncTeleportToRoom" /> 

• `Static` **asyncTeleportToRoom**(`roomId`, `userIds`, `options?`): `Promise`<[`TeleportResult`](../interfaces/mw.TeleportResult.md)\> <Badge type="tip" text="server" />

异步传送到指定房间

#### Parameters

| `roomId` `string` | 要传送的目标游戏Id range: 无 |
| :------ | :------ |
| `userIds` `string`[] | 要传送的玩家userId数组 |
| `options?` [`TeleportOptions`](../interfaces/mw.TeleportOptions.md) | 可选的额外传送信息. 不支持 createNewPrivateRoom 参数，设置为true也不会创建新房间 default:undefined |

#### Returns

| `Promise`<[`TeleportResult`](../interfaces/mw.TeleportResult.md)\> | 本次请求正常则返回resolve，异常则返回reject |
| :------ | :------ |

::: warning Precautions

指定房间不存在或者可容纳人数不足，则会失败。参与传送的玩家数量越多，失败率越高

:::

::: warning Precautions

不支持 createNewPrivateRoom 参数，设置为true也不会创建新房间

:::

<span style="font-size: 14px;">
使用示例:创建一个名为"TeleportScript"的脚本，放在场景中，设置为双端。代码如下：
</span>

```ts
@Component
export default class TeleportScript extends Script {
    protected onStart(): void {
        // 服务端逻辑
        if (SystemUtil.isServer()) {
            Player.onPlayerJoin.add((player: Player) => {
                // 当玩家加入时，倒计时5s后发起传送，避免玩家加入立即传送，不易观察
                setTimeout(() => {
                    // 假定我们想传送到UserId为"123456"的玩家所在房间一起游玩
                    const targetUserId: string = "123456";
                    // 先用asyncGetPlayerRoomInfo获取玩家所在的房间信息
                    TeleportService.asyncGetPlayerRoomInfo(targetUserId).then((roomInfo) => {
                        // 拿到RoomId
                        const roomId: string = roomInfo.roomId;
                        // 将要传送到新场景的玩家加入数组
                        const playerToTeleport: string[] = [player.userId];
                        // 可以填充要携带的额外数据
                        const opt: TeleportOptions = {
                            teleportData: "This is test data."
                        }

                        // 声明成功和失败的回调函数，用于处理传送接口的回调结果。
                        // 成功的情况一般不需要处理，会继续走后续跳转流程。
                        // 如果失败了，有可能是超时或者有报错，可以从回调的数据中读取信息做进一步处理。
                        const onSuccess = () => { }
                        const onFailed = (result: mw.TeleportResult) => {
                            switch (result.status) {
                                case mw.TeleportStatus.success:
                                    break;
                                case mw.TeleportStatus.ignored:
                                    // 触发太频繁了，本次请求被忽略
                                    break;
                                case mw.TeleportStatus.timeout:
                                    // 超时了，可以选择重试传送或者提示玩家
                                    break;
                                case mw.TeleportStatus.error:
                                    // 将错误信息发给所有参与的客户端
                                    for (const userId in result.userIds) {
                                        const player = Player.getPlayer(userId)
                                        if (player) {
                                            Event.dispatchToClient(player, "TeleportResult", result);
                                        }
                                    }
                            }
                        };

                        // 传送功能需要在服务端发起，在客户端使用会报错
                        TeleportService.asyncTeleportToRoom(roomId, playerToTeleport, opt).then(onSuccess, onFailed);
                    }).catch((error: Error) => {
                        console.error(`getPlayerRoomInfo has error: ${error.message}`);
                    })
                }, 5 * 1000);
            });
        } else {
            // 客户端逻辑
            Event.addServerListener("TeleportResult", (result: mw.TeleportResult) => {
                console.error(`Teleport has error:`);
                console.error(`errorCode: ${result.errorCode}`);
                console.error(`message: ${result.message}`);
            });
        }
    }
}
```

___

### asyncTeleportToScene <Score text="asyncTeleportToScene" /> 

• `Static` **asyncTeleportToScene**(`sceneName`, `userIds`, `options?`): `Promise`<[`TeleportResult`](../interfaces/mw.TeleportResult.md)\> <Badge type="tip" text="server" />

异步传送到当前游戏的指定场景

#### Parameters

| `sceneName` `string` | 要传送的目标场景名称 range: 无 |
| :------ | :------ |
| `userIds` `string`[] | 要传送的玩家 userId 数组 |
| `options?` [`TeleportOptions`](../interfaces/mw.TeleportOptions.md) | 可选的额外传送信息 default:undefined |

#### Returns

| `Promise`<[`TeleportResult`](../interfaces/mw.TeleportResult.md)\> | 本次请求正常则返回resolve，异常则返回reject |
| :------ | :------ |

::: warning Precautions

仅限当前游戏的场景间传送，场景名不存在则会传送失败

:::

<span style="font-size: 14px;">
使用示例:在编辑器中创建了一个名为"Scene1"的场景。创建一个名为"TeleportScript"的脚本，放在场景中，设置为双端。代码如下：
</span>

```ts
@Component
export default class TeleportScript extends Script {
    protected onStart(): void {
        // 服务端逻辑
        if (SystemUtil.isServer()) {
            Player.onPlayerJoin.add((player: Player) => {
                // 当玩家加入时，倒计时5s后发起传送，避免玩家加入立即传送，不易观察
                setTimeout(() => {
                    // 假定已经在编辑器中创建了一个名为"Scene1"的场景
                    const sceneName: string = "Scene1";
                    // 将要传送到新场景的玩家加入数组
                    const playerToTeleport: string[] = [player.userId];
                    // 可以填充要携带的额外数据
                    const opt: TeleportOptions = {
                        teleportData: "This is test data."
                    }

                    // 声明成功和失败的回调函数，用于处理传送接口的回调结果。
                    // 成功的情况一般不需要处理，会继续走后续跳转流程。
                    // 如果失败了，有可能是超时或者有报错，可以从回调的数据中读取信息做进一步处理。
                    const onSuccess = () => { }
                    const onFailed = (result: mw.TeleportResult) => {
                        switch (result.status) {
                            case mw.TeleportStatus.success:
                                break;
                            case mw.TeleportStatus.ignored:
                                // 触发太频繁了，本次请求被忽略
                                break;
                            case mw.TeleportStatus.timeout:
                                // 超时了，可以选择重试传送或者提示玩家
                                break;
                            case mw.TeleportStatus.error:
                                // 将错误信息发给所有参与的客户端
                                for (const userId in result.userIds) {
                                    const player = Player.getPlayer(userId)
                                    if (player) {
                                        Event.dispatchToClient(player, "TeleportResult", result);
                                    }
                                }
                        }
                    };

                    // 传送功能需要在服务端发起，在客户端使用会报错
                    TeleportService.asyncTeleportToScene(sceneName, playerToTeleport, opt).then(onSuccess, onFailed);
                }, 5 * 1000);
            });
        } else {
            // 客户端逻辑
            Event.addServerListener("TeleportResult", (result: mw.TeleportResult) => {
                console.error(`Teleport has error:`);
                console.error(`errorCode: ${result.errorCode}`);
                console.error(`message: ${result.message}`);
            });
        }
    }
}
```

___

### getSourceInfo <Score text="getSourceInfo" /> 

• `Static` **getSourceInfo**(`teleportId`): [`RoomInfo`](../interfaces/mw.RoomInfo.md) <Badge type="tip" text="server" />

获取传送的来源信息

#### Parameters

| `teleportId` `string` | 要查询的传送Id range: 无 |
| :------ | :------ |

#### Returns

| [`RoomInfo`](../interfaces/mw.RoomInfo.md) | 玩家传送的来源信息 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为"ServerScript"的脚本，放在场景中。代码如下：
</span>

```ts
@Component
export default class Server extends Script {
    protected onStart(): void {
        // 获取传送来源信息的接口需要在服务端发起，在客户端使用会报错
        if (SystemUtil.isServer()) {
            Player.onPlayerJoin.add((player: Player) => {
                // 用玩家的teleportId属性来查询来源信息
                const sourceInfo = TeleportService.getSourceInfo(player.teleportId);
                if (sourceInfo) {
                    console.log("Teleport from:");
                    console.log(`GameId: ${sourceInfo.gameId}`);
                    console.log(`RoomId: ${sourceInfo.roomId}`);
                } else {
                    // 不是传送进入的当前场景，则没有来源信息
                    console.log("Not join by Teleport.")
                }
            });
        }
    }
}
```

___

### getTeleportData <Score text="getTeleportData" /> 

• `Static` **getTeleportData**(`teleportId`): [`TeleportData`](../modules/Core.mw.md#teleportdata) <Badge type="tip" text="server" />

获取调用传送接口时在TeleportOptions中设置的数据

#### Parameters

| `teleportId` `string` | 要查询的传送Id range: 无 |
| :------ | :------ |

#### Returns

| [`TeleportData`](../modules/Core.mw.md#teleportdata) | 传送时携带的数据 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为"ServerScript"的脚本，放在场景中。代码如下：
</span>

```ts
@Component
export default class Server extends Script {
    protected onStart(): void {
        // 获取传送时携带的数据的接口需要在服务端发起，在客户端使用会报错
        if (SystemUtil.isServer()) {
            Player.onPlayerJoin.add((player: Player) => {
                // 用玩家的teleportId属性来查询传送时携带的数据
                const data = TeleportService.getTeleportData(player.teleportId);
                if (data) {
                    console.log(`Teleport data: ${data}`);
                } else {
                    // 不是传送进入的当前场景，则没有携带的数据；也可能是传送时未指定数据
                    console.log("Not join by Teleport or no data.")
                }
            });
        }
    }
}
```
