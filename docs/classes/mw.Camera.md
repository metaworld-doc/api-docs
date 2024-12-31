[玩法](../groups/玩法.玩法.md) / Camera

# Camera <Badge type="tip" text="Class" /> <Score text="Camera" />

摄像机

-------------------------

Camera 对象定义 3D 游戏世界的视图。

Camera 的位置在哪里？

在游戏的一个实例中，每个客户端都有自己的与其关联的 Camera 对象。 相机对象仅存在于查看者的客户端上，驻留在该用户的本地中，因此不能直接从服务器进行编辑。

每个客户端的特定 Camera 对象都可以通过该客户端上 Camera.currentCamera 属性进行访问。

Camera 对象如何工作？

相机的属性定义了 3D 游戏世界的当前视图。 其中最重要的是：

- Camera.currentCamera.worldTransform 表示相机的位置和方向。

- Camera.currentCamera.rotationMode 属性调整相机的旋转模式，是否跟随人物旋转而旋转、相机固定不旋转、可由鼠标右键控制旋转三种模式。Camera.currentCamera.positionMode 属性调整相机的位置模式。

- Camera.currentCamera.fov 表示可见的可观察世界的范围。

## Hierarchy

- [`GameObject`](mw.GameObject.md)

  ↳ **`Camera`**

## Table of contents

