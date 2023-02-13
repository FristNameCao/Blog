---
cover: https://fristnamecao.github.io/img/imgs/0_5.jpg
title: flex布局
date: 2023-02-11 23:34:43
tags: "flex"
categories: flex

---

# flex:

大号的行内布局

### 外层元素: flex container flex 容器

flex 窗口的子元素: flex item flex 元素

- flex-wrap:wrap 折行
- flex-grow:0; /_ 扩张权重_/宽度的权重 默认为 0
- flex-grow:0.x; /_按照百分比获取剩余空间_/ 所有求和不超过 100%也就是 1 生效
- flex-shrink:; /_收缩系数_/ 默认 1
- - 不是 flex item 的 flex 父元素从外面看就像块元素一样
    如宽度会打满包含块
    但是子元素的 margin 不会超出去
    但是相邻的元素垂直方向的 margin 还是会合并的

  - 收缩或者扩张都不会让元素超出自己 min-w/h 以及 max-w/h 设定 的尺寸
    收缩不能收到比自己的 min-width 还小
    扩张不能扩张到比自己的 max-width 还大
    收缩只发生在不折行的时候
    因为如果折行就不可能存在空间不够的情况
    flex 父元素"垂直"方向上的额外空间,只会均等的分配给每一行
    当高度固定了如果还有额外空间用 height:auto;会自动分配填满

  ### flex 父元素用来调用子元素摆放属性 justify-content

      * justify-content
        设定一"行"的元素在行中的"水平"分布
       start 项目与容器的左侧对齐。
       end 项目与容器的右侧对齐
       center 项目在容器的中心对齐
       space-between 项目以相等的间距显示。
       space-around 项目以等间距显示
       space-evenly 平均分配物品

  项目在它们周围有相等的空间

##### align-items

设定一"行"的元素在行中的"垂直"分布
start 项目与容器顶部对齐

end 项目与容器底部对齐

center 项目在容器的垂直中心对

baseline 项目显示在容器的基线处

stretch 物品被拉伸以适合容器

- ## align-content

  ​ 设定所有行("行们")在父元素垂直方向的分布
  (设置父元素垂直方向上额外空间的分配)

       start 	flex-start: 线装在容器的顶部
       end 	flex-end: 线装在容器的底部
       center 	center: 线在容器的垂直中心包装
       space-between	：行以相等的间距显示 两边对齐
        
       space-around 	 行以相等的间距显示在它们周围
       space-evenly		平均分配物品
        
       项目在它们周围有相等的空间
        
       stretch(额外空间均分给每一行)：线条被拉伸以适合容器
        
       flex父元素"垂直"方向上的额外空间,只会均等的分配给每一行
       * 不是flex item的flex父元素从外面看就像块元素一样如宽度会打满包含块
        
       但是子元素的margin不会超出去
        
       但是相邻的元素垂直方向的margin还是合并的

### flex 子元素用来调整自身摆放属性

       align-self 类似align-items,但是只调整自己
    
       order 调整自己的显示顺序(不是层叠顺序)
    
       flex子元素不用定位就可以使用z-index属性
    
      flex: 在一个属性上直接设置flex子元素的flex-grow flex-shrink flex-basis

- flex: auto;

      flex-grow: 1;
      flex-shrink: 1;
      flex-basis: auto;

- flex: 1;

      flex-grow: 1;
      flex-shrink: 1;
      flex-basis: 0%;

- flex: 0;

      flex-grow: 0;
      flex-shrink: 1;
      flex-basis: 0%;

- flex: 100px;

      flex-grow: 1;
      flex-shrink: 1;
      flex-basis: 100px;

- - flex-basis: 设定元素在主轴方向上的初始尺寸
    当主轴水平时，它相当于 width

    当主轴垂直时，它相当于 height

    当它与 width/height 一起用的时候，如果 flex-basis 的
    值不为 auto，则它更优先

### flex 父元素的轴向:flex-direction

    flex-direction: 设定主轴方向
    row 向右 项目的放置与文本方向相同
    row-reverse 向左 项目放置在与文本方向相反的位置
    column 向下 项目从上到下放置
    column-reverse 向上  项目从下到上放置

### flex-wrap 设定交叉轴方向,交叉轴肯定跟主轴是垂直的

wrap 垂直与主轴,向右或向下

- 项目环绕到其他行 ，类似于折行

-

- wrap-reverse 垂直与主轴,向左或向上

- 项目反向环绕到附加行。

- nowrap 每个项目都适合一行

- 不设定交叉轴方向,即不折行,所有元素在同一行或同一列

-

- flex-flow 在一个属性上直接设置 flex-direction 和
  flex-wrap 换行

  flex-flow: wrap column; 换行 向下 项目从上到下放置

  flex-grow 设定主轴方向上额外空间的分配
  flex-shrink 设定主轴方向上空间收缩的系数

  ## flex-flow 弹性容器

  \*_ /_ flex-flow: <'flex-direction'> \*/

  flex-flow: row; 向右 项目的放置与文本方向相同

  flex-flow: row-reverse; 向左 项目放置在与文本方向相反的位置

  flex-flow: column; 向下 项目从上到下放置

  flex-flow: column-reverse; 设置反转

  /_ flex-flow: <'flex-wrap'> _/

  flex-flow: nowrap;

  flex-flow: wrap; 换行

  flex-flow: wrap-reverse;

  /_ flex-flow: <'flex-direction'> and <'flex-wrap'> _/

  flex-flow: row nowrap;

  flex-flow: column wrap;

  flex-flow: column-reverse wrap-reverse;

  /_ Global values _/

  flex-flow: inherit;

  flex-flow: initial;

  flex-flow: revert;

  flex-flow: revert-layer;

  flex-flow: unset;

  ​

#### flex 父元素中的匿名文本

    flex父元素中的匿名文本相当于将该文本包进一个标签但不给该标签设置任何属性
    
    但它会受到flex父元素 justify-content, align-items, align-content属性的影响
    
    flex子元素的的margin：auto会均等的分配额外的空间，但晚于flex-grow对空间的占用

## gap

    设置在flex父元素用于指定子元素之间的间隙
    gap: <row-gap> <column-gap>;
    row-gap:
    column-gap:
     行内flex元素,外面看是行内,里面看是flex
    display: inline-flex
    
     定位flex元素,外面看是定位,里面看是flex
    display: flex;
    position: absolute;
    
    浮动flex元素,外面看是浮动,里面看是flex
    display: flex;
    float: left;







![flex](D:\Blog\source\_posts\flex.jpg)