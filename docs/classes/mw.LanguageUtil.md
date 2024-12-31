[工具](../groups/工具.工具.md) / LanguageUtil

# LanguageUtil <Badge type="tip" text="Class" /> <Score text="LanguageUtil" />

多语言工具

## Table of contents

### Methods <Score text="Methods" /> 
| **[addKey](mw.LanguageUtil.md#addkey)**(`textkey`: `string`): `string` <Badge type="tip" text="client" />  |
| :-----|
| 多语言标记|
| **[getDefaultLocale](mw.LanguageUtil.md#getdefaultlocale)**(): `string`   |
| 获取默认的语言和地区|
| **[getText](mw.LanguageUtil.md#gettext)**(`textkey`: `string`): `string` <Badge type="tip" text="client" />  |
| 根据key获取翻译内容|
| **[getlanguage](mw.LanguageUtil.md#getlanguage)**(): [`LanguageCodeType`](../enums/mw.LanguageCodeType.md) <Badge type="tip" text="client" />  |
| 获取当前本地化语言|
| **[setLanguage](mw.LanguageUtil.md#setlanguage)**(`type`: [`LanguageCodeType`](../enums/mw.LanguageCodeType.md)): `boolean` <Badge type="tip" text="client" />  |
| 游戏语言设置|

## Methods

### addKey <Score text="addKey" /> 

• `Static` **addKey**(`textkey`): `string` <Badge type="tip" text="client" />

多语言标记

#### Parameters

| `textkey` `string` | 用户多语言配置表收集的 Key range: 不做限制 |
| :------ | :------ |

#### Returns

| `string` | 返回Key，此函数只用于做翻译文本收集标识。 |
| :------ | :------ |

___

### getDefaultLocale <Score text="getDefaultLocale" /> 

• `Static` **getDefaultLocale**(): `string` 

获取默认的语言和地区

#### Returns

| `string` | 可选ISO 3166-1 国家码 (如, "CN") |
| :------ | :------ |

<span style="font-size: 14px;">
使用示例:创建一个名为LocaleExample的脚本，放置在对象栏中，打开脚本，将原本内容修改为如下内容，保存并运行游戏，日志会输出默认的语言和地区
</span>

```ts
@Component
export default class LocaleExample extends Script {

    protected onStart(): void {
        if (!SystemUtil.isClient()) return;
        this.test();
    }

    private async test(): Promise<void> {
        const locale = LanguageUtil.getDefaultLocale();
        console.log(`locale: ${locale}`);
// zh-CN
    }
}
```

___

### getText <Score text="getText" /> 

• `Static` **getText**(`textkey`): `string` <Badge type="tip" text="client" />

根据key获取翻译内容

#### Parameters

| `textkey` `string` | 需要查找的翻译的 key range: 不做限制 |
| :------ | :------ |

#### Returns

| `string` | 返回Key对应的当前语言环境的翻译内容 |
| :------ | :------ |

___

### getlanguage <Score text="getlanguage" /> 

• `Static` **getlanguage**(): [`LanguageCodeType`](../enums/mw.LanguageCodeType.md) <Badge type="tip" text="client" />

获取当前本地化语言

#### Returns

| [`LanguageCodeType`](../enums/mw.LanguageCodeType.md) | 语言枚举对象 |
| :------ | :------ |

___

### setLanguage <Score text="setLanguage" /> 

• `Static` **setLanguage**(`type`): `boolean` <Badge type="tip" text="client" />

游戏语言设置

#### Parameters

| `type` [`LanguageCodeType`](../enums/mw.LanguageCodeType.md) | 切换游戏语言种类 |
| :------ | :------ |

#### Returns

| `boolean` | true修改成功 false修改失败 |
| :------ | :------ |
