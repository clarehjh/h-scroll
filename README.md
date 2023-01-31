# h-scroll

# 目的

hjh-scroll 是为了解决移动端获取设备滚动距离，是否滚动到底部提示并刷新新数据的工具函数

# 安装

```js
yarn add hjh-scroll

```

# 基础使用

```js
import { useScroll } from "hjh-scroll";
const { isReachBottom, clientHeight, scrollTop, scrollHeight } = useScroll();
```

# tab 标签点击滑动到指定位置

```html
<div class="detail top-page" ref="contentRef">
  <tab-control
    v-if="showTabControl"
    class="tabs"
    :titles="names"
    @tabItemClick="tabClick"
  />
</div>
```

```js
// tabControl相关的操作
const contentRef = ref();
const { scrollTop } = useScroll(contentRef);

//指定位置显示tabControl
const showTabControl = computed(() => {
  return scrollTop.value >= 300;
});

//滚动到指定距离
contentRef.value.scrollTo({
  top: xxxx,
  behavior: "smooth",
});
```
