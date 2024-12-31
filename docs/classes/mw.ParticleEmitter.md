[场景](../groups/场景.场景.md) / ParticleEmitter

# ParticleEmitter <Badge type="tip" text="Class" /> <Score text="ParticleEmitter" />

粒子特效

通常用于游戏场景中的效果表现，目前开放部分粒子效果，当编辑器细节面板勾选自动启用时，运行游戏会自动播放特效。

如需精确控制特效的播放与停止，请使用 play 和 stop 方法。该特效需要手动控制生命周期，效果可通过细节面板中参数调节。

<span style="font-size: 14px;">
使用示例:创建一个名为"EffectExample"的脚本，拖拽到对象栏特效下，打开脚本，输入以下代码保存，运行游戏，你将在场景中看到粒子的变化效果。代码如下：
</span>

```ts
@Component
export default class EffectExample extends Script {

    protected onStart(): void {

         let Effect = this.gameObject as ParticleEmitter;
         // 涉及部分对生命周期内效果的修改
         // 创建尺寸生命周期数组 效果为由蓝线性过度至红色
         let ColorSequence = Array<mw.colorSequencePoint>();
         // 生命周期0%时为蓝色 详见LinearColor
         ColorSequence.push(new mw.colorSequencePoint(0, new LinearColor(1,0,0)));
         // 生命周期100%时为红色
         ColorSequence.push(new mw.colorSequencePoint(0, new LinearColor(0,0,1)));
         Effect.color = ColorSequence;
         // 创建透明度生命周期数组 效果为逐渐清晰
         let TransparencySequence = Array<mw.numberSequencePoint>();
         // 刚生成时透明度为0 看不见
         TransparencySequence.push(new mw.numberSequencePoint(0, 0));
         // 逐渐过渡到生命周期末 全显示
         TransparencySequence.push(new mw.numberSequencePoint(1, 1));
         Effect.transparency = TransparencySequence;

         // 创建尺寸生命周期数组 效果为变大再缩小
         let SizeSequence = Array<mw.numberSequencePoint>();
         // 生命周期0%时大小为0
         Size
         // 生命周期50%时大小为4
         SizeSequence.push(new mw.numberSequencePoint(0.5, 4));
         // 生命周期100%时大小回到0
         SizeSequence.push(new mw.numberSequencePoint(1, 0));
         Effect.size = SizeSequence;

         // 设置特效阻力为1
         Effect.drag = 1;
         // 增加特效生成的速度
         Effect.rate = 100;
         // 不进行边缘裁剪,全部保留,方形
         Effect.maskRadius = 1;
         // 仅在表面生成
         Effect.shapeStyle = mw.ParticleEmitterShapeStyle.OnlySurface;
         // 生成范围长宽高100
         Effect.shapeExtents = new Vector(100, 100, 100);

         // 生命周期在1~10范围内随机
         Effect.lifetime = new Vector2(1, 10);
         // 10秒后停止, 不影响已生成粒子
         setTimeout(() => {
             Effect.stop();
         }, 10000);
    }
}
```

## Hierarchy

- [`GameObject`](mw.GameObject.md)

  ↳ **`ParticleEmitter`**

## Table of contents

