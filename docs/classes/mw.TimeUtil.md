[工具](../groups/工具.工具.md) / TimeUtil

# TimeUtil <Badge type="tip" text="Class" /> <Score text="TimeUtil" />

时间工具

## Table of contents

### Properties <Score text="Properties" /> 
| **[onEnterFrame](mw.TimeUtil.md#onenterframe)**: [`Action1`](mw.Action1.md)<`number`\>  |
| :-----|
| 帧刷新事件(参数deltaTime)|
| **[traceFrameTime](mw.TimeUtil.md#traceframetime)**: `boolean`  |
| 是否输出每帧的执行时间|

### Methods <Score text="Methods" /> 
| **[clearDelayExecute](mw.TimeUtil.md#cleardelayexecute)**(`id`: `number`): `void`   |
| :-----|
| 清除 delayExecute|
| **[clearInterval](mw.TimeUtil.md#clearinterval)**(`id`: `number`): `void`   |
| 清除 setInterval|
| **[delayExecute](mw.TimeUtil.md#delayexecute)**(`handler`: () => `void`, `frameNum?`: `number`): `number`   |
| 延迟一定帧数执行方法|
| **[delaySecond](mw.TimeUtil.md#delaysecond)**(`second`: `number`): `Promise`<`void`\>   |
| 延迟一定秒数，用于异步方法中间的等待|
| **[deltatime](mw.TimeUtil.md#deltatime)**(): `number`   |
| 每一帧经过的时间 (单位：秒)|
| **[elapsedTime](mw.TimeUtil.md#elapsedtime)**(): `number`   |
| 返回自游戏运行后所经过的总时长，单位秒，精确到毫秒。|
| **[parseTime](mw.TimeUtil.md#parsetime)**(`timeData`: `Date`, `format?`: `string`): `string`   |
| 格式化时间戳|
| **[setInterval](mw.TimeUtil.md#setinterval)**(`handler`: () => `void`, `timeout`: `number`, `exitJudge?`: () => `boolean`): `number`   |
| 按一定时间间隔执行方法|
| **[time](mw.TimeUtil.md#time)**(): `number`   |
| 返回当前本地会话所在的电脑自 UNIX Epoch（UNIX 纪元）开始所经过的时间（以秒为单位）。|

## Properties

### onEnterFrame <Score text="onEnterFrame" /> 

▪ `Static` **onEnterFrame**: [`Action1`](mw.Action1.md)<`number`\>

帧刷新事件(参数deltaTime)

::: warning Precautions

每次update自动执行所绑定的方法

:::

<span style="font-size: 14px;">
使用示例:创建一个名为TimeExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，会每帧输出dt
</span>

```ts
@Component
export default class TimeExample extends Script {

    protected onStart(): void {
        this.test();
    }

    private async test(): Promise<void> {
        if (!SystemUtil.isClient()) return;
        TimeUtil.onEnterFrame.add(this.onEnterFrame, this);
    }

    private onEnterFrame(dt: number): void {
        console.log("dt", dt);
    }

}
```

___

### traceFrameTime <Score text="traceFrameTime" /> 

▪ `Static` **traceFrameTime**: `boolean`

是否输出每帧的执行时间

## Methods

### clearDelayExecute <Score text="clearDelayExecute" /> 

• `Static` **clearDelayExecute**(`id`): `void` 

清除 delayExecute

#### Parameters

| `id` `number` |  delayExecute 方法返回的 ID <br> range: 根据 ID 长度而定。 type: 整形 |
| :------ | :------ |


<span style="font-size: 14px;">
使用示例:创建一个名为TimeExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，原本会延迟600帧执行，现在不会执行
</span>

```ts
@Component
export default class TimeExample extends Script {

    protected onStart(): void {
        this.test();
    }

    private async test(): Promise<void> {
        if (!SystemUtil.isClient()) return;
        let id = TimeUtil.delayExecute(() => {
            //延迟600帧执行 pie环境大概10s
            console.log("delay 600execute");
        }, 600)
        TimeUtil.clearDelayExecute(id);
//清除延迟执行
    }

}
```

___

### clearInterval <Score text="clearInterval" /> 

• `Static` **clearInterval**(`id`): `void` 

清除 setInterval

#### Parameters

| `id` `number` |  setInterval 方法返回的 ID <br> range: 根据 ID 长度而定。 type: 浮点数 |
| :------ | :------ |


<span style="font-size: 14px;">
使用示例:创建一个名为TimeExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，原本会每隔2秒执行一次输出id 直到id>5，按下F键后会提前停止
</span>

```ts
@Component
export default class TimeExample extends Script {

    protected onStart(): void {
        this.test();
    }

    private async test(): Promise<void> {
        if (!SystemUtil.isClient()) return;
        let isInterval = false;
        let id = 0;
        let ineterval = TimeUtil.setInterval(() => {
            console.log(id);
            id++;
            if (id > 5) {
                isInterval = true;
            }
        }, 2, () => {
            return isInterval;
        })
        InputUtil.onKeyDown(Keys.F, () => {
            TimeUtil.clearInterval(ineterval);
        })
    }

}
```

___

### delayExecute <Score text="delayExecute" /> 

• `Static` **delayExecute**(`handler`, `frameNum?`): `number` 

延迟一定帧数执行方法

#### Parameters

| `handler` () => `void` |  执行的方法 |
| :------ | :------ |
| `frameNum?` `number` |  要延迟的帧数 default: 1 <br> range: 根据你想要延迟的帧数而定，不做限制。 type: 整形 |

#### Returns

| `number` | 用于停止的ID |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为TimeExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，会延迟600帧执行
</span>

```ts
@Component
export default class TimeExample extends Script {

    protected onStart(): void {
        this.test();
    }

    private async test(): Promise<void> {
        if (!SystemUtil.isClient()) return;
        TimeUtil.delayExecute(() => {
            //延迟600帧执行 pie环境大概10s
            console.log("delay 600execute");
        }, 600)
    }
}
```

___

### delaySecond <Score text="delaySecond" /> 

• `Static` **delaySecond**(`second`): `Promise`<`void`\> 

延迟一定秒数，用于异步方法中间的等待

#### Parameters

| `second` `number` |  时间(单位：秒) <br> range: 不限制 type: 浮点数 |
| :------ | :------ |

#### Returns

| `Promise`<`void`\> | Promise |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为TimeExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，会5秒后输出5 seconds later
</span>

```ts
@Component
export default class TimeExample extends Script {

    protected onStart(): void {
        this.test();
    }

    private async test(): Promise<void> {
        if (!SystemUtil.isClient()) return;
        TimeUtil.delaySecond(5).then(() => {
            console.log("5 seconds later");
        })
    }

}
```

___

### deltatime <Score text="deltatime" /> 

• `Static` **deltatime**(): `number` 

每一帧经过的时间 (单位：秒)

#### Returns

| `number` | number（单位：秒） |
| :------ | :------ |

::: warning Precautions

调用这个函数之前两次Update函数调用之间的间隔时间

:::

___

### elapsedTime <Score text="elapsedTime" /> 

• `Static` **elapsedTime**(): `number` 

返回自游戏运行后所经过的总时长，单位秒，精确到毫秒。

#### Returns

| `number` | 自游戏运行后所经过的总时长。 |
| :------ | :------ |

::: warning Precautions

在 Editor 中，该数值是从每次开始运行起计算，而非从打开 Editor 场景起计算。

:::

<span style="font-size: 14px;">
使用示例:创建一个名为TimeExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，按F键会输出游戏运行的总时长
</span>

```ts
@Component
export default class TimeExample extends Script {

    protected onStart(): void {
        this.test();
    }

    private async test(): Promise<void> {
        if (!SystemUtil.isClient()) return;
        InputUtil.onKeyDown(Keys.F, () => {
            const elapsedTime = TimeUtil.elapsedTime();
            console.log(`The game ran for ${elapsedTime} seconds`);
        });
    }

}
```

___

### parseTime <Score text="parseTime" /> 

• `Static` **parseTime**(`timeData`, `format?`): `string` 

格式化时间戳

#### Parameters

| `timeData` `Date` | 标准时间，时间戳等 |
| :------ | :------ |
| `format?` `string` | 日期字符串 default:outer range: 传入时间格式，如：1996-01-20 |

#### Returns

| `string` | 格式化后时间字符串 |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为TimeExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，会输出当前时间
</span>

```ts
@Component
export default class TimeExample extends Script {

    protected onStart(): void {
       this.test();
    }

    private async test(): Promise<void> {
       if (!SystemUtil.isClient()) return;
       const time = TimeUtil.parseTime(new Date());
       console.log(`time:${time}`);
    }

}
```

___

### setInterval <Score text="setInterval" /> 

• `Static` **setInterval**(`handler`, `timeout`, `exitJudge?`): `number` 

按一定时间间隔执行方法

#### Parameters

| `handler` () => `void` |  要执行的方法 |
| :------ | :------ |
| `timeout` `number` |  间隔时间（最小时间为两帧时间差 单位：秒） <br> range:[0, +∞] type: 浮点数 |
| `exitJudge?` () => `boolean` |  退出的判断方法 返回 true 停止 default: null |

#### Returns

| `number` | 用于停止的 ID |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为TimeExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，会每隔2秒执行一次输出id 直到id>5
</span>

```ts
@Component
export default class TimeExample extends Script {

    protected onStart(): void {
        this.test();
    }

    private async test(): Promise<void> {
        if (!SystemUtil.isClient()) return;
        let isInterval = false;
        let id = 0;
        TimeUtil.setInterval(() => {
            console.log(id);
            id++;
            if (id > 5) {
                isInterval = true;
            }
        }, 2, () => {
            return isInterval;
        })
    }

}
```

___

### time <Score text="time" /> 

• `Static` **time**(): `number` 

返回当前本地会话所在的电脑自 UNIX Epoch（UNIX 纪元）开始所经过的时间（以秒为单位）。

#### Returns

| `number` | （UNIX 纪元）开始所经过的秒数。 |
| :------ | :------ |

::: warning Precautions

UNIX 纪元的开始日期为 1970 年 1 月 1 日。

:::

<span style="font-size: 14px;">
使用示例:创建一个名为TimeExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，会输出当前时间戳
</span>

```ts
@Component
export default class TimeExample extends Script {

    protected onStart(): void {
        this.test();
    }

    private async test(): Promise<void> {
        if (!SystemUtil.isClient()) return;
        const time = TimeUtil.time();
        console.log(`time stamp:${time}`);
    }

}
```
