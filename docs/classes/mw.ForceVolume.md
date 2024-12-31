[玩法](../groups/玩法.玩法.md) / ForceVolume

# ForceVolume <Badge type="tip" text="Class" /> <Score text="ForceVolume" />

物理力区域

-------------------------

进入力区域的角色或开启物理模拟的物体，会受到力的作用

如何使用力区域：

- 创建一个力区域对象。可手动将左侧栏中逻辑对象中的力区域拖入场景中，在编辑器属性面板中调整参数；也可以在脚本中动态创建力区域。

- 设置力区域对象属性 自动启用/enabled 为 true ，才可触发力的效果。

- 选择一种力区域的类型，指向力会向指定方向施加指定大小的力，而径向力会沿球心方向施加指定大小的力

- 对于指向力，需要设置 指向力值/directionalForce 指定大小和方向；对于径向力，需要设置 径向力值/radialForce 指定大小

<span style="font-size: 14px;">
使用示例:创建一个名为"ForceVolumeSample"的脚本，按 Q 使方块进入力区域，接下来使用数字键 1 控制开关，使用数字键 2 切换力的类型，使用数字键 3 切换力的大小，就可以看到方块在力区域中的表现了
</span>

注意：默认给的径向力大小不足以使方块运动起来，所以不调整大小的情况下切换为径向力之后方块坠地为正常表现；如果方块在运动过程中离开了区域，再按一次 Q 可以将方块重新置于力区域中；由于力区域仅存在于服务端，对于以主控端表现为主的角色无影响也是正常表现
代码如下：
```ts
@Component
export default class ForceVolumeSample extends Script {

   public myFV: ForceVolume;
   public myCube: Model;
   public myFlag: boolean = true;

   // 当脚本被实例后，会在第一帧更新前调用此函数
   protected async onStart(): Promise<void> {

       // 在服务端添加一个开启物理模拟并移动位置的监听回调函数
       if (SystemUtil.isServer()) {
           Event.addClientListener("EnablePhysicsAndSetPosition", (player: Player)=>{
               this.myCube.physicsEnabled = true;
               this.myCube.localTransform.position = new Vector(500, 0, 0);
           });
       }

       // 在服务端添加一个开启/关闭力区域的监听回调函数
       if (SystemUtil.isServer()) {
           Event.addClientListener("SwitchForceVolumeEnabledStatus", (player: Player)=>{
               if (this.myFV.enabled) {
                   this.myFV.enabled = false;
               } else {
                   this.myFV.enabled = true;
               }
           });
       }

       // 在服务端添加一个切换指向力/径向力区域的监听回调函数
       if (SystemUtil.isServer()) {
           Event.addClientListener("SwitchForceVolumeType", (player: Player)=>{
               if (this.myFV.forceType == ForceType.Directed) {
                   this.myFV.forceType = ForceType.Radial;
               } else {
                   this.myFV.forceType = ForceType.Directed;
               }
           });
       }

       // 在服务端添加一个切换切换指向力/径向力大小（正常大小与三倍大小）的监听回调函数
       if (SystemUtil.isServer()) {
           Event.addClientListener("SwitchForceVolumeIntensity", (player: Player)=>{
               if (this.myFlag) {
                   this.myFV.directionalForce = new Vector(0, 0, 900000);
                   this.myFV.radialForce = 900000;
                   this.myFlag = false;
               } else {
                   this.myFV.directionalForce = new Vector(0, 0, 300000);
                   this.myFV.radialForce = 300000;
                   this.myFlag = true;
               }
           });
       }

       // 在服务端添加一个切换稳定性系数（0与50）的监听回调函数
       if (SystemUtil.isServer()) {
           Event.addClientListener("SwitchStability", (player: Player)=>{
               if (this.myFV.stability == 0) {
                   this.myFV.stability = 50;
               } else {
                   this.myFV.stability = 0;
               }
           });
       }

       // 在服务端创建一个力区域对象
       if (SystemUtil.isServer()) {
           this.myFV = await GameObject.asyncSpawn<ForceVolume>("ForceVolume",
           {
               replicates: true,
               transform: new Transform()
           });
       }

       // 在服务端修改力区域的位置与缩放
       if (SystemUtil.isServer()) {
           let myFVTrans = this.myFV.localTransform;
           let newPosition = new Vector(500, 0, 250);
           myFVTrans.position = newPosition;
           let newScale = new Vector(5, 5, 5);
           myFVTrans.scale = newScale;
       }

       // 在服务端修改力区域的具体数据，并绑定进出区域事件输出log
       if (SystemUtil.isServer()) {
           this.myFV.enabled = true;
           this.myFV.forceType = ForceType.Directed;
           this.myFV.directionalForce = new Vector(0, 0, 300000);
           this.myFV.radialForce = 300000;
           this.myFV.stability = 0;
           this.myFV.onEnter.add(()=>{
               console.log("Something entered ForceVolume");
           });
           this.myFV.onLeave.add(()=>{
               console.log("Something left ForceVolume");
           });
       }

       // 在服务端创建一个方块，客户端按下 Q 开启物理模拟，并将方块移动到力区域内
       if (SystemUtil.isServer()) {
           this.myCube = await GameObject.asyncSpawn<Model>("197386",
           {
               replicates: true,
               transform: new Transform()
           });
       }
       InputUtil.onKeyDown(Keys.Q, ()=>{
           // 客户端通知服务器执行相应操作
           Event.dispatchToServer("EnablePhysicsAndSetPosition");
       });

       // 在客户端按数字键 1 来开启/关闭力区域
       InputUtil.onKeyDown(Keys.One, ()=>{
           // 客户端通知服务器执行相应操作
           Event.dispatchToServer("SwitchForceVolumeEnabledStatus");
       });

       // 在客户端按数字键 2 来切换指向力/径向力区域
       InputUtil.onKeyDown(Keys.Two, ()=>{
           // 客户端通知服务器执行相应操作
           Event.dispatchToServer("SwitchForceVolumeType");
       });

       // 在客户端按数字键 3 来切换指向力/径向力大小（正常大小与三倍大小）
       InputUtil.onKeyDown(Keys.Three, ()=>{
           // 客户端通知服务器执行相应操作
           Event.dispatchToServer("SwitchForceVolumeIntensity");
       });

       // 在客户端按数字键 4 来切换稳定性系数（0与50）
       InputUtil.onKeyDown(Keys.Four, ()=>{
           // 客户端通知服务器执行相应操作
           Event.dispatchToServer("SwitchStability");
       });
   }
}
```

