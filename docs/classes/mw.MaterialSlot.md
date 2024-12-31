[玩法](../groups/玩法.玩法.md) / MaterialSlot

# MaterialSlot <Badge type="tip" text="Class" /> <Score text="MaterialSlot" />

Model插槽，执行材质相关操作

-------------------------

- model 材质插槽引用的Model

- index 材质插槽的索引

- materialAssetID 材质插槽使用的资源

- color 材质插槽的颜色

- resetColor 方法重置材质插槽颜色

- resetMaterial 方法重置材质资源

- getCustomMaterial 方法获取自定义材质

<span style="font-size: 14px;">
使用示例:创建一个名为"ModelExample"的脚本，放置在对象栏中，打开脚本，输入以下代码保存，运行游戏，你可以通过F1键，在场景中动态生成模型并模拟物理。代码如下：
</span>

```ts
@Component
export default class ModelExample extends Script {
    //当脚本被实例后，会在第一帧更新前调用此函数
    protected async onStart(): Promise<void> {
        if(SystemUtil.isClient())
            {
                InputUtil.onKeyDown(Keys.F1,()=>{
                    // F1键 通知服务器执行事件
                    mw.Event.dispatchToServer("Model");
                });
            }
        if(SystemUtil.isServer()){
            mw.Event.addClientListener("Model",()=>{
                let box = GameObject.spawn("197386",{
                    transform:new Transform(new Vector(500,0,100),new Rotation(0,0,0),new Vector(1,1,1)),
                    replicates:true
                }) as Model;
                // 设置透明度
                box.opacity = 0.8;
                // 设置颜色
                box.color = new mw.LinearColor(1.0,0.0,0.0,0.0);

                // 获取第0个插槽
                let matSlot0 = box.getMaterialSlot(0);
                // 设置材质插槽颜色
                matSlot0.color = new mw.LinearColor(1.0,0.0,0.0,0.0);
                // 重置颜色
                matSlot0.resetColor();
                // 设置材质插槽材质资源
                matSlot0.materialAssetID = "128569";
                // 重置插槽材质资源
                matSlot0.resetMaterial();
                // 获取插槽自定义材质
                let customMat = matSlot0.getCustomMaterial();
            });
        }
    }
}
```

## Table of contents

### Accessors <Score text="Accessors" /> 
| **[color](mw.MaterialSlot.md#color)**(): [`LinearColor`](mw.LinearColor.md)   |
| :-----|
| 插槽的颜色|
| **[index](mw.MaterialSlot.md#index)**(): `number`   |
| 插槽的索引，只读|
| **[materialAssetID](mw.MaterialSlot.md#materialassetid)**(): `string`   |
| 插槽的资源ID|
| **[model](mw.MaterialSlot.md#model)**(): [`Model`](mw.Model.md)   |
| 插槽的Model，只读|

### Methods <Score text="Methods" /> 
| **[getCustomMaterial](mw.MaterialSlot.md#getcustommaterial)**(): [`MaterialInstance`](mw.MaterialInstance.md) <Badge type="tip" text="other" />  |
| :-----|
| 获取自定义材质|
| **[resetColor](mw.MaterialSlot.md#resetcolor)**(): `void`   |
| 重置插槽颜色|
| **[resetMaterial](mw.MaterialSlot.md#resetmaterial)**(): `void`   |
| 重置当前插槽材质为初始材质|

构造函数

#### Parameters

| `index` `number` | 材质插槽的索引 default: 无 range: 无 type: 整形 |
| :------ | :------ |
| `model` [`Model`](mw.Model.md) | 材质插槽引用的Model default: 无 range: 无 |

## Accessors

### color <Score text="color" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **color**(): [`LinearColor`](mw.LinearColor.md) 

</th>
<th style="text-align: left">

• `set` **color**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


插槽的颜色

#### Returns

| [`LinearColor`](mw.LinearColor.md) | 获取插槽颜色 |
| :------ | :------ |


</td>
<td style="text-align: left">


设置插槽的颜色

#### Parameters

| `value` [`LinearColor`](mw.LinearColor.md) | 插槽颜色 |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### index <Score text="index" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **index**(): `number` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


插槽的索引，只读

#### Returns

| `number` | 获取插槽的索引 |
| :------ | :------ |

</td>
</tr></tbody>
</table>

___

### materialAssetID <Score text="materialAssetID" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **materialAssetID**(): `string` 

</th>
<th style="text-align: left">

• `set` **materialAssetID**(`value`): `void` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


插槽的资源ID

#### Returns

| `string` | 获取插槽资源ID |
| :------ | :------ |


</td>
<td style="text-align: left">


设置插槽的资源

#### Parameters

| `value` `string` | 插槽资源ID |
| :------ | :------ |



</td>
</tr></tbody>
</table>

___

### model <Score text="model" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **model**(): [`Model`](mw.Model.md) 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


插槽的Model，只读

#### Returns

</td>
</tr></tbody>
</table>

| [`Model`](mw.Model.md) | 获取插槽的Model |
| :------ | :------ |

## Methods

### getCustomMaterial <Score text="getCustomMaterial" /> 

• **getCustomMaterial**(): [`MaterialInstance`](mw.MaterialInstance.md) <Badge type="tip" text="other" />

获取自定义材质

#### Returns

| [`MaterialInstance`](mw.MaterialInstance.md) | 返回自定义材质实例 |
| :------ | :------ |

网络材质将返回空

___

### resetColor <Score text="resetColor" /> 

• **resetColor**(): `void` 

重置插槽颜色


___

### resetMaterial <Score text="resetMaterial" /> 

• **resetMaterial**(): `void` 

重置当前插槽材质为初始材质

