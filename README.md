# prettierrc-best([github](https://github.com/luozyiii/prettierrc-best))

代码风格规范化最佳实践：prettierrc + vscode 插件和自定义工作区; 打造个性团队的最佳规范。

## 环境要求

vscode 编码开发

## 开始

- 1.安装 vscode 插件 Prettier - Code formatter
- 2.vscode 自定义工作区; 保存时自动格式化

```js
// .vscode/settings.json

{
  "editor.formatOnSave": true, // 保存的时候自动格式化
  "editor.defaultFormatter": "esbenp.prettier-vscode" // 默认格式化工具为 prettier
}
```

- 3.添加 .prettierrc.js, 自定义风格

```js
// .prettierrc.js
module.exports = {
  // 一行最多 120 字符
  printWidth: 120,
  // 使用 2 个空格缩进
  tabWidth: 4,
  // 不使用缩进符，而使用空格
  useTabs: false,
  // 行尾需要有分号
  semi: true,
  // 使用单引号
  singleQuote: true,
  // 对象的 key 仅在必要时用引号
  quoteProps: 'as-needed',
  // jsx 不使用单引号，而使用双引号
  jsxSingleQuote: false,
  // 末尾不需要逗号
  trailingComma: 'none',
  // 大括号内的首尾需要空格
  bracketSpacing: true,
  // jsx 标签的反尖括号需要换行
  jsxBracketSameLine: false,
  // 箭头函数，只有一个参数的时候，也需要括号
  arrowParens: 'always',
  // 每个文件格式化的范围是文件的全部内容
  rangeStart: 0,
  rangeEnd: Infinity,
  // 不需要写文件开头的 @prettier
  requirePragma: false,
  // 不需要自动在文件开头插入 @prettier
  insertPragma: false,
  // 使用默认的折行标准
  proseWrap: 'preserve',
  // 根据显示样式决定 html 要不要折行
  htmlWhitespaceSensitivity: 'css',
  // 换行符使用 lf
  endOfLine: 'lf'
};
```

### .prettierignore 忽略配置

```bash
# Ignore artifacts:
build
coverage
```

意味着 build 和 coverage 目录下的文件不会格式化

### Git hooks 代码提交前格式化

```

```

### 总结

- 无 npm 包无配置文件，使用 vscode 插件 prettier + settings.json。
- 有 npm 包无配置文件，使用 npm prettier + settings.json。
- 有 npm 包有配置文件，使用 npm prettier + .prettierrc.js。
- 无 npm 包有配置文件，使用 vscode 插件 prettier + .prettierrc.js。`示例就是这种，本文推荐`

## 资料

- [prettier 官网](https://www.prettier.cn/docs/install.html)
- [eslint-config-alloy](https://github.com/AlloyTeam/eslint-config-alloy)
