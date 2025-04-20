请作为专业前端开发工程师，为 CSS/LESS 文件中的所有类选择器添加指定前缀。

**处理规则:**
1. 将所有类选择器（`.example`）添加前缀 `{{prefix}}`（变为 `.{{prefix}}example`）
2. 已有 `{{prefix}}` 前缀的类选择器不重复添加
3. 不修改 ID 选择器、属性选择器、元素选择器、伪元素等非类选择器
4. 处理组合选择器和多层嵌套（如 `.a .b .c` → `.{{prefix}}a .{{prefix}}b .{{prefix}}c`）
5. 对 LESS 特有语法：
   - 父选择器引用（&）保持不变，但主选择器需加前缀（`.menu { &-item {} }` → `.{{prefix}}menu { &-item {} }`）
   - 保留变量、混合、导入等原样不变
   - 处理嵌套规则、媒体查询中的所有类选择器
6. 特殊情况处理：
   - 多重选择器（`.a, .b`）分别添加前缀
   - 伪类和伪元素（`.btn:hover::before`）正确处理
   - 复杂组合（`.a > .b + .c ~ .d`）正确处理所有类选择器

**输出格式:**
仅输出修改后的完整代码，不包含任何解释文字，保持原有缩进和格式。

示例输入(LESS)：
```less
.header {
  color: red;
  .title {
    font-size: 20px;
    &:hover { color: blue; }
  }
  &-logo { width: 100px; }
}
.{{prefix}}footer {
  @media (max-width: 768px) {
    .copyright { font-size: 12px; }
  }
}
#main { color: green; }
```

示例输出(LESS)：
```less
.{{prefix}}header {
  color: red;
  .{{prefix}}title {
    font-size: 20px;
    &:hover { color: blue; }
  }
  &-logo { width: 100px; }
}
.{{prefix}}footer {
  @media (max-width: 768px) {
    .{{prefix}}copyright { font-size: 12px; }
  }
}
#main { color: green; }
```

请处理以下CSS/LESS代码：
```less
{{content}}
```请作为专业前端开发工程师，为 CSS/LESS 文件中的所有类选择器添加指定前缀。

**处理规则:**
1. 将所有类选择器（`.example`）添加前缀 `{{prefix}}`（变为 `.{{prefix}}example`）
2. 已有 `{{prefix}}` 前缀的类选择器不重复添加
3. 不修改 ID 选择器、属性选择器、元素选择器、伪元素等非类选择器
4. 处理组合选择器和多层嵌套（如 `.a .b .c` → `.{{prefix}}a .{{prefix}}b .{{prefix}}c`）
5. 对 LESS 特有语法：
   - 父选择器引用（&）保持不变，但主选择器需加前缀（`.menu { &-item {} }` → `.{{prefix}}menu { &-item {} }`）
   - 保留变量、混合、导入等原样不变
   - 处理嵌套规则、媒体查询中的所有类选择器
6. 特殊情况处理：
   - 多重选择器（`.a, .b`）分别添加前缀
   - 伪类和伪元素（`.btn:hover::before`）正确处理
   - 复杂组合（`.a > .b + .c ~ .d`）正确处理所有类选择器

**输出格式:**
仅输出修改后的完整代码，不包含任何解释文字，保持原有缩进和格式。

示例输入(LESS)：
```less
.header {
  color: red;
  .title {
    font-size: 20px;
    &:hover { color: blue; }
  }
  &-logo { width: 100px; }
}
.{{prefix}}footer {
  @media (max-width: 768px) {
    .copyright { font-size: 12px; }
  }
}
#main { color: green; }
```

示例输出(LESS)：
```less
.{{prefix}}header {
  color: red;
  .{{prefix}}title {
    font-size: 20px;
    &:hover { color: blue; }
  }
  &-logo { width: 100px; }
}
.{{prefix}}footer {
  @media (max-width: 768px) {
    .{{prefix}}copyright { font-size: 12px; }
  }
}
#main { color: green; }
```

请处理以下CSS/LESS代码：
```less
{{content}}
```