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

## 总结
- B（block）：某一块展示/功能区域，比如：.nav。
- E（element）：这块展示/功能区域里的某个元素，比如: .nav__item。
- M（modifier）：某个元素或者某个块的状态，比如：.nav--hide, .nav__item--active 等。

## 参考
- [BEM 命名规范](http://www.qianduan.org/post-458.html)
- [CSS命名方式=》BEM](https://github.com/zhongxia245/blog/issues/48)
- [BEM Quick Start](https://en.bem.info/methodology/quick-start/)
