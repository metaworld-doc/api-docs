[输入](../groups/输入.输入.md) / GestureDelegate

# GestureDelegate <Badge type="tip" text="Class" /> <Score text="GestureDelegate" />

手势代理类

## Table of contents

### Properties <Score text="Properties" /> 
| **[oneFingerMoveGestureDelegate](mw.GestureDelegate.md#onefingermovegesturedelegate)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`location`: [`Vector2`](mw.Vector2.md)) => `void`\>  |
| :-----|
| 单指滑动代理|
| **[pinchGestureDelegate](mw.GestureDelegate.md#pinchgesturedelegate)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`Distance`: `number`) => `void`\>  |
| 挤压手势代理|
| **[tapGestureDelegate](mw.GestureDelegate.md#tapgesturedelegate)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`SelectType`: [`SelectTapType`](../enums/mw.SelectTapType.md), `location`: [`Vector2`](mw.Vector2.md)) => `void`\>  |
| 点击事件代理|
| **[touchBeganGestureDelegate](mw.GestureDelegate.md#touchbegangesturedelegate)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`FingerIndex`: `number`, `Position`: [`Vector2`](mw.Vector2.md)) => `void`\>  |
| 手指按下代理|
| **[touchEndGestureDelegate](mw.GestureDelegate.md#touchendgesturedelegate)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`FingerIndex`: `number`) => `void`\>  |
| 手指抬起代理|
| **[touchMoveGestureDelegate](mw.GestureDelegate.md#touchmovegesturedelegate)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`FingerIndex`: `number`, `Position`: [`Vector2`](mw.Vector2.md)) => `void`\>  |
| 手指滑动代理|
| **[twoFingerMoveGestureDelegate](mw.GestureDelegate.md#twofingermovegesturedelegate)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`location`: [`Vector2`](mw.Vector2.md)) => `void`\>  |
| 双指滑动代理|

## Properties

### oneFingerMoveGestureDelegate <Score text="oneFingerMoveGestureDelegate" /> 

▪ `Static` **oneFingerMoveGestureDelegate**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`location`: [`Vector2`](mw.Vector2.md)) => `void`\>

单指滑动代理

___

### pinchGestureDelegate <Score text="pinchGestureDelegate" /> 

▪ `Static` **pinchGestureDelegate**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`Distance`: `number`) => `void`\>

挤压手势代理

___

### tapGestureDelegate <Score text="tapGestureDelegate" /> 

▪ `Static` **tapGestureDelegate**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`SelectType`: [`SelectTapType`](../enums/mw.SelectTapType.md), `location`: [`Vector2`](mw.Vector2.md)) => `void`\>

点击事件代理

___

### touchBeganGestureDelegate <Score text="touchBeganGestureDelegate" /> 

▪ `Static` **touchBeganGestureDelegate**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`FingerIndex`: `number`, `Position`: [`Vector2`](mw.Vector2.md)) => `void`\>

手指按下代理

___

### touchEndGestureDelegate <Score text="touchEndGestureDelegate" /> 

▪ `Static` **touchEndGestureDelegate**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`FingerIndex`: `number`) => `void`\>

手指抬起代理

___

### touchMoveGestureDelegate <Score text="touchMoveGestureDelegate" /> 

▪ `Static` **touchMoveGestureDelegate**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`FingerIndex`: `number`, `Position`: [`Vector2`](mw.Vector2.md)) => `void`\>

手指滑动代理

___

### twoFingerMoveGestureDelegate <Score text="twoFingerMoveGestureDelegate" /> 

▪ `Static` **twoFingerMoveGestureDelegate**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`location`: [`Vector2`](mw.Vector2.md)) => `void`\>

双指滑动代理
