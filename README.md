## 简介
BEM 的意思就是块（block）、元素（element）、修饰符（modifier），是由 Yandex 团队提出的一种前端命名方法论。这种巧妙的命名方法让你的 CSS 类对其他开发者来说更加透明而且更有意义。BEM 命名约定更加严格，而且包含更多的信息，它们用于一个团队开发一个耗时的大项目。
> 重要的是要注意，这里使用的基于 BEM 的命名方式是经过 Nicolas Gallagher 修改过的。

## 命名约定
```css
.block {}
.block__element {}
.block--modifier {}
```
之所以使用两个连字符和下划线而不是一个，是为了让 block 可以用单个连字符来界定，如：
```css
.site-search {} /* 块 */
.site-search__field {} /* 元素 */
.site-search--full {} /* 修饰符 */
```

## 举个栗子
- block__element：块里的元素，如：nav（block）里的 a 标签（element）；
- block__element--modifier：块里的元素的状态、属性或修饰，如：nav 里的 a 标签，有 active、hover、normal 3 种状态（modifier）。
```html
<nav class="nav">
  <a href="#" class="nav__item nav__item--active">当前状态</a>
  <a href="#" class="nav__item nav__item--hover">鼠标移上时的状态</a>
  <a href="#" class="nav__item nav__item--normal">正常状态</a>
</nav>
```
```scss
.nav {
  &__item {
    &--active {
    }
    &--hover {
    }
    &--normal {
    }
  }
}
```

## 命名空间
可以参考 BlazeUI 的命名规范：https://github.com/BlazeUI/blaze。
- o-：表示一个对象（Object），如 .o-layout。
- c-：表示一个组件（Component），指一个具体的、特定实现的 UI。如 .c-avatar。
- u-：表示一个通用工具（Utility），如 .u-hidden。
- t-：表示一个主题（Theme），如 .t-light。
- s-：表示一个上下文或作用域（Scope），如 .s-cms-content。
- is-，has-：表示一种状态或条件样式。如 .is-active
- _：表示一个 hack，如 ._important。
- js-：表示一个 JavaScript 钩子。如 .js-modal。
- qa-：表示测试钩子。

## 总结
- B（block）：某一块展示/功能区域，比如：.nav。
- E（element）：这块展示/功能区域里的某个元素，比如: .nav__item。
- M（modifier）：某个元素或者某个块的状态，比如：.nav--hide, .nav__item--active 等。

## 参考
- [BEM 命名规范](http://www.qianduan.org/post-458.html)
- [CSS命名方式=》BEM](https://github.com/zhongxia245/blog/issues/48)
- [BEM 快速入门](https://github.com/woai30231/webDevDetails/tree/master/15)
- [BEM Quick Start](https://en.bem.info/methodology/quick-start/)
- [和BEM的战斗：10个常见问题及如何避免](https://segmentfault.com/a/1190000006135647)
- [决战BEM, 10个常见问题及其解决方案](https://zhuanlan.zhihu.com/p/26407119?group_id=837593211068362752)
- [BEM实战分享](http://v.youku.com/v_show/id_XMjcwMzczNjkxNg==.html?spm=a2h3j.8428770.3416059.1)
- [Sensible CSS Guidelines for large scale projects](https://github.com/chris-pearce/css-guidelines)
- [BEM方法论](http://www.zcfy.cc/article/faq-methodology-bem-3145.html)
- [［翻译］更透明的 UI 代码和命名空间](http://zangbianxuegu.farbox.com/post/fan-yi-geng-tou-ming-de-ui-dai-ma-he-ming-ming-kong-jian)
