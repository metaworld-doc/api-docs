[角色系统](../groups/角色系统.角色系统.md) / Character

# Character <Badge type="tip" text="Class" /> <Score text="Character" />

角色

--------------------------------------

什么是角色？

角色是指代表玩家游戏实体。它是游戏中能够在虚拟世界中移动、与环境和其他角色进行交互的主要对象。可以将 Character 看作是游戏中的角色扮演者，它可以是玩家控制的角色或由游戏系统控制的角色。

角色具备哪些功能？

移动和交互。Character 具备在游戏世界中移动和与环境进行交互的能力。它可以行走、跑动、跳跃或飞行等，根据游戏规则和角色设计的不同， Character 可以执行各种动作。

功能和行为。Character 可以具备各种功能和行为。例如，一个角色可以是战士，具有攻击和防御技能；另一个角色可以是商人，负责交易和提供物品。 Character 的功能和行为由游戏开发者根据游戏需求进行定义和实现。

总的来说：

1. 控制角色移动：你可以使用它来指定角色的移动速度、方向和加速度等参数。它允许你以编程的方式控制角色的运动，例如让角色向前移动、旋转或跳跃等。并支持多种移动方式：例如，它可以实现直线运动、旋转、跳跃、游泳、蹲伏和飞行等。根据你的游戏需求，你可以选择合适的移动方式，并使用对应接口来实现。

2. 处理物理模拟与碰撞：它可以使用物理引擎来模拟角色的重力、碰撞和惯性等效果。通过物理模拟，角色可以与游戏世界中的其他对象进行交互，并受到合理的物理影响。执行碰撞检测：它可以检测角色与墙壁、地面或其他角色的碰撞，并采取相应的行动。这有助于实现更真实和可靠的角色移动和交互。

3. 处理角色外观：可以给角色赋予各种各样的外貌。为角色选择合适的服装、装备和特征。无论是超级英雄的紧身服、中世纪骑士的盔甲还是未来战士的高科技装备，感受到角色的独特风格和个性。

4. 实现生动的动画：还能赋予角色生动的动画效果。能够让角色在游戏中跳跃、奔跑、战斗，甚至是展现出各种特殊技能和动作。

其中比较重要的：

- addMovement 函数控制角色沿着给定方向移动。

- loadAnimation 函数将左侧动画资源加载在角色身上，使角色自如的使用多种动作。

- description 属性更改角色外观，左侧栏中提供角色大量的衣服、饰品等资源，传入资源ID字符串进行随意更换外观。

<span style="font-size: 14px;">
使用示例: 生成一个角色
</span>

```ts
@Component
 export default class NewExample extends Script {
     protected onStart(): void {
         GameObject.asyncSpawn<Model>("183107",{transform: new Transform(new Vector(100,0,0),new Rotation(0,0,0),new Vector(1,1,1))}).then(()=>{
             console.log("character spawn success！");
         });
     }
}
```

## Hierarchy

- [`Pawn`](mw.Pawn.md)

  ↳ **`Character`**

## Table of contents

