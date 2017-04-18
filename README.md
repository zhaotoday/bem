## 简介
BEM的意思就是块（block）、元素（element）、修饰符（modifier）,是由Yandex团队提出的一种前端命名方法论。这种巧妙的命名方法让你的CSS类对其他开发者来说更加透明而且更有意义。BEM命名约定更加严格，而且包含更多的信息，它们用于一个团队开发一个耗时的大项目。
> 重要的是要注意，这里使用的基于BEM的命名方式是经过Nicolas Gallagher修改过的。

## 命名约定
```css
.block {}
.block__element {}
.block--modifier {}
```
- .block 代表了更高级别的抽象或组件。
- .block__element 代表.block的后代，用于形成一个完整的.block的整体。
- .block--modifier代表.block的不同状态或不同版本。
> 之所以使用两个连字符和下划线而不是一个，是为了让 block 可以用单个连字符来界定，如：
```css
.site-search {} /* 块 */
.site-search__field {} /* 元素 */
.site-search--full {} /* 修饰符 */
```

## 举个栗子
- block__element：block 里的元素，如：nav（block）里的 a 标签（element）；
- block__element--modifier：block 里的元素的状态、属性或修饰，如：nav 里的 a 标签，有 active、hover、normal 3 种状态（modifier）。
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