# 记录好的用户体验

### 做前端也有一段时间了，对于实现各种需求来说已经是游刃有余了，代码的质量和可扩展性都能把控。目前最缺乏的就是所谓的用户体验。


#### 用户体验说起来是一个比较模糊的概念，但是又是实实在在地决定着用户用起来爽不爽。

1. 典型的中后台应用，大多数是对表格的增删改查，有如下改进
* 头部添加菜单解释说明，一个菜单标题只有简简单单的几个字，用户一开始用起来可能都不知道该菜单是干说明用的，增加的解释说明能很好的帮用户了解该页面功能

* 操作按钮的归类，之前一般将增加，删除，修改，导出表格，搜索，搜索条件等都放在一块，这样给人一种很杂乱的感觉，现在将这些控件分为两类（`搜索条件和搜索按钮`，`增删导出刷新等操作按钮`）。其中 `增删导出刷新等操作按钮` 放到头部菜单里，和下面的 `搜索条件和搜索按钮` 区分开来。

* 对于复杂的搜索条件，划分为基础查询条件和全部查询条件，基础查询条件涵盖用户常用的几个搜索条件，其余高级搜索条件先隐藏，通过 `显示全部` 按钮显示全部搜索条件。这样体验具有层次感，而且用户不会因为一大堆条件输入框而感到厌烦。

* 对于表格，如果查询数据为空，则显示 `暂无数据`； 如果是后台报错，则显示 `网络异常，请点击按钮刷新`，之前都是通过提示框显示接口报错等。这样的好处有两点，一是如果用户想尝试重新获取数据不用再点刷新整个页面了，二是提示框会打断用户聚焦的视线，对于用户来说是不好的体验。  
当表格的列数很多时，操作一栏要固定住，方便用户操作。

* 左侧菜单树，当菜单过多时，增加搜索框，可以快速定位到该菜单页面，方便用户操作。

* 避免全部页面loading，只用局部loading。


2. 大数据项目的一些用户体验优化的点
* 指标卡片 加问号图标，用tooltip显示指标的含义；包括页面上一些文案，如果含义难懂的都可以加tooltip
* 可点击的元素鼠标变成手型
* 前端缓存优化（用户点击过的图标数据缓存起来）
* 表单要尽可能简单，负责的表单会让用户失去耐心
* 下拉框如果选项比较少，可以直接用radio来代替，用户可以省一步点击下拉框的操作
* 查询图表的时候需要填时间区间，可以放一些常见的时间区间给用户选择，比如`今天/昨天/上周/上月/前三月`, 避免用户去手动选择两个时间框

3. 通用
* 当前用户登录后被其他用户挤下线，选择用全屏提示框+确定按钮提示用户。此类通知属于一级重要，必须确保用户知道该重要通知，确定按钮是为了强行让用户浏览该重要通知的。  
产品提出自动跳转到登录页面，用一行小字提示，让用户看到该重要通知的可能性大大降低。实在不妥。
* 前面说 的table 显示三种状态：有数据/无数据（no data）/网络异常，点击刷新，这三种其实适用于很多的展示数据的组件，比如图表组件
* 
---
to be continued!