# 信保插件技术接入指南
## 接入概述
接入信保插件,开发者需要按照以下步骤完成:
  1. 获取data-token
  2. 在页面中引入插件脚本
  3. 在页面相应功能DOM中插入className    

下面详细介绍这3个步骤

## 1. 获取data-token
`data-token`是卖家身份的凭据,需要卖家登陆i.alibaba.com,才能获取.
1. 卖家登陆i.alibaba.com, 在页面中部有如下区域,点击获取代码.
![](1.png)
1. 点击获取代码后,有一个如下弹窗,我们只需要文本框中这段代码.
![](2.png)
1. 得到代码后,在这个`script`标签中,有一个`data-token`属性,该属性的值即为`data-token`.(注意:我们只需要得到`data-token`,该段script标签代码为老代码,跟我们本次信保插件没有关系,下面会重新给出新脚本)

## 2. 在页面中引入插件脚本
下面的脚本支持IE8+
1. 如下为脚本模板,首先需要你填入前面获取到的属性`data-token`.
```javascript
  <script id="ali-ta-plugin-loader"  
  src="//i.alicdn.com/sc-trade-ma/ta-plugin/dist/ta-plugin-loader.js"
  type="text/javascript"
  data-token=""></script>
```
1. 把填入完毕的`script`插入到`html`文档中.脚本会在`html`文档加载完毕后才执行,所以你可以把`script`插入到`head`节点或者`body`节点中.

## 3. 在页面相应功能DOM中插入className
信保插件提供了4个className,把这4个className加入到相应`DOM`的属性`class`中,实现不同业务效果.

1. `class="ali-ta-plugin-popup-trigger"`,该class会hover出如下效果.
```javascript
  <div class="ali-ta-plugin-popup-trigger"
  style="height:100px;background-color:#aaa"></div>
```
![](3.png)
1. `class="ali-ta-plugin-draft-order-trigger"`,该class监听点击事件,点击会跳转到起草信保订单页面.
```javascript
  <a class="ali-ta-plugin-draft-order-trigger"
   href="javascript:void(0)" target="_blank">打开新窗口,起草信保订单</a>
```
1. `class="ali-ta-plugin-credit-trigger"`,该class监听点击事件,点击会跳转到卖家信保信息页面.
```javascript
  <a class="ali-ta-plugin-credit-trigger"
   href="javascript:void(0)" target="_blank">打开新窗口,卖家信保信息</a>
```
1. `class="ali-ta-plugin-ta-trigger"`,该class监听点击事件,点击会跳转到信保业务介绍页面.
```javascript
  <a class="ali-ta-plugin-ta-trigger"
   href="javascript:void(0)" target="_blank">打开新窗口,信保业务介绍</a>
```

## 4. Q&A
如果你在开发中遇到问题,可以使用钉钉扫描下面的二维码获取技术支持.
![](4.png)
