## 简介
BEM的意思就是块（block）、元素（element）、修饰符（modifier）,是由Yandex团队提出的一种前端命名方法论。这种巧妙的命名方法让你的CSS类对其他开发者来说更加透明而且更有意义。BEM命名约定更加严格，而且包含更多的信息，它们用于一个团队开发一个耗时的大项目。
> 重要的是要注意，我使用的基于BEM的命名方式是经过Nicolas Gallagher修改过的。

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

## 总结
- B（block）：某一块展示/功能区域，比如：.nav。
- E（element）：这块展示/功能区域里的某个元素，比如: .nav__item。
- M（modifier）：某个元素或者某个块的状态，比如：.nav--hide, .nav__item--open 等。

## 举个栗子
HTML：
```html
<nav class="nav">
  <a href="#" class="nav__item nav__item--active">当前</a>
  <a href="#" class="nav__item nav__item--hover">鼠标移上</a>
  <a href="#" class="nav__item nav__item--normal">正常状态</a>
</nav>
```
SASS：
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