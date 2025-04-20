请作为专业前端开发工程师，将小程序 WXML/AXML 文件中所有 class 属性的类名添加 `{{prefix}}` 前缀，规则如下：

1. 所有类名均加前缀，已带 `{{prefix}}` 的不重复添加
2. 正确处理多个类名（空格分隔）、动态绑定（如 `class="item {{active ? 'active' : ''}}"`)和插值表达式
3. 保持原有空格、引号及缩进格式，不修改其他属性和标签
4. 仅输出修改后的完整代码，不包含解释说明

示例输入:
```
<view class="container">
  <view class="header {{isFixed ? 'fixed' : ''}}">
    <text class="title">标题</text>
    <view class="{{prefix}}logo"></view>
  </view>
  <view class="content content-main active">
    <text>内容</text>
  </view>
</view>
```

示例输出:
```
<view class="{{prefix}}container">
  <view class="{{prefix}}header {{isFixed ? '{{prefix}}fixed' : ''}}">
    <text class="{{prefix}}title">标题</text>
    <view class="{{prefix}}logo"></view>
  </view>
  <view class="{{prefix}}content {{prefix}}content-main {{prefix}}active">
    <text>内容</text>
  </view>
</view>
```

请处理以下 WXML/AXML 代码：
```xml
{{content}}
```