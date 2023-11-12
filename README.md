# cz-conventional-changelog-zh-cn

[![npm version](https://img.shields.io/npm/v/cz-conventional-changelog-zh-cn.svg?style=flat-square)](https://www.npmjs.org/package/cz-conventional-changelog-zh-cn)
[![npm downloads](https://img.shields.io/npm/dt/cz-conventional-changelog-zh-cn)](http://npm-stat.com/charts.html?package=cz-conventional-changelog-zh-cn&from=2023-11-01)

[English](./README_en_US.md) | 简体中文

符合 [conventional changelog](https://github.com/conventional-changelog/conventional-changelog) 标准的 **简体中文版** 提示，[cz-conventional-changelog](https://github.com/commitizen/cz-conventional-changelog) 的分叉（Fork）版本。

## 截图

![提交](./meta/screenshots/s1.png)

![日志](./meta/screenshots/s2.png)

## 配置

### package.json

与 commitizen 类似，可以通过 package.json 文件中的 `config.commitizen` 键来指定 cz-conventional-changelog-zh-cn 的配置。

```json5

{
// ...
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
              "feat": {
                "description": "添加新功能或功能性变化"
              },
              "fix": {
                "description": "修复 bug"
              },
              "docs": {
                "description": "只修改了文档"
              },
              "style": {
                "description": "修改了代码风格，不影响代码运行的变更"
              },
              "refactor": {
                "description": "重构代码，既不新增功能，也不是修复 bug"
              },
              "perf": {
                "description": "提升性能的代码更改"
              },
              "test": {
                "description": "增加或修改测试用例"
              },
              "build": {
                "description": "对构建过程或辅助工具和库的更改"
              },
              "chore": {
                "description": "对构建过程或辅助工具和库的更改"
              },
              "ci": {
                "description": "用于对持续集成（CI）配置文件和脚本的更改"
              },
              "revert": {
                "description": "撤销之前的提交"
              }
            }
        }
    }
// ...
}

```

### 环境变量

以下环境变量可用于覆盖任何默认配置或基于 package.json 的配置。

* CZ_TYPE = 默认类型
* CZ_SCOPE = 默认范围
* CZ_SUBJECT = 默认简要描述
* CZ_BODY = 默认正文
* CZ_MAX_HEADER_WIDTH = 标题最大长度
* CZ_MAX_LINE_WIDTH = 行最大长度

### Commitizen

初始化项目以使用 cz-conventional-changelog-zh-cn 适配器，更多内容请参考 [commitizen](https://github.com/commitizen/cz-cli) 主页。

```bash

# npm
commitizen init cz-conventional-changelog-zh-cn --save-dev --save-exact

# yarn
commitizen init cz-conventional-changelog-zh-cn --yarn --dev --exact

# pnpm
commitizen init cz-conventional-changelog-zh-cn --pnpm --save-dev --save-exact

```

> 注意：package.json 中的 `config.commitizen.types` 的配置，定义 commitizen 的提交类型与描述，如果未配置该项，当 commitizen 提示时，commitizen 使用默认的为英文版本。

> 建议：复制上面 package.json 中的 `config.commitizen.types` 配置到项目中。

更多提交类型的说明请参考 [conventional-changelog 提交类型](./meta/docs/conventional-changelog-types.md)。

### Commitlint

如果使用 [commitlint](https://github.com/conventional-changelog/commitlint) JavaScript 库，`maxHeaderWidth` 配置属性将默认使用 `header-max-length` 规则的配置值，而不是硬编码的默认值 100。这可以通过在 package.json 中设置 `maxHeaderWidth` 配置或者设置 `CZ_MAX_HEADER_WIDTH` 环境变量来进行覆盖。
