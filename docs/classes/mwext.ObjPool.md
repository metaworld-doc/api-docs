[基类](../groups/Extension.基类.md) / ObjPool

# ObjPool<T\> <Badge type="tip" text="Class" /> <Score text="ObjPool<T\>" />

通用对象池，可用于各种类型对象的复用

<span style="font-size: 14px;">
使用示例:创建一个名为ObjPoolExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，按F键会在玩家当前位置按照对象池中已有方块生成一个方块并在5秒后进行回收坐标回归到原点,频繁按F客户端日志会提示对象池中没有对象，按G键会销毁所有处于回收状态方块
</span>

```ts
@Component
export default class ObjPoolExample extends Script {

    private objPool: ObjPool<Cube>;

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        const cubeAssetId = "197386";
        AssetUtil.asyncDownloadAsset(cubeAssetId).then(() => {
            //初始化一个5个对象的对象池
            this.objPool = new ObjPool<Cube>(
                this.onCubeCreate,
                this.onCubeReset,
                this.onCubeDestroy,
                this.onCubeDespawn,
                5
            );
            InputUtil.onKeyDown(Keys.F, () => {
                let size = this.objPool.size;
                if (size <= 0) {
                    console.log("对象池中没有对象");
                    return;
                }
                let cube = this.objPool.spawn();
                setTimeout(() => {
                    //5秒后回收该方块
                    this.objPool.despawn(cube);
                    cube.obj.worldTransform.position = new Vector(0, 0, 0);
                }, 5000);
            });
            InputUtil.onKeyDown(Keys.G, () => {
                //将对象池中的已回收对象全部销毁
                this.objPool.clear();
            })
        });
    }

    //创建了新对象的回调
    private onCubeCreate(): Cube {
        let cube = new Cube();
        cube.obj.setCollision(CollisionStatus.Off);
        cube.obj.worldTransform.position = new Vector(0, 0, 0);
        return cube;
    }

    //重置对象的回调
    private onCubeReset(cube: Cube): void {
        let playerPos = mw.getCurrentPlayer().character.worldTransform.position;
        cube.obj.worldTransform.position = playerPos;
    }

    //销毁对象的回调
    private onCubeDestroy(cube: Cube): void {
        cube.obj.destroy();
        cube.obj = null;
    }

    //归还对象的回调
    private onCubeDespawn(cube: Cube): void {

    }

}

class Cube {

    public obj: mw.GameObject = null;

    constructor() {
        this.obj = mw.GameObject.spawn("197386");
    }
}
```

## Type parameters

| Name |
| :------ |
| `T` |

## Table of contents

### Accessors <Score text="Accessors" /> 
| **[size](mwext.ObjPool.md#size)**(): `number`   |
| :-----|
| 获取对象池中空闲对象的数量|

### Methods <Score text="Methods" /> 
| **[clear](mwext.ObjPool.md#clear)**(): `void`   |
| :-----|
| 清除池中对象|
| **[despawn](mwext.ObjPool.md#despawn)**(`obj`: `T`): `void`   |
| 归还一个对象|
| **[spawn](mwext.ObjPool.md#spawn)**(): `T`   |
| 生成一个对象|

构造一个对象池

#### Type parameters

| Name |
| :------ |
| `T` |

#### Parameters

| `onCreateObj` () => `T` |  创建新对象的回调 |
| :------ | :------ |
| `onReset?` (`obj`: `T`) => `void` |  重置对象的回调 default: null |
| `onDestroy?` (`obj`: `T`) => `void` |  销毁对象的回调 default: null |
| `onDespawn?` (`obj`: `T`) => `void` |  归还对象的回调 default: null |
| `initNum?` `number` |  默认缓存对象数量 default: 2 range: 不做限制 type: 整形 |

## Accessors

### size <Score text="size" /> 

<table class="get-set-table">
<thead><tr>
<th style="text-align: left">

• `get` **size**(): `number` 

</th>
</tr></thead>
<tbody><tr>
<td style="text-align: left">


获取对象池中空闲对象的数量

#### Returns

</td>
</tr></tbody>
</table>

| `number` |  |
| :------ | :------ |

## Methods

### clear <Score text="clear" /> 

• **clear**(): `void` 

清除池中对象


___

### despawn <Score text="despawn" /> 

• **despawn**(`obj`): `void` 

归还一个对象

#### Parameters

| `obj` `T` |  对象 |
| :------ | :------ |


___

### spawn <Score text="spawn" /> 

• **spawn**(): `T` 

生成一个对象

#### Returns

| `T` | 对象 |
| :------ | :------ |
