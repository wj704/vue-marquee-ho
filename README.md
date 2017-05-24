# vue-marquee

> A Vue component to marquee

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```
## 使用组件
通过`npm install vue-marquee-ho -s` 安装到相应的项目下，安装成功如下图所示：

![如图][10]

到项目中的node_modules/目录下将可以看到：

![如图][11]

需要用到该组件时可以这样引入

```
import VueMarquee from 'vue-marquee-ho';
import Css from 'vue-marquee-ho/dist/vue-marquee.min.css'
export default {
  name: 'app',
  components:{
      "vue-marquee": VueMarquee
    },
}
```
看一个demo:

```
<template>
  <div id="app">
    <div class="marquee-wrap" style="width: 100px;"><vue-marquee content="33333" class="two"  :showtwo="false"></vue-marquee></div>
    <div class="marquee-wrap" style="width: 100px;"><vue-marquee content="22222" class="two"  :showtwo="false"></vue-marquee></div>
    <div class="marquee-wrap" style="width: 100px;"><vue-marquee content="1" class="two"  :showtwo="false"></vue-marquee></div>
    <router-view></router-view>
  </div>
</template>

<script>
import VueMarquee from 'vue-marquee-ho';
import Css from 'vue-marquee-ho/dist/vue-marquee.min.css'
export default {
  name: 'app',
  components:{
      "vue-marquee": VueMarquee
    },
}
</script>
```
效果：

![如图][12]

  [10]: http://images.cnblogs.com/cnblogs_com/wj204/871432/o_8.png 
  [11]: http://images.cnblogs.com/cnblogs_com/wj204/871432/o_9.png
  [12]: http://images.cnblogs.com/cnblogs_com/wj204/871432/o_11.gif

For detailed explanation on how things work, checkout the [guide](http://www.cnblogs.com/wj204/p/6868375.html) 
构建过程，见 [guide](http://www.cnblogs.com/wj204/p/6868375.html) 
