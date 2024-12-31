[玩法](../groups/玩法.玩法.md) / PhysicsService

# PhysicsService <Badge type="tip" text="Class" /> <Score text="PhysicsService" />

碰撞组

## Table of contents

### Accessors <Score text="Accessors" /> 
| **[touchesUseCollisionGroups](mw.PhysicsService.md#touchesusecollisiongroups)**(): `boolean`   |
| :-----|
| 确定不同组中设置为不碰撞的模型是否在忽略碰撞的同时忽略touch事件|

### Methods <Score text="Methods" /> 
| **[addCollisionGroup](mw.PhysicsService.md#addcollisiongroup)**(`name`: `string`): `void`   |
| :-----|
| 添加新碰撞组|
| **[boxOverlap](mw.PhysicsService.md#boxoverlap)**(`boxPos`: [`Vector`](mw.Vector.md), `boxExtent`: [`Vector`](mw.Vector.md), `collisionParams`: [`CollisionQueryParams`](../interfaces/mw.CollisionQueryParams.md), `renderParams`: [`RenderQueryParams`](../interfaces/mw.RenderQueryParams.md)): [`GameObject`](mw.GameObject.md)[]   |
| 返回一个与给定盒体重叠的对象数组|
| **[boxTraceMulti](mw.PhysicsService.md#boxtracemulti)**(`start`: [`Vector`](mw.Vector.md), `end`: [`Vector`](mw.Vector.md), `halfSize`: [`Vector`](mw.Vector.md), `orientation`: [`Rotation`](mw.Rotation.md), `collisionParams`: [`CollisionQueryParams`](../interfaces/mw.CollisionQueryParams.md), `renderParams`: [`RenderQueryParams`](../interfaces/mw.RenderQueryParams.md)): [`HitResult`](mw.HitResult.md)[]   |
| 盒体沿着给定的路径扫过一个空间，直到首次在起点盒体空间之外遇到阻挡命中时结束（盒体在起点时重叠的阻挡对象不包含在首次判定中），返回沿途遇到的所有命中。|
| **[boxTraceSingle](mw.PhysicsService.md#boxtracesingle)**(`start`: [`Vector`](mw.Vector.md), `end`: [`Vector`](mw.Vector.md), `halfSize`: [`Vector`](mw.Vector.md), `orientation`: [`Rotation`](mw.Rotation.md), `collisionParams`: [`CollisionQueryParams`](../interfaces/mw.CollisionQueryParams.md), `renderParams`: [`RenderQueryParams`](../interfaces/mw.RenderQueryParams.md)): [`HitResult`](mw.HitResult.md)   |
| 盒体沿着给定的路径扫过一个空间，并返回遇到的第一个阻挡命中。|
| **[capsuleOverlap](mw.PhysicsService.md#capsuleoverlap)**(`capsulePos`: [`Vector`](mw.Vector.md), `radius`: `number`, `halfHeight`: `number`, `collisionParams`: [`CollisionQueryParams`](../interfaces/mw.CollisionQueryParams.md), `renderParams`: [`RenderQueryParams`](../interfaces/mw.RenderQueryParams.md)): [`GameObject`](mw.GameObject.md)[]   |
| 返回一个与给定胶囊体重叠的对象数组|
| **[capsuleTraceMulti](mw.PhysicsService.md#capsuletracemulti)**(`start`: [`Vector`](mw.Vector.md), `end`: [`Vector`](mw.Vector.md), `radius`: `number`, `halfHeight`: `number`, `collisionParams`: [`CollisionQueryParams`](../interfaces/mw.CollisionQueryParams.md), `renderParams`: [`RenderQueryParams`](../interfaces/mw.RenderQueryParams.md)): [`HitResult`](mw.HitResult.md)[]   |
| 胶囊体沿着给定的路径扫过一个空间，直到首次在起点胶囊体空间之外遇到阻挡命中时结束（胶囊体在起点时重叠的阻挡对象不包含在首次判定中），返回沿途遇到的所有命中。|
| **[capsuleTraceSingle](mw.PhysicsService.md#capsuletracesingle)**(`start`: [`Vector`](mw.Vector.md), `end`: [`Vector`](mw.Vector.md), `radius`: `number`, `halfHeight`: `number`, `collisionParams`: [`CollisionQueryParams`](../interfaces/mw.CollisionQueryParams.md), `renderParams`: [`RenderQueryParams`](../interfaces/mw.RenderQueryParams.md)): [`HitResult`](mw.HitResult.md)   |
| 胶囊体沿着给定的路径扫过一个空间，并返回遇到的第一个阻挡命中。|
| **[deleteCollisionGroup](mw.PhysicsService.md#deletecollisiongroup)**(`name`: `string`): `void`   |
| 删除已有碰撞组|
| **[getAvailableCollisionGroupsCount](mw.PhysicsService.md#getavailablecollisiongroupscount)**(): `number`   |
| 获取当前可剩余使用碰撞组数量|
| **[getCollisionBetweenGroups](mw.PhysicsService.md#getcollisionbetweengroups)**(`group1`: `string`, `group2`: `string`): `boolean`   |
| 获取两碰撞组之间的碰撞关系(是否可发生碰撞)|
| **[getValidCollisionGroups](mw.PhysicsService.md#getvalidcollisiongroups)**(): `string`[]   |
| 获取当前已添加的碰撞组名列表|
| **[isCollisionGroupValid](mw.PhysicsService.md#iscollisiongroupvalid)**(`name`: `string`): `boolean`   |
| 检测碰撞组是否有效(已添加过)|
| **[lineTraceMulti](mw.PhysicsService.md#linetracemulti)**(`start`: [`Vector`](mw.Vector.md), `end`: [`Vector`](mw.Vector.md), `collisionParams`: [`CollisionQueryParams`](../interfaces/mw.CollisionQueryParams.md), `renderParams`: [`RenderQueryParams`](../interfaces/mw.RenderQueryParams.md)): [`HitResult`](mw.HitResult.md)[]   |
| 沿着给定的路径进行射线追踪，直到首次遇到阻挡命中时结束，返回沿途遇到的所有命中。|
| **[lineTraceSingle](mw.PhysicsService.md#linetracesingle)**(`start`: [`Vector`](mw.Vector.md), `end`: [`Vector`](mw.Vector.md), `collisionParams`: [`CollisionQueryParams`](../interfaces/mw.CollisionQueryParams.md), `renderParams`: [`RenderQueryParams`](../interfaces/mw.RenderQueryParams.md)): [`HitResult`](mw.HitResult.md)   |
| 沿着给定的路径进行射线追踪，并返回遇到的第一个阻挡命中。|
| **[renameCollisionGroup](mw.PhysicsService.md#renamecollisiongroup)**(`previousName`: `string`, `newName`: `string`): `void`   |
| 重命名碰撞组|
| **[setCollisionBetweenGroups](mw.PhysicsService.md#setcollisionbetweengroups)**(`group1`: `string`, `group2`: `string`, `collidable`: `boolean`): `void`   |
| 设置俩碰撞组之间的碰撞关系(是否可发生碰撞)|
| **[sphereOverlap](mw.PhysicsService.md#sphereoverlap)**(`spherePos`: [`Vector`](mw.Vector.md), `sphereRadius`: `number`, `collisionParams`: [`CollisionQueryParams`](../interfaces/mw.CollisionQueryParams.md), `renderParams`: [`RenderQueryParams`](../interfaces/mw.RenderQueryParams.md)): [`GameObject`](mw.GameObject.md)[]   |
| 返回一个与给定球体重叠的对象数组|
| **[sphereTraceMulti](mw.PhysicsService.md#spheretracemulti)**(`start`: [`Vector`](mw.Vector.md), `end`: [`Vector`](mw.Vector.md), `radius`: `number`, `collisionParams`: [`CollisionQueryParams`](../interfaces/mw.CollisionQueryParams.md), `renderParams`: [`RenderQueryParams`](../interfaces/mw.RenderQueryParams.md)): [`HitResult`](mw.HitResult.md)[]   |
| 球体沿着给定的路径扫过一个空间，直到首次在起点球体空间之外遇到阻挡命中时结束（球体在起点时重叠的阻挡对象不包含在首次判定中），返回沿途遇到的所有命中。|
| **[sphereTraceSingle](mw.PhysicsService.md#spheretracesingle)**(`start`: [`Vector`](mw.Vector.md), `end`: [`Vector`](mw.Vector.md), `radius`: `number`, `collisionParams`: [`CollisionQueryParams`](../interfaces/mw.CollisionQueryParams.md), `renderParams`: [`RenderQueryParams`](../interfaces/mw.RenderQueryParams.md)): [`HitResult`](mw.HitResult.md)   |
| 球体沿着给定的路径扫过一个空间，并返回遇到的第一个阻挡命中。|

## Accessors

### touchesUseCollisionGroups <Score text="touchesUseCollisionGroups" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **touchesUseCollisionGroups**(): `boolean` 

</th>
<th style="text-align: left">

• `Static` `set` **touchesUseCollisionGroups**(`status`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


确定不同组中设置为不碰撞的模型是否在忽略碰撞的同时忽略touch事件

#### Returns

| `boolean` | 不同组中设置为不碰撞的模型是否在忽略碰撞的同时忽略touch事件 |
| :------ | :------ |


</td>
<td style="text-align: left">


确定不同组中设置为不碰撞的模型是否在忽略碰撞的同时忽略touch事件


#### Parameters

| `status` `boolean` | 不同组中设置为不碰撞的模型是否在忽略碰撞的同时忽略touch事件 range: 不限制 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:
</span>

在场景中创建一个名为TouchesUseCollisionGroups的脚本，并拖入场景中，并复制以下代码进入脚本。
依次按下1、2之后，会发现服务器会小球会调用onTouch函数并输出对应LOG。
```ts
@Component
export default class TouchesUseCollisionGroups extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        PhysicsService.touchesUseCollisionGroups = true;
        PhysicsService.addCollisionGroup("GroupA");
        PhysicsService.addCollisionGroup("GroupB");
        PhysicsService.setCollisionBetweenGroups("GroupA", "GroupB", false);

        // 创建正常碰撞的球体A并设置碰撞组为GroupA
        InputUtil.onKeyDown(Keys.One, ()=>{
            this.serverCreateBall(new Vector(300, 0, 0), "GroupA", false);
        })

        // 创建模拟物理的球体B并设置碰撞组为GroupB
        InputUtil.onKeyDown(Keys.Two, ()=>{
            this.serverCreateBall(new Vector(300, 0, 100), "GroupB", true);
        })
    }

    @mw.RemoteFunction(mw.Server)
    serverCreateBall(pos:Vector, Group:string, bPhysicsSimulate:boolean)
    {
        GameObject.asyncSpawn("197388", {replicates:true}).then((obj)=>{
            let ball  = obj as mw.Model;
            ball.worldTransform.position = pos;
            if (bPhysicsSimulate)
            {
                ball.physicsEnabled = true;
                ball.massEnabled = true;
                ball.mass = 50;
            }
            ball.collisionGroup = Group;
            ball.onTouch.add((obj : GameObject) => {
                console.log(`${obj.gameObjectId} - Touch - ${ball.gameObjectId}`);
            }
        );
        })
    }
}
```


## Methods

### addCollisionGroup <Score text="addCollisionGroup" /> 

• `Static` **addCollisionGroup**(`name`): `void` 

添加新碰撞组

#### Parameters

| `name` `string` | 碰撞组名 range: 不限制 |
| :------ | :------ |


<span style="font-size: 14px;">
使用示例:在场景中创建一个名为 CollisionGroup 的脚本，并拖入场景中，并复制以下代码进入脚本。按下 1 后可在编辑器窗口客户端内看到输出 "GroupA,GroupB,GroupC"
</span>

```ts
@Component
export default class CollisionGroup extends Script {

    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        PhysicsService.addCollisionGroup("GroupA");
        PhysicsService.addCollisionGroup("GroupB");
        PhysicsService.setCollisionBetweenGroups("GroupA", "GroupB", false);

        // 创建模拟物理的球体A并设置碰撞组为GroupA
        InputUtil.onKeyDown(Keys.One, ()=>{
            PhysicsService.addCollisionGroup("GroupC");
            console.log(PhysicsService.getValidCollisionGroups());
        })
    }
}
```

___

### boxOverlap <Score text="boxOverlap" /> 

• `Static` **boxOverlap**(`boxPos`, `boxExtent`, `collisionParams`, `renderParams`): [`GameObject`](mw.GameObject.md)[] 

返回一个与给定盒体重叠的对象数组

#### Parameters

| `boxPos` [`Vector`](mw.Vector.md) | 检测位置 |
| :------ | :------ |
| `boxExtent` [`Vector`](mw.Vector.md) | 盒体大小 |
| `collisionParams` [`CollisionQueryParams`](../interfaces/mw.CollisionQueryParams.md) | 碰撞查询渲染参数 |
| `renderParams` [`RenderQueryParams`](../interfaces/mw.RenderQueryParams.md) | 空间查询渲染参数 |

#### Returns

| [`GameObject`](mw.GameObject.md)[] | GameObject数组 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例: 如下示例展示使用矩形范围检测的基本流程
</span>

```ts
const result = PhysicsService.boxOverlap(new mw.Vector(0,0,0), new Vector(30, 30, 30), {}, {});
for (const item of result) {
    // item:  检测结果。
}
```

___

### boxTraceMulti <Score text="boxTraceMulti" /> 

• `Static` **boxTraceMulti**(`start`, `end`, `halfSize`, `orientation`, `collisionParams`, `renderParams`): [`HitResult`](mw.HitResult.md)[] 

盒体沿着给定的路径扫过一个空间，直到首次在起点盒体空间之外遇到阻挡命中时结束（盒体在起点时重叠的阻挡对象不包含在首次判定中），返回沿途遇到的所有命中。

#### Parameters

| `start` [`Vector`](mw.Vector.md) |  起始点 |
| :------ | :------ |
| `end` [`Vector`](mw.Vector.md) | 终止点 |
| `halfSize` [`Vector`](mw.Vector.md) |  盒形大小 range: 无 |
| `orientation` [`Rotation`](mw.Rotation.md) |  旋转大小 |
| `collisionParams` [`CollisionQueryParams`](../interfaces/mw.CollisionQueryParams.md) | 空间查询碰撞参数 |
| `renderParams` [`RenderQueryParams`](../interfaces/mw.RenderQueryParams.md) | 空间查询渲染参数 |

#### Returns

| [`HitResult`](mw.HitResult.md)[] | HitResult数组 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例: 如下示例展示使用矩形范围检测的基本流程
</span>

```ts
const result = PhysicsService.boxTraceMulti(new mw.Vector(0,0,0), new mw.Vector(1000,0,0), new Vector(30, 30, 30), new Rotation(45, 45, 45), {}, {});
for (const item of result) {
    // item:  检测结果。
}
```

___

### boxTraceSingle <Score text="boxTraceSingle" /> 

• `Static` **boxTraceSingle**(`start`, `end`, `halfSize`, `orientation`, `collisionParams`, `renderParams`): [`HitResult`](mw.HitResult.md) 

盒体沿着给定的路径扫过一个空间，并返回遇到的第一个阻挡命中。

#### Parameters

| `start` [`Vector`](mw.Vector.md) |  起始点 |
| :------ | :------ |
| `end` [`Vector`](mw.Vector.md) | 终止点 |
| `halfSize` [`Vector`](mw.Vector.md) |  盒形大小 range: 无 |
| `orientation` [`Rotation`](mw.Rotation.md) |  旋转大小 |
| `collisionParams` [`CollisionQueryParams`](../interfaces/mw.CollisionQueryParams.md) | 空间查询碰撞参数 |
| `renderParams` [`RenderQueryParams`](../interfaces/mw.RenderQueryParams.md) | 空间查询渲染参数 |

#### Returns

| [`HitResult`](mw.HitResult.md) | HitResult |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例: 如下示例展示使用矩形范围检测的基本流程
</span>

```ts
const result = PhysicsService.boxTraceSingle(new mw.Vector(0,0,0), new mw.Vector(1000,0,0), new Vector(30, 30, 30), new Rotation(45, 45, 45), {}, {});
```

___

### capsuleOverlap <Score text="capsuleOverlap" /> 

• `Static` **capsuleOverlap**(`capsulePos`, `radius`, `halfHeight`, `collisionParams`, `renderParams`): [`GameObject`](mw.GameObject.md)[] 

返回一个与给定胶囊体重叠的对象数组

#### Parameters

| `capsulePos` [`Vector`](mw.Vector.md) | 检测位置 |
| :------ | :------ |
| `radius` `number` |  胶囊体半径 range: 无 type: 浮点型 |
| `halfHeight` `number` | 胶囊体半高 range: 无 type: 浮点型 |
| `collisionParams` [`CollisionQueryParams`](../interfaces/mw.CollisionQueryParams.md) | 碰撞查询渲染参数 |
| `renderParams` [`RenderQueryParams`](../interfaces/mw.RenderQueryParams.md) | 空间查询渲染参数 |

#### Returns

| [`GameObject`](mw.GameObject.md)[] | GameObject数组 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例: 如下示例展示使用矩形范围检测的基本流程
</span>

```ts
const result = PhysicsService.capsuleOverlap(new mw.Vector(0,0,0), 30, 80, {}, {});
for (const item of result) {
    // item:  检测结果。
}
```

___

### capsuleTraceMulti <Score text="capsuleTraceMulti" /> 

• `Static` **capsuleTraceMulti**(`start`, `end`, `radius`, `halfHeight`, `collisionParams`, `renderParams`): [`HitResult`](mw.HitResult.md)[] 

胶囊体沿着给定的路径扫过一个空间，直到首次在起点胶囊体空间之外遇到阻挡命中时结束（胶囊体在起点时重叠的阻挡对象不包含在首次判定中），返回沿途遇到的所有命中。

#### Parameters

| `start` [`Vector`](mw.Vector.md) |  起始点 |
| :------ | :------ |
| `end` [`Vector`](mw.Vector.md) | 终止点 |
| `radius` `number` |  胶囊体半径 range: 无 type: 浮点型 |
| `halfHeight` `number` |  胶囊体半高 range: 无 type: 浮点型 |
| `collisionParams` [`CollisionQueryParams`](../interfaces/mw.CollisionQueryParams.md) | 空间查询碰撞参数 |
| `renderParams` [`RenderQueryParams`](../interfaces/mw.RenderQueryParams.md) | 空间查询渲染参数 |

#### Returns

| [`HitResult`](mw.HitResult.md)[] | HitResult数组 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例: 如下示例展示使用矩形范围检测的基本流程
</span>

```ts
const result = PhysicsService.capsuleTraceMulti(new mw.Vector(0,0,0), new mw.Vector(1000,0,0), 30, 80, {}, {});
for (const item of result) {
    // item:  检测结果。
}
```

___

### capsuleTraceSingle <Score text="capsuleTraceSingle" /> 

• `Static` **capsuleTraceSingle**(`start`, `end`, `radius`, `halfHeight`, `collisionParams`, `renderParams`): [`HitResult`](mw.HitResult.md) 

胶囊体沿着给定的路径扫过一个空间，并返回遇到的第一个阻挡命中。

#### Parameters

| `start` [`Vector`](mw.Vector.md) |  起始点 |
| :------ | :------ |
| `end` [`Vector`](mw.Vector.md) | 终止点 |
| `radius` `number` |  胶囊体半径 range: 无 type: 浮点型 |
| `halfHeight` `number` |  胶囊体半高 range: 无 type: 浮点型 |
| `collisionParams` [`CollisionQueryParams`](../interfaces/mw.CollisionQueryParams.md) | 空间查询碰撞参数 |
| `renderParams` [`RenderQueryParams`](../interfaces/mw.RenderQueryParams.md) | 空间查询渲染参数 |

#### Returns

| [`HitResult`](mw.HitResult.md) | HitResult |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例: 如下示例展示使用矩形范围检测的基本流程
</span>

```ts
const result = PhysicsService.capsuleTraceSingle(new mw.Vector(0,0,0), new mw.Vector(1000,0,0), 30, 80, {}, {});
```

___

### deleteCollisionGroup <Score text="deleteCollisionGroup" /> 

• `Static` **deleteCollisionGroup**(`name`): `void` 

删除已有碰撞组

#### Parameters

| `name` `string` | 碰撞组名 range: 不限制 |
| :------ | :------ |


<span style="font-size: 14px;">
使用示例:在场景中创建一个名为 CollisionGroup 的脚本，并拖入场景中，并复制以下代码进入脚本。按下 1 后可在编辑器窗口客户端内看到输出"GroupB"
</span>

```ts
@Component
export default class CollisionGroup extends Script {

    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        PhysicsService.addCollisionGroup("GroupA");
        PhysicsService.addCollisionGroup("GroupB");
        PhysicsService.setCollisionBetweenGroups("GroupA", "GroupB", false);

        // 创建模拟物理的球体A并设置碰撞组为GroupA
        InputUtil.onKeyDown(Keys.One, ()=>{
            PhysicsService.deleteCollisionGroup("GroupA");
            console.log(PhysicsService.getValidCollisionGroups());
        })
    }

    protected onUpdate(dt: number): void {

    }

    // 脚本被销毁时最后一帧执行完调用此函数
    protected onDestroy(): void {

    }
}
```

___

### getAvailableCollisionGroupsCount <Score text="getAvailableCollisionGroupsCount" /> 

• `Static` **getAvailableCollisionGroupsCount**(): `number` 

获取当前可剩余使用碰撞组数量

#### Returns

| `number` | 剩余可用碰撞组数量 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例: 在场景中创建一个名为 CollisionGroup 的脚本，并拖入场景中，并复制以下代码进入脚本。按下 1 后可在编辑器窗口客户端内看到输出 "8"
</span>

```ts
@Component
export default class CollisionGroup extends Script {

    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        PhysicsService.addCollisionGroup("GroupA");
        PhysicsService.addCollisionGroup("GroupB");
        PhysicsService.setCollisionBetweenGroups("GroupA", "GroupB", false);

        // 创建模拟物理的球体A并设置碰撞组为GroupA
        InputUtil.onKeyDown(Keys.One, ()=>{
            console.log(PhysicsService.getAvailableCollisionGroupsCount());
        })
    }
}
```

___

### getCollisionBetweenGroups <Score text="getCollisionBetweenGroups" /> 

• `Static` **getCollisionBetweenGroups**(`group1`, `group2`): `boolean` 

获取两碰撞组之间的碰撞关系(是否可发生碰撞)

#### Parameters

| `group1` `string` | 碰撞组名 1 range: 不限制 |
| :------ | :------ |
| `group2` `string` | 碰撞组名 2 range: 不限制 |

#### Returns

| `boolean` | 碰撞关系(是否可发生碰撞) |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例: 在场景中创建一个名为 CollisionGroup 的脚本，并拖入场景中，并复制以下代码进入脚本。按下 1 后可在编辑器窗口客户端内看到输出 "false"
</span>

```ts
@Component
export default class CollisionGroup extends Script {

    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        PhysicsService.addCollisionGroup("GroupA");
        PhysicsService.addCollisionGroup("GroupB");
        PhysicsService.setCollisionBetweenGroups("GroupA", "GroupB", false);

        // 创建模拟物理的球体A并设置碰撞组为GroupA
        InputUtil.onKeyDown(Keys.One, ()=>{
            console.log(PhysicsService.getCollisionBetweenGroups("GroupA", "GroupB"));
        })
    }
}
```

___

### getValidCollisionGroups <Score text="getValidCollisionGroups" /> 

• `Static` **getValidCollisionGroups**(): `string`[] 

获取当前已添加的碰撞组名列表

#### Returns

| `string`[] | 当前已添加的碰撞组名列表 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例: 在场景中创建一个名为 CollisionGroup 的脚本，并拖入场景中，并复制以下代码进入脚本。按下1后可在编辑器窗口客户端内看到输出 "GroupA,GroupB"
</span>

```ts
@Component
export default class CollisionGroup extends Script {

    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        PhysicsService.addCollisionGroup("GroupA");
        PhysicsService.addCollisionGroup("GroupB");
        PhysicsService.setCollisionBetweenGroups("GroupA", "GroupB", false);

        // 创建模拟物理的球体A并设置碰撞组为GroupA
        InputUtil.onKeyDown(Keys.One, ()=>{
            console.log(PhysicsService.getValidCollisionGroups());
        })
    }
}
```

___

### isCollisionGroupValid <Score text="isCollisionGroupValid" /> 

• `Static` **isCollisionGroupValid**(`name`): `boolean` 

检测碰撞组是否有效(已添加过)

#### Parameters

| `name` `string` | 碰撞组名 range: 不限制 |
| :------ | :------ |

#### Returns

| `boolean` | 碰撞组是否有效 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:在场景中创建一个名为 CollisionGroup 的脚本，并拖入场景中，并复制以下代码进入脚本。按下 1 后可在编辑器窗口客户端内看到输出 "false"
</span>

```ts
@Component
export default class CollisionGroup extends Script {

    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        PhysicsService.addCollisionGroup("GroupA");
        PhysicsService.addCollisionGroup("GroupB");
        PhysicsService.setCollisionBetweenGroups("GroupA", "GroupB", false);

        // 创建模拟物理的球体A并设置碰撞组为GroupA
        InputUtil.onKeyDown(Keys.One, ()=>{
            console.log(PhysicsService.isCollisionGroupValid("GroupC"));
        })
    }
}
```

___

### lineTraceMulti <Score text="lineTraceMulti" /> 

• `Static` **lineTraceMulti**(`start`, `end`, `collisionParams`, `renderParams`): [`HitResult`](mw.HitResult.md)[] 

沿着给定的路径进行射线追踪，直到首次遇到阻挡命中时结束，返回沿途遇到的所有命中。

#### Parameters

| `start` [`Vector`](mw.Vector.md) |  起始点 |
| :------ | :------ |
| `end` [`Vector`](mw.Vector.md) | 终止点 |
| `collisionParams` [`CollisionQueryParams`](../interfaces/mw.CollisionQueryParams.md) | 空间查询碰撞参数 |
| `renderParams` [`RenderQueryParams`](../interfaces/mw.RenderQueryParams.md) | 空间查询渲染参数 |

#### Returns

| [`HitResult`](mw.HitResult.md)[] | HitResult数组 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例: 如下示例展示使用矩形范围检测的基本流程
</span>

```ts
const result = PhysicsService.lineTraceMulti(new mw.Vector(0,0,0), new mw.Vector(1000,0,0), {}, {});
for (const item of result) {
    // item:  检测结果。
}
```

___

### lineTraceSingle <Score text="lineTraceSingle" /> 

• `Static` **lineTraceSingle**(`start`, `end`, `collisionParams`, `renderParams`): [`HitResult`](mw.HitResult.md) 

沿着给定的路径进行射线追踪，并返回遇到的第一个阻挡命中。

#### Parameters

| `start` [`Vector`](mw.Vector.md) |  起始点 |
| :------ | :------ |
| `end` [`Vector`](mw.Vector.md) | 终止点 |
| `collisionParams` [`CollisionQueryParams`](../interfaces/mw.CollisionQueryParams.md) | 空间查询碰撞参数 |
| `renderParams` [`RenderQueryParams`](../interfaces/mw.RenderQueryParams.md) | 空间查询渲染参数 |

#### Returns

| [`HitResult`](mw.HitResult.md) | HitResult |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例: 如下示例展示使用矩形范围检测的基本流程
</span>

```ts
const result = PhysicsService.lineTraceSingle(new mw.Vector(0,0,0), new mw.Vector(1000,0,0), {}, {});
```

___

### renameCollisionGroup <Score text="renameCollisionGroup" /> 

• `Static` **renameCollisionGroup**(`previousName`, `newName`): `void` 

重命名碰撞组

#### Parameters

| `previousName` `string` | 碰撞组名 range: 不限制 |
| :------ | :------ |
| `newName` `string` | 新碰撞组名 range: 不限制 |


<span style="font-size: 14px;">
使用示例:在场景中创建一个名为CollisionGroup的脚本，并拖入场景中，并复制以下代码进入脚本。按下1后可在编辑器窗口客户端内看到输出"GroupB,GroupC"
</span>

```ts
@Component
export default class CollisionGroup extends Script {

    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        PhysicsService.addCollisionGroup("GroupA");
        PhysicsService.addCollisionGroup("GroupB");
        PhysicsService.setCollisionBetweenGroups("GroupA", "GroupB", false);

        // 创建模拟物理的球体A并设置碰撞组为GroupA
        InputUtil.onKeyDown(Keys.One, ()=>{
            PhysicsService.renameCollisionGroup("GroupA","GroupC");
            console.log(PhysicsService.getValidCollisionGroups());
        })
    }

    protected onUpdate(dt: number): void {

    }

    // 脚本被销毁时最后一帧执行完调用此函数
    protected onDestroy(): void {

    }
}
```

___

### setCollisionBetweenGroups <Score text="setCollisionBetweenGroups" /> 

• `Static` **setCollisionBetweenGroups**(`group1`, `group2`, `collidable`): `void` 

设置俩碰撞组之间的碰撞关系(是否可发生碰撞)

#### Parameters

| `group1` `string` | 碰撞组名1 range: 不限制 |
| :------ | :------ |
| `group2` `string` | 碰撞组名2 range: 不限制 |
| `collidable` `boolean` | 是否可碰撞 |


<span style="font-size: 14px;">
使用示例: 在场景中创建一个名为CollisionGroup的脚本，并拖入场景中，并复制以下代码进入脚本。按下1和2会看到场景中生成了两个小球，并推动距离最近的小球去撞击另一个，会发现玩家可以与球体发生碰撞，但两个小球间可穿透。
</span>

```ts
@Component
export default class CollisionGroup extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        PhysicsService.addCollisionGroup("GroupA");
        PhysicsService.addCollisionGroup("GroupB");
        PhysicsService.setCollisionBetweenGroups("GroupA", "GroupB", false);

        // 创建模拟物理的球体A并设置碰撞组为GroupA
        InputUtil.onKeyDown(Keys.One, ()=>{
            this.serverCreateBall(new Vector(300, 0, 0), "GroupA", true);
        })

        // 创建正常碰撞的球体B并设置碰撞组为GroupB
        InputUtil.onKeyDown(Keys.Two, ()=>{
            this.serverCreateBall(new Vector(600, 0, 0), "GroupB", false);
        })
    }

    @mw.RemoteFunction(mw.Server)
    serverCreateBall(pos:Vector, Group:string, bPhysicsSimulate:boolean)
    {
        GameObject.asyncSpawn("197388", {replicates:true}).then((obj)=>{
            let ball  = obj as mw.Model;
            ball.worldTransform.position = pos;
            if (bPhysicsSimulate)
            {
                ball.physicsEnabled = true;
                ball.massEnabled = true;
                ball.mass = 50;
            }
            ball.collisionGroup = Group;
        })
    }
}
```

___

### sphereOverlap <Score text="sphereOverlap" /> 

• `Static` **sphereOverlap**(`spherePos`, `sphereRadius`, `collisionParams`, `renderParams`): [`GameObject`](mw.GameObject.md)[] 

返回一个与给定球体重叠的对象数组

#### Parameters

| `spherePos` [`Vector`](mw.Vector.md) | 检测位置 |
| :------ | :------ |
| `sphereRadius` `number` | 球半径 range: 无 type: 浮点型 |
| `collisionParams` [`CollisionQueryParams`](../interfaces/mw.CollisionQueryParams.md) | 碰撞查询渲染参数 |
| `renderParams` [`RenderQueryParams`](../interfaces/mw.RenderQueryParams.md) | 空间查询渲染参数 |

#### Returns

| [`GameObject`](mw.GameObject.md)[] | GameObject数组 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例: 如下示例展示使用矩形范围检测的基本流程
</span>

```ts
const result = PhysicsService.sphereOverlap(new mw.Vector(0,0,0), 30, {}, {});
for (const item of result) {
    // item:  检测结果。
}
```

___

### sphereTraceMulti <Score text="sphereTraceMulti" /> 

• `Static` **sphereTraceMulti**(`start`, `end`, `radius`, `collisionParams`, `renderParams`): [`HitResult`](mw.HitResult.md)[] 

球体沿着给定的路径扫过一个空间，直到首次在起点球体空间之外遇到阻挡命中时结束（球体在起点时重叠的阻挡对象不包含在首次判定中），返回沿途遇到的所有命中。

#### Parameters

| `start` [`Vector`](mw.Vector.md) |  起始点 |
| :------ | :------ |
| `end` [`Vector`](mw.Vector.md) | 终止点 |
| `radius` `number` |  球形半径 range: 无 type: 浮点型 |
| `collisionParams` [`CollisionQueryParams`](../interfaces/mw.CollisionQueryParams.md) | 空间查询碰撞参数 |
| `renderParams` [`RenderQueryParams`](../interfaces/mw.RenderQueryParams.md) | 空间查询渲染参数 |

#### Returns

| [`HitResult`](mw.HitResult.md)[] | HitResult数组 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例: 如下示例展示使用矩形范围检测的基本流程
</span>

```ts
const result = PhysicsService.sphereTraceMulti(new mw.Vector(0,0,0), new mw.Vector(1000,0,0), 30, {}, {});
for (const item of result) {
    // item:  检测结果。
}
```

___

### sphereTraceSingle <Score text="sphereTraceSingle" /> 

• `Static` **sphereTraceSingle**(`start`, `end`, `radius`, `collisionParams`, `renderParams`): [`HitResult`](mw.HitResult.md) 

球体沿着给定的路径扫过一个空间，并返回遇到的第一个阻挡命中。

#### Parameters

| `start` [`Vector`](mw.Vector.md) |  起始点 |
| :------ | :------ |
| `end` [`Vector`](mw.Vector.md) | 终止点 |
| `radius` `number` |  球形半径 range: 无 type: 浮点型 |
| `collisionParams` [`CollisionQueryParams`](../interfaces/mw.CollisionQueryParams.md) | 空间查询碰撞参数 |
| `renderParams` [`RenderQueryParams`](../interfaces/mw.RenderQueryParams.md) | 空间查询渲染参数 |

#### Returns

| [`HitResult`](mw.HitResult.md) | HitResult |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例: 如下示例展示使用矩形范围检测的基本流程
</span>

```ts
const result = PhysicsService.sphereTraceSingle(new mw.Vector(0,0,0), new mw.Vector(1000,0,0), 30, {}, {});
```
