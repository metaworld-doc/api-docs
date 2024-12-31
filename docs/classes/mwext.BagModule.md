[拓展](../groups/Extension.拓展.md) / BagModule

# BagModule <Badge type="tip" text="Class" /> <Score text="BagModule" />

背包实例

背包系统就像你在玩游戏时使用的一个特殊的背包，可以帮助你管理和存放各种物品和资源。MW编辑器已经封装好了一个可以直接使用的背包系统。

你的角色在游戏中收集了很多宝贵的物品，比如武器、装备、药品、材料等等。这些物品都需要一个地方来储存，而背包系统就是一个虚拟的背包，可以容纳这些物品。

它就是一个游戏中的特殊工具，帮助你整理、存储和管理你在游戏中收集到的各种物品和资源，让你的游戏体验更加方便和有序。

<span style="font-size: 14px;">
使用示例:创建一个名为BagExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏
</span>

```ts
@Component
export default class BagExample extends Script {
   protected onStart(): void {
      BagModule.registerItem(1,"37692","金铲铲",ItemQuality.Legend,10,{a:1,b:2});
      BagModule.registerItem(2,"37690","小喇叭",ItemQuality.Legend,10,{a:1,b:2});
      BagModule.registerItem(3,"37697","金币",ItemQuality.Legend,10,{a:1,b:2});
      BagModule.registerItem(4,"37695","南瓜",ItemQuality.Common,20,{a:1,b:2});
      if(SystemUtil.isClient()){
          BagModule.addItemClickListener(this.onItemClick,this);
          BagModule.addItem(1,1);
          BagModule.addItem(2,5);
          BagModule.addItem(3,10);
          BagModule.addItem(4,30);
          BagModule.open();
      }
   }
   private onItemClick(cfg:ItemConfig){
      console.log("点击了",cfg);
   }
}
```

## Table of contents

