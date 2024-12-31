[玩法](../groups/玩法.玩法.md) / ObjectLauncher

# ObjectLauncher <Badge type="tip" text="Class" /> <Score text="ObjectLauncher" />

投掷物发射器

-------------------------

投掷物发射器是一种游戏中常见的机制，用于模拟投掷物体的发射和飞行。它可以让玩家或游戏角色通过选择合适的方向和力量，将物体发射到目标位置。

想象一下，你站在一个阳台上，手里拿着一个小球，并希望将它投向一个目标。投掷物发射器就像是你的手臂和手，它帮助你控制球的发射。你可以调整你的手臂的方向和力量，以便球以特定的方式飞行。

一旦玩家决定好发射的方向和力量，投掷物发射器就会将投掷物体发射出去。投掷物体会根据发射器设置的速度和发射角度开始飞行。它会在空中经过弧线路径，并受到重力和其他物理效应的影响。

ObjectLauncher 为发射器。发射器发射出的实例称为投掷物实例 ProjectileInst 。投掷物实例上挂载着实际发射的物体。

当 spawnProjectileInstanceLaunch 启动发射时，传入对象ID（注意是场景里的对象 id，不是资源 id），投掷物实例拖着传入的模型进行运动，发射器作为发射终端，维护投掷物发射相关的参数。

发射器接口调用端可以是服务器，也可以是客户端；发射投掷物的方式有3种：1.双端投掷物 2.发射全客户端投掷物 3.发射单客户端投掷物

在客户端还是服务端加载 ObjectLauncher 对象呢？

1. 服务端

-  在服务端动态生成投掷物发射器，获得一个各端同步的投掷物发射器对象。修改投掷物发射器属性会同步至所有客户端。

-  在服务器添加投掷物发射器委托后，委托只会在服务器执行，同时执行前提是发射器要存在于服务器。

-  在服务器调用发射接口时，按服务器当前发射器属性生成双端投掷物发射，发射对象如果在服务端找不到（有可能是单客户端投掷物），直接返回，能找到（发射对象是双端对象），在投掷物上挂载发射物体。双端投掷物的碰撞和轨迹就是服务器计算，即以服务器的计算结果为准。

2. 客户端

-  在客户端动态生成投掷物发射器，只能获得一个本地的投掷物发射器对象，仅支持本地发射。

-  在本地添加回调后，回调只会在本地执行，同时执行前提是发射器要存在于本地。

-  在本地调用广播发射：按本地当前发射器属性生成单端投掷物，同时通知服务器广播其他客户端按本地当前发射器属性生成单端投掷物。发射对象如果在服务端找不到，直接返回，能找到（发射对象是双端对象），挂上投掷物。

另外有控制发射器发射初始速度、重力、投掷物半径等参数。

## Hierarchy

- [`GameObject`](mw.GameObject.md)

  ↳ **`ObjectLauncher`**

## Table of contents

