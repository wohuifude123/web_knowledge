结构、样式、行为分离
尽量确保文档和模板只包含 HTML 结构，样式都放到样式表里，行为都放到脚本里。

缩进
统一四个空格缩进（总之缩进统一即可），不要使用 Tab 或者 Tab、空格混搭。

文件编码
使用不带 BOM 的UTF-8编码。

在 HTML中指定编码<meta charset="UTF-8"> ；

无需使用 @charset 指定样式表的编码，它默认为 UTF-8 （参考 @charset）；

样式文件一律使用小写字母

省略外链资源URL协议部分
省略外链资源（图片及其它媒体资源）URL 中的 http / https 协议，使 URL 成为相对地址，避免Mixed Content 问题，减小文件字节数。

其它协议（ftp 等）的 URL 不省略。



目录结构


├── build 构建脚本目录
│ ├── build.js 生产环境构建脚本
│ ├── check-versions.js
│ ├── utils.js 构建相关工具方法
│ ├── vue-loader.conf.js
│ ├── webpack.base.conf.js webpack基础配置
│ ├── webpack.dev.conf.js webpack开发环境配置
│ └── webpack.prod.conf.js webpack生产环境配置
├── config 配置相关
│ ├── index.js
│ ├── dev.env.js 开发环境变量
│ ├── prod.env.js 生产环境变量
│ └── test.env.js
├── src
│ ├── components // 全局UI组件
│ ├── pages // 入口 加载组件 初始化等
│ │ └── home //图表组件
│ │ ├── assets 资源文件
│ │ ├── modules 存放不同页面
│ │ ├── router // 路由
│ │ ├── main.js // 入口 加载组件 初始化等
│ │ ├── App.vue // 入口页面
│ │ ├── index.html // html打包所用模板
│ ├── store // 全局store管理
│ ├── utils // 全局公用方法
├── lib // 第三方资源
├── .babelrc // babel-loader 配置
├── eslintrc.js // eslint 配置项
├── .gitignore // git 忽略项
└── package.json // package.json




项目命名
全部采用小写方式， 以下划线分隔。

示例：my_project_name

目录命名
参照项目命名规则；有复数结构时，要采用复数命名法。

示例：scripts, styles, images, data_models



scripts	js文件目录
styles	样式文件目录
images	图片文件目录
data_models	数据文件目录


文件夹命名


 admin	后台管理
app	应用
article	资讯
aboutus	关于我们
common	公共
config	配置
contactus	联系我们
data	数据
en-us	英文
extend	延伸
feedback	信息反馈
history	发展历史
leavewords	留言
install	安装
lang	语言包
lib	库
mall	商城
newslist	新闻列表
newsdetail	新闻详细页面
picture	组图
product	商品
prolist	产品列表
prodetail	产品详细页面
search	搜索
section	区块
shop	商店
static	静态
system	系统
templates	模版
ucenter	用户中心
upload	上传
video	视频
vote	投票
zh-tw	繁体中文
zh-cn	简体中文
CSS样式文件命名

global.css	全局样式
layout.css	布局结构
base.css	基本共用
style.css	综合样式
master.css	主要的
module.css	模块
forms.css	表单
themes.css	主题/网页换肤
font.css	字体
print.css	打印
mend.css	
补丁


私有样式/独立页面，根据实际情况，可以自定义命名 CSS 文件。

以上这些常用的文件命名，无需全部使用，根据实际情况，每个页面引用不超过 3 个 CSS 文件。

CSS命名
命名规则
class 必须单词全字母小写，每个单词间以 - 分隔，分隔符之间有且仅有一个单词。
class 必须代表相应模块或部件的内容或功能，不得以样式信息进行命名。

命名示例
.div1{} /* 不推荐；无意义 */
.a_green{} /* 不推荐；无意义 */
.menu{} /* 推荐；特殊性*/
.header{} /* 推荐；通用性*/

网页公共命名
#wrapper	页面外围控制整体布局宽度
#container或#content	容器，用于最外层
#layout	布局


命名精简
id和class命名越精简越好，只要足够表达意思，这样有助于理解，同时也能提高代码效率

.navigation{} /* 不推荐 */
.login_box_inside_con{} /* 不推荐 */
.nav{} /* 推荐 */

