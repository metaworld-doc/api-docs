[基类](../groups/基类.基类.md) / Base

# Base <Badge type="tip" text="Class" /> <Score text="Base" />

GameObject和Script的基类，定义基础能力

## Hierarchy

- **`Base`**

  ↳ [`GameObject`](mw.GameObject.md)

  ↳ [`Script`](mw.Script.md)

## Table of contents

### Properties <Score text="Properties" /> 
| **[onPropertyChange](mw.Base.md#onpropertychange)**: `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\>  |
| :-----|
| 监听系统属性同步事件|

### Methods <Score text="Methods" /> 
| **[getPropertyChangeDelegate](mw.Base.md#getpropertychangedelegate)**(`property`): `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> <Badge type="tip" text="client" />  |
| :-----|
| 获取给定对象属性修改时触发的事件代理。|

## Properties

### onPropertyChange <Score text="onPropertyChange" /> 

• **onPropertyChange**: `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\>

监听系统属性同步事件

<span style="font-size: 14px;">
使用示例:监听属性变化
</span>

```ts
this.onPropertyChange.add((path, value, oldValue) => {
    console.log(`属性 ${path} 改变了，新值为 ${value}，旧值为 ${oldValue}`);
});
```

## Methods

### getPropertyChangeDelegate <Score text="getPropertyChangeDelegate" /> 

• **getPropertyChangeDelegate**(`property`): `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> <Badge type="tip" text="client" />

获取给定对象属性修改时触发的事件代理。

#### Parameters

| `property` `string` | 对象属性名字 例如：'x' 'rotation.x' range:不为空 |
| :------ | :------ |

#### Returns

| `Readonly`<[`MulticastDelegate`](mw.MulticastDelegate.md)<(`path`: `string`, `value`: `unknown`, `oldValue`: `unknown`) => `void`\>\> | 代理对象 |
| :------ | :------ |
