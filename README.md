# vue-shop

## 加载首页轮播图数据
1. 获取数据, 使用vue-resource
2. 使用vue-resource 的 this.$http.get 获取数据
3. 获取到的数据,要保存到data身上
4. 使用v-for 循环渲染每个item 项

## 改造九宫格区域的样式

## 改造新闻资讯路由连接
1. 配置全局根路径


## 新闻资讯 页面 制作
1. 绘制界面
2. 使用vue-resource 获取数据
3. 渲染真是数据


## 新增全局日期过滤器
1. Vue.filter('dateFormat',function(dateStr,pattern='YYYY-MM-DD HH:mm:ss'){})


## 新增新闻详情页面
1. 根据路由参数获取id值
2. 根据ajax渲染数据

## 新增新闻评论控件
1. 根据ajax渲染数据
2. 通过双向绑定保存评论内容

## 绘制图片列表 组件结构并美化样式
1. 制作顶部的滑动条
2. 制作底部的图片列表
3. 滑动条无法触发滑动，通过文档，需要初始化组件
 + 导入mui.js
 + 调用官方提供的方法初始化
 ```
    mui('.mui-scroll-wrapper').scroll({
            deceleration: 0.0005 //flick 减速系数，系数越大，滚动速度越慢，滚动距离越小，默认值0.0006
        });
 ```
4. 初始化mui时候出现了错误 导入mui.js的时候由于严格模式导致的
 + 移除严格模式,正在.babelrc 中添加如下代码，让项目忽略第三方js的转码
 ```
 "plugins": ["transform-vue-jsx", "transform-runtime",["component", [
    {
      "libraryName": "mint-ui",
      "style": true
    }
  ]],"transform-remove-strict-mode",],
  "ignore": ["./src/lib/mui/js/*.js"]
 ```
5. 当滑动条调试ok后，发现，tabber无法正常工作了，在这时候我们需要把每个tabbar按钮的样式中 `mui-tab-itm` 重新改一下名字;
6. 获取图片全部分类，并渲染

### 制作图片区域列表
1. 图片列表需要使用懒加载技术，使用mint-ui的lazyLoad
2. 根据`lazy-load`的使用文档，尝试使用
3. 渲染图片列表

### 实现了图片列表的 懒加载改造 样式美化
1. 在改造li 成 router-link 的时候，需要使用tag标签指定成渲染那种元素

### 实现详情页面的布局和美化，同时获取数据渲染页面


### 实现图片详情的缩略图的功能
1. 使用插件 vue2-preview 这个缩略图插件
2. 获取所有的图片列表，然后使用v-for 指令渲染
3. 这里点击事件有问题