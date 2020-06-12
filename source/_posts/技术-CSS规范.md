---
title: '[技术]-CSS规范'
date: 2020-06-11 21:36:06
tags:
  - 技术
  - css
top: true
cover: false
summary: 总结日常开发中，写css的规范
categories: 技术
---
# CSS规范
`前端技术太多，不可能熟悉每一个知识点，熟知其核心尽快上手，需要用时再翻看api文档。`
`“敲出每一行完美的代码，默默的改变这个世界！”`

------
现在前端技术鱼龙混杂，各种css技术层出不穷，花了不少时间整理规范跟技术，总结css开发解决方案。



### 核心技术点

选择器、css值和单位、继承、盒模型、浏览器调试、定位、层叠、flexBox布局、媒体查询。



## 说明

- OOCSS 面向对象的方式编写css      ——  模块化
- BEM改善命名css的思考方式            ——  高效率
- ITCSS的倒三角css结构规范              ——  结构规范
- styleLint树立书写规则
- scss 预处理器



### 1.OOCSS。

1. 重用，编写基本外观的组件（容器） .button｛…｝
2. 扩展，添加其他特性（外观）.button -3d{…}
3. 维护性，想更改容器还是内容、还是扩展？



### 2.BEM命名。

永远都是 Block-Element_Modifier 的格式

可以使用驼峰命名



### 3.ITCSS规范结构。

样式层级不能超过三层。

1. 还原本质

   ```
   // css页面重置
   yarn add normalize.css
   ```

2. 设置（基本颜色、排版、动画）、工具（函数、mixins）

3. 元素的固定样式、扩展样式



### 4.没有规矩，不成方圆

让SCSS规范保持一致

```
// stylelint stylelnit-order规则顺序 代码风格 配置规则
yarn add stylelint stylelint-order stylelint-config-standard stylelint-config-recess-order --dev

// 配置 .stylelintrc.json
{
  "extends": ["stylelint-config-standard", "stylelint-config-recess-order"],
  "rules": {
    "at-rule-no-unknown": [true, {"ignoreAtRules" :[
      "mixin", "extend", "content"
    ]}]
  }
}

// package.json
"stylelint": "stylelint src/css/**/*.scss src/css/**/*.css"
```



#### 举个栗子

```html
// html
<div class="search search_mode">
   // form为基础样式  search-form为扩展容器样式  search-form_mode为扩展外观样式
  <form class="form search-form search-form_mode">
    // search-form 为父级块
    <div class="content search-form-content search-form-content_mode">
      // 同form注释
      <input class="input content-input content-input_mode">
      <button class="button content-button content-button_mode">Search</button>
       // 三层以上，还存在快，只取父级块content
       <div class="content-media content-media_mode">
            <input class="input media-input media-input_mode">
      		<button class="button media-button media-button_mode">Search</button>
       </div>
    </div>
  </form>
</div>
```

```scss
.search {
    .search-form {
        width: xx;
        height: xx;
        .search-form-content {}
        .search-form-content_mode {}
    }
    .search-form_mode {
        font-size: xx;
        background: xx;
    }
}

.search_mode {
    ...外观样式
}

.search-form-content {
    .content-input: {}
    .content-input_mode: {}
    .content-button: {}
    .content-button_mode: {}
    .content-media: {
        .media-input: {}
        .media-input_mode: {}
        .media-button: {}
        .media-button_mode: {}
    }
}

.from {
    ...from全局样式
}
.content {
    ...content全局样式
}
.input {
    ...content全局样式
}
.button {
    ...button全局样式
}
```



##### 最后

- 尽量不使用!important
- [尽量不使用float](https://www.zhangxinxu.com/wordpress/2010/01/css-float%E6%B5%AE%E5%8A%A8%E7%9A%84%E6%B7%B1%E5%85%A5%E7%A0%94%E7%A9%B6%E3%80%81%E8%AF%A6%E8%A7%A3%E5%8F%8A%E6%8B%93%E5%B1%95%E4%BA%8C/)
- 尽量不要使用*这样的全局选择器
- 尽量在样式表中添加注释
- 在样式中避免使用#id
- 设置z-index层级不要超过10
- 声明每条一行
- scss层叠不超过3层


















