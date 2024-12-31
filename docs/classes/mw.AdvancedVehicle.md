[玩法](../groups/玩法.玩法.md) / AdvancedVehicle

# AdvancedVehicle <Badge type="tip" text="Class" /> <Score text="AdvancedVehicle" />

四轮载具

四轮载具是指模拟四个车轮的交通工具，例如汽车、卡车等。它们被设计成能够在游戏中自由移动、加速和转向，给玩家带来真实的驾驶体验。

::: warning Precautions

注意事项
1. 在未设置有效的owner之前，载具不会进行物理模拟，可能会遇到悬空等现象。
2. 载具由set owner时指定的玩家客户端控制。如果想设置载具位置，仅在服务器端设置位置是无效的，需要主控端一起修改。
3. 应注意同一客户端同时控制的载具数量，数量过大会影响载具的同步。建议在5个以内。

:::

<span style="font-size: 14px;">
使用示例: 通过脚本动态创建载具并绑定控制逻辑。创建一个名为"VehicleExample"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏。按下 Q 键创建载具，走到触发器范围自动上车，WASD 进行驾驶，F 键下车。代码如下：
</span>

```ts
enum VehicleEvents {
    createVehicle_C2S = "createVehicle_C2S",
    createVehicle_S2C = "createVehicle_S2C",
    outOfVehicle_local = "outOfVehicle_local",
}

@Component
export default class VehicleSample extends Script {

    // 该属性暴露在属性面板中，可以方便的进行调整。
    @Property({ displayName: "载具生成位置", hideInEditor: false })
    private vehicleSpawnLoc: Vector = new Vector(100, 100, 200);

    // 当前控制的载具。
    private vehicle: AdvancedVehicle = null;

    // 当前载具下面的交互物。
    private interactor: Interactor = null;

    // 当前载具下面的触发器，用于上下车。
    private trigger: Trigger = null;

    // 当前绑定的按钮事件handle，用于下车时解除绑定。
    private controlEventsHandle: mw.EventListener[] = [];

    // 当脚本被实例后，会在第一帧更新前调用此函数。
    protected onStart(): void {
        AssetUtil.asyncDownloadAsset("14015");

        this.bindCreationEvents();
    }

    // 绑定载具创建的事件
    private bindCreationEvents(): void {
        if (SystemUtil.isServer()) {
            mw.Event.addClientListener(VehicleEvents.createVehicle_C2S, async (player: Player) => {
                // 创建载具。
                this.vehicle = await mw.GameObject.asyncSpawn<mw.AdvancedVehicle> ("Vehicle4W", {
                    replicates: true,
                    transform: new Transform(this.vehicleSpawnLoc, new Rotation(0, 0, 0), new Vector(1)),
                })

                // 创建触发器。
                this.trigger = await mw.GameObject.asyncSpawn<mw.Trigger> ("Trigger", {
                    replicates: true,
                })

                // 创建交互物。
                this.interactor = await mw.GameObject.asyncSpawn<mw.Interactor>("Interactor", {
                    replicates: true,
                })

                // 创建一个Box，作为车身。
                const vehicleMesh = await mw.GameObject.asyncSpawn<mw.Model>("197386", {
                    replicates: true,
                })

                // 设置父子级关系。
                this.interactor.parent = this.vehicle;
                this.trigger.parent = this.vehicle;
                vehicleMesh.parent = this.vehicle;

                // 调整相对位置，使得玩家上车时刚好坐在Box上，下车时在触发器旁边。
                this.interactor.localTransform.position = new mw.Vector(0, 0, 150);
                this.trigger.localTransform.position = new mw.Vector(0, -100, 0);
                vehicleMesh.localTransform.position= new mw.Vector(0, 0, 50);

                // 通知发起请求的客户端，载具已经创建完成。因为我们只通知了发起请求的客户端，所以每个客户端只能驾驶自己请求创建的载具。
                mw.Event.dispatchToClient(player, VehicleEvents.createVehicle_S2C, [
                    this.vehicle.gameObjectId,
                    this.trigger.gameObjectId,
                    this.interactor.gameObjectId,
                ])
            })
        } else {
            InputUtil.onKeyDown(Keys.Q, () => {
                // 通过RPC调用，在服务器上动态生成载具以及触发器，交互物。
                mw.Event.dispatchToServer(VehicleEvents.createVehicle_C2S);
            })

            // 客户端监听服务器生成完毕的消息，绑定触发器的事件，实现上下车功能。
            mw.Event.addServerListener(VehicleEvents.createVehicle_S2C, async (info: string[]) => {
                const [vehicleGUID, triggerGUID, interactorGUID] = info;
                console.log(`vehicleGUID = [${vehicleGUID}], triggerGUID = [${triggerGUID}], interactorGUID = [${interactorGUID}]`);

                this.vehicle = await GameObject.asyncFindGameObjectById(vehicleGUID) as AdvancedVehicle;
                this.trigger = await GameObject.asyncFindGameObjectById(triggerGUID) as Trigger;
                this.interactor = await GameObject.asyncFindGameObjectById(interactorGUID) as Interactor;

                this.bindInOutVehicleEvents();
            })
        }
    }

    // 绑定触发器的事件，实现上下车功能。
    private bindInOutVehicleEvents(): void {
        // 通过触发器自动上车
        this.trigger.onEnter.add(async (chara: Character) => {
            // 判断是否是玩家角色触碰的触发器，且是当前玩家。
            if (chara && chara.player == await mw.Player.asyncGetLocalPlayer()) {
                // 关闭角色碰撞，避免与载具发生相互作用。
                chara.setCollision(CollisionStatus.Off);
                // 激活交互物，让角色坐在车上。
                this.interactor.enter(chara, mw.HumanoidSlotType.Buttocks, "14015");
                // 设置载具的驾驶员，此时开始模拟物理，可以驾驶。
                this.vehicle.owner = chara.player;
                // 调整一些参数。
                const handle_press_one = InputUtil.onKeyDown(Keys.One, () => {
                    // 按下 1 调整载具质量
                    this.adjustVehicleMass();
                });
                this.controlEventsHandle.push(handle_press_one);

                const handle_press_two = InputUtil.onKeyDown(Keys.Two, () => {
                    // 按下 2 调整载具摩擦力系数
                    this.adjustVehicleFriction();
                });
                this.controlEventsHandle.push(handle_press_two);

                const handle_press_three = InputUtil.onKeyDown(Keys.Three, () => {
                    // 按下 3 调整载具发动机最大转速
                    this.adjustVehicleMaxEngineRPM();
                });
                this.controlEventsHandle.push(handle_press_three);

                const handle_press_four = InputUtil.onKeyDown(Keys.Four, () => {
                    // 按下 4 调整载具加速度
                    this.adjustVehicleAcceleration();
                });
                this.controlEventsHandle.push(handle_press_four);

                const handle_press_five = InputUtil.onKeyDown(Keys.Five, () => {
                    // 按下 5 调整载具制动力矩
                    this.adjustVehicleBrakingTorque();
                });
                this.controlEventsHandle.push(handle_press_five);

                this.VehicleKeyEvents();
            }
        })

        // 监听下车事件。
        mw.Event.addLocalListener(VehicleEvents.outOfVehicle_local, async () => {
            const player = await Player.asyncGetLocalPlayer();
            // 设置下车位置在触发器左边。
            const outOfVehicleLoc = this.trigger.worldTransform.position.add(new Vector(0, -100, 50));
            // 结束交互，角色下车。
            this.interactor.leave(outOfVehicleLoc);
            // 开启角色碰撞，避免掉下地面和其它碰撞不正确的问题。
            player.character.setCollision(CollisionStatus.On);
            // 清空载具驾驶员，此时依然会模拟物理，但无法继续控制。
            this.vehicle.owner = null;

            this.clearControlEvents();
        })
    }

    // 通过按钮控制载具移动。
    private VehicleKeyEvents() {
        this.clearControlEvents();

        //按下UP键，载具加油前进；
        const handle_up_1 = InputUtil.onKeyDown(Keys.W, () => {
            this.vehicle.throttleInput = 1;
        });
        const handle_up_0 = InputUtil.onKeyUp(Keys.W, () => {
            this.vehicle.throttleInput = 0;
        });
        this.controlEventsHandle.push(handle_up_1, handle_up_0);

        //按下Down键，载具减速后退；
        const handle_down_1 = InputUtil.onKeyDown(Keys.S, () => {
            this.vehicle.throttleInput = -1;
        });
        const handle_down_0 = InputUtil.onKeyUp(Keys.S, () => {
            this.vehicle.throttleInput = 0;
        });
        this.controlEventsHandle.push(handle_down_1, handle_down_0);

        //按下LEFT键，载具左转；
        const handle_left_1 = InputUtil.onKeyDown(Keys.A, () => {
            this.vehicle.steeringInput = -1;
        });
        const handle_left_0 = InputUtil.onKeyUp(Keys.A, () => {
            this.vehicle.steeringInput = 0;
        });
        this.controlEventsHandle.push(handle_left_1, handle_left_0);

        //按下RIGHT键，载具右转；
        const handle_right_1 = InputUtil.onKeyDown(Keys.D, () => {
            this.vehicle.steeringInput = 1;
        });
        const handle_right_0 = InputUtil.onKeyUp(Keys.D, () => {
            this.vehicle.steeringInput = 0;
        });
        this.controlEventsHandle.push(handle_right_1, handle_right_0);

        //按下SpaceBar键，载具刹车；
        const handle_spaceBar_1 = InputUtil.onKeyDown(Keys.SpaceBar, () => {
            this.vehicle.handbrakeInputEnable = true;
        });
        const handle_spaceBar_0 = InputUtil.onKeyUp(Keys.SpaceBar, () => {
            this.vehicle.handbrakeInputEnable = false;
        });
        this.controlEventsHandle.push(handle_spaceBar_1, handle_spaceBar_0);

        //按下F键，下车。
        const handle_f = InputUtil.onKeyDown(Keys.F, () => {
            mw.Event.dispatchToLocal(VehicleEvents.outOfVehicle_local);
        });
        this.controlEventsHandle.push(handle_f);
    }

    // 解除绑定的按钮事件。
    private clearControlEvents(): void {
        for (const handle of this.controlEventsHandle) {
            handle.isConnected && handle.disconnect();
        }

        this.controlEventsHandle = [];
    }

    // 调整载具质量（1500与10000来回切换）。
    private adjustVehicleMass(): void {
        if (this.vehicle.mass == 1500) {
            this.vehicle.mass = 10000;
        } else {
            this.vehicle.mass = 1500;
        }
    }

    // 调整载具摩擦力系数（0.01与3来回切换）。
    private adjustVehicleFriction(): void {
        if (this.vehicle.friction == 3) {
            this.vehicle.friction = 0.01;
        } else {
            this.vehicle.friction = 3;
        }
    }

    // 调整载具发动机最大转速（1000与6000来回切换）。
    private adjustVehicleMaxEngineRPM(): void {
        if (this.vehicle.maxEngineRPM == 6000) {
            this.vehicle.maxEngineRPM = 1000;
        } else {
            this.vehicle.maxEngineRPM = 6000;
        }
    }

    // 调整载具加速度（0.1与1来回切换）。
    private adjustVehicleAcceleration(): void {
        if (this.vehicle.acceleration == 1) {
            this.vehicle.acceleration = 0.1;
        } else {
            this.vehicle.acceleration = 1;
        }
    }

    // 调整载具制动力矩（0与1500来回切换）。
    private adjustVehicleBrakingTorque(): void {
        if (this.vehicle.brakingTorque == 1500) {
            this.vehicle.brakingTorque = 0;
        } else {
            this.vehicle.brakingTorque = 1500;
        }
    }
}
```

