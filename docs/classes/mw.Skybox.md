[场景](../groups/场景.场景.md) / Skybox

# Skybox <Badge type="tip" text="Class" /> <Score text="Skybox" />

天空盒

----------------------------------

<span style="font-size: 14px;">
使用示例: 可按如下操作控制编辑器天空盒实时效果
</span>

创建一个名为"SkyboxExample"的脚本，放置在对象栏中，打开脚本，输入以下代码，运行游戏，你将可以通过 "+" 和 "-" 键控制天空盒的亮度， "*" 键切换预设。
```ts
@Component
export default class SkyboxExample extends mw.Script {
    // 当脚本被实例后，会在第一帧更新前调用此函数
    protected async onStart(): Promise<void> {
        if(Util.SystemUtil.isClient())
        {
            mw.InputUtil.onKeyDown(Type.Keys.Add,()=>{
                // 小键盘+建，增加天空盒亮度,依次递增1个单位
                Skybox.skyDomeIntensity = Skybox.skyDomeIntensity + 0.2;
                console.log("当前天空盒亮度:" + Skybox.skyDomeIntensity);
            });
            mw.InputUtil.onKeyDown(Type.Keys.Subtract,()=>{
                // 小键盘-建，降低天空盒亮度,依次递减1个单位
                Skybox.skyDomeIntensity = Skybox.skyDomeIntensity - 0.2;
                console.log("当前天空盒亮度:" + Skybox.skyDomeIntensity);
            });
            mw.InputUtil.onKeyDown(Type.Keys.Multiply,()=>{
                // 小键盘*建，切换天空盒预设
                Skybox.preset =7 % (Skybox.preset + 1);
            });
        }
    }
}
```

## Table of contents

