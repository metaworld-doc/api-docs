[场景](../groups/场景.场景.md) / vectorSequencePoint

# vectorSequencePoint <Badge type="tip" text="Class" /> <Score text="vectorSequencePoint" />

特效三维向量值曲线节点

## Table of contents

### Properties <Score text="Properties" /> 
| **[timeKey](mw.vectorSequencePoint.md#timekey)**: `number`  |
| :-----|
| 时间点 取值为[0, 1]，代表生命周期的起始和结束|
| **[value](mw.vectorSequencePoint.md#value)**: [`Vector`](mw.Vector.md)  |
| 向量值|

构造函数

#### Parameters

| `inTimeKey` `number` | 时间点 type: 浮点型 range:[0, 1] |
| :------ | :------ |
| `inValue` [`Vector`](mw.Vector.md) | 时间点 type: 浮点型 range: 无 |
| `inTolerance?` [`Vector`](mw.Vector.md) | 时间点 type: 浮点型 range: 无 default: mw.Vector(0, 0, 0) |

## Properties

### timeKey <Score text="timeKey" /> 

• **timeKey**: `number`

时间点 取值为[0, 1]，代表生命周期的起始和结束

___

### value <Score text="value" /> 

• **value**: [`Vector`](mw.Vector.md)

向量值
