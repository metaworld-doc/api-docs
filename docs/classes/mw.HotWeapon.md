[玩法](../groups/玩法.玩法.md) / HotWeapon

# HotWeapon <Badge type="tip" text="Class" /> <Score text="HotWeapon" />

热武器

热武器功能是指游戏中武器的使用和管理机制，它使得玩家可以在战斗中使用各种类型的武器。

1. 射击 - 玩家按下开火键，武器会射出子弹或光线。

2. 上膛 - 每次射击后，都需要加载下一发弹药进入膛室。

3. 换弹 - 当弹夹为空时，需要更换新的弹夹。

4. 后坐力 - 射击时会产生后坐力，让准星会稍稍偏移。

::: warning Precautions

当装备上玩家时，此对象的功能才能生效。

:::

<span style="font-size: 14px;">
使用示例: 创建一个名为"HotWeaponSample1"的脚本，放置在对象管理器中热武器对象子级，打开脚本，输入以下代码保存，在本地资源库中搜索80484、4172、4171动画资源，拖入对象管理器中的优先加载目录。运行游戏，按键1、2、3、4你将在场景中看到一个热武器设置参数，添加委托，绑定按键，以及人物换弹的效果，代码如下：
</span>

```ts
 @Component
 export default class HotWeaponSample1 extends Script {
     protected onStart(): void {
         // 构造
         const hotWeapon = this.gameObject as HotWeapon;

         if (SystemUtil.isServer()) {
             hotWeapon.fireComponent.isFireOnScreenCenter = false
             hotWeapon.fireComponent.clipSize = 50
             hotWeapon.fireComponent.fireInterval = 0
             hotWeapon.fireComponent.multipleShot = 3
             hotWeapon.fireComponent.isFireOnScreenCenter = false
             hotWeapon.fireComponent.offsetOfFireOnScreenCenter = new Vector(100, 30, 0);
             // 设置参数
             hotWeapon.fireComponent.animationAssetId = "80484";
             hotWeapon.fireComponent.fireMode = HotWeaponFireMode.SingleFire;

             hotWeapon.aimEnabled = true;
             // 切换瞄准时的 第一/第三 人称
             hotWeapon.aimComponent.aimMode = HotWeaponAimMode.ThirdPerson;
             // 设置模拟瞄准时的倍镜放大倍数(仅第一人称瞄准时生效，范围1~18)
             hotWeapon.aimComponent.aimingZoom = 16;
             hotWeapon.aimComponent.cameraOffsetDistanceInThirdPersonMode = 300;

             hotWeapon.loadEnabled = true;
             hotWeapon.loadComponent.loadDuration = 1
             hotWeapon.loadComponent.loadAfterFireEnabled = true;
             hotWeapon.loadComponent.animationAssetId = "4172";

             hotWeapon.reloadEnabled = true;
             hotWeapon.reloadComponent.reloadDuration = 2;
             hotWeapon.reloadComponent.animationAssetId = "4171";

             hotWeapon.recoilForceEnabled = true;
             hotWeapon.recoilForceComponent.minHorizontalOffset = 1;
             hotWeapon.recoilForceComponent.maxHorizontalOffset = 1;
             hotWeapon.recoilForceComponent.minVerticalOffset = 1;
             hotWeapon.recoilForceComponent.maxVerticalOffset = 1;
             hotWeapon.recoilForceComponent.minHorizontalJitter = 1;
             hotWeapon.recoilForceComponent.maxHorizontalJitter = 1;
             hotWeapon.recoilForceComponent.minVerticalJitter = 1;
             hotWeapon.recoilForceComponent.maxVerticalJitter = 1;

             hotWeapon.accuracyOfFireEnabled = true;
             // 影响射击精度的子弹偏移半角的最大值(范围Min~88)
             hotWeapon.accuracyOfFireComponent.maxDispersionHalfAngle = 4;
             // 影响射击精度的子弹偏移半角的最小值(范围0~Max)
             hotWeapon.accuracyOfFireComponent.minDispersionHalfAngle = 0.01;
             // 默认影响射击精度的子弹偏移半角(范围Min~Max)
             hotWeapon.accuracyOfFireComponent.defaultDispersionHalfAngle = 1;
             // 影响射击精度的子弹偏移半角的每秒扩张速度(范围0~88)
             hotWeapon.accuracyOfFireComponent.dispersionHalfAngleIncreaseSpeed = 5;
             // 影响射击精度的子弹偏移半角的每秒收缩速度(范围0~88)
             hotWeapon.accuracyOfFireComponent.dispersionHalfAngleDecreaseSpeed = 10;
             // 影响射击精度的子弹偏移半角的每次开火扩张值(范围0~88)
             hotWeapon.accuracyOfFireComponent.dispersionHalfAngleIncreasePerShot = 1;

             hotWeapon.onEquip.add((owner) => { console.log("热武器装备好了后会在服务器端触发回调") });
             hotWeapon.onUnequip.add(() => { console.log("onUnequippedServer") });

             hotWeapon.fireComponent.onStartFire.add(() => { console.log("fireComponent.onStartFireClient") });
             hotWeapon.fireComponent.onEndFire.add(() => { console.log("fireComponent.onEndFireClient") });
             hotWeapon.fireComponent.onEndContinuousFire.add(() => { console.log("fireComponent.onEndFireClient") });

             hotWeapon.loadComponent.onStartLoad.add(() => { console.log("loadComponent.onStartLoadClient") });
             hotWeapon.loadComponent.onEndLoad.add(() => { console.log("loadComponent.onEndLoadClient") });

             hotWeapon.recoilForceComponent.onStartRecoil.add(() => { console.log("recoilForceComponent.onStartRecoilForceClient") });

             hotWeapon.reloadComponent.onStartReload.add(() => { console.log("reloadComponent.onStartReloadClient") });
             hotWeapon.reloadComponent.onEndReload.add(() => { console.log("reloadComponent.onEndReloadClient") });

             hotWeapon.aimComponent.onStartAim.add(() => { console.log("aimComponent.onAimStartClient") });
             hotWeapon.aimComponent.onEndAim.add(() => { console.log("aimComponent.onAimEndClient") });

             mw.Event.addClientListener("weaponEquipment", (player) => {
                 // 目前装备方法只能在服务端调用
                 hotWeapon.equip(player.character, HumanoidSlotType.RightHand);
             });
         } else if (SystemUtil.isClient()) {
             hotWeapon.onEquip.add(() => { console.log("onEquippedClient") });
             hotWeapon.onUnequip.add(() => { console.log("onUnequippedClient") });

             hotWeapon.fireComponent.onStartFire.add(() => { console.log("fireComponent.onStartFireClient") });
             hotWeapon.fireComponent.onEndFire.add(() => { console.log("fireComponent.onEndFireClient") });

             hotWeapon.loadComponent.onStartLoad.add(() => { console.log("loadComponent.onStartLoadClient") });
             hotWeapon.loadComponent.onEndLoad.add(() => { console.log("loadComponent.onEndLoadClient") });

             hotWeapon.recoilForceComponent.onStartRecoil.add(() => { console.log("recoilForceComponent.onStartRecoilForceClient") });

             hotWeapon.reloadComponent.onStartReload.add(() => { console.log("reloadComponent.onStartReloadClient") });
             hotWeapon.reloadComponent.onEndReload.add(() => { console.log("reloadComponent.onEndReloadClient") });

             hotWeapon.accuracyOfFireComponent.onCurrentDispersionChange.add(() => { console.log("accuracyOfFireComponent.onCurrentDispersionChangedClient") });

             hotWeapon.aimComponent.onStartAim.add(() => { console.log("aimComponent.onAimStartClient") });
             hotWeapon.aimComponent.onEndAim.add(() => { console.log("aimComponent.onAimEndClient") });

             // 装备
             InputUtil.onKeyDown(Keys.One, () => {
                 mw.Event.dispatchToServer("weaponEquipment");
             });

             InputUtil.onKeyDown(Keys.Two, () => {
                 // 开始执行操作
                 if (hotWeapon.getCurrentState() == HotWeaponState.Firing) {
                     hotWeapon.stopFire();
                 } else {
                     hotWeapon.startFire();
                 }
             });

               InputUtil.onKeyDown(Keys.Three, () => {
                 // 开始执行操作
                 if (hotWeapon.getCurrentState() == HotWeaponState.Reloading) {
                     hotWeapon.breakReload();
                 } else {
                     hotWeapon.reload(30);
                 }
             });

             InputUtil.onKeyDown(Keys.Four, () => {
                 // 开始执行操作
                 if (hotWeapon.getCurrentState() == HotWeaponState.Loading) {
                     hotWeapon.breakLoad();
                 } else {
                     hotWeapon.load();
                 }
             });
         }
     }
 }
```