### Accessors <Score text="Accessors" /> 
| **[affectedByFog](mw.Skybox.md#affectedbyfog)**(): `boolean` <Badge type="tip" text="client" />  |
| :-----|
| 设置是否受环境雾影响|
| **[cloudColor](mw.Skybox.md#cloudcolor)**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />  |
| 获取云颜色|
| **[cloudDensity](mw.Skybox.md#clouddensity)**(): `number` <Badge type="tip" text="client" />  |
| 获取云密度|
| **[cloudOpacity](mw.Skybox.md#cloudopacity)**(): `number` <Badge type="tip" text="client" />  |
| 获取云的透明度|
| **[cloudSpeed](mw.Skybox.md#cloudspeed)**(): `number` <Badge type="tip" text="client" />  |
| 获取云速度|
| **[cloudTextureID](mw.Skybox.md#cloudtextureid)**(): `string` <Badge type="tip" text="client" />  |
| 获取云贴图ID|
| **[cloudVisible](mw.Skybox.md#cloudvisible)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取是否开启云|
| **[disturbanceDensity](mw.Skybox.md#disturbancedensity)**(): `number` <Badge type="tip" text="client" />  |
| 获取扰动密度|
| **[disturbanceEnabled](mw.Skybox.md#disturbanceenabled)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取扰动开关|
| **[disturbanceIntensity](mw.Skybox.md#disturbanceintensity)**(): `number` <Badge type="tip" text="client" />  |
| 获取扰动强度|
| **[layerDisturbanceEnabled](mw.Skybox.md#layerdisturbanceenabled)**(): `boolean` <Badge type="tip" text="client" />  |
| 设置是否开启分层扰动|
| **[moonColor](mw.Skybox.md#mooncolor)**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />  |
| 获取月亮颜色|
| **[moonIntensity](mw.Skybox.md#moonintensity)**(): `number` <Badge type="tip" text="client" />  |
| 获取月亮亮度|
| **[moonSize](mw.Skybox.md#moonsize)**(): `number` <Badge type="tip" text="client" />  |
| 获取月亮大小|
| **[moonTextureID](mw.Skybox.md#moontextureid)**(): `string` <Badge type="tip" text="client" />  |
| 获取月亮贴图ID|
| **[moonVisible](mw.Skybox.md#moonvisible)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取是否开启月亮|
| **[pitchAngle](mw.Skybox.md#pitchangle)**(): `number` <Badge type="tip" text="client" />  |
| 获取天空盒贴图pitch旋转（度）|
| **[preset](mw.Skybox.md#preset)**(): [`SkyPreset`](../enums/mw.SkyPreset.md) <Badge type="tip" text="client" />  |
| 获取预设|
| **[rollAngle](mw.Skybox.md#rollangle)**(): `number` <Badge type="tip" text="client" />  |
| 获取天空盒贴图roll旋转（度）|
| **[skyDomeBaseColor](mw.Skybox.md#skydomebasecolor)**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />  |
| 获取天空盒颜色|
| **[skyDomeBottomColor](mw.Skybox.md#skydomebottomcolor)**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />  |
| 天空下层颜色|
| **[skyDomeGradientEnabled](mw.Skybox.md#skydomegradientenabled)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取是否开启渐变效果|
| **[skyDomeHorizontalFallOff](mw.Skybox.md#skydomehorizontalfalloff)**(): `number` <Badge type="tip" text="client" />  |
| 获取地平线渐出值|
| **[skyDomeIntensity](mw.Skybox.md#skydomeintensity)**(): `number` <Badge type="tip" text="client" />  |
| 获取天空盒亮度|
| **[skyDomeMiddleColor](mw.Skybox.md#skydomemiddlecolor)**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />  |
| 天空中层颜色|
| **[skyDomeTextureID](mw.Skybox.md#skydometextureid)**(): `string` <Badge type="tip" text="client" />  |
| 获取天空盒贴图资源ID|
| **[skyDomeTopColor](mw.Skybox.md#skydometopcolor)**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />  |
| 获取天空顶层颜色|
| **[skyboxRotation](mw.Skybox.md#skyboxrotation)**(): [`Rotation`](mw.Rotation.md) <Badge type="tip" text="client" />  |
| 获取天空球旋转|
| **[starDensity](mw.Skybox.md#stardensity)**(): `number` <Badge type="tip" text="client" />  |
| 获取星星密度|
| **[starIntensity](mw.Skybox.md#starintensity)**(): `number` <Badge type="tip" text="client" />  |
| 获取星星亮度|
| **[starTextureID](mw.Skybox.md#startextureid)**(): `string` <Badge type="tip" text="client" />  |
| 获取星星贴图ID|
| **[starVisible](mw.Skybox.md#starvisible)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取是否开启星星|
| **[sunColor](mw.Skybox.md#suncolor)**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />  |
| 获取太阳颜色|
| **[sunIntensity](mw.Skybox.md#sunintensity)**(): `number` <Badge type="tip" text="client" />  |
| 获取太阳光亮度|
| **[sunSize](mw.Skybox.md#sunsize)**(): `number` <Badge type="tip" text="client" />  |
| 获取太阳大小|
| **[sunTextureID](mw.Skybox.md#suntextureid)**(): `string` <Badge type="tip" text="client" />  |
| 获取太阳贴图ID|
| **[sunVisible](mw.Skybox.md#sunvisible)**(): `boolean` <Badge type="tip" text="client" />  |
| 获取是否开启太阳|
| **[yawAngle](mw.Skybox.md#yawangle)**(): `number` <Badge type="tip" text="client" />  |
| 获取天空盒贴图yaw旋转（度）|

### Methods <Score text="Methods" /> 
| **[pausSwitch](mw.Skybox.md#pausswitch)**(): `void` <Badge type="tip" text="client" />  |
| :-----|
| 暂停天空盒背景|
| **[refresh](mw.Skybox.md#refresh)**(): `void` <Badge type="tip" text="client" />  |
| 天空盒刷新|
| **[reset](mw.Skybox.md#reset)**(): `void` <Badge type="tip" text="client" />  |
| 重置为默认参数|
| **[startSwitch](mw.Skybox.md#startswitch)**(`targetTexture`: `string`, `switchMode`: [`Gradient`](../enums/mw.SkyboxBackgroundSwitchMode.md#gradient), `switchTime`: `number`): `boolean` <Badge type="tip" text="client" />  |
| 开始切换天空盒背景|

## Accessors

### affectedByFog <Score text="affectedByFog" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **affectedByFog**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **affectedByFog**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


设置是否受环境雾影响

#### Returns

| `boolean` | 是否受环境雾影响 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否受环境雾影响

#### Parameters

| `value` `boolean` | 是否受环境雾影响 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### cloudColor <Score text="cloudColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **cloudColor**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **cloudColor**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取云颜色

#### Returns

| [`LinearColor`](mw.LinearColor.md) | 云颜色 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置云颜色

#### Parameters

| `value` [`LinearColor`](mw.LinearColor.md) | 云颜色 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### cloudDensity <Score text="cloudDensity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **cloudDensity**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **cloudDensity**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取云密度

#### Returns

| `number` | 云密度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置云密度

#### Parameters

| `value` `number` | 云密度(0~1) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### cloudOpacity <Score text="cloudOpacity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **cloudOpacity**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **cloudOpacity**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取云的透明度

#### Returns

| `number` | 云的透明度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置云的透明度

#### Parameters

| `value` `number` | 云的透明度(0~1) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### cloudSpeed <Score text="cloudSpeed" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **cloudSpeed**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **cloudSpeed**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取云速度

#### Returns

| `number` | 云速度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置云速度

#### Parameters

| `value` `number` | 云速度(0~10) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### cloudTextureID <Score text="cloudTextureID" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **cloudTextureID**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **cloudTextureID**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取云贴图ID

#### Returns

| `string` | 云贴图ID |
| :------ | :------ |


</td>
<td style="text-align: left">


设置云贴图资源ID

#### Parameters

| `value` `string` | 云贴图资源ID |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### cloudVisible <Score text="cloudVisible" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **cloudVisible**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **cloudVisible**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否开启云

#### Returns

| `boolean` | 是否开启云 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否开启云

#### Parameters

| `value` `boolean` | 是否开启云 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### disturbanceDensity <Score text="disturbanceDensity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **disturbanceDensity**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **disturbanceDensity**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取扰动密度

#### Returns

| `number` | 扰动密度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置扰动密度

#### Parameters

| `value` `number` | 扰动密度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### disturbanceEnabled <Score text="disturbanceEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **disturbanceEnabled**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **disturbanceEnabled**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取扰动开关

#### Returns

| `boolean` | 扰动开关 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置扰动开关

#### Parameters

| `value` `boolean` | 扰动开关 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### disturbanceIntensity <Score text="disturbanceIntensity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **disturbanceIntensity**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **disturbanceIntensity**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取扰动强度

#### Returns

| `number` | 扰动强度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置扰动强度

#### Parameters

| `value` `number` | 扰动强度 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### layerDisturbanceEnabled <Score text="layerDisturbanceEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **layerDisturbanceEnabled**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **layerDisturbanceEnabled**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


设置是否开启分层扰动

#### Returns

| `boolean` | 是否开启分层扰动 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否开启分层扰动

#### Parameters

| `value` `boolean` | 是否开启分层扰动 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### moonColor <Score text="moonColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **moonColor**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **moonColor**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取月亮颜色

#### Returns

| [`LinearColor`](mw.LinearColor.md) | 月亮颜色 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置月亮颜色

#### Parameters

| `value` [`LinearColor`](mw.LinearColor.md) | 月亮颜色 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### moonIntensity <Score text="moonIntensity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **moonIntensity**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **moonIntensity**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取月亮亮度

#### Returns

| `number` | 月亮亮度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置月亮亮度

#### Parameters

| `value` `number` | 月亮亮度(0~2000) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### moonSize <Score text="moonSize" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **moonSize**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **moonSize**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取月亮大小

#### Returns

| `number` | 月亮大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置月亮大小

#### Parameters

| `value` `number` | 月亮大小(0~100) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### moonTextureID <Score text="moonTextureID" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **moonTextureID**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **moonTextureID**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取月亮贴图ID

#### Returns

| `string` | 月亮贴图ID |
| :------ | :------ |


</td>
<td style="text-align: left">


设置月亮贴图资源ID

#### Parameters

| `value` `string` | 月亮贴图资源ID |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### moonVisible <Score text="moonVisible" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **moonVisible**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **moonVisible**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否开启月亮

#### Returns

| `boolean` | 是否开启月亮 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否开启月亮

#### Parameters

| `value` `boolean` | 是否开启月亮 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### pitchAngle <Score text="pitchAngle" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **pitchAngle**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **pitchAngle**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取天空盒贴图pitch旋转（度）

#### Returns

| `number` | 天空盒贴图旋转 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置天空盒贴图pitch旋转（度）

#### Parameters

| `value` `number` | 天空盒贴图旋转度(0~360) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### preset <Score text="preset" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **preset**(): [`SkyPreset`](../enums/mw.SkyPreset.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **preset**(`NewPreset`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取预设

#### Returns

| [`SkyPreset`](../enums/mw.SkyPreset.md) | 返回预设 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置预设

#### Parameters

| `NewPreset` [`SkyPreset`](../enums/mw.SkyPreset.md) | 预设枚举 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### rollAngle <Score text="rollAngle" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **rollAngle**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **rollAngle**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取天空盒贴图roll旋转（度）

#### Returns

| `number` | 天空盒贴图旋转 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置天空盒贴图roll旋转（度）

#### Parameters

| `value` `number` | 天空盒贴图旋转度(0~360) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### skyDomeBaseColor <Score text="skyDomeBaseColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **skyDomeBaseColor**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **skyDomeBaseColor**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取天空盒颜色

#### Returns

| [`LinearColor`](mw.LinearColor.md) | 天空盒颜色 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置天空盒颜色

#### Parameters

| `value` [`LinearColor`](mw.LinearColor.md) | 天空盒颜色值 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### skyDomeBottomColor <Score text="skyDomeBottomColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **skyDomeBottomColor**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **skyDomeBottomColor**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


天空下层颜色

#### Returns

| [`LinearColor`](mw.LinearColor.md) | 天空下层颜色 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置天空下层颜色

#### Parameters

| `value` [`LinearColor`](mw.LinearColor.md) | 天空下层颜色值 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### skyDomeGradientEnabled <Score text="skyDomeGradientEnabled" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **skyDomeGradientEnabled**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **skyDomeGradientEnabled**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否开启渐变效果

#### Returns

| `boolean` | 是否开启渐变效果 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否开启渐变效果

#### Parameters

| `value` `boolean` | 是否开启渐变效果 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### skyDomeHorizontalFallOff <Score text="skyDomeHorizontalFallOff" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **skyDomeHorizontalFallOff**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **skyDomeHorizontalFallOff**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取地平线渐出值

#### Returns

| `number` | 地平线渐出值 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置地平线渐出值

#### Parameters

| `value` `number` | 地平线渐出值(1~20) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### skyDomeIntensity <Score text="skyDomeIntensity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **skyDomeIntensity**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **skyDomeIntensity**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取天空盒亮度

#### Returns

| `number` | 天空盒亮度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置天空盒亮度

#### Parameters

| `value` `number` | 天空盒亮度值(0~100) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### skyDomeMiddleColor <Score text="skyDomeMiddleColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **skyDomeMiddleColor**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **skyDomeMiddleColor**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


天空中层颜色

#### Returns

| [`LinearColor`](mw.LinearColor.md) | 天空中层颜色 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置天空中层颜色

#### Parameters

| `value` [`LinearColor`](mw.LinearColor.md) | 天空中层颜色值 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### skyDomeTextureID <Score text="skyDomeTextureID" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **skyDomeTextureID**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **skyDomeTextureID**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取天空盒贴图资源ID

#### Returns

| `string` | 贴图资源ID |
| :------ | :------ |


</td>
<td style="text-align: left">


设置天空盒贴图资源ID

#### Parameters

| `value` `string` | 贴图资源ID |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### skyDomeTopColor <Score text="skyDomeTopColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **skyDomeTopColor**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **skyDomeTopColor**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取天空顶层颜色

#### Returns

| [`LinearColor`](mw.LinearColor.md) | 天空顶层颜色 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置天空顶层颜色

#### Parameters

| `value` [`LinearColor`](mw.LinearColor.md) | 天空顶层颜色值 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### skyboxRotation <Score text="skyboxRotation" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **skyboxRotation**(): [`Rotation`](mw.Rotation.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **skyboxRotation**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取天空球旋转

#### Returns

| [`Rotation`](mw.Rotation.md) | 天空球旋转值 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置天空球旋转

#### Parameters

| `value` [`Rotation`](mw.Rotation.md) | 天空球旋转值 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### starDensity <Score text="starDensity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **starDensity**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **starDensity**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取星星密度

#### Returns

| `number` | 星星密度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置星星密度

#### Parameters

| `value` `number` | 星星密度(0~100) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### starIntensity <Score text="starIntensity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **starIntensity**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **starIntensity**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取星星亮度

#### Returns

| `number` | 星星亮度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置星星亮度

#### Parameters

| `value` `number` | 星星亮度(0~1) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### starTextureID <Score text="starTextureID" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **starTextureID**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **starTextureID**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取星星贴图ID

#### Returns

| `string` | 星星贴图ID |
| :------ | :------ |


</td>
<td style="text-align: left">


设置星星贴图资源ID

#### Parameters

| `value` `string` | 星星贴图资源ID |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### starVisible <Score text="starVisible" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **starVisible**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **starVisible**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否开启星星

#### Returns

| `boolean` | 是否开启星星 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否开启星星

#### Parameters

| `value` `boolean` | 是否开启星星 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### sunColor <Score text="sunColor" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **sunColor**(): [`LinearColor`](mw.LinearColor.md) <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **sunColor**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取太阳颜色

#### Returns

| [`LinearColor`](mw.LinearColor.md) | 太阳颜色 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置太阳颜色

#### Parameters

| `value` [`LinearColor`](mw.LinearColor.md) | 太阳颜色 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### sunIntensity <Score text="sunIntensity" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **sunIntensity**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **sunIntensity**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取太阳光亮度

#### Returns

| `number` | 太阳光亮度 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置太阳光亮度

#### Parameters

| `value` `number` | 太阳光亮度(0~2000) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### sunSize <Score text="sunSize" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **sunSize**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **sunSize**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取太阳大小

#### Returns

| `number` | 太阳大小 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置太阳大小

#### Parameters

| `value` `number` | 太阳大小(0~100) |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### sunTextureID <Score text="sunTextureID" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **sunTextureID**(): `string` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **sunTextureID**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取太阳贴图ID

#### Returns

| `string` | 太阳贴图ID |
| :------ | :------ |


</td>
<td style="text-align: left">


设置太阳贴图资源ID

#### Parameters

| `value` `string` | 太阳贴图资源ID |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### sunVisible <Score text="sunVisible" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **sunVisible**(): `boolean` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **sunVisible**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取是否开启太阳

#### Returns

| `boolean` | 是否开启太阳 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置是否开启太阳

#### Parameters

| `value` `boolean` | 是否开启太阳 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### yawAngle <Score text="yawAngle" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **yawAngle**(): `number` <Badge type="tip" text="client" />

</th>
<th style="text-align: left">

• `Static` `set` **yawAngle**(`value`): `void` <Badge type="tip" text="client" />

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取天空盒贴图yaw旋转（度）

#### Returns

| `number` | 天空盒贴图旋转 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置天空盒贴图yaw旋转（度）

#### Parameters

| `value` `number` | 天空盒贴图yaw旋转度(0~360) |
| :------ | :------ |

</td>
</tr></tbody>
</table>



## Methods

### pausSwitch <Score text="pausSwitch" /> 

• `Static` **pausSwitch**(): `void` <Badge type="tip" text="client" />

暂停天空盒背景


___

### refresh <Score text="refresh" /> 

• `Static` **refresh**(): `void` <Badge type="tip" text="client" />

天空盒刷新


___

### reset <Score text="reset" /> 

• `Static` **reset**(): `void` <Badge type="tip" text="client" />

重置为默认参数


___

### startSwitch <Score text="startSwitch" /> 

• `Static` **startSwitch**(`targetTexture`, `switchMode`, `switchTime`): `boolean` <Badge type="tip" text="client" />

开始切换天空盒背景

#### Parameters

| `targetTexture` `string` | 要切换到的天空球贴图 range: 无 |
| :------ | :------ |
| `switchMode` [`Gradient`](../enums/mw.SkyboxBackgroundSwitchMode.md#gradient) | 过渡方式 |
| `switchTime` `number` | 过渡时间,单位：秒 range: 无 type: 浮点型 |

#### Returns

| `boolean` | 是否在切换 |
| :------ | :------ |
