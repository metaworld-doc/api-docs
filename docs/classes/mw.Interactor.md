[玩法](../groups/玩法.玩法.md) / Interactor

# Interactor <Badge type="tip" text="Class" /> <Score text="Interactor" />

交互物，请保证交互前动画资源已加载，否则可能导致位置错误或者其他不可预料的表现

<span style="font-size: 14px;">
使用示例:创建一个名为"InteractorSample"的脚本，放置在对象管理器某一交互物的子级中，打开脚本，输入以下代码保存，在本地资源库中搜索4175动画资源，拖入对象管理器中的优先加载目录。运行游戏，你将在场景中看到一个交互物的效果，玩家可以和此交互物进行交互，代码如下：
</span>

```ts
 @Component
export default class InteractorSample extends Script {
    protected async onStart(): Promise<void> {
        const interObj = this.gameObject as Interactor;
        // 开始交互回调
        interObj.onEnter.add(() => {
            console.log("onEnter")
            console.log("onEnter ", interObj.getCurrentCharacter())
            console.log("onEnter ", interObj.occupied)
        })
        interObj.slot = HumanoidSlotType.Buttocks;
        interObj.animationId = "4175";

        // 结束交互回调
        interObj.onLeave.add(() => {
            console.log("onLeave")
        })
        if (SystemUtil.isClient()) {
            InputUtil.onKeyDown(Keys.One, () => {
                interObj.enter(Player.localPlayer.character, HumanoidSlotType.Buttocks, "4175");
            })
            InputUtil.onKeyDown(Keys.Two, () => {
                // 不传退出交互时会自动回到交互前的坐标和旋转
                interObj.leave();
            })
        }
    }
}
```

## Hierarchy

- [`GameObject`](mw.GameObject.md)

  ↳ **`Interactor`**

## Table of contents

