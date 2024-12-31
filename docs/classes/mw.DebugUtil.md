[工具](../groups/工具.工具.md) / DebugUtil

# DebugUtil <Badge type="tip" text="Class" /> <Score text="DebugUtil" />

游戏性能数据，辅助 Debug 和性能优化

## Table of contents

### Accessors <Score text="Accessors" /> 
| **[cachedRPCs](mw.DebugUtil.md#cachedrpcs)**(): `string`[]  |
| :-----|
| 当前帧缓存的RPC消息。|
| **[frameTime](mw.DebugUtil.md#frametime)**(): `number`  |
| 帧时间是生成一帧游戏内容所花费的总时间。由于游戏线程和渲染线程在完成一帧之前保持同步，帧时往往接近其中一个线程中显示的时间。单位ms|
| **[gameThreadTime](mw.DebugUtil.md#gamethreadtime)**(): `number`  |
| 对象在游戏线程中消耗的时间，包括脚本，动画，游戏逻辑等。单位ms。如果帧时接近游戏线程中显示的时间，则游戏的性能很可能会受到游戏线程的阻碍。单位ms。|
| **[receivedBytes](mw.DebugUtil.md#receivedbytes)**(): `number`  |
| 一秒内收到的网络包的总大小。单位 Byte。|
| **[receivedRPCs](mw.DebugUtil.md#receivedrpcs)**(): `string`[]  |
| 当前帧收到的RPC消息。|
| **[renderThreadTime](mw.DebugUtil.md#renderthreadtime)**(): `number`  |
| 在渲染线程中处理这些对象的时间，受粒子，特效，网格等影响。单位ms。|
| **[sentBytes](mw.DebugUtil.md#sentbytes)**(): `number`  |
| 一秒内发出的网络包的总大小。单位 Byte|
| **[sentRPCs](mw.DebugUtil.md#sentrpcs)**(): `string`[]  |
| 当前帧发送的RPC消息。|
| **[usedMemory](mw.DebugUtil.md#usedmemory)**(): `number`  |
| 当前使用的总内存大小，单位MB。|

## Accessors

### cachedRPCs <Score text="cachedRPCs" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **cachedRPCs**(): `string`[]

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


当前帧缓存的RPC消息。

#### Returns

| `string`[] |  |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### frameTime <Score text="frameTime" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **frameTime**(): `number`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


帧时间是生成一帧游戏内容所花费的总时间。由于游戏线程和渲染线程在完成一帧之前保持同步，帧时往往接近其中一个线程中显示的时间。单位ms

#### Returns

| `number` |  |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### gameThreadTime <Score text="gameThreadTime" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **gameThreadTime**(): `number`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


对象在游戏线程中消耗的时间，包括脚本，动画，游戏逻辑等。单位ms。如果帧时接近游戏线程中显示的时间，则游戏的性能很可能会受到游戏线程的阻碍。单位ms。

#### Returns

| `number` |  |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### receivedBytes <Score text="receivedBytes" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **receivedBytes**(): `number`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


一秒内收到的网络包的总大小。单位 Byte。

#### Returns

| `number` |  |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### receivedRPCs <Score text="receivedRPCs" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **receivedRPCs**(): `string`[]

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


当前帧收到的RPC消息。

#### Returns

| `string`[] |  |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### renderThreadTime <Score text="renderThreadTime" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **renderThreadTime**(): `number`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


在渲染线程中处理这些对象的时间，受粒子，特效，网格等影响。单位ms。

::: warning Precautions

如果帧时接近Draw线程中显示的时间，则游戏的性能很可能会受到渲染线程的阻碍。单位ms。服务端该值为0。

:::

#### Returns

| `number` |  |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### sentBytes <Score text="sentBytes" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **sentBytes**(): `number`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


一秒内发出的网络包的总大小。单位 Byte

#### Returns

| `number` |  |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### sentRPCs <Score text="sentRPCs" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **sentRPCs**(): `string`[]

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


当前帧发送的RPC消息。

#### Returns

| `string`[] |  |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### usedMemory <Score text="usedMemory" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `Static` `get` **usedMemory**(): `number`

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


当前使用的总内存大小，单位MB。

#### Returns


</td>
</tr></tbody>
</table>

