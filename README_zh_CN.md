# cz-conventional-changelog-zh-cn

<p align="center">
  <a href="README.md">English</a>
  <span style="margin: 0px 8px">|</span>
  <a href="README_zh_CN.md">中文</a>
</p>

cz-conventional-changelog 的分支，符合 [conventional changelog](https://github.com/conventional-changelog/conventional-changelog) 标准的简体中文提示。

## 配置

### package.json

与 commitizen 类似，可以通过 package.json 文件中的 `config.commitizen` 键来指定 cz-conventional-changelog-zh-cn 的配置。

```json5
{
// ...  默认值
    "config": {
        "commitizen": {
            "path": "./node_modules/cz-conventional-changelog-zh-cn",
            "disableScopeLowerCase": false,
            "disableSubjectLowerCase": false,
            "maxHeaderWidth": 100,
            "maxLineWidth": 100,
            "defaultType": "",
            "defaultScope": "",
            "defaultSubject": "",
            "defaultBody": "",
            "defaultIssues": "",
            "types": {
              ...
              "feat": {
                "description": "新的特性",
                "title": "特性"
              },
              ...
            }
        }
    }
// ...
}
```

> 重点关注下 `config.commitizen.types` 的配置，定义 commitizen 的提交类型与描述，如果未配置该项，当 commitizen 提示时，commitizen 使用默认的为英文版本。

### 环境变量

以下环境变量可用于覆盖任何默认配置或基于 package.json 的配置。

* CZ_TYPE = 默认类型
* CZ_SCOPE = 默认范围
* CZ_SUBJECT = 默认简要描述
* CZ_BODY = 默认正文
* CZ_MAX_HEADER_WIDTH = 标题最大长度
* CZ_MAX_LINE_WIDTH = 行最大长度

### Commitlint

如果使用 [commitlint](https://github.com/conventional-changelog/commitlint) JavaScript 库，"maxHeaderWidth" 配置属性将默认使用 "header-max-length" 规则的配置值，而不是硬编码的默认值 100。这可以通过在 package.json 中设置 'maxHeaderWidth' 配置或者设置 CZ_MAX_HEADER_WIDTH 环境变量来进行覆盖。
