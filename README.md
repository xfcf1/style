###流程页面公用样式说明 Version 0.0.1

[Git下载地址，点我](http://git.elenet.me/xiaohao.dai/flow_style)
####此样式只规定了主要的布局，头部、侧边菜单及表单的基本样式，其余的可自行发挥。。。如果你用的是ReactJs框架可以直接import segment文件夹下面的jsx文件，后文是普通html运用方式。如果要demo，[可以点我](http://git.elenet.me/yi.liush/eFlow)不过是React的框架。普通html只需copy后面的代码即可。
-
####文件目录结构
#####css文件夹中style.css为你需要的文件
#####images文件夹中为需要的图片
#####segment文件夹中为React组件
-

######需要在页面上引入boostrap
```html
<a href="css/bootstrap.css" rel="stylesheet"/>
<a href="css/style.css" rel="stylesheet"/>
```
-
######头部的html代码
```html
<header>
    <div class="row">
        <div class="col-md-8">
            <div class="logo"><a to="index"><img src="images/act-logo.png"/></a></div>
            <nav>
                <a to="/index" class="active">首页</a>
                <a to="flow">流程首页</a>
                <a to="todo">EHR系统</a>
                <a href="#">费控系统</a>
                <a href="#">Javis系统</a>
            </nav>
        </div>
        <div class="col-md-4 text-right">
            <span>您好，夏夏夏！</span>
            <span class="logout">退出</span>
        </div>
    </div>
</header>
```
######nav中高亮颜色即选中颜色的样式名是 ```active```
-
######左边多级菜单代码
```html
<aside>
    <ul class="parent">
        <h3>管理流程</h3>
        <li class="parent">
            <a class="active" ><p class="parent ico tome-flow">我审批的流程</p></a>
        </li>
        <li class="parent">
            <a><p class="parent ico my-flow">我发起的流程</p></a>
        </li>
        <li class="parent">
            <a><p class="parent ico ccme-flow">转发给我的流程</p></a>
        </li>
        <li class="parent">
            <p class="parent ico watch-flow">流程监控</p>
        </li>
        <h3>流程创建</h3>
        <li class="parent">
            <p class="parent ico human">人事类流程<i></i></p>
            <ul>
                <li>
                    <a>离职申请</a>
                </li>
                <li>
                    <a>签卡申请</a>
                </li>
                <li>
                    <a>组织架构变更</a>
                </li>
                <li>
                    <a>调动申请</a>
                </li>
                <li>
                    <a>违规行为处罚</a>
                </li>
            </ul>
        </li>
        <li class="parent">
            <p class="parent ico bird">蜂鸟业务流程</p>
        </li>
        <li class="parent">
            <p class="parent ico admin">行政类流程<i></i></p>
            <ul>
                <li>
                    <a>合同审批</a>
                </li>
                <li>
                    <a>名片印制</a>
                </li>
                <li>
                    <a>快递寄件申请</a>
                </li>
                <li>
                    <a>用章申请</a>
                </li>
                <li>
                    <a>费用支出报备</a>
                </li>
                <li>
                    <a>通知发布申请</a>
                </li>
            </ul>
        </li>
        <li class="parent">
            <p class="parent ico design">设计类流程</p>
        </li>
        <li class="parent">
            <p class="parent ico sia">SIA业务流程</p>
        </li>
        <li class="parent">
            <p class="parent ico actives">活动类流程</p>
        </li>
        <li class="parent">
            <p class="parent ico skill">技术类流程</p>
        </li>
    </ul>
</aside>
```
######总共两级目录ul li 嵌套：一级目录用```parent```二级目录用放在```<li class="parent"></li>```内，
```<p class="parent ico admin">行政类流程<i></i></p>```带parent的```p```标签为一级目录名，其中的```i```标签是箭头

-
######tabel样例 主要class是```tableArea ```
```html
<section class="tableArea">
    <table>
        <colgroup>
            <col/>
            <col/>
            <col/>
            <col/>
            <col/>
            <col/>
            <col/>
            <col/>
        </colgroup>
        <thead>
            <tr>
                <th><input type="checkbox"/></th>
                <th>姓名</th>
                <th>常驻地</th>
                <th>职位等级</th>
                <th>媒体类型</th>
                <th>维护人</th>
                <th>维护级别</th>
                <th>操作</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><input type="checkbox"/></td>
                <td>Test</td>
                <td>北京</td>
                <td>4</td>
                <td>综合</td>
                <td>李欢</td>
                <td>A</td>
                <td>
                    <span>修改</span>
                    <span>查看</span>
                </td>
            </tr>
        </tbody>
    </table>
</section>
```
-
######翻页样例 主要class```paging```
```html

<div class="paging">
    <div class ="item">
        <span>条目总数：0</span>
        <span>选中条目：0</span>
    </div>
    <div class ="page">
        <span>每页显示数：<input type="text" value="10"/></span>
        <a>首页</a>
        <a>上一页</a>
        <span>第<input type="text" value="1"/>页</span>
        <span>共1页</span>
        <a>下一页</a>
        <a>尾页</a>
    </div>
</div>
```

-
######遮罩样例
```html
<div className="pop">
    <div className="title">
        <h4>新建媒体文件</h4>
        <i className="close">X</i>
    </div>
    <div className="pop-cont">
        <section>
        	...内容
        </section>
    </div>
</div>
<div className="shadow"></div>
```
-
######主内容用标签```article```包住即可，块可以用```section```，```a```，```input```，```select```的样式已初始化，其余的自行按需发挥。。。

有问题请联系 ```xiaohao.dai@ele.me```