## Hierarchy

- [`GameObject`](mw.GameObject.md)

  ↳ **`HotWeapon`**

## Table of contents

### Properties <Score text="Properties" /> 
| **[accuracyOfFireComponent](mw.HotWeapon.md#accuracyoffirecomponent)**: [`HotWeaponAccuracyOfFireComponent`](mw.HotWeaponAccuracyOfFireComponent.md)  |
| :-----|
| 射击精度功能。|
| **[aimComponent](mw.HotWeapon.md#aimcomponent)**: [`HotWeaponAimComponent`](mw.HotWeaponAimComponent.md)  |
| 瞄准功能。|
| **[fireComponent](mw.HotWeapon.md#firecomponent)**: [`HotWeaponFireComponent`](mw.HotWeaponFireComponent.md)  |
| 射击功能。|
| **[loadComponent](mw.HotWeapon.md#loadcomponent)**: [`HotWeaponLoadComponent`](mw.HotWeaponLoadComponent.md)  |
| 上膛功能。|
| **[onEquip](mw.HotWeapon.md#onequip)**: `MulticastDelegateInterface`<(`EquipOwner`: `$Nullable`<`Actor`\>) => `void`\>  |
| 装备热武器时执行绑定函数|
| **[onUnequip](mw.HotWeapon.md#onunequip)**: `MulticastDelegateInterface`<() => `void`\>  |
| 服务器卸载时执行绑定函数。使用示例见属性 onEquipped|
| **[recoilForceComponent](mw.HotWeapon.md#recoilforcecomponent)**: [`HotWeaponRecoilForceComponent`](mw.HotWeaponRecoilForceComponent.md)  |
| 后坐力功能。|
| **[reloadComponent](mw.HotWeapon.md#reloadcomponent)**: [`HotWeaponReloadComponent`](mw.HotWeaponReloadComponent.md)  |
| 换弹功能。|


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
| **[accuracyOfFireEnabled](mw.HotWeapon.md#accuracyoffireenabled)**(): `boolean`   |
| :-----|
| 是否开启了射击精度组件。|
| **[aimEnabled](mw.HotWeapon.md#aimenabled)**(): `boolean`   |
| 是否开启了瞄准组件。|
| **[loadEnabled](mw.HotWeapon.md#loadenabled)**(): `boolean`   |
| 是否开启了上膛组件。|
| **[recoilForceEnabled](mw.HotWeapon.md#recoilforceenabled)**(): `boolean`   |
| 获取是否开启了后坐力组件。|
| **[reloadEnabled](mw.HotWeapon.md#reloadenabled)**(): `boolean`   |
| 是否开启了换弹组件。|


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
| **[breakLoad](mw.HotWeapon.md#breakload)**(): `void` <Badge type="tip" text="other" />  |
| :-----|
| 打断上膛。|
| **[breakReload](mw.HotWeapon.md#breakreload)**(): `void` <Badge type="tip" text="other" />  |
| 打断换弹|
| **[cloneComponentsData](mw.HotWeapon.md#clonecomponentsdata)**(`otherHotWeapon`: [`HotWeapon`](mw.HotWeapon.md)): `void` <Badge type="tip" text="server" />  |
| 从传入的热武器逻辑对象中拷贝所有组件数据到当前的热武器中。|
| **[equip](mw.HotWeapon.md#equip)**(`character`: [`Character`](mw.Character.md), `slotName`: [`HumanoidSlotType`](../enums/mw.HumanoidSlotType.md)): `void` <Badge type="tip" text="other" />  |
| 装备热武器到角色的指定插槽位置|
| **[getBulletLocWhileSpawnOnScreenCenter](mw.HotWeapon.md#getbulletlocwhilespawnonscreencenter)**(): [`Vector`](mw.Vector.md) <Badge type="tip" text="client" />  |
| 使用屏幕中心生成子弹投掷物模式时，获取子弹投掷物生成的location|
| **[getCurrentOwner](mw.HotWeapon.md#getcurrentowner)**(): [`Character`](mw.Character.md)   |
| 获取当前热武器的所有者|
| **[getCurrentState](mw.HotWeapon.md#getcurrentstate)**(): [`HotWeaponState`](../enums/mw.HotWeaponState.md)   |
| 获取当前热武器状态|
| **[getDefaultCrossHairSize](mw.HotWeapon.md#getdefaultcrosshairsize)**(`maxShootRange`: `number`): `number` <Badge type="tip" text="client" />  |
| 传入最大射程，获取默认准星大小|
| **[getShootDirWithDispersion](mw.HotWeapon.md#getshootdirwithdispersion)**(`StartLoc`: [`Vector`](mw.Vector.md), `ShootRange`: `number`): [`Vector`](mw.Vector.md) <Badge type="tip" text="client" />  |
| 非屏幕中心生成子弹模式下，获取子弹飞行方向|
| **[load](mw.HotWeapon.md#load)**(): `void` <Badge type="tip" text="other" />  |
| 上膛|
| **[reload](mw.HotWeapon.md#reload)**(`bulletSize`: `number`): `void` <Badge type="tip" text="other" />  |
| 换弹|
| **[startFire](mw.HotWeapon.md#startfire)**(): `void` <Badge type="tip" text="other" />  |
| 开火|
| **[stopFire](mw.HotWeapon.md#stopfire)**(): `void` <Badge type="tip" text="other" />  |
| 停止开火|
| **[unequip](mw.HotWeapon.md#unequip)**(): `void` <Badge type="tip" text="other" />  |
| 卸载热武器。|


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

### accuracyOfFireComponent <Score text="accuracyOfFireComponent" /> 

• **accuracyOfFireComponent**: [`HotWeaponAccuracyOfFireComponent`](mw.HotWeaponAccuracyOfFireComponent.md)

射击精度功能。

此功能可以看做 hotweapon 的功能组件，只限于热武器使用。

<span style="font-size: 14px;">
使用示例: 创建一个名为"HotWeaponAofSample"的脚本，放置在对象管理器中，打开脚本，输入以下代码保存，运行游戏，代码如下：
</span>

```ts
@Component
export default class HotWeaponAofSample extends Script {
    protected onStart(): void {
        // 构造
        const hotWeapon = this.gameObject as HotWeapon;

        if (SystemUtil.isServer()) {
            hotWeapon.accuracyOfFireEnabled = true;
            // 影响射击精度的子弹偏移半角的最大值(范围Min~88)
            hotWeapon.accuracyOfFireComponent.maxDispersionHalfAngle = 4;
            // 影响射击精度的子弹偏移半角的最小值(范围0~Max)
            hotWeapon.accuracyOfFireComponent.minDispersionHalfAngle = 0.01;
            // 默认影响射击精度的子弹偏移半角(范围Min~Max)
            hotWeapon.accuracyOfFireComponent.defaultDispersionHalfAngle = 1;
            // 影响射击精度的子弹偏移半角的每秒扩张速度(范围0~88)
            hotWeapon.accuracyOfFireComponent.dispersionHalfAngleIncreaseSpeed = 5;
            // 影响射击精度的子弹偏移半角的每秒收缩速度(范围0~88)
            hotWeapon.accuracyOfFireComponent.dispersionHalfAngleDecreaseSpeed = 10;
            // 影响射击精度的子弹偏移半角的每次开火扩张值(范围0~88)
            hotWeapon.accuracyOfFireComponent.dispersionHalfAngleIncreasePerShot = 1;
        } else if (SystemUtil.isClient()) {
            hotWeapon.accuracyOfFireComponent.onCurrentDispersionChange.add(() => { console.log("accuracyOfFireComponent.onCurrentDispersionChangedClient") });
        }
    }
}
```

___

### aimComponent <Score text="aimComponent" /> 

• **aimComponent**: [`HotWeaponAimComponent`](mw.HotWeaponAimComponent.md)

瞄准功能。

<span style="font-size: 14px;">
使用示例: 创建一个名为"HotWeaponAimSample1"的脚本，放置在对象管理器中，打开脚本，输入以下代码保存，运行游戏，代码如下：
</span>

```ts
@Component
export default class HotWeaponAimSample1 extends Script {
    protected onStart(): void {
        // 构造
        const hotWeapon = this.gameObject as HotWeapon;

        if (SystemUtil.isServer()) {
            hotWeapon.aimEnabled = true;
            hotWeapon.aimComponent.aimMode = HotWeaponAimMode.ThirdPerson;
            hotWeapon.aimComponent.aimingZoom = 16;
            hotWeapon.aimComponent.cameraOffsetDistanceInThirdPersonMode = 300;
            hotWeapon.aimComponent.onStartAim.add(() => { console.log("aimComponent.onAimStartClient") });
            hotWeapon.aimComponent.onEndAim.add(() => { console.log("aimComponent.onAimEndClient") });
        } else if (SystemUtil.isClient()) {
            hotWeapon.aimComponent.onStartAim.add(() => { console.log("aimComponent.onAimStartClient") });
            hotWeapon.aimComponent.onEndAim.add(() => { console.log("aimComponent.onAimEndClient") });
        }
    }
}
```

___

### fireComponent <Score text="fireComponent" /> 

• **fireComponent**: [`HotWeaponFireComponent`](mw.HotWeaponFireComponent.md)

射击功能。

<span style="font-size: 14px;">
使用示例: 创建一个名为"HotWeaponFireSample1"的脚本，放置在对象管理器热武器的子节点中，打开脚本，输入以下代码保存，运行游戏，代码如下：
</span>

```ts
 @Component
 export default class HotWeaponFireSample1 extends Script {
     protected onStart(): void {
         // 构造
         const hotWeapon = this.gameObject as HotWeapon;

         if (SystemUtil.isServer()) {
             hotWeapon.fireComponent.isFireOnScreenCenter = false;
             hotWeapon.fireComponent.clipSize = 50;
             hotWeapon.fireComponent.fireInterval = 0;
             hotWeapon.fireComponent.multipleShot = 3;
             hotWeapon.fireComponent.isFireOnScreenCenter = false;
             hotWeapon.fireComponent.offsetOfFireOnScreenCenter = new Vector(100, 30, 0);
             // 设置参数
             hotWeapon.fireComponent.animationAssetId = "80484";
             hotWeapon.fireComponent.onStartFire.add(() => { console.log("fireComponent.onStartFireClient") });
             hotWeapon.fireComponent.onEndFire.add(() => { console.log("fireComponent.onEndFireClient") });
             hotWeapon.fireComponent.onEndContinuousFire.add(() => { console.log("fireComponent.onEndFireClient") });
         }
     }
 }
```

___

### loadComponent <Score text="loadComponent" /> 

• **loadComponent**: [`HotWeaponLoadComponent`](mw.HotWeaponLoadComponent.md)

上膛功能。

<span style="font-size: 14px;">
使用示例: 创建一个名为"HotWeaponLoadSample1"的脚本，放置在对象管理器中，打开脚本，输入以下代码保存，运行游戏，代码如下：
</span>

```ts
@Component
export default class HotWeaponLoadSample1 extends Script {
    protected onStart(): void {
        // 构造
        const hotWeapon = this.gameObject as HotWeapon;

        if (SystemUtil.isServer()) {
            hotWeapon.loadEnabled = true;
            hotWeapon.loadComponent.loadDuration = 1
            hotWeapon.loadComponent.loadAfterFireEnabled = true;
            hotWeapon.loadComponent.animationAssetId = "4172";

            hotWeapon.loadComponent.onStartLoad.add(() => { console.log("loadComponent.onStartLoad Server") });
            hotWeapon.loadComponent.onEndLoad.add(() => { console.log("loadComponent.onEndLoad Server") });
        } else if (SystemUtil.isClient()) {
            hotWeapon.loadComponent.onStartLoad.add(() => { console.log("loadComponent.onStartLoad Client") });
            hotWeapon.loadComponent.onEndLoad.add(() => { console.log("loadComponent.onEndLoad Client") });
        }
    }
}
```

___

### onEquip <Score text="onEquip" /> 

• **onEquip**: `MulticastDelegateInterface`<(`EquipOwner`: `$Nullable`<`Actor`\>) => `void`\>

装备热武器时执行绑定函数

此委托可双端执行。当你在服务端调用时，角色装备上热武器时会在服务端执行自定义绑定函数；在客户端调用时，角色装备上热武器时会在客户端执行自定义绑定函数。

<span style="font-size: 14px;">
使用示例: 创建一个名为"HotWeaponSample2"的脚本，放置在对象管理器中热武器对象子级，打开脚本，输入以下代码保存，运行游戏，代码如下：
</span>

```ts
@Component
export default class HotWeaponSample2 extends Script {
    protected onStart(): void {
        // 构造
        const hotWeapon = this.gameObject as HotWeapon;

        if (SystemUtil.isServer()) {
            hotWeapon.onEquip.add((owner) => { console.log("热武器装备好了后会在服务器端触发回调") });
            hotWeapon.onUnequip.add(() => { console.log("onUnequipServer") });
        } else if (SystemUtil.isClient()) {
            hotWeapon.onEquip.add(() => { console.log("onEquip Client") });
            hotWeapon.onUnequip.add(() => { console.log("onUnequip Client") });
        }
    }
}
```

___

### onUnequip <Score text="onUnequip" /> 

• **onUnequip**: `MulticastDelegateInterface`<() => `void`\>

服务器卸载时执行绑定函数。使用示例见属性 onEquipped

___

### recoilForceComponent <Score text="recoilForceComponent" /> 

• **recoilForceComponent**: [`HotWeaponRecoilForceComponent`](mw.HotWeaponRecoilForceComponent.md)

后坐力功能。

<span style="font-size: 14px;">
使用示例: 创建一个名为"HotWeaponRecoilForceSample"的脚本，放置在对象管理器中，打开脚本，输入以下代码保存，运行游戏，代码如下：
</span>

```ts
@Component
export default class HotWeaponRecoilForceSample extends Script {
    protected onStart(): void {
        // 构造
        const hotWeapon = this.gameObject as HotWeapon;

        if (SystemUtil.isServer()) {
            hotWeapon.recoilForceEnabled = true;
            hotWeapon.recoilForceComponent.minHorizontalOffset = 1
            hotWeapon.recoilForceComponent.maxHorizontalOffset = 1
            hotWeapon.recoilForceComponent.minVerticalOffset = 1
            hotWeapon.recoilForceComponent.maxVerticalOffset = 1
            hotWeapon.recoilForceComponent.minHorizontalJitter = 1;
            hotWeapon.recoilForceComponent.maxHorizontalJitter = 1;
            hotWeapon.recoilForceComponent.minVerticalJitter = 1;
            hotWeapon.recoilForceComponent.maxVerticalJitter = 1;
        }
        hotWeapon.recoilForceComponent.onStartRecoil.add(() => { console.log("recoilForceComponent.onStartRecoilForce") });
    }
}
```

___

### reloadComponent <Score text="reloadComponent" /> 

• **reloadComponent**: [`HotWeaponReloadComponent`](mw.HotWeaponReloadComponent.md)

换弹功能。

<span style="font-size: 14px;">
使用示例: 创建一个名为"HotWeaponReloadSample1"的脚本，放置在对象管理器中，打开脚本，输入以下代码保存，运行游戏，代码如下：
</span>

```ts
@Component
export default class HotWeaponReloadSample1 extends Script {
    protected onStart(): void {
        // 构造
        const hotWeapon = this.gameObject as HotWeapon;

        if (SystemUtil.isServer()) {

            hotWeapon.reloadEnabled = true;
            hotWeapon.reloadComponent.reloadDuration = 2;
            hotWeapon.reloadComponent.animationAssetId = "4171";

            hotWeapon.reloadComponent.onStartReload.add(() => { console.log("reloadComponent.onStartReload Server") });
            hotWeapon.reloadComponent.onEndReload.add(() => { console.log("reloadComponent.onEndReload Server") });
        } else if (SystemUtil.isClient()) {
            hotWeapon.reloadComponent.onStartReload.add(() => { console.log("reloadComponent.onStartReload Client") });
            hotWeapon.reloadComponent.onEndReload.add(() => { console.log("reloadComponent.onEndReload Client") });
        }
    }
}
```

## Accessors

### accuracyOfFireEnabled <Score text="accuracyOfFireEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **accuracyOfFireEnabled**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **accuracyOfFireEnabled**(`isEnabled`): `void` <Badge type="tip" text="server" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


是否开启了射击精度组件。

#### Returns

| `boolean` | 是否开启了射击精度组件 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否开启射击精度组件。

默认开启

#### Parameters

| `isEnabled` `boolean` |  射击精度组件启用状态 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### aimEnabled <Score text="aimEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **aimEnabled**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **aimEnabled**(`value`): `void` <Badge type="tip" text="server" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


是否开启了瞄准组件。

#### Returns

| `boolean` | 是否开启了瞄准组件 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否开启瞄准组件。

默认开启

#### Parameters

| `value` `boolean` |  瞄准组件启用状态 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### loadEnabled <Score text="loadEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **loadEnabled**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **loadEnabled**(`isEnabled`): `void` <Badge type="tip" text="server" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


是否开启了上膛组件。

#### Returns

| `boolean` | 是否开启了上膛组件 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否开启上膛组件。

默认开启

#### Parameters

| `isEnabled` `boolean` |  上膛组件启用状态 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### recoilForceEnabled <Score text="recoilForceEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **recoilForceEnabled**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **recoilForceEnabled**(`isEnabled`): `void` <Badge type="tip" text="server" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否开启了后坐力组件。

#### Returns

| `boolean` | 是否开启了后坐力组件 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否开启后座力组件。

默认开启

#### Parameters

| `isEnabled` `boolean` |  后座力组件启用状态 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### reloadEnabled <Score text="reloadEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **reloadEnabled**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **reloadEnabled**(`isEnabled`): `void` <Badge type="tip" text="server" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


是否开启了换弹组件。

#### Returns

| `boolean` | 是否开启了换弹组件 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否开启换弹组件。

默认开启

#### Parameters

| `isEnabled` `boolean` |  换弹组件启用状态 |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods

___

### breakLoad <Score text="breakLoad" /> 

• **breakLoad**(): `void` <Badge type="tip" text="other" />

打断上膛。


<span style="font-size: 14px;">
使用示例: 创建一个名为"HotWeaponSample10"的脚本，放置在对象管理器中热武器对象子级，打开脚本，输入以下代码保存，运行游戏，代码如下：
</span>

```ts
@Component
export default class HotWeaponSample10 extends Script {
    protected onStart(): void {
       const hotWeapon = this.gameObject as HotWeapon;
       if (SystemUtil.isClient()) {
           // 热武器需要先装备上，见方法 equipment
           InputUtil.onKeyDown(Keys.Two, () => {
               // 开始执行操作
               if (hotWeapon.getCurrentState() == HotWeaponState.Loading) {
                   hotWeapon.breakLoad();
               } else {
                   hotWeapon.load();
               }
           });
       }
    }
}
```

___

### breakReload <Score text="breakReload" /> 

• **breakReload**(): `void` <Badge type="tip" text="other" />

打断换弹


<span style="font-size: 14px;">
使用示例: 创建一个名为"HotWeaponSample9"的脚本，放置在对象管理器中热武器对象子级，打开脚本，输入以下代码保存，运行游戏，按下"2"键，热武器换弹，中止换弹，代码如下：
</span>

```ts
@Component
export default class HotWeaponSample9 extends Script {
    protected onStart(): void {
       const hotWeapon = this.gameObject as HotWeapon;
       if (SystemUtil.isClient()) {
           // 热武器需要先装备上，见方法 equipment
           InputUtil.onKeyDown(Keys.Two, () => {
               // 开始执行操作
               if (hotWeapon.getCurrentState() == HotWeaponState.Reloading) {
                   hotWeapon.breakReload();
               } else {
                   hotWeapon.reload(30);
               }
           });
       }
    }
}
```

___

### cloneComponentsData <Score text="cloneComponentsData" /> 

• **cloneComponentsData**(`otherHotWeapon`): `void` <Badge type="tip" text="server" />

从传入的热武器逻辑对象中拷贝所有组件数据到当前的热武器中。

#### Parameters

| `otherHotWeapon` [`HotWeapon`](mw.HotWeapon.md) |  数据源。 |
| :------ | :------ |


::: warning Precautions

无法拷贝代理委托绑定事件，完成拷贝后，数据同步到客户端有较短延迟。

:::

___

### equip <Score text="equip" /> 

• **equip**(`character`, `slotName`): `void` <Badge type="tip" text="other" />

装备热武器到角色的指定插槽位置

#### Parameters

| `character` [`Character`](mw.Character.md) |  该武器的装备对象 |
| :------ | :------ |
| `slotName` [`HumanoidSlotType`](../enums/mw.HumanoidSlotType.md) |  要装备到角色上的插槽名称 |


如果想将武器装备在角色身上，需要在服务端调用此函数。客户端调用不会报错，但不生效。

<span style="font-size: 14px;">
使用示例: 创建一个名为"HotWeaponSample"的脚本，打开脚本，输入以下代码保存，此示例为动态加载热武器与武器模型资源，不需要在右侧栏配置，运行游戏，一个热武器装备到角色右手上，代码如下：
</span>

```ts
@Component
export default class weapon extends Script {

   private hotweapon:HotWeapon;
   private gun:Model;

   protected async onStart(): Promise<void> {
       if(SystemUtil.isServer()) {
           this.hotweapon = await GameObject.asyncSpawn<HotWeapon>("HotWeapon",{
               replicates:true,
               transform: new Transform(new Vector(500,0,0), new Rotation(0, 0, 0), new Vector(1)),
           });
           this.gun = await GameObject.asyncSpawn<Model>("44980",{
               replicates:true,
               transform: new Transform(new Vector(500,0,0), new Rotation(0, 0, 0), new Vector(1)),
           });
           this.gun.parent = this.hotweapon;
           this.gun.setCollision(PropertyStatus.Off);
           Player.onPlayerJoin.add(()=>{
               Player.getAllPlayers().forEach(element => {
                   this.player = element.character;
               });
               this.hotweapon.equip(this.player,HumanoidSlotType.RightHand);
          })
       }
   }
}
```

___

### getBulletLocWhileSpawnOnScreenCenter <Score text="getBulletLocWhileSpawnOnScreenCenter" /> 

• **getBulletLocWhileSpawnOnScreenCenter**(): [`Vector`](mw.Vector.md) <Badge type="tip" text="client" />

使用屏幕中心生成子弹投掷物模式时，获取子弹投掷物生成的location

#### Returns

| [`Vector`](mw.Vector.md) | 子弹投掷物生成的location |
| :------ | :------ |

::: warning Precautions

服务器没有角色相机组件

:::

<span style="font-size: 14px;">
使用示例: 创建一个名为"HotWeaponSample5"的脚本，放置在对象管理器中热武器对象子级，打开脚本，输入以下代码保存，运行游戏，代码如下：
</span>

```ts
@Component
export default class HotWeaponSample5 extends Script {
    protected onStart(): void {
        // 构造
        const hotWeapon = this.gameObject as HotWeapon;
        if (SystemUtil.isClient()) {
            const bulletLoc = hotWeapon.getBulletLocWhileSpawnOnScreenCenter()
            // 省略：生成投掷物
        }
    }
}
```

___

### getCurrentOwner <Score text="getCurrentOwner" /> 

• **getCurrentOwner**(): [`Character`](mw.Character.md) 

获取当前热武器的所有者

#### Returns

| [`Character`](mw.Character.md) | 当前热武器的所有者 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例: 创建一个名为"HotWeaponSample6"的脚本，放置在对象管理器中热武器对象子级，打开脚本，输入以下代码保存，运行游戏，获取当前热武器所有者代码如下：
</span>

```ts
@Component
export default class HotWeaponSample6 extends Script {
    protected onStart(): void {
        // 构造
        const hotWeapon = this.gameObject as HotWeapon;
        const hotWeaponOwner = hotWeapon.getCurrentOwner()
    }
}
```

___

### getCurrentState <Score text="getCurrentState" /> 

• **getCurrentState**(): [`HotWeaponState`](../enums/mw.HotWeaponState.md) 

获取当前热武器状态

#### Returns

| [`HotWeaponState`](../enums/mw.HotWeaponState.md) | 当前热武器状态 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例: 创建一个名为"HotWeaponSample11"的脚本，放置在对象管理器中热武器对象子级，打开脚本，输入以下代码保存，运行游戏，代码如下：
</span>

```ts
@Component
export default class HotWeaponSample11 extends Script {
    protected onStart(): void {
       const hotWeapon = this.gameObject as HotWeapon;
       // 热武器需要先装备上，见方法 equipment
       const status = hotWeapon.getCurrentState();
    }
}
```

___

### getDefaultCrossHairSize <Score text="getDefaultCrossHairSize" /> 

• **getDefaultCrossHairSize**(`maxShootRange`): `number` <Badge type="tip" text="client" />

传入最大射程，获取默认准星大小

#### Parameters

| `maxShootRange` `number` |  最大射程 <br> default:100 <br> range:[0,100000] type:浮点数 |
| :------ | :------ |

#### Returns

| `number` | 默认准星大小(射击精度半角值) |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例: 创建一个名为"HotWeaponSample3"的脚本，放置在对象管理器中热武器对象子级，打开脚本，输入以下代码保存，运行游戏，代码如下：
</span>

```ts
@Component
export default class HotWeaponSample3 extends mw.Script {
    protected onStart(): void {
        // 构造
        const hotWeapon = this.gameObject as mw.HotWeapon;
        if (SystemUtil.isClient()) {
            // 传入射程，得到准心扩散大小
            const crossHairSize = hotWeapon.getDefaultCrossHairSize(1000)
            // 省略：更新 UI 准心位置
        }
    }
}
```

___

### getShootDirWithDispersion <Score text="getShootDirWithDispersion" /> 

• **getShootDirWithDispersion**(`StartLoc`, `ShootRange`): [`Vector`](mw.Vector.md) <Badge type="tip" text="client" />

非屏幕中心生成子弹模式下，获取子弹飞行方向

#### Parameters

| `StartLoc` [`Vector`](mw.Vector.md) |  子弹生成位置 |
| :------ | :------ |
| `ShootRange` `number` |  最大射程 <br> default:100 <br> range:[0, 100000] type:浮点数 |

#### Returns

| [`Vector`](mw.Vector.md) | 子弹的实际飞行方向 |
| :------ | :------ |

::: warning Precautions

该函数可传入经偏移了的屏幕中心发出的射线方向

:::

::: warning Precautions

服务器没有角色相机组件

:::

___

### load <Score text="load" /> 

• **load**(): `void` <Badge type="tip" text="other" />

上膛


<span style="font-size: 14px;">
使用示例: 创建一个名为"HotWeaponSample10"的脚本，放置在对象管理器中热武器对象子级，打开脚本，输入以下代码保存，运行游戏，代码如下：
</span>

```ts
@Component
export default class HotWeaponSample10 extends Script {
    protected onStart(): void {
       const hotWeapon = this.gameObject as HotWeapon;
       if (SystemUtil.isClient()) {
           // 热武器需要先装备上，见方法 equipment
           InputUtil.onKeyDown(Keys.Two, () => {
               // 开始执行操作
               if (hotWeapon.getCurrentState() == HotWeaponState.Loading) {
                   hotWeapon.breakLoad();
               } else {
                   hotWeapon.load();
               }
           });
       }
    }
}
```

___

### reload <Score text="reload" /> 

• **reload**(`bulletSize`): `void` <Badge type="tip" text="other" />

换弹

#### Parameters

| `bulletSize` `number` |  子弹数 <br> range:[1, ClipSize] type: 整形 |
| :------ | :------ |


<span style="font-size: 14px;">
使用示例: 创建一个名为"HotWeaponSample9"的脚本，放置在对象管理器中热武器对象子级，打开脚本，输入以下代码保存，运行游戏，按下"2"键，热武器换弹，中止换弹，代码如下：
</span>

```ts
@Component
export default class HotWeaponSample9 extends Script {
    protected onStart(): void {
       const hotWeapon = this.gameObject as HotWeapon;
       if (SystemUtil.isClient()) {
           // 热武器需要先装备上，见方法 equipment
           InputUtil.onKeyDown(Keys.Two, () => {
               // 开始执行操作
               if (hotWeapon.getCurrentState() == HotWeaponState.Reloading) {
                   hotWeapon.breakReload();
               } else {
                   hotWeapon.reload(30);
               }
           });
       }
    }
}
```

___

### startFire <Score text="startFire" /> 

• **startFire**(): `void` <Badge type="tip" text="other" />

开火


<span style="font-size: 14px;">
使用示例: 创建一个名为"HotWeaponSample8"的脚本，放置在对象管理器中热武器对象子级，打开脚本，输入以下代码保存，运行游戏，代码如下：
</span>

```ts
@Component
export default class HotWeaponSample8 extends Script {
    protected onStart(): void {
       const hotWeapon = this.gameObject as HotWeapon;
       if (SystemUtil.isClient()) {
           // 热武器需要先装备上，见方法 equipment
           InputUtil.onKeyDown(Keys.Two, () => {
               // 开始执行操作
               if (hotWeapon.getCurrentState() == HotWeaponState.Firing) {
                   hotWeapon.stopFire();
               } else {
                   hotWeapon.startFire();
               }
           });
       }
    }
}
```

___

### stopFire <Score text="stopFire" /> 

• **stopFire**(): `void` <Badge type="tip" text="other" />

停止开火


<span style="font-size: 14px;">
使用示例: 创建一个名为"HotWeaponSample8"的脚本，放置在对象管理器中热武器对象子级，打开脚本，输入以下代码保存，运行游戏，代码如下：
</span>

```ts
@Component
export default class HotWeaponSample8 extends Script {
    protected onStart(): void {
       const hotWeapon = this.gameObject as HotWeapon;
       if (SystemUtil.isClient()) {
           // 热武器需要先装备上，见方法 equipment
           InputUtil.onKeyDown(Keys.Two, () => {
               // 开始执行操作
               if (hotWeapon.getCurrentState() == HotWeaponState.Firing) {
                   hotWeapon.stopFire();
               } else {
                   hotWeapon.startFire();
               }
           });
       }
    }
}
```

___

### unequip <Score text="unequip" /> 

• **unequip**(): `void` <Badge type="tip" text="other" />

卸载热武器。

