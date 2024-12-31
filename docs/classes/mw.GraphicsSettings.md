[设置](../groups/设置.设置.md) / GraphicsSettings

# GraphicsSettings <Badge type="tip" text="Class" /> <Score text="GraphicsSettings" />

图片画质设置

<span style="font-size: 14px;">
使用示例:创建一个名为"ClassExample"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你将在服务器Log中看到对应方法调用信息。代码如下：
</span>

```ts
@Component
export default class ClassExample extends Script {

   protected onStart(): void {
       this.RoomSettings();
   }

   public RoomSettings(){
       //设置CPU和GPU的画质等级
       let cpu = mw.GraphicsLevel.Low1;
       let gpu = mw.GraphicsLevel.Low2;
       GraphicsSettings.setGraphicsCPULevel(cpu);
       GraphicsSettings.setGraphicsGPULevel(gpu);
       //开启自动分辨率
       GraphicsSettings.setAutoScreenPercentage(true);
       //设置FSR抗锯齿等级
       GraphicsSettings.setFSRLevel(3);
       //设置锐化程度
       GraphicsSettings.setSharpness(1);

       //获取当前CPU画质等级
       let cpulevel = GraphicsSettings.getCPULevel();
       //获取当前GPU画质等级
       let gpulevel = GraphicsSettings.getGPULevel();
       //获取默认CPU画质等级
       let Defaultcpulevel = GraphicsSettings.getDefaultCPULevel();
       //获取默认GPU画质等级
       let Defaultcgpulevel = GraphicsSettings.getDefaultGPULevel();
       //获取当前自动分辨率开启状态
       GraphicsSettings.getAutoScreenPercentage();
       //获取当前FSR抗锯齿等级
       GraphicsSettings.getFSRLevel();
       //获取当前锐化程度
       GraphicsSettings.getSharpness();
   }
}
```

## Table of contents

### Accessors <Score text="Accessors" /> 
| **[occlusionCullingEnabled](mw.GraphicsSettings.md#occlusioncullingenabled)**(): `boolean` <Badge type="tip" text="client" />  |
| :-----|
| 获取是否开启遮挡剔除(遮挡剔除开启后能一定程度上降低DrawCall，具体效果取决于场景物体相互遮挡的程度, 但是可能会导致物体从被剔除切换到不被剔除时延迟3帧才渲染)|

### Methods <Score text="Methods" /> 
| **[getAutoScreenPercentage](mw.GraphicsSettings.md#getautoscreenpercentage)**(): `boolean` <Badge type="tip" text="client" />  |
| :-----|
| 获取自动分辨率开关状态|
| **[getFSRLevel](mw.GraphicsSettings.md#getfsrlevel)**(): `number` <Badge type="tip" text="client" />  |
| 获取FSR画质等级|
| **[getSharpness](mw.GraphicsSettings.md#getsharpness)**(): `number` <Badge type="tip" text="client" />  |
| 获取锐化程度|
| **[setAutoScreenPercentage](mw.GraphicsSettings.md#setautoscreenpercentage)**(`isEnabled`: `boolean`): `void` <Badge type="tip" text="client" />  |
| 设置是否开启自动分辨率|
| **[setFSRLevel](mw.GraphicsSettings.md#setfsrlevel)**(`FSRLevel`: `number`): `void` <Badge type="tip" text="client" />  |
| 设置TSR等级|
| **[setSharpness](mw.GraphicsSettings.md#setsharpness)**(`sharpness`: `number`): `void` <Badge type="tip" text="client" />  |
| 设置锐化程度|

## Accessors

### occlusionCullingEnabled <Score text="occlusionCullingEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **occlusionCullingEnabled**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **occlusionCullingEnabled**(`isEnabled`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否开启遮挡剔除(遮挡剔除开启后能一定程度上降低DrawCall，具体效果取决于场景物体相互遮挡的程度, 但是可能会导致物体从被剔除切换到不被剔除时延迟3帧才渲染)

#### Returns

| `boolean` | 当前是否开启遮挡剔除。如果返回值为undefined，请检查是否在客户端调用 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置遮挡剔除(遮挡剔除开启后能一定程度上降低DrawCall，具体效果取决于场景物体相互遮挡的程度, 但是可能会导致物体从被剔除切换到不被剔除时延迟3帧才渲染)

#### Parameters

| `isEnabled` `boolean` | 是否开启遮挡剔除 |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods

### getAutoScreenPercentage <Score text="getAutoScreenPercentage" /> 

• `Static` **getAutoScreenPercentage**(): `boolean` <Badge type="tip" text="client" />

获取自动分辨率开关状态

#### Returns

| `boolean` | 获取自动分辨率开关状态。如果返回值为undefined，请检查是否在客户端调用 |
| :------ | :------ |

___

### getFSRLevel <Score text="getFSRLevel" /> 

• `Static` **getFSRLevel**(): `number` <Badge type="tip" text="client" />

获取FSR画质等级

#### Returns

| `number` | 获取FSR画质等级。如果返回值为undefined，请检查是否在客户端调用 |
| :------ | :------ |

___

### getSharpness <Score text="getSharpness" /> 

• `Static` **getSharpness**(): `number` <Badge type="tip" text="client" />

获取锐化程度

#### Returns

| `number` | 获取锐化程度。如果返回值为undefined，请检查是否在客户端调用 |
| :------ | :------ |

___

### setAutoScreenPercentage <Score text="setAutoScreenPercentage" /> 

• `Static` **setAutoScreenPercentage**(`isEnabled`): `void` <Badge type="tip" text="client" />

设置是否开启自动分辨率

#### Parameters

| `isEnabled` `boolean` | 开关 |
| :------ | :------ |


___

### setFSRLevel <Score text="setFSRLevel" /> 

• `Static` **setFSRLevel**(`FSRLevel`): `void` <Badge type="tip" text="client" />

设置TSR等级

#### Parameters

| `FSRLevel` `number` | FSR等级 type: 整形 range: 无 |
| :------ | :------ |


___

### setSharpness <Score text="setSharpness" /> 

• `Static` **setSharpness**(`sharpness`): `void` <Badge type="tip" text="client" />

设置锐化程度

#### Parameters

| `sharpness` `number` | 锐化程度 range:[0, 1] type: 浮点型 |
| :------ | :------ |