## Hierarchy

- [`GameObject`](mw.GameObject.md)

  ↳ **`AdvancedVehicle`**

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
| **[acceleration](mw.AdvancedVehicle.md#acceleration)**(): `number`   |
| :-----|
| 获取加速度。|
| **[brakingTorque](mw.AdvancedVehicle.md#brakingtorque)**(): `number`   |
| 获取制动力矩。单位：牛*米（N*m）|
| **[currentGearLevel](mw.AdvancedVehicle.md#currentgearlevel)**(): `number`   |
| 获取当前档位级别。|
| **[driveMode](mw.AdvancedVehicle.md#drivemode)**(): [`VehicleDriveMode4WNew`](../enums/mw.VehicleDriveMode4WNew.md)   |
| 获取载具驱动模式。|
| **[friction](mw.AdvancedVehicle.md#friction)**(): `number`   |
| 获取载具摩擦力系数。|
| **[handbrakeInputEnable](mw.AdvancedVehicle.md#handbrakeinputenable)**(`useHandbrake`: `boolean`): `void`   |
| 是否进行手刹，true-进行制动, false-取消制动。|
| **[mass](mw.AdvancedVehicle.md#mass)**(): `number`   |
| 获取质量。|
| **[maxEngineRPM](mw.AdvancedVehicle.md#maxenginerpm)**(): `number`   |
| 获取最大发动机转速。单位：转/分（r/min）|
| **[maxGearLevel](mw.AdvancedVehicle.md#maxgearlevel)**(): `number`   |
| 获取最大档位级别。如返回值为4，则表示有[-1, 0, 1, 2, 3, 4]这些档位。|
| **[owner](mw.AdvancedVehicle.md#owner)**(): [`Player`](mw.Player.md) <Badge type="tip" text="other" />  |
| 获取载具驾驶员。|
| **[simulatePhysics](mw.AdvancedVehicle.md#simulatephysics)**(`shouldSimulate`: `boolean`): `void`   |
| 设置四轮载具是否开启物理模拟计算，需要在客户端调用。|
| **[steeringInput](mw.AdvancedVehicle.md#steeringinput)**(`newInput`: `number`): `void`   |
| 控制载具左/右转向，设置转向幅度，取值范围[-1,1]，大于0时右转，小于0则左转。|
| **[throttleInput](mw.AdvancedVehicle.md#throttleinput)**(`newInput`: `number`): `void`   |
| 控制载具前进/后退，设置油门大小，取值范围[-1,1]，大于0时加速，小于0则减速。|
| **[velocity](mw.AdvancedVehicle.md#velocity)**(): `number`   |
| 获取当前行驶速度，单位：米/秒（m/s）。|
| **[wheelNum](mw.AdvancedVehicle.md#wheelnum)**(): `number`   |
| 获取车轮数量。|


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
| **[gearDown](mw.AdvancedVehicle.md#geardown)**(): `void`   |
| :-----|
| 降一档，立即切换。|
| **[gearUp](mw.AdvancedVehicle.md#gearup)**(): `void`   |
| 升一档，立即切换。|
| **[getGearData](mw.AdvancedVehicle.md#getgeardata)**(`gearLevel`: `number`): [`VehicleGearDataNew`](../modules/Core.mw.md#vehiclegeardatanew)   |
| 获取指定档位属性|
| **[getWheelMaxSteerAngle](mw.AdvancedVehicle.md#getwheelmaxsteerangle)**(`wheelId`: `number`): `number`   |
| 获取车轮最大转向角度，单位：度（°）。|
| **[getWheelModel](mw.AdvancedVehicle.md#getwheelmodel)**(`wheelId`: `number`): `string`   |
| 获取轮胎绑定对象。|
| **[getWheelRadius](mw.AdvancedVehicle.md#getwheelradius)**(`wheelId`: `number`): `number`   |
| 获取车轮半径，单位：厘米（cm）。|
| **[onDestroy](mw.AdvancedVehicle.md#ondestroy)**(): `void`   |
| 销毁|
| **[setCullDistance](mw.AdvancedVehicle.md#setculldistance)**(`inCullDistance`: `number`): `void`   |
| 与玩家之间超出此距离的对象将被剪裁，最终的裁剪距离会和画质等级有关；修改此属性≤0时，裁剪距离会根据对象尺寸自动调整(自动启用CullDistanceVolume功能)|
| **[setWheelRadius](mw.AdvancedVehicle.md#setwheelradius)**(`wheelId`: `number`, `Radius`: `number`): `void`   |
| 设置车轮半径，单位：厘米（cm）。|


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

• `get` **acceleration**(): `number` 

</th>
<th style="text-align: left">

• `set` **acceleration**(`acceleration`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取加速度。

#### Returns

| `number` | 载具加速系数 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置加速度。

**`Range`**

[0.01, 100]

#### Parameters

| `acceleration` `number` |  新的加速系数 default: 1 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### brakingTorque <Score text="brakingTorque" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **brakingTorque**(): `number` 

</th>
<th style="text-align: left">

• `set` **brakingTorque**(`Torque`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取制动力矩。单位：牛*米（N*m）

车辆制动力矩是指应用于车辆制动系统的力矩，用于减速或停止车辆运动。它是制动系统产生的力矩，通过制动器（如刹车盘和刹车片）施加到车轮上，从而减少车轮的旋转速度。

#### Returns

| `number` | 当前制动力矩 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置制动力矩。单位：牛*米（N*m）

**`Range`**

[0, 1000000]

#### Parameters

| `Torque` `number` |  新的制动力矩 default: 1500 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### currentGearLevel <Score text="currentGearLevel" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **currentGearLevel**(): `number` 

</th>
<th style="text-align: left">

• `set` **currentGearLevel**(`level`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取当前档位级别。

#### Returns

| `number` | 当前档位级别 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置当前档位级别。

**`Range`**

[-1, 设定的最大档位]

::: warning Precautions

1. 注意输入参数的取值范围。
2. 设置与当前车速不匹配的档位，会自动调整到匹配的档位。如当前车速适应1档，直接设置3档，会逐级（3-2-1）降到1档。

:::

#### Parameters

| `level` `number` |  将要切换到的档位 default: 0 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### driveMode <Score text="driveMode" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **driveMode**(): [`VehicleDriveMode4WNew`](../enums/mw.VehicleDriveMode4WNew.md) 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取载具驱动模式。

#### Returns

| [`VehicleDriveMode4WNew`](../enums/mw.VehicleDriveMode4WNew.md) | 载具驱动模式 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### friction <Score text="friction" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **friction**(): `number` 

</th>
<th style="text-align: left">

• `set` **friction**(`friction`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取载具摩擦力系数。

#### Returns

| `number` | 载具摩擦力系数 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置载具车轮摩擦力系数

**`Range`**

[0.01, 8]

#### Parameters

| `friction` `number` |  新的摩擦力系数 default: 3 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### handbrakeInputEnable <Score text="handbrakeInputEnable" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `set` **handbrakeInputEnable**(`useHandbrake`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


是否进行手刹，true-进行制动, false-取消制动。

::: warning Precautions

输入值发生变化时，调用一次即可。输入值会保持，不需要持续调用。

:::

#### Parameters

| `useHandbrake` `boolean` |  是否进行手刹，true-进行制动, false-取消制动。default: false |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### mass <Score text="mass" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **mass**(): `number` 

</th>
<th style="text-align: left">

• `set` **mass**(`mass`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取质量。

#### Returns

| `number` | 载具质量，单位：千克（kg） |
| :------ | :------ |


</td>
<td style="text-align: left">


设置载具质量，单位：千克（kg）。

**`Range`**

[0.01, 100000]

::: warning Precautions

1. 注意输入参数的取值范围。设置较小的质量，会出现载具抖动等非预期表现。
2. 运行时设置质量，会重新初始化载具，清除任何运行状态。如载具在行驶，设置质量后会停在原地。

:::

#### Parameters

| `mass` `number` |  设置值 default: 1500 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### maxEngineRPM <Score text="maxEngineRPM" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **maxEngineRPM**(): `number` 

</th>
<th style="text-align: left">

• `set` **maxEngineRPM**(`RPM`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取最大发动机转速。单位：转/分（r/min）

#### Returns

| `number` | 载具发动机转速 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置最大发动机转速。单位：转/分（r/min）

**`Range`**

[100, 5000000]

#### Parameters

| `RPM` `number` |  新的载具发动机转速 default: 6000 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### maxGearLevel <Score text="maxGearLevel" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **maxGearLevel**(): `number` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取最大档位级别。如返回值为4，则表示有[-1, 0, 1, 2, 3, 4]这些档位。

::: warning Precautions

最大可切换到的档位。如获取当前档位，请使用getCurrentGearLevel

:::

#### Returns

| `number` | 最大档位级别 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### owner <Score text="owner" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **owner**(): [`Player`](mw.Player.md) <Badge type="tip" text="other" />

</th>
<th style="text-align: left">

• `set` **owner**(`inOwner`): `void` <Badge type="tip" text="other" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取载具驾驶员。

#### Returns

| [`Player`](mw.Player.md) |  |
| :------ | :------ |


</td>
<td style="text-align: left">


设置载具驾驶员。只有驾驶员才可以操作载具。

#### Parameters

| `inOwner` | [`Player`](mw.Player.md) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### simulatePhysics <Score text="simulatePhysics" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `set` **simulatePhysics**(`shouldSimulate`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


设置四轮载具是否开启物理模拟计算，需要在客户端调用。

::: warning Precautions

四轮载具只在set owner成功后才会进行物理模拟。此时关闭物理模拟将无法继续驱动载具移动。

:::

#### Parameters

| `shouldSimulate` `boolean` |  是否启用物理模拟。true-启用，false-不启用 default: true |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### steeringInput <Score text="steeringInput" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `set` **steeringInput**(`newInput`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


控制载具左/右转向，设置转向幅度，取值范围[-1,1]，大于0时右转，小于0则左转。

**`Range`**

[-1, 1]，大于0时右转，小于0则左转。

::: warning Precautions

1. 注意输入参数的取值范围。输入100和1没有区别。
2. 输入值发生变化时，调用一次即可。输入值会保持，不需要持续调用。

:::


#### Parameters

| `newInput` `number` |  设置值 default: 0 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 用按钮和摇杆控制载具
</span>

```ts
   // 通过按钮控制载具油门
   this.btn_forward.onPressed.add(() => {
       vehicle.setThrottleInput(1);
   })

   this.btn_forward.onReleased.add(() => {
       vehicle.setThrottleInput(0);
   })

   // 通过摇杆控制载具，摇杆会同时提供两个轴向(x, y)的输入
   this.joystick.onInputDir.add((vec: mw.Vector2) => {
       // 控制油门
       vehicle.setThrottleInput(vec.y);
       // 控制转向
       vehicle.setSteeringInput(vec.x);
   })
```
___

### throttleInput <Score text="throttleInput" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `set` **throttleInput**(`newInput`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


控制载具前进/后退，设置油门大小，取值范围[-1,1]，大于0时加速，小于0则减速。

**`Range`**

[-1, 1]，大于0时加速，小于0则减速。

::: warning Precautions

1. 注意输入参数的取值范围。输入100和1没有区别。
2. 输入值发生变化时，调用一次即可。输入值会保持，不需要持续调用。

:::


#### Parameters

| `newInput` `number` |  设置值 default: 0 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 用按钮和摇杆控制载具
</span>

```ts
   // 通过按钮控制载具油门
   this.btn_forward.onPressed.add(() => {
       vehicle.throttleInput = 1;
   })

   this.btn_forward.onReleased.add(() => {
       vehicle.throttleInput = 0;
   })

   // 通过摇杆控制载具，摇杆会同时提供两个轴向(x, y)的输入
   this.joystick.onInputDir.add((vec: mw.Vector2) => {
       // 控制油门
       vehicle.throttleInput = vec.y;
       // 控制转向
       vehicle.steeringInput = vec.x;
   })
```
___

### velocity <Score text="velocity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **velocity**(): `number` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取当前行驶速度，单位：米/秒（m/s）。

#### Returns

| `number` | 当前行驶速度 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### wheelNum <Score text="wheelNum" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **wheelNum**(): `number` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取车轮数量。

#### Returns

</td>
</tr></tbody>
</table>

| `number` | 车轮数量 |
| :------ | :------ |

## Methods

___

### gearDown <Score text="gearDown" /> 

• **gearDown**(): `void` 

降一档，立即切换。


___

### gearUp <Score text="gearUp" /> 

• **gearUp**(): `void` 

升一档，立即切换。


___

### getGearData <Score text="getGearData" /> 

• **getGearData**(`gearLevel`): [`VehicleGearDataNew`](../modules/Core.mw.md#vehiclegeardatanew) 

获取指定档位属性

#### Parameters

| `gearLevel` `number` |  指定档位级别 range: [0, 1] type: 浮点数 |
| :------ | :------ |

#### Returns

| [`VehicleGearDataNew`](../modules/Core.mw.md#vehiclegeardatanew) | 指定档位属性 |
| :------ | :------ |

::: warning Precautions

注意输入参数的取值范围

:::

___

### getWheelMaxSteerAngle <Score text="getWheelMaxSteerAngle" /> 

• **getWheelMaxSteerAngle**(`wheelId`): `number` 

获取车轮最大转向角度，单位：度（°）。

#### Parameters

| `wheelId` `number` |  根据序号指定车轮 <br> range: 0.1.2.3 四个参数 type:整数 |
| :------ | :------ |

#### Returns

| `number` | 指定车轮最大转向角度 |
| :------ | :------ |

注意输入参数的取值范围。当前为四轮载具，[0, 1, 2, 3]分别对应[左前, 右前, 左后, 右后]。

___

### getWheelModel <Score text="getWheelModel" /> 

• **getWheelModel**(`wheelId`): `string` 

获取轮胎绑定对象。

#### Parameters

| `wheelId` `number` |  根据序号指定车轮 <br> range: 0.1.2.3 四个参数 type:整数 |
| :------ | :------ |

#### Returns

| `string` | 指定轮胎绑定对象GUID |
| :------ | :------ |

注意输入参数的取值范围。当前为四轮载具，[0, 1, 2, 3]分别对应[左前, 右前, 左后, 右后]。

___

### getWheelRadius <Score text="getWheelRadius" /> 

• **getWheelRadius**(`wheelId`): `number` 

获取车轮半径，单位：厘米（cm）。

#### Parameters

| `wheelId` `number` |  根据序号指定车轮 <br> range: 0.1.2.3 四个参数 type:整数 |
| :------ | :------ |

#### Returns

| `number` | 指定车轮半径 |
| :------ | :------ |

注意输入参数的取值范围。当前为四轮载具，[0, 1, 2, 3]分别对应[左前, 右前, 左后, 右后]。

___

### onDestroy <Score text="onDestroy" /> 

• `Protected` **onDestroy**(): `void` 

销毁


___

### setCullDistance <Score text="setCullDistance" /> 

• **setCullDistance**(`inCullDistance`): `void` 

与玩家之间超出此距离的对象将被剪裁，最终的裁剪距离会和画质等级有关；修改此属性≤0时，裁剪距离会根据对象尺寸自动调整(自动启用CullDistanceVolume功能)

#### Parameters

| `inCullDistance` `number` | 裁剪距离 range: 建议 (2000, 4000) type: 浮点数 |
| :------ | :------ |


::: warning Precautions

最终的裁剪距离会和画质等级有关

:::

___

### setWheelRadius <Score text="setWheelRadius" /> 

• **setWheelRadius**(`wheelId`, `Radius`): `void` 

设置车轮半径，单位：厘米（cm）。

#### Parameters

| `wheelId` `number` |  根据序号指定车轮 <br> range: 0.1.2.3 四个参数 type:整数 |
| :------ | :------ |
| `Radius` `number` |  指定车轮半径 range:不做限制，合理即可 type: 浮点数 |


注意输入参数的取值范围。当前为四轮载具，[0, 1, 2, 3]分别对应[左前, 右前, 左后, 右后]。仅在上车前生效，上车后调用此接口无效果。