### Properties <Score text="Properties" /> 
| **[onEnter](mw.Interactor.md#onenter)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\>  |
| :-----|
| 交互开始时执行绑定函数。通常与 enter 成对使用，使用示例详见方法 enter 中示例代码。|
| **[onLeave](mw.Interactor.md#onleave)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\>  |
| 交互结束时执行绑定函数。通常与 leave 成对使用，使用示例详见方法 leave 中示例代码。|


::: details click
### Properties <Score text="Properties" /> 
| **[onBeforeDestroyDelegate](mw.GameObject.md#onbeforedestroydelegate)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\>   |
| :-----|
| 物体销毁前事件回调|
| **[onCustomPropertyChange](mw.GameObject.md#oncustompropertychange)**: `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> <Badge type="tip" text="other" />  |
| 监听自定义属性同步事件|
| **[onDestroyDelegate](mw.GameObject.md#ondestroydelegate)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\>   |
| 物体销毁后事件回调|
:::


### Accessors <Score text="Accessors" /> 
| **[animationId](mw.Interactor.md#animationid)**(): `string`  |
| :-----|
| 交互动画资源 id|
| **[nonHumanoidAnimationId](mw.Interactor.md#nonhumanoidanimationid)**(): `string`  |
| 交互非人形动画资源 id|
| **[nonHumanoidSlot](mw.Interactor.md#nonhumanoidslot)**(): [`NonHumanoidSlotType`](../enums/mw.NonHumanoidSlotType.md)  |
| 交互物非人形插槽|
| **[occupied](mw.Interactor.md#occupied)**(): `boolean`  |
| 该交互物的交互状态|
| **[slot](mw.Interactor.md#slot)**(): [`HumanoidSlotType`](../enums/mw.HumanoidSlotType.md)  |
| 交互物插槽|


::: details click
### Accessors <Score text="Accessors" /> 
| **[actorLevel](mw.GameObject.md#actorlevel)**(): `number` <Badge type="tip" text="other" />  |
| :-----|
| 获取Actor等级|
| **[assetId](mw.GameObject.md#assetid)**(): `string`   |
| 获取当前物体使用资源的GUID|
| **[gameObjectId](mw.GameObject.md#gameobjectid)**(): `string`   |
| 获取物体的唯一标识（唯一标识一个对象的字符串）。|
| **[isDestroyed](mw.GameObject.md#isdestroyed)**(): `boolean`   |
| 当前物体是否被销毁|
| **[isReady](mw.GameObject.md#isready)**(): `boolean`   |
| 当前物体状态|
| **[localTransform](mw.GameObject.md#localtransform)**(): [`Transform`](mw.Transform.md)   |
| 当前物体本地变换|
| **[name](mw.GameObject.md#name)**(): `string`   |
| 返回当前物体名称|
| **[netStatus](mw.GameObject.md#netstatus)**(): [`NetStatus`](../enums/mw.NetStatus.md)   |
| 获取当前物体同步状态|
| **[parent](mw.GameObject.md#parent)**(): [`GameObject`](mw.GameObject.md)   |
| 获取当前父物体|
| **[sceneCaptureTag](mw.GameObject.md#scenecapturetag)**(): `string`   |
| 获取当前物体的捕捉标签|
| **[tag](mw.GameObject.md#tag)**(): `string`   |
| 获取当前物体的标签|
| **[worldTransform](mw.GameObject.md#worldtransform)**(): [`Transform`](mw.Transform.md)   |
| 当前物体世界变换|
:::


### Methods <Score text="Methods" /> 
| **[enter](mw.Interactor.md#enter)**(`character`: [`Character`](mw.Character.md), `slot?`: [`HumanoidSlotType`](../enums/mw.HumanoidSlotType.md)  [`NonHumanoidSlotType`](../enums/mw.NonHumanoidSlotType.md), `animationId?`: `string`): `boolean` <Badge type="tip" text="other" />  |
| :-----|
| 开始交互，请保证交互前动画资源已加载，否则可能导致位置错误或者其他不可预料的表现|
| **[getCurrentCharacter](mw.Interactor.md#getcurrentcharacter)**(): [`Character`](mw.Character.md)   |
| 获取正在交互的角色|
| **[leave](mw.Interactor.md#leave)**(`position?`: [`Vector`](mw.Vector.md), `rotation?`: [`Rotation`](mw.Rotation.md), `animationId?`: `string`): `boolean` <Badge type="tip" text="other" />  |
| 结束交互。通常与 enter 成对使用，使用示例详见方法 enter 中示例代码。|


::: details click
### Methods <Score text="Methods" /> 
| **[addComponent](mw.GameObject.md#addcomponent)**<`T`: extends [`Script`](mw.Script.md)<`T`\>\>(`constructor`: (...`args`: `unknown`[]) => `T`: extends [`Script`](mw.Script.md)<`T`\>, `bInReplicates?`: `boolean`): `T`: extends [`Script`](mw.Script.md)<`T`\>   |
| :-----|
| 添加一个脚本组件|
| **[asyncGetChildByName](mw.GameObject.md#asyncgetchildbyname)**(`name`: `string`): `Promise`<[`GameObject`](mw.GameObject.md)\>   |
| 异步根据名称查找子物体|
| **[asyncReady](mw.GameObject.md#asyncready)**(): `Promise`<[`GameObject`](mw.GameObject.md)\>   |
| 物体准备好后返回|
| **[clone](mw.GameObject.md#clone)**(`gameObjectInfo?`: [`GameObjectInfo`](../interfaces/mw.GameObjectInfo.md)): [`GameObject`](mw.GameObject.md)   |
| 复制对象|
| **[destroy](mw.GameObject.md#destroy)**(): `void`   |
| 删除对象|
| **[getBoundingBox](mw.GameObject.md#getboundingbox)**(`nonColliding?`: `boolean`, `includeFromChild?`: `boolean`, `outer?`: [`Vector`](mw.Vector.md)): [`Vector`](mw.Vector.md)   |
| 获取物体包围盒大小|
| **[getBounds](mw.GameObject.md#getbounds)**(`onlyCollidingComponents`: `boolean`, `originOuter`: [`Vector`](mw.Vector.md), `boxExtentOuter`: [`Vector`](mw.Vector.md), `includeFromChild?`: `boolean`): `void`   |
| 获取物体边界|
| **[getChildByGameObjectId](mw.GameObject.md#getchildbygameobjectid)**(`gameObjectId`: `string`): [`GameObject`](mw.GameObject.md)   |
| 根据 gameObjectId 查找子物体|
| **[getChildByName](mw.GameObject.md#getchildbyname)**(`name`: `string`): [`GameObject`](mw.GameObject.md)   |
| 根据名称查找子物体|
| **[getChildByPath](mw.GameObject.md#getchildbypath)**(`path`: `string`): [`GameObject`](mw.GameObject.md)   |
| 根据路径查找子物体|
| **[getChildren](mw.GameObject.md#getchildren)**(): [`GameObject`](mw.GameObject.md)[]   |
| 获取子物体|
| **[getChildrenByName](mw.GameObject.md#getchildrenbyname)**(`name`: `string`): [`GameObject`](mw.GameObject.md)[]   |
| 通过名字查找所有的子物体|
| **[getComponent](mw.GameObject.md#getcomponent)**<`T`: extends [`Script`](mw.Script.md)<`T`\>\>(`constructor?`: (...`args`: `unknown`[]) => `T`: extends [`Script`](mw.Script.md)<`T`\>): `T`: extends [`Script`](mw.Script.md)<`T`\>   |
| 获取指定类型的组件|
| **[getComponentPropertys](mw.GameObject.md#getcomponentpropertys)**<`T`: extends [`Script`](mw.Script.md)<`T`\>\>(`constructor`: (...`args`: `unknown`[]) => `T`: extends [`Script`](mw.Script.md)<`T`\>): `Map`<`string`, `IPropertyOptions`\>   |
| 获取脚本组件属性|
| **[getComponents](mw.GameObject.md#getcomponents)**<`T`: extends [`Script`](mw.Script.md)<`T`\>\>(`constructor?`: (...`args`: `unknown`[]) => `T`: extends [`Script`](mw.Script.md)<`T`\>): `T`: extends [`Script`](mw.Script.md)<`T`\>[]   |
| 获取指定类型的所有组件|
| **[getCustomProperties](mw.GameObject.md#getcustomproperties)**(): `string`[]   |
| 获取自定义属性名字数组，返回对象所有自定义属性。|
| **[getCustomProperty](mw.GameObject.md#getcustomproperty)**<`T`: extends [`CustomPropertyType`](../modules/Core.mw.md#custompropertytype)\>(`propertyName`: `string`): `T`: extends [`CustomPropertyType`](../modules/Core.mw.md#custompropertytype)   |
| 获取自定义属性的值，服务器客户端均可调用，客户端调用需注意属性同步的延迟。|
| **[getCustomPropertyChangeDelegate](mw.GameObject.md#getcustompropertychangedelegate)**(`property`): `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> <Badge type="tip" text="client" />  |
| 获取给定自定义属性修改时触发的事件代理。双端对象在服务器修改自定义属性后，双端均会触发事件并执行绑定函数。|
| **[getVisibility](mw.GameObject.md#getvisibility)**(): `boolean`   |
| 获取物体是否被显示|
| **[isPrefabActor](mw.GameObject.md#isprefabactor)**(): `boolean`   |
| 返回当前物体是否为预制体|
| **[moveBy](mw.GameObject.md#moveby)**(`velocity`: [`Vector`](mw.Vector.md), `isLocal?`: `boolean`): `void` <Badge type="tip" text="other" />  |
| 按给定的速度矢量随时间平滑地移动对象|
| **[moveTo](mw.GameObject.md#moveto)**(`targetPosition`: [`Vector`](mw.Vector.md), `time`: `number`, `isLocal?`: `boolean`, `onComplete?`: () => `void`): `void` <Badge type="tip" text="other" />  |
| 在指定时间内从当前位置平滑移动至目标位置|
| **[rotateBy](mw.GameObject.md#rotateby)**(`rotation`: [`Quaternion`](mw.Quaternion.md)  [`Rotation`](mw.Rotation.md), `multiplier`: `number`, `isLocal?`: `boolean`): `void` <Badge type="tip" text="other" />  |
| 按给定的旋转量随时间平滑地旋转对象|
| **[rotateTo](mw.GameObject.md#rotateto)**(`targetRotation`: [`Quaternion`](mw.Quaternion.md)  [`Rotation`](mw.Rotation.md), `time`: `number`, `isLocal?`: `boolean`, `onComplete?`: () => `void`): `void` <Badge type="tip" text="other" />  |
| 在指定时间内从当前旋转平滑变化至目标旋转|
| **[scaleBy](mw.GameObject.md#scaleby)**(`scale`: [`Vector`](mw.Vector.md), `isLocal?`: `boolean`): `void` <Badge type="tip" text="other" />  |
| 按每秒给定的缩放矢量随时间平滑缩放对象|
| **[scaleTo](mw.GameObject.md#scaleto)**(`targetScale`: [`Vector`](mw.Vector.md), `time`: `number`, `isLocal?`: `boolean`, `onComplete?`: () => `void`): `void` <Badge type="tip" text="other" />  |
| 在指定时间内从当前缩放平滑变化至目标缩放|
| **[setAbsolute](mw.GameObject.md#setabsolute)**(`absolutePosition?`: `boolean`, `absoluteRotation?`: `boolean`, `absoluteScale?`: `boolean`): `void`   |
| 设置物体localTransform是相对于父物体或者世界|
| **[setCustomProperty](mw.GameObject.md#setcustomproperty)**(`propertyName`: `string`, `value`: `undefined`  [`CustomPropertyType`](../modules/Core.mw.md#custompropertytype)): `void` <Badge type="tip" text="server" />  |
| 设置自定义属性的值，双端对象需在服务器调用。当设置的属性不存在时会新增自定义属性。|
| **[setVisibility](mw.GameObject.md#setvisibility)**(`status`: `boolean`  [`PropertyStatus`](../enums/mw.PropertyStatus.md), `propagateToChildren?`: `boolean`): `void`   |
| 设置物体是否被显示|
| **[stopMove](mw.GameObject.md#stopmove)**(): `void` <Badge type="tip" text="other" />  |
| 中断moveTo()、moveBy()的进一步移动|
| **[stopRotate](mw.GameObject.md#stoprotate)**(): `void` <Badge type="tip" text="other" />  |
| 中断从rotateTo()或rotateBy()的进一步旋转|
| **[stopScale](mw.GameObject.md#stopscale)**(): `void` <Badge type="tip" text="other" />  |
| 中断从ScaleTo()或ScaleBy()的进一步缩放|
| **[asyncFindGameObjectById](mw.GameObject.md#asyncfindgameobjectbyid)**(`gameObjectId`: `string`): `Promise`<[`GameObject`](mw.GameObject.md)\>   |
| 通过 gameObjectId 异步查找 GameObject|
| **[asyncGetGameObjectByPath](mw.GameObject.md#asyncgetgameobjectbypath)**(`path`: `string`): `Promise`<[`GameObject`](mw.GameObject.md)\>   |
| 通过路径异步查找物体|
| **[asyncSpawn](mw.GameObject.md#asyncspawn)**<`T`: extends [`GameObject`](mw.GameObject.md)<`T`\>\>(`assetId`: `string`, `gameObjectInfo?`: [`GameObjectInfo`](../interfaces/mw.GameObjectInfo.md)): `Promise`<`T`: extends [`GameObject`](mw.GameObject.md)<`T`\>\>   |
| 异步构造一个物体|
| **[bulkPivotTo](mw.GameObject.md#bulkpivotto)**(`gameObjects`: [`GameObject`](mw.GameObject.md)[], `transforms`: [`Transform`](mw.Transform.md)[]): `void`   |
| 批量设置位置|
| **[findGameObjectById](mw.GameObject.md#findgameobjectbyid)**(`gameObjectId`: `string`): [`GameObject`](mw.GameObject.md)   |
| 通过 gameObjectId 查找物体|
| **[findGameObjectByName](mw.GameObject.md#findgameobjectbyname)**(`name`: `string`): [`GameObject`](mw.GameObject.md)   |
| 通过名字查找物体|
| **[findGameObjectsByName](mw.GameObject.md#findgameobjectsbyname)**(`name`: `string`): [`GameObject`](mw.GameObject.md)[]   |
| 通过名字查找物体|
| **[findGameObjectsByTag](mw.GameObject.md#findgameobjectsbytag)**(`tag`: `string`): [`GameObject`](mw.GameObject.md)[]   |
| 通过自定义标签获取物体|
| **[getGameObjectByPath](mw.GameObject.md#getgameobjectbypath)**(`path`: `string`): [`GameObject`](mw.GameObject.md)   |
| 通过路径查找物体|
| **[spawn](mw.GameObject.md#spawn)**<`T`: extends [`GameObject`](mw.GameObject.md)<`T`\>\>(`assetId`: `string`, `gameObjectInfo?`: [`GameObjectInfo`](../interfaces/mw.GameObjectInfo.md)): `T`: extends [`GameObject`](mw.GameObject.md)<`T`\>   |
| 构造一个物体|
:::


## Properties

___

### onEnter <Score text="onEnter" /> 

• **onEnter**: [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\>

交互开始时执行绑定函数。通常与 enter 成对使用，使用示例详见方法 enter 中示例代码。

::: warning Precautions

会自动广播，若是双端对象，则可以在任意客户端调用

:::

___

### onLeave <Score text="onLeave" /> 

• **onLeave**: [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\>

交互结束时执行绑定函数。通常与 leave 成对使用，使用示例详见方法 leave 中示例代码。

::: warning Precautions

会自动广播，若是双端对象，则可以在任意客户端调用

:::

## Accessors

___

### animationId <Score text="animationId" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **animationId**(): `string`

</th>
<th style="text-align: left">

• `set` **animationId**(`assetGuid`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


交互动画资源 id

#### Returns

| `string` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


交互动画资源 id

#### Parameters

| `assetGuid` | `string` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### nonHumanoidAnimationId <Score text="nonHumanoidAnimationId" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **nonHumanoidAnimationId**(): `string`

</th>
<th style="text-align: left">

• `set` **nonHumanoidAnimationId**(`assetGuid`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


交互非人形动画资源 id

#### Returns

| `string` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


交互非人形动画资源 id

#### Parameters

| `assetGuid` | `string` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### nonHumanoidSlot <Score text="nonHumanoidSlot" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **nonHumanoidSlot**(): [`NonHumanoidSlotType`](../enums/mw.NonHumanoidSlotType.md)

</th>
<th style="text-align: left">

• `set` **nonHumanoidSlot**(`value`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


交互物非人形插槽

#### Returns

| [`NonHumanoidSlotType`](../enums/mw.NonHumanoidSlotType.md) |  |
| :------ | :------ |


</td>
<td style="text-align: left">


交互物非人形插槽

#### Parameters

| `value` | [`NonHumanoidSlotType`](../enums/mw.NonHumanoidSlotType.md) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### occupied <Score text="occupied" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **occupied**(): `boolean`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


该交互物的交互状态

#### Returns

| `boolean` |  |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### slot <Score text="slot" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **slot**(): [`HumanoidSlotType`](../enums/mw.HumanoidSlotType.md)

</th>
<th style="text-align: left">

• `set` **slot**(`value`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


交互物插槽

#### Returns

| [`HumanoidSlotType`](../enums/mw.HumanoidSlotType.md) |  |
| :------ | :------ |


</td>
<td style="text-align: left">


交互物插槽

#### Parameters

| `value` | [`HumanoidSlotType`](../enums/mw.HumanoidSlotType.md) |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods

___

### enter <Score text="enter" /> 

• **enter**(`character`, `slot?`, `animationId?`): `boolean` <Badge type="tip" text="other" />

开始交互，请保证交互前动画资源已加载，否则可能导致位置错误或者其他不可预料的表现

#### Parameters

| `character` [`Character`](mw.Character.md) |  要交互的角色（可以是玩家，也可以是AI） |
| :------ | :------ |
| `slot?` [`HumanoidSlotType`](../enums/mw.HumanoidSlotType.md)  [`NonHumanoidSlotType`](../enums/mw.NonHumanoidSlotType.md) |  交互插槽，不传默认以属性 slot 为准 default: 属性 slot |
| `animationId?` `string` |  交互姿态，不传默认以属性 animationId 为准 default: 属性 animationId range: 依据动画资源 ID 决定字符串长度 |

#### Returns

| `boolean` | 是否成功交互，异步逻辑，返回值不代表已经完成交互，如需确保已经完成交互，请使用 onEnter 委托 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为"InteractorStartEndSample"的脚本，放置在对象管理器某一交互物的子级中，打开脚本，输入以下代码保存，运行游戏，你将在场景中看到一个交互物的效果，玩家可以和此交互物进行交互，代码如下：
</span>

```ts
@Component
export default class InteractorStartEndSample extends Script {
    protected async onStart(): Promise<void> {
        const interObj = this.gameObject as Interactor;
        // 开始交互回调
        interObj.onEnter.add(() => {
            console.log("onEnter")
        })
        // 结束交互回调
        interObj.onLeave.add(() => {
            console.log("onLeave")
        })
        if (SystemUtil.isClient()) {
            InputUtil.onKeyDown(Keys.One, () => {
                interObj.enter(Player.localPlayer.character, HumanoidSlotType.Buttocks, "4175");
            })
            InputUtil.onKeyDown(Keys.Two, () => {
                // 不传退出交互时会自动回到交互前的坐标和旋转
                interObj.leave();
            })
        }
    }
}
```

___

### getCurrentCharacter <Score text="getCurrentCharacter" /> 

• **getCurrentCharacter**(): [`Character`](mw.Character.md) 

获取正在交互的角色

#### Returns

| [`Character`](mw.Character.md) | true：为交互中 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为"InteractorGetInteractCharacterSample"的脚本，放置在对象管理器某一交互物的子级中，打开脚本，输入以下代码保存，运行游戏，你将在场景中看到一个交互物的效果，玩家可以和此交互物进行交互，代码如下：
</span>

```ts
@Component
export default class InteractorGetInteractCharacterSample extends Script {
    protected async onStart(): Promise<void> {
        const interObj = this.gameObject as Interactor;
        // 开始交互回调
        interObj.onEnter.add(() => {
            console.log(`onEnter status: ${interObj.getCurrentCharacter()}`)
        })
        // 省略开始交互代码
    }
}
```

___

### leave <Score text="leave" /> 

• **leave**(`position?`, `rotation?`, `animationId?`): `boolean` <Badge type="tip" text="other" />

结束交互。通常与 enter 成对使用，使用示例详见方法 enter 中示例代码。

#### Parameters

| `position?` [`Vector`](mw.Vector.md) |  结束位置 default: 玩家开始交互前的坐标为准 |
| :------ | :------ |
| `rotation?` [`Rotation`](mw.Rotation.md) |  结束旋转量 default: 玩家开始交互前的旋转为准，如果玩家开始前的姿态是倾斜的，内部不会纠正 |
| `animationId?` `string` |  新姿态，default: 玩家开始交互前的姿态（动画会转姿态） range: 依据动画资源 ID 决定字符串长度 |

#### Returns

| `boolean` | true 代表触发了结束交互逻辑，异步操作，返回值不能代表结束交互逻辑已经成功，如需保证结束交互逻辑完成才执行时，请使用 onLeave 委托 |
| :------ | :------ |