命名嵌套问题
书写css要注意先后顺序和嵌套问题，从性能上考虑尽量减少选择器的层级

.nav ul.list{} /* 不推荐 */
.nav .list{} /* 推荐 */

注意事项
命名中尽量避免使用中文拼音，应该采用更简明有语义的英文单词进行组合
命名注意缩写，但是不能盲目缩写
不允许通过1、2、3等序号进行命名
避免class与id重名
id注意用于标识模块或页面的某一个父容器区域，名称必须唯一，不要随意新建id
class用于标识某一个类型的对象，命名必须言简意赅
尽可能提高代码模块的复用，样式尽量用组合的方式
规则名称中不应该包含颜色、定位等与具体显示效果相关的信息，应该用意义命名，而不是结果名称

其他规范
        不要轻易改动全站级CSS和通用CSS库，改动后，要经过全面测试
        避免使用filter
        避免在CSS中使用expression
        避免过小的背景图片平铺
        尽量不要在CSS中使用!important
        绝对不要在CSS中使用"*"选择符
        层级(z-index)必须清晰明确，页面弹窗、气泡为最高级(最高级为999)，不同弹窗气泡之间可在三位数之间调整，普通区块为10-90内10的倍数；区块展开、弹出为当前父层级上个位增加，禁止层级间盲目攀比
        背景图片在情况允许，尽可能使用sprite技术，减小http请求，考虑到多人协作开发，sprite按照模块、业务、页面来划分
        页面内部尽量避免使用style属性，CSS放在head标签中，由link标签引入，使页面的结构与表现分离
        尽量减少使用float、position等影响性能的属性，这样可以避免新手在布局时出现的混乱
        尽量少使用<br />来断行
        不要连续出现多个 (空格)，也尽量少使用全角空格（英文字符集下，全角空格会变成乱码），空白应该尽量使用text-indent、maring/padding等方法来实现
        排版如果遇到需要首行缩进的处理，可以使用text-indent:2em;
        图片如果需要加载就在页面上用img标签写出，并指明宽高，重要的图片必须加上alt属性，给重要的元素和截断的元素上加上title
        如果有跳转的地方，统一使用a标签，<a href="#"></a>，需要跳转到新页面，则还需要加上targent="_blank"属性，如果点击的是空链接(#)，则会自动将当前页面重置到首端，可以使用"javascript:void()"来替代原来的"#"
        分清楚什么情况下jpg/gif/png图片

JavaScript命名
变量
命名方式：小驼峰
命名规范：前缀应当是名词，找不到合适的名词可以根据情况使用形容词（函数的名字前缀为动词，以此区分变量和函数）
命名建议：语义化，尽量在变量名字中体现所属类型，如:length、count等表示数字类型；而包含name、title表示为字符串类型。

函数
命名方法：小驼峰式命名法。
命名规范：前缀应当为动词。
命名建议：使用常见动词约定。



can	
判断是否可执行某个动作（权限）

函数返回一个布尔值。

true：可执行；

false：不可执行

has	
判断是否含有某个值

函数返回一个布尔值。

true：含有此值；

false：不含有此值

is	
判断是否为某个值 

函数返回一个布尔值。

true：为某个值；

false：不为某个值

get	获取某个值	函数返回一个非布尔值
set	设置某个值	无返回值、返回是否设置成功或者返回链式对象
load	 加载某些数据  	


// 是否可阅读

function canRead() {

    return true;

}



// 获取名称

function getName() {

    return this.name;

}

目录命名
参照项目命名规则；
有复数结构时，要采用复数命名法。
例：scripts，styles，images，data_models

每个页面的资源文件都在该页面对应的目录的assets文件夹内

A.基本原则

符合web标准（UTF-8，HTML5），语义化html（HTML5新增要求，减少div和span等无特定语义的标签使用），结构表现行为分离（HTML-CSS-JS代码分离，不同行为代码高内聚低耦合），兼容性优良（早期版本浏览器兼容，移动端和PC端设备兼容）.页面性能方面（减少请求次数，例如使用精灵图和sass语法），代码要求简洁明了有序，尽可能的减小服务器负载，保证最快的解析速度（减小repaint和reflow）.

B.文件命名规范

1、html，css，js，lib，images文件均存放至项目的目录中。如果使用相关前端框架，根据框架的文件格式进行合理布局。

2、所有文件夹及文件使用英文命名（避免使用中文路径）。

3、html文件：入口文件使用index.html。如果有对应的设计组设计原稿，需要将对应的设计稿和html文件命名一致并合理存放。

4、css文件命名：后缀.css。通用initial.css，初始化base.css，首页index.css，其他页面按照对应的html命名。

5、Js文件命名：英文命名，后缀.js.通用common.js，初始化base.js。 其他页面按照对应的html命名。

C.HTML规范


1、文档类型声明及编码：统一为html5声明类型。书写时利用IDE实现层次分明的缩进（默认缩进4空格）。

2、非特殊情况下CSS文件放在body部分<meta>标签后。非特殊情况下大部分JS文件放在<body>标签尾部（如果需要界面未加载前执行的代码可以放在head标签后）避免行内JS和CSS代码。

3、所有编码需要遵循html（XML）标准，标签&属性&属性命名必须由小写字母及下划线数字组成，且所有标签必须闭合，包括br()，hr()等。属性值用双引号。

4、引入JS库文件，文件名须包含库名称及版本号及是否为压缩版，比如jquery-1.4.1.min.js。引入插件，文件名格式为库名称+插件名称，比如jQuery.bootstrap.js。

5、书写页面过程中，请考虑向后扩展性。class&id参见css书写规范.

6、需要为html元素添加自定义属性的时候，首先要考虑下有没有默认的已有的合适标签去设置，如果没有，可以使用须以"data-"为前缀来添加自定义属性，避免使用"data："等其他命名方式。

7、语义化html，如标题根据重要性用h*(同一页面只能有一个h1)，段落标记用p，列表用ul，内联元素中不可嵌套块级元素。

8、尽可能减少div多层级嵌套。

9、书写链接地址时，必须避免重定向，例如：href="http：//myVue.com/"，即须在URL地址后面加上“/”；

10、在页面中尽量避免使用style属性，即style="…"。

11、必须为含有描述性表单元素(input，textarea)添加label，如姓名：须写成：姓名：

12、能以背景形式呈现的图片，尽量写入css样式中。

13、重要图片必须加上alt属性。给重要的元素和截断的元素加上title。

14、给区块代码及重要功能(比如循环)加上注释，方便后台添加功能。

15、特殊符号使用：尽可能使用代码替代：比如<(<)&>(>)&空格()&»(»)等等。

D.CSS规范


1、编码规范为utf-8。

2、协作开发及分工：i会根据各个模块，同时根据页面相似程序，事先写**体框架文件，分配给前端人员实现内部结构&表现&行为。共用css文件base.css由i书写，协作开发过程中，每个页面请务必都要引入，此文件包含reset及头部底部样式，此文件不可随意修改。

3、class与id的使用：id是唯一的并是父级的，class是可以重复的并是子级的，所以id仅使用在大的模块上，class可用在重复使用率高及子级中。id原则上都是由我分发框架文件时命名的，为JS预留钩子的除外。

4、为JS预留钩子的命名，请以js_起始，比如：js_hide，js_show。

5、class与id命名：大的框架命名比如header/footer/wrapper/left/right之类的在2中由i统一命名.其他样式名称由小写英文&数字&来组合命名，如i_comment，fontred，width200。避免使用中文拼音，尽量使用简易的单词组合。总之，命名要语义化，简明化

6、规避class与id命名(此条重要，若有不明白请及时与i沟通)：a）通过从属写法规避，示例见d。b）取父级元素id/class命名部分命名，示例见d。c）重复使用率高的命名，请以自己代号加下划线起始，比如i_clear。d）a，b两条，适用于在2中已建好框架的页面，如，要在2中已建好框架的页面代码中加入新的div元素，按a命名法则：...，样式写法：#mainnav.firstnav{.......}按b命名法则：...，样式写法：.main_firstnav{.......}

7、css属性书写顺序，建议遵循：布局定位属性-->自身属性-->文本属性-->其他属性.此条可根据自身习惯书写，但尽量保证同类属性写在一起.属性列举：布局定位属性主要包括：display&list-style&position（相应的top，right，bottom，left）＆float&clear＆visibility＆overflow；

自身属性主要包括：width&height&margin&padding&border&background。

文本属性主要包括：color&font&text-decoration&text-align&vertical-align&white-space&

其他&content。

8、书写代码前，提高样式重复使用率。

9、充分利用html自身属性及样式继承原理减少代码量，例如：

即可实现日期居右显示


ul.list li {
position：relative
}
ul .list li span {
position：absolute；right：0
}
10、样式表中中文字体名，请务必转码成unicode码，以避免编码错误时乱码。

11、背景图片请尽可能使用精灵图技术，减小http请求，考虑到多人协作开发，精灵图按模块制作。

12、使用table标签时(尽量避免使用table标签)，请不要用width/height/cellspacing/cellpadding等table属性直接定义表现，应尽可能的利用table自身私有属性分离结构与表现，如thead，tr，th，td，tbody，tfoot，colgroup，scope。(cellspaing及cellpadding的css控制方法：table{border：0。margin：0。border-collapse：collapse。}tableth，tabletd{padding：0。}，base.css文件中我会初始化表格样式)

13、杜绝使用兼容ie8。

14、用png图片做图片时，要求图片格式为png-8格式，若png-8实在影响图片质量或其中有半透明效果，请为ie6单独定义背景：_background：none。_filter：progid：DXImageTransform.Microsoft.AlphaImageLoader(sizingMethod=crop，src=’img/bg.png’)。

15、避免兼容性属性的使用，比如text-shadow||css3的相关属性。

16、减少使用影响性能的属性，比如position：absolute||float。

17、必须为大区块样式添加注释，小区块适量注释。

18、代码缩进与格式：建议单行书写，可根据自身习惯，后期优化会统一处理。

E. JS书写规范

1、文件编码统一为utf-8，书写过程过，每行代码结束必须有分号。原则上所有功能均根据XXX项目需求原生开发，以避免网上down下来的代码造成的代码污染(沉冗代码||与现有代码冲突||...)。

2、库引入：原则上仅引入jQuery库，若需引入第三方库，须与团队其他人员讨论决定。

3、变量命名：驼峰式命名.原生JS变量要求是纯英文字母，首字母须小写，如myVue。jQuery变量要求首字符为'_'，其他与原生JS规则相同，如：_myVue。另，要求变量集中声明，避免全局变量.

4、类命名：首字母大写，驼峰式命名.如MyVue。

5、函数命名：首字母小写驼峰式命名.如myVue()。

6、命名语义化，尽可能利用英文单词或其缩写。

7、尽量避免使用存在兼容性及消耗资源的方法或属性，比如eval_r()&innerText。

8、后期优化中，JS非注释类中文字符须转换成unicode编码使用，以避免编码错误时乱码显示。

9、代码结构明了，加适量注释.提高函数重用率。

10、注重与html分离，减小reflow，注重浏览器性能.



F.图片规范

1、所有页面元素类图片均放入img文件夹，测试用图片放于demo文件夹。

2、图片格式gif/png/jpg。提倡使用webp文件格式，使用软件进行图片压缩。

3、命名全部用小写英文字母||数字||_的组合，其中不得包含汉字||空格||特殊字符；尽量用易懂的词汇，便于团队其他成员理解。另，命名分头尾两部分，用下划线隔开，比如ad_left01.gif||btn_submit.gif。

4、在保证视觉效果的情况下选择最小的图片格式与图片质量，以减少加载时间。5、尽量避免使用半透明的png图片(若使用，请参考css规范相关说明)。

6、运用css精灵图技术集中小的背景图或图标，减小页面http请求，但注意，请务必在对应的精灵图psd源图中划参考线，并保存至img目录下



G.测试规范

开发及测试工具约定建议使用Aptana-Sublime-Vim-WebStrom，亦可根据自己喜好选择，但须遵循如下原则：

1、不可利用IDE的视图模式'画'代码。

2、不可利用IDE生成相关功能代码。

3、编码必须格式化，比如缩进。测试工具：前期开发仅测试FireFox&IE6&IE7&IE8，后期优化时加入Opera&Chrome&Safari。建议测试顺序：FireFox-->IE-->Opera-->Chrome-->Safari。
