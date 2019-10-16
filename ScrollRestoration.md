#### Histroy API: ScrollRestoration

 浏览器的滚动记录功能，在刷新页面时，能继续停留在刷新前的位置，以方便用户操作。

 但是某些情况下，我们需要手动定位滚动条位置，这个功能就显得不是那么适用了，通过设置 history的scrollRestoration方法可以进行设置处理。

 ScrollRestoration有两个值 ： `auto` 和 `manual`
    + auto: 从跳转到的页面回到跳转页面，页面上的竖屏和横屏滚动效果会被保留，即记录了之前的滚动到的位置。
    + manual: 滚动记录效果被重置。

如果浏览器支持 `history.scrollRestoration`并且值为auto则会默认恢复滚动行为。如果设置manual则可以取消，这个行为不用去考虑兼容性的问题，如果有这个功能才会有回复滚动，所以直接判断一下就可以了。
```js
window.history.scrollRestoration && (window.history.scrollRestoration = 'auto');
```