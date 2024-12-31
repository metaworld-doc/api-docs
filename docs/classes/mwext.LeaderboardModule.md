[拓展](../groups/Extension.拓展.md) / LeaderboardModule

# LeaderboardModule <Badge type="tip" text="Class" /> <Score text="LeaderboardModule" />

**`Instance`**

编辑器内置排行榜

## Table of contents

### Methods <Score text="Methods" /> 
| **[addField](mwext.LeaderboardModule.md#addfield)**(`fieldId`: `number`, `fieldName`: `string`, `valueStyle?`: `string`): typeof [`LeaderboardModule`](mwext.LeaderboardModule.md) <Badge type="tip" text="client" />  |
| :-----|
| 添加一个字段|
| **[addPlayer](mwext.LeaderboardModule.md#addplayer)**(`player`: `number`  [`Player`](mw.Player.md), `data?`: `any`): `void` <Badge type="tip" text="server" />  |
| 向排行榜添加一个玩家|
| **[clear](mwext.LeaderboardModule.md#clear)**(): `void` <Badge type="tip" text="server" />  |
| 清除排行榜|
| **[hidePanel](mwext.LeaderboardModule.md#hidepanel)**(): `void` <Badge type="tip" text="client" />  |
| 隐藏UI|
| **[removePlayer](mwext.LeaderboardModule.md#removeplayer)**(`player`: `number`  [`Player`](mw.Player.md)): `void` <Badge type="tip" text="server" />  |
| 从排行榜移除一个玩家|
| **[setPlayerValue](mwext.LeaderboardModule.md#setplayervalue)**(`player`: `number`  [`Player`](mw.Player.md), `fieldId`: `number`, `value`: `string`  `number`): `void` <Badge type="tip" text="server" />  |
| 设置一个玩家的一个字段值|
| **[setSortFields](mwext.LeaderboardModule.md#setsortfields)**(`...fieldIds`: `number`[]): typeof [`LeaderboardModule`](mwext.LeaderboardModule.md) <Badge type="tip" text="client" />  |
| 设置排序字段|
| **[setSortMethod](mwext.LeaderboardModule.md#setsortmethod)**(`fn`: (`dataList`: [`LeaderboardPlayerData`](../modules/Extension.mwext.md#leaderboardplayerdata)[]) => [`LeaderboardPlayerData`](../modules/Extension.mwext.md#leaderboardplayerdata)[]): typeof [`LeaderboardModule`](mwext.LeaderboardModule.md) <Badge type="tip" text="client" />  |
| 设置排序的方法|
| **[setStyle](mwext.LeaderboardModule.md#setstyle)**(`title`: `string`, `fieldsAutoLayout`: `boolean`, `showPlayerNum`: `number`, `itemSpacing`: `number`): typeof [`LeaderboardModule`](mwext.LeaderboardModule.md) <Badge type="tip" text="client" />  |
| 设置样式|
| **[showPanel](mwext.LeaderboardModule.md#showpanel)**(`hideCallback?`: () => `void`): `void` <Badge type="tip" text="client" />  |
| 显示 UI|
| **[showRankField](mwext.LeaderboardModule.md#showrankfield)**(`fieldName`: `string`, `valueStyle?`: `string`, `notListed?`: `string`): typeof [`LeaderboardModule`](mwext.LeaderboardModule.md) <Badge type="tip" text="client" />  |
| 显示排名|

## Methods

### addField <Score text="addField" /> 

• `Static` **addField**(`fieldId`, `fieldName`, `valueStyle?`): typeof [`LeaderboardModule`](mwext.LeaderboardModule.md) <Badge type="tip" text="client" />

添加一个字段

#### Parameters

| `fieldId` `number` |  字段 ID range: 依据 ID 长度而定 type: |
| :------ | :------ |
| `fieldName` `string` |  字段名 range:不做限制 |
| `valueStyle?` `string` |  显示内容样式(例：`{0}`分) default: null range:不做限制 |

#### Returns

| typeof [`LeaderboardModule`](mwext.LeaderboardModule.md) | 返回自己，可用于链式调用 |
| :------ | :------ |

___

### addPlayer <Score text="addPlayer" /> 

• `Static` **addPlayer**(`player`, `data?`): `void` <Badge type="tip" text="server" />

向排行榜添加一个玩家

#### Parameters

| `player` `number`  [`Player`](mw.Player.md) |  玩家对象玩家id <br> range: 根据 ID 长度而定 |
| :------ | :------ |
| `data?` `any` |  玩家数据 default: `{}` |


___

### clear <Score text="clear" /> 

• `Static` **clear**(): `void` <Badge type="tip" text="server" />

清除排行榜


___

### hidePanel <Score text="hidePanel" /> 

• `Static` **hidePanel**(): `void` <Badge type="tip" text="client" />

隐藏UI


___

### removePlayer <Score text="removePlayer" /> 

• `Static` **removePlayer**(`player`): `void` <Badge type="tip" text="server" />

从排行榜移除一个玩家

#### Parameters

| `player` `number`  [`Player`](mw.Player.md) |  玩家对象玩家id <br> range: 根据 ID 长度而定 |
| :------ | :------ |


___

### setPlayerValue <Score text="setPlayerValue" /> 

• `Static` **setPlayerValue**(`player`, `fieldId`, `value`): `void` <Badge type="tip" text="server" />

设置一个玩家的一个字段值

#### Parameters

| `player` `number`  [`Player`](mw.Player.md) |  玩家对象玩家id <br> range: 根据 ID 长度而定 |
| :------ | :------ |
| `fieldId` `number` |  字段的ID <br> range: 根据 ID 长度而定 type:整数 |
| `value` `string`  `number` |  字段的值 <br> range: 不做限制，一个玩家一个数据 type:整数 |


___

### setSortFields <Score text="setSortFields" /> 

• `Static` **setSortFields**(`...fieldIds`): typeof [`LeaderboardModule`](mwext.LeaderboardModule.md) <Badge type="tip" text="client" />

设置排序字段

#### Parameters

| `...fieldIds` `number`[] |  排序字段 <br> range: 长度不做限制 |
| :------ | :------ |

#### Returns

| typeof [`LeaderboardModule`](mwext.LeaderboardModule.md) | 返回自己，可用于链式调用 |
| :------ | :------ |

可以设置多字段排序，只支持从大到小排序。

___

### setSortMethod <Score text="setSortMethod" /> 

• `Static` **setSortMethod**(`fn`): typeof [`LeaderboardModule`](mwext.LeaderboardModule.md) <Badge type="tip" text="client" />

设置排序的方法

#### Parameters

| `fn` (`dataList`: [`LeaderboardPlayerData`](../modules/Extension.mwext.md#leaderboardplayerdata)[]) => [`LeaderboardPlayerData`](../modules/Extension.mwext.md#leaderboardplayerdata)[] |  方法 |
| :------ | :------ |

#### Returns

| typeof [`LeaderboardModule`](mwext.LeaderboardModule.md) | 返回自己，可用于链式调用 |
| :------ | :------ |

___

### setStyle <Score text="setStyle" /> 

• `Static` **setStyle**(`title`, `fieldsAutoLayout`, `showPlayerNum`, `itemSpacing`): typeof [`LeaderboardModule`](mwext.LeaderboardModule.md) <Badge type="tip" text="client" />

设置样式

#### Parameters

| `title` `string` |  界面标题 range: UI 标题信息 |
| :------ | :------ |
| `fieldsAutoLayout` `boolean` |  字段是否自动布局，均匀分布 |
| `showPlayerNum` `number` |  最多显示的玩家数量 range:合理即可 type: 整形 |
| `itemSpacing` `number` |  每条数据的间距 range:合理即可 type: 整形 |

#### Returns

| typeof [`LeaderboardModule`](mwext.LeaderboardModule.md) | 返回自己，可用于链式调用 |
| :------ | :------ |

___

### showPanel <Score text="showPanel" /> 

• `Static` **showPanel**(`hideCallback?`): `void` <Badge type="tip" text="client" />

显示 UI

#### Parameters

| `hideCallback?` () => `void` |  Panel关闭的回调 default: null |
| :------ | :------ |


___

### showRankField <Score text="showRankField" /> 

• `Static` **showRankField**(`fieldName`, `valueStyle?`, `notListed?`): typeof [`LeaderboardModule`](mwext.LeaderboardModule.md) <Badge type="tip" text="client" />

显示排名

#### Parameters

| `fieldName` `string` |  字段名 range: 依据 ID 长度而定 type: |
| :------ | :------ |
| `valueStyle?` `string` |  字段值样式 default: null range:不做限制 |
| `notListed?` `string` |  未上榜(如果未上榜也显示名次请填写null) default: null range:不做限制 |

#### Returns

| typeof [`LeaderboardModule`](mwext.LeaderboardModule.md) | 返回自己，可用于链式调用 |
| :------ | :------ |
