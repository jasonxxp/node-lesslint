CHANGELOG
===

#### 2015.12.10

1. 读取文件流，提高性能。
2. block-indent: 分析 mixin 时，由于 AST 上没有 index 属性，因此无法获取行号，默认会获取到最后一行，因此行内容部准确，会造成错误。修改的方法是把 mixin 在全局匹配获取 index，根据这个 index 去获取行号和行内容。
3. 获取属性名称时，如果 name 是数组，那么 name.reduce 循环时 item 可能没有 toCSS 方法，本次加上了一个后备方案。
4. variable-name: 修复了 `@{aa}@{bb}@{cc}: value;` 的问题