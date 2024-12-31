[场景](../groups/场景.场景.md) / Effect

# Effect <Badge type="tip" text="Class" /> <Score text="Effect" />

特效

通常用于游戏场景中的效果表现，如火焰，水流，武器拖尾等，当编辑器细节面板勾选自动启用时，运行游戏会自动播放特效。

如需精确控制特效的播放与停止，请使用 play 和 stop 方法。不同特效有不同的生命周期，部分特效可通过细节面板中参数调节。

<span style="font-size: 14px;">
使用示例:创建一个名为"EffectExample"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中看到粒子特效炸裂的效果。代码如下：
</span>

```ts
@Component
export default class EffectExample extends Script {

    private readonly effect = {
        assetID: "145884",
        object: null as mw.Effect,
    };

    protected onStart(): void {
        this.createEffect();
    }

    @RemoteFunction(Client)
    public async createEffect(): Promise<void> {
        const success = await mw.AssetUtil.asyncDownloadAsset(this.effect.assetID);
            if (success) {
                // 下载完毕创建特效
                this.effect.object = await mw.GameObject.asyncSpawn(this.effect.assetID) as mw.Effect;

                // 设置特效transform
                const transform = new mw.Transform(new mw.Vector(500, 0, 0), new mw.Rotation(0, 0, 0), new mw.Vector(1, 1, 1));
                this.effect.object.localTransform = transform;

                // 播放特效
                this.effect.object.play();
                // 设置特效参数Life标量值
                this.effect.object.setFloat("LifeTime", 10);
                // 设置特效参数Speed向量值
                this.effect.object.setVector("Speed", new mw.Vector(0,0,150));
                // 设置特效参数Color颜色值
                this.effect.object.setColor("Color", new mw.LinearColor(1,0,0,1));
            }
    }
}
```

## Hierarchy

- [`GameObject`](mw.GameObject.md)

  ↳ **`Effect`**

## Table of contents