### Properties <Score text="Properties" /> 
| **[onSwitchComplete](mw.Camera.md#onswitchcomplete)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />  |
| :-----|
| 切换摄像机完成的回调|
| **[springArm](mw.Camera.md#springarm)**: [`SpringArm`](mw.SpringArm.md) <Badge type="tip" text="client" />  |
| 弹簧臂|


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
| **[aspectRatioAxisConstraint](mw.Camera.md#aspectratioaxisconstraint)**(): [`AspectRatioAxisConstraint`](../enums/mw.AspectRatioAxisConstraint.md) <Badge type="tip" text="client" />  |
| :-----|
| 获取横纵比约束|
| **[downAngleLimit](mw.Camera.md#downanglelimit)**(): `number` <Badge type="tip" text="client" />  |
| 获取摄像机向下角度限制|
| **[fadeObstructionEnabled](mw.Camera.md#fadeobstructionenabled)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取是否启用透明效果|
| **[fadeObstructionOpacity](mw.Camera.md#fadeobstructionopacity)**(): `number` <Badge type="tip" text="client" />  |
| 获取透明度|
| **[fixedElevation](mw.Camera.md#fixedelevation)**(): `boolean` <Badge type="tip" text="client" />  |
| 固定摄像机高度|
| **[fov](mw.Camera.md#fov)**(): `number` <Badge type="tip" text="client" />  |
| 获取摄像机视场|
| **[isFrameCaptured](mw.Camera.md#isframecaptured)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取是否每帧捕获|
| **[maxLagDistance](mw.Camera.md#maxlagdistance)**(): `number` <Badge type="tip" text="client" />  |
| 位置最大延迟距离|
| **[positionLagEnabled](mw.Camera.md#positionlagenabled)**(): `boolean` <Badge type="tip" text="client" />  |
| 启用位置延迟|
| **[positionLagSpeed](mw.Camera.md#positionlagspeed)**(): `number` <Badge type="tip" text="client" />  |
| 位置延迟速度|
| **[positionMode](mw.Camera.md#positionmode)**(): [`CameraPositionMode`](../enums/mw.CameraPositionMode.md) <Badge type="tip" text="client" />  |
| 位置模式|
| **[preset](mw.Camera.md#preset)**(`value`: [`CameraPreset`](../enums/mw.CameraPreset.md)): `void`  |
| 设置摄像机预设|
| **[rotationLagEnabled](mw.Camera.md#rotationlagenabled)**(): `boolean` <Badge type="tip" text="client" />  |
| 启用旋转延迟|
| **[rotationLagSpeed](mw.Camera.md#rotationlagspeed)**(): `number` <Badge type="tip" text="client" />  |
| 旋转延迟速度|
| **[rotationMode](mw.Camera.md#rotationmode)**(): [`CameraRotationMode`](../enums/mw.CameraRotationMode.md) <Badge type="tip" text="client" />  |
| 旋转模式|
| **[upAngleLimit](mw.Camera.md#upanglelimit)**(): `number` <Badge type="tip" text="client" />  |
| 向上角度限制|
| **[currentCamera](mw.Camera.md#currentcamera)**(): [`Camera`](mw.Camera.md) <Badge type="tip" text="client" />  |
| 当前摄像机|


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
| **[lock](mw.Camera.md#lock)**(`target`: [`GameObject`](mw.GameObject.md), `val?`: `Object`): `void` <Badge type="tip" text="client" />  |
| :-----|
| 相机锁定目标|
| **[lookAt](mw.Camera.md#lookat)**(`target`: [`GameObject`](mw.GameObject.md)  [`Vector`](mw.Vector.md)): `void` <Badge type="tip" text="client" />  |
| 摄像机朝向目标|
| **[unlock](mw.Camera.md#unlock)**(): `void` <Badge type="tip" text="client" />  |
| 取消锁定目标|
| **[shake](mw.Camera.md#shake)**(`[shake](mw.Camera.md#shake)Info`, `duration?`: `number`): `void` <Badge type="tip" text="client" />  |
| 开始摄像机抖动|
| **[stopShake](mw.Camera.md#stopshake)**(): `void` <Badge type="tip" text="client" />  |
| 停止摄像机抖动|
| **[switch](mw.Camera.md#switch)**(`newCamera`: [`Camera`](mw.Camera.md), `blendTime?`: `number`, `blendFunc?`: [`CameraSwitchBlendFunction`](../enums/mw.CameraSwitchBlendFunction.md), `blendExp?`: `number`): [`Camera`](mw.Camera.md) <Badge type="tip" text="client" />  |
| 切换摄像机|


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

### onSwitchComplete <Score text="onSwitchComplete" /> 

• **onSwitchComplete**: [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> <Badge type="tip" text="client" />

切换摄像机完成的回调

::: warning Precautions

切换到当前摄像机完成执行绑定函数

:::

<span style="font-size: 14px;">
使用示例:创建一个名为"CameraExample"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，在场景中随机创建5个摄像机。按下键盘“1”，切换摄像机.按下键盘“2”，切换回默认摄像机。你将在场景中看到摄像机切换时的效果。代码如下：
</span>

```ts
@Component
export default class CameraExample extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前摄像机
            let myCamera = Camera.currentCamera;
            let curCameraIndex = -1;
            // 在场景中随机创建5个摄像机
            let cameraArray = new Array<Camera>();
            for (let i = 0;
i < 5;
i++) {
                let camera = GameObject.spawn<Camera>("Camera") as Camera;
                camera.worldTransform.position = new Vector(MathUtil.randomInt(-1000, 1000), MathUtil.randomInt(-1000, 1000),MathUtil.randomInt(0, 1000));
                camera.worldTransform.rotation = new Rotation(MathUtil.randomInt(-90, 90), MathUtil.randomInt(-30, 30),MathUtil.randomInt(-150, 150));
                cameraArray.push(camera);
                camera.onSwitchComplete.add(() => {
                    console.log("当前摄像机序号 " + i);
                    curCameraIndex = i;
                });
            }
            // 添加一个按键方法：按下键盘“1”，切换摄像机
            InputUtil.onKeyDown(Keys.One, () => {
                console.log("Switch Camera");
                let newCamera = (curCameraIndex + 1) % 5;
                Camera.switch(cameraArray[newCamera], 5, CameraSwitchBlendFunction.Linear);
            });
            // 添加一个按键方法：按下键盘“2”，切换回默认摄像机
            InputUtil.onKeyDown(Keys.Two, () => {
                console.log("Switch Default Camera");
                Camera.switch(myCamera);
            });
        }
    }
}
```

___

### springArm <Score text="springArm" /> 

• **springArm**: [`SpringArm`](mw.SpringArm.md) <Badge type="tip" text="client" />

弹簧臂

::: warning Precautions

摄像机系统由弹簧臂和摄像机组成，实际挂点是弹簧臂负责，而摄像机是挂载弹簧臂尾端。

:::

<span style="font-size: 14px;">
使用示例:将使用到的资源:"26950"拖入优先加载栏创建一个名为"Camera_SpringArm"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中生成10根柱子用作触发摄像机弹簧杆碰撞，按下键盘“1”，启用/禁用摄像机弹簧杆碰撞，按下键盘“2”，启用/禁用摄像机弹簧杆移动碰撞检测。你可以看到禁用这些属性产生的不同的效果。代码如下：
</span>

```ts
@Component
export default class Camera_SpringArm extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        if(SystemUtil.isServer()) {
            // 生成10根柱子用作摄像机弹簧杆碰撞
            for (let i = 0;
i < 10;
i++) {
                GameObject.spawn<Model>("26950",{transform: new Transform(new Vector(100, i * 100, 0), Rotation.zero, Vector.one)});
            }
        }
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前摄像机
            let myCamera = Camera.currentCamera;
            // 添加一个按键方法：按下键盘“1”，启用/禁用摄像机弹簧杆碰撞
            InputUtil.onKeyDown(Keys.One, () => {
                myCamera.springArm.collisionEnabled = !myCamera.springArm.collisionEnabled;
                console.log("摄像机弹簧臂的碰撞 " + myCamera.springArm.collisionEnabled);
            });
            // 添加一个按键方法：按下键盘“2”，启用/禁用摄像机弹簧杆移动碰撞检测
            InputUtil.onKeyDown(Keys.Two, () => {
                myCamera.springArm.collisionEnabled = !myCamera.springArm.collisionEnabled;
                console.log("摄像机弹簧臂移动碰撞检测 " + myCamera.springArm.collisionEnabled);
            });
        }
    }
}
```

## Accessors

___

### aspectRatioAxisConstraint <Score text="aspectRatioAxisConstraint" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **aspectRatioAxisConstraint**(): [`AspectRatioAxisConstraint`](../enums/mw.AspectRatioAxisConstraint.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **aspectRatioAxisConstraint**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取横纵比约束

::: warning Precautions

设置FOV是约束X轴方向视角角度还是Y轴方向视角角度

:::


#### Returns

| [`AspectRatioAxisConstraint`](../enums/mw.AspectRatioAxisConstraint.md) |  |
| :------ | :------ |


</td>
<td style="text-align: left">


设置透明度

::: warning Precautions

范围0-1，值越大透明度越高，1是完全透明

:::

#### Parameters

| `value` | [`AspectRatioAxisConstraint`](../enums/mw.AspectRatioAxisConstraint.md) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 创建一个名为"Example_Camera_AspectRatioAxisConstraint"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，代码如下：
</span>

```ts
@Component
export default class Example_Camera_AspectRatioAxisConstraint extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取玩家角色
            let myCharacter = myPlayer.character;
            // 获取当前摄像机
            let myCamera = Camera.currentCamera;
            // 开启透明效果
            myCamera.transparencyEnabled = true;
            // 添加一个按键方法：按下键盘“1”，设置为保持X轴FOV
            InputUtil.onKeyDown(Keys.One, () => {
                myCamera.aspectRatioAxisConstraint = AspectRatioAxisConstraint.maintainXFOV;
            });
            // 添加一个按键方法：按住键盘“2”，设置为保持Y轴FOV
            InputUtil.onKeyPress(Keys.Two, () => {
                myCamera.aspectRatioAxisConstraint = AspectRatioAxisConstraint.maintainYFOV;
            });
        }
    }
}
```
___

### downAngleLimit <Score text="downAngleLimit" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **downAngleLimit**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **downAngleLimit**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取摄像机向下角度限制

::: warning Precautions

摄像机向下旋转时的最大角度使用范围在0-90之间。

:::


#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


设置摄像机向下角度限制

::: warning Precautions

摄像机向下旋转时的最大角度使用范围在0-90之间。

:::

#### Parameters

| `value` `number` | 角度限制 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 创建一个名为"Example_Camera_DownAngleLimit"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，置摄像机角度限制，上抬最大角度为30，下旋最大角度为10。你将在场景中看到摄像机旋转受限的效果。代码如下：
</span>

```ts
@Component
export default class Example_Camera_DownAngleLimit extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取玩家角色
            let myCharacter = myPlayer.character;
            // 获取当前摄像机
            let myCamera = Camera.currentCamera;
            // 开启摄像机位置延迟
            myCamera.positionLagEnabled = true;
            // 位置延迟恢复速度1
            myCamera.positionLagSpeed = 1;
            // 最大位置延迟距离200
            myCamera.maxLagDistance = 200;
            // 开启摄像机旋转延迟
            myCamera.rotationLagEnabled = true;
            // 旋转延迟恢复速度2
            myCamera.rotationLagSpeed = 2;
            // 设置摄像机角度限制
            myCamera.upAngleLimit = 30
            myCamera.downAngleLimit = 10;
            // 添加一个按键方法：按下键盘“1”，固定摄像机高度后跳跃
            InputUtil.onKeyDown(Keys.One, () => {
                myCamera.fixedElevation = true;
                myCharacter.jump();
                setTimeout(() => {
                    myCamera.fixedElevation = false;
                }, 1000);
            });
            // 添加一个按键方法：按住键盘“2”，增大摄像机FOV
            InputUtil.onKeyPress(Keys.Two, () => {
                myCamera.fov += 1;
            });
            // 添加一个按键方法：按住键盘“3”，减少摄像机FOV
            InputUtil.onKeyPress(Keys.Three, () => {
                myCamera.fov -= 1;
            });
        }
    }
}
```
___

### fadeObstructionEnabled <Score text="fadeObstructionEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **fadeObstructionEnabled**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **fadeObstructionEnabled**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否启用透明效果

::: warning Precautions

在进入弹簧臂范围的物体会透明，离开后恢复

:::

#### Returns

| `boolean` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否启用透明效果

::: warning Precautions

在进入弹簧臂范围的物体会透明，离开后恢复

:::

#### Parameters

| `value` | `boolean` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### fadeObstructionOpacity <Score text="fadeObstructionOpacity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **fadeObstructionOpacity**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **fadeObstructionOpacity**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取透明度

::: warning Precautions

范围0-1，值越大透明度越高，1是完全透明

:::


#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


设置透明度

::: warning Precautions

范围0-1，值越大透明度越高，1是完全透明

:::

#### Parameters

| `value` | `number` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 创建一个名为"Example_Camera_FixedElevation"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“1”，固定摄像机高度后跳跃。你将在场景中看到角色跳跃时摄像机跟随角色高度的效果。代码如下：
</span>

```ts
@Component
export default class Example_Camera_FixedElevation extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取玩家角色
            let myCharacter = myPlayer.character;
            // 获取当前摄像机
            let myCamera = Camera.currentCamera;
            // 开启透明效果
            myCamera.transparencyEnabled = true;
            // 添加一个按键方法：按下键盘“1”，增大透明度
            InputUtil.onKeyDown(Keys.One, () => {
                myCamera.transparency += 0.1;
            });
            // 添加一个按键方法：按住键盘“2”，减小透明度
            InputUtil.onKeyPress(Keys.Two, () => {
                myCamera.transparency -= 0.1;
            });
        }
    }
}
```
___

### fixedElevation <Score text="fixedElevation" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **fixedElevation**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **fixedElevation**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


固定摄像机高度

::: warning Precautions

无论挂点如何移动摄像机位置的z轴值不会被改变。

:::


#### Returns

| `boolean` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


固定摄像机高度

::: warning Precautions

无论挂点如何移动摄像机位置的z轴值不会被改变。

:::

#### Parameters

| `value` `boolean` | 是否固定 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 创建一个名为"Example_Camera_FixedElevation"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“1”，固定摄像机高度后跳跃。你将在场景中看到角色跳跃时摄像机跟随角色高度的效果。代码如下：
</span>

```ts
@Component
export default class Example_Camera_FixedElevation extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取玩家角色
            let myCharacter = myPlayer.character;
            // 获取当前摄像机
            let myCamera = Camera.currentCamera;
            // 开启摄像机位置延迟
            myCamera.positionLagEnabled = true;
            // 位置延迟恢复速度1
            myCamera.positionLagSpeed = 1;
            // 最大位置延迟距离200
            myCamera.maxLagDistance = 200;
            // 开启摄像机旋转延迟
            myCamera.rotationLagEnabled = true;
            // 旋转延迟恢复速度2
            myCamera.rotationLagSpeed = 2;
            // 设置摄像机角度限制
            myCamera.upAngleLimit = 30
            myCamera.downAngleLimit = 10;
            // 添加一个按键方法：按下键盘“1”，固定摄像机高度后跳跃
            InputUtil.onKeyDown(Keys.One, () => {
                myCamera.fixedElevation = true;
                myCharacter.jump();
                setTimeout(() => {
                    myCamera.fixedElevation = false;
                }, 1000);
            });
            // 添加一个按键方法：按住键盘“2”，增大摄像机FOV
            InputUtil.onKeyPress(Keys.Two, () => {
                myCamera.fov += 1;
            });
            // 添加一个按键方法：按住键盘“3”，减少摄像机FOV
            InputUtil.onKeyPress(Keys.Three, () => {
                myCamera.fov -= 1;
            });
        }
    }
}
```
___

### fov <Score text="fov" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **fov**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **fov**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取摄像机视场

::: warning Precautions

FOV，也就是透视模式下的水平视野角度，FOV越大，可见的视野角度越大

:::


#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


设置摄像机视场

::: warning Precautions

FOV，也就是透视模式下的水平视野角度，FOV越大，可见的视野角度越大

:::

#### Parameters

| `value` `number` | 视场 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 创建一个名为"Example_Camera_FOV"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按住键盘“2”，增大摄像机FOV,按住键盘“3”，减少摄像机FOV。你将在场景中看到摄像机FOV变化的效果。代码如下：
</span>

```ts
@Component
export default class Example_Camera_FOV extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取玩家角色
            let myCharacter = myPlayer.character;
            // 获取当前摄像机
            let myCamera = Camera.currentCamera;
            // 开启摄像机位置延迟
            myCamera.positionLagEnabled = true;
            // 位置延迟恢复速度1
            myCamera.positionLagSpeed = 1;
            // 最大位置延迟距离200
            myCamera.maxLagDistance = 200;
            // 开启摄像机旋转延迟
            myCamera.rotationLagEnabled = true;
            // 旋转延迟恢复速度2
            myCamera.rotationLagSpeed = 2;
            // 设置摄像机角度限制
            myCamera.upAngleLimit = 30
            myCamera.downAngleLimit = 10;
            // 添加一个按键方法：按下键盘“1”，固定摄像机高度后跳跃
            InputUtil.onKeyDown(Keys.One, () => {
                myCamera.fixedElevation = true;
                myCharacter.jump();
                setTimeout(() => {
                    myCamera.fixedElevation = false;
                }, 1000);
            });
            // 添加一个按键方法：按住键盘“2”，增大摄像机FOV
            InputUtil.onKeyPress(Keys.Two, () => {
                myCamera.fov += 1;
            });
            // 添加一个按键方法：按住键盘“3”，减少摄像机FOV
            InputUtil.onKeyPress(Keys.Three, () => {
                myCamera.fov -= 1;
            });
        }
    }
}
```
___

### isFrameCaptured <Score text="isFrameCaptured" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **isFrameCaptured**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **isFrameCaptured**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否每帧捕获

::: warning Precautions

false时只会捕获一次，节省性能

:::


#### Returns

| `boolean` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否每帧捕获

::: warning Precautions

false时只会捕获一次，节省性能

:::

#### Parameters

| `value` | `boolean` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 创建一个名为"Example_Camera_FrameCaptured"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，在UI编辑器中添加图片，运行游戏，代码如下：
</span>

```ts
@Component
export default class Example_Camera_FrameCaptured extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    private camera: Camera;
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取玩家角色
            let myCharacter = myPlayer.character;
            // 生成摄像机
            GameObject.asyncSpawn("Camera").then((obj)=>{
               this.camera = obj as Camera;
            })
            // 获取UI图片
            const image = this.uiWidgetBase.findChildByPath('RootCanvas/Image') as Image
            // 设置图片来源为生成的摄像机
            image.currentCamera = this.camera;
            // 添加一个按键方法：按下键盘“1”，开启每帧捕获
            InputUtil.onKeyDown(Keys.One, () => {
                myCamera.isFrameCaptured = true;
            });
            // 添加一个按键方法：按住键盘“2”，关闭每帧捕获
            InputUtil.onKeyPress(Keys.Two, () => {
                myCamera.isFrameCaptured = false;
            });
        }
    }
}
```
___

### maxLagDistance <Score text="maxLagDistance" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **maxLagDistance**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **maxLagDistance**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


位置最大延迟距离

::: warning Precautions

控制人物在位移时，摄像机与挂点的最大距离

:::


#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


位置最大延迟距离

::: warning Precautions

控制人物在位移时，摄像机与挂点的最大距离

:::

#### Parameters

| `value` `number` | 延迟最大距离 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 创建一个名为"Example_Camera_MaxLagDistance"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，开启位置延迟后设置最大位置延迟距离为200，你将在场景中看到摄像机位置延迟后摄像机最远只延迟200cm的效果。代码如下：
</span>

```ts
@Component
export default class Example_Camera_MaxLagDistance extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取玩家角色
            let myCharacter = myPlayer.character;
            // 获取当前摄像机
            let myCamera = Camera.currentCamera;
        }
    }
}
```
___

### positionLagEnabled <Score text="positionLagEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **positionLagEnabled**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **positionLagEnabled**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


启用位置延迟

::: warning Precautions

开启后在人物位移时，对摄像机跟随人物的运动进行延迟，关闭则没有延迟效果

:::


#### Returns

| `boolean` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


启用位置延迟

::: warning Precautions

开启后在人物位移时，对摄像机跟随人物的运动进行延迟，关闭则没有延迟效果

:::

#### Parameters

| `value` `boolean` | 是否开启 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 创建一个名为"Example_Camera_PositionLagEnabled"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中看到摄像机位置延迟的效果。代码如下：
</span>

```ts
@Component
export default class Example_Camera_PositionLagEnabled extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取玩家角色
            let myCharacter = myPlayer.character;
            // 获取当前摄像机
            let myCamera = Camera.currentCamera;
            // 开启摄像机位置延迟
            myCamera.positionLagEnabled = true;
            // 位置延迟恢复速度1
            myCamera.positionLagSpeed = 1;
            // 添加一个按键方法：按下键盘“1”，固定摄像机高度后跳跃
            InputUtil.onKeyDown(Keys.One, () => {
                myCamera.fixedElevation = true;
                myCharacter.jump();
                setTimeout(() => {
                    myCamera.fixedElevation = false;
                }, 1000);
            });
            // 添加一个按键方法：按住键盘“2”，增大摄像机FOV
            InputUtil.onKeyPress(Keys.Two, () => {
                myCamera.fov += 1;
            });
            // 添加一个按键方法：按住键盘“3”，减少摄像机FOV
            InputUtil.onKeyPress(Keys.Three, () => {
                myCamera.fov -= 1;
            });
        }
    }
}
```
___

### positionLagSpeed <Score text="positionLagSpeed" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **positionLagSpeed**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **positionLagSpeed**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


位置延迟速度

::: warning Precautions

控制人物在位移时，摄像机抵达目标位置的速度

:::


#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


设置摄像机位置延迟速度

::: warning Precautions

控制人物在位移时，摄像机抵达目标位置的速度

:::

#### Parameters

| `value` `number` | 延迟速度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 创建一个名为"Example_Camera_PositionLagSpeed"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，开启位置延迟后设置位置延迟恢复速度为1，你将在场景中看到摄像机位置延迟后摄像机缓慢恢复位置的效果。代码如下：
</span>

```ts
@Component
export default class Example_Camera_PositionLagSpeed extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取玩家角色
            let myCharacter = myPlayer.character;
            // 获取当前摄像机
            let myCamera = Camera.currentCamera;
            // 开启摄像机位置延迟
            myCamera.positionLagEnabled = true;
            // 位置延迟恢复速度1
            myCamera.positionLagSpeed = 1;
            // 添加一个按键方法：按下键盘“1”，固定摄像机高度后跳跃
            InputUtil.onKeyDown(Keys.One, () => {
                myCamera.fixedElevation = true;
                myCharacter.jump();
                setTimeout(() => {
                    myCamera.fixedElevation = false;
                }, 1000);
            });
            // 添加一个按键方法：按住键盘“2”，增大摄像机FOV
            InputUtil.onKeyPress(Keys.Two, () => {
                myCamera.fov += 1;
            });
            // 添加一个按键方法：按住键盘“3”，减少摄像机FOV
            InputUtil.onKeyPress(Keys.Three, () => {
                myCamera.fov -= 1;
            });
        }
    }
}
```
___

### positionMode <Score text="positionMode" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **positionMode**(): [`CameraPositionMode`](../enums/mw.CameraPositionMode.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **positionMode**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


位置模式

::: warning Precautions

摄像机的位置模式。固定模式:摄像机固定在某一位置，不可移动。跟随模式:摄像机跟随某个物体(默认是人物角色)一直移动。

:::


#### Returns

| [`CameraPositionMode`](../enums/mw.CameraPositionMode.md) |  |
| :------ | :------ |


</td>
<td style="text-align: left">


位置模式

::: warning Precautions

摄像机的位置模式。固定模式:摄像机固定在某一位置，不可移动。跟随模式:摄像机跟随某个物体(默认是人物角色)一直移动。

:::

#### Parameters

| `value` [`CameraPositionMode`](../enums/mw.CameraPositionMode.md) | 位置模式 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 创建一个名为"Example_Camera_PositionMode"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“2”，切换摄像机的位置模式。你将在场景中看到摄像机不同位置模式的效果并在控制台看到打印的摄像机当前位置模式。代码如下：
</span>

```ts
@Component
export default class Example_Camera_PositionMode extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 获取当前摄像机
            let myCamera = Camera.currentCamera;
            // 打印当前角色摄像机的位置模式和旋转模式
            console.log("当前角色摄像机的位置模式 " + CameraPositionMode[myCamera.positionMode]);
            console.log("当前角色摄像机的旋转模式 " + CameraRotationMode[myCamera.rotationMode]);
            let preset = 0;
            // 添加一个按键方法：按下键盘“1”，切换摄像机预设
            InputUtil.onKeyDown(Keys.One, () => {
                myCamera.preset = (preset + 1) % 6;
                console.log("当前角色相机预设 " + CameraPreset[preset]);
                preset++;
            });
            // 添加一个按键方法：按下键盘“2”，切换摄像机的位置模式
            InputUtil.onKeyDown(Keys.Two, () => {
                myCamera.positionMode = (myCamera.positionMode + 1) % 2;
                console.log("当前角色摄像机的位置模式 " + CameraPositionMode[myCamera.positionMode]);
            });
            // 添加一个按键方法：按下键盘“3”，切换摄像机的旋转模式
            InputUtil.onKeyDown(Keys.Three, () => {
                myCamera.rotationMode = (myCamera.rotationMode + 1) % 3;
                console.log("当前角色摄像机的旋转模式 " + CameraRotationMode[myCamera.rotationMode]);
            });
        }
    }
}
```
___

### preset <Score text="preset" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `set` **preset**(`value`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


设置摄像机预设

::: warning Precautions

摄像机提供预设视角模式。第一人称，第三人称，俯视角，默认，TPS过肩视角，FPS射击视角。

:::


#### Parameters

| `value` [`CameraPreset`](../enums/mw.CameraPreset.md) | 预设 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 创建一个名为"Camera_Preset"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“1”，切换摄像机预设。你将在场景中看到摄像机不同预设的效果。代码如下：
</span>

```ts
@Component
export default class Camera_Preset extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 获取当前摄像机
            let myCamera = Camera.currentCamera;
            // 打印当前角色摄像机的位置模式和旋转模式
            console.log("当前角色摄像机的位置模式 " + CameraPositionMode[myCamera.positionMode]);
            console.log("当前角色摄像机的旋转模式 " + CameraRotationMode[myCamera.rotationMode]);
            let preset = 0;
            // 添加一个按键方法：按下键盘“1”，切换摄像机预设
            InputUtil.onKeyDown(Keys.One, () => {
                myCamera.preset = (preset + 1) % 6;
                console.log("当前角色相机预设 " + CameraPreset[preset]);
                preset++;
            });
            // 添加一个按键方法：按下键盘“2”，切换摄像机的位置模式
            InputUtil.onKeyDown(Keys.Two, () => {
                myCamera.positionMode = (myCamera.positionMode + 1) % 2;
                console.log("当前角色摄像机的位置模式 " + CameraPositionMode[myCamera.positionMode]);
            });
            // 添加一个按键方法：按下键盘“3”，切换摄像机的旋转模式
            InputUtil.onKeyDown(Keys.Three, () => {
                myCamera.rotationMode = (myCamera.rotationMode + 1) % 3;
                console.log("当前角色摄像机的旋转模式 " + CameraRotationMode[myCamera.rotationMode]);
            });
        }
    }
}
```
___

### rotationLagEnabled <Score text="rotationLagEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **rotationLagEnabled**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **rotationLagEnabled**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


启用旋转延迟

::: warning Precautions

开启后在视角旋转时，对摄像机跟随人物的运动进行延迟，关闭则没有延迟效果

:::


#### Returns

| `boolean` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


启用旋转延迟

::: warning Precautions

开启后在视角旋转时，对摄像机跟随人物的运动进行延迟，关闭则没有延迟效果

:::

#### Parameters

| `value` `boolean` | 是否开启 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 创建一个名为"Example_Camera_RotationLagEnabled"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，开启摄像机旋转延迟，你将在场景中看到摄像机旋转时延迟的效果。代码如下：
</span>

```ts
@Component
export default class RotationLagEnabled extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取玩家角色
            let myCharacter = myPlayer.character;
            // 获取当前摄像机
            let myCamera = Camera.currentCamera;
            // 开启摄像机位置延迟
            myCamera.positionLagEnabled = true;
            // 位置延迟恢复速度1
            myCamera.positionLagSpeed = 1;
            // 最大位置延迟距离200
            myCamera.maxLagDistance = 200;
            // 开启摄像机旋转延迟
            myCamera.rotationLagEnabled = true;
            // 旋转延迟恢复速度2
            myCamera.rotationLagSpeed = 2;
            // 设置摄像机角度限制
            myCamera.upAngleLimit = 30
            myCamera.downAngleLimit = 10;
            // 添加一个按键方法：按下键盘“1”，固定摄像机高度后跳跃
            InputUtil.onKeyDown(Keys.One, () => {
                myCamera.fixedElevation = true;
                myCharacter.jump();
                setTimeout(() => {
                    myCamera.fixedElevation = false;
                }, 1000);
            });
            // 添加一个按键方法：按住键盘“2”，增大摄像机FOV
            InputUtil.onKeyPress(Keys.Two, () => {
                myCamera.fov += 1;
            });
            // 添加一个按键方法：按住键盘“3”，减少摄像机FOV
            InputUtil.onKeyPress(Keys.Three, () => {
                myCamera.fov -= 1;
            });
        }
    }
}
```
___

### rotationLagSpeed <Score text="rotationLagSpeed" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **rotationLagSpeed**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **rotationLagSpeed**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


旋转延迟速度

::: warning Precautions

控制视角在旋转时，摄像机抵达目标位置的角速度

:::


#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


旋转延迟速度

::: warning Precautions

控制视角在旋转时，摄像机抵达目标位置的角速度

:::

#### Parameters

| `value` `number` | 延迟速度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 创建一个名为"Example_Camera_RotationLagSpeed"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，开启摄像机旋转延迟，你将在场景中看到摄像机旋转时延迟的效果。代码如下：
</span>

```ts
@Component
export default class Example_Camera_RotationLagSpeed extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取玩家角色
            let myCharacter = myPlayer.character;
            // 获取当前摄像机
            let myCamera = Camera.currentCamera;
            // 开启摄像机位置延迟
            myCamera.positionLagEnabled = true;
            // 位置延迟恢复速度1
            myCamera.positionLagSpeed = 1;
            // 最大位置延迟距离200
            myCamera.maxLagDistance = 200;
            // 开启摄像机旋转延迟
            myCamera.rotationLagEnabled = true;
            // 旋转延迟恢复速度2
            myCamera.rotationLagSpeed = 2;
            // 设置摄像机角度限制
            myCamera.upAngleLimit = 30
            myCamera.downAngleLimit = 10;
            // 添加一个按键方法：按下键盘“1”，固定摄像机高度后跳跃
            InputUtil.onKeyDown(Keys.One, () => {
                myCamera.fixedElevation = true;
                myCharacter.jump();
                setTimeout(() => {
                    myCamera.fixedElevation = false;
                }, 1000);
            });
            // 添加一个按键方法：按住键盘“2”，增大摄像机FOV
            InputUtil.onKeyPress(Keys.Two, () => {
                myCamera.fov += 1;
            });
            // 添加一个按键方法：按住键盘“3”，减少摄像机FOV
            InputUtil.onKeyPress(Keys.Three, () => {
                myCamera.fov -= 1;
            });
        }
    }
}
```
___

### rotationMode <Score text="rotationMode" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **rotationMode**(): [`CameraRotationMode`](../enums/mw.CameraRotationMode.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **rotationMode**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


旋转模式

::: warning Precautions

摄像机旋转模式。固定朝向:摄像机固定朝向某一个方向。跟随朝向:摄像机跟随目标面朝方向。控制朝向:摄像机的朝向受到输入控制。

:::


#### Returns

| [`CameraRotationMode`](../enums/mw.CameraRotationMode.md) |  |
| :------ | :------ |


</td>
<td style="text-align: left">


旋转模式

::: warning Precautions

摄像机旋转模式。固定朝向:摄像机固定朝向某一个方向。跟随朝向:摄像机跟随目标面朝方向。控制朝向:摄像机的朝向受到输入控制。

:::

#### Parameters

| `value` [`CameraRotationMode`](../enums/mw.CameraRotationMode.md) | 旋转模式 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 创建一个名为"Example_Camera_RotationMode"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“3”，切换摄像机的旋转模式。你将在场景中看到摄像机不同旋转模式的效果并在控制台看到打印的摄像机当前旋转模式。代码如下：
</span>

```ts
@Component
export default class Example_Camera_RotationMode extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 获取当前摄像机
            let myCamera = Camera.currentCamera;
            // 打印当前角色摄像机的位置模式和旋转模式
            console.log("当前角色摄像机的位置模式 " + CameraPositionMode[myCamera.positionMode]);
            console.log("当前角色摄像机的旋转模式 " + CameraRotationMode[myCamera.rotationMode]);
            let preset = 0;
            // 添加一个按键方法：按下键盘“1”，切换摄像机预设
            InputUtil.onKeyDown(Keys.One, () => {
                myCamera.preset = (preset + 1) % 6;
                console.log("当前角色相机预设 " + CameraPreset[preset]);
                preset++;
            });
            // 添加一个按键方法：按下键盘“2”，切换摄像机的位置模式
            InputUtil.onKeyDown(Keys.Two, () => {
                myCamera.positionMode = (myCamera.positionMode + 1) % 2;
                console.log("当前角色摄像机的位置模式 " + CameraPositionMode[myCamera.positionMode]);
            });
            // 添加一个按键方法：按下键盘“3”，切换摄像机的旋转模式
            InputUtil.onKeyDown(Keys.Three, () => {
                myCamera.rotationMode = (myCamera.rotationMode + 1) % 3;
                console.log("当前角色摄像机的旋转模式 " + CameraRotationMode[myCamera.rotationMode]);
            });
        }
    }
}
```
___

### upAngleLimit <Score text="upAngleLimit" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **upAngleLimit**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `set` **upAngleLimit**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


向上角度限制

::: warning Precautions

摄像机向上旋转时的最大角度使用范围在0-90之间。

:::


#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


向上角度限制

::: warning Precautions

摄像机向上旋转时的最大角度使用范围在0-91之间。

:::

#### Parameters

| `value` `number` | 角度限制 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 创建一个名为"Example_Camera_UpAngleLimit"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，置摄像机角度限制，上抬最大角度为30，下旋最大角度为10。你将在场景中看到摄像机旋转受限的效果。代码如下：
</span>

```ts
@Component
export default class Example_Camera_UpAngleLimit extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取玩家角色
            let myCharacter = myPlayer.character;
            // 获取当前摄像机
            let myCamera = Camera.currentCamera;
            // 开启摄像机位置延迟
            myCamera.positionLagEnabled = true;
            // 位置延迟恢复速度1
            myCamera.positionLagSpeed = 1;
            // 最大位置延迟距离200
            myCamera.maxLagDistance = 200;
            // 开启摄像机旋转延迟
            myCamera.rotationLagEnabled = true;
            // 旋转延迟恢复速度2
            myCamera.rotationLagSpeed = 2;
            // 设置摄像机角度限制
            myCamera.upAngleLimit = 30
            myCamera.downAngleLimit = 10;
            // 添加一个按键方法：按下键盘“1”，固定摄像机高度后跳跃
            InputUtil.onKeyDown(Keys.One, () => {
                myCamera.fixedElevation = true;
                myCharacter.jump();
                setTimeout(() => {
                    myCamera.fixedElevation = false;
                }, 1000);
            });
            // 添加一个按键方法：按住键盘“2”，增大摄像机FOV
            InputUtil.onKeyPress(Keys.Two, () => {
                myCamera.fov += 1;
            });
            // 添加一个按键方法：按住键盘“3”，减少摄像机FOV
            InputUtil.onKeyPress(Keys.Three, () => {
                myCamera.fov -= 1;
            });
        }
    }
}
```
___

### currentCamera <Score text="currentCamera" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **currentCamera**(): [`Camera`](mw.Camera.md) <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


当前摄像机

::: warning Precautions

当前正在使用的摄像机

:::


#### Returns

</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"CurrentCamera"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，在场景中随机创建5个摄像机。按下键盘“1”，切换摄像机。按下键盘“2”，切换回默认摄像机。你将在场景中看到摄像机切换时的效果。代码如下：
</span>

```ts
@Component
export default class CurrentCamera extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前摄像机
            let myCamera = Camera.currentCamera;
            let curCameraIndex = -1;
            // 在场景中随机创建5个摄像机
            let cameraArray = new Array<Camera>();
            for (let i = 0;
i < 5;
i++) {
                let camera = GameObject.spawn<Camera>("Camera") as Camera;
                camera.worldTransform.position = new Vector(MathUtil.randomInt(-1000, 1000), MathUtil.randomInt(-1000, 1000),MathUtil.randomInt(0, 1000));
                camera.worldTransform.rotation = new Rotation(MathUtil.randomInt(-90, 90), MathUtil.randomInt(-30, 30),MathUtil.randomInt(-150, 150));
                cameraArray.push(camera);
                camera.onSwitchComplete.add(() => {
                    console.log("当前摄像机序号 " + i);
                    curCameraIndex = i;
                });
            }
            // 添加一个按键方法：按下键盘“1”，切换摄像机
            InputUtil.onKeyDown(Keys.One, () => {
                console.log("Switch Camera");
                let newCamera = (curCameraIndex + 1) % 5;
                Camera.switch(cameraArray[newCamera], 5, CameraSwitchBlendFunction.Linear);
            });
            // 添加一个按键方法：按下键盘“2”，切换回默认摄像机
            InputUtil.onKeyDown(Keys.Two, () => {
                console.log("Switch Default Camera");
                Camera.switch(myCamera);
            });
        }
    }
}
```
| [`Camera`](mw.Camera.md) |  |
| :------ | :------ |

## Methods

___

### lock <Score text="lock" /> 

• **lock**(`target`, `val?`): `void` <Badge type="tip" text="client" />

相机锁定目标

#### Parameters

| `target` [`GameObject`](mw.GameObject.md) | 目标物体 |
| :------ | :------ |
| `val?` `Object` | lockInterval,lockSpeed,lockRange,lockDistance,lockOffset,bPause参数集合 default:null |
| `val.bPause?` `boolean` | - |
| `val.lockDistance?` `number` | - |
| `val.lockInterval?` `number` | - |
| `val.lockOffset?` [`Vector`](mw.Vector.md) | - |
| `val.lockRange?` `number` | - |
| `val.lockRotationY?` `boolean` | - |
| `val.lockRotationZ?` `boolean` | - |
| `val.lockSpeed?` `number` | - |


::: warning Precautions

当前摄像机按照参数设置锁定目标对象。

:::

<span style="font-size: 14px;">
使用示例:创建一个名为"Example_Camera_Lock"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，创建一个敌方角色作为锁定目标。敌方角色会持续追踪玩家角色。按下键盘“1”，锁定敌方角色。按下键盘“2”，手动取消锁定：当bPause参数true时，需要手动取消锁定才能结束锁定流程。按下键盘“3”，角色摄像机朝向目标（无追踪效果）。你将在场景中看到锁定切换时的效果。代码如下：
</span>

```ts
@Component
export default class Example_Camera_Lock extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家角色
            let myCharacter = myPlayer.character;
            // 创建一个敌方角色作为锁定目标
            let enemy = Player.spawnDefaultCharacter();
            enemy.switchToFlying()
            enemy.worldTransform.position = new Vector(1000, 500, 130);
            // 敌方角色追踪玩家角色
            TimeUtil.setInterval(() => {
                let distance = Vector.subtract(myCharacter.worldTransform.position, enemy.worldTransform.position);
                if(distance.length < 200) {
                    enemy.addMovement(new Vector(0, 0, 5));
                } else {
                    let dir = distance.normalized;
                    enemy.addMovement(dir);
                    enemy.worldTransform.rotation = distance.toRotation();
                }
            }, 0.02)
            // 添加一个按键方法：按下键盘“1”，锁定敌方角色
            InputUtil.onKeyDown(Keys.One, () => {
                console.error("Start Lock");
                let myCamera = Camera.currentCamera;
                myCamera.lock(enemy, {lockInterval:0, lockSpeed: 0, lockRange: 500, lockDistance: 5000, lockOffset: new Vector(0, 0, 80), bPause: true});
            });
            // 添加一个按键方法：按下键盘“2”，手动取消锁定：当bPause参数true时，需要手动取消锁定才能结束锁定流程
            InputUtil.onKeyDown(Keys.Two, () => {
                let myCamera = Camera.currentCamera;
                myCamera.unlock();
            });
            // 添加一个按键方法：按下键盘“3”，角色看向目标（无追踪效果）
            InputUtil.onKeyDown(Keys.Three, () => {
                let myCamera = Camera.currentCamera;
                myCamera.lookAt(enemy);
            });
        }
    }
}
```

___

### lookAt <Score text="lookAt" /> 

• **lookAt**(`target`): `void` <Badge type="tip" text="client" />

摄像机朝向目标

#### Parameters

| `target` [`GameObject`](mw.GameObject.md)  [`Vector`](mw.Vector.md) | 目标 |
| :------ | :------ |


<span style="font-size: 14px;">
使用示例:创建一个名为"Example_Camera_LookAt"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，创建一个敌方角色作为锁定目标。敌方角色会持续追踪玩家角色。按下键盘“1”，锁定敌方角色。按下键盘“2”，手动取消锁定：当bPause参数true时，需要手动取消锁定才能结束锁定流程。按下键盘“3”，角色摄像机朝向目标（无追踪效果）。你将在场景中看到锁定切换时的效果。代码如下：
</span>

```ts
@Component
export default class Example_Camera_LookAt extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家角色
            let myCharacter = myPlayer.character;
            // 创建一个敌方角色作为锁定目标
            let enemy = Player.spawnDefaultCharacter();
            enemy.switchToFlying()
            enemy.worldTransform.position = new Vector(1000, 500, 130);
            // 敌方角色追踪玩家角色
            TimeUtil.setInterval(() => {
                let distance = Vector.subtract(myCharacter.worldTransform.position, enemy.worldTransform.position);
                if(distance.length < 200) {
                    enemy.addMovement(new Vector(0, 0, 5));
                } else {
                    let dir = distance.normalized;
                    enemy.addMovement(dir);
                    enemy.worldTransform.rotation = distance.toRotation();
                }
            }, 0.02)
            // 添加一个按键方法：按下键盘“1”，锁定敌方角色
            InputUtil.onKeyDown(Keys.One, () => {
                console.error("Start Lock");
                let myCamera = Camera.currentCamera;
                myCamera.lock(enemy, {lockInterval:0, lockSpeed: 0, lockRange: 500, lockDistance: 5000, lockOffset: new Vector(0, 0, 80), bPause: true});
            });
            // 添加一个按键方法：按下键盘“2”，手动取消锁定：当bPause参数true时，需要手动取消锁定才能结束锁定流程
            InputUtil.onKeyDown(Keys.Two, () => {
                let myCamera = Camera.currentCamera;
                myCamera.unlock();
            });
            // 添加一个按键方法：按下键盘“3”，角色看向目标（无追踪效果）
            InputUtil.onKeyDown(Keys.Three, () => {
                let myCamera = Camera.currentCamera;
                myCamera.lookAt(enemy);
            });
        }
    }
}
```

___

### unlock <Score text="unlock" /> 

• **unlock**(): `void` <Badge type="tip" text="client" />

取消锁定目标


<span style="font-size: 14px;">
使用示例:创建一个名为"Example_Camera_Unlock"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，创建一个敌方角色作为锁定目标。敌方角色会持续追踪玩家角色。按下键盘“1”，锁定敌方角色。按下键盘“2”，手动取消锁定：当bPause参数true时，需要手动取消锁定才能结束锁定流程。按下键盘“3”，角色摄像机朝向目标（无追踪效果）。你将在场景中看到锁定切换时的效果。代码如下：
</span>

```ts
@Component
export default class Example_Camera_Unlock extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家角色
            let myCharacter = myPlayer.character;
            // 创建一个敌方角色作为锁定目标
            let enemy = Player.spawnDefaultCharacter();
            enemy.switchToFlying()
            enemy.worldTransform.position = new Vector(1000, 500, 130);
            // 敌方角色追踪玩家角色
            TimeUtil.setInterval(() => {
                let distance = Vector.subtract(myCharacter.worldTransform.position, enemy.worldTransform.position);
                if(distance.length < 200) {
                    enemy.addMovement(new Vector(0, 0, 5));
                } else {
                    let dir = distance.normalized;
                    enemy.addMovement(dir);
                    enemy.worldTransform.rotation = distance.toRotation();
                }
            }, 0.02)
            // 添加一个按键方法：按下键盘“1”，锁定敌方角色
            InputUtil.onKeyDown(Keys.One, () => {
                console.error("Start Lock");
                let myCamera = Camera.currentCamera;
                myCamera.lock(enemy, {lockInterval:0, lockSpeed: 0, lockRange: 500, lockDistance: 5000, lockOffset: new Vector(0, 0, 80), bPause: true});
            });
            // 添加一个按键方法：按下键盘“2”，手动取消锁定：当bPause参数true时，需要手动取消锁定才能结束锁定流程
            InputUtil.onKeyDown(Keys.Two, () => {
                let myCamera = Camera.currentCamera;
                myCamera.unlock();
            });
            // 添加一个按键方法：按下键盘“3”，角色看向目标（无追踪效果）
            InputUtil.onKeyDown(Keys.Three, () => {
                let myCamera = Camera.currentCamera;
                myCamera.lookAt(enemy);
            });
        }
    }
}
```

___

### shake <Score text="shake" /> 

• `Static` **shake**(`shakeInfo`, `duration?`): `void` <Badge type="tip" text="client" />

开始摄像机抖动

#### Parameters

| `shakeInfo` [`CameraShakeInfo`](../interfaces/mw.CameraShakeInfo.md) |  抖动信息 |
| :------ | :------ |
| `duration?` `number` |  持续时间(秒) default: 1 range: 不做限制 type: 浮点数 |


<span style="font-size: 14px;">
使用示例:创建一个名为"Example_Camera_Shake"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“1”，抖动相机5秒。按下键盘“2”，停止相机抖动。你将在场景中看到摄像机镜头抖动时的效果。代码如下：
</span>

```ts
@Component
export default class Example_Camera_Shake extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 添加一个按键方法:按下键盘“1”，抖动相机5秒
            InputUtil.onKeyDown(Keys.One, () => {
                console.log("Start Shake ");
                Camera.shake({positionYAmplitude: 1, positionYFrequency: 0.5, positionZAmplitude: 1, positionZFrequency: 1}, 5);
            });
            // 添加一个按键方法:按下键盘“2”，停止相机抖动
            InputUtil.onKeyUp(Keys.Two, () => {
                console.log("Stop Shake ");
                Camera.stopShake();
            });
        }
    }
}
```

___

### stopShake <Score text="stopShake" /> 

• `Static` **stopShake**(): `void` <Badge type="tip" text="client" />

停止摄像机抖动


<span style="font-size: 14px;">
使用示例:创建一个名为"Example_Camera_StopShake"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“1”，抖动相机5秒。按下键盘“2”，停止相机抖动。你将在场景中看到摄像机镜头抖动时的效果。代码如下：
</span>

```ts
@Component
export default class Example_Camera_StopShake extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 添加一个按键方法:按下键盘“1”，抖动相机5秒
            InputUtil.onKeyDown(Keys.One, () => {
                console.log("Start Shake ");
                Camera.shake({positionYAmplitude: 1, positionYFrequency: 0.5, positionZAmplitude: 1, positionZFrequency: 1}, 5);
            });
            // 添加一个按键方法:按下键盘“2”，停止相机抖动
            InputUtil.onKeyUp(Keys.Two, () => {
                console.log("Stop Shake ");
                Camera.stopShake();
            });
        }
    }
}
```

___

### switch <Score text="switch" /> 

• `Static` **switch**(`newCamera`, `blendTime?`, `blendFunc?`, `blendExp?`): [`Camera`](mw.Camera.md) <Badge type="tip" text="client" />

切换摄像机

#### Parameters

| `newCamera` [`Camera`](mw.Camera.md) |  想要切换的目标摄像机对象，当传入的参数类型为 Transform 时会使用该 Transform 的位置跟旋转生成一个 Camera 再进行切换。 |
| :------ | :------ |
| `blendTime?` `number` |  混合时间(秒) default: 0 range: 不做限制 type: 浮点数 |
| `blendFunc?` [`CameraSwitchBlendFunction`](../enums/mw.CameraSwitchBlendFunction.md) |  切换时用到的混合函数 default: Linear |
| `blendExp?` `number` |  混合额外变量，用于控制混合时的快慢程度，具体作用看枚举 SwitchCameraBlendFunction default: 0 range: 不做限制 type: 浮点数 |

#### Returns

| [`Camera`](mw.Camera.md) | 目标camera对象 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为"Example_Camera_Switch"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，在场景中随机创建5个摄像机。按下键盘“1”，切换摄像机。按下键盘“2”，切换回默认摄像机。你将在场景中看到摄像机切换时的效果。代码如下：
</span>

```ts
@Component
export default class Example_Camera_Switch extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前摄像机
            let myCamera = Camera.currentCamera;
            let curCameraIndex = -1;
            // 在场景中随机创建5个摄像机
            let cameraArray = new Array<Camera>();
            for (let i = 0;
i < 5;
i++) {
                let camera = GameObject.spawn<Camera>("Camera") as Camera;
                camera.worldTransform.position = new Vector(MathUtil.randomInt(-1000, 1000), MathUtil.randomInt(-1000, 1000),MathUtil.randomInt(0, 1000));
                camera.worldTransform.rotation = new Rotation(MathUtil.randomInt(-90, 90), MathUtil.randomInt(-30, 30),MathUtil.randomInt(-150, 150));
                cameraArray.push(camera);
                camera.onSwitchComplete.add(() => {
                    console.log("当前摄像机序号 " + i);
                    curCameraIndex = i;
                });
            }
            // 添加一个按键方法：按下键盘“1”，切换摄像机
            InputUtil.onKeyDown(Keys.One, () => {
                console.log("Switch Camera");
                let newCamera = (curCameraIndex + 1) % 5;
                Camera.switch(cameraArray[newCamera], 5, CameraSwitchBlendFunction.Linear);
            });
            // 添加一个按键方法：按下键盘“2”，切换回默认摄像机
            InputUtil.onKeyDown(Keys.Two, () => {
                console.log("Switch Default Camera");
                Camera.switch(myCamera);
            });
        }
    }
}
```