### Properties <Score text="Properties" /> 
| **[onDescriptionChange](mw.Character.md#ondescriptionchange)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<[`OnDescriptionChange`](../modules/Core.mw.md#ondescriptionchange)\>   |
| :-----|
| 外观加载细节变化委托|
| **[onDescriptionComplete](mw.Character.md#ondescriptioncomplete)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<[`OnDescriptionComplete`](../modules/Core.mw.md#ondescriptioncomplete)\>   |
| 角色外观加载完成时，调用委托|
| **[onEmergeFromWater](mw.Character.md#onemergefromwater)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\>   |
| 角色向上游泳到达游泳区域水面时，调用委托|
| **[onLoadDescriptionFailed](mw.Character.md#onloaddescriptionfailed)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<[`OnLoadDescriptionFailed`](../modules/Core.mw.md#onloaddescriptionfailed)\>   |
| 外观主体（前发，后发，头，上衣，下衣，手套，鞋）加载失败委托|
| **[onStateChanged](mw.Character.md#onstatechanged)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`prevState`: [`CharacterStateType`](../enums/mw.CharacterStateType.md), `currentState`: [`CharacterStateType`](../enums/mw.CharacterStateType.md)) => `void`\>  |
| 角色状态改变回调|
| **[onSweepCollision](mw.Character.md#onsweepcollision)**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`velocities`: [`Vector`](mw.Vector.md)[], `hitActors`: [`GameObject`](mw.GameObject.md)[], `impactPoints`: [`Vector`](mw.Vector.md)[], `impactNormals`: [`Vector`](mw.Vector.md)[]) => `void`\>  |
| 角色开启强制位移后，移动中碰撞检测结果的代理|

### Accessors <Score text="Accessors" /> 
| **[brakingDecelerationFlying](mw.Character.md#brakingdecelerationflying)**(): `number`   |
| :-----|
| 获取角色的飞行制动速率|
| **[brakingDecelerationSwimming](mw.Character.md#brakingdecelerationswimming)**(): `number`   |
| 获取角色游泳制动速率。角色在游泳状态下移动时受到的减速度。|
| **[brakingDecelerationWalking](mw.Character.md#brakingdecelerationwalking)**(): `number`   |
| 设置角色行走制动速率。行走制动速率是指角色在行走状态下的刹车减速度。当角色在行走状态下停止移动或改变方向时，刹车减速度会影响角色减速的速率。较高的值将导致角色更快地减速，而较低的值将导致角色减速得更慢。|
| **[canStandOn](mw.Character.md#canstandon)**(): `boolean`   |
| 获取角色是否可以被其他玩家站立。。true表示其他角色可以站到玩家头上。false表示其他角色不可以站到玩家头上。|
| **[capsuleCorrectionEnabled](mw.Character.md#capsulecorrectionenabled)**(): `boolean`   |
| 获取角色当前是否使用胶囊体修正。true代表应用角色编辑中的数据自动计算胶囊体大小。false 代表应用"capsuleHalfHeight"和"capsuleRadius"设置胶囊体的大小。|
| **[characterType](mw.Character.md#charactertype)**(): [`CharacterType`](../enums/mw.CharacterType.md)  |
| 获取角色是什么类型。角色类型分为基础人形、高级人形和四足类型。|
| **[collisionExtent](mw.Character.md#collisionextent)**(): [`Vector`](mw.Vector.md)   |
| 获取包裹角色碰撞体的形状大小。角色碰撞盒形状的大小，决定角色与场景对象交互时检测碰撞范围的大小。|
| **[collisionShape](mw.Character.md#collisionshape)**(): [`CustomShapeType`: [`CustomShapeType`](../enums/mw.CustomShapeType.md)](../enums/mw.CustomShapeType.md)   |
| 获取角色碰撞形状（胶囊体型、球型、盒型）。角色碰撞盒形状的大小，决定角色与场景对象交互时检测碰撞范围的大小。球体取xyz最小值，胶囊体半径取xy最小值，z为半长，盒体xyz为半长宽高。|
| **[collisionWithOtherCharacterEnabled](mw.Character.md#collisionwithothercharacterenabled)**(): `boolean`   |
| 获取角色当前是否可以与其他角色产生碰撞。|
| **[complexMovementEnabled](mw.Character.md#complexmovementenabled)**(): `boolean`  |
| 是否启用复杂移动策略|
| **[crouchedHeight](mw.Character.md#crouchedheight)**(): `number`   |
| 获取角色下蹲状态下，碰撞盒的高度。|
| **[currentAnimation](mw.Character.md#currentanimation)**(): [`Animation`](mw.Animation.md)  |
| 当前播放的动画对象|
| **[currentStance](mw.Character.md#currentstance)**(): [`Stance`](mw.Stance.md)  |
| 获取当前正在播放的基础姿态|
| **[currentSubStance](mw.Character.md#currentsubstance)**(): [`SubStance`](mw.SubStance.md)  |
| 获取当前正在播放的二级姿态，二级姿态类型为SubStance|
| **[description](mw.Character.md#description)**(): [`CharacterDescription`](mw.CharacterDescription.md)   |
| 角色外观配置。返回值为 CharacterDescription 类。调用 description 变量可以修改角色的外观，可更改角色的外观参数详见 CharacterDescription 类。|
| **[displayName](mw.Character.md#displayname)**(): `string`  |
| 获取角色名称。角色名称默认会显示在角色头顶上方。|
| **[driftControl](mw.Character.md#driftcontrol)**(): `number`   |
| 获取角色在空中的灵活度。角色在空中时, 控制水平方向移动的灵活度；范围:0~1, 0表示不能控制, 1表示能按地面最大移动速率完全控制|
| **[forceUpdateMovement](mw.Character.md#forceupdatemovement)**(`value`: `boolean`): `void`   |
| 强制更新移动|
| **[gravityScale](mw.Character.md#gravityscale)**(): `number`   |
| 获取重力的倍率。对于角色来说，重力会乘以该值。范围0~10, 过大和过小的值都会被限制。|
| **[groundFriction](mw.Character.md#groundfriction)**(): `number`   |
| 获取地面摩檫力|
| **[groundFrictionEnabled](mw.Character.md#groundfrictionenabled)**(): `boolean`   |
| 获取单独制动摩擦状态。开启后使用行走制动速率进行计算摩擦效果，不开启则使用的是地面摩擦力进行计算摩擦效果。|
| **[horizontalBrakingDecelerationFalling](mw.Character.md#horizontalbrakingdecelerationfalling)**(): `number`   |
| 获取角色下落制动速率。角色在下落状态下移动时受到的减速度。|
| **[isCrouching](mw.Character.md#iscrouching)**(): `boolean`   |
| 获取角色是否正在蹲下|
| **[isDescriptionReady](mw.Character.md#isdescriptionready)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取当前角色外观是否准备完毕。刚进入场景中或角色还未加载出外观衣服等时，isDescriptionReady为false，完全加载完成后变为true。|
| **[isJumping](mw.Character.md#isjumping)**(): `boolean`   |
| 获取角色是否正在跳跃|
| **[isMoving](mw.Character.md#ismoving)**(): `boolean`   |
| 获取角色是否正在移动|
| **[jumpMaxCount](mw.Character.md#jumpmaxcount)**(): `number`   |
| 获取角色最大可跳跃次数。角色能够执行跳跃的最大次数。|
| **[maxAcceleration](mw.Character.md#maxacceleration)**(): `number`   |
| 获取角色最大加速度。角色移动时，角色可以达到的最大加速度|
| **[maxFallingSpeed](mw.Character.md#maxfallingspeed)**(): `number`   |
| 设置角色最大下落速度。角色在下落状态下移动时，角色可达到的最大移动速度|
| **[maxFlySpeed](mw.Character.md#maxflyspeed)**(): `number`   |
| 获取角色最大飞行速度。角色在飞行状态下进行移动时，角色可达到的最大移动速度|
| **[maxJumpHeight](mw.Character.md#maxjumpheight)**(): `number`   |
| 获取角色最大跳跃高度。角色跳跃时，从起跳位置到最高位置的距离。该值受重力影响。|
| **[maxStepHeight](mw.Character.md#maxstepheight)**(): `number`   |
| 获取角色最大可跨越高度。角色跨越台阶时，台阶的最大高度，大于等于该高度角色均无法跨越。|
| **[maxSwimSpeed](mw.Character.md#maxswimspeed)**(): `number`   |
| 获取角色最大游泳速度。角色在游泳状态下，可达到的最大移动速度。|
| **[maxWalkSpeed](mw.Character.md#maxwalkspeed)**(): `number`   |
| 获取角色的最大行走速度。角色移动时，并不是直接变为最大速度，而是随着输入或其他控制，速度逐渐增加，最大行走速度为角色可以达到的最大速度。同时也是跌倒时的最大横向速度。|
| **[maxWalkSpeedCrouched](mw.Character.md#maxwalkspeedcrouched)**(): `number`   |
| 获取角色最大蹲伏行走速度|
| **[meshPositionOffset](mw.Character.md#meshpositionoffset)**(): [`Vector`](mw.Vector.md)   |
| 获取mesh相对角色坐标点的偏移|
| **[meshRotationOffset](mw.Character.md#meshrotationoffset)**(): [`Rotation`](mw.Rotation.md)   |
| 获取mesh相对角色旋转的偏移|
| **[moveFacingDirection](mw.Character.md#movefacingdirection)**(): [`MoveFacingDirection`](../enums/mw.MoveFacingDirection.md)   |
| 获取角色运动面朝方向。角色模型运动时朝向的方向：|
| **[movementDirection](mw.Character.md#movementdirection)**(): [`MovementDirection`](../enums/mw.MovementDirection.md)   |
| 获取角色运动正方向。角色运动时依据的正方向。|
| **[opacity](mw.Character.md#opacity)**(): `number`   |
| 获取角色单层透明度|
| **[outOfWaterVerticalSpeed](mw.Character.md#outofwaterverticalspeed)**(): `number`   |
| 出水时垂直方向速度|
| **[overheadUI](mw.Character.md#overheadui)**(): [`UIWidget`](Core.mw.UIWidget.md) <Badge type="tip" text="client" />  |
| 获取角色头顶名字的界面|
| **[physicsEnabled](mw.Character.md#physicsenabled)**(): `boolean`  |
| 获取角色物理模拟状态|
| **[ragdollEnabled](mw.Character.md#ragdollenabled)**(): `boolean`  |
| 启用布娃娃|
| **[rotateRate](mw.Character.md#rotaterate)**(): `number`   |
| 获取角色最大转向速度。角色每秒旋转的最大速度。设置为负值时，转向速度被视为无限大，可以瞬间转向。|
| **[velocity](mw.Character.md#velocity)**(): [`Vector`](mw.Vector.md)   |
| 获取角色当前移动速度|
| **[walkableFloorAngle](mw.Character.md#walkablefloorangle)**(): `number`   |
| 获取角色可行走的最大角度。角色站立在斜坡上时，斜坡的最大角度，超过该角度，角色将无法站立在这个斜坡上，角色会存在坠落的表现。使用范围在0-90之间。|
| **[nameDisplayDistance](mw.Character.md#namedisplaydistance)**(): `number` <Badge type="tip" text="client" />  |
| 获取当前客户端所有角色头顶显示名称可见距离。|
| **[nameVisible](mw.Character.md#namevisible)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取当前客户端所有角色头顶显示名称是否可见。|


::: details click
### Accessors <Score text="Accessors" /> 
| **[customTimeDilation](mw.Pawn.md#customtimedilation)**(): `number`   |
| :-----|
| 膨胀时间速度|
| **[player](mw.Pawn.md#player)**(): [`Player`](mw.Player.md)   |
| 玩家对象|
:::


### Methods <Score text="Methods" /> 
| **[addImpulse](mw.Character.md#addimpulse)**(`vector`: [`Vector`](mw.Vector.md), `ignoreMass?`: `boolean`): `void` <Badge type="tip" text="server" />  |
| :-----|
| 添加冲量，相同冲量值在布娃娃与正常状态时，力效果会有差异。质量固定为100，受质量影响的算法为: 冲量按位除以质量|
| **[addMovement](mw.Character.md#addmovement)**(`direction`: [`Vector`](mw.Vector.md)): `void`   |
| 沿着给定的方向向量添加移动输入。不会自动应用移动，由开发者在 onUpdate 事件中执行此操作。效果受 movementDirection 属性影响。如果此时同时有用户输入效果是叠加而不是覆盖。|
| **[attachToSlot](mw.Character.md#attachtoslot)**(`gameObject`: [`GameObject`](mw.GameObject.md), `slotName`: [`HumanoidSlotType`](../enums/mw.HumanoidSlotType.md)  [`NonHumanoidSlotType`](../enums/mw.NonHumanoidSlotType.md)): `void`   |
| 将物体附着到人物角色的指定插槽。只适用于人形角色，附加规则是 KeepRelative，会保留物体之前的 localTransform|
| **[cancelHeadFollow](mw.Character.md#cancelheadfollow)**(): `void` <Badge type="tip" text="client" />  |
| 取消头部追踪|
| **[changeState](mw.Character.md#changestate)**(`stateType`: [`CharacterStateType`](../enums/mw.CharacterStateType.md)): `void`   |
| 改变角色的状态|
| **[clearDescription](mw.Character.md#cleardescription)**(`appearance?`: `boolean`, `slotAndDecoration?`: `boolean`): `void`   |
| 清空角色外观数据。清空角色外观数据，此时角色不具备任何视觉表现。|
| **[detachAllFromSlot](mw.Character.md#detachallfromslot)**(`param?`: `Object`): `void`   |
| 将角色插槽附着的对象全部分离。如果不填入插槽则将全部插槽的附着对象分离。仅对高级人型角色生效。|
| **[detachFromSlot](mw.Character.md#detachfromslot)**(`gameObject`: [`GameObject`](mw.GameObject.md)): `void`   |
| 将物体从插槽中分离|
| **[getAttachmentsFromSlot](mw.Character.md#getattachmentsfromslot)**(`slotName`: [`HumanoidSlotType`](../enums/mw.HumanoidSlotType.md)  [`NonHumanoidSlotType`](../enums/mw.NonHumanoidSlotType.md)): [`GameObject`](mw.GameObject.md)[]   |
| 获取附着到人物角色指定插槽的所有物体。只适用于人形角色，附加规则是 KeepRelative，会保留物体之前的 localTransform|
| **[getCenterVertexByMorphName](mw.Character.md#getcentervertexbymorphname)**(`morphName`: `string`): [`Vector`](mw.Vector.md)   |
| 通过头部模型MorphName实时获取中心顶点位置|
| **[getCurrentState](mw.Character.md#getcurrentstate)**(): [`CharacterStateType`](../enums/mw.CharacterStateType.md)   |
| 获取当前角色的状态|
| **[getDescription](mw.Character.md#getdescription)**(): [`CharacterDescription`](mw.CharacterDescription.md)   |
| 获取角色外观数据。该接口获取角色当前外观数据的拷贝|
| **[getSlotWorldPosition](mw.Character.md#getslotworldposition)**(`slotName`: [`HumanoidSlotType`](../enums/mw.HumanoidSlotType.md)): [`Vector`](mw.Vector.md)   |
| 获取角色插槽的世界坐标。受角色外观中插槽偏移影响，仅对高级人型角色生效。|
| **[getVertexArrayByMorphName](mw.Character.md#getvertexarraybymorphname)**(`morphName`: `string`): [`Vector`](mw.Vector.md)[]   |
| 通过头部模型MorphName实时获取所有顶点位置|
| **[getVertexPosition](mw.Character.md#getvertexposition)**(`index`: `number`): [`Vector`](mw.Vector.md)   |
| 通过头部模型顶点 index 实时获取顶点位置。目前顶点 index 只能从内部工程中查看|
| **[headFollow](mw.Character.md#headfollow)**(`target`: ``null``  [`GameObject`](mw.GameObject.md)  [`Vector`](mw.Vector.md)): `void` <Badge type="tip" text="client" />  |
| 头部追踪|
| **[jump](mw.Character.md#jump)**(): `void`   |
| 使角色触发一个跳跃行为|
| **[loadAnimation](mw.Character.md#loadanimation)**(`assetId`: `string`): [`Animation`](mw.Animation.md)   |
| 为角色加载一个动画资源。该接口会将给定的动画加载到角色上，返回一个可播放的Animation。|
| **[loadStance](mw.Character.md#loadstance)**(`assetId`: `string`): [`Stance`](mw.Stance.md)   |
| 为角色加载一个基础姿态。loadStance会将给定的基础姿态加载到角色上，返回一个可播放的基础姿态 stance 类型。|
| **[loadSubStance](mw.Character.md#loadsubstance)**(`assetId`: `string`): [`SubStance`](mw.SubStance.md)   |
| 为角色加载一个二级姿态|
| **[setCollisionShapeAndExtent](mw.Character.md#setcollisionshapeandextent)**(`shapeType`: [`CustomShapeType`](../enums/mw.CustomShapeType.md), `collisionExtent`: [`Vector`](mw.Vector.md)): `void`   |
| 为角色设置不同形状不同大小的碰撞体|
| **[setCullDistance](mw.Character.md#setculldistance)**(`inCullDistance`: `number`): `void` <Badge type="tip" text="client" />  |
| 角色对象裁剪距离|
| **[setDescription](mw.Character.md#setdescription)**(`data`: `string`  `string`[]  [`CharacterDescription`](mw.CharacterDescription.md)): `void`   |
| 设置角色外观数据。此函数无法更换基础角色。|
| **[setStateEnabled](mw.Character.md#setstateenabled)**(`characterStateType`: [`CharacterStateType`](../enums/mw.CharacterStateType.md), `enabled`: `boolean`): `void`   |
| 设置角色状态开关|
| **[swimUpDown](mw.Character.md#swimupdown)**(`speed`: `number`): `void`   |
| 使角色在水中上浮下潜|
| **[syncDescription](mw.Character.md#syncdescription)**(`appearance?`: `boolean`, `slotAndDecoration?`: `boolean`): `void` <Badge type="tip" text="client" />  |
| 同步角色外观数据。角色在客户端设置外观后只会更换本地角色的外观，其他客户端角色外观未修改。通过该接口可以将本地外观广播至其他客户端。|


::: details click
### Methods <Score text="Methods" /> 
| **[setOutline](mw.Pawn.md#setoutline)**(`enabled`: `boolean`, `color?`: [`LinearColor`](mw.LinearColor.md), `width?`: `number`): `void` <Badge type="tip" text="client" />  |
| :-----|
| 添加描边效果|
| **[setPostProcessOutline](mw.Pawn.md#setpostprocessoutline)**(`enabled`: `boolean`, `color?`: [`LinearColor`](mw.LinearColor.md), `width?`: `number`): `void` <Badge type="tip" text="client" />  |
| 添加后处理描边|
:::


## Properties

___

### onDescriptionChange <Score text="onDescriptionChange" /> 

• **onDescriptionChange**: [`MulticastDelegate`](mw.MulticastDelegate.md)<[`OnDescriptionChange`](../modules/Core.mw.md#ondescriptionchange)\> 

外观加载细节变化委托

::: warning Precautions

当角色对象外观发生变化时执行绑定函数

:::

<span style="font-size: 14px;">
使用示例:将使用到的资源:"14521,35391,161245,75674,57731,63910,58694,58700,60384,58696,136183"拖入优先加载栏。创建一个名为"Example_Character_OnDescriptionChange"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中看到玩家控制角色玩家外观准备未完成播放摊手的效果。给【角色外观描述完成】委托添加函数来播放换装完成特效，并保存角色初始默认外观数据。给【角色外观描述变化】委托添加函数在控制台打印当前角色外观描述变化的具体子项和索引。按下键盘“1”，重置为默认角色外观。按下键盘“2”，修改角色外观。按下键盘“3”，同步角色外观。按下键盘“4”，清空角色外观。代码如下：
</span>

```ts
@Component
export default class Example_Character_OnDescriptionChange extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端玩家
            let myPlayer = Player.localPlayer;
            // 获取玩家控制角色
            let myCharacter = myPlayer.character;
            // 如果玩家外观准备完成挥手，反之摊手
            if(myCharacter.isDescriptionReady) {
                let animation = myCharacter.loadAnimation("35391");
                animation.play();
            } else {
                let animation = myCharacter.loadAnimation("14521");
                animation.play();
            }
            let defaultStyle = null;
            // 给【角色外观描述完成】委托添加函数
            myCharacter.onDescriptionComplete.add(() => {
                // 播放换装完成特效
                EffectService.playOnGameObject("161245", myCharacter, {slotType: HumanoidSlotType.Root});
                // 获取角色默认外观风格
                if(defaultStyle == null) {
                    defaultStyle = myCharacter.getDescription();
                }
            });
            // 给【角色外观描述变化】委托添加函数
            myCharacter.onDescriptionChange.add((operationCode: number, index: number, value: unknown) => {
                console.log("Appearance Changed");
                console.log("OperationCode " + operationCode + " Index " + index);
            });
            // 添加一个按键方法:按下键盘“1”，重置为默认角色外观
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.setDescription(defaultStyle);
            });
            // 添加一个按键方法:按下键盘“2”，修改角色外观
            InputUtil.onKeyDown(Keys.Two, () => {
                if(myCharacter.characterType == CharacterType.HumanoidV2) {
                    // 修改角色style头部:头大小为1.5倍
                    myCharacter.description.advance.headFeatures.head.headOverallScale = 1.5;
                    // 修改角色style体型:身高为1.2倍
                    myCharacter.description.advance.bodyFeatures.body.height = 1.2;
                    // 修改角色style化妆:腮红为75674
                    myCharacter.description.advance.makeup.blush.blushStyle = "75674";
                    // 修改角色style头发:前发为57731，后发为63910
                    myCharacter.description.advance.hair.frontHair.style = "57731";
                    myCharacter.description.advance.hair.backHair.style = "63910";
                    // 修改角色style:上衣为58694，下衣为58700，手套为60384，鞋子为58696
                    myCharacter.description.advance.clothing.upperCloth.style = "58694";
                    myCharacter.description.advance.clothing.lowerCloth.style = "58700";
                    myCharacter.description.advance.clothing.gloves.style = "60384";
                    myCharacter.description.advance.clothing.shoes.style = "58696";
                }
            });
            // 添加一个按键方法:按下键盘“3”，同步角色外观
            InputUtil.onKeyDown(Keys.Three, () => {
                myCharacter.syncDescription();
            });
            // 添加一个按键方法:按下键盘“4”，清空角色外观
            InputUtil.onKeyDown(Keys.Four, () => {
                myCharacter.clearDescription();
            });
        }
    }
}
```

___

### onDescriptionComplete <Score text="onDescriptionComplete" /> 

• **onDescriptionComplete**: [`MulticastDelegate`](mw.MulticastDelegate.md)<[`OnDescriptionComplete`](../modules/Core.mw.md#ondescriptioncomplete)\> 

角色外观加载完成时，调用委托

::: warning Precautions

当角色对象外观加载完成时执行绑定函数

:::

<span style="font-size: 14px;">
使用示例:将使用到的资源:"14521,35391,161245,75674,57731,63910,58694,58700,60384,58696,136183"拖入优先加载栏。创建一个名为"Example_Character"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏。给【角色外观加载完成】委托添加函数来播放换装完成特效。按下键盘“1”，重置为默认角色外观。按下键盘“2”，修改角色外观。按下键盘“3”，同步角色外观。按下键盘“4”，清空角色外观。代码如下：
</span>

```ts
@Component
export default class Example_Character extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端玩家
            let myPlayer = Player.localPlayer;
            // 获取玩家控制角色
            let myCharacter = myPlayer.character;
            // 如果玩家外观准备完成挥手，反之摊手
            if(myCharacter.isDescriptionReady) {
                let animation = myCharacter.loadAnimation("35391");
                animation.play();
            } else {
                let animation = myCharacter.loadAnimation("14521");
                animation.play();
            }
            let defaultStyle = null;
            // 给【角色换装完成】委托添加函数
            myCharacter.onDescriptionComplete.add(() => {
                // 播放换装完成特效
                EffectService.playOnGameObject("161245", myCharacter, {slotType:HumanoidSlotType.Hair});
                // 获取角色默认外观风格
                if(defaultStyle == null) {
                    defaultStyle = myCharacter.getDescription();
                }
            });
            // 添加一个按键方法:按下键盘“1”，重置为默认角色外观
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.setDescription(defaultStyle);
            });
            // 添加一个按键方法:按下键盘“2”，修改角色外观
            InputUtil.onKeyDown(Keys.Two, () => {
                if(myCharacter.characterType == CharacterType.HumanoidV2) {
                    // 修改角色style头部:头大小为1.5倍
                    myCharacter.description.advance.headFeatures.head.headOverallScale = 1.5;
                    // 修改角色style体型:身高为1.2倍
                    myCharacter.description.advance.bodyFeatures.body.height = 1.2;
                    // 修改角色style化妆:腮红为75674
                    myCharacter.description.advance.makeup.blush.blushStyle = "75674";
                    // 修改角色style头发:前发为57731，后发为63910
                    myCharacter.description.advance.hair.frontHair.style = "57731";
                    myCharacter.description.advance.hair.backHair.style = "63910";
                    // 修改角色style:上衣为58694，下衣为58700，手套为60384，鞋子为58696
                    myCharacter.description.advance.clothing.upperCloth.style = "58694";
                    myCharacter.description.advance.clothing.lowerCloth.style = "58700";
                    myCharacter.description.advance.clothing.gloves.style = "60384";
                    myCharacter.description.advance.clothing.shoes.style = "58696";
                }
            });
            // 添加一个按键方法:按下键盘“3”，同步角色外观
            InputUtil.onKeyDown(Keys.Three, () => {
                myCharacter.syncDescription();
            });
            // 添加一个按键方法:按下键盘“4”，清空角色外观
            InputUtil.onKeyDown(Keys.Four, () => {
                myCharacter.clearDescription();
            });
        }
    }
}
```

___

### onEmergeFromWater <Score text="onEmergeFromWater" /> 

• **onEmergeFromWater**: [`MulticastDelegate`](mw.MulticastDelegate.md)<() => `void`\> 

角色向上游泳到达游泳区域水面时，调用委托

::: warning Precautions

当角色对象向上游泳到达游泳区域水面时执行绑定函数

:::

<span style="font-size: 14px;">
使用示例: 如下代码将实现出水面后自动跳跃的功能
</span>

```ts
@Component
export default class Example_Character extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端玩家
            let myPlayer = Player.localPlayer;
            // 获取玩家控制角色
            let myCharacter = myPlayer.character;
            // 给【角色到达游泳区域水面】委托添加函数
            myCharacter.onDescriptionComplete.add(() => {
                // 跳跃
                myCharacter.changeState(CharacterStateType.Jumping);
                }
            });
        }
    }
}
```

___

### onLoadDescriptionFailed <Score text="onLoadDescriptionFailed" /> 

• **onLoadDescriptionFailed**: [`MulticastDelegate`](mw.MulticastDelegate.md)<[`OnLoadDescriptionFailed`](../modules/Core.mw.md#onloaddescriptionfailed)\> 

外观主体（前发，后发，头，上衣，下衣，手套，鞋）加载失败委托

::: warning Precautions

当角色外观加载失败时执行绑定函数

:::

___

### onStateChanged <Score text="onStateChanged" /> 

• **onStateChanged**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`prevState`: [`CharacterStateType`](../enums/mw.CharacterStateType.md), `currentState`: [`CharacterStateType`](../enums/mw.CharacterStateType.md)) => `void`\>

角色状态改变回调
<span style="font-size: 14px;">
使用示例:按0-9，Z、X、C、V后查看打印
</span>

```ts
@Component
export default class NewScript1 extends Script {
    private character: Character;
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        Player.asyncGetLocalPlayer().then((player) => {
            this.character = player.character;
            this.character.onStateChanged.add((pre, curr)=>{
                console.log(`pre: ${pre} curr: ${curr}`);

            })
        });
      InputUtil.onKeyDown(Keys.Zero, ()=>{
            this.character.changeState(CharacterStateType.None);
        })
        InputUtil.onKeyDown(Keys.One, ()=>{
            this.character.changeState(CharacterStateType.Running);
        })
        InputUtil.onKeyDown(Keys.Two, ()=>{
            this.character.changeState(CharacterStateType.Flying);
        })
        InputUtil.onKeyDown(Keys.Three, ()=>{
            this.character.changeState(CharacterStateType.Swimming);
        })
        InputUtil.onKeyDown(Keys.Four, ()=>{
            this.character.changeState(CharacterStateType.Jumping);
        })
        InputUtil.onKeyDown(Keys.Five, ()=>{
            this.character.changeState(CharacterStateType.Freefall);
        })
        InputUtil.onKeyDown(Keys.Six, ()=>{
            this.character.changeState(CharacterStateType.Ragdoll);
        })
        InputUtil.onKeyDown(Keys.Seven, ()=>{
            this.character.changeState(CharacterStateType.GettingUp);
        })
        InputUtil.onKeyDown(Keys.Eight, ()=>{
            this.character.changeState(CharacterStateType.Climbing);
        })
        InputUtil.onKeyDown(Keys.Nine, ()=>{
            this.character.changeState(CharacterStateType.Crouching);
        })
        InputUtil.onKeyDown(Keys.Z, ()=>{
            this.character.changeState(CharacterStateType.Pushed);
        })
        InputUtil.onKeyDown(Keys.X, ()=>{
            this.character.changeState(CharacterStateType.Landed);
        })
        InputUtil.onKeyDown(Keys.C, ()=>{
            this.character.changeState(CharacterStateType.Hit);
        })
        InputUtil.onKeyDown(Keys.V, ()=>{
            this.character.changeState(CharacterStateType.Dead);
        })
      InputUtil.onKeyDown(Keys.E, ()=>{
          console.log("currentState=="+this.character.getCurrentState());
        })
      InputUtil.onKeyDown(Keys.R, ()=>{
          this.character.setStateEnabled(CharacterStateType.Flying, false);
        })
    }
}
```

___

### onSweepCollision <Score text="onSweepCollision" /> 

• **onSweepCollision**: [`MulticastDelegate`](mw.MulticastDelegate.md)<(`velocities`: [`Vector`](mw.Vector.md)[], `hitActors`: [`GameObject`](mw.GameObject.md)[], `impactPoints`: [`Vector`](mw.Vector.md)[], `impactNormals`: [`Vector`](mw.Vector.md)[]) => `void`\>

角色开启强制位移后，移动中碰撞检测结果的代理

## Accessors

___

### brakingDecelerationFlying <Score text="brakingDecelerationFlying" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **brakingDecelerationFlying**(): `number` 

</th>
<th style="text-align: left">

• `set` **brakingDecelerationFlying**(`InBrakingDecelerationFlying`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色的飞行制动速率


#### Returns

| `number` | 制动速率。<br> 默认值为2048。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色飞行制动速率。角色在空中飞行时减速且不施加加速度。

#### Parameters

| `InBrakingDecelerationFlying` `number` | 制动速率。 <br> range: (0,+∞) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"53011,20307"拖入优先加载栏。创建一个名为"Example_BrakingDecelerationFlying"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“1”，角色切换为飞行，按下键盘“2”，角色进行喷射加速，修改飞行制动速度。你将在场景中看到角色在加速飞行过程中飞行制动速度变化的效果。代码如下：
</span>

```ts
@Component
export default class Example_BrakingDecelerationFlying extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 加载喷射加速动画
            let boostAnimation = myCharacter.loadAnimation("53011");
            boostAnimation.loop = 0;
            let isBoost = false
            // 加载上升姿态
            let boostStance = myCharacter.loadSubStance("20307");
            // 添加一个按键方法:键盘“1”，角色切换为飞行
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.switchToFlying();
            });
            // 添加一个按键方法:按下键盘“2”，角色进行喷射加速
            InputUtil.onKeyDown(Keys.Two, () => {
                if(isBoost) return;
                let boost_interval = 0;
                if(myCharacter.isMoving) {
                    // 播放飞行动画，修改飞行速度和制动速度
                    boostAnimation.play();
                    myCharacter.maxFlySpeed = 2000;
                    myCharacter.brakingDecelerationFlying = 5000;
                    // 设置加速周期，每帧检查角色是否移动，当角色停止移动时,执行停止加速操作:停止动画清除姿态，还原飞行速度，清除加速周期
                    boost_interval = setInterval(() => {
                        if(!myCharacter.isMoving) {
                            isBoost = false;
                            clearInterval(boost_interval);
                            myCharacter.maxFlySpeed = 500;
                            boostAnimation.stop();
                            boostStance.stop();
                        }
                    }, 1);
                // 如果当前角色静止，修改角色为上升姿态，设置加速周期，每帧上升5个单位
                } else {
                    boostStance.play();
                    boost_interval = setInterval(() => {
                        myCharacter.addMovement(new Vector(0, 0, 5));
                    }, 1);
                }
                // 2秒后执行停止加速操作
                    setTimeout(() => {
                        isBoost = false;
                        clearInterval(boost_interval);
                        myCharacter.maxFlySpeed = 500;
                        boostAnimation.stop();
                        boostStance.stop();
                    }, 2000);
                    // 2.2秒后还原角色飞行制动速度
                    setTimeout(() => {
                        myCharacter.brakingDecelerationFlying = 300;
                    }, 2200);
            });
        }
    }
}
```
___

### brakingDecelerationSwimming <Score text="brakingDecelerationSwimming" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **brakingDecelerationSwimming**(): `number` 

</th>
<th style="text-align: left">

• `set` **brakingDecelerationSwimming**(`InBrakingDecelerationSwimming`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色游泳制动速率。角色在游泳状态下移动时受到的减速度。


#### Returns

| `number` | 制动速率。<br> 默认值为2048。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色游泳制动速率

#### Parameters

| `InBrakingDecelerationSwimming` `number` |  制动速率。 <br> range: (0,+∞) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"53011,20307"拖入优先加载栏。创建一个名为"Example_BrakingDecelerationSwimming"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中生成拱形容器并适配游泳区域。按下键盘“1”，角色切换游泳。按下键盘“4”，角色修改游泳制动速度后进行喷射加速。你可以看到的角色游泳制动速度变化的效果。代码如下：
</span>

```ts
@Component
export default class Example_BrakingDecelerationSwimming extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在服务端执行
        if(SystemUtil.isServer()) {
            // 生成拱形容器并适配游泳区域
            GameObject.spawn("WaterVolume",{transform: new Transform(new Vector(0, 0, 500), new Rotation(0, 0, 90), new Vector(20, 20, 10))});
        }
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            let flag = true;
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 设置游泳属性
            myCharacter.canJumpOutOfWater = true;
            myCharacter.outOfWaterVerticalSpeed = 100;
            // 加载加速动画
            let boostAnimation = myCharacter.loadAnimation("53011");
            boostAnimation.loop = 10;
            let isBoost = false
            // 加载上升姿态
            let boostStance = myCharacter.loadSubStance("20307");
            // 添加一个按键方法:按下键盘“1”，角色切换游泳 / 行走
            InputUtil.onKeyDown(Keys.One, () => {
                if(flag) {
                    myCharacter.switchToWalking();
                } else {
                    myCharacter.switchToSwimming();
                }
                flag = !flag;
            });
            // 添加一个按键方法:按住键盘“2”，角色上浮
            InputUtil.onKeyPress(Keys.Two, () => {
                myCharacter.swimUp(10);
            });
            // 添加一个按键方法:按住键盘“3”，角色下潜
            InputUtil.onKeyPress(Keys.Three, () => {
                myCharacter.swimDown(10);
            });
            // 添加一个按键方法:按下键盘“4”，角色进行喷射加速
            InputUtil.onKeyDown(Keys.Four, () => {
                if(isBoost) return;
                let boost_interval = 0;
                if(myCharacter.isMoving) {
                    // 播放游泳动画，修改游泳速度和制动速度
                    boostAnimation.play();
                    myCharacter.maxSwimSpeed = 600;
                    myCharacter.brakingDecelerationSwimming = 4096;
                    // 设置加速周期，每帧检查角色是否移动，当角色停止移动时,执行停止加速操作:停止动画清除姿态，还原游泳速度，清除加速周期
                    boost_interval = setInterval(() => {
                        if(!myCharacter.isMoving) {
                            isBoost = false;
                            clearInterval(boost_interval);
                            myCharacter.maxSwimSpeed = 300;
                            boostAnimation.stop();
                            boostStance.stop();
                        }
                    }, 1);
                // 如果当前角色静止，修改角色为上升姿态，设置加速周期，每帧上升5个单位
                } else {
                    boostStance.play();
                    boost_interval = setInterval(() => {
                        myCharacter.swimUp(1)
                    }, 1);
                }
                // 1秒后执行停止加速操作
                    setTimeout(() => {
                        isBoost = false;
                        clearInterval(boost_interval);
                        myCharacter.maxSwimSpeed = 300;
                        boostAnimation.stop();
                        boostStance.stop();
                    }, 1000);
                    // 1.2秒后还原角色游泳制动速度
                    setTimeout(() => {
                        myCharacter.brakingDecelerationSwimming = 4096
                    }, 1200);
            });
        }
    }
}
```
___

### brakingDecelerationWalking <Score text="brakingDecelerationWalking" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **brakingDecelerationWalking**(): `number` 

</th>
<th style="text-align: left">

• `set` **brakingDecelerationWalking**(`InBrakingDecelerationWalking`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


设置角色行走制动速率。行走制动速率是指角色在行走状态下的刹车减速度。当角色在行走状态下停止移动或改变方向时，刹车减速度会影响角色减速的速率。较高的值将导致角色更快地减速，而较低的值将导致角色减速得更慢。


#### Returns

| `number` | 行走制动速率。 <br> 默认值为：2048 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色行走制动速率

::: warning Precautions

仅在启用单独制动摩擦 groundFriction 时生效。

:::

#### Parameters

| `InBrakingDecelerationWalking` `number` |  行走制动速率 <br> range: (0,+∞) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"Example_Braking"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将设置角色行走制动速率为原来的0.1，并在场景中看到角色移动加速变快的效果。代码如下：
</span>

```ts
@Component
export default class Example_Braking extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            this.useUpdate = true;
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 最大加速度为原来的0.1倍
            myCharacter.maxAcceleration = 0.1 * myCharacter.maxAcceleration;
            // 最大转向速度为原来的0.5倍
            myCharacter.rotateRate = 0.5 * myCharacter.rotateRate;
            // 最大行走速度为原来的2倍
            myCharacter.maxWalkSpeed = 2 * myCharacter.maxWalkSpeed;
            // 最大加速度为原来的0.1倍
            myCharacter.brakingDecelerationWalking = 0.1 * myCharacter.brakingDecelerationWalking;
            myCharacter.groundFriction = 1;
            // 添加一个按键方法：按下键盘“1”，切换角色摩擦力的来源
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.groundFrictionEnabled = !myCharacter.groundFriction;
            });
        }
    }
    // 周期函数每帧执行，此函数执行需要将this.useUpdate赋值为true，dt是当前帧与上一帧的延迟（秒）
    protected onUpdate(dt: number): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 如果角色正在移动，打印角色的移动速度
            if(myCharacter.isMoving) {
                console.log("当前角色速度：" + myCharacter.velocity);
            }
        }
    }
}
```
___

### canStandOn <Score text="canStandOn" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **canStandOn**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **canStandOn**(`CanStepUpOn`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色是否可以被其他玩家站立。。true表示其他角色可以站到玩家头上。false表示其他角色不可以站到玩家头上。


#### Returns

| `boolean` | 可否被站立。<br> 默认值为true。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色是否可以被其他玩家站立。

#### Parameters

| `CanStepUpOn` `boolean` |  是否可被站立。 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"36851"拖入优先加载栏。创建一个名为"Example_Character_CanStandOn"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中生成一个NPC。按下键盘“2”，开启/关闭角色是否可被站立。可以看到NPC切换可被站立后与角色不同的交互效果。代码如下：
</span>

```ts
@Component
export default class Example_Character_CanStandOn extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 生成拱门带碰撞的拱门
            let arch = GameObject.spawn("36851",{transform: new Transform(new Vector(300, 210, 0), new Rotation(0, 0, 90), new Vector(2, 1, 2))}) as Model;
            arch.setCollision(CollisionStatus.On);
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 设置角色碰撞属性和跳跃属性
            myCharacter.capsuleCorrectionEnabled = true;
            myCharacter.maxJumpHeight = 250;
            let NPC = Player.spawnDefaultCharacter();
            NPC.worldTransform.position = new Vector(0, 100, 100);
            // 添加一个按键方法：按下键盘“1”，开启/关闭NPC与其他角色的碰撞
            InputUtil.onKeyDown(Keys.One, () => {
                NPC.collisionWithOtherCharacterEnabled = !NPC.collisionWithOtherCharacterEnabled;
                console.log("NPC与角色的碰撞 " + NPC.collisionWithOtherCharacterEnabled);
            });
            // 添加一个按键方法：按下键盘“2”，开启/关闭角色是否可被站立
            InputUtil.onKeyDown(Keys.Two, () => {
                NPC.canStandOn = !NPC.canStandOn;
                console.log("NPC角色可被站立 " + NPC.canStandOn);
            });
            // 添加一个按键方法：按下键盘“3”，修改角色碰撞并打印结果
            InputUtil.onKeyDown(Keys.Three, () => {
                // 碰撞范围collisionExtent内部值全是半值，半径半高半长
                myCharacter.setCollisionShapeAndExtent(CustomShapeType.Box, new Vector(50, 50, 200));
                console.log("当前角色碰撞 " + myCharacter.collisionShape + " " + myCharacter.collisionExtent);
            });
        }
    }
}
```
___

### capsuleCorrectionEnabled <Score text="capsuleCorrectionEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **capsuleCorrectionEnabled**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **capsuleCorrectionEnabled**(`usedCapsuleCorrection`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色当前是否使用胶囊体修正。true代表应用角色编辑中的数据自动计算胶囊体大小。false 代表应用"capsuleHalfHeight"和"capsuleRadius"设置胶囊体的大小。


#### Returns

| `boolean` | 是否使用胶囊体修正。<br> 默认值为true。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色当前是否使用胶囊体修正

#### Parameters

| `usedCapsuleCorrection` `boolean` |  是否使用胶囊体修正。 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"36851"拖入优先加载栏。创建一个名为"Example_Character_CapsuleCorrectionEnabled"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，设置角色碰撞修正为true，代表角色碰撞会和角色外观保持一致。代码如下：
</span>

```ts
@Component
export default class Example_Character_CapsuleCorrectionEnabled extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 生成拱门带碰撞的拱门
            let arch = GameObject.spawn("36851",{transform: new Transform(new Vector(300, 210, 0), new Rotation(0, 0, 90), new Vector(2, 1, 2))}) as Model;
            arch.setCollision(CollisionStatus.On);
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 设置角色碰撞属性和跳跃属性
            myCharacter.capsuleCorrectionEnabled = true;
            myCharacter.maxJumpHeight = 250;
            let NPC = Player.spawnDefaultCharacter();
            NPC.worldTransform.position = new Vector(0, 100, 100);
            // 添加一个按键方法：按下键盘“1”，开启/关闭NPC与其他角色的碰撞
            InputUtil.onKeyDown(Keys.One, () => {
                NPC.collisionWithOtherCharacterEnabled = !NPC.collisionWithOtherCharacterEnabled;
                console.log("NPC与角色的碰撞 " + NPC.collisionWithOtherCharacterEnabled);
            });
            // 添加一个按键方法：按下键盘“2”，开启/关闭角色是否可被站立
            InputUtil.onKeyDown(Keys.Two, () => {
                NPC.canStandOn = !NPC.canStandOn;
                console.log("NPC角色可被站立 " + NPC.canStandOn);
            });
            // 添加一个按键方法：按下键盘“3”，修改角色碰撞并打印结果
            InputUtil.onKeyDown(Keys.Three, () => {
                // 碰撞范围collisionExtent内部值全是半值，半径半高半长
                myCharacter.setCollisionShapeAndExtent(CustomShapeType.Box, new Vector(50, 50, 200));
                console.log("当前角色碰撞 " + myCharacter.collisionShape + " " + myCharacter.collisionExtent);
            });
        }
    }
}
```
___

### characterType <Score text="characterType" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **characterType**(): [`CharacterType`](../enums/mw.CharacterType.md)

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色是什么类型。角色类型分为基础人形、高级人形和四足类型。


#### Returns

| [`CharacterType`](../enums/mw.CharacterType.md) |  |
| :------ | :------ |

</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"14521,35391,161245,75674,57731,63910,58694,58700,60384,58696,136183"拖入优先加载栏。创建一个名为"Example_Character"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中看到玩家控制角色玩家外观准备未完成播放摊手的效果。【角色外观描述完成】委托添加函数来播放换装完成特效，并保存角色初始默认外观数据。【角色外观描述变化】委托添加函数在控制台打印当前角色外观描述变化的具体子项和索引。按下键盘“1”，重置为默认角色外观。按下键盘“2”，修改角色外观。按下键盘“3”，同步角色外观。按下键盘“4”，清空角色外观。代码如下：
</span>

```ts
@Component
export default class Example_Character extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端玩家
            let myPlayer = Player.localPlayer;
            // 获取玩家控制角色
            let myCharacter = myPlayer.character;
            // 如果玩家外观准备完成挥手，反之摊手
            if(myCharacter.isDescriptionReady) {
                let animation = myCharacter.loadAnimation("35391");
                animation.play();
            } else {
                let animation = myCharacter.loadAnimation("14521");
                animation.play();
            }
            let defaultStyle = null;
            // 给【角色外观描述完成】委托添加函数
            myCharacter.onDescriptionComplete.add(() => {
                // 播放换装完成特效
                EffectService.playOnGameObject("161245", myCharacter, {slotType: HumanoidSlotType.Root});
                // 获取角色默认外观风格
                if(defaultStyle == null) {
                    defaultStyle = myCharacter.getDescription();
                }
            });
            // 给【角色外观描述变化】委托添加函数
            myCharacter.onDescriptionChange.add((operationCode: number, index: number, value: unknown) => {
                console.log("Appearance Changed");
                console.log("OperationCode " + operationCode + " Index " + index);
            });
            // 添加一个按键方法:按下键盘“1”，重置为默认角色外观
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.setDescription(defaultStyle);
            });
            // 添加一个按键方法:按下键盘“2”，修改角色外观
            InputUtil.onKeyDown(Keys.Two, () => {
                if(myCharacter.characterType == CharacterType.HumanoidV2) {
                    // 修改角色style头部:头大小为1.5倍
                    myCharacter.description.advance.headFeatures.head.headOverallScale = 1.5;
                    // 修改角色style体型:身高为1.2倍
                    myCharacter.description.advance.bodyFeatures.body.height = 1.2;
                    // 修改角色style化妆:腮红为75674
                    myCharacter.description.advance.makeup.blush.blushStyle = "75674";
                    // 修改角色style头发:前发为57731，后发为63910
                    myCharacter.description.advance.hair.frontHair.style = "57731";
                    myCharacter.description.advance.hair.backHair.style = "63910";
                    // 修改角色style:上衣为58694，下衣为58700，手套为60384，鞋子为58696
                    myCharacter.description.advance.clothing.upperCloth.style = "58694";
                    myCharacter.description.advance.clothing.lowerCloth.style = "58700";
                    myCharacter.description.advance.clothing.gloves.style = "60384";
                    myCharacter.description.advance.clothing.shoes.style = "58696";
                }
            });
            // 添加一个按键方法:按下键盘“3”，同步角色外观
            InputUtil.onKeyDown(Keys.Three, () => {
                myCharacter.syncDescription();
            });
            // 添加一个按键方法:按下键盘“4”，清空角色外观
            InputUtil.onKeyDown(Keys.Four, () => {
                myCharacter.clearDescription();
            });
        }
    }
}
```
___

### collisionExtent <Score text="collisionExtent" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **collisionExtent**(): [`Vector`](mw.Vector.md) 

</th>
<th style="text-align: left">

• `set` **collisionExtent**(`extent`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取包裹角色碰撞体的形状大小。角色碰撞盒形状的大小，决定角色与场景对象交互时检测碰撞范围的大小。


#### Returns

| [`Vector`](mw.Vector.md) | 形状大小。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置包裹角色碰撞体的形状大小

#### Parameters

| `extent` [`Vector`](mw.Vector.md) |  形状大小。 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"36851"拖入优先加载栏。创建一个名为"Example_Character_CollisionExtent"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“3”，修改角色碰撞并打印结果。你将在控制台中看到打印的当前角色碰撞形状大小。代码如下：
</span>

```ts
@Component
export default class Example_Character_CollisionExtent extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 生成拱门带碰撞的拱门
            let arch = GameObject.spawn("36851",{transform: new Transform(new Vector(300, 210, 0), new Rotation(0, 0, 90), new Vector(2, 1, 2))}) as Model;
            arch.setCollision(CollisionStatus.On);
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 设置角色碰撞属性和跳跃属性
            myCharacter.capsuleCorrectionEnabled = true;
            myCharacter.maxJumpHeight = 250;
            let NPC = Player.spawnDefaultCharacter();
            NPC.worldTransform.position = new Vector(0, 100, 100);
            // 添加一个按键方法：按下键盘“1”，开启/关闭NPC与其他角色的碰撞
            InputUtil.onKeyDown(Keys.One, () => {
                NPC.collisionWithOtherCharacterEnabled = !NPC.collisionWithOtherCharacterEnabled;
                console.log("NPC与角色的碰撞 " + NPC.collisionWithOtherCharacterEnabled);
            });
            // 添加一个按键方法：按下键盘“2”，开启/关闭角色是否可被站立
            InputUtil.onKeyDown(Keys.Two, () => {
                NPC.canStandOn = !NPC.canStandOn;
                console.log("NPC角色可被站立 " + NPC.canStandOn);
            });
            // 添加一个按键方法：按下键盘“3”，修改角色碰撞并打印结果
            InputUtil.onKeyDown(Keys.Three, () => {
                // 碰撞范围collisionExtent内部值全是半值，半径半高半长
                myCharacter.setCollisionShapeAndExtent(CustomShapeType.Box, new Vector(50, 50, 200));
                console.log("当前角色碰撞 " + myCharacter.collisionShape + " " + myCharacter.collisionExtent);
            });
        }
    }
}
```
___

### collisionShape <Score text="collisionShape" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **collisionShape**(): [`CustomShapeType`](../enums/mw.CustomShapeType.md) 

</th>
<th style="text-align: left">

• `set` **collisionShape**(`CustomShapeType`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色碰撞形状（胶囊体型、球型、盒型）。角色碰撞盒形状的大小，决定角色与场景对象交互时检测碰撞范围的大小。球体取xyz最小值，胶囊体半径取xy最小值，z为半长，盒体xyz为半长宽高。


#### Returns

| [`CustomShapeType`](../enums/mw.CustomShapeType.md) | 碰撞形状。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色碰撞形状（胶囊体型、球型、盒型）

#### Parameters

| `CustomShapeType` [`CustomShapeType`](../enums/mw.CustomShapeType.md) |  碰撞形状。 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"36851"拖入优先加载栏。创建一个名为"Example_Character_CollisionShape"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“3”，修改角色碰撞并打印结果。你将在控制台中看到打印的当前角色碰撞形状。代码如下：
</span>

```ts
@Component
export default class Example_Character_CollisionShape extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 生成拱门带碰撞的拱门
            let arch = GameObject.spawn("36851",{transform: new Transform(new Vector(300, 210, 0), new Rotation(0, 0, 90), new Vector(2, 1, 2))}) as Model;
            arch.setCollision(CollisionStatus.On);
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 设置角色碰撞属性和跳跃属性
            myCharacter.capsuleCorrectionEnabled = true;
            myCharacter.maxJumpHeight = 250;
            let NPC = Player.spawnDefaultCharacter();
            NPC.worldTransform.position = new Vector(0, 100, 100);
            // 添加一个按键方法：按下键盘“1”，开启/关闭NPC与其他角色的碰撞
            InputUtil.onKeyDown(Keys.One, () => {
                NPC.collisionWithOtherCharacterEnabled = !NPC.collisionWithOtherCharacterEnabled;
                console.log("NPC与角色的碰撞 " + NPC.collisionWithOtherCharacterEnabled);
            });
            // 添加一个按键方法：按下键盘“2”，开启/关闭角色是否可被站立
            InputUtil.onKeyDown(Keys.Two, () => {
                NPC.canStandOn = !NPC.canStandOn;
                console.log("NPC角色可被站立 " + NPC.canStandOn);
            });
            // 添加一个按键方法：按下键盘“3”，修改角色碰撞并打印结果
            InputUtil.onKeyDown(Keys.Three, () => {
                // 碰撞范围collisionExtent内部值全是半值，半径半高半长
                myCharacter.setCollisionShapeAndExtent(CustomShapeType.Box, new Vector(50, 50, 200));
                console.log("当前角色碰撞 " + myCharacter.collisionShape + " " + myCharacter.collisionExtent);
            });
        }
    }
}
```
___

### collisionWithOtherCharacterEnabled <Score text="collisionWithOtherCharacterEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **collisionWithOtherCharacterEnabled**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **collisionWithOtherCharacterEnabled**(`value`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色当前是否可以与其他角色产生碰撞。

::: warning Precautions

true表示角色可以与其他角色碰撞，false表示角色不能与其他角色产生碰撞。

:::


#### Returns

| `boolean` | 可否产生碰撞。 <br> 默认值为true。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色当前是否可以与其他角色产生碰撞。

#### Parameters

| `value` `boolean` |  可否产生碰撞。 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"36851"拖入优先加载栏。创建一个名为"Example_Character_CollisionWithOtherCharacterEnabled"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中生成一个NPC。按下键盘“1”，开启/关闭NPC与其他角色的碰撞.可以看到NPC关闭碰撞后与角色不同的交互效果。代码如下：
</span>

```ts
@Component
export default class Example_Character_CollisionWithOtherCharacterEnabled extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 生成拱门带碰撞的拱门
            let arch = GameObject.spawn("36851",{transform: new Transform(new Vector(300, 210, 0), new Rotation(0, 0, 90), new Vector(2, 1, 2))}) as Model;
            arch.setCollision(CollisionStatus.On);
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 设置角色碰撞属性和跳跃属性
            myCharacter.capsuleCorrectionEnabled = true;
            myCharacter.maxJumpHeight = 250;
            let NPC = Player.spawnDefaultCharacter();
            NPC.worldTransform.position = new Vector(0, 100, 100);
            // 添加一个按键方法：按下键盘“1”，开启/关闭NPC与其他角色的碰撞
            InputUtil.onKeyDown(Keys.One, () => {
                NPC.collisionWithOtherCharacterEnabled = !NPC.collisionWithOtherCharacterEnabled;
                console.log("NPC与角色的碰撞 " + NPC.collisionWithOtherCharacterEnabled);
            });
            // 添加一个按键方法：按下键盘“2”，开启/关闭角色是否可被站立
            InputUtil.onKeyDown(Keys.Two, () => {
                NPC.canStandOn = !NPC.canStandOn;
                console.log("NPC角色可被站立 " + NPC.canStandOn);
            });
            // 添加一个按键方法：按下键盘“3”，修改角色碰撞并打印结果
            InputUtil.onKeyDown(Keys.Three, () => {
                // 碰撞范围collisionExtent内部值全是半值，半径半高半长
                myCharacter.setCollisionShapeAndExtent(CustomShapeType.Box, new Vector(50, 50, 200));
                console.log("当前角色碰撞 " + myCharacter.collisionShape + " " + myCharacter.collisionExtent);
            });
        }
    }
}
```
___

### complexMovementEnabled <Score text="complexMovementEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **complexMovementEnabled**(): `boolean`

</th>
<th style="text-align: left">

• `set` **complexMovementEnabled**(`inValue`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


是否启用复杂移动策略

#### Returns

| `boolean` | 返回复杂移动策略是否开启布尔值。 |
| :------ | :------ |


</td>
<td style="text-align: left">


是否启用复杂移动策略。当开启复杂移动策略时，会根据当前的移动模式决定应该采取的移动逻辑。它会根据角色的输入、物理属性（如质量、摩擦力等）计算角色在当前帧应该移动的距离和方向。实现了角色的高级移动逻辑和物理模拟，确保角色在游戏世界中按照预期的方式进行移动，并与周围的环境进行交互。

#### Parameters

| `inValue` `boolean` |  ture为开启，false为关闭。 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### crouchedHeight <Score text="crouchedHeight" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **crouchedHeight**(): `number` 

</th>
<th style="text-align: left">

• `set` **crouchedHeight**(`InCrouchedHeight`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色下蹲状态下，碰撞盒的高度。


#### Returns

| `number` | 碰撞盒高度。<br> 默认值为60。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色下蹲状态下，碰撞盒的高度。

#### Parameters

| `InCrouchedHeight` `number` |  碰撞盒高度。 <br> range: (0,+∞) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"54834,36851"拖入优先加载栏。创建一个名为"Example_Character_CrouchedHeight"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中生成草丛和拱门并添加触发器，并添加委托函数实现角色进入草丛蹲下，离开站起的效果。设置下蹲后高度为100。你可以看到角色蹲下后可以穿过之前不能穿过的拱门。代码如下：
</span>

```ts
@Component
export default class Example_Character_CrouchedHeight extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 生成草丛和拱门
            GameObject.spawn("54834",{transform: new Transform(new Vector(300, 0, 0), Rotation.zero, new Vector(2, 2, 2))});
            let arch = GameObject.spawn("36851",{transform: new Transform(new Vector(300, 210, 0), new Rotation(0, 0, 90), new Vector(2, 1, 2))}) as Model;
            arch.setCollision(CollisionStatus.On);
            // 生成触发器并添加委托函数：进入触发器的角色蹲下，离开触发器站起
            let tri = GameObject.spawn("Trigger",{transform: new Transform(new Vector(300, 0, 50), Rotation.zero, new Vector(2, 2, 1))}) as Trigger;
            tri.onEnter.add((character: Character) => {
                character.crouch(true);
                setTimeout(() => {
                    console.log("当前角色下蹲 " + character.isCrouching);
                }, 500);
            });
            tri.onLeave.add((character: Character) => {
                character.crouch(false);
                console.log("当前角色下蹲 " + character.isCrouching);
            });
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 地面蹲伏行走时的最大移动速度100
            myCharacter.maxWalkSpeedCrouched = 100;
            // 下蹲后高度为100
            myCharacter.crouchedHeight = 100;
            // 添加一个按键方法：按下键盘“1”，启用/禁用下蹲能力
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.crouchEnabled = !myCharacter.crouchEnabled;
                console.log("当前角色是否能下蹲 " + myCharacter.crouchEnabled);
            });
        }
    }
}
```
___

### currentAnimation <Score text="currentAnimation" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **currentAnimation**(): [`Animation`](mw.Animation.md)

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


当前播放的动画对象

#### Returns

| [`Animation`](mw.Animation.md) |  |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### currentStance <Score text="currentStance" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **currentStance**(): [`Stance`](mw.Stance.md)

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取当前正在播放的基础姿态


#### Returns

| [`Stance`](mw.Stance.md) | 返回值为当前基础姿态 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 将使用到的资源:"234423,216081"拖入优先加载栏。创建一个名为"Example_Character"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“1”，切换播放二次元男性基础姿态和二次元女性基础姿态。按下键盘“2”，停止播放基础姿态。代码如下：
</span>

```ts
@Component
export default class Example_Character extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端玩家
            let myPlayer = Player.localPlayer;
            // 获取玩家控制角色
            let myCharacter = myPlayer.character;
            // 给角色加载一个二次元男性基础姿态
            let animeManStance = myCharacter.loadStance("234423");
            console.log("animeManStance assetId " + animeManStance.assetId);
            // 给角色加载一个二次元女性基础姿态（默认）,关闭瞄准偏移
            let animeWomanStance = myCharacter.loadStance("216081");
            animeWomanStance.aimOffsetEnabled = false;
            console.log("animeWomanStance assetId " + animeWomanStance.assetId);
            // 添加一个按键方法：按下键盘“1”，切换播放二次元男性基础姿态和二次元女性基础姿态
            InputUtil.onKeyDown(Keys.One, () => {
                if(myCharacter.currentStance == animeWomanStance) {
                    animeManStance.play();
                    // 开启瞄准偏移
                    animeManStance.aimOffsetEnabled = true;
                } else {
                    animeWomanStance.play();
                    // 关闭瞄准偏移
                    animeWomanStance.aimOffsetEnabled = false;
                }
            });
            // 添加一个按键方法：按下键盘“2”，停止播放基础姿态
            InputUtil.onKeyDown(Keys.Two, () => {
                if(myCharacter.currentStance) {
                    myCharacter.currentStance.stop();
                }
            });
        }
    }
}
```
___

### currentSubStance <Score text="currentSubStance" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **currentSubStance**(): [`SubStance`](mw.SubStance.md)

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取当前正在播放的二级姿态，二级姿态类型为SubStance


#### Returns

| [`SubStance`](mw.SubStance.md) | 返回一个二级姿态类型 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"94261,14520"拖入优先加载栏。创建一个名为"Example_Character"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，在玩家角色上加载一个仅上半身的瞄准姿态和一个仅下半身的踢腿姿态。按下键盘“1”，切换播放瞄准姿态和踢腿姿态。按下键盘“2”，停止播放姿态。代码如下：
</span>

```ts
@Component
export default class Example_Character extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端玩家
            let myPlayer = Player.localPlayer;
            // 获取玩家控制角色
            let myCharacter = myPlayer.character;
            // 给角色加载仅上半身瞄准姿态
            let aimStance = myCharacter.loadSubStance("94261");
            aimStance.blendMode = StanceBlendMode.BlendUpper;
            console.log("aimStance assetId " + aimStance.assetId);
            // 给角色加载仅下半身踢腿姿态
            let kickStance = myCharacter.loadSubStance("14520");
            kickStance.blendMode = StanceBlendMode.BlendLower;
            console.log("kickStance assetId " + kickStance.assetId);
            // 添加一个按键方法:按下键盘“1”，切换播放瞄准姿态和踢腿姿态
            InputUtil.onKeyDown(Keys.One, () => {
                if(myCharacter.currentSubStance == aimStance) {
                    kickStance.play();
                } else {
                    aimStance.play();
                }
            });
            // 添加一个按键方法:按下键盘“2”，停止播放姿态
            InputUtil.onKeyDown(Keys.Two, () => {
                if(myCharacter.currentSubStance) {
                    myCharacter.currentSubStance.stop();
                }
            });
        }
    }
}
```
___

### description <Score text="description" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **description**(): [`CharacterDescription`](mw.CharacterDescription.md) 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


角色外观配置。返回值为 CharacterDescription 类。调用 description 变量可以修改角色的外观，可更改角色的外观参数详见 CharacterDescription 类。


#### Returns

| [`CharacterDescription`](mw.CharacterDescription.md) | 返回值为 CharacterDescription 类型对象。 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"14521,35391,161245,75674,57731,63910,58694,58700,60384,58696,136183"拖入优先加载栏。创建一个名为"Example_Character"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中看到玩家控制角色玩家外观准备未完成播放摊手的效果。【角色外观描述完成】委托添加函数来播放换装完成特效，并保存角色初始默认外观数据。【角色外观描述变化】委托添加函数在控制台打印当前角色外观描述变化的具体子项和索引。按下键盘“1”，重置为默认角色外观。按下键盘“2”，修改角色外观。按下键盘“3”，同步角色外观。按下键盘“4”，清空角色外观。代码如下：
</span>

```ts
@Component
export default class Example_Character extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端玩家
            let myPlayer = Player.localPlayer;
            // 获取玩家控制角色
            let myCharacter = myPlayer.character;
            // 如果玩家外观准备完成挥手，反之摊手
            if(myCharacter.isDescriptionReady) {
                let animation = myCharacter.loadAnimation("35391");
                animation.play();
            } else {
                let animation = myCharacter.loadAnimation("14521");
                animation.play();
            }
            let defaultStyle = null;
            // 给【角色外观描述完成】委托添加函数
            myCharacter.onDescriptionComplete.add(() => {
                // 播放换装完成特效
                EffectService.playOnGameObject("161245", myCharacter, {slotType: HumanoidSlotType.Root});
                // 获取角色默认外观风格
                if(defaultStyle == null) {
                    defaultStyle = myCharacter.getDescription();
                }
            });
            // 给【角色外观描述变化】委托添加函数
            myCharacter.onDescriptionChange.add((operationCode: number, index: number, value: unknown) => {
                console.log("Appearance Changed");
                console.log("OperationCode " + operationCode + " Index " + index);
            });
            // 添加一个按键方法:按下键盘“1”，重置为默认角色外观
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.setDescription(defaultStyle);
            });
            // 添加一个按键方法:按下键盘“2”，修改角色外观
            InputUtil.onKeyDown(Keys.Two, () => {
                if(myCharacter.characterType == CharacterType.HumanoidV2) {
                    // 头部:头大小为1.5倍
                    myCharacter.description.advance.headFeatures.head.headOverallScale = 1.5;
                    // 体型:身高为1.2倍
                    myCharacter.description.advance.bodyFeatures.body.height = 1.2;
                    // 化妆:腮红为75674
                    myCharacter.description.advance.makeup.blush.blushStyle = "75674";
                    // 头发:前发为57731，后发为63910
                    myCharacter.description.advance.hair.frontHair.style = "57731";
                    myCharacter.description.advance.hair.backHair.style = "63910";
                    // 上衣为58694，下衣为58700，手套为60384，鞋子为58696
                    myCharacter.description.advance.clothing.upperCloth.style = "58694";
                    myCharacter.description.advance.clothing.lowerCloth.style = "58700";
                    myCharacter.description.advance.clothing.gloves.style = "60384";
                    myCharacter.description.advance.clothing.shoes.style = "58696";
                }
            });
            // 添加一个按键方法:按下键盘“3”，同步角色外观
            InputUtil.onKeyDown(Keys.Three, () => {
                myCharacter.syncDescription();
            });
            // 添加一个按键方法:按下键盘“4”，清空角色外观
            InputUtil.onKeyDown(Keys.Four, () => {
                myCharacter.clearDescription();
            });
        }
    }
}
```
___

### displayName <Score text="displayName" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **displayName**(): `string`

</th>
<th style="text-align: left">

• `set` **displayName**(`inName`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色名称。角色名称默认会显示在角色头顶上方。


#### Returns

| `string` | 角色名称字符串 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色名称。名字为随机初始化的一个英文名，可根据自己的喜好随意更换角色名字。

#### Parameters

| `inName` `string` |  想要更改的角色名称 range:设置合理的名称即可 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例: 创建一个名为"Example_Character"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“1”，场景中角色显示的名称发生了变化。代码如下：
</span>

```ts
@Component
export default class Example_Character extends Script {
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            let names = ["Cali", "Lily", "Emmie"];
            let index = 0;
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 打印本地玩家控制的character对象的guid和名字
            console.log("My character: " + myPlayer.character.gameObjectId + " " + myPlayer.character.displayName);
            // 添加一个按键方法：按下键盘“1”，切换角色显示名称
            InputUtil.onKeyDown(Keys.One, () => {
                myPlayer.character.displayName = names[index % 3];
                index++;
            });
        }
    }
}
```
___

### driftControl <Score text="driftControl" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **driftControl**(): `number` 

</th>
<th style="text-align: left">

• `set` **driftControl**(`InAirControl`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色在空中的灵活度。角色在空中时, 控制水平方向移动的灵活度；范围:0~1, 0表示不能控制, 1表示能按地面最大移动速率完全控制


#### Returns

| `number` | 空中灵活度。<br> 默认值为0.2。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色在空中的灵活度

#### Parameters

| `InAirControl` `number` |  制动速率。 <br> range: [0,1] |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"Example_DriftControl"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将设置角色空中控制系数为0.1。按下键盘“1”，角色设置跳跃高度为1000后跳跃，你可以在场景中看到超过下落速度阈值后空中角色难以控制的效果。代码如下：
</span>

```ts
@Component
export default class Example_DriftControl extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 最大下落速度为1024
            myCharacter.maxFallingSpeed = 1024;
            // 下落制动速率为10
            myCharacter.horizontalBrakingDecelerationFalling = 10;
            // 按地面移动速率的0.1倍控制下落过程
            myCharacter.driftControl = 0.1;
            // 10倍重力
            myCharacter.gravityScale = 10;
            // 添加一个按键方法：按下键盘“1”，角色设置跳跃高度为1000后跳跃。
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.maxJumpHeight = 1000;
                myCharacter.jump();
            });
        }
    }
}
```
___

### forceUpdateMovement <Score text="forceUpdateMovement" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `set` **forceUpdateMovement**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


强制更新移动

::: warning Precautions

角色当前是否启用强制更新移动，true表示角色会因碰撞被动位移，false表示角色不会因碰撞被动位移。

:::


#### Parameters

| `value` `boolean` |  true为开启，false为关闭强制更新移动。<br> 默认为true |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"197386"拖入优先加载栏。创建一个名为"Example_Character"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏你将在场景中生成一个立方体，并在 onUpdate 里左右移动，按下键盘“1”，启用/禁用角色【强制更新移动】，看到立方体对角色的推动效果。代码如下：
</span>

```ts
@Component
export default class Example_Character extends Script {
    // 声明变量
    cube: GameObject;
    stride: Vector;
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在服务端执行
        if(SystemUtil.isServer()) {
            this.useUpdate = true;
            // 移动步长：Y轴单位距离
            this.stride = new Vector(-2, 0, 0);
            // 在前方生成一个立方体，并在onUpdate里左右移动
            let spawnTransform = new Transform(new Vector(300, 0, 0), Rotation.zero, Vector.one);
            this.cube = GameObject.spawn("197386",{transform: spawnTransform});
        }
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 添加一个按键方法：按下键盘“1”，启用/禁用【强制更新移动】
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.forceUpdateMovement = !myCharacter.forceUpdateMovement;
                console.log("当前角色是否强制更新移动: "+ myCharacter.forceUpdateMovement);
            });
        }
    }
    // 周期函数每帧执行，此函数执行需要将this.useUpdate赋值为true，dt是当前帧与上一帧的延迟（秒）
    protected onUpdate(dt: number): void {
        // 下列代码仅在服务端执行
        if(SystemUtil.isServer()) {
            // 当立方体不为空时按步长每帧更新立方体世界坐标（左右移动）
            if(this.cube) {
                this.cube.worldTransform.position = this.cube.worldTransform.position.add(this.stride);
                // 当立方体y轴世界坐标绝对值超过1000时，步长取反
                if(Math.abs(this.cube.worldTransform.position.x) > 500) {
                    this.stride.multiply(-1);
                }
            }
        }
    }
}
```
___

### gravityScale <Score text="gravityScale" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **gravityScale**(): `number` 

</th>
<th style="text-align: left">

• `set` **gravityScale**(`newGravityScale`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取重力的倍率。对于角色来说，重力会乘以该值。范围0~10, 过大和过小的值都会被限制。


#### Returns

| `number` | 倍率。<br> 默认值为1.0。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置重力的倍率

#### Parameters

| `newGravityScale` `number` |  制动速率。 <br> range: (0,10] |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"Example_Character_GravityScale"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将设置角色重力倍率为10。按下键盘“1”，角色设置跳跃高度为1000后跳跃，你可以在场景中看到十倍重力下角色下落的效果。代码如下：
</span>

```ts
@Component
export default class Example_Character_GravityScale extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 最大下落速度为1024
            myCharacter.maxFallingSpeed = 1024;
            // 下落制动速率为10
            myCharacter.horizontalBrakingDecelerationFalling = 10;
            // 按地面移动速率的0.1倍控制下落过程
            myCharacter.driftControl = 0.1;
            // 10倍重力
            myCharacter.gravityScale = 10;
            // 添加一个按键方法：按下键盘“1”，角色设置跳跃高度为1000后跳跃。
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.maxJumpHeight = 1000;
                myCharacter.jump();
            });
        }
    }
}
```
___

### groundFriction <Score text="groundFriction" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **groundFriction**(): `number` 

</th>
<th style="text-align: left">

• `set` **groundFriction**(`inGroundFriction`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取地面摩檫力


#### Returns

| `number` | 摩擦力。<br> 默认值为 8。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置地面摩檫力

::: warning Precautions

角色在地面上受到的摩擦力大小。在开启单独制动摩擦 groundFriction 时该值不生效。

:::

#### Parameters

| `inGroundFriction` | `number` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"Example_GroundFriction"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将设置角色地面摩擦力为1，按下键盘“1”，切换角色摩擦力的来源。并在场景中看到角色移动加速变快的效果。代码如下：
</span>

```ts
@Component
export default class Example_GroundFriction extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            this.useUpdate = true;
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 最大加速度为原来的0.1倍
            myCharacter.maxAcceleration = 0.1 * myCharacter.maxAcceleration;
            // 最大转向速度为原来的0.5倍
            myCharacter.rotateRate = 0.5 * myCharacter.rotateRate;
            // 最大行走速度为原来的2倍
            myCharacter.maxWalkSpeed = 2 * myCharacter.maxWalkSpeed;
            // 行走制动速率为原来的0.1倍
            myCharacter.brakingDecelerationWalking = 0.1 * myCharacter.brakingDecelerationWalking;
            myCharacter.groundFriction = 1;
            // 添加一个按键方法:按下键盘“1”，启用/禁用地面摩擦力
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.groundFrictionEnabled = !myCharacter.groundFriction;
            });
        }
    }
    // 周期函数每帧执行，此函数执行需要将this.useUpdate赋值为true，dt是当前帧与上一帧的延迟（秒）
    protected onUpdate(dt: number): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 如果角色正在移动，打印角色的移动速度
            if(myCharacter.isMoving) {
                console.log("当前角色速度:" + myCharacter.velocity);
            }
        }
    }
}
```
___

### groundFrictionEnabled <Score text="groundFrictionEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **groundFrictionEnabled**(): `boolean` 

</th>
<th style="text-align: left">

• `set` **groundFrictionEnabled**(`used`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取单独制动摩擦状态。开启后使用行走制动速率进行计算摩擦效果，不开启则使用的是地面摩擦力进行计算摩擦效果。


#### Returns

| `boolean` | 是否开启制动摩擦，true 为开启，false 为关闭。<br> 默认值为 false。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置单独制动摩擦状态。当角色处于运动状态，制动摩擦用于让角色去停止移动（当没有加速时）。

#### Parameters

| `used` `boolean` |  制动摩擦。 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"Example_GroundFriction"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“1”，切换角色摩擦力的来源。并在场景中看到角色移动加速变化的效果。代码如下：
</span>

```ts
@Component
export default class Example_GroundFriction extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            this.useUpdate = true;
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 最大加速度为原来的0.1倍
            myCharacter.maxAcceleration = 0.1 * myCharacter.maxAcceleration;
            // 最大转向速度为原来的0.5倍
            myCharacter.rotateRate = 0.5 * myCharacter.rotateRate;
            // 最大行走速度为原来的2倍
            myCharacter.maxWalkSpeed = 2 * myCharacter.maxWalkSpeed;
            // 行走制动速率为原来的0.1倍
            myCharacter.brakingDecelerationWalking = 0.1 * myCharacter.brakingDecelerationWalking;
            myCharacter.groundFriction = 1;
            // 添加一个按键方法:按下键盘“1”，启用/禁用地面摩擦力
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.groundFrictionEnabled = !myCharacter.groundFriction;
            });
        }
    }
    // 周期函数每帧执行，此函数执行需要将this.useUpdate赋值为true，dt是当前帧与上一帧的延迟（秒）
    protected onUpdate(dt: number): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 如果角色正在移动，打印角色的移动速度
            if(myCharacter.isMoving) {
                console.log("当前角色速度:" + myCharacter.velocity);
            }
        }
    }
}
```
___

### horizontalBrakingDecelerationFalling <Score text="horizontalBrakingDecelerationFalling" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **horizontalBrakingDecelerationFalling**(): `number` 

</th>
<th style="text-align: left">

• `set` **horizontalBrakingDecelerationFalling**(`InBrakingDecelerationFalling`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色下落制动速率。角色在下落状态下移动时受到的减速度。


#### Returns

| `number` | 制动速率。<br> 默认值为500。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色下落制动速率

#### Parameters

| `InBrakingDecelerationFalling` `number` |  制动速率。 <br> range: (0,+∞) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"Example_HorizontalBrakingDecelerationFalling"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将设置角色下落制动速度为10。按下键盘“1”，角色设置跳跃高度为1000后跳跃，你可以在场景中看到比正常更慢的下落加速的效果。代码如下：
</span>

```ts
@Component
export default class Example_HorizontalBrakingDecelerationFalling extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 最大下落速度为1024
            myCharacter.maxFallingSpeed = 1024;
            // 下落制动速率为10
            myCharacter.horizontalBrakingDecelerationFalling = 10;
            // 按地面移动速率的0.1倍控制下落过程
            myCharacter.driftControl = 0.1;
            // 10倍重力
            myCharacter.gravityScale = 10;
            // 添加一个按键方法：按下键盘“1”，角色设置跳跃高度为1000后跳跃。
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.maxJumpHeight = 1000;
                myCharacter.jump();
            });
        }
    }
}
```
___

### isCrouching <Score text="isCrouching" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **isCrouching**(): `boolean` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色是否正在蹲下


#### Returns

| `boolean` | 下蹲状态。 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"54834,36851"拖入优先加载栏。创建一个名为"Example_Character_IsCrouching"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中生成草丛和拱门并添加触发器。看到角色进入草丛蹲下，离开站起的效果，并在控制台看到打印的角色当前的蹲起状态。代码如下：
</span>

```ts
@Component
export default class Example_Character_IsCrouching extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 生成草丛和拱门
            GameObject.spawn("54834",{transform: new Transform(new Vector(300, 0, 0), Rotation.zero, new Vector(2, 2, 2))});
            let arch = GameObject.spawn("36851",{transform: new Transform(new Vector(300, 210, 0), new Rotation(0, 0, 90), new Vector(2, 1, 2))}) as Model;
            arch.setCollision(CollisionStatus.On);
            // 生成触发器并添加委托函数：进入触发器的角色蹲下，离开触发器站起
            let tri = GameObject.spawn("Trigger",{transform: new Transform(new Vector(300, 0, 50), Rotation.zero, new Vector(2, 2, 1))}) as Trigger;
            tri.onEnter.add((character: Character) => {
                character.crouch(true);
                setTimeout(() => {
                    console.log("当前角色下蹲 " + character.isCrouching);
                }, 500);
            });
            tri.onLeave.add((character: Character) => {
                character.crouch(false);
                console.log("当前角色下蹲 " + character.isCrouching);
            });
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 地面蹲伏行走时的最大移动速度100
            myCharacter.maxWalkSpeedCrouched = 100;
            // 下蹲后高度为100
            myCharacter.crouchedHeight = 100;
            // 添加一个按键方法：按下键盘“1”，启用/禁用下蹲能力
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.crouchEnabled = !myCharacter.crouchEnabled;
                console.log("当前角色是否能下蹲 " + myCharacter.crouchEnabled);
            });
        }
    }
}
```
___

### isDescriptionReady <Score text="isDescriptionReady" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **isDescriptionReady**(): `boolean` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取当前角色外观是否准备完毕。刚进入场景中或角色还未加载出外观衣服等时，isDescriptionReady为false，完全加载完成后变为true。


#### Returns

| `boolean` | true表示准备完毕，false表示未准备好。 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"14521,35391,161245,75674,57731,63910,58694,58700,60384,58696,136183"拖入优先加载栏。创建一个名为"Example_Character"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中看到玩家控制角色玩家外观准备未完成播放摊手的效果。【角色外观描述完成】委托添加函数来播放换装完成特效，并保存角色初始默认外观数据。【角色外观描述变化】委托添加函数在控制台打印当前角色外观描述变化的具体子项和索引。按下键盘“1”，重置为默认角色外观。按下键盘“2”，修改角色外观。按下键盘“3”，同步角色外观。按下键盘“4”，清空角色外观。代码如下：
</span>

```ts
@Component
export default class Example_Character extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端玩家
            let myPlayer = Player.localPlayer;
            // 获取玩家控制角色
            let myCharacter = myPlayer.character;
            // 如果玩家外观准备完成挥手，反之摊手
            if(myCharacter.isDescriptionReady) {
                let animation = myCharacter.loadAnimation("35391");
                animation.play();
            } else {
                let animation = myCharacter.loadAnimation("14521");
                animation.play();
            }
            let defaultStyle = null;
            // 给【角色外观描述完成】委托添加函数
            myCharacter.onDescriptionComplete.add(() => {
                // 播放换装完成特效
                EffectService.playOnGameObject("161245", myCharacter, {slotType: HumanoidSlotType.Root});
                // 获取角色默认外观风格
                if(defaultStyle == null) {
                    defaultStyle = myCharacter.getDescription();
                }
            });
            // 给【角色外观描述变化】委托添加函数
            myCharacter.onDescriptionChange.add((operationCode: number, index: number, value: unknown) => {
                console.log("Appearance Changed");
                console.log("OperationCode " + operationCode + " Index " + index);
            });
            // 添加一个按键方法:按下键盘“1”，重置为默认角色外观
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.setDescription(defaultStyle);
            });
            // 添加一个按键方法:按下键盘“2”，修改角色外观
            InputUtil.onKeyDown(Keys.Two, () => {
                if(myCharacter.characterType == CharacterType.HumanoidV2) {
                    // 修改角色style头部:头大小为1.5倍
                    myCharacter.description.advance.headFeatures.head.headOverallScale = 1.5;
                    // 修改角色style体型:身高为1.2倍
                    myCharacter.description.advance.bodyFeatures.body.height = 1.2;
                    // 修改角色style化妆:腮红为75674
                    myCharacter.description.advance.makeup.blush.blushStyle = "75674";
                    // 修改角色style头发:前发为57731，后发为63910
                    myCharacter.description.advance.hair.frontHair.style = "57731";
                    myCharacter.description.advance.hair.backHair.style = "63910";
                    // 修改角色style:上衣为58694，下衣为58700，手套为60384，鞋子为58696
                    myCharacter.description.advance.clothing.upperCloth.style = "58694";
                    myCharacter.description.advance.clothing.lowerCloth.style = "58700";
                    myCharacter.description.advance.clothing.gloves.style = "60384";
                    myCharacter.description.advance.clothing.shoes.style = "58696";
                }
            });
            // 添加一个按键方法:按下键盘“3”，同步角色外观
            InputUtil.onKeyDown(Keys.Three, () => {
                myCharacter.syncDescription();
            });
            // 添加一个按键方法:按下键盘“4”，清空角色外观
            InputUtil.onKeyDown(Keys.Four, () => {
                myCharacter.clearDescription();
            });
        }
    }
}
```
___

### isJumping <Score text="isJumping" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **isJumping**(): `boolean` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色是否正在跳跃


#### Returns

| `boolean` | 跳跃状态。true表示正在跳跃，false表示不在跳跃。 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"Example_Character_IsJumping"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，设置角色最大跳跃高度为300，最高三连跳。按下键盘“1”，角色跳跃。按下键盘“2”，启用/禁用跳跃能力。你将在场景中看到角色禁用跳跃能力的效果。代码如下：
</span>

```ts
@Component
export default class Example_Character_IsJumping extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 最大跳跃高度为300
            myCharacter.maxJumpHeight = 300;
            // 最高三连跳
            myCharacter.jumpMaxCount = 3;
            // 添加一个按键方法:按下键盘“1”，角色跳跃。
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.jump();
                console.log("当前角色是否在跳跃 " + myCharacter.isJumping);
            });
            // 添加一个按键方法:按下键盘“2”，启用/禁用跳跃能力。
            InputUtil.onKeyDown(Keys.Two, () => {
                myCharacter.jumpEnabled = !myCharacter.jumpEnabled;
                console.log("当前角色跳跃能力 " + myCharacter.jumpEnabled);
            });
        }
    }
}
```
___

### isMoving <Score text="isMoving" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **isMoving**(): `boolean` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色是否正在移动


#### Returns

| `boolean` | 是否正在移动布尔值。true表示正在移动，角色速度不为0。false表示未移动，角色速度为0。 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"Example_Character"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，如果角色正在移动，你将在控制台中看到打印的角色移动速度。代码如下：
</span>

```ts
@Component
export default class Example_Character extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            this.useUpdate = true;
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 最大加速度为原来的0.1倍
            myCharacter.maxAcceleration = 0.1 * myCharacter.maxAcceleration;
            // 最大转向速度为原来的0.5倍
            myCharacter.rotateRate = 0.5 * myCharacter.rotateRate;
            // 最大行走速度为原来的2倍
            myCharacter.maxWalkSpeed = 2 * myCharacter.maxWalkSpeed;
            // 最大加速度为原来的0.1倍
            myCharacter.brakingDecelerationWalking = 0.1 * myCharacter.brakingDecelerationWalking;
            myCharacter.groundFriction = 1;
            // 添加一个按键方法：按下键盘“1”，切换角色摩擦力的来源
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.groundFrictionEnabled = !myCharacter.groundFriction;
            });
        }
    }
    // 周期函数每帧执行，此函数执行需要将this.useUpdate赋值为true，dt是当前帧与上一帧的延迟（秒）
    protected onUpdate(dt: number): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 如果角色正在移动，打印角色的移动速度
            if(myCharacter.isMoving) {
                console.log("当前角色速度：" + myCharacter.velocity);
            }
        }
    }
}
```
___

### jumpMaxCount <Score text="jumpMaxCount" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **jumpMaxCount**(): `number` 

</th>
<th style="text-align: left">

• `set` **jumpMaxCount**(`InJumpMaxCount`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色最大可跳跃次数。角色能够执行跳跃的最大次数。


#### Returns

| `number` | 跳跃次数。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色最大可跳跃次数

#### Parameters

| `InJumpMaxCount` `number` |  跳跃次数。 <br> range: (0,+∞) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"Example_Character_jumpMaxCount"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏设置角色最大跳跃高度为300，最高三连跳。按下键盘“1”，角色跳跃。按下键盘“2”，启用/禁用跳跃能力。你将在场景中看到角色禁用跳跃能力的效果。代码如下：
</span>

```ts
@Component
export default class Example_Character_jumpMaxCount extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 最大跳跃高度为300
            myCharacter.maxJumpHeight = 300;
            // 最高三连跳
            myCharacter.jumpMaxCount = 3;
            // 添加一个按键方法:按下键盘“1”，角色跳跃。
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.jump();
                console.log("当前角色是否在跳跃 " + myCharacter.isJumping);
            });
            // 添加一个按键方法:按下键盘“2”，启用/禁用跳跃能力。
            InputUtil.onKeyDown(Keys.Two, () => {
                myCharacter.jumpEnabled = !myCharacter.jumpEnabled;
                console.log("当前角色跳跃能力 " + myCharacter.jumpEnabled);
            });
        }
    }
}
```
___

### maxAcceleration <Score text="maxAcceleration" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **maxAcceleration**(): `number` 

</th>
<th style="text-align: left">

• `set` **maxAcceleration**(`InMaxAcceleration`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色最大加速度。角色移动时，角色可以达到的最大加速度


#### Returns

| `number` | 最大加速度。<br> 默认值为2048。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色最大加速度

#### Parameters

| `InMaxAcceleration` `number` |  最大加速度。 <br> range: (0,+∞) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"Example_Character_MaxAcceleration"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将设置角色最大加速度为原来的0.1倍，并在场景中看到角色加速变慢的效果。代码如下：
</span>

```ts
@Component
export default class Example_Character_MaxAcceleration extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            this.useUpdate = true;
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 最大加速度为原来的0.1倍
            myCharacter.maxAcceleration = 0.1 * myCharacter.maxAcceleration;
            // 最大转向速度为原来的0.5倍
            myCharacter.rotateRate = 0.5 * myCharacter.rotateRate;
            // 最大行走速度为原来的2倍
            myCharacter.maxWalkSpeed = 2 * myCharacter.maxWalkSpeed;
            // 最大加速度为原来的0.1倍
            myCharacter.brakingDecelerationWalking = 0.1 * myCharacter.brakingDecelerationWalking;
            myCharacter.groundFriction = 1;
            // 添加一个按键方法：按下键盘“1”，切换角色摩擦力的来源
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.groundFrictionEnabled = !myCharacter.groundFriction;
            });
        }
    }
    // 周期函数每帧执行，此函数执行需要将this.useUpdate赋值为true，dt是当前帧与上一帧的延迟（秒）
    protected onUpdate(dt: number): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 如果角色正在移动，打印角色的移动速度
            if(myCharacter.isMoving) {
                console.log("当前角色速度：" + myCharacter.velocity);
            }
        }
    }
}
```
___

### maxFallingSpeed <Score text="maxFallingSpeed" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **maxFallingSpeed**(): `number` 

</th>
<th style="text-align: left">

• `set` **maxFallingSpeed**(`speed`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


设置角色最大下落速度。角色在下落状态下移动时，角色可达到的最大移动速度


#### Returns

| `number` | 下落速度。<br> 默认值为2048。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色最大下落速度

#### Parameters

| `speed` `number` |  下落速度。 <br> range: (0,+∞) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"Example_MaxFallingSpeed"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将设置角色最大下落速度为1024。按下键盘“1”，角色设置跳跃高度为1000后跳跃，你可以在场景中看到比正常更快的下落速度的效果。代码如下：
</span>

```ts
@Component
export default class Example_MaxFallingSpeed extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 最大下落速度为1024
            myCharacter.maxFallingSpeed = 1024;
            // 下落制动速率为10
            myCharacter.horizontalBrakingDecelerationFalling = 10;
            // 按地面移动速率的0.1倍控制下落过程
            myCharacter.driftControl = 0.1;
            // 10倍重力
            myCharacter.gravityScale = 10;
            // 添加一个按键方法：按下键盘“1”，角色设置跳跃高度为1000后跳跃。
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.maxJumpHeight = 1000;
                myCharacter.jump();
            });
        }
    }
}
```
___

### maxFlySpeed <Score text="maxFlySpeed" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **maxFlySpeed**(): `number` 

</th>
<th style="text-align: left">

• `set` **maxFlySpeed**(`InMaxFlySpeed`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色最大飞行速度。角色在飞行状态下进行移动时，角色可达到的最大移动速度


#### Returns

| `number` | 最大飞行速度。 <br> 默认值为：800 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色最大飞行速度

#### Parameters

| `InMaxFlySpeed` `number` |  最大飞行速度。 <br> range: (0,+∞) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"53011,20307"拖入优先加载栏。创建一个名为"Example_MaxFlySpeed"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“1”，角色切换为飞行，按下键盘“2”，角色进行喷射加速。你将在场景中看到角色在加速过程中最大飞行速度变化的效果。代码如下：
</span>

```ts
@Component
export default class Example_MaxFlySpeed extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 加载喷射加速动画
            let boostAnimation = myCharacter.loadAnimation("53011");
            boostAnimation.loop = 0;
            let isBoost = false
            // 加载上升姿态
            let boostStance = myCharacter.loadSubStance("20307");
            // 添加一个按键方法:按下键盘“1”，角色切换为飞行
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.switchToFlying();
            });
            // 添加一个按键方法:按下键盘“2”，角色进行喷射加速
            InputUtil.onKeyDown(Keys.Two, () => {
                if(isBoost) return;
                let boost_interval = 0;
                if(myCharacter.isMoving) {
                    // 播放飞行动画，修改飞行速度和制动速度
                    boostAnimation.play();
                    myCharacter.maxFlySpeed = 2000;
                    myCharacter.brakingDecelerationFlying = 5000;
                    // 设置加速周期，每帧检查角色是否移动，当角色停止移动时,执行停止加速操作:停止动画清除姿态，还原飞行速度，清除加速周期
                    boost_interval = setInterval(() => {
                        if(!myCharacter.isMoving) {
                            isBoost = false;
                            clearInterval(boost_interval);
                            myCharacter.maxFlySpeed = 500;
                            boostAnimation.stop();
                            boostStance.stop();
                        }
                    }, 1);
                // 如果当前角色静止，修改角色为上升姿态，设置加速周期，每帧上升5个单位
                } else {
                    boostStance.play();
                    boost_interval = setInterval(() => {
                        myCharacter.addMovement(new Vector(0, 0, 5));
                    }, 1);
                }
                // 2秒后执行停止加速操作
                    setTimeout(() => {
                        isBoost = false;
                        clearInterval(boost_interval);
                        myCharacter.maxFlySpeed = 500;
                        boostAnimation.stop();
                        boostStance.stop();
                    }, 2000);
                    // 2.2秒后还原角色飞行制动速度
                    setTimeout(() => {
                        myCharacter.brakingDecelerationFlying = 300;
                    }, 2200);
            });
        }
    }
}
```
___

### maxJumpHeight <Score text="maxJumpHeight" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **maxJumpHeight**(): `number` 

</th>
<th style="text-align: left">

• `set` **maxJumpHeight**(`InMaxJumpHeight`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色最大跳跃高度。角色跳跃时，从起跳位置到最高位置的距离。该值受重力影响。


#### Returns

| `number` | 跳跃高度。<br> 默认值为50.0。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色最大跳跃高度

#### Parameters

| `InMaxJumpHeight` `number` |  制动速率。 <br> range: (0,+∞) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"Example_Character"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，设置角色最大跳跃高度为300，最高三连跳。按下键盘“1”，角色跳跃。按下键盘“2”，启用/禁用跳跃能力。你将在场景中看到角色禁用跳跃能力的效果。代码如下：
</span>

```ts
@Component
export default class Example_Character extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 最大跳跃高度为300
            myCharacter.maxJumpHeight = 300;
            // 最高三连跳
            myCharacter.jumpMaxCount = 3;
            // 添加一个按键方法:按下键盘“1”，角色跳跃。
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.jump();
                console.log("当前角色是否在跳跃 " + myCharacter.isJumping);
            });
            // 添加一个按键方法:按下键盘“2”，启用/禁用跳跃能力。
            InputUtil.onKeyDown(Keys.Two, () => {
                myCharacter.jumpEnabled = !myCharacter.jumpEnabled;
                console.log("当前角色跳跃能力 " + myCharacter.jumpEnabled);
            });
        }
    }
}
```
___

### maxStepHeight <Score text="maxStepHeight" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **maxStepHeight**(): `number` 

</th>
<th style="text-align: left">

• `set` **maxStepHeight**(`InMaxStepHeight`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色最大可跨越高度。角色跨越台阶时，台阶的最大高度，大于等于该高度角色均无法跨越。


#### Returns

| `number` | 最大可跨越高度。 <br> 默认值为45。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色最大可跨越高度

#### Parameters

| `InMaxStepHeight` `number` |  最大可跨越高度。 <br> range: (0,+∞) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"7667,197386"拖入优先加载栏。创建一个名为"Example_MaxStepHeight"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中创建5个不同高度的立方体:10，20，40，80，160。按下键盘“1”，角色最大可跨越高度增加10。按下键盘“2”，角色最大可跨越高度减小10。你将看到角色最大可跨越高度变化带来的效果。代码如下：
</span>

```ts
@Component
export default class Example_MaxStepHeight extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
         // 下列代码仅在服务端执行
         if(SystemUtil.isServer()) {
            // 创建5个不同高度的立方体：10，20，40，80，160
            let cubeHeight = [10, 20, 40, 80, 160];
            for (let i = 0;
i < cubeHeight.length;
i++) {
                GameObject.spawn("197386",{transform: new Transform(new Vector(250 * i, -500, 0), Rotation.zero, new Vector(2, 2, cubeHeight[i] / 100))});
            }
            // 创建5个不同坡度的锥体:1，30，45，60，89
            let coneAngle = [1, 30, 45, 60, 89];
            for (let i = 0;
i < coneAngle.length;
i++) {
                console.log("1111");
                GameObject.spawn("7667",{transform: new Transform(new Vector(250 * i, 500, 0), Rotation.zero, new Vector(2, 2, Math.tan(coneAngle[i] * Math.PI / 180)))});
            }
         }
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 添加一个按键方法：按下键盘“1”，角色最大可跨越高度增加10
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.maxStepHeight += 10;
                console.log("角色最大可跨越高度：" + myCharacter.maxStepHeight);
            });
            // 添加一个按键方法：按下键盘“2”，角色最大可跨越高度减小10
            InputUtil.onKeyDown(Keys.Two, () => {
                myCharacter.maxStepHeight -= 10;
                console.log("角色最大可跨越高度：" + myCharacter.maxStepHeight);
            });
            // 添加一个按键方法：按下键盘“3”，角色可行走的最大角度增加5
            InputUtil.onKeyDown(Keys.Three, () => {
                myCharacter.walkableFloorAngle += 5;
                console.log("可行走的最大角度：" + myCharacter.walkableFloorAngle);
            });
            // 添加一个按键方法：按下键盘“4”，角色可行走的最大角度减小5
            InputUtil.onKeyDown(Keys.Four, () => {
                myCharacter.walkableFloorAngle -= 5;
                console.log("可行走的最大角度：" + myCharacter.walkableFloorAngle);
            });
        }
    }
}
```
___

### maxSwimSpeed <Score text="maxSwimSpeed" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **maxSwimSpeed**(): `number` 

</th>
<th style="text-align: left">

• `set` **maxSwimSpeed**(`InMaxSwimSpeed`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色最大游泳速度。角色在游泳状态下，可达到的最大移动速度。


#### Returns

| `number` | 最大游泳速度。<br> 默认值为300 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色最大游泳速度

#### Parameters

| `InMaxSwimSpeed` `number` |  最大游泳速度。<br> range: (0,+∞) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"53011,20307"拖入优先加载栏。创建一个名为"Example_MaxSwimSpeed"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中生成拱形容器并适配游泳区域。按下键盘“1”，角色切换游泳。按下键盘“4”，角色修改最大游泳速度进行喷射加速。你可以看到的角色最大游泳速度变化的效果。代码如下：
</span>

```ts
@Component
export default class Example_MaxSwimSpeed extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在服务端执行
        if(SystemUtil.isServer()) {
            // 生成拱形容器并适配游泳区域
            GameObject.spawn("WaterVolume",{transform: new Transform(new Vector(0, 0, 500), new Rotation(0, 0, 90), new Vector(20, 20, 10))});
        }
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            let flag = true;
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 设置游泳属性
            myCharacter.canJumpOutOfWater = true;
            myCharacter.outOfWaterVerticalSpeed = 100;
            // 加载加速动画
            let boostAnimation = myCharacter.loadAnimation("53011");
            boostAnimation.loop = 10;
            let isBoost = false
            // 加载上升姿态
            let boostStance = myCharacter.loadSubStance("20307");
            // 添加一个按键方法:按下键盘“1”，角色切换游泳 / 行走
            InputUtil.onKeyDown(Keys.One, () => {
                if(flag) {
                    myCharacter.switchToWalking();
                } else {
                    myCharacter.switchToSwimming();
                }
                flag = !flag;
            });
            // 添加一个按键方法:按住键盘“2”，角色上浮
            InputUtil.onKeyPress(Keys.Two, () => {
                myCharacter.swimUp(10);
            });
            // 添加一个按键方法:按住键盘“3”，角色下潜
            InputUtil.onKeyPress(Keys.Three, () => {
                myCharacter.swimDown(10);
            });
            // 添加一个按键方法:按下键盘“4”，角色进行喷射加速
            InputUtil.onKeyDown(Keys.Four, () => {
                if(isBoost) return;
                let boost_interval = 0;
                if(myCharacter.isMoving) {
                    // 播放游泳动画，修改游泳速度和制动速度
                    boostAnimation.play();
                    myCharacter.maxSwimSpeed = 600;
                    myCharacter.brakingDecelerationSwimming = 4096;
                    // 设置加速周期，每帧检查角色是否移动，当角色停止移动时,执行停止加速操作:停止动画清除姿态，还原游泳速度，清除加速周期
                    boost_interval = setInterval(() => {
                        if(!myCharacter.isMoving) {
                            isBoost = false;
                            clearInterval(boost_interval);
                            myCharacter.maxSwimSpeed = 300;
                            boostAnimation.stop();
                            boostStance.stop();
                        }
                    }, 1);
                // 如果当前角色静止，修改角色为上升姿态，设置加速周期，每帧上升5个单位
                } else {
                    boostStance.play();
                    boost_interval = setInterval(() => {
                        myCharacter.swimUp(1)
                    }, 1);
                }
                // 1秒后执行停止加速操作
                    setTimeout(() => {
                        isBoost = false;
                        clearInterval(boost_interval);
                        myCharacter.maxSwimSpeed = 300;
                        boostAnimation.stop();
                        boostStance.stop();
                    }, 1000);
                    // 1.2秒后还原角色游泳制动速度
                    setTimeout(() => {
                        myCharacter.brakingDecelerationSwimming = 4096
                    }, 1200);
            });
        }
    }
}
```
___

### maxWalkSpeed <Score text="maxWalkSpeed" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **maxWalkSpeed**(): `number` 

</th>
<th style="text-align: left">

• `set` **maxWalkSpeed**(`InMaxWalkSpeed`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色的最大行走速度。角色移动时，并不是直接变为最大速度，而是随着输入或其他控制，速度逐渐增加，最大行走速度为角色可以达到的最大速度。同时也是跌倒时的最大横向速度。


#### Returns

| `number` | 角色最大行走速度浮点数。<br> 默认值为450 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色的最大行走速度

#### Parameters

| `InMaxWalkSpeed` `number` |  最大行走速度 <br> range: (0,+∞) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"Example_MaxWalkSpeed"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将设置角色最大行走速度为原来的2倍，并在场景中看到角色移动最高速度变快的效果。代码如下：
</span>

```ts
@Component
export default class Example_MaxWalkSpeed extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            this.useUpdate = true;
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 最大加速度为原来的0.1倍
            myCharacter.maxAcceleration = 0.1 * myCharacter.maxAcceleration;
            // 最大转向速度为原来的0.5倍
            myCharacter.rotateRate = 0.5 * myCharacter.rotateRate;
            // 最大行走速度为原来的2倍
            myCharacter.maxWalkSpeed = 2 * myCharacter.maxWalkSpeed;
            // 最大加速度为原来的0.1倍
            myCharacter.brakingDecelerationWalking = 0.1 * myCharacter.brakingDecelerationWalking;
            myCharacter.groundFriction = 1;
            // 添加一个按键方法：按下键盘“1”，切换角色摩擦力的来源
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.groundFrictionEnabled = !myCharacter.groundFriction;
            });
        }
    }
    // 周期函数每帧执行，此函数执行需要将this.useUpdate赋值为true，dt是当前帧与上一帧的延迟（秒）
    protected onUpdate(dt: number): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 如果角色正在移动，打印角色的移动速度
            if(myCharacter.isMoving) {
                console.log("当前角色速度：" + myCharacter.velocity);
            }
        }
    }
}
```
___

### maxWalkSpeedCrouched <Score text="maxWalkSpeedCrouched" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **maxWalkSpeedCrouched**(): `number` 

</th>
<th style="text-align: left">

• `set` **maxWalkSpeedCrouched**(`maxSpeed`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色最大蹲伏行走速度

::: warning Precautions

角色在下蹲状态下移动时，角色可达到的最大移动速度

:::


#### Returns

| `number` | 最大蹲伏行走速度。 <br> 默认值为：100 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色最大蹲伏行走速度

::: warning Precautions

角色在下蹲状态下移动时，角色可达到的最大移动速度

:::

#### Parameters

| `maxSpeed` `number` |  最大蹲伏行走速度 <br> range: (0,+∞) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"54834,36851"拖入优先加载栏。创建一个名为"Example_MaxWalkSpeedCrouched"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中生成草丛和拱门并添加触发器，添加委托函数实现角色进入草丛蹲下，离开站起的效果。设置地面蹲伏行走时的最大移动速度100。你可以看到角色蹲下后行走速度减慢的效果。代码如下：
</span>

```ts
@Component
export default class Example_MaxWalkSpeedCrouched extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 生成草丛和拱门
            GameObject.spawn("54834",{transform: new Transform(new Vector(300, 0, 0), Rotation.zero, new Vector(2, 2, 2))});
            let arch = GameObject.spawn("36851",{transform: new Transform(new Vector(300, 210, 0), new Rotation(0, 0, 90), new Vector(2, 1, 2))}) as Model;
            arch.setCollision(CollisionStatus.On);
            // 生成触发器并添加委托函数：进入触发器的角色蹲下，离开触发器站起
            let tri = GameObject.spawn("Trigger",{transform: new Transform(new Vector(300, 0, 50), Rotation.zero, new Vector(2, 2, 1))}) as Trigger;
            tri.onEnter.add((character: Character) => {
                character.crouch(true);
                setTimeout(() => {
                    console.log("当前角色下蹲 " + character.isCrouching);
                }, 500);
            });
            tri.onLeave.add((character: Character) => {
                character.crouch(false);
                console.log("当前角色下蹲 " + character.isCrouching);
            });
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 地面蹲伏行走时的最大移动速度100
            myCharacter.maxWalkSpeedCrouched = 100;
            // 下蹲后高度为100
            myCharacter.crouchedHeight = 100;
            // 添加一个按键方法：按下键盘“1”，启用/禁用下蹲能力
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.crouchEnabled = !myCharacter.crouchEnabled;
                console.log("当前角色是否能下蹲 " + myCharacter.crouchEnabled);
            });
        }
    }
}
```
___

### meshPositionOffset <Score text="meshPositionOffset" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **meshPositionOffset**(): [`Vector`](mw.Vector.md) 

</th>
<th style="text-align: left">

• `set` **meshPositionOffset**(`offset`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取mesh相对角色坐标点的偏移

#### Returns

| [`Vector`](mw.Vector.md) | mesh相对角色坐标点的偏移 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置mesh相对角色坐标点的偏移

#### Parameters

| `offset` | [`Vector`](mw.Vector.md) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### meshRotationOffset <Score text="meshRotationOffset" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **meshRotationOffset**(): [`Rotation`](mw.Rotation.md) 

</th>
<th style="text-align: left">

• `set` **meshRotationOffset**(`offset`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取mesh相对角色旋转的偏移

#### Returns

| [`Rotation`](mw.Rotation.md) | mesh相对角色坐标点的偏移 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置mesh相对角色旋转的偏移

#### Parameters

| `offset` | [`Rotation`](mw.Rotation.md) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### moveFacingDirection <Score text="moveFacingDirection" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **moveFacingDirection**(): [`MoveFacingDirection`](../enums/mw.MoveFacingDirection.md) 

</th>
<th style="text-align: left">

• `set` **moveFacingDirection**(`InMoveFacingDirection`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色运动面朝方向。角色模型运动时朝向的方向：
1. 始终朝向移动方向:主角模型面朝方向始终朝向移动方向。
2. 始终朝向固定方向:主角模型面朝方向始终朝向固定方向。
3. 始终朝向控制器方向:主角模型面朝方向始终朝向控制器


#### Returns

| [`MoveFacingDirection`](../enums/mw.MoveFacingDirection.md) | 面朝方向枚举值。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色运动时面朝方向。

#### Parameters

| `InMoveFacingDirection` [`MoveFacingDirection`](../enums/mw.MoveFacingDirection.md) |  面朝方向。 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"Example_Character_MoveFacingDirection"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“1”，切换角色的运动面朝方向。你将在场景中看到角色不同运动面朝方向的效果并在控制台看到打印的当前角色的运动轴和面朝方向。代码如下：
</span>

```ts
@Component
export default class Example_Character_MoveFacingDirection extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 设置定轴方向
            myCharacter.movementAxisDirection = new Vector(1, 0, 0);
            // 打印当前角色的运动轴和面朝方向
            console.log("当前角色的运动面朝方向 " + MoveFacingDirection[myCharacter.moveFacingDirection]);
            console.log("当前角色的运动时依据的正方向 " + MovementDirection[myCharacter.movementDirection]);
            // 添加一个按键方法:按下键盘“1”，切换角色的运动面朝方向
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.moveFacingDirection = (myCharacter.moveFacingDirection + 1) % 3;
                console.log("当前角色的运动 " + MoveFacingDirection[myCharacter.moveFacingDirection] + " + " + MovementDirection[myCharacter.movementDirection]);
            });
            // 添加一个按键方法:按下键盘“2”，切换角色的运动时依据的正方向
            InputUtil.onKeyDown(Keys.Two, () => {
                myCharacter.movementDirection = (myCharacter.movementDirection + 1) % 3;
                console.log("当前角色的运动 " + MoveFacingDirection[myCharacter.moveFacingDirection] + " + " + MovementDirection[myCharacter.movementDirection]);
                if(myCharacter.movementDirection == 0) {
                    console.log("当前角色的运动 " + MoveFacingDirection[myCharacter.moveFacingDirection] + " + " + MovementDirection[myCharacter.movementDirection] + " 定轴方向 " + myCharacter.movementAxisDirection);
                }
            });
        }
    }
}
```
___

### movementDirection <Score text="movementDirection" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **movementDirection**(): [`MovementDirection`](../enums/mw.MovementDirection.md) 

</th>
<th style="text-align: left">

• `set` **movementDirection**(`InMovementDirection`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色运动正方向。角色运动时依据的正方向。
1. 控制器方向，就以控制器坐标系为轴;
2. 如果是定轴方向，就以世界坐标系中movementAxisDirection为轴;
3. 如果是视线方向，就以相机坐标系的为轴。在玩家相机不存在Z轴旋转时，控制器方向和视线方向效果一致，人形对象的控制器方向和视线方向效果永远一致。


#### Returns

| [`MovementDirection`](../enums/mw.MovementDirection.md) | 运动正方向。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色运动正方向

#### Parameters

| `InMovementDirection` [`MovementDirection`](../enums/mw.MovementDirection.md) |  运动正方向。 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"Example_Character_MovementDirection"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“2”，切换角色的运动时依据的正方向。你将在场景中看到角色不同运动时依据正方向的效果并在控制台看到打印的当前角色的运动轴和依据的正方向。代码如下：
</span>

```ts
@Component
export default class Example_Character_MovementDirection extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 设置定轴方向
            myCharacter.movementAxisDirection = new Vector(1, 0, 0);
            // 打印当前角色的运动轴和面朝方向
            console.log("当前角色的运动面朝方向 " + MoveFacingDirection[myCharacter.moveFacingDirection]);
            console.log("当前角色的运动时依据的正方向 " + MovementDirection[myCharacter.movementDirection]);
            // 添加一个按键方法:按下键盘“1”，切换角色的运动面朝方向
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.moveFacingDirection = (myCharacter.moveFacingDirection + 1) % 3;
                console.log("当前角色的运动 " + MoveFacingDirection[myCharacter.moveFacingDirection] + " + " + MovementDirection[myCharacter.movementDirection]);
            });
            // 添加一个按键方法:按下键盘“2”，切换角色的运动时依据的正方向
            InputUtil.onKeyDown(Keys.Two, () => {
                myCharacter.movementDirection = (myCharacter.movementDirection + 1) % 3;
                console.log("当前角色的运动 " + MoveFacingDirection[myCharacter.moveFacingDirection] + " + " + MovementDirection[myCharacter.movementDirection]);
                if(myCharacter.movementDirection == 0) {
                    console.log("当前角色的运动 " + MoveFacingDirection[myCharacter.moveFacingDirection] + " + " + MovementDirection[myCharacter.movementDirection] + " 定轴方向 " + myCharacter.movementAxisDirection);
                }
            });
        }
    }
}
```
___

### opacity <Score text="opacity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **opacity**(): `number` 

</th>
<th style="text-align: left">

• `set` **opacity**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色单层透明度

#### Returns

| `number` | 获取透明度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色单层透明度

#### Parameters

| `value` `number` | 透明度[0,1] |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### outOfWaterVerticalSpeed <Score text="outOfWaterVerticalSpeed" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **outOfWaterVerticalSpeed**(): `number` 

</th>
<th style="text-align: left">

• `set` **outOfWaterVerticalSpeed**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


出水时垂直方向速度


#### Returns

| `number` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


出水时垂直方向速度

#### Parameters

| `value` `number` |  出水速度。 <br> range: (0,+∞) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"53011,20307"拖入优先加载栏。创建一个名为"Example_OutOfWaterVerticalSpeed "的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，设置角色可以跳出水面且出水垂直速度为100。在场景中生成拱形容器并适配游泳区域。按住键盘“2”，角色上浮。你可以看到的角色到达水面并跃出的效果。代码如下：
</span>

```ts
@Component
export default class Example_OutOfWaterVerticalSpeed  extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在服务端执行
        if(SystemUtil.isServer()) {
            // 生成拱形容器并适配游泳区域
            GameObject.spawn("WaterVolume",{transform: new Transform(new Vector(0, 0, 500), new Rotation(0, 0, 90), new Vector(20, 20, 10))});
        }
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            let flag = true;
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 设置游泳属性
            myCharacter.canJumpOutOfWater = true;
            myCharacter.outOfWaterVerticalSpeed = 100;
            // 加载加速动画
            let boostAnimation = myCharacter.loadAnimation("53011");
            boostAnimation.loop = 10;
            let isBoost = false
            // 加载上升姿态
            let boostStance = myCharacter.loadSubStance("20307");
            // 添加一个按键方法:按下键盘“1”，角色切换游泳 / 行走
            InputUtil.onKeyDown(Keys.One, () => {
                if(flag) {
                    myCharacter.switchToWalking();
                } else {
                    myCharacter.switchToSwimming();
                }
                flag = !flag;
            });
            // 添加一个按键方法:按住键盘“2”，角色上浮
            InputUtil.onKeyPress(Keys.Two, () => {
                myCharacter.swimUp(10);
            });
            // 添加一个按键方法:按住键盘“3”，角色下潜
            InputUtil.onKeyPress(Keys.Three, () => {
                myCharacter.swimDown(10);
            });
            // 添加一个按键方法:按下键盘“4”，角色进行喷射加速
            InputUtil.onKeyDown(Keys.Four, () => {
                if(isBoost) return;
                let boost_interval = 0;
                if(myCharacter.isMoving) {
                    // 播放游泳动画，修改游泳速度和制动速度
                    boostAnimation.play();
                    myCharacter.maxSwimSpeed = 600;
                    myCharacter.brakingDecelerationSwimming = 4096;
                    // 设置加速周期，每帧检查角色是否移动，当角色停止移动时,执行停止加速操作:停止动画清除姿态，还原游泳速度，清除加速周期
                    boost_interval = setInterval(() => {
                        if(!myCharacter.isMoving) {
                            isBoost = false;
                            clearInterval(boost_interval);
                            myCharacter.maxSwimSpeed = 300;
                            boostAnimation.stop();
                            boostStance.stop();
                        }
                    }, 1);
                // 如果当前角色静止，修改角色为上升姿态，设置加速周期，每帧上升5个单位
                } else {
                    boostStance.play();
                    boost_interval = setInterval(() => {
                        myCharacter.swimUp(1)
                    }, 1);
                }
                // 1秒后执行停止加速操作
                    setTimeout(() => {
                        isBoost = false;
                        clearInterval(boost_interval);
                        myCharacter.maxSwimSpeed = 300;
                        boostAnimation.stop();
                        boostStance.stop();
                    }, 1000);
                    // 1.2秒后还原角色游泳制动速度
                    setTimeout(() => {
                        myCharacter.brakingDecelerationSwimming = 4096
                    }, 1200);
            });
        }
    }
}
```
___

### overheadUI <Score text="overheadUI" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **overheadUI**(): [`UIWidget`](Core.mw.UIWidget.md) <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色头顶名字的界面


#### Returns

| [`UIWidget`](Core.mw.UIWidget.md) | 头顶UIWidget对象 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"Example_Character"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“1”会隐藏 / 显示头顶UI。代码如下：
</span>

```ts
@Component
export default class Example_Character extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 添加一个按键方法：按下键盘“1”，隐藏 / 显示头顶UI
            InputUtil.onKeyDown(Keys.One, () => {
                if(myCharacter.overheadUI.getVisibility() == true) {
                    myCharacter.overheadUI.setVisibility(PropertyStatus.Off);
                } else {
                    myCharacter.overheadUI.setVisibility(PropertyStatus.On);
                }
            });
        }
    }
}
```
___

### physicsEnabled <Score text="physicsEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **physicsEnabled**(): `boolean`

</th>
<th style="text-align: left">

• `set` **physicsEnabled**(`value`): `void`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色物理模拟状态

#### Returns

| `boolean` | 角色当前的是否开启物理模拟。<br> 默认值为false。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色物理模拟状态

#### Parameters

| `value` `boolean` | 是否开启角色物理模拟。 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### ragdollEnabled <Score text="ragdollEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **ragdollEnabled**(): `boolean`

</th>
<th style="text-align: left">

• `set` **ragdollEnabled**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


启用布娃娃

::: warning Precautions

角色当前是否使用布娃娃状态。true表示使用，false表示禁用。

:::


#### Returns

| `boolean` |  |
| :------ | :------ |


</td>
<td style="text-align: left">


角色的布娃娃效果，与其他物体进行交互时，使角色在发生某些条件时可以像布娃娃一样松弛和摆动，而不是保持刚体的僵硬状态。

::: warning Precautions

角色当前是否使用布娃娃状态。true表示使用，false表示禁用。

:::

#### Parameters

| `value` `boolean` |  true为启用布娃娃效果，false为禁用。 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"27693"拖入优先加载栏。创建一个名为"Example_Character"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏你将在场景中生成一个循环黑洞特效。如果角色与黑洞中心距离小于300且角色没有开启布娃娃，则朝中心移动角色。如果角色与黑洞中心距离小于50，则开启布娃娃。你可以看到角色开关布娃娃时的不同效果。代码如下：
</span>

```ts
@Component
export default class Example_Character extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            this.useUpdate = true;
            // 生成一个黑洞特效循环播放
            EffectService.playAtPosition("27693", new Vector(500, 0, 50), {loopCount: 0});
        }
    }
    // 周期函数每帧执行，此函数执行需要将this.useUpdate赋值为true，dt是当前帧与上一帧的延迟（秒）
    protected onUpdate(dt: number): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 如果角色与黑洞中心距离小于300且角色没有开启布娃娃，则朝中心移动角色
            if(myCharacter.worldTransform.position.subtract(new Vector(500, 0, 50)).length < 300 && !myCharacter.ragdollEnabled) {
                let dir = new Vector(500, 0, 50).subtract(myCharacter.worldTransform.position).normalize();
                myCharacter.addMovement(new Vector(dir.x, dir.y, 0));
            }
            // 如果角色与黑洞中心距离小于50，则开启布娃娃
            if(myCharacter.worldTransform.position.subtract(new Vector(500, 0, 50)).length < 50) {
                myCharacter.ragdollEnabled = true;
                setTimeout(() => {
                    myCharacter.worldTransform.position = new Vector(0, 0, 130);
                    myCharacter.ragdollEnabled = false;
                }, 2000);
            }
        }
    }
}
```
___

### rotateRate <Score text="rotateRate" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **rotateRate**(): `number` 

</th>
<th style="text-align: left">

• `set` **rotateRate**(`InRotateRate`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色最大转向速度。角色每秒旋转的最大速度。设置为负值时，转向速度被视为无限大，可以瞬间转向。


#### Returns

| `number` | 最大转向速度。<br> 默认值为180度/秒。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色最大转向速度

#### Parameters

| `InRotateRate` | `number` |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"Example_Character_RotateRate"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将设置角色转向速度为原来的0.5倍，并在场景中看到角色转向变慢的效果。代码如下：
</span>

```ts
@Component
export default class Example_Character_RotateRate extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            this.useUpdate = true;
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 最大加速度为原来的0.1倍
            myCharacter.maxAcceleration = 0.1 * myCharacter.maxAcceleration;
            // 最大转向速度为原来的0.5倍
            myCharacter.rotateRate = 0.5 * myCharacter.rotateRate;
            // 最大行走速度为原来的2倍
            myCharacter.maxWalkSpeed = 2 * myCharacter.maxWalkSpeed;
            // 最大加速度为原来的0.1倍
            myCharacter.brakingDecelerationWalking = 0.1 * myCharacter.brakingDecelerationWalking;
            myCharacter.groundFriction = 1;
            // 添加一个按键方法：按下键盘“1”，切换角色摩擦力的来源
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.groundFrictionEnabled = !myCharacter.groundFriction;
            });
        }
    }
    // 周期函数每帧执行，此函数执行需要将this.useUpdate赋值为true，dt是当前帧与上一帧的延迟（秒）
    protected onUpdate(dt: number): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 如果角色正在移动，打印角色的移动速度
            if(myCharacter.isMoving) {
                console.log("当前角色速度：" + myCharacter.velocity);
            }
        }
    }
}
```
___

### velocity <Score text="velocity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **velocity**(): [`Vector`](mw.Vector.md) 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色当前移动速度

::: warning Precautions

角色当前移动的速度

:::


#### Returns

| [`Vector`](mw.Vector.md) | 移动速度大小和方向的三维向量。 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:创建一个名为"Example_Character"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，如果角色正在移动，你将在控制台中看到打印的角色移动速度。代码如下：
</span>

```ts
@Component
export default class Example_Character extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            this.useUpdate = true;
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 最大加速度为原来的0.1倍
            myCharacter.maxAcceleration = 0.1 * myCharacter.maxAcceleration;
            // 最大转向速度为原来的0.5倍
            myCharacter.rotateRate = 0.5 * myCharacter.rotateRate;
            // 最大行走速度为原来的2倍
            myCharacter.maxWalkSpeed = 2 * myCharacter.maxWalkSpeed;
            // 最大加速度为原来的0.1倍
            myCharacter.brakingDecelerationWalking = 0.1 * myCharacter.brakingDecelerationWalking;
            myCharacter.groundFriction = 1;
            // 添加一个按键方法：按下键盘“1”，切换角色摩擦力的来源
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.groundFrictionEnabled = !myCharacter.groundFriction;
            });
        }
    }
    // 周期函数每帧执行，此函数执行需要将this.useUpdate赋值为true，dt是当前帧与上一帧的延迟（秒）
    protected onUpdate(dt: number): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 如果角色正在移动，打印角色的移动速度
            if(myCharacter.isMoving) {
                console.log("当前角色速度：" + myCharacter.velocity);
            }
        }
    }
}
```
___

### walkableFloorAngle <Score text="walkableFloorAngle" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **walkableFloorAngle**(): `number` 

</th>
<th style="text-align: left">

• `set` **walkableFloorAngle**(`InWalkableFloorAngle`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取角色可行走的最大角度。角色站立在斜坡上时，斜坡的最大角度，超过该角度，角色将无法站立在这个斜坡上，角色会存在坠落的表现。使用范围在0-90之间。


#### Returns

| `number` | 最大角度。<br> 默认值为45（角度值） |
| :------ | :------ |


</td>
<td style="text-align: left">


设置角色可行走的最大角度

#### Parameters

| `InWalkableFloorAngle` `number` |  可行走的最大角度。<br> range: [0,) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

<span style="font-size: 14px;">
使用示例:将使用到的资源:"7667,197386"拖入优先加载栏。创建一个名为"Example_WalkableFloorAngle"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中创建5个不同坡度的锥体:1，30，45，60，89。按下键盘“3”，角色可行走的最大角度增加5。按下键盘“4”，角色可行走的最大角度减小5。你将看到角色可行走的最大角度变化带来的效。代码如下：
</span>

```ts
@Component
export default class Example_WalkableFloorAngle extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
         // 下列代码仅在服务端执行
         if(SystemUtil.isServer()) {
            // 创建5个不同高度的立方体：10，20，40，80，160
            let cubeHeight = [10, 20, 40, 80, 160];
            for (let i = 0;
i < cubeHeight.length;
i++) {
                GameObject.spawn("197386",{transform: new Transform(new Vector(250 * i, -500, 0), Rotation.zero, new Vector(2, 2, cubeHeight[i] / 100))});
            }
            // 创建5个不同坡度的锥体:1，30，45，60，89
            let coneAngle = [1, 30, 45, 60, 89];
            for (let i = 0;
i < coneAngle.length;
i++) {
                console.log("1111");
                GameObject.spawn("7667",{transform: new Transform(new Vector(250 * i, 500, 0), Rotation.zero, new Vector(2, 2, Math.tan(coneAngle[i] * Math.PI / 180)))});
            }
         }
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 添加一个按键方法：按下键盘“1”，角色最大可跨越高度增加10
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.maxStepHeight += 10;
                console.log("角色最大可跨越高度：" + myCharacter.maxStepHeight);
            });
            // 添加一个按键方法：按下键盘“2”，角色最大可跨越高度减小10
            InputUtil.onKeyDown(Keys.Two, () => {
                myCharacter.maxStepHeight -= 10;
                console.log("角色最大可跨越高度：" + myCharacter.maxStepHeight);
            });
            // 添加一个按键方法：按下键盘“3”，角色可行走的最大角度增加5
            InputUtil.onKeyDown(Keys.Three, () => {
                myCharacter.walkableFloorAngle += 5;
                console.log("可行走的最大角度：" + myCharacter.walkableFloorAngle);
            });
            // 添加一个按键方法：按下键盘“4”，角色可行走的最大角度减小5
            InputUtil.onKeyDown(Keys.Four, () => {
                myCharacter.walkableFloorAngle -= 5;
                console.log("可行走的最大角度：" + myCharacter.walkableFloorAngle);
            });
        }
    }
}
```
___

### nameDisplayDistance <Score text="nameDisplayDistance" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **nameDisplayDistance**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **nameDisplayDistance**(`range`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取当前客户端所有角色头顶显示名称可见距离。

::: warning Precautions

显示名称可见距离

:::

#### Returns

| `number` | 显示名称可见距离 <br> 默认值为2000。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置当前客户端所有角色头顶显示名称可见距离，当角色头顶显示名称可见时生效。距离为0时不可见。

::: warning Precautions

显示名称可见距离

:::

#### Parameters

| `range` `number` |  显示名称可见距离 <br> range: (0,+∞) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### nameVisible <Score text="nameVisible" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **nameVisible**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **nameVisible**(`isVisible`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取当前客户端所有角色头顶显示名称是否可见。

#### Returns

| `boolean` | 为true时角色头顶显示名称可见，为false时角色头顶显示名称不可见。<br> 默认为可见。 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置当前客户端所有角色头顶显示名称是否可见，当角色头顶显示名称可见时会受设置面板控制，不可见时不受设置面板控制。

#### Parameters

| `isVisible` `boolean` |  为true时角色头顶显示名称可见，为false时角色头顶显示名称不可见。 |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods

___

### addImpulse <Score text="addImpulse" /> 

• **addImpulse**(`vector`, `ignoreMass?`): `void` <Badge type="tip" text="server" />

添加冲量，相同冲量值在布娃娃与正常状态时，力效果会有差异。质量固定为100，受质量影响的算法为: 冲量按位除以质量

#### Parameters

| `vector` [`Vector`](mw.Vector.md) | 应用的冲量 |
| :------ | :------ |
| `ignoreMass?` `boolean` | 是否忽略质量对冲量的影响 default:false |


<span style="font-size: 14px;">
使用示例:将使用到的资源:"122180,122182,132631,75354"拖入优先加载栏。创建一个名为"Example_Character"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中生成一个生成大炮模型。在大炮附加生成一个触发器并添加进入委托，当角色进入范围后向服务器发送【发射】事件。如果角色进入触发器则，你可以看到角色添加一个冲量被大炮发射出去的效果。代码如下：
</span>

```ts
@Component
export default class Example_Character extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在服务端执行
        if(SystemUtil.isServer()) {
            // 生成大炮模型
            let cannon_base = GameObject.spawn("122180",{transform: new Transform(new Vector(750, 0, 0), new Rotation(0, 0, -90), Vector.one.multiply(2))});
            let cannon_tube  = GameObject.spawn("122182",{transform: new Transform(new Vector(750, 0, 250), new Rotation(0, 30, 90), Vector.one.multiply(2))});
            // 在服务端添加一个【Launch】事件监听器，给角色添加冲量
            mw.Event.addClientListener("Launch", (player) => {
                player.character.addImpulse(new Vector(0, 1, 1).multiply(1000), true);
            });
        }
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 生成触发器并添加进入委托，当角色进入范围后向服务器发送【发射】事件
            let cannon_trigger  = GameObject.spawn("Trigger",{transform: new Transform(new Vector(750, 0, 0), new Rotation(0, 30, 90), Vector.one.multiply(4))}) as Trigger;
            cannon_trigger.onEnter.add((character: Character) => {
                character.worldTransform.position = new Vector(750, 275, 330);
                // 向服务器派发【Launch】事件
                mw.Event.dispatchToServer("Launch");
                // 播放音效特效。
                EffectService.playAtPosition("132631", new Vector(750, 275, 330))
                SoundService.playSound("75354");
            });
        }
    }
}
```

___

### addMovement <Score text="addMovement" /> 

• **addMovement**(`direction`): `void` 

沿着给定的方向向量添加移动输入。不会自动应用移动，由开发者在 onUpdate 事件中执行此操作。效果受 movementDirection 属性影响。如果此时同时有用户输入效果是叠加而不是覆盖。

#### Parameters

| `direction` [`Vector`](mw.Vector.md) | 输入的方向 |
| :------ | :------ |


<span style="font-size: 14px;">
使用示例:将使用到的资源:"27693"拖入优先加载栏。创建一个名为"Example_Character_AddMovement"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中生成一个循环黑洞特效。如果角色与黑洞中心距离小于300且角色没有开启布娃娃，则朝中心移动角色。如果角色与黑洞中心距离小于50，则开启布娃娃。你可以看到角色开关布娃娃的不同效果代码如下：
</span>

```ts
@Component
export default class Example_Character_AddMovement extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            this.useUpdate = true;
            // 生成一个黑洞特效循环播放
            EffectService.playAtPosition("27693", new Vector(500, 0, 50), {loopCount: 0});
        }
    }
    // 周期函数每帧执行，此函数执行需要将this.useUpdate赋值为true，dt是当前帧与上一帧的延迟（秒）
    protected onUpdate(dt: number): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 如果角色与黑洞中心距离小于300且角色没有开启布娃娃，则朝中心移动角色
            if(myCharacter.worldTransform.position.subtract(new Vector(500, 0, 50)).length < 300 && !myCharacter.ragdollEnabled) {
                let dir = new Vector(500, 0, 50).subtract(myCharacter.worldTransform.position).normalize();
                myCharacter.addMovement(new Vector(dir.x, dir.y, 0));
            }
            // 如果角色与黑洞中心距离小于50，则开启布娃娃
            if(myCharacter.worldTransform.position.subtract(new Vector(500, 0, 50)).length < 50) {
                myCharacter.ragdollEnabled = true;
                setTimeout(() => {
                    myCharacter.worldTransform.position = new Vector(0, 0, 130);
                    myCharacter.ragdollEnabled = false;
                }, 2000);
            }
        }
    }
}
```

___

### attachToSlot <Score text="attachToSlot" /> 

• **attachToSlot**(`gameObject`, `slotName`): `void` 

将物体附着到人物角色的指定插槽。只适用于人形角色，附加规则是 KeepRelative，会保留物体之前的 localTransform

#### Parameters

| `gameObject` [`GameObject`](mw.GameObject.md) |  被附着的物体 |
| :------ | :------ |
| `slotName` [`HumanoidSlotType`](../enums/mw.HumanoidSlotType.md)  [`NonHumanoidSlotType`](../enums/mw.NonHumanoidSlotType.md) |  插槽名字，被附着到指定的插槽名 |


<span style="font-size: 14px;">
使用示例:将使用到的资源:"27704,29052,118149,122953,26168"拖入优先加载栏。创建一个名为"Example_Character_AttachToSlot"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“1”，添加 / 移除角色的头顶光环。按下键盘“2”，给角色插槽装备模型。按下键盘“3”，将角色左手，右手，左背的插槽挂载的对象全部移除。按下键盘“4”，在角色头顶顶点0位置和头顶UI位置分别生成一个特效。代码如下：
</span>

```ts
@Component
export default class Example_Character_AttachToSlot extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            let halo = null;
            // 添加一个按键方法：按下键盘“1”，添加 / 移除角色的头顶光环
            InputUtil.onKeyDown(Keys.One, () => {
                if(halo) {
                    myCharacter.detachFromSlot(halo);
                    setTimeout(() => {
                        halo.destroy();
                        halo = null;
                    }, 1000);
                } else {
                    // 在角色头顶生成一个光环并附加到头顶插槽
                    halo = GameObject.spawn("27704") as Effect;
                    myCharacter.attachToSlot(halo, HumanoidSlotType.Rings);
                    halo.play();
                }
            });
            // 生成三件装备
            let sword = GameObject.spawn("29052",{transform: new Transform(new Vector(300, -100, 100), Rotation.zero, Vector.one)});
            let shield = GameObject.spawn("118149",{transform: new Transform(new Vector(300, 0, 100), Rotation.zero, Vector.one)});
            let spike = GameObject.spawn("122953",{transform: new Transform(new Vector(300, 100, 100), Rotation.zero, Vector.one)});
            // 添加一个按键方法：按下键盘“2”，给角色插槽增加装备
            InputUtil.onKeyDown(Keys.Two, () => {
                myCharacter.attachToSlot(sword, HumanoidSlotType.RightHand);
                myCharacter.attachToSlot(shield, HumanoidSlotType.LeftHand);
                myCharacter.attachToSlot(spike, HumanoidSlotType.LeftBack);
            });
            // 添加一个按键方法：按下键盘“3”，将角色左手，右手，左背的插槽挂载的对象全部移除
            InputUtil.onKeyDown(Keys.Three, () => {
                myCharacter.detachAllFromSlot();
                sword.worldTransform = new Transform(new Vector(300, -100, 100), Rotation.zero, Vector.one);
                shield.worldTransform = new Transform(new Vector(300, 0, 100), Rotation.zero, Vector.one);
                spike.worldTransform = new Transform(new Vector(300, 100, 100), Rotation.zero, Vector.one);
            });
            // 添加一个按键方法：按下键盘“4”，在角色头顶顶点0位置和头顶UI位置分别生成一个特效
            InputUtil.onKeyDown(Keys.Four, () => {
                let pos = myCharacter.getVertexPosition(0);
                if(pos) {
                    let zzz = GameObject.spawn("26168") as Effect;
                    zzz.worldTransform.position = pos;
                    zzz.play(() => {
                        zzz.destroy();
                    });
                }
                pos = myCharacter.getSlotWorldPosition(HumanoidSlotType.Rings);
                if(pos) {
                    let zzz = GameObject.spawn("26168") as Effect;
                    zzz.worldTransform.position = pos;
                    zzz.play(() => {
                        zzz.destroy();
                    });
                }
            });
        }
    }
}
```

___

### cancelHeadFollow <Score text="cancelHeadFollow" /> 

• **cancelHeadFollow**(): `void` <Badge type="tip" text="client" />

取消头部追踪


___

### changeState <Score text="changeState" /> 

• **changeState**(`stateType`): `void` 

改变角色的状态

#### Parameters

| `stateType` [`CharacterStateType`](../enums/mw.CharacterStateType.md) |  新的状态 使用示例: 按0-9，Z、X、C、V后查看当前角色状态 ``` |
| :------ | :------ |


___

### clearDescription <Score text="clearDescription" /> 

• **clearDescription**(`appearance?`, `slotAndDecoration?`): `void` 

清空角色外观数据。清空角色外观数据，此时角色不具备任何视觉表现。

#### Parameters

| `appearance?` `boolean` | 是否清空形象数据 default:true |
| :------ | :------ |
| `slotAndDecoration?` `boolean` | 是否清空插槽和物品数据 default:true |


<span style="font-size: 14px;">
使用示例:将使用到的资源:"14521,35391,161245,75674,57731,63910,58694,58700,60384,58696,136183"拖入优先加载栏。创建一个名为"Example_Character"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中看到玩家控制角色玩家外观准备未完成播放摊手的效果。【角色外观描述完成】委托添加函数来播放换装完成特效，并保存角色初始默认外观数据。【角色外观描述变化】委托添加函数在控制台打印当前角色外观描述变化的具体子项和索引。按下键盘“1”，重置为默认角色外观。按下键盘“2”，修改角色外观。按下键盘“3”，同步角色外观。按下键盘“4”，清空角色外观。代码如下：
</span>

```ts
@Component
export default class Example_Character extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端玩家
            let myPlayer = Player.localPlayer;
            // 获取玩家控制角色
            let myCharacter = myPlayer.character;
            // 如果玩家外观准备完成挥手，反之摊手
            if(myCharacter.isDescriptionReady) {
                let animation = myCharacter.loadAnimation("35391");
                animation.play();
            } else {
                let animation = myCharacter.loadAnimation("14521");
                animation.play();
            }
            let defaultStyle = null;
            // 给【角色外观描述完成】委托添加函数
            myCharacter.onDescriptionComplete.add(() => {
                // 播放换装完成特效
                EffectService.playOnGameObject("161245", myCharacter, {slotType: HumanoidSlotType.Root});
                // 获取角色默认外观风格
                if(defaultStyle == null) {
                    defaultStyle = myCharacter.getDescription();
                }
            });
            // 给【角色外观描述变化】委托添加函数
            myCharacter.onDescriptionChange.add((operationCode: number, index: number, value: unknown) => {
                console.log("Appearance Changed");
                console.log("OperationCode " + operationCode + " Index " + index);
            });
            // 添加一个按键方法:按下键盘“1”，重置为默认角色外观
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.setDescription(defaultStyle);
            });
            // 添加一个按键方法:按下键盘“2”，修改角色外观
            InputUtil.onKeyDown(Keys.Two, () => {
                if(myCharacter.characterType == CharacterType.HumanoidV2) {
                    // 修改角色style头部:头大小为1.5倍
                    myCharacter.description.advance.headFeatures.head.headOverallScale = 1.5;
                    // 修改角色style体型:身高为1.2倍
                    myCharacter.description.advance.bodyFeatures.body.height = 1.2;
                    // 修改角色style化妆:腮红为75674
                    myCharacter.description.advance.makeup.blush.blushStyle = "75674";
                    // 修改角色style头发:前发为57731，后发为63910
                    myCharacter.description.advance.hair.frontHair.style = "57731";
                    myCharacter.description.advance.hair.backHair.style = "63910";
                    // 修改角色style:上衣为58694，下衣为58700，手套为60384，鞋子为58696
                    myCharacter.description.advance.clothing.upperCloth.style = "58694";
                    myCharacter.description.advance.clothing.lowerCloth.style = "58700";
                    myCharacter.description.advance.clothing.gloves.style = "60384";
                    myCharacter.description.advance.clothing.shoes.style = "58696";
                }
            });
            // 添加一个按键方法:按下键盘“3”，同步角色外观
            InputUtil.onKeyDown(Keys.Three, () => {
                myCharacter.syncDescription();
            });
            // 添加一个按键方法:按下键盘“4”，清空角色外观
            InputUtil.onKeyDown(Keys.Four, () => {
                myCharacter.clearDescription();
            });
        }
    }
}
```

___

### detachAllFromSlot <Score text="detachAllFromSlot" /> 

• **detachAllFromSlot**(`param?`): `void` 

将角色插槽附着的对象全部分离。如果不填入插槽则将全部插槽的附着对象分离。仅对高级人型角色生效。

#### Parameters

| `param?` `Object` |  (可选参数)插槽数据，以下两个为 param 的数据结构 slotName: mw.HumanoidSlotType; isDestroy: boolean <br> default:null |
| :------ | :------ |
| `param.isDestroy?` `boolean` |  是否销毁这些分离的插槽 |
| `param.slotName?` [`HumanoidSlotType`](../enums/mw.HumanoidSlotType.md) | 分离的插槽名称 |


<span style="font-size: 14px;">
使用示例:将使用到的资源:"27704,29052,118149,122953,26168"拖入优先加载栏。创建一个名为"Example_Character_DetachAllFromSlot"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“1”，添加 / 移除角色的头顶光环。按下键盘“2”，给角色插槽装备模型。按下键盘“3”，将角色左手，右手，左背的插槽挂载的对象全部移除。按下键盘“4”，在角色头顶顶点0位置和头顶UI位置分别生成一个特效。代码如下：
</span>

```ts
@Component
export default class Example_Character_DetachAllFromSlot extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            let halo = null;
            // 添加一个按键方法：按下键盘“1”，添加 / 移除角色的头顶光环
            InputUtil.onKeyDown(Keys.One, () => {
                if(halo) {
                    myCharacter.detachFromSlot(halo);
                    setTimeout(() => {
                        halo.destroy();
                        halo = null;
                    }, 1000);
                } else {
                    // 在角色头顶生成一个光环并附加到头顶插槽
                    halo = GameObject.spawn("27704") as Effect;
                    myCharacter.attachToSlot(halo, HumanoidSlotType.Rings);
                    halo.play();
                }
            });
            // 生成三件装备
            let sword = GameObject.spawn("29052",{transform: new Transform(new Vector(300, -100, 100), Rotation.zero, Vector.one)});
            let shield = GameObject.spawn("118149",{transform: new Transform(new Vector(300, 0, 100), Rotation.zero, Vector.one)});
            let spike = GameObject.spawn("122953",{transform: new Transform(new Vector(300, 100, 100), Rotation.zero, Vector.one)});
            // 添加一个按键方法：按下键盘“2”，给角色插槽增加装备
            InputUtil.onKeyDown(Keys.Two, () => {
                myCharacter.attachToSlot(sword, HumanoidSlotType.RightHand);
                myCharacter.attachToSlot(shield, HumanoidSlotType.LeftHand);
                myCharacter.attachToSlot(spike, HumanoidSlotType.LeftBack);
            });
            // 添加一个按键方法：按下键盘“3”，将角色左手，右手，左背的插槽挂载的对象全部移除
            InputUtil.onKeyDown(Keys.Three, () => {
                myCharacter.detachAllFromSlot();
                sword.worldTransform = new Transform(new Vector(300, -100, 100), Rotation.zero, Vector.one);
                shield.worldTransform = new Transform(new Vector(300, 0, 100), Rotation.zero, Vector.one);
                spike.worldTransform = new Transform(new Vector(300, 100, 100), Rotation.zero, Vector.one);
            });
            // 添加一个按键方法：按下键盘“4”，在角色头顶顶点0位置和头顶UI位置分别生成一个特效
            InputUtil.onKeyDown(Keys.Four, () => {
                let pos = myCharacter.getVertexPosition(0);
                if(pos) {
                    let zzz = GameObject.spawn("26168") as Effect;
                    zzz.worldTransform.position = pos;
                    zzz.play(() => {
                        zzz.destroy();
                    });
                }
                pos = myCharacter.getSlotWorldPosition(HumanoidSlotType.Rings);
                if(pos) {
                    let zzz = GameObject.spawn("26168") as Effect;
                    zzz.worldTransform.position = pos;
                    zzz.play(() => {
                        zzz.destroy();
                    });
                }
            });
        }
    }
}
```

___

### detachFromSlot <Score text="detachFromSlot" /> 

• **detachFromSlot**(`gameObject`): `void` 

将物体从插槽中分离

#### Parameters

| `gameObject` [`GameObject`](mw.GameObject.md) |  物体GameObject |
| :------ | :------ |


<span style="font-size: 14px;">
使用示例:将使用到的资源:"27704,29052,118149,122953,26168"拖入优先加载栏。创建一个名为"Example_Character_DetachFromSlot"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“1”，添加 / 移除角色的头顶光环。按下键盘“2”，给角色插槽装备模型。按下键盘“3”，将角色左手，右手，左背的插槽挂载的对象全部移除。按下键盘“4”，在角色头顶顶点0位置和头顶UI位置分别生成一个特效。代码如下：
</span>

```ts
@Component
export default class Example_Character_DetachFromSlot extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            let halo = null;
            // 添加一个按键方法：按下键盘“1”，添加 / 移除角色的头顶光环
            InputUtil.onKeyDown(Keys.One, () => {
                if(halo) {
                    myCharacter.detachFromSlot(halo);
                    setTimeout(() => {
                        halo.destroy();
                        halo = null;
                    }, 1000);
                } else {
                    // 在角色头顶生成一个光环并附加到头顶插槽
                    halo = GameObject.spawn("27704") as Effect;
                    myCharacter.attachToSlot(halo, HumanoidSlotType.Rings);
                    halo.play();
                }
            });
            // 生成三件装备
            let sword = GameObject.spawn("29052",{transform: new Transform(new Vector(300, -100, 100), Rotation.zero, Vector.one)});
            let shield = GameObject.spawn("118149",{transform: new Transform(new Vector(300, 0, 100), Rotation.zero, Vector.one)});
            let spike = GameObject.spawn("122953",{transform: new Transform(new Vector(300, 100, 100), Rotation.zero, Vector.one)});
            // 添加一个按键方法：按下键盘“2”，给角色插槽增加装备
            InputUtil.onKeyDown(Keys.Two, () => {
                myCharacter.attachToSlot(sword, HumanoidSlotType.RightHand);
                myCharacter.attachToSlot(shield, HumanoidSlotType.LeftHand);
                myCharacter.attachToSlot(spike, HumanoidSlotType.LeftBack);
            });
            // 添加一个按键方法：按下键盘“3”，将角色左手，右手，左背的插槽挂载的对象全部移除
            InputUtil.onKeyDown(Keys.Three, () => {
                myCharacter.detachAllFromSlot();
                sword.worldTransform = new Transform(new Vector(300, -100, 100), Rotation.zero, Vector.one);
                shield.worldTransform = new Transform(new Vector(300, 0, 100), Rotation.zero, Vector.one);
                spike.worldTransform = new Transform(new Vector(300, 100, 100), Rotation.zero, Vector.one);
            });
            // 添加一个按键方法：按下键盘“4”，在角色头顶顶点0位置和头顶UI位置分别生成一个特效
            InputUtil.onKeyDown(Keys.Four, () => {
                let pos = myCharacter.getVertexPosition(0);
                if(pos) {
                    let zzz = GameObject.spawn("26168") as Effect;
                    zzz.worldTransform.position = pos;
                    zzz.play(() => {
                        zzz.destroy();
                    });
                }
                pos = myCharacter.getSlotWorldPosition(HumanoidSlotType.Rings);
                if(pos) {
                    let zzz = GameObject.spawn("26168") as Effect;
                    zzz.worldTransform.position = pos;
                    zzz.play(() => {
                        zzz.destroy();
                    });
                }
            });
        }
    }
}
```

___

### getAttachmentsFromSlot <Score text="getAttachmentsFromSlot" /> 

• **getAttachmentsFromSlot**(`slotName`): [`GameObject`](mw.GameObject.md)[] 

获取附着到人物角色指定插槽的所有物体。只适用于人形角色，附加规则是 KeepRelative，会保留物体之前的 localTransform

#### Parameters

| `slotName` [`HumanoidSlotType`](../enums/mw.HumanoidSlotType.md)  [`NonHumanoidSlotType`](../enums/mw.NonHumanoidSlotType.md) |  插槽名字，被附着到指定的插槽名 |
| :------ | :------ |

#### Returns

| [`GameObject`](mw.GameObject.md)[] | 符合条件的物体数组 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:将使用到的资源:"27704,29052,118149,122953,26168"拖入优先加载栏。创建一个名为"Example_Character_AttachToSlot"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“1”，添加 / 移除角色的头顶光环。按下键盘“2”，给角色插槽装备模型。按下键盘“3”，将角色左手，右手，左背的插槽挂载的对象全部移除。按下键盘“4”，在角色头顶顶点0位置和头顶UI位置分别生成一个特效。代码如下：
</span>

```ts
@Component
export default class Example_Character_AttachToSlot extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            let halo = null;
            // 添加一个按键方法：按下键盘“1”，添加 / 移除角色的头顶光环
            InputUtil.onKeyDown(Keys.One, () => {
                if(halo) {
                    myCharacter.detachFromSlot(halo);
                    setTimeout(() => {
                        halo.destroy();
                        halo = null;
                    }, 1000);
                } else {
                    // 在角色头顶生成一个光环并附加到头顶插槽
                    halo = GameObject.spawn("27704") as Effect;
                    myCharacter.attachToSlot(halo, HumanoidSlotType.Rings);
                    halo.play();
                }
            });
            // 生成三件装备
            let sword = GameObject.spawn("29052",{transform: new Transform(new Vector(300, -100, 100), Rotation.zero, Vector.one)});
            let shield = GameObject.spawn("118149",{transform: new Transform(new Vector(300, 0, 100), Rotation.zero, Vector.one)});
            let spike = GameObject.spawn("122953",{transform: new Transform(new Vector(300, 100, 100), Rotation.zero, Vector.one)});
            // 添加一个按键方法：按下键盘“2”，给角色插槽增加装备
            InputUtil.onKeyDown(Keys.Two, () => {
                myCharacter.attachToSlot(sword, HumanoidSlotType.RightHand);
                myCharacter.attachToSlot(shield, HumanoidSlotType.LeftHand);
                myCharacter.attachToSlot(spike, HumanoidSlotType.LeftBack);
            });
            // 添加一个按键方法：按下键盘“3”，将角色左手，右手，左背的插槽挂载的对象全部移除
            InputUtil.onKeyDown(Keys.Three, () => {
                myCharacter.detachAllFromSlot();
                sword.worldTransform = new Transform(new Vector(300, -100, 100), Rotation.zero, Vector.one);
                shield.worldTransform = new Transform(new Vector(300, 0, 100), Rotation.zero, Vector.one);
                spike.worldTransform = new Transform(new Vector(300, 100, 100), Rotation.zero, Vector.one);
            });
            // 添加一个按键方法：按下键盘“4”，在角色头顶顶点0位置和头顶UI位置分别生成一个特效
            InputUtil.onKeyDown(Keys.Four, () => {
                let pos = myCharacter.getVertexPosition(0);
                if(pos) {
                    let zzz = GameObject.spawn("26168") as Effect;
                    zzz.worldTransform.position = pos;
                    zzz.play(() => {
                        zzz.destroy();
                    });
                }
                pos = myCharacter.getSlotWorldPosition(HumanoidSlotType.Rings);
                if(pos) {
                    let zzz = GameObject.spawn("26168") as Effect;
                    zzz.worldTransform.position = pos;
                    zzz.play(() => {
                        zzz.destroy();
                    });
                }
            });
        }get
    }
}
```

___

### getCenterVertexByMorphName <Score text="getCenterVertexByMorphName" /> 

• **getCenterVertexByMorphName**(`morphName`): [`Vector`](mw.Vector.md) 

通过头部模型MorphName实时获取中心顶点位置

#### Parameters

| `morphName` `string` |  MorphName range: 无 |
| :------ | :------ |

#### Returns

| [`Vector`](mw.Vector.md) | 顶点位置 |
| :------ | :------ |

___

### getCurrentState <Score text="getCurrentState" /> 

• **getCurrentState**(): [`CharacterStateType`](../enums/mw.CharacterStateType.md) 

获取当前角色的状态

#### Returns

| [`CharacterStateType`](../enums/mw.CharacterStateType.md) | 当前角色状态 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:按E后查看当前状态打印
</span>

```ts
@Component
export default class NewScript1 extends Script {
    private character: Character;
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        Player.asyncGetLocalPlayer().then((player) => {
            this.character = player.character;
            this.character.onStateChanged.add((pre, curr)=>{
                console.log(`pre: ${pre} curr: ${curr}`);
            })
        });
      InputUtil.onKeyDown(Keys.Zero, ()=>{
            this.character.changeState(CharacterStateType.None);
        })
        InputUtil.onKeyDown(Keys.One, ()=>{
            this.character.changeState(CharacterStateType.Running);
        })
        InputUtil.onKeyDown(Keys.Two, ()=>{
            this.character.changeState(CharacterStateType.Flying);
        })
        InputUtil.onKeyDown(Keys.Three, ()=>{
            this.character.changeState(CharacterStateType.Swimming);
        })
        InputUtil.onKeyDown(Keys.Four, ()=>{
            this.character.changeState(CharacterStateType.Jumping);
        })
        InputUtil.onKeyDown(Keys.Five, ()=>{
            this.character.changeState(CharacterStateType.Freefall);
        })
        InputUtil.onKeyDown(Keys.Six, ()=>{
            this.character.changeState(CharacterStateType.Ragdoll);
        })
        InputUtil.onKeyDown(Keys.Seven, ()=>{
            this.character.changeState(CharacterStateType.GettingUp);
        })
        InputUtil.onKeyDown(Keys.Eight, ()=>{
            this.character.changeState(CharacterStateType.Climbing);
        })
        InputUtil.onKeyDown(Keys.Nine, ()=>{
            this.character.changeState(CharacterStateType.Crouching);
        })
        InputUtil.onKeyDown(Keys.Z, ()=>{
            this.character.changeState(CharacterStateType.Pushed);
        })
        InputUtil.onKeyDown(Keys.X, ()=>{
            this.character.changeState(CharacterStateType.Landed);
        })
        InputUtil.onKeyDown(Keys.C, ()=>{
            this.character.changeState(CharacterStateType.Hit);
        })
        InputUtil.onKeyDown(Keys.V, ()=>{
            this.character.changeState(CharacterStateType.Dead);
        })
        InputUtil.onKeyDown(Keys.E, ()=>{
            console.log("currentState=="+this.character.getCurrentState());
        })
    }
}
```

___

### getDescription <Score text="getDescription" /> 

• **getDescription**(): [`CharacterDescription`](mw.CharacterDescription.md) 

获取角色外观数据。该接口获取角色当前外观数据的拷贝

#### Returns

| [`CharacterDescription`](mw.CharacterDescription.md) | 角色外观数据的拷贝 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:将使用到的资源:"14521,35391,161245,75674,57731,63910,58694,58700,60384,58696,136183"拖入优先加载栏。创建一个名为"Example_Character"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中看到玩家控制角色玩家外观准备未完成播放摊手的效果。【角色外观描述完成】委托添加函数来播放换装完成特效，并保存角色初始默认外观数据。【角色外观描述变化】委托添加函数在控制台打印当前角色外观描述变化的具体子项和索引。按下键盘“1”，重置为默认角色外观。按下键盘“2”，修改角色外观。按下键盘“3”，同步角色外观。按下键盘“4”，清空角色外观。代码如下：
</span>

```ts
@Component
export default class Example_Character extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端玩家
            let myPlayer = Player.localPlayer;
            // 获取玩家控制角色
            let myCharacter = myPlayer.character;
            // 如果玩家外观准备完成挥手，反之摊手
            if(myCharacter.isDescriptionReady) {
                let animation = myCharacter.loadAnimation("35391");
                animation.play();
            } else {
                let animation = myCharacter.loadAnimation("14521");
                animation.play();
            }
            let defaultStyle = null;
            // 给【角色外观描述完成】委托添加函数
            myCharacter.onDescriptionComplete.add(() => {
                // 播放换装完成特效
                EffectService.playOnGameObject("161245", myCharacter, {slotType: HumanoidSlotType.Root});
                // 获取角色默认外观风格
                if(defaultStyle == null) {
                    defaultStyle = myCharacter.getDescription();
                }
            });
            // 给【角色外观描述变化】委托添加函数
            myCharacter.onDescriptionChange.add((operationCode: number, index: number, value: unknown) => {
                console.log("Appearance Changed");
                console.log("OperationCode " + operationCode + " Index " + index);
            });
            // 添加一个按键方法:按下键盘“1”，重置为默认角色外观
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.setDescription(defaultStyle);
            });
            // 添加一个按键方法:按下键盘“2”，修改角色外观
            InputUtil.onKeyDown(Keys.Two, () => {
                if(myCharacter.characterType == CharacterType.HumanoidV2) {
                    // 修改角色style头部:头大小为1.5倍
                    myCharacter.description.advance.headFeatures.head.headOverallScale = 1.5;
                    // 修改角色style体型:身高为1.2倍
                    myCharacter.description.advance.bodyFeatures.body.height = 1.2;
                    // 修改角色style化妆:腮红为75674
                    myCharacter.description.advance.makeup.blush.blushStyle = "75674";
                    // 修改角色style头发:前发为57731，后发为63910
                    myCharacter.description.advance.hair.frontHair.style = "57731";
                    myCharacter.description.advance.hair.backHair.style = "63910";
                    // 修改角色style:上衣为58694，下衣为58700，手套为60384，鞋子为58696
                    myCharacter.description.advance.clothing.upperCloth.style = "58694";
                    myCharacter.description.advance.clothing.lowerCloth.style = "58700";
                    myCharacter.description.advance.clothing.gloves.style = "60384";
                    myCharacter.description.advance.clothing.shoes.style = "58696";
                }
            });
            // 添加一个按键方法:按下键盘“3”，同步角色外观
            InputUtil.onKeyDown(Keys.Three, () => {
                myCharacter.syncDescription();
            });
            // 添加一个按键方法:按下键盘“4”，清空角色外观
            InputUtil.onKeyDown(Keys.Four, () => {
                myCharacter.clearDescription();
            });
        }
    }
}
```

___

### getSlotWorldPosition <Score text="getSlotWorldPosition" /> 

• **getSlotWorldPosition**(`slotName`): [`Vector`](mw.Vector.md) 

获取角色插槽的世界坐标。受角色外观中插槽偏移影响，仅对高级人型角色生效。

#### Parameters

| `slotName` [`HumanoidSlotType`](../enums/mw.HumanoidSlotType.md) | 插槽名字 |
| :------ | :------ |

#### Returns

| [`Vector`](mw.Vector.md) | 坐标位置 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:将使用到的资源:"27704,29052,118149,122953,26168"拖入优先加载栏。创建一个名为"Example_Character_GetSlotWorldPosition"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“1”，添加 / 移除角色的头顶光环。按下键盘“2”，给角色插槽装备模型。按下键盘“3”，将角色左手，右手，左背的插槽挂载的对象全部移除。按下键盘“4”，在角色头顶顶点0位置和头顶UI位置分别生成一个特效。代码如下：
</span>

```ts
@Component
export default class Example_Character_GetSlotWorldPosition extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            let halo = null;
            // 添加一个按键方法：按下键盘“1”，添加 / 移除角色的头顶光环
            InputUtil.onKeyDown(Keys.One, () => {
                if(halo) {
                    myCharacter.detachFromSlot(halo);
                    setTimeout(() => {
                        halo.destroy();
                        halo = null;
                    }, 1000);
                } else {
                    // 在角色头顶生成一个光环并附加到头顶插槽
                    halo = GameObject.spawn("27704") as Effect;
                    myCharacter.attachToSlot(halo, HumanoidSlotType.Rings);
                    halo.play();
                }
            });
            // 生成三件装备
            let sword = GameObject.spawn("29052",{transform: new Transform(new Vector(300, -100, 100), Rotation.zero, Vector.one)});
            let shield = GameObject.spawn("118149",{transform: new Transform(new Vector(300, 0, 100), Rotation.zero, Vector.one)});
            let spike = GameObject.spawn("122953",{transform: new Transform(new Vector(300, 100, 100), Rotation.zero, Vector.one)});
            // 添加一个按键方法：按下键盘“2”，给角色插槽增加装备
            InputUtil.onKeyDown(Keys.Two, () => {
                myCharacter.attachToSlot(sword, HumanoidSlotType.RightHand);
                myCharacter.attachToSlot(shield, HumanoidSlotType.LeftHand);
                myCharacter.attachToSlot(spike, HumanoidSlotType.LeftBack);
            });
            // 添加一个按键方法：按下键盘“3”，将角色左手，右手，左背的插槽挂载的对象全部移除
            InputUtil.onKeyDown(Keys.Three, () => {
                myCharacter.detachAllFromSlot();
                sword.worldTransform = new Transform(new Vector(300, -100, 100), Rotation.zero, Vector.one);
                shield.worldTransform = new Transform(new Vector(300, 0, 100), Rotation.zero, Vector.one);
                spike.worldTransform = new Transform(new Vector(300, 100, 100), Rotation.zero, Vector.one);
            });
            // 添加一个按键方法：按下键盘“4”，在角色头顶顶点0位置和头顶UI位置分别生成一个特效
            InputUtil.onKeyDown(Keys.Four, () => {
                let pos = myCharacter.getVertexPosition(0);
                if(pos) {
                    let zzz = GameObject.spawn("26168") as Effect;
                    zzz.worldTransform.position = pos;
                    zzz.play(() => {
                        zzz.destroy();
                    });
                }
                pos = myCharacter.getSlotWorldPosition(HumanoidSlotType.Rings);
                if(pos) {
                    let zzz = GameObject.spawn("26168") as Effect;
                    zzz.worldTransform.position = pos;
                    zzz.play(() => {
                        zzz.destroy();
                    });
                }
            });
        }
    }
}
```

___

### getVertexArrayByMorphName <Score text="getVertexArrayByMorphName" /> 

• **getVertexArrayByMorphName**(`morphName`): [`Vector`](mw.Vector.md)[] 

通过头部模型MorphName实时获取所有顶点位置

#### Parameters

| `morphName` `string` |  MorphName range: morph名字 |
| :------ | :------ |

#### Returns

| [`Vector`](mw.Vector.md)[] | 顶点位置数组 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:将使用到的资源:"27704,29052,118149,122953,26168"拖入优先加载栏。创建一个名为"Example_Character_GetVertexPosition"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“1”，添加 / 移除角色的头顶光环。按下键盘“2”，给角色插槽装备模型。按下键盘“3”，将角色左手，右手，左背的插槽挂载的对象全部移除。按下键盘“4”，在角色头顶顶点0位置和头顶UI位置分别生成一个特效。代码如下：
</span>

```ts
@Component
export default class Example_Character_GetVertexPosition extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    *    private character: Character;
   private obj: Model;
   protected onStart(): void {
       this.useUpdate = true;
       Player.asyncGetLocalPlayer().then((player)=>{
           this.character = player.character;
       })
       GameObject.asyncSpawn("84121").then((obj)=>{
           this.obj = obj as Model;
           this.obj.worldTransform.scale = new Vector(0.1,0.1,0.1);
           this.obj.setCollision(CollisionStatus.Off);
       })
   }
   protected onUpdate(dt: number): void {
       if (this.character && this.obj) {
           this.obj.worldTransform.position = this.character.getVertexArrayByMorphName("EarOverallScale")[0];
       }
   }
}
```

___

### getVertexPosition <Score text="getVertexPosition" /> 

• **getVertexPosition**(`index`): [`Vector`](mw.Vector.md) 

通过头部模型顶点 index 实时获取顶点位置。目前顶点 index 只能从内部工程中查看

#### Parameters

| `index` `number` |  模型顶点 index <br> range: 根据骨架网格物体顶点的数据而定。 type:整数 |
| :------ | :------ |

#### Returns

| [`Vector`](mw.Vector.md) | 顶点位置 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:将使用到的资源:"27704,29052,118149,122953,26168"拖入优先加载栏。创建一个名为"Example_Character_GetVertexPosition"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“1”，添加 / 移除角色的头顶光环。按下键盘“2”，给角色插槽装备模型。按下键盘“3”，将角色左手，右手，左背的插槽挂载的对象全部移除。按下键盘“4”，在角色头顶顶点0位置和头顶UI位置分别生成一个特效。代码如下：
</span>

```ts
@Component
export default class Example_Character_GetVertexPosition extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    *    private character: Character;
   private obj: Model;
   protected onStart(): void {
       this.useUpdate = true;
       Player.asyncGetLocalPlayer().then((player)=>{
           this.character = player.character;
       })
       GameObject.asyncSpawn("84121").then((obj)=>{
           this.obj = obj as Model;
           this.obj.worldTransform.scale = new Vector(0.1,0.1,0.1);
           this.obj.setCollision(CollisionStatus.Off);
       })
   }
   protected onUpdate(dt: number): void {
       if (this.character && this.obj) {
           this.obj.worldTransform.position = this.character.getVertexPosition(0);
       }
   }
}
```

___

### headFollow <Score text="headFollow" /> 

• **headFollow**(`target`): `void` <Badge type="tip" text="client" />

头部追踪

#### Parameters

| `target` ``null``  [`GameObject`](mw.GameObject.md)  [`Vector`](mw.Vector.md) |  追踪点或者追踪对象 |
| :------ | :------ |


___

### jump <Score text="jump" /> 

• **jump**(): `void` 

使角色触发一个跳跃行为


<span style="font-size: 14px;">
使用示例:创建一个名为"Example_Character_Jump"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，设置角色最大跳跃高度为300，最高三连跳。按下键盘“1”，角色跳跃。按下键盘“2”，启用/禁用跳跃能力。你将在场景中看到角色禁用跳跃能力的效果。代码如下：
</span>

```ts
@Component
export default class Example_Character_Jump extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 最大跳跃高度为300
            myCharacter.maxJumpHeight = 300;
            // 最高三连跳
            myCharacter.jumpMaxCount = 3;
            // 添加一个按键方法：按下键盘“1”，角色跳跃。
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.jump();
                console.log("当前角色是否在跳跃 " + myCharacter.isJumping);
            });
            // 添加一个按键方法：按下键盘“2”，启用/禁用跳跃能力。
            InputUtil.onKeyDown(Keys.Two, () => {
                myCharacter.jumpEnabled = !myCharacter.jumpEnabled;
                console.log("当前角色跳跃能力 " + myCharacter.jumpEnabled);
            });
        }
    }
}
```

___

### loadAnimation <Score text="loadAnimation" /> 

• **loadAnimation**(`assetId`): [`Animation`](mw.Animation.md) 

为角色加载一个动画资源。该接口会将给定的动画加载到角色上，返回一个可播放的Animation。

#### Parameters

| `assetId` `string` | 动画资源 ID（编辑器左侧栏动画，选中某一个动画资源右键可复制资源ID） <br> range:字符串长度根据具体的资源 ID 而定 |
| :------ | :------ |

#### Returns

| [`Animation`](mw.Animation.md) | 动画对象 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:将使用到的资源:"14700,20380"拖入优先加载栏。创建一个名为"Example_Character"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，在玩家角色上加载舞蹈动画，并修改循环次数为10，播放速度为2倍。给【动画完成】委托添加函数，当动画播放完成，出现一个升级特效。按下键盘“1”，开始播放动画。按下键盘“2”，暂停播放动画。按下键盘“3”，继续播放动画。按下键盘“4”，停止播放动画。代码如下：
</span>

```ts
@Component
export default class Example_Character extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端玩家
            let myPlayer = Player.localPlayer;
            // 获取玩家控制角色
            let myCharacter = myPlayer.character;
            // 给角色加载一个舞蹈动画
            let danceAnimation = myCharacter.loadAnimation("14700");
            // 动画的属性
            console.log("动画时长 " + danceAnimation.length);
            // 循环播放10次
            danceAnimation.loop = 10;
            // 2倍播放速度
            danceAnimation.speed = 2;
            // 给【动画完成】委托添加函数，播放一个升级特效
            danceAnimation.onFinish.add(() => {
                EffectService.playOnGameObject("20380", myCharacter, {slotType: HumanoidSlotType.Root});
            });
            // 添加一个按键方法:按下键盘“1”，开始播放
            InputUtil.onKeyDown(Keys.One, () => {
                danceAnimation.play();
                console.log("动画播放 " + danceAnimation.isPlaying);
            });
            // 添加一个按键方法:按下键盘“2”，暂停播放
            InputUtil.onKeyDown(Keys.Two, () => {
                danceAnimation.pause();
                console.log("动画播放 " + danceAnimation.isPlaying);
            });
            // 添加一个按键方法:按下键盘“3”，继续播放
            InputUtil.onKeyDown(Keys.Three, () => {
                danceAnimation.resume();
                console.log("动画播放 " + danceAnimation.isPlaying);
            });
            // 添加一个按键方法:按下键盘“4”，停止播放
            InputUtil.onKeyDown(Keys.Four, () => {
                danceAnimation.stop();
                console.log("动画播放 " + danceAnimation.isPlaying);
            });
        }
    }
}
```

___

### loadStance <Score text="loadStance" /> 

• **loadStance**(`assetId`): [`Stance`](mw.Stance.md) 

为角色加载一个基础姿态。loadStance会将给定的基础姿态加载到角色上，返回一个可播放的基础姿态 stance 类型。

#### Parameters

| `assetId` `string` |  基础姿态资源ID <br> range:字符串长度根据具体的资源 ID 而定 |
| :------ | :------ |

#### Returns

| [`Stance`](mw.Stance.md) | 基础姿态对象 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:将使用到的资源:"234423,216081"拖入优先加载栏。创建一个名为"Example_Character"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，按下键盘“1”，切换播放二次元男性基础姿态和二次元女性基础姿态。按下键盘“2”，停止播放基础姿态。代码如下：
</span>

```ts
@Component
export default class Example_Character extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端玩家
            let myPlayer = Player.localPlayer;
            // 获取玩家控制角色
            let myCharacter = myPlayer.character;
            // 给角色加载一个二次元男性基础姿态
            let animeManStance = myCharacter.loadStance("234423");
            console.log("animeManStance assetId " + animeManStance.assetId);
            // 给角色加载一个二次元女性基础姿态（默认）,关闭瞄准偏移
            let animeWomanStance = myCharacter.loadStance("216081");
            animeWomanStance.aimOffsetEnabled = false;
            console.log("animeWomanStance assetId " + animeWomanStance.assetId);
            // 添加一个按键方法：按下键盘“1”，切换播放二次元男性基础姿态和二次元女性基础姿态
            InputUtil.onKeyDown(Keys.One, () => {
                if(myCharacter.currentStance == animeWomanStance) {
                    animeManStance.play();
                    // 开启瞄准偏移
                    animeManStance.aimOffsetEnabled = true;
                } else {
                    animeWomanStance.play();
                    // 关闭瞄准偏移
                    animeWomanStance.aimOffsetEnabled = false;
                }
            });
            // 添加一个按键方法：按下键盘“2”，停止播放基础姿态
            InputUtil.onKeyDown(Keys.Two, () => {
                if(myCharacter.currentStance) {
                    myCharacter.currentStance.stop();
                }
            });
        }
    }
}
```

___

### loadSubStance <Score text="loadSubStance" /> 

• **loadSubStance**(`assetId`): [`SubStance`](mw.SubStance.md) 

为角色加载一个二级姿态

#### Parameters

| `assetId` `string` |  姿态资源 ID 或动画资源 ID <br> range:字符串长度根据具体的资源 ID 而定 |
| :------ | :------ |

#### Returns

| [`SubStance`](mw.SubStance.md) | 二级姿态对象 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:将使用到的资源:"94261,14520"拖入优先加载栏。创建一个名为"Example_Character"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，在玩家角色上加载一个仅上半身的瞄准姿态和一个仅下半身的踢腿姿态。按下键盘“1”，切换播放瞄准姿态和踢腿姿态。按下键盘“2”，停止播放姿态。代码如下：
</span>

```ts
@Component
export default class Example_Character extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端玩家
            let myPlayer = Player.localPlayer;
            // 获取玩家控制角色
            let myCharacter = myPlayer.character;
            // 给角色加载仅上半身瞄准姿态
            let aimStance = myCharacter.loadSubStance("94261");
            aimStance.blendMode = StanceBlendMode.BlendUpper;
            console.log("aimStance assetId " + aimStance.assetId);
            // 给角色加载仅下半身踢腿姿态
            let kickStance = myCharacter.loadSubStance("14520");
            kickStance.blendMode = StanceBlendMode.BlendLower;
            console.log("kickStance assetId " + kickStance.assetId);
            // 添加一个按键方法:按下键盘“1”，切换播放瞄准姿态和踢腿姿态
            InputUtil.onKeyDown(Keys.One, () => {
                if(myCharacter.currentSubStance == aimStance) {
                    kickStance.play();
                } else {
                    aimStance.play();
                }
            });
            // 添加一个按键方法:按下键盘“2”，停止播放姿态
            InputUtil.onKeyDown(Keys.Two, () => {
                if(myCharacter.currentSubStance) {
                    myCharacter.currentSubStance.stop();
                }
            });
        }
    }
}
```

___

### setCollisionShapeAndExtent <Score text="setCollisionShapeAndExtent" /> 

• **setCollisionShapeAndExtent**(`shapeType`, `collisionExtent`): `void` 

为角色设置不同形状不同大小的碰撞体

#### Parameters

| `shapeType` [`CustomShapeType`](../enums/mw.CustomShapeType.md) |  碰撞体形状（胶囊体、球型、盒型） |
| :------ | :------ |
| `collisionExtent` [`Vector`](mw.Vector.md) |  碰撞体形状的大小 |


<span style="font-size: 14px;">
使用示例:将使用到的资源:"36851"拖入优先加载栏。创建一个名为"Example_Character"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，生成带碰撞的拱门和单端NPC，展示角色碰撞效果。按下键盘“1”，开启/关闭NPC与其他角色的碰撞。按下键盘“2”，开启/关闭NPC是否可被站立。按下键盘“3”，修改角色碰撞形状和大小并打印结果。
</span>

```ts
@Component
export default class Example_Character extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 生成拱门带碰撞的拱门
            let arch = GameObject.spawn("36851",{transform: new Transform(new Vector(300, 210, 0), new Rotation(0, 0, 90), new Vector(2, 1, 2))}) as Model;
            arch.setCollision(CollisionStatus.On);
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 设置角色碰撞属性和跳跃属性
            myCharacter.capsuleCorrectionEnabled = true;
            myCharacter.maxJumpHeight = 250;
            // 生成单端NPC展示角色碰撞
            let NPC = Player.spawnDefaultCharacter();
            NPC.worldTransform.position = new Vector(0, 100, 100);
            // 添加一个按键方法：按下键盘“1”，开启/关闭NPC与其他角色的碰撞
            InputUtil.onKeyDown(Keys.One, () => {
                NPC.collisionWithOtherCharacterEnabled = !NPC.collisionWithOtherCharacterEnabled;
                console.log("NPC与角色的碰撞 " + NPC.collisionWithOtherCharacterEnabled);
            });
            // 添加一个按键方法：按下键盘“2”，开启/关闭角色是否可被站立
            InputUtil.onKeyDown(Keys.Two, () => {
                NPC.canStandOn = !NPC.canStandOn;
                console.log("NPC角色可被站立 " + NPC.canStandOn);
            });
            // 添加一个按键方法：按下键盘“3”，修改角色碰撞并打印结果
            InputUtil.onKeyDown(Keys.Three, () => {
                // 碰撞范围collisionExtent内部值全是半值，半径半高半长
                myCharacter.setCollisionShapeAndExtent(CustomShapeType.Box, new Vector(50, 50, 200));
                console.log("当前角色碰撞 " + myCharacter.collisionShape + " " + myCharacter.collisionExtent);
            });
        }
    }
}
```

___

### setCullDistance <Score text="setCullDistance" /> 

• **setCullDistance**(`inCullDistance`): `void` <Badge type="tip" text="client" />

角色对象裁剪距离

#### Parameters

| `inCullDistance` `number` | 裁剪距离 range: 建议 (2000, 4000) type: 浮点数 |
| :------ | :------ |


最终的裁剪距离会和画质等级有关；修改此属性 ≤0 时，裁剪距离会根据对象尺寸自动调整 (自动启用 CullDistanceVolume 功能)

___

### setDescription <Score text="setDescription" /> 

• **setDescription**(`data`): `void` 

设置角色外观数据。此函数无法更换基础角色。

#### Parameters

| `data` `string`  `string`[]  [`CharacterDescription`](mw.CharacterDescription.md) | 外观数据 |
| :------ | :------ |



<span style="font-size: 14px;">
使用示例:将使用到的资源:"14521,35391,161245,75674,57731,63910,58694,58700,60384,58696,136183"拖入优先加载栏。创建一个名为"Example_Character"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中看到玩家控制角色玩家外观准备未完成播放摊手的效果。【角色外观描述完成】委托添加函数来播放换装完成特效，并保存角色初始默认外观数据。【角色外观描述变化】委托添加函数在控制台打印当前角色外观描述变化的具体子项和索引。按下键盘“1”，重置为默认角色外观。按下键盘“2”，修改角色外观。按下键盘“3”，同步角色外观。按下键盘“4”，清空角色外观。代码如下：
</span>

```ts
@Component
export default class Example_Character extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端玩家
            let myPlayer = Player.localPlayer;
            // 获取玩家控制角色
            let myCharacter = myPlayer.character;
            // 如果玩家外观准备完成挥手，反之摊手
            if(myCharacter.isDescriptionReady) {
                let animation = myCharacter.loadAnimation("35391");
                animation.play();
            } else {
                let animation = myCharacter.loadAnimation("14521");
                animation.play();
            }
            let defaultStyle = null;
            // 给【角色外观描述完成】委托添加函数
            myCharacter.onDescriptionComplete.add(() => {
                // 播放换装完成特效
                EffectService.playOnGameObject("161245", myCharacter, {slotType: HumanoidSlotType.Root});
                // 获取角色默认外观风格
                if(defaultStyle == null) {
                    defaultStyle = myCharacter.getDescription();
                }
            });
            // 给【角色外观描述变化】委托添加函数
            myCharacter.onDescriptionChange.add((operationCode: number, index: number, value: unknown) => {
                console.log("Appearance Changed");
                console.log("OperationCode " + operationCode + " Index " + index);
            });
            // 添加一个按键方法:按下键盘“1”，重置为默认角色外观
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.setDescription(defaultStyle);
            });
            // 添加一个按键方法:按下键盘“2”，修改角色外观
            InputUtil.onKeyDown(Keys.Two, () => {
                if(myCharacter.characterType == CharacterType.HumanoidV2) {
                    // 修改角色style头部:头大小为1.5倍
                    myCharacter.description.advance.headFeatures.head.headOverallScale = 1.5;
                    // 修改角色style体型:身高为1.2倍
                    myCharacter.description.advance.bodyFeatures.body.height = 1.2;
                    // 修改角色style化妆:腮红为75674
                    myCharacter.description.advance.makeup.blush.blushStyle = "75674";
                    // 修改角色style头发:前发为57731，后发为63910
                    myCharacter.description.advance.hair.frontHair.style = "57731";
                    myCharacter.description.advance.hair.backHair.style = "63910";
                    // 修改角色style:上衣为58694，下衣为58700，手套为60384，鞋子为58696
                    myCharacter.description.advance.clothing.upperCloth.style = "58694";
                    myCharacter.description.advance.clothing.lowerCloth.style = "58700";
                    myCharacter.description.advance.clothing.gloves.style = "60384";
                    myCharacter.description.advance.clothing.shoes.style = "58696";
                }
            });
            // 添加一个按键方法:按下键盘“3”，同步角色外观
            InputUtil.onKeyDown(Keys.Three, () => {
                myCharacter.syncDescription();
            });
            // 添加一个按键方法:按下键盘“4”，清空角色外观
            InputUtil.onKeyDown(Keys.Four, () => {
                myCharacter.clearDescription();
            });
        }
    }
}
```

___

### setStateEnabled <Score text="setStateEnabled" /> 

• **setStateEnabled**(`characterStateType`, `enabled`): `void` 

设置角色状态开关

#### Parameters

| `characterStateType` [`CharacterStateType`](../enums/mw.CharacterStateType.md) |  角色状态 |
| :------ | :------ |
| `enabled` `boolean` |  角色状态是否启用 使用示例:按 R 后禁用飞行状态，再按 2 切换飞行 ``` |


___

### swimUpDown <Score text="swimUpDown" /> 

• **swimUpDown**(`speed`): `void` 

使角色在水中上浮下潜

#### Parameters

| `speed` `number` | 速度,大于0是上浮,小于0是下潜 <br> range: 不做限制。 type: 浮点数 |
| :------ | :------ |



<span style="font-size: 14px;">
使用示例:将使用到的资源:"53011,20307"拖入优先加载栏。创建一个名为"Example_Character_SwimUp"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中生成拱形容器并适配游泳区域。按下键盘“1”，角色切换游泳。按下键盘“4”，角色修改最大游泳速度进行喷射加速。你可以看到的角色最大游泳速度变化的效果。代码如下：
</span>

```ts
@Component
export default class Example_Character_SwimUp extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在服务端执行
        if(SystemUtil.isServer()) {
            // 生成拱形容器并适配游泳区域
            GameObject.spawn("WaterVolume",{transform: new Transform(new Vector(0, 0, 500), new Rotation(0, 0, 90), new Vector(20, 20, 10))});
        }
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            let flag = true;
            // 获取当前客户端的玩家(自己)
            let myPlayer = Player.localPlayer;
            // 获取当前玩家控制的角色
            let myCharacter = myPlayer.character;
            // 添加一个按键方法：按下键盘“1”，角色切换游泳 / 行走
            InputUtil.onKeyDown(Keys.One, () => {
                if(flag) {
                    myCharacter.switchToWalking();
                } else {
                    myCharacter.switchToSwimming();
                }
                flag = !flag;
            });
            // 添加一个按键方法：按住键盘“2”，角色上浮
            InputUtil.onKeyPress(Keys.Two, () => {
                myCharacter.swimUpDown(100);
            });
            // 添加一个按键方法：按住键盘“3”，角色下潜
            InputUtil.onKeyPress(Keys.Three, () => {
                myCharacter.swimUpDown(-100);
            });
        }
    }
}
```

___

### syncDescription <Score text="syncDescription" /> 

• **syncDescription**(`appearance?`, `slotAndDecoration?`): `void` <Badge type="tip" text="client" />

同步角色外观数据。角色在客户端设置外观后只会更换本地角色的外观，其他客户端角色外观未修改。通过该接口可以将本地外观广播至其他客户端。

#### Parameters

| `appearance?` `boolean` | 角色同步 default:true |
| :------ | :------ |
| `slotAndDecoration?` `boolean` | 插槽和装饰同步 default:true |


<span style="font-size: 14px;">
使用示例:将使用到的资源:"14521,35391,161245,75674,57731,63910,58694,58700,60384,58696,136183"拖入优先加载栏。创建一个名为"Example_Character"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在场景中看到玩家控制角色玩家外观准备未完成播放摊手的效果。给【角色外观描述完成】委托添加函数来播放换装完成特效，并保存角色初始默认外观数据。给【角色外观描述变化】委托添加函数在控制台打印当前角色外观描述变化的具体子项和索引。按下键盘“1”，重置为默认角色外观。按下键盘“2”，修改角色外观。按下键盘“3”，同步角色外观。按下键盘“4”，清空角色外观。代码如下：
</span>

```ts
@Component
export default class Example_Character extends Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected onStart(): void {
        // 下列代码仅在客户端执行
        if(SystemUtil.isClient()) {
            // 获取当前客户端玩家
            let myPlayer = Player.localPlayer;
            // 获取玩家控制角色
            let myCharacter = myPlayer.character;
            // 如果玩家外观准备完成挥手，反之摊手
            if(myCharacter.isDescriptionReady) {
                let animation = myCharacter.loadAnimation("35391");
                animation.play();
            } else {
                let animation = myCharacter.loadAnimation("14521");
                animation.play();
            }
            let defaultStyle = null;
            // 给【角色外观描述完成】委托添加函数
            myCharacter.onDescriptionComplete.add(() => {
                // 播放换装完成特效
                EffectService.playOnGameObject("161245", myCharacter, {slotType: HumanoidSlotType.Root});
                // 获取角色默认外观风格
                if(defaultStyle == null) {
                    defaultStyle = myCharacter.getDescription();
                }
            });
            // 给【角色外观描述变化】委托添加函数
            myCharacter.onDescriptionChange.add((operationCode: number, index: number, value: unknown) => {
                console.log("Appearance Changed");
                console.log("OperationCode " + operationCode + " Index " + index);
            });
            // 添加一个按键方法:按下键盘“1”，重置为默认角色外观
            InputUtil.onKeyDown(Keys.One, () => {
                myCharacter.setDescription(defaultStyle);
            });
            // 添加一个按键方法:按下键盘“2”，修改角色外观
            InputUtil.onKeyDown(Keys.Two, () => {
                if(myCharacter.characterType == CharacterType.HumanoidV2) {
                    // 修改角色style头部:头大小为1.5倍
                    myCharacter.description.advance.headFeatures.head.headOverallScale = 1.5;
                    // 修改角色style体型:身高为1.2倍
                    myCharacter.description.advance.bodyFeatures.body.height = 1.2;
                    // 修改角色style化妆:腮红为75674
                    myCharacter.description.advance.makeup.blush.blushStyle = "75674";
                    // 修改角色style头发:前发为57731，后发为63910
                    myCharacter.description.advance.hair.frontHair.style = "57731";
                    myCharacter.description.advance.hair.backHair.style = "63910";
                    // 修改角色style:上衣为58694，下衣为58700，手套为60384，鞋子为58696
                    myCharacter.description.advance.clothing.upperCloth.style = "58694";
                    myCharacter.description.advance.clothing.lowerCloth.style = "58700";
                    myCharacter.description.advance.clothing.gloves.style = "60384";
                    myCharacter.description.advance.clothing.shoes.style = "58696";
                }
            });
            // 添加一个按键方法:按下键盘“3”，同步角色外观
            InputUtil.onKeyDown(Keys.Three, () => {
                myCharacter.syncDescription();
            });
            // 添加一个按键方法:按下键盘“4”，清空角色外观
            InputUtil.onKeyDown(Keys.Four, () => {
                myCharacter.clearDescription();
            });
        }
    }
}
```
