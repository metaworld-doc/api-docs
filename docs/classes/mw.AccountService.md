[服务](../groups/服务.服务.md) / AccountService

# AccountService <Badge type="tip" text="Class" /> <Score text="AccountService" />

用户账号信息管理服务

## Table of contents

### Methods <Score text="Methods" /> 
| **[addFriend](mw.AccountService.md#addfriend)**(`resp`: [`MGSResponse`](../modules/Core.mw.md#mgsresponse), `userId`: `string`, `reason`: `string`): `void` <Badge type="tip" text="client" />  |
| :-----|
| 发起添加好友请求|
| **[applySharedId](mw.AccountService.md#applysharedid)**(`character`: [`Character`](mw.Character.md), `id`: `string`, `callback`: [`BoolResponse`](../modules/Core.mw.md#boolresponse)): `void` <Badge type="tip" text="client" />  |
| 应用分享Id的角色数据|
| **[checkVIP](mw.AccountService.md#checkvip)**(`userId`: `string`, `gameId`: `string`, `callback`: (`result`: `string`) => `void`): `void` <Badge type="tip" text="client" />  |
| 发起checkVIP并获得回调，查询玩家的vip信息|
| **[createSharedId](mw.AccountService.md#createsharedid)**(`character`: [`Character`](mw.Character.md), `callback`: [`StringResponse`](../modules/Core.mw.md#stringresponse)): `void` <Badge type="tip" text="client" />  |
| 生成分享Id|
| **[dataShowToOther](mw.AccountService.md#datashowtoother)**(`index`: `number`, `isOpen`: `boolean`, `callback?`: [`BoolResponse`](../modules/Core.mw.md#boolresponse)): `void` <Badge type="tip" text="client" />  |
| 设置数据是否公开给其他用户|
| **[downloadData](mw.AccountService.md#downloaddata)**(`character`: [`Character`](mw.Character.md), `callback?`: [`BoolResponse`](../modules/Core.mw.md#boolresponse)  [`VoidResponse`](../modules/Core.mw.md#voidresponse), `index?`: `number`): `void` <Badge type="tip" text="client" />  |
| 下载角色形象并应用到当前角色身上|
| **[fillAvatar](mw.AccountService.md#fillavatar)**(`img`: [`Image`](mw.Image.md)): `void` <Badge type="tip" text="client" />  |
| 将头像赋值到Image变量上|
| **[getNickName](mw.AccountService.md#getnickname)**(): `string` <Badge type="tip" text="client" />  |
| 获取玩家昵称|
| **[getUserData](mw.AccountService.md#getuserdata)**(`userId`: `string`, `index`: `number`, `callback`: [`StringResponse`](../modules/Core.mw.md#stringresponse)): `void` <Badge type="tip" text="client" />  |
| 获取用户存储在服务器上的角色形象数据|
| **[getUserId](mw.AccountService.md#getuserid)**(): `string` <Badge type="tip" text="client" />  |
| 获取平台的用户Id,可以用于getUserData接口|
| **[getUserInfo](mw.AccountService.md#getuserinfo)**(`userId`: `string`, `gameId`: `string`, `callback`: (`nickname`: `string`, `gender`: `number`) => `void`): `void` <Badge type="tip" text="client" />  |
| 发起getUserInfo并获得回调，查询玩家的昵称、性别|
| **[isFriend](mw.AccountService.md#isfriend)**(`resp`: [`MGSResponse`](../modules/Core.mw.md#mgsresponse), `userId`: `string`): `void` <Badge type="tip" text="client" />  |
| 若需要检测玩家是否好友关系，可通过调用isFriend接口进行查看|
| **[setUserData](mw.AccountService.md#setuserdata)**(`character`: [`Character`](mw.Character.md), `dataString`: `string`, `callback?`: [`BoolResponse`](../modules/Core.mw.md#boolresponse)): `void` <Badge type="tip" text="client" />  |
| 将角色形象数据应用至角色|
| **[uploadData](mw.AccountService.md#uploaddata)**(`character`: [`Character`](mw.Character.md), `callback?`: [`BoolResponse`](../modules/Core.mw.md#boolresponse)  [`VoidResponse`](../modules/Core.mw.md#voidresponse), `index?`: `number`, `openStatus?`: `number`): `void` <Badge type="tip" text="client" />  |
| 上传角色形象资源到服务器  Character，Hair, UpperCloth, LowerCloth, Gloves, Shoe|

## Methods

### addFriend <Score text="addFriend" /> 

• `Static` **addFriend**(`resp`, `userId`, `reason`): `void` <Badge type="tip" text="client" />

发起添加好友请求

#### Parameters

| `resp` [`MGSResponse`](../modules/Core.mw.md#mgsresponse) | GameService的回调 |
| :------ | :------ |
| `userId` `string` | 要加的玩家UserId range: 无 |
| `reason` `string` | 申请理由 range: 无 |


::: warning Precautions

1. 只在移动端生效
2. 查询的目标玩家需要和当前玩家在同一房间。否则返回的数据会是"参数格式不正确"。

:::

___

### applySharedId <Score text="applySharedId" /> 

• `Static` **applySharedId**(`character`, `id`, `callback`): `void` <Badge type="tip" text="client" />

应用分享Id的角色数据

#### Parameters

| `character` [`Character`](mw.Character.md) | 分享换装数据的角色 |
| :------ | :------ |
| `id` `string` | 分享Id range: 无 |
| `callback` [`BoolResponse`](../modules/Core.mw.md#boolresponse) |  回调参数，true:应用成功；false:应用失败 |


___

### checkVIP <Score text="checkVIP" /> 

• `Static` **checkVIP**(`userId`, `gameId`, `callback`): `void` <Badge type="tip" text="client" />

发起checkVIP并获得回调，查询玩家的vip信息

#### Parameters

| `userId` `string` | 玩家UserId range: 无 |
| :------ | :------ |
| `gameId` `string` | GameId range: 无 |
| `callback` (`result`: `string`) => `void` | 返回 result，玩家的vip是否正常 |


::: warning Precautions

1. 只在移动端生效
2. 查询的目标玩家需要和当前玩家在同一房间。否则返回的数据会是"参数格式不正确"。

:::

___

### createSharedId <Score text="createSharedId" /> 

• `Static` **createSharedId**(`character`, `callback`): `void` <Badge type="tip" text="client" />

生成分享Id

#### Parameters

| `character` [`Character`](mw.Character.md) | 分享换装数据的角色 |
| :------ | :------ |
| `callback` [`StringResponse`](../modules/Core.mw.md#stringresponse) |  回调参数，返回生成的Id |


___

### dataShowToOther <Score text="dataShowToOther" /> 

• `Static` **dataShowToOther**(`index`, `isOpen`, `callback?`): `void` <Badge type="tip" text="client" />

设置数据是否公开给其他用户

#### Parameters

| `index` `number` | 角色资源位 default:0（主角资源位） range: [0,5] type: 整形 |
| :------ | :------ |
| `isOpen` `boolean` | 是否公开 |
| `callback?` [`BoolResponse`](../modules/Core.mw.md#boolresponse) | 设置是否成功的回调 default:无 |


___

### downloadData <Score text="downloadData" /> 

• `Static` **downloadData**(`character`, `callback?`, `index?`): `void` <Badge type="tip" text="client" />

下载角色形象并应用到当前角色身上

#### Parameters

| `character` [`Character`](mw.Character.md) | 要应用换装数据的角色 |
| :------ | :------ |
| `callback?` [`BoolResponse`](../modules/Core.mw.md#boolresponse)  [`VoidResponse`](../modules/Core.mw.md#voidresponse) | 设置是否成功的回调 default:默认没有回调 |
| `index?` `number` | 角色资源位 default:0（主角资源位） range: [0,5] type: 整形 |


___

### fillAvatar <Score text="fillAvatar" /> 

• `Static` **fillAvatar**(`img`): `void` <Badge type="tip" text="client" />

将头像赋值到Image变量上

#### Parameters

| `img` [`Image`](mw.Image.md) | 需要赋值获得头像的Image变量 |
| :------ | :------ |


::: warning Precautions

只在移动端生效

:::

<span style="font-size: 14px;">
使用示例:创建一个名为AccountExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，会在屏幕右上方显示用户的头像，PC环境下为白图
</span>

```ts
@Component
export default class AccountExample extends Script {

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        this.test();
    }

    private async test(): Promise<void> {
        let imgUI = new ImageUI();
        AccountService.fillAvatar(imgUI.image);
    }

}

class ImageUI {
    public image: mw.Image;

    constructor() {
        this.creatUI();
    }

    private creatUI() {
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
        this.image = mw.Image.newObject(rootCanvas);
        this.image.position = new Vector2(1700, 310);
        this.image.size = new Vector2(150, 50);
        this.image.visibility = SlateVisibility.Visible;
    }
}
```

___

### getNickName <Score text="getNickName" /> 

• `Static` **getNickName**(): `string` <Badge type="tip" text="client" />

获取玩家昵称

#### Returns

| `string` | 昵称 |
| :------ | :------ |

::: warning Precautions

只在移动端生效

:::

<span style="font-size: 14px;">
使用示例:创建一个名为AccountExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，控制窗口会输出用户的昵称,PC环境下为空
</span>

```ts
@Component
export default class AccountExample extends Script {

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        this.test();
    }

    private async test(): Promise<void> {
        let name = AccountService.getNickName();
        console.log("获取玩家昵称", name);
    }

}
```

___

### getUserData <Score text="getUserData" /> 

• `Static` **getUserData**(`userId`, `index`, `callback`): `void` <Badge type="tip" text="client" />

获取用户存储在服务器上的角色形象数据

#### Parameters

| `userId` `string` | 用户Id range: 无 |
| :------ | :------ |
| `index` `number` | 角色资源位 default:0（主角资源位） range: [0,5] type: 整形 |
| `callback` [`StringResponse`](../modules/Core.mw.md#stringresponse) | 返回获取的数据string. |


<span style="font-size: 14px;">
使用示例:创建一个名为AccountExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，发布在真机上运行游戏，会看到一个和玩家形象一致的人形对象
</span>

```ts
@Component
export default class AccountExample extends Script {

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        this.test();
    }

    private async test(): Promise<void> {
        let player = await Player.asyncGetLocalPlayer();
        let npc = (await GameObject.asyncSpawn({ guid: "NPC" })) as Character;
        npc.worldTransform.position = new Vector(0, 0, 200);
        AccountService.getUserData(player.userId, 0, async str => {
            await TimeUtil.delaySecond(5);
            AccountService.setUserData(npc, str, isSuccess => {
                player.character.name = isSuccess ? "成功" : "失败";
            })
        });
    }
}
```

___

### getUserId <Score text="getUserId" /> 

• `Static` **getUserId**(): `string` <Badge type="tip" text="client" />

获取平台的用户Id,可以用于getUserData接口

#### Returns

| `string` | 用户Id |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为AccountExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，控制窗口会输出用户的UserId
</span>

```ts
@Component
export default class AccountExample extends Script {

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        this.test();
    }

    private async test(): Promise<void> {
        let userId = AccountService.getUserId();
        console.log("获取平台的用户Id", userId);
    }
}
```

___

### getUserInfo <Score text="getUserInfo" /> 

• `Static` **getUserInfo**(`userId`, `gameId`, `callback`): `void` <Badge type="tip" text="client" />

发起getUserInfo并获得回调，查询玩家的昵称、性别

#### Parameters

| `userId` `string` | 玩家UserId range: 无 |
| :------ | :------ |
| `gameId` `string` | GameId range: 无 |
| `callback` (`nickname`: `string`, `gender`: `number`) => `void` | 返回 nickname(string) 和 gender(number) |


::: warning Precautions

1. 只在移动端生效
2. 查询的目标玩家需要和当前玩家在同一房间。否则返回的数据会是"参数格式不正确"。

:::

___

### isFriend <Score text="isFriend" /> 

• `Static` **isFriend**(`resp`, `userId`): `void` <Badge type="tip" text="client" />

若需要检测玩家是否好友关系，可通过调用isFriend接口进行查看

#### Parameters

| `resp` [`MGSResponse`](../modules/Core.mw.md#mgsresponse) | GameService的回调。在收到结果时会触发该回调，参数含义如下： - isSuccess - 正常获取到了查询结果即为true，并不代表为好友关系。false表示请求出错。 - jsonData - 当userId对应的角色和当前玩家不在同一房间，返回值为"参数格式不正确"； 当userId对应的角色和当前玩家在同一房间，且互为好友，返回值为"true"； 当userId对应的角色和当前玩家在同一房间，不为好友，返回值为"false"； |
| :------ | :------ |
| `userId` `string` | 要确定的玩家UserId range: 无 |


::: warning Precautions

1. 只在移动端生效
2. 查询的目标玩家需要和当前玩家在同一房间。否则返回的数据会是"参数格式不正确"。

:::

___

### setUserData <Score text="setUserData" /> 

• `Static` **setUserData**(`character`, `dataString`, `callback?`): `void` <Badge type="tip" text="client" />

将角色形象数据应用至角色

#### Parameters

| `character` [`Character`](mw.Character.md) |  用于换装的角色 |
| :------ | :------ |
| `dataString` `string` |  返回的数据 range: 无 |
| `callback?` [`BoolResponse`](../modules/Core.mw.md#boolresponse) | 设置是否成功的回调 default:无回调 |


<span style="font-size: 14px;">
使用示例:创建一个名为AccountExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，发布在真机上运行游戏，会看到一个和玩家形象一致的人形对象
</span>

```ts
@Component
export default class AccountExample extends Script {

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        this.test();
    }

    private async test(): Promise<void> {
        let player = await Player.asyncGetLocalPlayer();
        let npc = (await GameObject.asyncSpawn({ guid: "NPC" })) as Character;
        npc.worldTransform.position = new Vector(0, 0, 200);
        AccountService.getUserData(player.userId, 0, async str => {
            await TimeUtil.delaySecond(5);
            AccountService.setUserData(npc, str, isSuccess => {
                player.character.name = isSuccess ? "成功" : "失败";
            })
        });
    }
}
```

___

### uploadData <Score text="uploadData" /> 

• `Static` **uploadData**(`character`, `callback?`, `index?`, `openStatus?`): `void` <Badge type="tip" text="client" />

上传角色形象资源到服务器  Character，Hair, UpperCloth, LowerCloth, Gloves, Shoe

#### Parameters

| `character` [`Character`](mw.Character.md) | 要上传换装数据的角色 |
| :------ | :------ |
| `callback?` [`BoolResponse`](../modules/Core.mw.md#boolresponse)  [`VoidResponse`](../modules/Core.mw.md#voidresponse) | 设置是否成功的回调 default:默认没有回调 |
| `index?` `number` | 角色资源位 default:0（主角资源位） range: [0,5] type: 整形 |
| `openStatus?` `number` | 开放状态 default:1,默认是开放状态 range: [0,1] type: 整形 |

