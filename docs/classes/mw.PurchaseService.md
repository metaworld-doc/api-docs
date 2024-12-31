[服务](../groups/服务.服务.md) / PurchaseService

# PurchaseService <Badge type="tip" text="Class" /> <Score text="PurchaseService" />

应用内购服务

## Table of contents

### Accessors <Score text="Accessors" /> 
| **[onArkBalanceUpdated](mw.PurchaseService.md#onarkbalanceupdated)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<[`OnArkBalanceUpdated`](../modules/Core.mw.md#onarkbalanceupdated)\> <Badge type="tip" text="client" />  |
| :-----|
| 获取 Ark 币余额更新的委托|
| **[onOrderDelivered](mw.PurchaseService.md#onorderdelivered)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<[`OnOrderDelivered`](../modules/Core.mw.md#onorderdelivered)\> <Badge type="tip" text="server" />  |
| 获取订单发货的委托|
| **[onPremiumMemberOrderDelivered](mw.PurchaseService.md#onpremiummemberorderdelivered)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<[`OnKeyConsume`](../modules/Core.mw.md#onkeyconsume)\> <Badge type="tip" text="server" />  |
| 获取订单发货的委托|
| **[onPremiumMemberStatusUpdate](mw.PurchaseService.md#onpremiummemberstatusupdate)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`result`: `boolean`) => `void`\> <Badge type="tip" text="client" />  |
| 获取大会员状态更新时触发的委托|

### Methods <Score text="Methods" /> 
| **[consumeKey](mw.PurchaseService.md#consumekey)**(`boxId`: `string`, `number`: `number`, `keyType`: `number`, `placeOrderResult`: (`status`: [`consumeKeyStatus`](../enums/mw.consumeKeyStatus.md)) => `void`): `void` <Badge type="tip" text="client" />  |
| :-----|
| 大会员开宝箱消耗金钥匙|
| **[findKeyUsageHistory](mw.PurchaseService.md#findkeyusagehistory)**(`currentPage`: `number`, `pageSize`: `number`, `historyResult`: (`total`: `number`, `currentPage`: `number`, `bill`: [`keyUsageInfo`](../modules/Core.mw.md#keyusageinfo)[]) => `void`): `void`   |
| 分页查询大会员使用钥匙的历史记录|
| **[getArkBalance](mw.PurchaseService.md#getarkbalance)**(): `void` <Badge type="tip" text="client" />  |
| 获取代币余额|
| **[getUserKeyNumber](mw.PurchaseService.md#getuserkeynumber)**(`[getUserKeyNumber](mw.PurchaseService.md#getuserkeynumber)Result`, `keyType?`: `number`): `void` <Badge type="tip" text="client" />  |
| 获取用户剩余钥匙数量|
| **[isPremiumMember](mw.PurchaseService.md#ispremiummember)**(`[isPremiumMember](mw.PurchaseService.md#ispremiummember)Result`): `void` <Badge type="tip" text="client" />  |
| 获取用户是否是大会员|
| **[isPremiumMemberSupported](mw.PurchaseService.md#ispremiummembersupported)**(`isSupportedResult`: (`result`: `boolean`) => `void`): `void` <Badge type="tip" text="client" />  |
| 获取用户使用软件版本是否有大会员功能|
| **[openPremiumMemberPurchasePage](mw.PurchaseService.md#openpremiummemberpurchasepage)**(): `void` <Badge type="tip" text="client" />  |
| 跳转会员充值页面|
| **[placeOrder](mw.PurchaseService.md#placeorder)**(`commodityId`: `string`, `amount`: `number`, `[placeOrder](mw.PurchaseService.md#placeorder)Result`): `void` <Badge type="tip" text="client" />  |
| 下单指定数量的指定商品|
| **[redeemGiftCode](mw.PurchaseService.md#redeemgiftcode)**(`player`: [`Player`](mw.Player.md), `GiftCode`: `string`, `redeemCallback`: (`result`: [`RedeemResponse`](../modules/Core.mw.md#redeemresponse)) => `void`): `void` <Badge type="tip" text="server" />  |
| 礼包码兑换|

## Accessors

### onArkBalanceUpdated <Score text="onArkBalanceUpdated" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **onArkBalanceUpdated**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<[`OnArkBalanceUpdated`](../modules/Core.mw.md#onarkbalanceupdated)\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取 Ark 币余额更新的委托

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<[`OnArkBalanceUpdated`](../modules/Core.mw.md#onarkbalanceupdated)\> | 代币余额更新的委托 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onOrderDelivered <Score text="onOrderDelivered" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **onOrderDelivered**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<[`OnOrderDelivered`](../modules/Core.mw.md#onorderdelivered)\> <Badge type="tip" text="server" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取订单发货的委托

::: warning Precautions

仅在服务端有效。暂未考虑单机模式，使用需谨慎

:::

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<[`OnOrderDelivered`](../modules/Core.mw.md#onorderdelivered)\> | 订单发货的委托 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onPremiumMemberOrderDelivered <Score text="onPremiumMemberOrderDelivered" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **onPremiumMemberOrderDelivered**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<[`OnKeyConsume`](../modules/Core.mw.md#onkeyconsume)\> <Badge type="tip" text="server" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取订单发货的委托

::: warning Precautions

仅在服务端有效。暂未考虑单机模式，使用需谨慎

:::

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<[`OnKeyConsume`](../modules/Core.mw.md#onkeyconsume)\> | 订单发货的委托 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onPremiumMemberStatusUpdate <Score text="onPremiumMemberStatusUpdate" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **onPremiumMemberStatusUpdate**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`result`: `boolean`) => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取大会员状态更新时触发的委托

#### Returns

</td>
</tr></tbody>
</table>

| [`MulticastDelegate`](mw.MulticastDelegate.md)<(`result`: `boolean`) => `void`\> | 大会员状态更新时触发的委托 |
| :------ | :------ |

## Methods

### consumeKey <Score text="consumeKey" /> 

• `Static` **consumeKey**(`boxId`, `number`, `keyType`, `placeOrderResult`): `void` <Badge type="tip" text="client" />

大会员开宝箱消耗金钥匙

#### Parameters

| `boxId` `string` | 宝箱 ID，代表一种福利，暂时自定义id。后续会在开发者平台配制 range:依据 boxId 长度 |
| :------ | :------ |
| `number` `number` | 领取的宝箱数量 <br> default: 1 range: 不做限制 type: 整形 |
| `keyType` `number` | 钥匙类型，当前只有一种钥匙类型值为 1 <br> default: 1 range: 1 type:整数 |
| `placeOrderResult` (`status`: [`consumeKeyStatus`](../enums/mw.consumeKeyStatus.md)) => `void` | 订单结果。status 大会员扣除钥匙下单状态 |


<span style="font-size: 14px;">
使用示例: 需要先在服务端监听发货信息，扣除钥匙时会判断服务端是否监听
</span>

```ts
if (SystemUtil.isServer()) {
     console.log("监听发货");
     //发货监听
     mw.PurchaseService.onPremiumMemberOrderDelivered.add((
          playerController: mw.Player,
          orderId: string,
          boxId: string,
          amount: number,
          confirmOrder: (bReceived: boolean) => void
     ) => {
          mw.Event.dispatchToClient(playerController, orderId, boxId, amount);
          //确认收货
          confirmOrder(true);
     });
}

// 扣除钥匙
mw.PurchaseService.consumeKey("1000", 1, 1, (status : mw.consumeKeyStatus) => {
     console.log("consumeKey status : " + status);
     if (status == mw.consumeKeyStatus.Success) {
          console.log("下单成功");
     } else if (status == mw.consumeKeyStatus.PremiumMemberNotSupported) {
          console.log("不支持大会员");
     } else if (status == mw.consumeKeyStatus.NotPremiumMember) {
          console.log("不是大会员");
     } else if (status == mw.consumeKeyStatus.InsufficientKeys) {
          console.log("钥匙不足");
     } else if (status == mw.consumeKeyStatus.Error) {
          console.log("扣除失败");
     }
});
```

___

### findKeyUsageHistory <Score text="findKeyUsageHistory" /> 

• `Static` **findKeyUsageHistory**(`currentPage`, `pageSize`, `historyResult`): `void` 

分页查询大会员使用钥匙的历史记录

#### Parameters

| `currentPage` `number` | 查找第几页 <br> type:整数型 <br> range:（1, 65535) |
| :------ | :------ |
| `pageSize` `number` | 每页大小 <br> type:整数型 <br> range:(1, 100) |
| `historyResult` (`total`: `number`, `currentPage`: `number`, `bill`: [`keyUsageInfo`](../modules/Core.mw.md#keyusageinfo)[]) => `void` | 查询结果回调函数 |


<span style="font-size: 14px;">
使用示例:将代码片段放入脚本中即可
</span>

```ts
mw.PurchaseService.findKeyUsageHistory(1, 100, (total : number, currentPage : number, bills : mw.keyUsageInfo[]) => {
    console.log("bill len : " + bills.length);
    for(let bill of bills)
    {
        console.log("bill orderId : " + bill.orderId);
        console.log("bill boxId : " + bill.boxId);
        console.log("bill number : " + bill.number);
        console.log("bill consumeTime : " + bill.consumeTime);
    }
});
```

___

### getArkBalance <Score text="getArkBalance" /> 

• `Static` **getArkBalance**(): `void` <Badge type="tip" text="client" />

获取代币余额


<span style="font-size: 14px;">
使用示例:创建一个名为PurchaseExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，发布游戏在移动端测试，5秒后会显示代币余额
</span>

```ts
@Component
export default class PurchaseExample extends mw.Script {

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        this.test();
    }

    private async test(): Promise<void> {
        //在客户端注册刷新监听
        const onArkUpdate = (amount: number) => {
            //刷新逻辑，amount为当前代币数量
        }
        PurchaseService.onArkBalanceUpdated.add(onArkUpdate);

        //触发代币余额刷新。接收更新的值要用PurchaseService.onArkBalanceUpdated监听
        PurchaseService.getArkBalance();
    }
}
```

___

### getUserKeyNumber <Score text="getUserKeyNumber" /> 

• `Static` **getUserKeyNumber**(`getUserKeyNumberResult`, `keyType?`): `void` <Badge type="tip" text="client" />

获取用户剩余钥匙数量

#### Parameters

| `getUserKeyNumberResult` (`keyNumber`: `number`) => `void` | 结果回调，查询到结果后执行回调函数。keyNumber : 剩余钥匙数量 |
| :------ | :------ |
| `keyType?` `number` | 搜索的钥匙类型，暂时只有类型 1 <br> default: 1 range: 1 type: 整形 |


<span style="font-size: 14px;">
使用示例:创建一个名为PurchaseExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，发布游戏在移动端测试，可以看到当前用户剩余钥匙数量
</span>

```ts
@Component
export default class PurchaseExample extends mw.Script {

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        this.test();
    }

    private async test(): Promise<void> {
        let player = Player.localPlayer;
        PurchaseService.getUserKeyNumber(keyNumber => {
            player.character.displayName = "当前用户剩余钥匙数量：", keyNumber.toString();
        })
    }
}
```

___

### isPremiumMember <Score text="isPremiumMember" /> 

• `Static` **isPremiumMember**(`isPremiumMemberResult`): `void` <Badge type="tip" text="client" />

获取用户是否是大会员

#### Parameters

| `isPremiumMemberResult` (`result`: `boolean`) => `void` | 结果回调，查询到结果后执行回调函数。true:是大会员，false:不是大会员 |
| :------ | :------ |


::: warning Precautions

暂未考虑单机模式，第一次结果会通过异步回调的方式返回（构造时自动请求），后续会通过缓存直接执行回调函数（同步），

:::

<span style="font-size: 14px;">
使用示例:创建一个名为PurchaseExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，发布游戏在移动端测试，可以看到当前用户是否是大会员
</span>

```ts
@Component
export default class PurchaseExample extends mw.Script {

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        this.test();
    }

    private async test(): Promise<void> {
        let player = Player.localPlayer;
        PurchaseService.isPremiumMember(isSupport => {
            player.character.displayName = isSupport ? "当前玩家是大会员" : "当前玩家不是大会员";
        })
    }
}
```

___

### isPremiumMemberSupported <Score text="isPremiumMemberSupported" /> 

• `Static` **isPremiumMemberSupported**(`isSupportedResult`): `void` <Badge type="tip" text="client" />

获取用户使用软件版本是否有大会员功能

#### Parameters

| `isSupportedResult` (`result`: `boolean`) => `void` | 结果回调，查询到结果后执行回调函数。true:支持大会员功能，false:不支持大会员功能 |
| :------ | :------ |


::: warning Precautions

暂未考虑单机模式，第一次结果会通过异步回调的方式返回（构造时自动请求），后续会通过缓存直接执行回调函数（同步）。老版本的App可能出现无回调的情况，需要自行判断超时

:::

<span style="font-size: 14px;">
使用示例:创建一个名为PurchaseExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，发布游戏在移动端测试，可以看到当前app是否支持大会员功能
</span>

```ts
@Component
export default class PurchaseExample extends mw.Script {

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        this.test();
    }

    private async test(): Promise<void> {
        let player = Player.localPlayer;
        PurchaseService.isPremiumMemberSupported(isSupport => {
            player.character.displayName = isSupport ? "当前app支持大会员功能" : "当前app不支持大会员功能";
        })
    }
}
```

___

### openPremiumMemberPurchasePage <Score text="openPremiumMemberPurchasePage" /> 

• `Static` **openPremiumMemberPurchasePage**(): `void` <Badge type="tip" text="client" />

跳转会员充值页面


<span style="font-size: 14px;">
使用示例:创建一个名为PurchaseExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，发布游戏在移动端测试，10秒后会自动打开会员充值页面。
</span>

```ts
@Component
export default class PurchaseExample extends mw.Script {

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        this.test();
    }

    private async test(): Promise<void> {
        await TimeUtil.delaySecond(10);
        PurchaseService.openPremiumMemberPurchasePage();
    }
}
```

___

### placeOrder <Score text="placeOrder" /> 

• `Static` **placeOrder**(`commodityId`, `amount`, `placeOrderResult`): `void` <Badge type="tip" text="client" />

下单指定数量的指定商品

#### Parameters

| `commodityId` `string` |  商品Id range: 依据商品 ID 长度而定 |
| :------ | :------ |
| `amount` `number` |  数量 range:不做限制 type:整数 |
| `placeOrderResult` (`status`: `number`, `msg`: `string`) => `void` |  订单状态回调 |


status 含义：

status = 200: 订单支付成功

status = 408: 请求超时

status = 409: 处理下单回调报错

status = 410: 处理支付回调报错

status = 501: 余额不足

status = 502: 暂未开放购买

status = 503: amount参数类型错误

___

### redeemGiftCode <Score text="redeemGiftCode" /> 

• `Static` **redeemGiftCode**(`player`, `GiftCode`, `redeemCallback`): `void` <Badge type="tip" text="server" />

礼包码兑换

#### Parameters

| `player` [`Player`](mw.Player.md) |  需要兑换的玩家对象 |
| :------ | :------ |
| `GiftCode` `string` |  礼包码 <br> range: 依据兑换码长度而定 |
| `redeemCallback` (`result`: [`RedeemResponse`](../modules/Core.mw.md#redeemresponse)) => `void` |  兑换结果的回调函数 |


RedeemResponse中status : 兑换状态。

200 ： 兑换成功

400 ： 兑换失败（兑换码不存在）

423 ： 兑换失败（请求频繁）

1002 ：兑换失败（兑换码不在使用期限内）

1010 ：兑换失败（兑换码已使用）

1011 ：兑换失败（兑换超时）

1012 ：兑换失败（礼包库存不足）

1013 ：兑换失败（超出兑换次数）

1014 ：兑换失败（数据库失败）

1015 ：兑换失败（非本游戏道具）

RedeemResponse中message : 兑换信息

当兑换状态为成功时：兑换信息为礼包内容道具详情。

当兑换状态为失败时：兑换信息为失败详情，例如：兑换码不存在。

<span style="font-size: 14px;">
使用示例:创建一个名为PurchaseExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，发布游戏在移动端测试，5秒后会显示代币余额
</span>

```ts
@Component
export default class NewScript extends Script {
    @Property({replicated:true,multicast:true})
    public player:Player;
    @Property({replicated:true,multicast:true})
    public playerid:string

    protected onStart(): void {
        if(SystemUtil.isClient()) {
            this.playerid = Player.localPlayer.userId;
            console.log(this.playerid);
        }
        if(SystemUtil.isServer()){
            this.textFunc();
        }
    }

    @RemoteFunction(Server)
    public textFunc(){
        Player.getAllPlayers().forEach(element => {
            this.player = element;
        });
        // ""中填写兑换码
        PurchaseService.redeemGiftCode(this.player, "" ,(result:RedeemResponse)=>{
            console.log("result.message------------" + result.message);
            console.log("result.message------------" + result.status);
        });
        console.log("--------over----------")
    }
}
```
