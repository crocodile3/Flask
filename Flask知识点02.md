<!DOCTYPE html>
<html><head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">

<title>Flask基础知识02.md</title>
    
<style id="wiz_custom_css">html, body {font-size: 12pt;}body {font-family: Helvetica, 'Hiragino Sans GB', '微软雅黑', 'Microsoft YaHei UI', SimSun, SimHei, arial, sans-serif;line-height: 1.6;margin: 0 auto;padding: 20px 16px;padding: 1.25rem 1rem;}h1, h2, h3, h4, h5, h6 {margin:20px 0 10px;margin:1.25rem 0 0.625rem;padding: 0;font-weight: bold;}h1 {font-size:20pt;font-size:1.67rem;}h2 {font-size:18pt;font-size:1.5rem;}h3 {font-size:15pt;font-size:1.25rem;}h4 {font-size:14pt;font-size:1.17rem;}h5 {font-size:12pt;font-size:1rem;}h6 {font-size:12pt;font-size:1rem;color: #777777;margin: 1rem 0;}div, p, ul, ol, dl, li {margin:0;}blockquote, table, pre, code {margin:8px 0;}ul, ol {padding-left:32px;padding-left:2rem;}ol.wiz-list-level1 > li {list-style-type:decimal;}ol.wiz-list-level2 > li {list-style-type:lower-latin;}ol.wiz-list-level3 > li {list-style-type:lower-roman;}blockquote {padding:0 12px;padding:0 0.75rem;}blockquote > :first-child {margin-top:0;}blockquote > :last-child {margin-bottom:0;}img {border:0;max-width:100%;height:auto !important;margin:2px 0;}table {border-collapse:collapse;border:1px solid #bbbbbb;}td, th {padding:4px 8px;border-collapse:collapse;border:1px solid #bbbbbb;min-height:28px;word-break:break-all;box-sizing: border-box;}.wiz-hide {display:none !important;}</style><style name="wiz_tmp_editor_style">html {height:100%;} body {min-height:100%;box-sizing:border-box;word-wrap: break-word !important;}a {word-wrap: break-word;}img::selection {background-color: rgba(0, 0, 255, 0.3);}.wiz-table-container {border:0px !important;}.wiz-table-body {border:0px !important;position:relative;margin:10px 0;overflow-x:auto;overflow-y:hidden;-webkit-overflow-scrolling:touch;}.wiz-table-body table {margin:0;outline:none;}td,th {outline:none;}undefinedundefined</style><link rel="stylesheet" charset="utf-8" name="wiz_tmp_editor_style" href="C:/Users/Administrator/Desktop/Flask基础知识02_files/github2.css"><link rel="stylesheet" charset="utf-8" name="wiz_tmp_editor_style" href="C:/Users/Administrator/Desktop/Flask基础知识02_files/wizToc.css"><style id="wiz_code_style">.wiz-code-container{position: relative; padding:8px 0; margin: 5px 25px 5px 5px;text-indent:0; text-align:left;}.CodeMirror {font-family: Consolas, "Liberation Mono", Menlo, Courier, monospace; color: black; font-size: 10pt; font-size: 0.83rem}.CodeMirror-lines {padding: 4px 0;}.CodeMirror pre {padding: 0 4px;}.CodeMirror-scrollbar-filler, .CodeMirror-gutter-filler {background-color: white;}.CodeMirror-gutters {border-right: 1px solid #ddd; background-color: #f7f7f7; white-space: nowrap;}.CodeMirror-linenumbers {}.CodeMirror-linenumber {padding: 0 3px 0 5px; min-width: 20px; text-align: right; color: #999; white-space: nowrap;}.CodeMirror-guttermarker {color: black;}.CodeMirror-guttermarker-subtle {color: #999;}.CodeMirror-cursor {border-left: 1px solid black; border-right: none; width: 0;}.CodeMirror div.CodeMirror-secondarycursor {border-left: 1px solid silver;}.cm-fat-cursor .CodeMirror-cursor {width: auto; border: 0 !important; background: #7e7;}.cm-fat-cursor div.CodeMirror-cursors {z-index: 1;}.cm-animate-fat-cursor {width: auto; border: 0; -webkit-animation: blink 1.06s steps(1) infinite; -moz-animation: blink 1.06s steps(1) infinite; animation: blink 1.06s steps(1) infinite; background-color: #7e7;}@-moz-keyframes blink {  0% {}  50% { background-color: transparent; }  100% {}}@-webkit-keyframes blink {  0% {}  50% { background-color: transparent; }  100% {}}@keyframes blink {  0% {}  50% { background-color: transparent; }  100% {}}.CodeMirror-overwrite .CodeMirror-cursor {}.cm-tab { display: inline-block; text-decoration: inherit; }.CodeMirror-rulers {position: absolute; left: 0; right: 0; top: -50px; bottom: -20px; overflow: hidden;}.CodeMirror-ruler {border-left: 1px solid #ccc; top: 0; bottom: 0; position: absolute;}.cm-s-default .cm-header {color: blue;}.cm-s-default .cm-quote {color: #090;}.cm-negative {color: #d44;}.cm-positive {color: #292;}.cm-header, .cm-strong {font-weight: bold;}.cm-em {font-style: italic;}.cm-link {text-decoration: underline;}.cm-strikethrough {text-decoration: line-through;}.cm-s-default .cm-keyword {color: #708;}.cm-s-default .cm-atom {color: #219;}.cm-s-default .cm-number {color: #164;}.cm-s-default .cm-def {color: #00f;}.cm-s-default .cm-variable,.cm-s-default .cm-punctuation,.cm-s-default .cm-property,.cm-s-default .cm-operator {}.cm-s-default .cm-variable-2 {color: #05a;}.cm-s-default .cm-variable-3 {color: #085;}.cm-s-default .cm-comment {color: #a50;}.cm-s-default .cm-string {color: #a11;}.cm-s-default .cm-string-2 {color: #f50;}.cm-s-default .cm-meta {color: #555;}.cm-s-default .cm-qualifier {color: #555;}.cm-s-default .cm-builtin {color: #30a;}.cm-s-default .cm-bracket {color: #997;}.cm-s-default .cm-tag {color: #170;}.cm-s-default .cm-attribute {color: #00c;}.cm-s-default .cm-hr {color: #999;}.cm-s-default .cm-link {color: #00c;}.cm-s-default .cm-error {color: #f00;}.cm-invalidchar {color: #f00;}.CodeMirror-composing { border-bottom: 2px solid; }div.CodeMirror span.CodeMirror-matchingbracket {color: #0f0;}div.CodeMirror span.CodeMirror-nonmatchingbracket {color: #f22;}.CodeMirror-matchingtag { background: rgba(255, 150, 0, .3); }.CodeMirror-activeline-background {background: #e8f2ff;}.CodeMirror {position: relative; background: #f5f5f5;}.CodeMirror-scroll {overflow: hidden !important; margin-bottom: 0; margin-right: -30px; padding: 16px 30px 16px 0; outline: none; position: relative;}.CodeMirror-sizer {position: relative; border-right: 30px solid transparent;}.CodeMirror-vscrollbar, .CodeMirror-hscrollbar, .CodeMirror-scrollbar-filler, .CodeMirror-gutter-filler {position: absolute; z-index: 6; display: none;}.CodeMirror-vscrollbar {right: 0; top: 0; overflow-x: hidden; overflow-y: scroll;}.CodeMirror-hscrollbar {bottom: 0; left: 0 !important; overflow-y: hidden; overflow-x: scroll;}.CodeMirror-scrollbar-filler {right: 0; bottom: 0;}.CodeMirror-gutter-filler {left: 0; bottom: 0;}.CodeMirror-gutters {position: absolute; left: 0; top: -5px; min-height: 100%; z-index: 3;}.CodeMirror-gutter {white-space: normal; height: inherit; display: inline-block; vertical-align: top; margin-bottom: -30px;}.CodeMirror-gutter-wrapper {position: absolute; z-index: 4; background: none !important; border: none !important;}.CodeMirror-gutter-background {position: absolute; top: 0; bottom: 0; z-index: 4;}.CodeMirror-gutter-elt {position: absolute; cursor: default; z-index: 4; text-align: center;}.CodeMirror-gutter-wrapper ::selection { background-color: transparent }.CodeMirror-gutter-wrapper ::-moz-selection { background-color: transparent }.CodeMirror-lines {cursor: text; min-height: 1px;}.CodeMirror pre {-moz-border-radius: 0; -webkit-border-radius: 0; border-radius: 0; border-width: 0; background: transparent; font-family: inherit; font-size: inherit; margin: 0; white-space: pre; word-wrap: normal; line-height: inherit; color: inherit; z-index: 2; position: relative; overflow: visible; -webkit-tap-highlight-color: transparent; -webkit-font-variant-ligatures: contextual; font-variant-ligatures: contextual;}.CodeMirror-wrap pre {word-wrap: break-word; white-space: pre-wrap; word-break: normal;}.CodeMirror-linebackground {position: absolute; left: 0; right: 0; top: 0; bottom: 0; z-index: 0;}.CodeMirror-linewidget {position: relative; z-index: 2; overflow: auto;}.CodeMirror-widget {}.CodeMirror-rtl pre { direction: rtl; }.CodeMirror-code {outline: none;}.CodeMirror-scroll,.CodeMirror-sizer,.CodeMirror-gutter,.CodeMirror-gutters,.CodeMirror-linenumber {-moz-box-sizing: content-box; box-sizing: content-box;}.CodeMirror-measure {position: absolute; width: 100%; height: 0; overflow: hidden; visibility: hidden;}.CodeMirror-cursor {position: absolute; pointer-events: none;}.CodeMirror-measure pre { position: static; }div.CodeMirror-cursors {visibility: hidden; position: relative; z-index: 3;}div.CodeMirror-dragcursors {visibility: visible;}.CodeMirror-focused div.CodeMirror-cursors {visibility: visible;}.CodeMirror-selected { background: #d9d9d9; }.CodeMirror-focused .CodeMirror-selected { background: #d7d4f0; }.CodeMirror-crosshair { cursor: crosshair; }.CodeMirror-line::selection, .CodeMirror-line > span::selection, .CodeMirror-line > span > span::selection { background: #d7d4f0; }.CodeMirror-line::-moz-selection, .CodeMirror-line > span::-moz-selection, .CodeMirror-line > span > span::-moz-selection { background: #d7d4f0; }.cm-searching {background: #ffa; background: rgba(255, 255, 0, .4);}.cm-force-border { padding-right: .1px; }@media print {  .CodeMirror div.CodeMirror-cursors {visibility: hidden;}}.cm-tab-wrap-hack:after { content: ""; }span.CodeMirror-selectedtext { background: none; }.CodeMirror-activeline-background, .CodeMirror-selected {transition: visibility 0ms 100ms;}.CodeMirror-blur .CodeMirror-activeline-background, .CodeMirror-blur .CodeMirror-selected {visibility:hidden;}.CodeMirror-blur .CodeMirror-matchingbracket {color:inherit !important;outline:none !important;text-decoration:none !important;}</style><style name="wiz_tmp_editor_style">.wiz-code-tools {display:none;position: absolute; top: -32px; right: 0; opacity: .95; z-index: 10;}.CodeMirror-focused .wiz-code-tools {display:block;}.CodeMirror-sizer {border-right: 0 !important;}body pre.prettyprint {padding:0;}body pre.prettyprint code {white-space: pre;}body pre.prettyprint.linenums {box-shadow:none; overflow: auto;-webkit-overflow-scrolling: touch;}body pre.prettyprint.linenums ol.linenums {box-shadow: 40px 0 0 #FBFBFC inset, 41px 0 0 #ECECF0 inset; padding: 10px 10px 10px 40px !important;}</style><style name="wiz_tmp_editor_style">.CodeMirror-cursors {visibility: hidden !important;}</style></head>

<body class="markdown-body" spellcheck="false" contenteditable="false"><h2 id="1.7获取请求数据">1.7获取请求数据</h2>

<div class="wiz-table-container" style="position: relative; padding: 0px;"><div class="wiz-table-body"><table style="width: 836px;"><tbody><tr><td align="left" valign="middle" style="width: 119px;">属性</td><td align="left" valign="middle" style="width: 404px;">描述</td><td align="left" valign="middle" style="width: 161px;">类型</td><td align="left" valign="middle" style="width: 151px;">备注</td></tr><tr><td align="left" valign="middle" style="width: 119px;">method</td><td align="left" valign="middle" style="width: 404px;">记录请求使用的HTTP方法</td><td align="left" valign="middle" style="width: 161px;">GET/POST</td><td align="left" valign="middle" style="width: 151px;"><br></td></tr><tr><td align="left" valign="middle" style="width: 119px;">headers</td><td align="left" valign="middle" style="width: 404px;">记录请求中的报文头</td><td align="left" valign="middle" style="width: 161px;">EnvironHeaders</td><td align="left" valign="middle" style="width: 151px;"><br></td></tr><tr><td align="left" valign="middle" style="width: 119px;">url</td><td align="left" valign="middle" style="width: 404px;">记录请求的URL地址</td><td align="left" valign="middle" style="width: 161px;">string</td><td align="left" valign="middle" style="width: 151px;"><br></td></tr><tr><td align="left" valign="middle" style="width: 119px;">cookies</td><td align="left" valign="middle" style="width: 404px;">记录请求中的cookie信息</td><td align="left" valign="middle" style="width: 161px;">Dict</td><td align="left" valign="middle" style="width: 151px;"><br></td></tr><tr><td align="left" valign="middle" style="width: 119px;">args</td><td align="left" valign="middle" style="width: 404px;">记录请求中的查询参数</td><td align="left" valign="middle" style="width: 161px;">MultiDict</td><td align="left" valign="middle" style="width: 151px;"><br></td></tr><tr><td align="left" valign="middle" style="width: 119px;">form</td><td align="left" valign="middle" style="width: 404px;">记录请求中的表单数据</td><td align="left" valign="middle" style="width: 161px;">MultiDict</td><td align="left" valign="middle" style="width: 151px;"><br></td></tr><tr><td align="left" valign="middle" style="width: 119px;">data</td><td align="left" valign="middle" style="width: 404px;">记录请求的数据，并转换为字符串</td><td align="left" valign="middle" style="width: 161px;">*</td><td align="left" valign="middle" style="width: 151px;"><br></td></tr><tr><td align="left" valign="middle" style="width: 119px;">files</td><td align="left" valign="middle" style="width: 404px;">记录请求上传的文件</td><td align="left" valign="middle" style="width: 161px;">*</td><td align="left" valign="middle" style="width: 151px;"><br></td></tr></tbody></table></div></div>

<p>注：在flaskz中，以上都是request对象的属性，可以通过requst得到属性的值。 <br>
例如： <br>
获取请求的方法：request.method; <br>
获取请求中的数据：request.post.get('键名')</p>

<h2 id="1.8异常捕获">1.8异常捕获</h2>

<h3 id="1.8.1abort方法-程序主动抛出异常，程序不再往下执行；">1.8.1abort方法-程序主动抛出异常，程序不再往下执行；</h3>

<p>用法：abort(错误状态码)</p>

<h3 id="1.8errorhandler装饰器-能够捕获异常或者状态码">1.8errorhandler装饰器-能够捕获异常或者状态码</h3>

<p>@app.errorhandler(404) <br>
def internal_server_error(e): <br>
    return '网页找不到了', 404</p>

<h2 id="1.9请求钩子-类似django中的中间件，通过装饰器实现">1.9请求钩子-类似django中的中间件，通过装饰器实现</h2>

<p>四种请求钩子 <br>
before_first_request：在处理第一个请求前运行，应用场景：链接数据库 <br>
before_request：在每次请求前运行。应用场景：进行参数校验，不满足，直接返回一个信息，不调用视图函数； <br>
after_request：如果没有未处理的异常抛出，在每次请求后运行。注：运用该钩子时，函数需要传入response参数。应用场景：可以拼接响应头的信息，例如更改返回数据的类型 <br>
teardown_request：在每次请求后运行，即使有未处理的异常抛出。应用场景：捕获异常，添加到日志中；</p>

<h2 id="1.10cookie">1.10cookie</h2>

<h3 id="1.10.1设置cookie，利用make_response进行设置">1.10.1设置cookie，利用make_response进行设置</h3>

<p>response = make_response(返回的内容) <br>
response.set_cookie('键','值'，max_age=3600) <br>
eg <br>
from flask imoprt Flask,make_response <br>
@app.route('/cookie') <br>
def set_cookie(): <br>
    resp = make_response('this is to set cookie') <br>
    resp.set_cookie('username', 'itcast') <br>
    return resp</p>

<h3 id="1.10.2获取cookie-request.cookies.get(键名)">1.10.2获取cookie-request.cookies.get(键名)</h3>

<p>eg <br>
rom flask import Flask,request <br>
获取cookie <br>
@app.route('/request') <br>
def resp_cookie(): <br>
    resp = request.cookies.get('username') <br>
    return resp</p>

<h2 id="1.11session">1.11session</h2>

<h3 id="1.11.1设置session">1.11.1设置session</h3>

<p>类似于字典：session['键名']=‘值’ <br>
secret_key(盐值)-用于做混淆 <br>
eg <br>
设置session首先先设置secret_key <br>
app.secret_key = 'adc%scs%fgh%' <br>
from flask import Flask, session <br>
@app.route('/set_session') <br>
def set_session(): <br>
    session['username'] = 'crocodile' <br>
    return redirect(url_for('get_session'))</p>

<h3 id="1.11.2获取session">1.11.2获取session</h3>

<p>session.get('键') <br>
eg <br>
@app.route('/get_session') <br>
def get_session(): <br>
    print session.get('username')</p>

<p>注：flask的session值存放在浏览器中</p>

<h2 id="1.12Flask-Script-命令行启动服务器">1.12Flask-Script-命令行启动服务器</h2>

<p>步骤： <br>
第一步：导入Flask-Script扩展 <br>
第二步：创建manager对象-由manager托管app的命令 <br>
第三步：使用manager运行项目- manager.run() <br>
第四步：运行项目文件 <br>
python 文件名 runserver(-p改端口，-d调试模式，-h改ip) <br>
eg <br>
from flask import Flask <br>
from flask_script import Manager</p>

<p>app = Flask(<strong>name</strong>) <br>
manager = Manager(app)</p>

<p>@app.route('/') <br>
def index(): <br>
return '床前明月光'</p>

<p>if <strong>name</strong> == "<strong>main</strong>": <br>
manager.run()</p>

<h1 id="2.模板">2.模板</h1>

<h2 id="2.1jinja2模板引擎">2.1jinja2模板引擎</h2>

<p>1.render_template函数封装了模板引擎； <br>
2.render_template函数的第一个参数是模板的文件名，后面的参数都是键值对，表示模板中变量对应的真实值； <br>
3.变量代码块表示：{{}} <br>
4.for循环，if语句的表示方法 <br>
{% if user %} <br>
    {{ user }} <br>
{% else %} <br>
    hello!</p>

<ul>
    {% for index in indexs %}
    <li> {{ index }} </li>
    {% endfor %}
</ul>

<p>5.注释-{#   xxxx    # }</p>

<h2 id="2.2过滤器">2.2过滤器</h2>

<ul>
<li>过滤器的使用方式：变量名 | 过滤器 <br>
{{variable | filter_name(*args)}}</li>
<li>链式调用-使用多个过滤器 <br>
先将字符串进行反转，然后全部变为大写 <br>
{{ "hello world" | reverse | upper }}</li>
<li>求字典中年龄的和 <br>
dict_list = [{'name':'jack','age':'18'},{'name':'tom','age':'16'},{'name':'marry','age':'20'}] <br>
{{ dict_list | sum(attribute = 'age') }} <br>
+常见的过滤器</li>
</ul>

<div class="wiz-table-container" style="position: relative; padding: 0px;"><div class="wiz-table-body"><table style="width: 852px;"><tbody><tr><td style="width: 90px;">名称</td><td style="width: 84px;">过滤器</td><td style="width: 342px;">描述</td><td style="width: 335px;">用法</td></tr><tr><td align="left" valign="middle" style="width: 90px;" rowspan="9" colspan="1">字符串</td><td align="left" valign="middle" style="width: 84px;"><span style="color:rgb(51, 51, 51);font-family:&quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;font-size:1rem;font-style:normal;font-weight:400;text-align:left;text-indent:0px;background-color:rgb(255, 255, 255);display:inline !important;">safe</span><br></td><td align="left" valign="middle" style="width: 342px;"><span style="color:rgb(51, 51, 51);font-family:&quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;font-size:1rem;font-style:normal;font-weight:400;text-align:left;text-indent:0px;background-color:rgb(255, 255, 255);display:inline !important;">禁用转义</span><br></td><td align="left" valign="middle" style="width: 335px;">&lt;p&gt;{{ '&lt;em&gt;hello&lt;/em&gt;' | safe }}&lt;/p&gt;<br></td></tr><tr><td align="left" valign="middle" style="width: 84px;">capitalize<br></td><td align="left" valign="middle" style="width: 342px;"><span style="color:rgb(51, 51, 51);font-family:&quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;font-size:1rem;font-style:normal;font-weight:400;text-align:left;text-indent:0px;background-color:rgb(255, 255, 255);display:inline !important;">把变量值的首字母转成大写，其余字母转小写</span><br></td><td align="left" valign="middle" style="width: 335px;">&lt;p&gt;{{ 'hello' | capitalize }}&lt;/p&gt;<br></td></tr><tr><td align="left" valign="middle" style="width: 84px;">lower<br></td><td align="left" valign="middle" style="width: 342px;">把值转成小写<br></td><td align="left" valign="middle" style="width: 335px;">&lt;p&gt;{{ 'HELLO' | lower }}&lt;/p&gt;<br></td></tr><tr><td align="left" valign="middle" style="width: 84px;"><span style="color:rgb(51, 51, 51);font-family:&quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;font-size:1rem;font-style:normal;font-weight:400;text-align:left;text-indent:0px;background-color:rgb(255, 255, 255);display:inline !important;">upper</span><br></td><td align="left" valign="middle" style="width: 342px;"><span style="color:rgb(51, 51, 51);font-family:&quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;font-size:1rem;font-style:normal;font-weight:400;text-align:left;text-indent:0px;background-color:rgb(255, 255, 255);display:inline !important;">把值转成大写</span><br></td><td align="left" valign="middle" style="width: 335px;">&lt;p&gt;{{ 'hello' | upper }}&lt;/p&gt;<br></td></tr><tr><td align="left" valign="middle" style="width: 84px;"><span style="color:rgb(51, 51, 51);font-family:&quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;font-size:1rem;font-style:normal;font-weight:400;text-align:left;text-indent:0px;background-color:rgb(255, 255, 255);display:inline !important;">title</span><br></td><td align="left" valign="middle" style="width: 342px;"><span style="color:rgb(51, 51, 51);font-family:&quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;font-size:1rem;font-style:normal;font-weight:400;text-align:left;text-indent:0px;background-color:rgb(255, 255, 255);display:inline !important;">把值中的每个单词的首字母都转成大写</span><br></td><td align="left" valign="middle" style="width: 335px;">&lt;p&gt;{{ 'hello' | title }}&lt;/p&gt;<br></td></tr><tr><td align="left" valign="middle" style="width: 84px;"><span style="color:rgb(51, 51, 51);font-family:&quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;font-size:1rem;font-style:normal;font-weight:400;text-align:left;text-indent:0px;background-color:rgb(255, 255, 255);display:inline !important;">reverse</span><br></td><td align="left" valign="middle" style="width: 342px;"><span style="color:rgb(51, 51, 51);font-family:&quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;font-size:1rem;font-style:normal;font-weight:400;text-align:left;text-indent:0px;background-color:rgb(255, 255, 255);display:inline !important;">字符串反转</span><br></td><td align="left" valign="middle" style="width: 335px;">&lt;p&gt;{{ 'olleh' | reverse }}&lt;/p&gt;<br></td></tr><tr><td align="left" valign="middle" style="width: 84px;">format<br></td><td align="left" valign="middle" style="width: 342px;"><span style="color:rgb(0, 0, 0);font-family:Helvetica, 'Hiragino Sans GB', 微软雅黑, 'Microsoft YaHei UI', SimSun, SimHei, arial, sans-serif;font-size:1rem;font-style:normal;font-weight:normal;text-align:-webkit-left;text-indent:0px;display:inline !important;">格式化输出</span><br></td><td align="left" valign="middle" style="width: 335px;">&lt;p&gt;{{ '%s is %d' | format('name',17) }}&lt;/p&gt;<br></td></tr><tr><td align="left" valign="middle" style="width: 84px;">striptags<br></td><td align="left" valign="middle" style="width: 342px;">渲染之前把值中所有的HTML标签都删掉<br></td><td align="left" valign="middle" style="width: 335px;">&lt;p&gt;{{ '&lt;em&gt;hello&lt;/em&gt;' | striptags }}&lt;/p&gt;<br></td></tr><tr><td align="left" valign="middle" style="width: 84px;">truncate<br></td><td align="left" valign="middle" style="width: 342px;">字符串截断<br></td><td align="left" valign="middle" style="width: 335px;">&lt;p&gt;{{ 'hello every one' | truncate(9)}}&lt;/p&gt;<br></td></tr><tr><td style="width: 90px;" rowspan="5" colspan="1">列表</td><td style="width: 84px;">first</td><td style="width: 342px;"><span style="color:rgb(51, 51, 51);font-family:&quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;font-size:1rem;font-style:normal;font-weight:400;text-align:left;text-indent:0px;background-color:rgb(255, 255, 255);display:inline !important;">取第一个元素</span><br></td><td style="width: 335px;">&lt;p&gt;{{ [1,2,3,4,5,6] | first }}&lt;/p&gt;<br></td></tr><tr><td style="width: 84px;">last</td><td style="width: 342px;"><span style="color:rgb(51, 51, 51);font-family:&quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;font-size:1rem;font-style:normal;font-weight:400;text-align:left;text-indent:0px;background-color:rgb(255, 255, 255);display:inline !important;">取最后一个元素</span><br></td><td style="width: 335px;">&lt;p&gt;{{ [1,2,3,4,5,6] | last }}&lt;/p&gt;<br></td></tr><tr><td style="width: 84px;">length</td><td style="width: 342px;"><span style="color:rgb(51, 51, 51);font-family:&quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;font-size:1rem;font-style:normal;font-weight:400;text-align:left;text-indent:0px;background-color:rgb(255, 255, 255);display:inline !important;">获取列表长度</span><br></td><td style="width: 335px;">&lt;p&gt;{{ [1,2,3,4,5,6] | length }}&lt;/p&gt;<br></td></tr><tr><td style="width: 84px;">sum</td><td style="width: 342px;"><span style="color:rgb(51, 51, 51);font-family:&quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;font-size:1rem;font-style:normal;font-weight:400;text-align:left;text-indent:0px;background-color:rgb(255, 255, 255);display:inline !important;">列表求和</span><br></td><td style="width: 335px;">&lt;p&gt;{{ [1,2,3,4,5,6] | sum }}&lt;/p&gt;<br></td></tr><tr><td style="width: 84px;">sort</td><td style="width: 342px;"><span style="color:rgb(51, 51, 51);font-family:&quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;font-size:1rem;font-style:normal;font-weight:400;text-align:left;text-indent:0px;background-color:rgb(255, 255, 255);display:inline !important;">列表排序</span><br></td><td style="width: 335px;">&lt;p&gt;{{ [6,2,3,1,5,4] | sort }}&lt;/p&gt;<br></td></tr><tr><td style="width: 90px;" rowspan="2" colspan="1">语句块</td><td style="width: 84px;" rowspan="2" colspan="1"><br></td><td style="width: 342px;" rowspan="2" colspan="1"><br></td><td style="width: 335px;" rowspan="2" colspan="1">{% filter upper %}<br>&nbsp; &nbsp; 一段文字<br>{% endfilter %}<br></td></tr><tr></tr></tbody></table></div></div>

<h2 id="2.3自定义过滤器">2.3自定义过滤器</h2>

<ul>
<li><p>方式一：调用app的add_template_filter方法 <br>
步骤 <br>
第一步：先定义一个函数 <br>
第二步：调用app的add_template_filter方法 <br>
<img src="file:///C:/Users/Administrator/Desktop/Flask基础知识02_files/0738cde0-2157-4c76-a94f-05a01617420f.png" style="vertical-align: bottom; max-width: 100%;"></p></li>
<li><p>方式二：用装饰器来实现过滤器-@app.template_filter(名称) <br>
<img src="file:///C:/Users/Administrator/Desktop/Flask基础知识02_files/a33acf64-26ce-41f8-bfee-ee3fd63f5ba0.png" style="vertical-align: bottom; max-width: 100%;"></p></li>
</ul>

<h2 id="2.4控制代码块">2.4控制代码块</h2>

<ul>
<li>if 语句 <br>
<img src="file:///C:/Users/Administrator/Desktop/Flask基础知识02_files/3e545ccd-8a2f-4dad-9afd-af37b59a155c.png" style="vertical-align: bottom; max-width: 100%;"></li>
<li><p>for循环语句 <br>
<img src="file:///C:/Users/Administrator/Desktop/Flask基础知识02_files/638a1552-2842-487c-83dd-88b85b9f54e1.png" style="vertical-align: bottom; max-width: 100%;"></p></li>
<li><p>for循环中嵌套if语句 <br>
<img src="file:///C:/Users/Administrator/Desktop/Flask基础知识02_files/8eddcbf5-dcce-48f3-889a-e874f42245fb.png" style="vertical-align: bottom; max-width: 100%;"></p></li>
<li><p>for循环块中可以文芳的变量</p></li>
</ul>

<div class="wiz-table-container" style="position: relative; padding: 0px;"><div class="wiz-table-body"><table style="width: 859px;"><tbody><tr><td align="left" valign="middle" style="text-align: center; width: 157px;">变量</td><td align="left" valign="middle" style="text-align: center; width: 430px;">描述</td><td align="left" valign="middle" style="text-align: center; width: 271px;">备注</td></tr><tr style="height: 36px;"><td align="left" valign="middle" style="width: 157px;">loop.index</td><td align="left" valign="middle" style="width: 430px;">当前循环迭代的次数（从 1 开始）</td><td align="left" valign="middle" style="width: 271px;"><br></td></tr><tr><td align="left" valign="middle" style="width: 157px;">loop.index0</td><td align="left" valign="middle" style="width: 430px;">当前循环迭代的次数（从 0 开始）</td><td align="left" valign="middle" style="width: 271px;"><br></td></tr><tr><td align="left" valign="middle" style="width: 157px;">loop.revindex</td><td align="left" valign="middle" style="width: 430px;">到循环结束需要迭代的次数（从 1 开始）</td><td align="left" valign="middle" style="width: 271px;"><br></td></tr><tr><td align="left" valign="middle" style="width: 157px;">loop.revindex0</td><td align="left" valign="middle" style="width: 430px;">到循环结束需要迭代的次数（从 0 开始）</td><td align="left" valign="middle" style="width: 271px;"><br></td></tr><tr><td align="left" valign="middle" style="width: 157px;">loop.first</td><td align="left" valign="middle" style="width: 430px;">如果是第一次迭代，为 True 。</td><td align="left" valign="middle" style="width: 271px;"><br></td></tr><tr><td align="left" valign="middle" style="width: 157px;">loop.last</td><td align="left" valign="middle" style="width: 430px;">如果是最后一次迭代，为 True 。</td><td align="left" valign="middle" style="width: 271px;"><br></td></tr><tr><td align="left" valign="middle" style="width: 157px;">loop.length</td><td align="left" valign="middle" style="width: 430px;">序列中的项目数。</td><td align="left" valign="middle" style="width: 271px;"><br></td></tr><tr><td align="left" valign="middle" style="width: 157px;">loop.cycle</td><td align="left" valign="middle" style="width: 430px;">在一串序列间期取值的辅助函数。见下面示例程序。</td><td align="left" valign="middle" style="width: 271px;">loop.cycle（传入自定义的索引值） 能够改变默认的索引值<br></td></tr></tbody></table></div></div>

<ul>
<li>去除循环中不换行的空格 <br>
<img src="file:///C:/Users/Administrator/Desktop/Flask基础知识02_files/985d1f16-898e-46e7-9e68-e0e49f4ee321.png" style="vertical-align: bottom; max-width: 100%;"></li>
</ul>

<h2 id="2.5模板代码复用">2.5模板代码复用</h2>

<p><strong>1. 继承</strong> <br>
{% block top %} {% endblock %} <br>
<img src="file:///C:/Users/Administrator/Desktop/Flask基础知识02_files/73c4ba02-fbf2-41f2-9c89-01e727676368.png" style="vertical-align: bottom; max-width: 100%;"> <br>
<strong>2. 包含</strong>-将另一个模板全部加载到当前模板中，并直接渲染 <br>
<img src="file:///C:/Users/Administrator/Desktop/Flask基础知识02_files/7abf8af0-817a-421c-9b46-4d922aba7526.png" style="vertical-align: bottom; max-width: 100%;"> <br>
<strong>3. 宏（macro）</strong>-避免代码的重复 <br>
相当于jinja2模板中的一个函数，对重复的代码进行一个封装 <br>
宏用法： <br>
第一步：定义宏（一般在一个单独文件中进行定义）； <br>
第二步：调用宏； <br>
eg <br>
需求，构造如下一个表单 <br>
<img src="file:///C:/Users/Administrator/Desktop/Flask基础知识02_files/37b926e9-56a1-458c-841f-4c30a1b36265.png" style="vertical-align: bottom; max-width: 100%;"> <br>
用宏的方法实现 <br>
<img src="file:///C:/Users/Administrator/Desktop/Flask基础知识02_files/6e2330c5-253b-43e7-b37f-0c07200e930f.png" style="vertical-align: bottom; max-width: 100%;"></p><wiz_tmp_tag id="wiz-table-range-border" contenteditable="false" style="display: none;"><div id="wiz-table-col-line" style="display: none;"></div><div id="wiz-table-row-line" style="display: none;"></div><div id="wiz-table-range-border_start" style="display: none;"><div id="wiz-table-range-border_start_top"></div><div id="wiz-table-range-border_start_right"></div><div id="wiz-table-range-border_start_bottom"></div><div id="wiz-table-range-border_start_left"></div><div id="wiz-table-range-border_start_dot"></div></div><div id="wiz-table-range-border_range" style="display: none;"><div id="wiz-table-range-border_range_top"></div><div id="wiz-table-range-border_range_right"></div><div id="wiz-table-range-border_range_bottom"></div><div id="wiz-table-range-border_range_left"></div><div id="wiz-table-range-border_range_dot"></div></div></wiz_tmp_tag></body></html>