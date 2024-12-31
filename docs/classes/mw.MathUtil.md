[工具](../groups/工具.工具.md) / MathUtil

# MathUtil <Badge type="tip" text="Class" /> <Score text="MathUtil" />

数学库工具

## Table of contents

### Properties <Score text="Properties" /> 
| **[D2R](mw.MathUtil.md#d2r)**: `number`  |
| :-----|
| 角度转换弧度参数（Math.PI/180）|
| **[DBL\_DECIMAL\_DIG](mw.MathUtil.md#dbl_decimal_dig)**: `number`  |
| 序列化/反序列化浮点值所要求的十进制精度 (double)|
| **[DBL\_DIG](mw.MathUtil.md#dbl_dig)**: `number`  |
| 文本的往返转换中保留而不会因舍入或溢出发生改变的的十进制位数 (double)|
| **[DBL\_EPSILON](mw.MathUtil.md#dbl_epsilon)**: `number`  |
| 1 和大于 1 的最小浮点数之间的差值。(double)|
| **[DBL\_HAS\_SUBNORM](mw.MathUtil.md#dbl_has_subnorm)**: `number`  |
| 指明类型是否支持非正规数值：-1 为不确定，0 为不支持，1 为支持。 (double)|
| **[DBL\_MANT\_DIG](mw.MathUtil.md#dbl_mant_dig)**: `number`  |
| 有效数字（尾数）的位数(double)|
| **[DBL\_MAX](mw.MathUtil.md#dbl_max)**: `number`  |
| 最大的有效浮点数的值（为正数），也即浮点数的最大值。(double)|
| **[DBL\_MAX\_10\_EXP](mw.MathUtil.md#dbl_max_10_exp)**: `number`  |
| 分别为能够使 10 的该整数减一次幂为可表示的有限的最大正整数 (double)|
| **[DBL\_MAX\_EXP](mw.MathUtil.md#dbl_max_exp)**: `number`  |
| 最大二进制指数 (double)|
| **[DBL\_MIN](mw.MathUtil.md#dbl_min)**: `number`  |
| 最小规格化正数值 (double)|
| **[DBL\_MIN\_10\_EXP](mw.MathUtil.md#dbl_min_10_exp)**: `number`  |
| 能够使 10 的该整数减一次幂为规格化的最小负整数 (double)|
| **[DBL\_MIN\_EXP](mw.MathUtil.md#dbl_min_exp)**: `number`  |
| 能够使FLT_RADIX 的该整数减一次幂为规格化的最小负整数 (double)|
| **[DBL\_RADIX](mw.MathUtil.md#dbl_radix)**: `number`  |
| 基数(进制)(double)|
| **[DBL\_TRUE\_MIN](mw.MathUtil.md#dbl_true_min)**: `number`  |
| 最小正数值(double)|
| **[EPSILON](mw.MathUtil.md#epsilon)**: `number`  |
| 最小误差数|
| **[FLOAT\_NON\_FRACTIONAL](mw.MathUtil.md#float_non_fractional)**: `number`  |
| 所有大于或等于此值的单精度浮点数都没有小数|
| **[FLT\_DECIMAL\_DIG](mw.MathUtil.md#flt_decimal_dig)**: `number`  |
| 序列化/反序列化浮点值所要求的十进制精度 (float)|
| **[FLT\_DIG](mw.MathUtil.md#flt_dig)**: `number`  |
| 文本的往返转换中保留而不会因舍入或溢出发生改变的的十进制位数 (float)|
| **[FLT\_EPSILON](mw.MathUtil.md#flt_epsilon)**: `number`  |
| 1 和大于 1 的最小浮点数之间的差值。(float)|
| **[FLT\_GUARD](mw.MathUtil.md#flt_guard)**: `number`  |
| 算术结果中是否使用保护位(例如 0)|
| **[FLT\_HAS\_SUBNORM](mw.MathUtil.md#flt_has_subnorm)**: `number`  |
| 指明类型是否支持非正规数值：-1 为不确定，0 为不支持，1 为支持。|
| **[FLT\_MANT\_DIG](mw.MathUtil.md#flt_mant_dig)**: `number`  |
| 有效数字（尾数）的位数 (float)|
| **[FLT\_MAX](mw.MathUtil.md#flt_max)**: `number`  |
| 最大的有效浮点数的值(为正数)，也即浮点数的最大值。(float)|
| **[FLT\_MAX\_10\_EXP](mw.MathUtil.md#flt_max_10_exp)**: `number`  |
| 转换成十进制形式后，规格化浮点数的指数的最大值（为正数）。 (float)|
| **[FLT\_MAX\_EXP](mw.MathUtil.md#flt_max_exp)**: `number`  |
| 最大二进制指数 (float)|
| **[FLT\_MIN](mw.MathUtil.md#flt_min)**: `number`  |
| 最小正规值 (float)|
| **[FLT\_MIN\_10\_EXP](mw.MathUtil.md#flt_min_10_exp)**: `number`  |
| 最小十进制指数 (float)|
| **[FLT\_MIN\_EXP](mw.MathUtil.md#flt_min_exp)**: `number`  |
| 最小二进制指数 (float)|
| **[FLT\_NORMALIZE](mw.MathUtil.md#flt_normalize)**: `number`  |
| 指示应始终规范化浮点数。|
| **[FLT\_RADIX](mw.MathUtil.md#flt_radix)**: `number`  |
| 基数(进制)(float)|
| **[FLT\_TRUE\_MIN](mw.MathUtil.md#flt_true_min)**: `number`  |
| 最小正数值 (float)|
| **[HALF\_PI](mw.MathUtil.md#half_pi)**: `number`  |
| PI/2|
| **[INV\_PI](mw.MathUtil.md#inv_pi)**: `number`  |
| 1/PI|
| **[R2D](mw.MathUtil.md#r2d)**: `number`  |
| 弧度转换角度参数|
| **[SIGN\_BIT](mw.MathUtil.md#sign_bit)**: `number`  |
| 字节偏移|

### Methods <Score text="Methods" /> 
| **[angleCheck](mw.MathUtil.md#anglecheck)**(`StartLocation`: [`Vector`](mw.Vector.md), `StartDirection`: [`Vector`](mw.Vector.md), `TargetLocation`: [`Vector`](mw.Vector.md), `Angle`: `number`): `boolean`   |
| :-----|
| 判断终点位置是否处于起点位置在某一方向的一定角度内|
| **[areFloatsEqual](mw.MathUtil.md#arefloatsequal)**(`a`: `number`, `b`: `number`, `epsilon?`: `number`): `boolean`   |
| 判断浮点数是否近似相等|
| **[clamp](mw.MathUtil.md#clamp)**(`a`: `number`, `min`: `number`, `max`: `number`): `number`   |
| 将传入的数值 a 限制在 min 与 max 范围内，超出部分自动舍弃|
| **[cos](mw.MathUtil.md#cos)**(`a`: `number`): `number`   |
| 计算 cos 值|
| **[degreesToRadians](mw.MathUtil.md#degreestoradians)**(`a`: `number`): `number`   |
| 根据输入的度数返回弧度值|
| **[fmod](mw.MathUtil.md#fmod)**(`x`: `number`, `y`: `number`): `number`   |
| 数值 x 除以数值 y 的余数|
| **[lerp](mw.MathUtil.md#lerp)**(`a`: `number`, `b`: `number`, `alpha`: `number`): `number`   |
| 基于 alpha 在 数值a 和 数值b 之间线性插值|
| **[radiansToDegrees](mw.MathUtil.md#radianstodegrees)**(`a`: `number`): `number`   |
| 根据输入的弧度值返回度数|
| **[randomFloat](mw.MathUtil.md#randomfloat)**(`min`: `number`, `max`: `number`): `number`   |
| 获取随机范围内浮点数[包含min, 不包含max)|
| **[randomInt](mw.MathUtil.md#randomint)**(`min`: `number`, `max`: `number`): `number`   |
| 获取随机范围内整数[包含min, 不包含max)|
| **[sin](mw.MathUtil.md#sin)**(`a`: `number`): `number`   |
| 计算 sin 值|
| **[tan](mw.MathUtil.md#tan)**(`a`: `number`): `number`   |
| 计算 tan 值|

## Properties

### D2R <Score text="D" /> 

▪ `Static` **D2R**: `number`

角度转换弧度参数（Math.PI/180）

___

### DBL\_DECIMAL\_DIG <Score text="DBL" /> 

▪ `Static` **DBL\_DECIMAL\_DIG**: `number`

序列化/反序列化浮点值所要求的十进制精度 (double)

___

### DBL\_DIG <Score text="DBL" /> 

▪ `Static` **DBL\_DIG**: `number`

文本的往返转换中保留而不会因舍入或溢出发生改变的的十进制位数 (double)

___

### DBL\_EPSILON <Score text="DBL" /> 

▪ `Static` **DBL\_EPSILON**: `number`

1 和大于 1 的最小浮点数之间的差值。(double)

___

### DBL\_HAS\_SUBNORM <Score text="DBL" /> 

▪ `Static` **DBL\_HAS\_SUBNORM**: `number`

指明类型是否支持非正规数值：-1 为不确定，0 为不支持，1 为支持。 (double)

___

### DBL\_MANT\_DIG <Score text="DBL" /> 

▪ `Static` **DBL\_MANT\_DIG**: `number`

有效数字（尾数）的位数(double)

___

### DBL\_MAX <Score text="DBL" /> 

▪ `Static` **DBL\_MAX**: `number`

最大的有效浮点数的值（为正数），也即浮点数的最大值。(double)

___

### DBL\_MAX\_10\_EXP <Score text="DBL" /> 

▪ `Static` **DBL\_MAX\_10\_EXP**: `number`

分别为能够使 10 的该整数减一次幂为可表示的有限的最大正整数 (double)

___

### DBL\_MAX\_EXP <Score text="DBL" /> 

▪ `Static` **DBL\_MAX\_EXP**: `number`

最大二进制指数 (double)

___

### DBL\_MIN <Score text="DBL" /> 

▪ `Static` **DBL\_MIN**: `number`

最小规格化正数值 (double)

___

### DBL\_MIN\_10\_EXP <Score text="DBL" /> 

▪ `Static` **DBL\_MIN\_10\_EXP**: `number`

能够使 10 的该整数减一次幂为规格化的最小负整数 (double)

___

### DBL\_MIN\_EXP <Score text="DBL" /> 

▪ `Static` **DBL\_MIN\_EXP**: `number`

能够使FLT_RADIX 的该整数减一次幂为规格化的最小负整数 (double)

___

### DBL\_RADIX <Score text="DBL" /> 

▪ `Static` **DBL\_RADIX**: `number`

基数(进制)(double)

___

### DBL\_TRUE\_MIN <Score text="DBL" /> 

▪ `Static` **DBL\_TRUE\_MIN**: `number`

最小正数值(double)

___

### EPSILON <Score text="EPSILON" /> 

▪ `Static` **EPSILON**: `number`

最小误差数

___

### FLOAT\_NON\_FRACTIONAL <Score text="FLOAT" /> 

▪ `Static` **FLOAT\_NON\_FRACTIONAL**: `number`

所有大于或等于此值的单精度浮点数都没有小数

___

### FLT\_DECIMAL\_DIG <Score text="FLT" /> 

▪ `Static` **FLT\_DECIMAL\_DIG**: `number`

序列化/反序列化浮点值所要求的十进制精度 (float)

___

### FLT\_DIG <Score text="FLT" /> 

▪ `Static` **FLT\_DIG**: `number`

文本的往返转换中保留而不会因舍入或溢出发生改变的的十进制位数 (float)

___

### FLT\_EPSILON <Score text="FLT" /> 

▪ `Static` **FLT\_EPSILON**: `number`

1 和大于 1 的最小浮点数之间的差值。(float)

___

### FLT\_GUARD <Score text="FLT" /> 

▪ `Static` **FLT\_GUARD**: `number`

算术结果中是否使用保护位(例如 0)

___

### FLT\_HAS\_SUBNORM <Score text="FLT" /> 

▪ `Static` **FLT\_HAS\_SUBNORM**: `number`

指明类型是否支持非正规数值：-1 为不确定，0 为不支持，1 为支持。

___

### FLT\_MANT\_DIG <Score text="FLT" /> 

▪ `Static` **FLT\_MANT\_DIG**: `number`

有效数字（尾数）的位数 (float)

___

### FLT\_MAX <Score text="FLT" /> 

▪ `Static` **FLT\_MAX**: `number`

最大的有效浮点数的值(为正数)，也即浮点数的最大值。(float)

___

### FLT\_MAX\_10\_EXP <Score text="FLT" /> 

▪ `Static` **FLT\_MAX\_10\_EXP**: `number`

转换成十进制形式后，规格化浮点数的指数的最大值（为正数）。 (float)

___

### FLT\_MAX\_EXP <Score text="FLT" /> 

▪ `Static` **FLT\_MAX\_EXP**: `number`

最大二进制指数 (float)

___

### FLT\_MIN <Score text="FLT" /> 

▪ `Static` **FLT\_MIN**: `number`

最小正规值 (float)

___

### FLT\_MIN\_10\_EXP <Score text="FLT" /> 

▪ `Static` **FLT\_MIN\_10\_EXP**: `number`

最小十进制指数 (float)

___

### FLT\_MIN\_EXP <Score text="FLT" /> 

▪ `Static` **FLT\_MIN\_EXP**: `number`

最小二进制指数 (float)

___

### FLT\_NORMALIZE <Score text="FLT" /> 

▪ `Static` **FLT\_NORMALIZE**: `number`

指示应始终规范化浮点数。

___

### FLT\_RADIX <Score text="FLT" /> 

▪ `Static` **FLT\_RADIX**: `number`

基数(进制)(float)

___

### FLT\_TRUE\_MIN <Score text="FLT" /> 

▪ `Static` **FLT\_TRUE\_MIN**: `number`

最小正数值 (float)

___

### HALF\_PI <Score text="HALF" /> 

▪ `Static` **HALF\_PI**: `number`

PI/2

___

### INV\_PI <Score text="INV" /> 

▪ `Static` **INV\_PI**: `number`

1/PI

___

### R2D <Score text="R" /> 

▪ `Static` **R2D**: `number`

弧度转换角度参数

___

### SIGN\_BIT <Score text="SIGN" /> 

▪ `Static` **SIGN\_BIT**: `number`

字节偏移

## Methods

### angleCheck <Score text="angleCheck" /> 

• `Static` **angleCheck**(`StartLocation`, `StartDirection`, `TargetLocation`, `Angle`): `boolean` 

判断终点位置是否处于起点位置在某一方向的一定角度内

#### Parameters

| `StartLocation` [`Vector`](mw.Vector.md) | 起始位置 |
| :------ | :------ |
| `StartDirection` [`Vector`](mw.Vector.md) | 起始方向 |
| `TargetLocation` [`Vector`](mw.Vector.md) | 目标位置 |
| `Angle` `number` | 检测角度 range:[-360,360] type: 浮点数 |

#### Returns

| `boolean` | true，在角度范围内 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例: 如下示例原点X方向进行60度角的检测基本流程，假设目标位置（100,20,20）
</span>

```ts
if(angleCheck(new mw.Vector(0,0,0), new mw.Vector(1,0,0), new mw.Vector(100,20,20), 60)) {
// 在范围内
}
else {
// 不在范围内
}
```

___

### areFloatsEqual <Score text="areFloatsEqual" /> 

• `Static` **areFloatsEqual**(`a`, `b`, `epsilon?`): `boolean` 

判断浮点数是否近似相等

#### Parameters

| `a` `number` | 对比变量 a range: 数据大小不做限制 type: 浮点 |
| :------ | :------ |
| `b` `number` | 对比变量 b range: 数据大小不做限制 type: 浮点 |
| `epsilon?` `number` | 判断精度 range: 数据大小不做限制 type: 浮点 default: MathUtil.EPSILON(1.e-7) |

#### Returns

| `boolean` | true，两浮点数近似相等 |
| :------ | :------ |

___

### clamp <Score text="clamp" /> 

• `Static` **clamp**(`a`, `min`, `max`): `number` 

将传入的数值 a 限制在 min 与 max 范围内，超出部分自动舍弃

#### Parameters

| `a` `number` | 数值 a range: 数据大小不做限制 type: 浮点数 |
| :------ | :------ |
| `min` `number` | 最小值 range: 数据大小不做限制 min < max type: 浮点数 |
| `max` `number` | 最大值 range: 数据大小不做限制 min < max type: 浮点数 |

#### Returns

| `number` | 计算结果 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为MathExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，日志会输出20的最大值为10的值。
</span>

```ts
@Component
export default class MathExample extends Script {

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        this.test();
    }

    private async test(): Promise<void> {
        let clamp = MathUtil.clamp(20, 0, 10);
        console.log(`clamp: ${clamp}`);
    }

}
```

___

### cos <Score text="cos" /> 

• `Static` **cos**(`a`): `number` 

计算 cos 值

#### Parameters

| `a` `number` | 待计算的数值 a range: 数据大小不做限制 type: 浮点数 |
| :------ | :------ |

#### Returns

| `number` | cos值 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为MathExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，日志会输出cos值-1。
</span>

```ts
@Component
export default class MathExample extends Script {

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        this.test();
    }

    //输出弧度制的cos值
    private async test(): Promise<void> {
        let cos = MathUtil.cos(Math.PI);
        console.log(`cos: ${cos}`);
    }
}
```

___

### degreesToRadians <Score text="degreesToRadians" /> 

• `Static` **degreesToRadians**(`a`): `number` 

根据输入的度数返回弧度值

#### Parameters

| `a` `number` | 度数 range: 数据大小不做限制 type: 浮点数 |
| :------ | :------ |

#### Returns

| `number` | 弧度值 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为MathExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，日志会输出180度角的弧度值。
</span>

```ts
@Component
export default class MathExample extends Script {

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        this.test();
    }

    private async test(): Promise<void> {
        let degree = 180;
        let radians = MathUtil.degreesToRadians(degree);
        console.log(`degreesToRadians: ${radians}`);
    }

}
```

___

### fmod <Score text="fmod" /> 

• `Static` **fmod**(`x`, `y`): `number` 

数值 x 除以数值 y 的余数

#### Parameters

| `x` `number` | 数值 x range: 数据大小不做限制 type: 浮点数 |
| :------ | :------ |
| `y` `number` | 数值 y range: 数据大小不做限制 type: 浮点数 |

#### Returns

| `number` | 数值x 除以 数值y 的余数 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为MathExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，日志会输出20除以3的余数。
</span>

```ts
@Component
export default class MathExample extends Script {

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        this.test();
    }

    private async test(): Promise<void> {
        let fmod = MathUtil.fmod(20, 3);
        console.log(`fmod: ${fmod}`);
    }

}
```

___

### lerp <Score text="lerp" /> 

• `Static` **lerp**(`a`, `b`, `alpha`): `number` 

基于 alpha 在 数值a 和 数值b 之间线性插值

#### Parameters

| `a` `number` | 数值 a range: 数据大小不做限制 type: 浮点数 |
| :------ | :------ |
| `b` `number` | 数值 b range: 数据大小不做限制 type: 浮点数 |
| `alpha` `number` | 插值 <br> range: [0, 1] type:浮点数 |

#### Returns

| `number` | 计算结果 |
| :------ | :------ |

::: warning Precautions

alpha=0 时 数值 a 的 100% 和 alpha = 1 时 数值 b 的 100%

:::

<span style="font-size: 14px;">
使用示例:创建一个名为MathExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，日志会输出1和10之间的中间值。
</span>

```ts
@Component
export default class MathExample extends Script {

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        this.test();
    }

    private async test(): Promise<void> {
        let lerp = MathUtil.lerp(1, 10, 0.5);
        console.log(`lerp: ${lerp}`);
    }

}
```

___

### radiansToDegrees <Score text="radiansToDegrees" /> 

• `Static` **radiansToDegrees**(`a`): `number` 

根据输入的弧度值返回度数

#### Parameters

| `a` `number` | 弧度值 <br> range: 数据大小不做限制 type: 浮点数 |
| :------ | :------ |

#### Returns

| `number` | 度数 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为MathExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，日志会输出π的度数。
</span>

```ts
@Component
export default class MathExample extends Script {

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        this.test();
    }

    private async test(): Promise<void> {
        let radian = Math.PI;
        let degrees = MathUtil.radiansToDegrees(radian);
        console.log(`radiansToDegrees: ${degrees}`);
    }

}
```

___

### randomFloat <Score text="randomFloat" /> 

• `Static` **randomFloat**(`min`, `max`): `number` 

获取随机范围内浮点数[包含min, 不包含max)

#### Parameters

| `min` `number` | 最小值 range: 数据大小不做限制 type: 浮点数 |
| :------ | :------ |
| `max` `number` | 最大值 range: 数据大小不做限制 type: 浮点数 |

#### Returns

| `number` | 随机范围内的浮点数 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为MathExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，日志会输出1和10之间的随机浮点数。
</span>

```ts
@Component
export default class MathExample extends Script {

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        this.test();
    }

    private async test(): Promise<void> {
        let randomFloat = MathUtil.randomFloat(1, 10);
        console.log(`randomFloat: ${randomFloat}`);
    }

}
```

___

### randomInt <Score text="randomInt" /> 

• `Static` **randomInt**(`min`, `max`): `number` 

获取随机范围内整数[包含min, 不包含max)

#### Parameters

| `min` `number` | 最小值 range: 数据大小不做限制 type: 整形 |
| :------ | :------ |
| `max` `number` | 最大值 range: 数据大小不做限制 type: 整形 |

#### Returns

| `number` | 随机范围内的整数 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为MathExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，日志会输出1和10之间的随机整数。
</span>

```ts
@Component
export default class MathExample extends Script {

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        this.test();
    }

    private async test(): Promise<void> {
        let randomInt = MathUtil.randomInt(1, 10);
        console.log(`randomInt: ${randomInt}`);
    }

}
```

___

### sin <Score text="sin" /> 

• `Static` **sin**(`a`): `number` 

计算 sin 值

#### Parameters

| `a` `number` | 待计算的数值 a range: 数据大小不做限制 type: 浮点数 |
| :------ | :------ |

#### Returns

| `number` | sin值 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为MathExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，日志会输出sin值1。
</span>

```ts
@Component
export default class MathExample extends Script {

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        this.test();
    }

    //输出弧度制的sin值
    private async test(): Promise<void> {
        let sin = MathUtil.sin(Math.PI / 2);
        console.log(`sin: ${sin}`);
    }
}
```

___

### tan <Score text="tan" /> 

• `Static` **tan**(`a`): `number` 

计算 tan 值

#### Parameters

| `a` `number` | 待计算的数值 a range: 数据大小不做限制 type: 浮点数 |
| :------ | :------ |

#### Returns

| `number` | tan值 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为MathExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，日志会输出Math.PI / 4的tan值。
</span>

```ts
@Component
export default class MathExample extends Script {

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        this.test();
    }

    //输出弧度制的tan值
    private async test(): Promise<void> {
        let tan = MathUtil.tan(Math.PI / 4);
        console.log(`tan: ${tan}`);
    }
}
```
