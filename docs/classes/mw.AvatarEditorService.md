[服务](../groups/服务.服务.md) / AvatarEditorService

# AvatarEditorService <Badge type="tip" text="Class" /> <Score text="AvatarEditorService" />

Avatar商城的应用内购服务

## Table of contents

### Accessors <Score text="Accessors" /> 
| **[avatarServiceDelegate](mw.AvatarEditorService.md#avatarservicedelegate)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`eventName`: `string`, ...`params`: `unknown`[]) => `void`\> <Badge type="tip" text="client" />  |
| :-----|
| 角编商城状态发生变化时会触发的委托|
| **[onAccountBalanceUpdated](mw.AvatarEditorService.md#onaccountbalanceupdated)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`balance`: [`BalanceInfo`](../modules/Core.mw.md#balanceinfo)) => `void`\> <Badge type="tip" text="client" />  |
| 获取代币和积分余额更新的委托。购买成功后/充值成功后, 都会触发|
| **[onOrderDelivered](mw.AvatarEditorService.md#onorderdelivered)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`resp`: [`ShipOrderResponse`](../modules/Core.mw.md#shiporderresponse)) => `void`\> <Badge type="tip" text="client" />  |
| 玩家数据服务完成发货后会触发的委托|
| **[onRecharge](mw.AvatarEditorService.md#onrecharge)**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`info`: [`RechargeInfo`](../modules/Core.mw.md#rechargeinfo)) => `void`\> <Badge type="tip" text="client" />  |
| 玩家充值时会触发的委托|

### Methods <Score text="Methods" /> 
| **[asyncCloseAvatarEditorModule](mw.AvatarEditorService.md#asynccloseavatareditormodule)**(): `Promise`<`void`\> <Badge type="tip" text="client" />  |
| :-----|
| 打开角编商城|
| **[asyncDumpImg](mw.AvatarEditorService.md#asyncdumpimg)**(`locImgPath`: `string`, `imgName`: `string`): `Promise`<`string`\> <Badge type="tip" text="client" />  |
| 本地图片路径转存成网络图|
| **[asyncGetCashPayEnabled](mw.AvatarEditorService.md#asyncgetcashpayenabled)**(): `Promise`<`boolean`\> <Badge type="tip" text="client" />  |
| 异步查询现金支付是否支持|
| **[asyncGetCommodityByAssetIds](mw.AvatarEditorService.md#asyncgetcommoditybyassetids)**(`assetIds`: `string`[]): `Promise`<[`CommodityListObj`](../modules/Core.mw.md#commoditylistobj)\> <Badge type="tip" text="client" />  |
| 通过资源Id获取商品列表|
| **[asyncGetCommodityListByItemIds](mw.AvatarEditorService.md#asyncgetcommoditylistbyitemids)**(`itemIds`: `number`[]): `Promise`<[`CommodityListObj`](../modules/Core.mw.md#commoditylistobj)\> <Badge type="tip" text="client" />  |
| 通过物品Id获取商品列表|
| **[asyncGetCommodityListByTag](mw.AvatarEditorService.md#asyncgetcommoditylistbytag)**(`tagIds`: `number`[]): `Promise`<[`CommodityListObj`](../modules/Core.mw.md#commoditylistobj)\> <Badge type="tip" text="client" />  |
| 获取商品列表|
| **[asyncGetMyItemsListByTag](mw.AvatarEditorService.md#asyncgetmyitemslistbytag)**(`tagIds`: `number`[]): `Promise`<[`CommodityListObj`](../modules/Core.mw.md#commoditylistobj)\> <Badge type="tip" text="client" />  |
| 获取我可使用的物品列表|
| **[asyncGetPointPayEnabled](mw.AvatarEditorService.md#asyncgetpointpayenabled)**(): `Promise`<`boolean`\> <Badge type="tip" text="client" />  |
| 异步查询积分支付是否支持|
| **[asyncOpenAvatarEditorModule](mw.AvatarEditorService.md#asyncopenavatareditormodule)**(`extraInfo?`: `any`): `Promise`<`boolean`\> <Badge type="tip" text="client" />  |
| 打开角编商城|
| **[asyncSaveAvatarAndUpdateProfile](mw.AvatarEditorService.md#asyncsaveavatarandupdateprofile)**(`targetNPC`: [`Character`](mw.Character.md), `updateHead?`: `boolean`): `Promise`<`number`\> <Badge type="tip" text="client" />  |
| 保存平台形象，并更新全身照。是否更新头像，取决于入参。|
| **[getAccountBalance](mw.AvatarEditorService.md#getaccountbalance)**(): `void` <Badge type="tip" text="client" />  |
| 获取余额。会同时更新代币和积分的余额。|
| **[placeOrder](mw.AvatarEditorService.md#placeorder)**(`commodityList`: [`CommodityInfo`](../modules/Core.mw.md#commodityinfo)[], `[placeOrder](mw.AvatarEditorService.md#placeorder)Result`): `void` <Badge type="tip" text="client" />  |
| 下单商品并跳转支付，可以指定多个商品进行购买。如果需要携带额外信息（比如折扣token），可以加入到CommodityInfo.expand字段中|
| **[promptRecharge](mw.AvatarEditorService.md#promptrecharge)**(): `void` <Badge type="tip" text="client" />  |
| 拉起充值页面|
| **[setAvatarEditorButtonVisible](mw.AvatarEditorService.md#setavatareditorbuttonvisible)**(`visible`: `boolean`): `void` <Badge type="tip" text="client" />  |
| 设置角色编辑器按钮可见性|

## Accessors

### avatarServiceDelegate <Score text="avatarServiceDelegate" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **avatarServiceDelegate**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`eventName`: `string`, ...`params`: `unknown`[]) => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


角编商城状态发生变化时会触发的委托

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<(`eventName`: `string`, ...`params`: `unknown`[]) => `void`\> | 角编商城状态发生变化时会触发的委托 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onAccountBalanceUpdated <Score text="onAccountBalanceUpdated" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **onAccountBalanceUpdated**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`balance`: [`BalanceInfo`](../modules/Core.mw.md#balanceinfo)) => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取代币和积分余额更新的委托。购买成功后/充值成功后, 都会触发

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<(`balance`: [`BalanceInfo`](../modules/Core.mw.md#balanceinfo)) => `void`\> | 代币余额更新的委托。coin对应代币余额，point对应积分余额 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onOrderDelivered <Score text="onOrderDelivered" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **onOrderDelivered**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`resp`: [`ShipOrderResponse`](../modules/Core.mw.md#shiporderresponse)) => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


玩家数据服务完成发货后会触发的委托

#### Returns

| [`MulticastDelegate`](mw.MulticastDelegate.md)<(`resp`: [`ShipOrderResponse`](../modules/Core.mw.md#shiporderresponse)) => `void`\> | 订单发货的委托 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### onRecharge <Score text="onRecharge" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **onRecharge**(): [`MulticastDelegate`](mw.MulticastDelegate.md)<(`info`: [`RechargeInfo`](../modules/Core.mw.md#rechargeinfo)) => `void`\> <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


玩家充值时会触发的委托

#### Returns

</td>
</tr></tbody>
</table>

| [`MulticastDelegate`](mw.MulticastDelegate.md)<(`info`: [`RechargeInfo`](../modules/Core.mw.md#rechargeinfo)) => `void`\> | 充值时会触发的委托 |
| :------ | :------ |

## Methods

### asyncCloseAvatarEditorModule <Score text="asyncCloseAvatarEditorModule" /> 

• `Static` **asyncCloseAvatarEditorModule**(): `Promise`<`void`\> <Badge type="tip" text="client" />

打开角编商城

#### Returns

| `Promise`<`void`\> | 异步void |
| :------ | :------ |

___

### asyncDumpImg <Score text="asyncDumpImg" /> 

• `Static` **asyncDumpImg**(`locImgPath`, `imgName`): `Promise`<`string`\> <Badge type="tip" text="client" />

本地图片路径转存成网络图

#### Parameters

| `locImgPath` `string` |  本地图片文件路径 range: 无 |
| :------ | :------ |
| `imgName` `string` |  本地图片文件名 range: 无 |

#### Returns

| `Promise`<`string`\> | 成功返回url，失败返回null |
| :------ | :------ |

___

### asyncGetCashPayEnabled <Score text="asyncGetCashPayEnabled" /> 

• `Static` **asyncGetCashPayEnabled**(): `Promise`<`boolean`\> <Badge type="tip" text="client" />

异步查询现金支付是否支持

#### Returns

| `Promise`<`boolean`\> | 是否支持 |
| :------ | :------ |

___

### asyncGetCommodityByAssetIds <Score text="asyncGetCommodityByAssetIds" /> 

• `Static` **asyncGetCommodityByAssetIds**(`assetIds`): `Promise`<[`CommodityListObj`](../modules/Core.mw.md#commoditylistobj)\> <Badge type="tip" text="client" />

通过资源Id获取商品列表

#### Parameters

| `assetIds` `string`[] |  用于筛选商品的AssetId数组 |
| :------ | :------ |

#### Returns

| `Promise`<[`CommodityListObj`](../modules/Core.mw.md#commoditylistobj)\> | 商品列表 |
| :------ | :------ |

___

### asyncGetCommodityListByItemIds <Score text="asyncGetCommodityListByItemIds" /> 

• `Static` **asyncGetCommodityListByItemIds**(`itemIds`): `Promise`<[`CommodityListObj`](../modules/Core.mw.md#commoditylistobj)\> <Badge type="tip" text="client" />

通过物品Id获取商品列表

#### Parameters

| `itemIds` `number`[] |  用于筛选商品的ItemId数组 |
| :------ | :------ |

#### Returns

| `Promise`<[`CommodityListObj`](../modules/Core.mw.md#commoditylistobj)\> | 商品列表 |
| :------ | :------ |

___

### asyncGetCommodityListByTag <Score text="asyncGetCommodityListByTag" /> 

• `Static` **asyncGetCommodityListByTag**(`tagIds`): `Promise`<[`CommodityListObj`](../modules/Core.mw.md#commoditylistobj)\> <Badge type="tip" text="client" />

获取商品列表

#### Parameters

| `tagIds` `number`[] |  用于筛选商品的Tag数组 |
| :------ | :------ |

#### Returns

| `Promise`<[`CommodityListObj`](../modules/Core.mw.md#commoditylistobj)\> | 商品列表 |
| :------ | :------ |

___

### asyncGetMyItemsListByTag <Score text="asyncGetMyItemsListByTag" /> 

• `Static` **asyncGetMyItemsListByTag**(`tagIds`): `Promise`<[`CommodityListObj`](../modules/Core.mw.md#commoditylistobj)\> <Badge type="tip" text="client" />

获取我可使用的物品列表

#### Parameters

| `tagIds` `number`[] |  用于筛选商品的Tag数组 |
| :------ | :------ |

#### Returns

| `Promise`<[`CommodityListObj`](../modules/Core.mw.md#commoditylistobj)\> | 物品列表 |
| :------ | :------ |

___

### asyncGetPointPayEnabled <Score text="asyncGetPointPayEnabled" /> 

• `Static` **asyncGetPointPayEnabled**(): `Promise`<`boolean`\> <Badge type="tip" text="client" />

异步查询积分支付是否支持

#### Returns

| `Promise`<`boolean`\> | 是否支持 |
| :------ | :------ |

___

### asyncOpenAvatarEditorModule <Score text="asyncOpenAvatarEditorModule" /> 

• `Static` **asyncOpenAvatarEditorModule**(`extraInfo?`): `Promise`<`boolean`\> <Badge type="tip" text="client" />

打开角编商城

#### Parameters

| `extraInfo?` `any` |  额外的传参 default: undefined |
| :------ | :------ |

#### Returns

| `Promise`<`boolean`\> | 打开结果 |
| :------ | :------ |

___

### asyncSaveAvatarAndUpdateProfile <Score text="asyncSaveAvatarAndUpdateProfile" /> 

• `Static` **asyncSaveAvatarAndUpdateProfile**(`targetNPC`, `updateHead?`): `Promise`<`number`\> <Badge type="tip" text="client" />

保存平台形象，并更新全身照。是否更新头像，取决于入参。

#### Parameters

| `targetNPC` [`Character`](mw.Character.md) |  目标NPC |
| :------ | :------ |
| `updateHead?` `boolean` |  是否更新头像。不影响形象保存和全身照的更新。default: true |

#### Returns

| `Promise`<`number`\> | ``` |
| :------ | :------ |

___

### getAccountBalance <Score text="getAccountBalance" /> 

• `Static` **getAccountBalance**(): `void` <Badge type="tip" text="client" />

获取余额。会同时更新代币和积分的余额。


___

### placeOrder <Score text="placeOrder" /> 

• `Static` **placeOrder**(`commodityList`, `placeOrderResult`): `void` <Badge type="tip" text="client" />

下单商品并跳转支付，可以指定多个商品进行购买。如果需要携带额外信息（比如折扣token），可以加入到CommodityInfo.expand字段中

#### Parameters

| `commodityList` [`CommodityInfo`](../modules/Core.mw.md#commodityinfo)[] |  商品信息 range: 依据 商品数量 而定 |
| :------ | :------ |
| `placeOrderResult` (`status`: `number`, `msg`: `string`, `orderId`: `string`) => `void` |  订单状态回调 |


status 含义：
```ts
status = 200: 订单支付成功
status = 408: 请求超时
status = 409: 处理下单回调报错
status = 410: 处理支付回调报错
status = 501: 余额不足
status = 502: 暂未开放购买
status = 503: 参数类型错误
status = 504: 用户取消
status = 505: 轮询失败，未支付成功
status = 506: 该版本不支持 payType
status = 507: 未知异常，包括但不限于网络连接失败
其它：服务端返回的错误码，包括但不限于：下单，预支付，轮询等接口的报错
```

___

### promptRecharge <Score text="promptRecharge" /> 

• `Static` **promptRecharge**(): `void` <Badge type="tip" text="client" />

拉起充值页面


___

### setAvatarEditorButtonVisible <Score text="setAvatarEditorButtonVisible" /> 

• `Static` **setAvatarEditorButtonVisible**(`visible`): `void` <Badge type="tip" text="client" />

设置角色编辑器按钮可见性

#### Parameters

| `visible` `boolean` |  true表示可见，false不可见 |
| :------ | :------ |

