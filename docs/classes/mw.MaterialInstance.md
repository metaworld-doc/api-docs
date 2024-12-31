[玩法](../groups/玩法.玩法.md) / MaterialInstance

# MaterialInstance <Badge type="tip" text="Class" /> <Score text="MaterialInstance" />

材质实例类

<span style="font-size: 14px;">
使用示例:创建一个名为"MaterialExample"的脚本，把脚本挂载到一个模型对象下，打开脚本，输入以下代码保存，运行游戏，你将在场景中看到动态设置材质的效果。代码如下：
</span>

```ts
@Component
export default class MaterialExample extends Script {
    protected onStart(): void {
        if (this.gameObject instanceof mw.Model){
            // 获取当前Mesh上的材质
            const mis = this.gameObject.getMaterialInstance();
            mis.forEach(mi => {
            // 获取当前材质的浮点参数
                let aspns = mi.getAllScalarParameterName();
                aspns.forEach(aspn => {
                    // 设置当前材质的浮点参数
                    mi.setScalarParameterValue(aspn, 1);
                });
                // 获取当前材质的颜色参数
                let avpns = mi.getAllVectorParameterName();
                avpns.forEach(avpn => {
                    // 设置当前材质的颜色参数
                    mi.setVectorParameterValue(avpn, LinearColor.red);
                });
                // 获取当前材质的贴图参数
                let atpns = mi.getAllTextureParameterName();
                atpns.forEach(atpn => {
                    // 设置当前材质的贴图参数，确保设置的资源被加载了
                    mi.setTextureParameterValue(atpn, "26512");
                });
            });
        }
    }
}
```

## Table of contents

### Methods <Score text="Methods" /> 
| **[getAllScalarParameterName](mw.MaterialInstance.md#getallscalarparametername)**(): `string`[]   |
| :-----|
| 返回所有的浮点材质参数|
| **[getAllTextureParameterName](mw.MaterialInstance.md#getalltextureparametername)**(): `string`[]   |
| 返回所有的贴图材质参数|
| **[getAllVectorParameterName](mw.MaterialInstance.md#getallvectorparametername)**(): `string`[]   |
| 返回所有的颜色材质参数|
| **[getProperty](mw.MaterialInstance.md#getproperty)**(`propertyName`: `string`): `any`   |
| 获取材质指定名称属性|
| **[getPropertyNames](mw.MaterialInstance.md#getpropertynames)**(): `string`[]   |
| 获取材质所有属性名称|
| **[getScalarParameterValue](mw.MaterialInstance.md#getscalarparametervalue)**(`parameterName`: `string`): `number`   |
| 获取浮点参数值|
| **[getTextureParameterValue](mw.MaterialInstance.md#gettextureparametervalue)**(`parameterName`: `string`): `string`   |
| 获取贴图参数值|
| **[getVectorParameterValue](mw.MaterialInstance.md#getvectorparametervalue)**(`parameterName`: `string`): [`LinearColor`](mw.LinearColor.md)   |
| 获取颜色参数值|
| **[setProperty](mw.MaterialInstance.md#setproperty)**(`propertyName`: `string`, `value`: `any`): `void`   |
| 设置材质属性|
| **[setScalarParameterValue](mw.MaterialInstance.md#setscalarparametervalue)**(`parameterName`: `string`, `value`: `number`): `void`   |
| 设置浮点参数值。|
| **[setTextureParameterValue](mw.MaterialInstance.md#settextureparametervalue)**(`parameterName`: `string`, `value`: `string`): `void`   |
| 设置贴图参数值|
| **[setVectorParameterValue](mw.MaterialInstance.md#setvectorparametervalue)**(`parameterName`: `string`, `value`: [`LinearColor`](mw.LinearColor.md)): `void`   |
| 设置颜色参数值|

## Methods

### getAllScalarParameterName <Score text="getAllScalarParameterName" /> 

• **getAllScalarParameterName**(): `string`[] 

返回所有的浮点材质参数

#### Returns

| `string`[] | 材质参数数组 |
| :------ | :------ |

___

### getAllTextureParameterName <Score text="getAllTextureParameterName" /> 

• **getAllTextureParameterName**(): `string`[] 

返回所有的贴图材质参数

#### Returns

| `string`[] | 材质参数数组 |
| :------ | :------ |

___

### getAllVectorParameterName <Score text="getAllVectorParameterName" /> 

• **getAllVectorParameterName**(): `string`[] 

返回所有的颜色材质参数

#### Returns

| `string`[] | 材质参数数组 |
| :------ | :------ |

___

### getProperty <Score text="getProperty" /> 

• **getProperty**(`propertyName`): `any` 

获取材质指定名称属性

#### Parameters

| `propertyName` `string` | 属性名称 range: 无 |
| :------ | :------ |

#### Returns

| `any` | 属性 |
| :------ | :------ |

___

### getPropertyNames <Score text="getPropertyNames" /> 

• **getPropertyNames**(): `string`[] 

获取材质所有属性名称

#### Returns

| `string`[] | 返回属性名称列表 |
| :------ | :------ |

___

### getScalarParameterValue <Score text="getScalarParameterValue" /> 

• **getScalarParameterValue**(`parameterName`): `number` 

获取浮点参数值

#### Parameters

| `parameterName` `string` |  传入材质标量参数名称 range:参数名称 |
| :------ | :------ |

#### Returns

| `number` | 参数值 |
| :------ | :------ |

标量参数是材质中的一个可调节的数值，可以用于控制材质的各种属性，例如颜色、强度、透明度等。

通过获取标量参数的值，可以根据需要在游戏中进行动态调整和使用。

___

### getTextureParameterValue <Score text="getTextureParameterValue" /> 

• **getTextureParameterValue**(`parameterName`): `string` 

获取贴图参数值

#### Parameters

| `parameterName` `string` |  参数名称 range: |
| :------ | :------ |

#### Returns

| `string` | 参数值 |
| :------ | :------ |

___

### getVectorParameterValue <Score text="getVectorParameterValue" /> 

• **getVectorParameterValue**(`parameterName`): [`LinearColor`](mw.LinearColor.md) 

获取颜色参数值

#### Parameters

| `parameterName` `string` |  参数名称 range: |
| :------ | :------ |

#### Returns

| [`LinearColor`](mw.LinearColor.md) | 参数值 |
| :------ | :------ |

___

### setProperty <Score text="setProperty" /> 

• **setProperty**(`propertyName`, `value`): `void` 

设置材质属性

#### Parameters

| `propertyName` `string` | 属性名称 range: 无 |
| :------ | :------ |
| `value` `any` | 属性值 range: 无 |


___

### setScalarParameterValue <Score text="setScalarParameterValue" /> 

• **setScalarParameterValue**(`parameterName`, `value`): `void` 

设置浮点参数值。

#### Parameters

| `parameterName` `string` |  参数名称 range: |
| :------ | :------ |
| `value` `number` |  参数值 设置可调节参数的数值为多少。type: 浮点数 range: 不做限制。 |


___

### setTextureParameterValue <Score text="setTextureParameterValue" /> 

• **setTextureParameterValue**(`parameterName`, `value`): `void` 

设置贴图参数值

#### Parameters

| `parameterName` `string` |  参数名称 range: |
| :------ | :------ |
| `value` `string` |  参数值 range: 被设置的值，不做限制，合理即可 |


___

### setVectorParameterValue <Score text="setVectorParameterValue" /> 

• **setVectorParameterValue**(`parameterName`, `value`): `void` 

设置颜色参数值

#### Parameters

| `parameterName` `string` |  参数名称 range: |
| :------ | :------ |
| `value` [`LinearColor`](mw.LinearColor.md) |  参数值 type: 浮点数 range: 不做限制。 |