## Hierarchy

- [`GameObject`](mw.GameObject.md)

  ↳ **`ForceVolume`**

## Table of contents

### Properties <Score text="Properties" /> 
| **[onEnter](mw.ForceVolume.md#onenter)**: [`MulticastGameObjectDelegate`](mw.MulticastGameObjectDelegate.md)  |
| :-----|
| 进入物理力区域回调函数|
| **[onLeave](mw.ForceVolume.md#onleave)**: [`MulticastGameObjectDelegate`](mw.MulticastGameObjectDelegate.md)  |
| 离开物理力区域回调函数|


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
| **[directionalForce](mw.ForceVolume.md#directionalforce)**(): [`Vector`](mw.Vector.md)   |
| :-----|
| 获取物理力区域在指向类型时力的大小|
| **[enabled](mw.ForceVolume.md#enabled)**(): `boolean`   |
| 获取是否启用物理力区域|
| **[forceType](mw.ForceVolume.md#forcetype)**(): [`ForceType`](../enums/mw.ForceType.md)   |
| 获取物理力区域力的应用方式|
| **[radialForce](mw.ForceVolume.md#radialforce)**(): `number`   |
| 获取物理力区域在指向类型时力的大小|
| **[stability](mw.ForceVolume.md#stability)**(): `number`   |
| 获取物理力区域的稳定性系数|


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

• **onEnter**: [`MulticastGameObjectDelegate`](mw.MulticastGameObjectDelegate.md)

进入物理力区域回调函数

<span style="font-size: 14px;">
使用示例:（回调使用）创建一个名为"FVOnEnterSample"的脚本，将脚本挂载到对象管理器中的力区域下，控制角色走进区域，你将会看到服务端和客户端的log输出，代码如下：
</span>

```ts
@Component
export default class FVOnEnterSample extends Script {

   // 当脚本被实例后，会在第一帧更新前调用此函数
   protected onStart(): void {
       let FV = this.gameObject as ForceVolume;
       FV.onEnter.add(()=>{
           console.log("Something entered ForceVolume");
       });
   }
}
```

___

### onLeave <Score text="onLeave" /> 

• **onLeave**: [`MulticastGameObjectDelegate`](mw.MulticastGameObjectDelegate.md)

离开物理力区域回调函数

<span style="font-size: 14px;">
使用示例:（回调使用）创建一个名为"FVOnLeaveSample"的脚本，将脚本挂载到对象管理器中的力区域下，控制角色走进再离开区域，你将会看到服务端和客户端的log输出，代码如下：
</span>

```ts
@Component
export default class FVOnLeaveSample extends Script {

   // 当脚本被实例后，会在第一帧更新前调用此函数
   protected onStart(): void {
       let FV = this.gameObject as ForceVolume;
       FV.onLeave.add(()=>{
           console.log("Something left ForceVolume");
       });
   }
}
```

## Accessors

___

### directionalForce <Score text="directionalForce" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **directionalForce**(): [`Vector`](mw.Vector.md) 

</th>
<th style="text-align: left">

• `set` **directionalForce**(`newVector`): `void` <Badge type="tip" text="other" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取物理力区域在指向类型时力的大小

#### Returns

| [`Vector`](mw.Vector.md) | 当前指向力的向量 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置物理力区域在指向类型时力的大小

#### Parameters

| `newVector` [`Vector`](mw.Vector.md) |  指向力向量 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### enabled <Score text="enabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **enabled**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **enabled**(`newEnabledStatus`): `void` <Badge type="tip" text="other" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否启用物理力区域

#### Returns

| `boolean` | 是否启用物理力区域 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否启用物理力区域，禁用状态下，不会应用力到物体上

#### Parameters

| `newEnabledStatus` `boolean` |  是否启用该物理区域，设置为 false 后依然会有碰撞事件，但不会应用力 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### forceType <Score text="forceType" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **forceType**(): [`ForceType`](../enums/mw.ForceType.md) 

</th>
<th style="text-align: left">

• `set` **forceType**(`newForceType`): `void` <Badge type="tip" text="other" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取物理力区域力的应用方式

#### Returns

| [`ForceType`](../enums/mw.ForceType.md) | 当前物理力区域的类型 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置物理力区域力的应用方式

#### Parameters

| `newForceType` [`ForceType`](../enums/mw.ForceType.md) |  力区域的类型 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### radialForce <Score text="radialForce" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **radialForce**(): `number` 

</th>
<th style="text-align: left">

• `set` **radialForce**(`newIntensity`): `void` <Badge type="tip" text="other" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取物理力区域在指向类型时力的大小

#### Returns

| `number` | 当前径向力的大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置物理力区域在径向类型时力的大小

#### Parameters

| `newIntensity` `number` |  径向力大小 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### stability <Score text="stability" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **stability**(): `number` 

</th>
<th style="text-align: left">

• `set` **stability**(`newFactor`): `void` <Badge type="tip" text="other" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取物理力区域的稳定性系数

#### Returns

| `number` | 当前稳定性系数大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置物理力区域的稳定性系数

#### Parameters

| `newFactor` `number` |  稳定性系数大小 |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods
