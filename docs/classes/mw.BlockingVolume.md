[玩法](../groups/玩法.玩法.md) / BlockingVolume

# BlockingVolume <Badge type="tip" text="Class" /> <Score text="BlockingVolume" />

禁行区

用于控制角色是否可以进出此区域。

::: warning Precautions

该对象各端生成，通行许可由服务器同步到客户端

:::

<span style="font-size: 14px;">
使用示例:创建一个名为"BlockingVolExample"的脚本，放置在对象栏中，打开脚本，输入以下代码，替换GUID保存，运行游戏，你将可以通过该GUID对应的禁行区。代码如下：
</span>

```ts
@Component
export default class BlockingVolExample extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected async onStart(): Promise<void> {
        // 获取当前玩家
        let player = await mw.Player.asyncGetLocalPlayer();
        // GUID根据实际情况填写，可在编辑器对象管理器内右键复制对象ID
        let blockingVolume = await GameObject.asyncFindGameObjectById(`GUID`) as BlockingVolume;
        if(SystemUtil.isClient())
        {
            mw.InputUtil.onKeyDown(Keys.F1,()=>{
                // F1键 通知服务器执行事件 参数传入当前玩家
                mw.Event.dispatchToServer(`AddPlayerPassable`,player);
            })
        }
        if(SystemUtil.isServer()){
            // 侦听客户端通知
            mw.Event.addClientListener(`AddPlayerPassable`,(player : Player)=>{
            // 玩家角色添加通行许可
            blockingVolume.addPassableTarget(player.character);
            })
        }
    }
}
```

## Hierarchy

- [`GameObject`](mw.GameObject.md)

  ↳ **`BlockingVolume`**

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
| **[addPassableTarget](mw.BlockingVolume.md#addpassabletarget)**(`target`: [`GameObject`](mw.GameObject.md)): `void` <Badge type="tip" text="other" />  |
| :-----|
| 为目标添加通过该区域的权限|
| **[clear](mw.BlockingVolume.md#clear)**(): `void` <Badge type="tip" text="other" />  |
| 重置禁行区|
| **[getTargetPassable](mw.BlockingVolume.md#gettargetpassable)**(`target`: [`GameObject`](mw.GameObject.md)): `boolean`   |
| 获得目标通过该区域的权限|
| **[removePassableTarget](mw.BlockingVolume.md#removepassabletarget)**(`target`: [`GameObject`](mw.GameObject.md)): `void` <Badge type="tip" text="other" />  |
| 移除目标通过该区域的权限|
| **[unblockAll](mw.BlockingVolume.md#unblockall)**(): `void` <Badge type="tip" text="other" />  |
| 开放禁行区|


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

## Methods

___

### addPassableTarget <Score text="addPassableTarget" /> 

• **addPassableTarget**(`target`): `void` <Badge type="tip" text="other" />

为目标添加通过该区域的权限

#### Parameters

| `target` [`GameObject`](mw.GameObject.md) | GameObject |
| :------ | :------ |


<span style="font-size: 14px;">
使用示例: 针对此禁行区为其他GameObject添加通行许可
</span>

```ts
 // 获取当前玩家
 let player =  Player.localPlayer;
 // GUID根据实际情况填写，可在编辑器对象管理器内右键复制对象ID
 let blockingVolume = await GameObject.asyncFindGameObjectById(`GUID`) as BlockingVolume;
 if(SystemUtil.isClient())
 {
     InputUtil.onKeyDown(Keys.F1,()=>{
         // F1键 通知服务器执行事件 参数传入当前玩家
         mw.Event.dispatchToServer(`AddPlayerPassable`,player);
     })
 }
 if(SystemUtil.isServer()){
     // 侦听客户端通知
     mw.Event.addClientListener(`AddPlayerPassable`,(player : Player)=>{
     // 玩家角色添加通行许可
     blockingVolume.addPassableTarget(player.character);
     })
 }
```

___

### clear <Score text="clear" /> 

• **clear**(): `void` <Badge type="tip" text="other" />

重置禁行区


<span style="font-size: 14px;">
使用示例: 重置该禁行区发布的所有通行许可
</span>

```ts
  // GUID根据实际情况填写，可在编辑器对象管理器内右键复制对象ID
 let blockingVolume = await GameObject.asyncFindGameObjectById(`GUID`) as BlockingVolume;
 if(SystemUtil.isClient())
 {
     InputUtil.onKeyDown(Keys.F4,()=>{
         // F4键 通知服务器执行事件
         mw.Event.dispatchToServer(`Clear`);
     })
 }
 if(SystemUtil.isServer()){
     // 侦听客户端通知
     mw.Event.addClientListener(`Clear`,()=>{
     // 重置该禁行区通行许可
     blockingVolume.clear();
     })
 }
```

___

### getTargetPassable <Score text="getTargetPassable" /> 

• **getTargetPassable**(`target`): `boolean` 

获得目标通过该区域的权限

#### Parameters

| `target` [`GameObject`](mw.GameObject.md) | GameObject |
| :------ | :------ |

#### Returns

| `boolean` | bool |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例: 获取此禁行区对某GameObject的通行许可
</span>

```ts
 // 获取当前玩家
 let player = Player.localPlayer;
 // GUID根据实际情况填写，可在编辑器对象管理器内右键复制对象ID
 let blockingVolume = await GameObject.asyncFindGameObjectById(`GUID`) as BlockingVolume;
 InputUtil.onKeyDown(Keys.F3,()=>{
     // F3键 获取玩家角色的通行权限
     blockingVolume.getTargetPassable(player.character);
 })
```

___

### removePassableTarget <Score text="removePassableTarget" /> 

• **removePassableTarget**(`target`): `void` <Badge type="tip" text="other" />

移除目标通过该区域的权限

#### Parameters

| `target` [`GameObject`](mw.GameObject.md) | GameObject |
| :------ | :------ |


<span style="font-size: 14px;">
使用示例: 针对此禁行区为其他GameObject移除通行许可
</span>

```ts
 // 获取当前玩家
 let player =  Player.localPlayer;
 // GUID根据实际情况填写，可在编辑器对象管理器内右键复制对象ID
 let blockingVolume = await GameObject.asyncFindGameObjectById(`GUID`) as BlockingVolume;
 if(SystemUtil.isClient())
 {
     InputUtil.onKeyDown(Keys.F2,()=>{
         // F2键 通知服务器执行事件 参数传入当前玩家
         mw.Event.dispatchToServer(`RemovePlayerPassable`,player);
     })
 }
 if(SystemUtil.isServer()){
     // 侦听客户端通知
     mw.Event.addClientListener(`RemovePlayerPassable`,(player : Player)=>{
     // 玩家角色移除通行许可
     blockingVolume.removePassableTarget(player.character);
     })
 }
```

___

### unblockAll <Score text="unblockAll" /> 

• **unblockAll**(): `void` <Badge type="tip" text="other" />

开放禁行区


<span style="font-size: 14px;">
使用示例: 开放该禁行区
</span>

```ts
 // GUID根据实际情况填写，可在编辑器对象管理器内右键复制对象ID
 let blockingVolume = await GameObject.asyncSpawn<BlockingVolume>(`BlockingVolume`);
 if(SystemUtil.isClient())
 {
     InputUtil.onKeyDown(Keys.F5,()=>{
         // F5键 通知服务器执行事件
         mw.Event.dispatchToServer(`UnblockAll`);
     })
 }
 if(SystemUtil.isServer()){
     // 侦听客户端通知
     mw.Event.addClientListener(`UnblockAll`,()=>{
     // 该禁行区开放通行
     blockingVolume.unblockAll();
     })
 }
```
