[设置](../groups/设置.设置.md) / AvatarSettings

# AvatarSettings <Badge type="tip" text="Class" /> <Score text="AvatarSettings" />

控制一些优化项的开启关闭

<span style="font-size: 14px;">
使用示例:创建一个名为"ClassExample"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在服务器Log中看到对应方法调用信息。代码如下：
</span>

```ts
@Component
export default class ClassExample extends Script {

    protected onStart(): void {
       this.RoomSettings();
    }

    public RoomSettings(){
       let opt = AvatarSettings.optimizationEnabled;
       console.log("角色优化是否开启：" + opt);
    }
}
```

## Table of contents

### Accessors <Score text="Accessors" /> 
| **[optimizationEnabled](mw.AvatarSettings.md#optimizationenabled)**(): `boolean` <Badge type="tip" text="client" />  |
| :-----|
| 开启或关闭角色优化:通过动态限制骨架网格体组件的tick频率来限制运行动画数据的时间。|

### Methods <Score text="Methods" /> 
| **[getAvatarForcedLOD](mw.AvatarSettings.md#getavatarforcedlod)**(`character`: [`Character`](mw.Character.md)): `number` <Badge type="tip" text="client" />  |
| :-----|
| 获取角色形象细节层次，0 表示  自动切换。 1， 2， 3 表示 3个等级，Level1细节最多。|
| **[setAvatarForcedLOD](mw.AvatarSettings.md#setavatarforcedlod)**(`character`: [`Character`](mw.Character.md), `level`: `number`): `void` <Badge type="tip" text="client" />  |
| 设置角色形象细节层次，0 表示  自动切换。 1， 2， 3 表示 3个等级，Level1细节最多。|
| **[setOptimization](mw.AvatarSettings.md#setoptimization)**(`character`: [`Character`](mw.Character.md), `useAnimationBudget`: `boolean`, `useWave`: `boolean`): `void` <Badge type="tip" text="client" />  |
| 开启或关闭角色优化:通过动态限制骨架网格体组件的tick频率来限制运行动画数据的时间。|

## Accessors

### optimizationEnabled <Score text="optimizationEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **optimizationEnabled**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **optimizationEnabled**(`isEnabled`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


开启或关闭角色优化:通过动态限制骨架网格体组件的tick频率来限制运行动画数据的时间。

#### Returns

| `boolean` | boolean:角色优化是否开启,如果返回值为undefined，请检查是否在客户端调用,默认值是:true |
| :------ | :------ |


</td>
<td style="text-align: left">


开启或关闭角色优化:通过动态限制骨架网格体组件的tick频率来限制运行动画数据的时间。

#### Parameters

| `isEnabled` `boolean` | 是否开启或关闭角色优化 |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods

### getAvatarForcedLOD <Score text="getAvatarForcedLOD" /> 

• `Static` **getAvatarForcedLOD**(`character`): `number` <Badge type="tip" text="client" />

获取角色形象细节层次，0 表示  自动切换。 1， 2， 3 表示 3个等级，Level1细节最多。

#### Parameters

| `character` [`Character`](mw.Character.md) | 角色对象 |
| :------ | :------ |

#### Returns

| `number` | level usage:Lod等级：0 表示  自动切换。 1， 2， 3 表示 3个等级 |
| :------ | :------ |

___

### setAvatarForcedLOD <Score text="setAvatarForcedLOD" /> 

• `Static` **setAvatarForcedLOD**(`character`, `level`): `void` <Badge type="tip" text="client" />

设置角色形象细节层次，0 表示  自动切换。 1， 2， 3 表示 3个等级，Level1细节最多。

#### Parameters

| `character` [`Character`](mw.Character.md) | 角色对象 |
| :------ | :------ |
| `level` `number` | Lod等级：0 表示 自动切换。 1， 2， 3 表示 3个等级 range:[0, 3] type: 整形 |


___

### setOptimization <Score text="setOptimization" /> 

• `Static` **setOptimization**(`character`, `useAnimationBudget`, `useWave`): `void` <Badge type="tip" text="client" />

开启或关闭角色优化:通过动态限制骨架网格体组件的tick频率来限制运行动画数据的时间。

#### Parameters

| `character` [`Character`](mw.Character.md) | 角色对象 |
| :------ | :------ |
| `useAnimationBudget` `boolean` | 是否开启或关闭角色动画预算分配器 |
| `useWave` `boolean` | 该参数现已弃用 |