### Accessors <Score text="Accessors" /> 
| **[capacity](mwext.BagModule.md#capacity)**(): `number` <Badge type="tip" text="client" />  |
| :-----|
| 背包容量|
| **[dragEnabled](mwext.BagModule.md#dragenabled)**(): `boolean` <Badge type="tip" text="client" />  |
| 是否可以拖拽|
| **[labelVisible](mwext.BagModule.md#labelvisible)**(): `boolean` <Badge type="tip" text="client" />  |
| 物品名称是否可见|
| **[searchEnabled](mwext.BagModule.md#searchenabled)**(): `boolean` <Badge type="tip" text="client" />  |
| 是否显示搜索框|

### Methods <Score text="Methods" /> 
| **[addItem](mwext.BagModule.md#additem)**(`itemId`: `number`, `count?`: `number`, `player?`: [`Player`](mw.Player.md)): `Promise`<`number`\>   |
| :-----|
| 添加道具|
| **[addItemClickListener](mwext.BagModule.md#additemclicklistener)**(`clickCallback`: (`cfg`: [`ItemConfig`](../interfaces/mwext.ItemConfig.md)) => `void`, `thisObject`: `any`): typeof [`BagModule`](mwext.BagModule.md) <Badge type="tip" text="client" />  |
| 增加道具点击回调|
| **[close](mwext.BagModule.md#close)**(`player?`: [`Player`](mw.Player.md)): typeof [`BagModule`](mwext.BagModule.md)   |
| 关闭背包界面|
| **[getItemCount](mwext.BagModule.md#getitemcount)**(`itemId`: `number`, `player?`: [`Player`](mw.Player.md)): `number`   |
| 获取背包指定道具数量|
| **[open](mwext.BagModule.md#open)**(`player?`: [`Player`](mw.Player.md)): typeof [`BagModule`](mwext.BagModule.md)   |
| 打开背包界面|
| **[registerItem](mwext.BagModule.md#registeritem)**(`itemId`: `number`, `icon`: `string`, `name`: `string`, `quality?`: [`ItemQuality`](../enums/mwext.ItemQuality.md), `stackCount?`: `number`, `customData?`: `any`): typeof [`BagModule`](mwext.BagModule.md)   |
| 背包注册道具信息，道具需要在客户端注册|
| **[removeItem](mwext.BagModule.md#removeitem)**(`itemId`: `number`, `count?`: `number`, `player?`: [`Player`](mw.Player.md)): typeof [`BagModule`](mwext.BagModule.md)   |
| 删除道具|
| **[removeItemClickListener](mwext.BagModule.md#removeitemclicklistener)**(`clickCallback`: (`cfg`: [`ItemConfig`](../interfaces/mwext.ItemConfig.md)) => `void`, `thisObject`: `any`): typeof [`BagModule`](mwext.BagModule.md) <Badge type="tip" text="client" />  |
| 移除道具点击回调|
| **[skin](mwext.BagModule.md#skin)**(`bagSkin`: (...`args`: `any`[]) => [`IBagSkin`](mwext.IBagSkin.md), `itemSkin`: (...`args`: `any`[]) => [`IBagItemSkin`](../interfaces/mwext.IBagItemSkin.md), `itemBgSkin`: (...`args`: `any`[]) => [`UIScript`](mw.UIScript.md), `deleteDialogSkin`: (...`args`: `any`[]) => [`IItemDeleteSkin`](../interfaces/mwext.IItemDeleteSkin.md)): typeof [`BagModule`](mwext.BagModule.md) <Badge type="tip" text="client" />  |
| 设置背包皮肤|
| **[sort](mwext.BagModule.md#sort)**(): typeof [`BagModule`](mwext.BagModule.md) <Badge type="tip" text="client" />  |
| 整理背包|

## Accessors

### capacity <Score text="capacity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **capacity**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **capacity**(`capacity`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


背包容量

#### Returns

| `number` | 背包容量 |
| :------ | :------ |


</td>
<td style="text-align: left">


背包容量

#### Parameters

| `capacity` `number` | 背包容量 <br> range: [1,128] |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### dragEnabled <Score text="dragEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **dragEnabled**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **dragEnabled**(`isDragable`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


是否可以拖拽

#### Returns

| `boolean` | 返回是否可以拖拽 |
| :------ | :------ |


</td>
<td style="text-align: left">


是否可以拖拽

#### Parameters

| `isDragable` `boolean` | 是否可以拖拽 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### labelVisible <Score text="labelVisible" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **labelVisible**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **labelVisible**(`isLabelVisible`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


物品名称是否可见

#### Returns

| `boolean` | 返回物品名称是否可见 |
| :------ | :------ |


</td>
<td style="text-align: left">


物品名称是否可见

#### Parameters

| `isLabelVisible` | `boolean` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### searchEnabled <Score text="searchEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **searchEnabled**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **searchEnabled**(`isSearchEnabled`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


是否显示搜索框

#### Returns

| `boolean` | 返回是否显示搜索框 |
| :------ | :------ |


</td>
<td style="text-align: left">


是否显示搜索框

#### Parameters

| `isSearchEnabled` `boolean` | 是否显示搜索框 |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods

### addItem <Score text="addItem" /> 

• `Static` **addItem**(`itemId`, `count?`, `player?`): `Promise`<`number`\> 

添加道具

#### Parameters

| `itemId` `number` | 道具ID <br> range: 不做限制 type: 整形 |
| :------ | :------ |
| `count?` `number` | 道具数量 default:1 <br> range: 不做限制 type: 整形 |
| `player?` [`Player`](mw.Player.md) | 道具所有者 default:服务端必传入 |

#### Returns

| `Promise`<`number`\> | 返回添加的道具数量，如果添加失败则返回0 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个BagExample脚本并拖入对象管理器中，添加以下代码,运行项目
</span>

```ts
@Component
export default class BagExample extends Script {
   protected onStart(): void {
      BagModule.registerItem(1,"37692","金铲铲",ItemQuality.Legend,10,{a:1,b:2});
      if (SystemUtil.isServer()) return;
      BagModule.addItem(1).then((count:number)=>{
         console.log("添加道具数量",count);
      });
      BagModule.open();
   }
```

___

### addItemClickListener <Score text="addItemClickListener" /> 

• `Static` **addItemClickListener**(`clickCallback`, `thisObject`): typeof [`BagModule`](mwext.BagModule.md) <Badge type="tip" text="client" />

增加道具点击回调

#### Parameters

| `clickCallback` (`cfg`: [`ItemConfig`](../interfaces/mwext.ItemConfig.md)) => `void` | 点击回调 |
| :------ | :------ |
| `thisObject` `any` | 调用上下文 |

#### Returns

| typeof [`BagModule`](mwext.BagModule.md) | 返回背包实例 |
| :------ | :------ |

___

### close <Score text="close" /> 

• `Static` **close**(`player?`): typeof [`BagModule`](mwext.BagModule.md) 

关闭背包界面

#### Parameters

| `player?` [`Player`](mw.Player.md) | 服务端调用时需要传入player default:服务端必传入 |
| :------ | :------ |

#### Returns

| typeof [`BagModule`](mwext.BagModule.md) | 返回背包实例 |
| :------ | :------ |

___

### getItemCount <Score text="getItemCount" /> 

• `Static` **getItemCount**(`itemId`, `player?`): `number` 

获取背包指定道具数量

#### Parameters

| `itemId` `number` | 道具ID <br> range: 根据道具ID确定 type: 整形 |
| :------ | :------ |
| `player?` [`Player`](mw.Player.md) | 服务端传入，打开指定玩家的背包 default:服务端必传入 |

#### Returns

| `number` | 返回背包实例 |
| :------ | :------ |

___

### open <Score text="open" /> 

• `Static` **open**(`player?`): typeof [`BagModule`](mwext.BagModule.md) 

打开背包界面

#### Parameters

| `player?` [`Player`](mw.Player.md) | 背包的所有者 default:服务端填写，客户端不填写 |
| :------ | :------ |

#### Returns

| typeof [`BagModule`](mwext.BagModule.md) | 返回背包实例 |
| :------ | :------ |

___

### registerItem <Score text="registerItem" /> 

• `Static` **registerItem**(`itemId`, `icon`, `name`, `quality?`, `stackCount?`, `customData?`): typeof [`BagModule`](mwext.BagModule.md) 

背包注册道具信息，道具需要在客户端注册

#### Parameters

| `itemId` `number` | 道具ID <br> range: 根据道具ID确定 type: 整形 |
| :------ | :------ |
| `icon` `string` | 道具图片 <br> range: 不做限制 |
| `name` `string` | 名称 <br> range: 不做限制 |
| `quality?` [`ItemQuality`](../enums/mwext.ItemQuality.md) | 道具品质-默认普通 default:ItemQuality.Common |
| `stackCount?` `number` | 堆叠数量 default:1 <br> range: 不做限制 type: 整形 |
| `customData?` `any` | 额外数据 default:null |

#### Returns

| typeof [`BagModule`](mwext.BagModule.md) | 返回背包实例 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个BagExample脚本并拖入对象管理器中，添加以下代码
</span>

这样就注册了4个道具，然后通过BagModule.addItem添加对应ID在背包中就可以看到这4个道具了
```ts
@Component
export default class BagExample extends Script {

    protected onStart(): void {
        BagModule.registerItem(1,"37692","金铲铲",ItemQuality.Legend,10,{a:1,b:2});
        BagModule.registerItem(2,"37690","小喇叭",ItemQuality.Legend,10,{a:1,b:2});
        BagModule.registerItem(3,"37697","金币",ItemQuality.Legend,10,{a:1,b:2});
        BagModule.registerItem(4,"37695","南瓜",ItemQuality.Common,20,{a:1,b:2});
    }
}
```

___

### removeItem <Score text="removeItem" /> 

• `Static` **removeItem**(`itemId`, `count?`, `player?`): typeof [`BagModule`](mwext.BagModule.md) 

删除道具

#### Parameters

| `itemId` `number` | 道具ID <br> range: 根据道具ID确定 type: 整形 |
| :------ | :------ |
| `count?` `number` | 道具数量 default:1 <br> range: 不做限制 type: 整形 |
| `player?` [`Player`](mw.Player.md) | 道具所有者，服务端必传入 default:服务端必传入 |

#### Returns

| typeof [`BagModule`](mwext.BagModule.md) | 返回背包实例 |
| :------ | :------ |

___

### removeItemClickListener <Score text="removeItemClickListener" /> 

• `Static` **removeItemClickListener**(`clickCallback`, `thisObject`): typeof [`BagModule`](mwext.BagModule.md) <Badge type="tip" text="client" />

移除道具点击回调

#### Parameters

| `clickCallback` (`cfg`: [`ItemConfig`](../interfaces/mwext.ItemConfig.md)) => `void` | 点击回调 |
| :------ | :------ |
| `thisObject` `any` | 调用上下文 |

#### Returns

| typeof [`BagModule`](mwext.BagModule.md) | 返回背包实例 |
| :------ | :------ |

___

### skin <Score text="skin" /> 

• `Static` **skin**(`bagSkin`, `itemSkin`, `itemBgSkin`, `deleteDialogSkin`): typeof [`BagModule`](mwext.BagModule.md) <Badge type="tip" text="client" />

设置背包皮肤

#### Parameters

| `bagSkin` (...`args`: `any`[]) => [`IBagSkin`](mwext.IBagSkin.md) | 背包UI皮肤,null为默认皮肤 |
| :------ | :------ |
| `itemSkin` (...`args`: `any`[]) => [`IBagItemSkin`](../interfaces/mwext.IBagItemSkin.md) | 背包Item皮肤,null为默认皮肤 |
| `itemBgSkin` (...`args`: `any`[]) => [`UIScript`](mw.UIScript.md) | 背包Item背景皮肤,null为默认皮肤 |
| `deleteDialogSkin` (...`args`: `any`[]) => [`IItemDeleteSkin`](../interfaces/mwext.IItemDeleteSkin.md) | 背包Item删除弹窗皮肤,null为默认皮肤 |

#### Returns

| typeof [`BagModule`](mwext.BagModule.md) | 返回背包实例 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:
</span>

1.在项目中创建一个UI,名为BagUI,拖入以下控件
closeBtn: mw.StaleButton;
content: mw.Canvas;
filterBox: mw.InputBox;
filterCanvas: mw.Canvas;
2.导出UI,将导出的UI文件BagUI_Generate拷贝到JavaScripts文件夹,重命名为BagSkin,并修改extends为BagUI
创建一个名为BagExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏
3.其他UI皮肤同理
```ts
@Component
export default class BagExample extends Script {

    protected onStart(): void {
        if (!SystemUtil.isServer()) return;
        BagModule.skin(BagSkin, null, null, null);
        BagModule.open();
    }
}
```

___

### sort <Score text="sort" /> 

• `Static` **sort**(): typeof [`BagModule`](mwext.BagModule.md) <Badge type="tip" text="client" />

整理背包

#### Returns

| typeof [`BagModule`](mwext.BagModule.md) | 返回背包实例 |
| :------ | :------ |