### Properties <Score text="Properties" /> 


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
| **[acceleration](mw.ParticleEmitter.md#acceleration)**(): [`vectorSequencePoint`](mw.vectorSequencePoint.md)[] <Badge type="tip" text="client" />  |
| :-----|
| 获取生命周期内加速度变化曲线|
| **[brightness](mw.ParticleEmitter.md#brightness)**(): [`numberSequencePoint`](mw.numberSequencePoint.md)[] <Badge type="tip" text="client" />  |
| 亮度|
| **[color](mw.ParticleEmitter.md#color)**(): [`[color](mw.ParticleEmitter.md#color)SequencePoint`](Core.mw.[color](mw.ParticleEmitter.md#color)SequencePoint.md)[] <Badge type="tip" text="client" />  |
| 获取设置生命周期内颜色变化曲线|
| **[drag](mw.ParticleEmitter.md#drag)**(): `number` <Badge type="tip" text="client" />  |
| 阻力|
| **[flipbookCellCount](mw.ParticleEmitter.md#flipbookcellcount)**(): `number` <Badge type="tip" text="client" />  |
| 序列帧布局可用单元数量|
| **[flipbookCirculationTime](mw.ParticleEmitter.md#flipbookcirculationtime)**(): `number` <Badge type="tip" text="client" />  |
| 序列帧动画循环次数|
| **[flipbookLayout](mw.ParticleEmitter.md#flipbooklayout)**(): [`ParticleFlipbookLayout`](../enums/mw.ParticleFlipbookLayout.md) <Badge type="tip" text="client" />  |
| 序列帧贴图的布局|
| **[flipbookMode](mw.ParticleEmitter.md#flipbookmode)**(): [`ParticleFlipbookMode`](../enums/mw.ParticleFlipbookMode.md) <Badge type="tip" text="client" />  |
| 序列帧的播放模式|
| **[isLocalSpace](mw.ParticleEmitter.md#islocalspace)**(): `boolean` <Badge type="tip" text="client" />  |
| 是否使用局部空间|
| **[lifetime](mw.ParticleEmitter.md#lifetime)**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />  |
| 生命周期|
| **[lightInfluence](mw.ParticleEmitter.md#lightinfluence)**(): `number` <Badge type="tip" text="client" />  |
| 光照影响|
| **[maskRadius](mw.ParticleEmitter.md#maskradius)**(): `number` <Badge type="tip" text="client" />  |
| 遮罩半径|
| **[orientation](mw.ParticleEmitter.md#orientation)**(): [`ParticleEmitterOrientation`](../enums/mw.ParticleEmitterOrientation.md) <Badge type="tip" text="client" />  |
| 发射取向/对齐方式|
| **[rate](mw.ParticleEmitter.md#rate)**(): `number` <Badge type="tip" text="client" />  |
| 速率（即单位时间生成粒子的数量）|
| **[rotSpeed](mw.ParticleEmitter.md#rotspeed)**(): [`numberSequencePoint`](mw.numberSequencePoint.md)[] <Badge type="tip" text="client" />  |
| 获取生命周期内旋转速度变化曲线|
| **[rotation](mw.ParticleEmitter.md#rotation)**(): `number` <Badge type="tip" text="client" />  |
| 初始旋转|
| **[shape](mw.ParticleEmitter.md#shape)**(): [`ParticleEmitterShape`](../enums/mw.ParticleEmitterShape.md) <Badge type="tip" text="client" />  |
| 形状|
| **[shapeExtents](mw.ParticleEmitter.md#shapeextents)**(): [`Vector`](mw.Vector.md) <Badge type="tip" text="client" />  |
| 形状范围|
| **[shapeInOut](mw.ParticleEmitter.md#shapeinout)**(): [`ParticleEmitterShapeInOut`](../enums/mw.ParticleEmitterShapeInOut.md) <Badge type="tip" text="client" />  |
| 获取发射内外朝向|
| **[shapeStyle](mw.ParticleEmitter.md#shapestyle)**(): [`ParticleEmitterShapeStyle`](../enums/mw.ParticleEmitterShapeStyle.md) <Badge type="tip" text="client" />  |
| 形状样式|
| **[size](mw.ParticleEmitter.md#size)**(): [`vector2DSequencePoint`](mw.vector2DSequencePoint.md)[] <Badge type="tip" text="client" />  |
| 获取生命周期内大小变化曲线|
| **[speed](mw.ParticleEmitter.md#speed)**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />  |
| 初始速度|
| **[spreadAngle](mw.ParticleEmitter.md#spreadangle)**(): `number` <Badge type="tip" text="client" />  |
| 扩散角度|
| **[texture](mw.ParticleEmitter.md#texture)**(`[texture](mw.ParticleEmitter.md#texture)Id`): `void` <Badge type="tip" text="client" />  |
| 自定义贴图|
| **[transparency](mw.ParticleEmitter.md#transparency)**(): [`numberSequencePoint`](mw.numberSequencePoint.md)[] <Badge type="tip" text="client" />  |
| 获取生命周期内透明度变化曲线|


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
| **[emit](mw.ParticleEmitter.md#emit)**(`[emit](mw.ParticleEmitter.md#emit)Count`): `void` <Badge type="tip" text="client" />  |
| :-----|
| 发射固定数量粒子|
| **[forceStop](mw.ParticleEmitter.md#forcestop)**(): `void` <Badge type="tip" text="client" />  |
| 强制停止特效，所有粒子全部销毁|
| **[play](mw.ParticleEmitter.md#play)**(): `void` <Badge type="tip" text="client" />  |
| 播放特效|
| **[stop](mw.ParticleEmitter.md#stop)**(): `void` <Badge type="tip" text="client" />  |
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

## Accessors

### acceleration <Score text="acceleration" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **acceleration**(): [`vectorSequencePoint`](mw.vectorSequencePoint.md)[] <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **acceleration**(`sequence`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取生命周期内加速度变化曲线

#### Returns

| [`vectorSequencePoint`](mw.vectorSequencePoint.md)[] | 特效向量值曲线节点数组 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置生命周期内加速度变化曲线

#### Parameters

| `sequence` [`Vector`](mw.Vector.md)  [`vectorSequencePoint`](mw.vectorSequencePoint.md)[] | 特效向量值曲线节点数组 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### brightness <Score text="brightness" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **brightness**(): [`numberSequencePoint`](mw.numberSequencePoint.md)[] <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **brightness**(`sequence`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


亮度

#### Returns

| [`numberSequencePoint`](mw.numberSequencePoint.md)[] | 特效的亮度 |
| :------ | :------ |


</td>
<td style="text-align: left">


亮度

#### Parameters

| `sequence` `number`  [`numberSequencePoint`](mw.numberSequencePoint.md)[] | 生成粒子的亮度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### color <Score text="color" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **color**(): [`colorSequencePoint`](mw.colorSequencePoint.md)[] <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **color**(`sequence`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取设置生命周期内颜色变化曲线

#### Returns

| [`colorSequencePoint`](mw.colorSequencePoint.md)[] | 特效颜色值曲线节点数组 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置生命周期内颜色变化曲线

#### Parameters

| `sequence` [`LinearColor`](mw.LinearColor.md)  [`colorSequencePoint`](mw.colorSequencePoint.md)[] | 特效颜色值曲线节点数组 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### drag <Score text="drag" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **drag**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **drag**(`drag`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


阻力

#### Returns

| `number` | 特效的阻力 |
| :------ | :------ |


</td>
<td style="text-align: left">


阻力

#### Parameters

| `drag` `number` | 生成粒子所受到的的阻力 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### flipbookCellCount <Score text="flipbookCellCount" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **flipbookCellCount**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **flipbookCellCount**(`avalidNum`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


序列帧布局可用单元数量

#### Returns

| `number` | 序列帧布局可用单元数量 |
| :------ | :------ |


</td>
<td style="text-align: left">


序列帧布局可用单元数量

#### Parameters

| `avalidNum` `number` | 序列帧布局拆分后使用的拆分单元数量 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### flipbookCirculationTime <Score text="flipbookCirculationTime" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **flipbookCirculationTime**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **flipbookCirculationTime**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


序列帧动画循环次数

#### Returns

| `number` | 序列帧动画循环次数 |
| :------ | :------ |


</td>
<td style="text-align: left">


序列帧动画循环次数

#### Parameters

| `value` `number` | 序列帧在生命周期内循环播放的次数 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### flipbookLayout <Score text="flipbookLayout" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **flipbookLayout**(): [`ParticleFlipbookLayout`](../enums/mw.ParticleFlipbookLayout.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **flipbookLayout**(`Layout`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


序列帧贴图的布局

#### Returns

| [`ParticleFlipbookLayout`](../enums/mw.ParticleFlipbookLayout.md) | 序列帧贴图的布局 |
| :------ | :------ |


</td>
<td style="text-align: left">


序列帧贴图的布局

#### Parameters

| `Layout` [`ParticleFlipbookLayout`](../enums/mw.ParticleFlipbookLayout.md) | 序列帧贴图的布局 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### flipbookMode <Score text="flipbookMode" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **flipbookMode**(): [`ParticleFlipbookMode`](../enums/mw.ParticleFlipbookMode.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **flipbookMode**(`Layout`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


序列帧的播放模式

#### Returns

| [`ParticleFlipbookMode`](../enums/mw.ParticleFlipbookMode.md) | 序列帧的播放模式 |
| :------ | :------ |


</td>
<td style="text-align: left">


序列帧的播放模式

#### Parameters

| `Layout` [`ParticleFlipbookMode`](../enums/mw.ParticleFlipbookMode.md) | 序列帧的播放模式 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### isLocalSpace <Score text="isLocalSpace" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **isLocalSpace**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **isLocalSpace**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


是否使用局部空间

#### Returns

| `boolean` | 特效的空间计算 |
| :------ | :------ |


</td>
<td style="text-align: left">


是否使用局部空间

#### Parameters

| `value` `boolean` | 是否使用局部空间 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### lifetime <Score text="lifetime" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **lifetime**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **lifetime**(`lifetime`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


生命周期

#### Returns

| [`Vector2`](mw.Vector2.md) | 特效的生命周期 （x为最小值y为最大值，粒子生成时在x~y范围内随机取值） |
| :------ | :------ |


</td>
<td style="text-align: left">


生命周期

#### Parameters

| `lifetime` [`Vector2`](mw.Vector2.md) | 生命周期，粒子的存在时间（x为最小值y为最大值，粒子生成时在x~y范围内随机取值） |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### lightInfluence <Score text="lightInfluence" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **lightInfluence**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **lightInfluence**(`lightInfluence`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


光照影响

#### Returns

| `number` | 特效的光照影响程度 |
| :------ | :------ |


</td>
<td style="text-align: left">


光照影响

#### Parameters

| `lightInfluence` `number` | 特效的光照影响程度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### maskRadius <Score text="maskRadius" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **maskRadius**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **maskRadius**(`radius`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


遮罩半径

#### Returns

| `number` | 生成粒子的遮罩剔除半径 |
| :------ | :------ |


</td>
<td style="text-align: left">


遮罩半径

#### Parameters

| `radius` `number` | 生成粒子的遮罩剔除半径 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### orientation <Score text="orientation" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **orientation**(): [`ParticleEmitterOrientation`](../enums/mw.ParticleEmitterOrientation.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **orientation**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


发射取向/对齐方式

#### Returns

| [`ParticleEmitterOrientation`](../enums/mw.ParticleEmitterOrientation.md) | 特效的发射取向 |
| :------ | :------ |


</td>
<td style="text-align: left">


发射取向/对齐方式

#### Parameters

| `value` [`ParticleEmitterOrientation`](../enums/mw.ParticleEmitterOrientation.md) | 特效的发射取向 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### rate <Score text="rate" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **rate**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **rate**(`rate`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


速率（即单位时间生成粒子的数量）

#### Returns

| `number` | 特效的速率 |
| :------ | :------ |


</td>
<td style="text-align: left">


速率（即单位时间生成粒子的数量）

#### Parameters

| `rate` `number` | 速率 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### rotSpeed <Score text="rotSpeed" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **rotSpeed**(): [`numberSequencePoint`](mw.numberSequencePoint.md)[] <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **rotSpeed**(`sequence`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取生命周期内旋转速度变化曲线

#### Returns

| [`numberSequencePoint`](mw.numberSequencePoint.md)[] | 特效标量值曲线节点数组 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置生命周期内旋转速度变化曲线

#### Parameters

| `sequence` `number`  [`numberSequencePoint`](mw.numberSequencePoint.md)[] | 特效标量值曲线节点数组 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### rotation <Score text="rotation" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **rotation**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **rotation**(`initialRotation`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


初始旋转

#### Returns

| `number` | 特效的初始旋转 |
| :------ | :------ |


</td>
<td style="text-align: left">


初始旋转

#### Parameters

| `initialRotation` `number` | 生成粒子的初始旋转值 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### shape <Score text="shape" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **shape**(): [`ParticleEmitterShape`](../enums/mw.ParticleEmitterShape.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **shape**(`shape`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


形状

#### Returns

| [`ParticleEmitterShape`](../enums/mw.ParticleEmitterShape.md) | 特效的形状 |
| :------ | :------ |


</td>
<td style="text-align: left">


形状

#### Parameters

| `shape` [`ParticleEmitterShape`](../enums/mw.ParticleEmitterShape.md) | 特效的形状 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### shapeExtents <Score text="shapeExtents" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **shapeExtents**(): [`Vector`](mw.Vector.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **shapeExtents**(`extents`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


形状范围

#### Returns

| [`Vector`](mw.Vector.md) | 特效的形状样式 |
| :------ | :------ |


</td>
<td style="text-align: left">


形状范围

#### Parameters

| `extents` [`Vector`](mw.Vector.md) | 特效的形状范围 （设置粒子发射器的形状大小, 这决定了粒子会在多大的范围内随机生成） 仅非点状类型时生效 X 代表圆/球半径 三角形边长 Y 代表等腰三角形内角 Z 代表体积高度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### shapeInOut <Score text="shapeInOut" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **shapeInOut**(): [`ParticleEmitterShapeInOut`](../enums/mw.ParticleEmitterShapeInOut.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **shapeInOut**(`shape`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取发射内外朝向

#### Returns

| [`ParticleEmitterShapeInOut`](../enums/mw.ParticleEmitterShapeInOut.md) | 特效的发射朝向 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置发射内外朝向

#### Parameters

| `shape` [`ParticleEmitterShapeInOut`](../enums/mw.ParticleEmitterShapeInOut.md) | 特效的发射朝向 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### shapeStyle <Score text="shapeStyle" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **shapeStyle**(): [`ParticleEmitterShapeStyle`](../enums/mw.ParticleEmitterShapeStyle.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **shapeStyle**(`style`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


形状样式

#### Returns

| [`ParticleEmitterShapeStyle`](../enums/mw.ParticleEmitterShapeStyle.md) | 特效的形状样式 |
| :------ | :------ |


</td>
<td style="text-align: left">


形状样式

#### Parameters

| `style` [`ParticleEmitterShapeStyle`](../enums/mw.ParticleEmitterShapeStyle.md) | 特效的形状样式表面生成还是体积内生成，仅非点状类型时生效） |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### size <Score text="size" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **size**(): [`vector2DSequencePoint`](mw.vector2DSequencePoint.md)[] <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **size**(`sequence`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取生命周期内大小变化曲线

#### Returns

| [`vector2DSequencePoint`](mw.vector2DSequencePoint.md)[] | 大小变化曲线节点数组 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置生命周期内大小变化曲线

#### Parameters

| `sequence` [`Vector2`](mw.Vector2.md)  [`numberSequencePoint`](mw.numberSequencePoint.md)[]  [`vector2DSequencePoint`](mw.vector2DSequencePoint.md)[] | 特效标量值曲线节点数组 numberSequencePoint传参已废弃，请改用vector2DSequencePoint |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### speed <Score text="speed" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **speed**(): [`Vector2`](mw.Vector2.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **speed**(`speed`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


初始速度

#### Returns

| [`Vector2`](mw.Vector2.md) | 生成粒子的初始速度（x为最小值y为最大值，粒子生成时在x~y范围内随机取值） |
| :------ | :------ |


</td>
<td style="text-align: left">


初始速度

#### Parameters

| `speed` [`Vector2`](mw.Vector2.md) | 生成粒子的初始速度（x为最小值y为最大值，粒子生成时在x~y范围内随机取值） |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### spreadAngle <Score text="spreadAngle" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **spreadAngle**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **spreadAngle**(`spreadAngle`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


扩散角度

#### Returns

| `number` | 特效的扩散角度 |
| :------ | :------ |


</td>
<td style="text-align: left">


扩散角度

#### Parameters

| `spreadAngle` `number` | 生成粒子的扩散角度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### texture <Score text="texture" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `set` **texture**(`textureId`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


自定义贴图

#### Parameters

| `textureId` `string`  `number` | 特效自定义贴图ID |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### transparency <Score text="transparency" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **transparency**(): [`numberSequencePoint`](mw.numberSequencePoint.md)[] <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **transparency**(`sequence`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取生命周期内透明度变化曲线

#### Returns

| [`numberSequencePoint`](mw.numberSequencePoint.md)[] | 特效标量值曲线节点数组 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置生命周期内透明度变化曲线

#### Parameters

| `sequence` `number`  [`numberSequencePoint`](mw.numberSequencePoint.md)[] | 特效标量值曲线节点数组 |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods

___

### emit <Score text="emit" /> 

• **emit**(`emitCount`): `void` <Badge type="tip" text="client" />

发射固定数量粒子

#### Parameters

| `emitCount` `number` | 需要发射的粒子数量 range: 不做限制 type: 浮点数 |
| :------ | :------ |


___

### forceStop <Score text="forceStop" /> 

• **forceStop**(): `void` <Badge type="tip" text="client" />

强制停止特效，所有粒子全部销毁


___

### play <Score text="play" /> 

• **play**(): `void` <Badge type="tip" text="client" />

播放特效


___

### stop <Score text="stop" /> 

• **stop**(): `void` <Badge type="tip" text="client" />

停止特效，不影响已经生成的粒子