### Properties <Score text="Properties" /> 
| **[onProjectileHit](mw.ObjectLauncher.md#onprojectilehit)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`projectile`: [`ProjectileInst`](mw.ProjectileInst.md), `hitGameObject`: [`GameObject`](mw.GameObject.md), `hitResult`: [`HitResult`](mw.HitResult.md)) => `void`\>  |
| :-----|
| 投掷物击中物体时触发绑定函数|
| **[onProjectileHomingFail](mw.ObjectLauncher.md#onprojectilehomingfail)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`projectile`: [`ProjectileInst`](mw.ProjectileInst.md)) => `void`\>  |
| 投掷物追踪目标失败(即为被销毁时)触发绑定函数|
| **[onProjectileLifeEnd](mw.ObjectLauncher.md#onprojectilelifeend)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`projectile`: [`ProjectileInst`](mw.ProjectileInst.md)) => `void`\>  |
| 投掷物生命周期结束（即速度降为0、LifeSpan 到期）时触发绑定函数|
| **[onProjectileLifeStart](mw.ObjectLauncher.md#onprojectilelifestart)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`projectile`: [`ProjectileInst`](mw.ProjectileInst.md)) => `void`\>  |
| 投掷物生成实例时触发绑定函数，此时实例还没有开始移动|


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
| **[acceleration](mw.ObjectLauncher.md#acceleration)**(): `number`  |
| :-----|
| 投掷物运动的加速度（cm/s），正值会使投掷物加速，负值减速。default: 0，range: [-10000,10000]。|
| **[capsuleHalfLength](mw.ObjectLauncher.md#capsulehalflength)**(): `number`  |
| 投掷物碰撞胶囊体的半长（cm），半长小于半径时为球体。default: 50。range: [1, 1000]。|
| **[capsuleRadius](mw.ObjectLauncher.md#capsuleradius)**(): `number`  |
| 投掷物碰撞胶囊体的半径（cm）。default: 25。range: [1, 1000]。|
| **[collisionVelocityRetention](mw.ObjectLauncher.md#collisionvelocityretention)**(): `number`  |
| 碰撞后投掷物保持原来速度的比例。0表示。default: 0.6。range: [0, 1]。|
| **[gravityScale](mw.ObjectLauncher.md#gravityscale)**(): `number`  |
| 投掷物受世界重力影响的倍率，正值会使投掷物下坠，负值上升，0可以使投掷物以直线运动。default: 1，range: [-10, 10]。|
| **[initialSpeed](mw.ObjectLauncher.md#initialspeed)**(): `number`  |
| 投掷物的初始运动速度（cm/s），default: 5000，range: [1,100000]。|
| **[isRotationFollowsVelocity](mw.ObjectLauncher.md#isrotationfollowsvelocity)**(): `boolean`  |
| 投掷物的正方向（以及挂载对象）是否始终跟随运动方向。true：跟随。false：不跟随。default: true。|
| **[isShouldBounce](mw.ObjectLauncher.md#isshouldbounce)**(): `boolean`  |
| 决定投掷物运动过程中与其他对象发生碰撞时是否能反弹。true：反弹。false：穿透。default: true。|
| **[isShouldReplicateDelegates](mw.ObjectLauncher.md#isshouldreplicatedelegates)**(): `boolean`  |
| 投掷物触发对应事件时是否广播（仅双端发射器生效），true：广播。false：仅本地|
| **[lifeSpan](mw.ObjectLauncher.md#lifespan)**(): `number`  |
| 投掷物存在的最长时间（s），0意味着没有限制。default: 10。range: [0, 1000]。|
| **[maxSpeed](mw.ObjectLauncher.md#maxspeed)**(): `number`  |
| 投掷物的最大运动速度（cm/s），0意味着没有限制。default: 0，range: [0,100000]。|


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
| **[predictedTrajectory](mw.ObjectLauncher.md#predictedtrajectory)**(`startPosition`: [`Vector`](mw.Vector.md), `startDirection`: [`Vector`](mw.Vector.md), `density`: `number`, `duration`: `number`): [`Vector`](mw.Vector.md)[]   |
| :-----|
| 按照预测时间和密度返回的路径点数组。不预测碰撞后的反弹路径。|
| **[spawnProjectileInstanceLaunch](mw.ObjectLauncher.md#spawnprojectileinstancelaunch)**(`childObjectId`: `string`, `startPosition?`: [`Vector`](mw.Vector.md), `direction?`: [`Vector`](mw.Vector.md), `isAllClientLaunch?`: `boolean`): [`ProjectileInst`](mw.ProjectileInst.md)   |
| 按照对象发射器当前参数生成的投掷物对象|
| **[spawnProjectileInstanceLaunchToTarget](mw.ObjectLauncher.md#spawnprojectileinstancelaunchtotarget)**(`childObjectId`: `string`, `target`: [`GameObject`](mw.GameObject.md), `targetingAcceleration?`: `number`, `startPosition?`: [`Vector`](mw.Vector.md), `direction?`: [`Vector`](mw.Vector.md), `isAllClientLaunch?`: `boolean`): [`ProjectileInst`](mw.ProjectileInst.md)   |
| 按照对象发射器当前参数生成的投掷物对象|


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

### onProjectileHit <Score text="onProjectileHit" /> 

• **onProjectileHit**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`projectile`: [`ProjectileInst`](mw.ProjectileInst.md), `hitGameObject`: [`GameObject`](mw.GameObject.md), `hitResult`: [`HitResult`](mw.HitResult.md)) => `void`\>

投掷物击中物体时触发绑定函数

::: warning Precautions

所有投掷物都是使用的同一个回调，请不要循环添加事件绑定函数

:::

___

### onProjectileHomingFail <Score text="onProjectileHomingFail" /> 

• **onProjectileHomingFail**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`projectile`: [`ProjectileInst`](mw.ProjectileInst.md)) => `void`\>

投掷物追踪目标失败(即为被销毁时)触发绑定函数

::: warning Precautions

所有投掷物都是使用的同一个回调，请不要循环添加事件绑定函数

:::

<span style="font-size: 14px;">
使用示例:创建一个脚本放置在对象栏中，在脚本中复制下列"Example_ObjectLauncher_OnHomingFail"的代码保存，运行游戏，场景中将会生成一个对象发射器、一个用于发射的球以及一个NPC目标。给发射器对应事件的委托绑定函数。按下按键”1“，发射球并追踪NPC。设置对象代码如下：
</span>

```ts
 @Component
 export default class Example_ObjectLauncher_OnHomingFail extends Script {

     protected async onStart(): Promise<void> {

         // 下列逻辑在服务端执行
         if(SystemUtil.isServer()) {
             // 在世界坐标（200，0，25）异步生成一个球
             let ball = await GameObject.asyncSpawn("84121") as Model;
             ball.worldTransform.position = new Vector(200, 0, 25);

             // 在世界坐标（2000，1000，130）异步生成一个NPC,2s后销毁。
             let target = Player.spawnDefaultCharacter();
             target.worldTransform.position = new Vector(2000, 1000, 130);

             // 异步生成对象发射器
             let myLauncher = await GameObject.asyncSpawn("ObjectLauncher") as ObjectLauncher;

             // 设置发射初始速度为1000
             myLauncher.initialSpeed = 1000;
             // 设置碰撞半径为25
             myLauncher.capsuleRadius = 25;
             // 设置碰撞半长为25
             myLauncher.capsuleHalfLength = 25;
             // 开启反弹
             myLauncher.isShouldBounce = true;
             // 设置碰撞速度衰减为0.5
             myLauncher.collisionVelocityRetention = 0.5;

             // 给发射器追踪失败委托绑定函数，追踪失败时打印信息
             myLauncher.onProjectileHomingFail.add((projectile) => {
                 console.log("Homing Fail");
             });

             // 添加客户端发送的”LAUNCHTOTARGET“事件监听器，将球朝斜上方发射并追踪NPC。
             Event.addClientListener("LAUNCHTOTARGET", () => {
                 TimeUtil.delaySecond(1).then(() => {
                     target.destroy();
                  });
                 myLauncher.spawnProjectileInstanceLaunchToTarget(ball.gameObjectId, target, 2000, ball.worldTransform.position, new Vector(1, 0, 1));
             });
         }

         // 下列逻辑在客户端执行
         if(SystemUtil.isClient()) {
             // 添加一个按键方法：按下按键”1“，向服务端派送一个”LAUNCHTOTARGET“事件，发射一个球追踪NPC。
             InputUtil.onKeyDown(Keys.One, () => {
                 Event.dispatchToServer("LAUNCHTOTARGET");
             });
         }
     }
 }
```

___

### onProjectileLifeEnd <Score text="onProjectileLifeEnd" /> 

• **onProjectileLifeEnd**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`projectile`: [`ProjectileInst`](mw.ProjectileInst.md)) => `void`\>

投掷物生命周期结束（即速度降为0、LifeSpan 到期）时触发绑定函数

::: warning Precautions

所有投掷物都是使用的同一个回调，请不要循环添加事件绑定函数；客户端添加的回调，在发射双端对象时，此委托触发时无法保证实例是否依然存在

:::

___

### onProjectileLifeStart <Score text="onProjectileLifeStart" /> 

• **onProjectileLifeStart**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`projectile`: [`ProjectileInst`](mw.ProjectileInst.md)) => `void`\>

投掷物生成实例时触发绑定函数，此时实例还没有开始移动

::: warning Precautions

所有投掷物都是使用的同一个回调，请不要循环添加事件绑定函数

:::

## Accessors

### acceleration <Score text="acceleration" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **acceleration**(): `number`

</th>
<th style="text-align: left">

• `set` **acceleration**(`value`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


投掷物运动的加速度（cm/s），正值会使投掷物加速，负值减速。default: 0，range: [-10000,10000]。

#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


投掷物运动的加速度（cm/s），正值会使投掷物加速，负值减速。default: 0，range: [-10000,10000]。

#### Parameters

| `value` | `number` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### capsuleHalfLength <Score text="capsuleHalfLength" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **capsuleHalfLength**(): `number`

</th>
<th style="text-align: left">

• `set` **capsuleHalfLength**(`value`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


投掷物碰撞胶囊体的半长（cm），半长小于半径时为球体。default: 50。range: [1, 1000]。

#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


投掷物碰撞胶囊体的半长（cm），半长小于半径时为球体。default: 50。range: [1, 1000]。

#### Parameters

| `value` | `number` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### capsuleRadius <Score text="capsuleRadius" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **capsuleRadius**(): `number`

</th>
<th style="text-align: left">

• `set` **capsuleRadius**(`value`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


投掷物碰撞胶囊体的半径（cm）。default: 25。range: [1, 1000]。

#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


投掷物碰撞胶囊体的半径（cm）。default: 25。range: [1, 1000]。

#### Parameters

| `value` | `number` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### collisionVelocityRetention <Score text="collisionVelocityRetention" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **collisionVelocityRetention**(): `number`

</th>
<th style="text-align: left">

• `set` **collisionVelocityRetention**(`value`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


碰撞后投掷物保持原来速度的比例。0表示。default: 0.6。range: [0, 1]。

#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


碰撞后投掷物保持原来速度的比例。0表示。default: 0.6。range: [0, 1]。

#### Parameters

| `value` | `number` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### gravityScale <Score text="gravityScale" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **gravityScale**(): `number`

</th>
<th style="text-align: left">

• `set` **gravityScale**(`value`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


投掷物受世界重力影响的倍率，正值会使投掷物下坠，负值上升，0可以使投掷物以直线运动。default: 1，range: [-10, 10]。

#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


投掷物受世界重力影响的倍率，正值会使投掷物下坠，负值上升，0可以使投掷物以直线运动。default: 1，range: [-10, 10]。

#### Parameters

| `value` | `number` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### initialSpeed <Score text="initialSpeed" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **initialSpeed**(): `number`

</th>
<th style="text-align: left">

• `set` **initialSpeed**(`value`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


投掷物的初始运动速度（cm/s），default: 5000，range: [1,100000]。

#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


投掷物的初始运动速度（cm/s），default: 5000，range: [1,100000]。

#### Parameters

| `value` | `number` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### isRotationFollowsVelocity <Score text="isRotationFollowsVelocity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **isRotationFollowsVelocity**(): `boolean`

</th>
<th style="text-align: left">

• `set` **isRotationFollowsVelocity**(`value`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


投掷物的正方向（以及挂载对象）是否始终跟随运动方向。true：跟随。false：不跟随。default: true。

#### Returns

| `boolean` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


投掷物的正方向（以及挂载对象）是否始终跟随运动方向。true：跟随。false：不跟随。default: true。

#### Parameters

| `value` | `boolean` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### isShouldBounce <Score text="isShouldBounce" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **isShouldBounce**(): `boolean`

</th>
<th style="text-align: left">

• `set` **isShouldBounce**(`value`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


决定投掷物运动过程中与其他对象发生碰撞时是否能反弹。true：反弹。false：穿透。default: true。

#### Returns

| `boolean` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


决定投掷物运动过程中与其他对象发生碰撞时是否能反弹。true：反弹。false：穿透。default: true。

#### Parameters

| `value` | `boolean` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### isShouldReplicateDelegates <Score text="isShouldReplicateDelegates" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **isShouldReplicateDelegates**(): `boolean`

</th>
<th style="text-align: left">

• `set` **isShouldReplicateDelegates**(`value`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


投掷物触发对应事件时是否广播（仅双端发射器生效），true：广播。false：仅本地

#### Returns

| `boolean` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


投掷物触发对应事件时是否广播（仅双端发射器生效），true：广播。false：仅本地

#### Parameters

| `value` | `boolean` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### lifeSpan <Score text="lifeSpan" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **lifeSpan**(): `number`

</th>
<th style="text-align: left">

• `set` **lifeSpan**(`value`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


投掷物存在的最长时间（s），0意味着没有限制。default: 10。range: [0, 1000]。

#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


投掷物存在的最长时间（s），0意味着没有限制。default: 10。range: [0, 1000]。

#### Parameters

| `value` | `number` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### maxSpeed <Score text="maxSpeed" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **maxSpeed**(): `number`

</th>
<th style="text-align: left">

• `set` **maxSpeed**(`value`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


投掷物的最大运动速度（cm/s），0意味着没有限制。default: 0，range: [0,100000]。

#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


投掷物的最大运动速度（cm/s），0意味着没有限制。default: 0，range: [0,100000]。

#### Parameters

| `value` | `number` |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods

___

### predictedTrajectory <Score text="predictedTrajectory" /> 

• **predictedTrajectory**(`startPosition`, `startDirection`, `density`, `duration`): [`Vector`](mw.Vector.md)[] 

按照预测时间和密度返回的路径点数组。不预测碰撞后的反弹路径。

#### Parameters

| `startPosition` [`Vector`](mw.Vector.md) |  发射起始位置 |
| :------ | :------ |
| `startDirection` [`Vector`](mw.Vector.md) |  发射起始方向 |
| `density` `number` |  预测结果的点密度（个/秒），值越大路径点越细，性能消耗越大。 range:(0, density * duration + 1] type: 浮点数 |
| `duration` `number` |  预测的时长。 range: 不做限制 type: 浮点数 |

#### Returns

| [`Vector`](mw.Vector.md)[] | 路径轨迹点，预测结果的点的最大数量为 density * duration + 1。 |
| :------ | :------ |

::: warning Precautions

如果返回的数组长度为1，可能投掷物被卡住了

:::

___

### spawnProjectileInstanceLaunch <Score text="spawnProjectileInstanceLaunch" /> 

• **spawnProjectileInstanceLaunch**(`childObjectId`, `startPosition?`, `direction?`, `isAllClientLaunch?`): [`ProjectileInst`](mw.ProjectileInst.md) 

按照对象发射器当前参数生成的投掷物对象

#### Parameters

| `childObjectId` `string` |  发射对象的 id。 range: 字符串长度取决于 ID 长度。 |
| :------ | :------ |
| `startPosition?` [`Vector`](mw.Vector.md) |  发射起始位置 default: 发射对象的位置 |
| `direction?` [`Vector`](mw.Vector.md) |  发射起始方向 default: 发射对象的正前方 |
| `isAllClientLaunch?` `boolean` |  仅在发射单客户端对象是有效, 是否广播到所有客户端发射实例 default: false |

#### Returns

| [`ProjectileInst`](mw.ProjectileInst.md) | 投掷物实例 |
| :------ | :------ |

::: warning Precautions

发射后再更新其他属性无法对本次发射的投掷物产生影响

:::

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
                 myLauncher.spawnProjectileInstanceLaunch(rocket.gameObjectId, rocket.worldTransform.position, new Vector(0, 0, 1));
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

___

### spawnProjectileInstanceLaunchToTarget <Score text="spawnProjectileInstanceLaunchToTarget" /> 

• **spawnProjectileInstanceLaunchToTarget**(`childObjectId`, `target`, `targetingAcceleration?`, `startPosition?`, `direction?`, `isAllClientLaunch?`): [`ProjectileInst`](mw.ProjectileInst.md) 

按照对象发射器当前参数生成的投掷物对象

#### Parameters

| `childObjectId` `string` |  发射对象的 id。 range: 字符串长度取决于 ID 长度 |
| :------ | :------ |
| `target` [`GameObject`](mw.GameObject.md) |  追踪目标 |
| `targetingAcceleration?` `number` |  追踪加速度 default: 10000 range: 不做限制 type: 浮点数 |
| `startPosition?` [`Vector`](mw.Vector.md) |  发射起始位置 default: 发射对象的位置 |
| `direction?` [`Vector`](mw.Vector.md) |  发射起始方向 default: 发射对象的正前方 |
| `isAllClientLaunch?` `boolean` |  仅在发射单客户端对象是有效, 是否广播到所有客户端发射实例 default: false |

#### Returns

| [`ProjectileInst`](mw.ProjectileInst.md) | 投掷物实例 |
| :------ | :------ |

::: warning Precautions

发射后再更新其他属性无法对本次发射的子弹产生影响;
当在服务端调用方法广播，追踪模式发射时，会自带一个追踪的加速度，速度表现和预期会有差异

:::

<span style="font-size: 14px;">
使用示例:创建一个脚本放置在对象栏中，在脚本中复制下列"Example_ObjectLauncher_OnHomingFail"的代码保存，运行游戏，场景中将会生成一个对象发射器、一个用于发射的球以及一个NPC目标。给发射器对应事件的委托绑定函数。按下按键”1“，发射球并追踪NPC。设置对象代码如下：
</span>

```ts
 @Component
 export default class Example_ObjectLauncher_OnHomingFail extends Script {

     protected async onStart(): Promise<void> {

         // 下列逻辑在服务端执行
         if(SystemUtil.isServer()) {
             // 在世界坐标（200，0，25）异步生成一个球
             let ball = await GameObject.asyncSpawn("84121") as Model;
             ball.worldTransform.position = new Vector(200, 0, 25);

             // 在世界坐标（2000，1000，130）异步生成一个NPC,2s后销毁。
             let target = Player.spawnDefaultCharacter();
             target.worldTransform.position = new Vector(2000, 1000, 130);

             // 异步生成对象发射器
             let myLauncher = await GameObject.asyncSpawn("ObjectLauncher") as ObjectLauncher;

             // 设置发射初始速度为1000
             myLauncher.initialSpeed = 1000;
             // 设置碰撞半径为25
             myLauncher.capsuleRadius = 25;
             // 设置碰撞半长为25
             myLauncher.capsuleHalfLength = 25;
             // 开启反弹
             myLauncher.isShouldBounce = true;
             // 设置碰撞速度衰减为0.5
             myLauncher.collisionVelocityRetention = 0.5;

             // 给发射器追踪失败委托绑定函数，追踪失败时打印信息
             myLauncher.onProjectileHomingFail.add((projectile) => {
                 console.log("Homing Fail");
             });

             // 添加客户端发送的”LAUNCHTOTARGET“事件监听器，将球朝斜上方发射并追踪NPC。
             Event.addClientListener("LAUNCHTOTARGET", () => {
                 TimeUtil.delaySecond(1).then(() => {
                     target.destroy();
                  });
                 myLauncher.spawnProjectileInstanceLaunchToTarget(ball.gameObjectId, target, 2000, ball.worldTransform.position, new Vector(1, 0, 1));
             });
         }

         // 下列逻辑在客户端执行
         if(SystemUtil.isClient()) {
             // 添加一个按键方法：按下按键”1“，向服务端派送一个”LAUNCHTOTARGET“事件，发射一个球追踪NPC。
             InputUtil.onKeyDown(Keys.One, () => {
                 Event.dispatchToServer("LAUNCHTOTARGET");
             });
         }
     }
 }
```
