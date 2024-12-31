[玩法](../groups/玩法.玩法.md) / CollisionQueryParams

# CollisionQueryParams <Badge type="tip" text="Interface" /> <Score text="CollisionQueryParams" />

空间查询碰撞参数

## Table of contents

### Properties <Score text="Properties" /> 
| **[collisionGroup](mw.CollisionQueryParams.md#collisiongroup)**: `string`  |
| :-----|
| 指定检测使用的碰撞通道。碰撞组中设置为不与该组碰撞的模型将被忽略。默认值为“Default”组。|
| **[objectsToIgnore](mw.CollisionQueryParams.md#objectstoignore)**: [`GameObject`](../classes/mw.GameObject.md)[]  |
| 一个对象数组，检测结果会忽略这个数组内的对象。|
| **[respectCanCollide](mw.CollisionQueryParams.md#respectcancollide)**: `boolean`  |
| 如果此属性为true，则查询操作将使用交互模型的Model.collisionEnabled值优先于Model.queryEnabled值，用于确定该模型是否包含在空间查询结果数组中。|

## Properties

### collisionGroup <Score text="collisionGroup" /> 

• `Optional` **collisionGroup**: `string`

指定检测使用的碰撞通道。碰撞组中设置为不与该组碰撞的模型将被忽略。默认值为“Default”组。

___

### objectsToIgnore <Score text="objectsToIgnore" /> 

• `Optional` **objectsToIgnore**: [`GameObject`](../classes/mw.GameObject.md)[]

一个对象数组，检测结果会忽略这个数组内的对象。

___

### respectCanCollide <Score text="respectCanCollide" /> 

• `Optional` **respectCanCollide**: `boolean`

如果此属性为true，则查询操作将使用交互模型的Model.collisionEnabled值优先于Model.queryEnabled值，用于确定该模型是否包含在空间查询结果数组中。
