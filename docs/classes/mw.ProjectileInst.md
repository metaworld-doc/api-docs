[玩法](../groups/玩法.玩法.md) / ProjectileInst

# ProjectileInst <Badge type="tip" text="Class" /> <Score text="ProjectileInst" />

投掷物发射器专用实例对象

## Hierarchy

- [`GameObject`](mw.GameObject.md)

  ↳ **`ProjectileInst`**

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
| **[owner](mw.ProjectileInst.md#owner)**(): [`Player`](mw.Player.md)  |
| :-----|
| 发射的玩家|
| **[velocity](mw.ProjectileInst.md#velocity)**(): [`Vector`](mw.Vector.md)  |
| 获取当前速度|


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

## Accessors

___

### owner <Score text="owner" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **owner**(): [`Player`](mw.Player.md)

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


发射的玩家

#### Returns

| [`Player`](mw.Player.md) |  |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### velocity <Score text="velocity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **velocity**(): [`Vector`](mw.Vector.md)

</th>
<th style="text-align: left">

• `set` **velocity**(`newVelocity`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取当前速度


#### Returns

| [`Vector`](mw.Vector.md) |  |
| :------ | :------ |


</td>
<td style="text-align: left">


设置当前速度

::: warning Precautions

不会自动 rpc 到服务端，如在客户端调用且需同步，请自行到服务端调用

:::

#### Parameters

| `newVelocity` | [`Vector`](mw.Vector.md) |
| :------ | :------ |

</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个脚本放置在对象栏中，在脚本中复制下列"Example_ObjectLauncher_Acceleration"的代码保存，运行游戏，场景中将会生成一个对象发射器和用于发射的火箭。按下按键”1“，发射火箭。设置对象代码如下：
</span>

```ts
@Component
 export default class Example_ObjectLauncher_Acceleration extends Script {

     protected async onStart(): Promise<void> {

         // 下列逻辑在服务端执行
         if(SystemUtil.isServer()) {
             // 在世界坐标（200，0，25）异步生成一个火箭
             let rocket = await GameObject.asyncSpawn("162807") as Model;
             rocket.worldTransform.position = new Vector(2000, 0, 25);

             // 异步生成对象发射器
             let myLauncher = await GameObject.asyncSpawn("ObjectLauncher") as ObjectLauncher;

             // 设置发射初始速度为1
             myLauncher.initialSpeed = 1;
             // 设置发射最大速度为1000
             myLauncher.maxSpeed = 1000;
             // 设置发射加速度为200
             myLauncher.acceleration = 200;
             // 设置碰撞半径为25
             myLauncher.capsuleRadius = 25;
             // 设置碰撞半长为25
             myLauncher.capsuleHalfLength = 25;
             // 开启反弹
             myLauncher.isShouldBounce = true;
             // 设置重力缩放为0
             myLauncher.gravityScale = 0;
             // 设置旋转不跟随速度方向
             myLauncher.isRotationFollowsVelocity = false;
             // 运动时间为10s
             myLauncher.lifeSpan = 10;

             // 添加客户端发送的”LAUNCH“事件监听器，将火箭朝上方发射。
             Event.addClientListener("LAUNCH", () => {
                 let velRocket = myLauncher.spawnProjectileInstanceLaunch(rocket.gameObjectId, rocket.worldTransform.position, new Vector(0, 0, 1));
                 console.log("Rocket velocity is: " + velRocket.velocity);
                 rocket.localTransform.rotation = new Rotation(0, 90, 0);
             });
         }

         // 下列逻辑在客户端执行
         if(SystemUtil.isClient()) {
             // 添加一个按键方法：按下按键”1“，向服务端派送一个”LAUNCH“事件，发射一个球。
             InputUtil.onKeyDown(Keys.One, () => {
                 Event.dispatchToServer("LAUNCH");
             });
         }
     }
 }
```


## Methods
