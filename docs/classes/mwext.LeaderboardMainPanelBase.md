[拓展](../groups/Extension.拓展.md) / LeaderboardMainPanelBase

# LeaderboardMainPanelBase<T\> <Badge type="tip" text="Class" /> <Score text="LeaderboardMainPanelBase<T\>" />

排行榜主界面

## Type parameters

| `T` | extends [`ILeaderboardPanelView`](../interfaces/mwext.ILeaderboardPanelView.md) |
| :------ | :------ |

## Hierarchy

- [`BasePanel`](mwext.BasePanel.md)<`T`\>

  ↳ **`LeaderboardMainPanelBase`**

## Table of contents

### Properties <Score text="Properties" /> 
| **[onClose](mwext.LeaderboardMainPanelBase.md#onclose)**: [`Action`](mw.Action.md)  |
| :-----|
| 当关闭的时候调用的事件|

### Accessors <Score text="Accessors" /> 


::: details click
### Accessors <Score text="Accessors" /> 
| **[size](mwext.BasePanel.md#size)**(): [`Vector2`](mw.Vector2.md)  |
| :-----|
| 面板尺寸|
| **[view](mwext.BasePanel.md#view)**(): `T`  |
| 面板所控制的界面|
:::


### Methods <Score text="Methods" /> 
| **[addField](mwext.LeaderboardMainPanelBase.md#addfield)**(`fieldId`: `number`, `fieldName`: `string`, `valueStyle?`: `string`): [`LeaderboardMainPanelBase`](mwext.LeaderboardMainPanelBase.md)<`T`\> <Badge type="tip" text="client" />  |
| :-----|
| 添加一个字段|
| **[creatItem](mwext.LeaderboardMainPanelBase.md#creatitem)**(): [`LeaderboardItemPanelBase`](mwext.LeaderboardItemPanelBase.md)<`{ `mContent`: [`Canvas`](mw.Canvas.md)  }` & [`UIScript`](mw.UIScript.md)\> <Badge type="tip" text="client" />  |
| 创建用于显示一条排行信息的item子UI|
| **[onHide](mwext.LeaderboardMainPanelBase.md#onhide)**(): `void` <Badge type="tip" text="client" />  |
| 当UI隐藏调用|
| **[onSelfFieldSet](mwext.LeaderboardMainPanelBase.md#onselffieldset)**(`rankIndex`: `number`, `fieldId`: `number`, `fieldValue`: `string`  `number`, `textBlockIndex`: `number`, `textBlock`: [`TextBlock`](mw.TextBlock.md)): `void` <Badge type="tip" text="client" />  |
| 设置自己(界面最下面那一行)的字段内容后调用，需要请复写|
| **[onShow](mwext.LeaderboardMainPanelBase.md#onshow)**(`playerDataList`: [`LeaderboardPlayerData`](../modules/Extension.mwext.md#leaderboardplayerdata)[]): `void` <Badge type="tip" text="client" />  |
| 当UI显示调用|
| **[onSort](mwext.LeaderboardMainPanelBase.md#onsort)**(`dataList`: [`LeaderboardPlayerData`](../modules/Extension.mwext.md#leaderboardplayerdata)[]): [`LeaderboardPlayerData`](../modules/Extension.mwext.md#leaderboardplayerdata)[] <Badge type="tip" text="client" />  |
| 排序的时候调用，需要请重写|
| **[setSortFields](mwext.LeaderboardMainPanelBase.md#setsortfields)**(`...fieldIds`: `number`[]): [`LeaderboardMainPanelBase`](mwext.LeaderboardMainPanelBase.md)<`T`\> <Badge type="tip" text="client" />  |
| 设置排序字段ID，可以设置多字段排序，只支持从大到小排序|
| **[setStyle](mwext.LeaderboardMainPanelBase.md#setstyle)**(`title`: `string`, `fieldsAutoLayout`: `boolean`, `showPlayerNum`: `number`, `itemSpacing`: `number`): [`LeaderboardMainPanelBase`](mwext.LeaderboardMainPanelBase.md)<`T`\> <Badge type="tip" text="client" />  |
| 设置排行榜样式|
| **[showRankField](mwext.LeaderboardMainPanelBase.md#showrankfield)**(`fieldName`: `string`, `valueStyle?`: `string`, `notListed?`: `string`): [`LeaderboardMainPanelBase`](mwext.LeaderboardMainPanelBase.md)<`T`\> <Badge type="tip" text="client" />  |
| 显示"名次"字段，并进行设置，默认不显示|


::: details click
### Methods <Score text="Methods" /> 
| **[onAdded](mwext.BasePanel.md#onadded)**(): `void` <Badge type="tip" text="client" />  |
| :-----|
| 生命周期-被添加到父节点时候触发，可能会多次调用|
| **[onAwake](mwext.BasePanel.md#onawake)**(): `void` <Badge type="tip" text="client" />  |
| 生命周期方法-构建面板自动触发，只会调用一次|
:::


## Properties

### onClose <Score text="onClose" /> 

• `Readonly` **onClose**: [`Action`](mw.Action.md)

当关闭的时候调用的事件

## Accessors

## Methods

### addField <Score text="addField" /> 

• **addField**(`fieldId`, `fieldName`, `valueStyle?`): [`LeaderboardMainPanelBase`](mwext.LeaderboardMainPanelBase.md)<`T`\> <Badge type="tip" text="client" />

添加一个字段

#### Parameters

| `fieldId` `number` |  字段 ID range: 依据 ID 长度而定 type: |
| :------ | :------ |
| `fieldName` `string` |  字段的标题 range: |
| `valueStyle?` `string` |  字段值的展示样式 (例：`{0}`分) default: null range:不做限制 |

#### Returns

| [`LeaderboardMainPanelBase`](mwext.LeaderboardMainPanelBase.md)<`T`\> | 返回自己，可用于链式调用 |
| :------ | :------ |

___

### creatItem <Score text="creatItem" /> 

• `Protected` `Abstract` **creatItem**(): [`LeaderboardItemPanelBase`](mwext.LeaderboardItemPanelBase.md)<`{ `mContent`: [`Canvas`](mw.Canvas.md)  }` & [`UIScript`](mw.UIScript.md)\> <Badge type="tip" text="client" />

创建用于显示一条排行信息的item子UI

#### Returns

| [`LeaderboardItemPanelBase`](mwext.LeaderboardItemPanelBase.md)<`{ `mContent`: [`Canvas`](mw.Canvas.md)  }` & [`UIScript`](mw.UIScript.md)\> | 一条排行信息的item子UI |
| :------ | :------ |

___

### onHide <Score text="onHide" /> 

• `Protected` **onHide**(): `void` <Badge type="tip" text="client" />

当UI隐藏调用


::: warning Precautions

如果要复写此方法，记得调用super.onHide()

:::

___

### onSelfFieldSet <Score text="onSelfFieldSet" /> 

• `Protected` **onSelfFieldSet**(`rankIndex`, `fieldId`, `fieldValue`, `textBlockIndex`, `textBlock`): `void` <Badge type="tip" text="client" />

设置自己(界面最下面那一行)的字段内容后调用，需要请复写

#### Parameters

| `rankIndex` `number` |  名次索引(0开始) range: 合理即可，不做限制 type: 整形 |
| :------ | :------ |
| `fieldId` `number` |  字段索引 (如果是排行字段，此参数为mull) range: 合理即可，不做限制 type: 整形 |
| `fieldValue` `string`  `number` |  字段显示内容 range: 合理即可，不做限制 type: 整形 |
| `textBlockIndex` `number` |  文本控件索引 range: 合理即可，不做限制 type: 整形 |
| `textBlock` [`TextBlock`](mw.TextBlock.md) |  文本控件 |


___

### onShow <Score text="onShow" /> 

• `Protected` **onShow**(`playerDataList`): `void` <Badge type="tip" text="client" />

当UI显示调用

#### Parameters

| `playerDataList` [`LeaderboardPlayerData`](../modules/Extension.mwext.md#leaderboardplayerdata)[] |  玩家数据列表 |
| :------ | :------ |


::: warning Precautions

如果要复写此方法，记得调用super.onShow()

:::

___

### onSort <Score text="onSort" /> 

• `Protected` **onSort**(`dataList`): [`LeaderboardPlayerData`](../modules/Extension.mwext.md#leaderboardplayerdata)[] <Badge type="tip" text="client" />

排序的时候调用，需要请重写

#### Parameters

| `dataList` [`LeaderboardPlayerData`](../modules/Extension.mwext.md#leaderboardplayerdata)[] |  排行数据数组 |
| :------ | :------ |

#### Returns

| [`LeaderboardPlayerData`](../modules/Extension.mwext.md#leaderboardplayerdata)[] | 排序后的数据队列 |
| :------ | :------ |

___

### setSortFields <Score text="setSortFields" /> 

• **setSortFields**(`...fieldIds`): [`LeaderboardMainPanelBase`](mwext.LeaderboardMainPanelBase.md)<`T`\> <Badge type="tip" text="client" />

设置排序字段ID，可以设置多字段排序，只支持从大到小排序

#### Parameters

| `...fieldIds` `number`[] |  排序字段 |
| :------ | :------ |

#### Returns

| [`LeaderboardMainPanelBase`](mwext.LeaderboardMainPanelBase.md)<`T`\> | 返回自己，可用于链式调用 |
| :------ | :------ |

___

### setStyle <Score text="setStyle" /> 

• **setStyle**(`title`, `fieldsAutoLayout`, `showPlayerNum`, `itemSpacing`): [`LeaderboardMainPanelBase`](mwext.LeaderboardMainPanelBase.md)<`T`\> <Badge type="tip" text="client" />

设置排行榜样式

#### Parameters

| `title` `string` |  UI 标题 range: UI 标题信息 |
| :------ | :------ |
| `fieldsAutoLayout` `boolean` |  字段是否自动布局(true-均匀分布, false-所摆即所得） |
| `showPlayerNum` `number` |  最多显示的玩家数量 range:合理即可 type: 整形 |
| `itemSpacing` `number` |  每条数据的间距 range:合理即可 type: 整形 |

#### Returns

| [`LeaderboardMainPanelBase`](mwext.LeaderboardMainPanelBase.md)<`T`\> | 返回自己，可用于链式调用 |
| :------ | :------ |

___

### showRankField <Score text="showRankField" /> 

• **showRankField**(`fieldName`, `valueStyle?`, `notListed?`): [`LeaderboardMainPanelBase`](mwext.LeaderboardMainPanelBase.md)<`T`\> <Badge type="tip" text="client" />

显示"名次"字段，并进行设置，默认不显示

#### Parameters

| `fieldName` `string` |  字段标题 range: 依据 ID 长度而定 type: |
| :------ | :------ |
| `valueStyle?` `string` |  字段值样式 default: null range:不做限制 |
| `notListed?` `string` |  未上榜(如果未上榜也显示"名次"请填写null) default: null range:不做限制 |

#### Returns

| [`LeaderboardMainPanelBase`](mwext.LeaderboardMainPanelBase.md)<`T`\> | 返回自己，可用于链式调用 |
| :------ | :------ |