### Properties <Score text="Properties" /> 
| **[onFinish](mw.Effect.md#onfinish)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\>  |
| :-----|
| 特效播放完毕事件|


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
| **[duration](mw.Effect.md#duration)**(): `number` <Badge type="tip" text="client" />  |
| :-----|
| 获取特效循环次数，仅对非永久循环特效有效|
| **[loopCount](mw.Effect.md#loopcount)**(): `number` <Badge type="tip" text="client" />  |
| 获取特效循环次数，仅对非永久循环特效有效|
| **[timeLength](mw.Effect.md#timelength)**(): `number` <Badge type="tip" text="client" />  |
| 获取特效单次播放时长(s)|


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
| **[forceStop](mw.Effect.md#forcestop)**(): `void`   |
| :-----|
| 强制停止特效，所有粒子全部销毁|
| **[play](mw.Effect.md#play)**(`onSuccess?`: () => `void`): `void`   |
| 播放特效|
| **[setColor](mw.Effect.md#setcolor)**(`parameterName`: `string`, `value`: [`LinearColor`](mw.LinearColor.md)): `void` <Badge type="tip" text="client" />  |
| 设置特效颜色参数值|
| **[setColorRandom](mw.Effect.md#setcolorrandom)**(`parameterName`: `string`, `maxValue`: [`LinearColor`](mw.LinearColor.md), `minValue`: [`LinearColor`](mw.LinearColor.md)): `void` <Badge type="tip" text="client" />  |
| 设置特效颜色参数随机|
| **[setCullDistance](mw.Effect.md#setculldistance)**(`inCullDistance`: `number`): `void` <Badge type="tip" text="client" />  |
| 与玩家之间超出此距离的对象将被剪裁，最终的裁剪距离会和画质等级有关；修改此属性≤0时，裁剪距离会根据对象尺寸自动调整(自动启用CullDistanceVolume功能)|
| **[setFloat](mw.Effect.md#setfloat)**(`parameterName`: `string`, `value`: `number`): `void` <Badge type="tip" text="client" />  |
| 设置特效标量参数值|
| **[setFloatRandom](mw.Effect.md#setfloatrandom)**(`parameterName`: `string`, `maxValue`: `number`, `minValue`: `number`): `void` <Badge type="tip" text="client" />  |
| 设置特效标量参数随机|
| **[setVector](mw.Effect.md#setvector)**(`parameterName`: `string`, `value`: [`Vector`](mw.Vector.md)): `void` <Badge type="tip" text="client" />  |
| 设置特效向量参数值|
| **[setVectorRandom](mw.Effect.md#setvectorrandom)**(`parameterName`: `string`, `maxValue`: [`Vector`](mw.Vector.md), `minValue`: [`Vector`](mw.Vector.md)): `void` <Badge type="tip" text="client" />  |
| 设置特效向量参数范围随机，在一定范围内取向量的随机值|
| **[stop](mw.Effect.md#stop)**(): `void`   |
| 停止特效，不影响已经生成的粒子|


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

### onFinish <Score text="onFinish" /> 

• **onFinish**: [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\>

特效播放完毕事件

## Accessors

___

### duration <Score text="duration" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **duration**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **duration**(`NewDuration`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取特效循环次数，仅对非永久循环特效有效

#### Returns

| `number` | 循环的次数 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置特效持续时间，仅对循环特效有效

#### Parameters

| `NewDuration` `number` | 播放的时间 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### loopCount <Score text="loopCount" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **loopCount**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **loopCount**(`NewLoopCount`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取特效循环次数，仅对非永久循环特效有效

#### Returns

| `number` | 循环的次数 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置特效循环次数，仅对非永久循环特效有效

#### Parameters

| `NewLoopCount` `number` | 循环的次数 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### timeLength <Score text="timeLength" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **timeLength**(): `number` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取特效单次播放时长(s)

#### Returns

</td>
</tr></tbody>
</table>

| `number` | 特效单次播放时长 |
| :------ | :------ |

## Methods

___

### forceStop <Score text="forceStop" /> 

• **forceStop**(): `void` 

强制停止特效，所有粒子全部销毁


___

### play <Score text="play" /> 

• **play**(`onSuccess?`): `void` 

播放特效

#### Parameters

| `onSuccess?` () => `void` | 特效播放完成后回调 default: null |
| :------ | :------ |


___

### setColor <Score text="setColor" /> 

• **setColor**(`parameterName`, `value`): `void` <Badge type="tip" text="client" />

设置特效颜色参数值

#### Parameters

| `parameterName` `string` | 参数名 range: 想要设置的颜色参数值对应的字段 |
| :------ | :------ |
| `value` [`LinearColor`](mw.LinearColor.md) | 颜色变量 |


特效颜色参数为特效选中之后右侧属性面板“特效参数控制”中的"color"字段。

存在一个特效可以设置多个颜色属性的情况，如："color01"、"color02"。

___

### setColorRandom <Score text="setColorRandom" /> 

• **setColorRandom**(`parameterName`, `maxValue`, `minValue`): `void` <Badge type="tip" text="client" />

设置特效颜色参数随机

#### Parameters

| `parameterName` `string` | 参数名 range: 想要设置的颜色参数值对应的字段 |
| :------ | :------ |
| `maxValue` [`LinearColor`](mw.LinearColor.md) | 颜色变量最大值 |
| `minValue` [`LinearColor`](mw.LinearColor.md) | 颜色变量最小值 |


特效颜色参数为特效选中之后右侧属性面板“特效参数控制”中的"color"字段。

___

### setCullDistance <Score text="setCullDistance" /> 

• **setCullDistance**(`inCullDistance`): `void` <Badge type="tip" text="client" />

与玩家之间超出此距离的对象将被剪裁，最终的裁剪距离会和画质等级有关；修改此属性≤0时，裁剪距离会根据对象尺寸自动调整(自动启用CullDistanceVolume功能)

#### Parameters

| `inCullDistance` `number` | 裁剪距离 range: 建议 (2000, 4000) type: 浮点数 |
| :------ | :------ |


::: warning Precautions

最终的裁剪距离会和画质等级有关

:::

___

### setFloat <Score text="setFloat" /> 

• **setFloat**(`parameterName`, `value`): `void` <Badge type="tip" text="client" />

设置特效标量参数值

#### Parameters

| `parameterName` `string` | 参数名 range: 想要设置的特效标量参数名字长度 |
| :------ | :------ |
| `value` `number` | 标量值 range: 不做限制 type: 浮点数 |


___

### setFloatRandom <Score text="setFloatRandom" /> 

• **setFloatRandom**(`parameterName`, `maxValue`, `minValue`): `void` <Badge type="tip" text="client" />

设置特效标量参数随机

#### Parameters

| `parameterName` `string` | 参数名 range: 想要设置的特效标量参数名字长度 |
| :------ | :------ |
| `maxValue` `number` | 标量最大值 range: 不做限制 type: 浮点数 |
| `minValue` `number` | 标量最小值 range: 不做限制 type: 浮点数 |


___

### setVector <Score text="setVector" /> 

• **setVector**(`parameterName`, `value`): `void` <Badge type="tip" text="client" />

设置特效向量参数值

#### Parameters

| `parameterName` `string` | 参数名 range: 想要设置的特效标量参数名字长度 |
| :------ | :------ |
| `value` [`Vector`](mw.Vector.md) | 向量值 |


___

### setVectorRandom <Score text="setVectorRandom" /> 

• **setVectorRandom**(`parameterName`, `maxValue`, `minValue`): `void` <Badge type="tip" text="client" />

设置特效向量参数范围随机，在一定范围内取向量的随机值

#### Parameters

| `parameterName` `string` | 参数名 range: 合理即可 range: 想要设置的特效标量参数名字长度 |
| :------ | :------ |
| `maxValue` [`Vector`](mw.Vector.md) | 向量最大值 |
| `minValue` [`Vector`](mw.Vector.md) | 向量最小值 |


___

### stop <Score text="stop" /> 

• **stop**(): `void` 

停止特效，不影响已经生成的粒子

