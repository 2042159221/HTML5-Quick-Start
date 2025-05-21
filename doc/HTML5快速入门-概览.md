

# 课程目标

[TOC]

系统学习前端开发，夯实基础，美化自己的工具布局显示，强化独立开发能力。



# 一、认识互联网



## （一）、本地开发 & 服务器共享

### 本地开发（开发阶段）

 -使用编辑器写代码

 -浏览器访问（只能在本地访问）:localhost:3000

 -服务通常使用的本地端口：8080、3000、3001...(仅供测试调试)

### 上线→服务器共享

 -把写好的 代码部署公网服务器上（阿里云、腾讯云）

 -访问域名（如：www.baidu.com）→实际访问服务器ip+应用服务

 -通过网络可以实现网站、服务共享

### 总结

本地开发是自测，服务器部署是共享。

## （二）、HTTP协议

**前后端通信的“语言协议”**，基于请求/响应模型。

### 完整通信流程

1. 浏览器发出request
2. 服务器收到请求，执行代码，返回response
3. 浏览器拿到响应结果，渲染页面以及处理数据

### 常见请求结构

请求request;

```http
GET /user?id=1 HTTP/1.1
Host: www.example.com
Content-Type: application/json
```

相应 response：

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "id": 1,
  "name": "张三"
}

```

### 常见请求方法

| 方法   | 用途     |
| ------ | -------- |
| GET    | 获取资源 |
| POST   | 提交数据 |
| PUT    | 更新资源 |
| DELETE | 删除资源 |

## （三）、前后端请求交互流程

用浏览器访问标准

用户点击按钮
    ↓
前端（JS）发出请求 fetch('/api/user')
    ↓
后端接收到请求（Controller）
    ↓
调用服务层 -> 数据库查数据
    ↓
封装成 JSON 数据
    ↓
后端返回 Response
    ↓
前端拿到数据，更新页面内容



# 二、HTML5基础语法

## （一）文档基本结构

预览：

![](https://cdn.jsdelivr.net/gh/2042159221/image_bed//iamges/20250519132313871.png)

```
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>我的网页</title>
</head>
<body>
  <h1>你好，HTML5！</h1>
</body>
</html>
```

| 标签                     | 作用                                 |
| ------------------------ | ------------------------------------ |
| `<!DOCTYPE html>`        | 声明 HTML5 文档类型                  |
| `<html>`                 | 页面根元素                           |
| `<head>`                 | 页头信息（编码、标题、引用资源）     |
| `<meta charset="UTF-8">` | 声明字符集为 UTF-8（支持中文）       |
| `<title>`                | 浏览器标签上的名字                   |
| `<body>`                 | 页面内容区域（你看到的内容都在这里） |

### 文档类型声明（DTD / Document Type Declaration）

#### 什么是 `<!DOCTYPE>`？

`<!DOCTYPE>` 不是 HTML 标签，而是一条**告诉浏览器如何解析页面的声明指令**。
 它的位置必须在 HTML 文档的**最顶行**，位于 `<html>` 之前！

#### DTD 的定义

DTD=文档类型定义

#### SGML是什么

=标准通用语言标记

HTML 4.01 是 SGML 的子集，必须用 `DTD` 告诉浏览器页面采用的是哪一套语法标准。

####  HTML5 与 HTML4 DTD 区别一览

| 项目              | HTML4.01     | HTML5        |
| ----------------- | ------------ | ------------ |
| 是否基于 SGML     | 是           | 否           |
| 是否引用 DTD 文件 | 引用         | 不引用       |
| 语法复杂度        | 三种声明方式 | 统一一种写法 |
| 建议使用          | 历史了解     | 现在主流     |

#### 各版本写法

HTML5 标准（最常用，推荐使用）：

```

<!DOCTYPE html>
```

 HTML 4.01 有三种 DTD 写法：

**严格版（Strict）**：不允许使用旧标签（如 `<font>`）

```
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN"
"http://www.w3.org/TR/html4/strict.dtd">
```

**过渡版（Transitional）**：允许使用旧标签（过渡用）

```
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN"
"http://www.w3.org/TR/html4/loose.dtd">
```

**框架版（Frameset）**：用于框架结构的页面（早已废弃）

```
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Frameset//EN"
"http://www.w3.org/TR/html4/frameset.dtd">
```

###  常见基础标签

####  文本类标签

| 标签            | 功能             |
| --------------- | ---------------- |
| `<h1>` ~ `<h6>` | 标题（从大到小） |
| `<p>`           | 段落             |
| `<br>`          | 换行（单标签）   |
| `<hr>`          | 水平线（单标签） |
| `<strong>`      | 加粗             |
| `<em>`          | 斜体（强调）     |

------

####  链接和图片

| 标签                   | 功能                              |
| ---------------------- | --------------------------------- |
| `<a href="URL">`       | 超链接                            |
| `<img src="图片地址">` | 插入图片（必须有 `src` 和 `alt`） |



```
<a href="https://www.baidu.com">去百度</a>
<img src="cat.jpg" alt="一只猫">
```

------

#### 列表

| 标签   | 功能              |
| ------ | ----------------- |
| `<ul>` | 无序列表（点点）  |
| `<ol>` | 有序列表（1.2.3） |
| `<li>` | 列表项            |



```
<ul>
  <li>苹果</li>
  <li>香蕉</li>
</ul>

```



------

#### 表格

```
<table>
  <tr>
    <th>姓名</th>
    <th>年龄</th>
  </tr>
  <tr>
    <td>小明</td>
    <td>18</td>
  </tr>
</table>
```

------

####  表单元素

| 标签                    | 功能       |
| ----------------------- | ---------- |
| `<form>`                | 表单容器   |
| `<input>`               | 输入框     |
| `<textarea>`            | 多行输入框 |
| `<button>`              | 按钮       |
| `<label>`               | 标签绑定   |
| `<select>` + `<option>` | 下拉框     |



```
<form>
  <label>用户名: <input type="text" name="user"></label>
  <button type="submit">提交</button>
</form>
```

------

###  HTML5新增标签

| 标签        | 含义           |
| ----------- | -------------- |
| `<header>`  | 页头           |
| `<footer>`  | 页尾           |
| `<section>` | 区块           |
| `<article>` | 文章内容       |
| `<nav>`     | 导航菜单       |
| `<main>`    | 页面主体       |
| `<video>`   | 视频播放       |
| `<audio>`   | 音频播放       |
| `<canvas>`  | 画布（JS绘图） |

### 网页组成

网页主要由三部分组成：

结构（Structure）、表现（Presentation）和行为（Behavior）

| 标准 | 简介                                                         | 描述       |
| :--- | :----------------------------------------------------------- | :--------- |
| 结构 | 用于对网页元素进行整理和分类，即当下学习的 HTML              | 网页的骨骼 |
| 表现 | 表现用户设置网页元素的排版、颜色、大小修饰等外观样式，即 CSS | 网页的皮肤 |
| 行为 | 行为是指网页模型的定义、交互等编写，即要学习的 JavaScript    | 网页的神经 |

Web 标准提出的最佳体验方案：

- 结构、样式、行为相分离
- 即：结构写在 HTML 文件中，表现写在 CSS 文件中，行为写在 JavaScript 文件中

### 网页三要素

- title：标题
- keywords：关键词
- description：描述

**SEO优化**

利用搜索引擎的规则提高网站在有关搜索引擎内的自然排名。目的是让其在行业内占据领先地位，获得品牌收益。

示例：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <!--IE8及以上的版本按照最新的标准去渲染-->
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
      <!--用户移动端适配-->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <title>微信智能营销系统 - AI自动评论助手｜智能聊天机器人｜品牌名</title>
    <meta name="description" content="专业微信营销工具：AI智能朋友圈评论系统+全场景聊天助手，帮助销售、微商和私域运营者提升客户互动效率，激活沉睡客户资源。"/>
    <meta name="keywords" content="微信营销工具,朋友圈自动评论,微信聊天机器人,私域流量管理,客户关系维护"/>

    <meta name="robots" content="index,follow"/>
    
    <style>
        body {
            font-family: 'PingFang SC', 'Microsoft YaHei', sans-serif;
            line-height: 1.8;
            color: #333;
            max-width: 900px;
            margin: 0 auto;
            padding: 25px;
            background-color: #f9f9f9;
        }
        h1, h2, h3 {
            color: #2c3e50;
            margin-top: 1.8em;
            font-weight: 600;
        }
        h1 { 
            font-size: 2.4rem;
            border-bottom: 2px solid #eaeaea;
            padding-bottom: 12px;
            margin-bottom: 1.2em;
        }
        h2 {
            font-size: 1.9rem;
            color: #2980b9;
            padding-left: 10px;
            border-left: 4px solid #2980b9;
        }
        h3 {
            font-size: 1.5rem;
            color: #34495e;
        }
        code {
            background: #f0f3f5;
            padding: 3px 6px;
            border-radius: 4px;
            font-family: 'Courier New', monospace;
            color: #c7254e;
        }
        .feature-card {
            background: white;
            border-radius: 6px;
            padding: 20px;
            margin: 25px 0;
            box-shadow: 0 2px 8px rgba(0,0,0,0.08);
            border-left: 4px solid #3498db;
        }
        pre {
            background: #f5f7f9;
            padding: 15px;
            border-radius: 6px;
            overflow-x: auto;
            border-left: 3px solid #3498db;
        }
        ul {
            padding-left: 1.5em;
        }
        li {
            margin-bottom: 0.8em;
        }
        .update-info {
            font-size: 0.9em;
            color: #7f8c8d;
            text-align: right;
            margin-top: 40px;
        }
    </style>
</head>
<body>

    <h1>微信营销工具SEO优化方案</h1>
    
    <div class="feature-card">
        <h2>核心价值定位</h2>
        <p>通过专业SEO优化提升工具在搜索引擎中的可见度，精准触达以下目标用户群体：</p>
        <ul>
            <li><strong>销售顾问</strong>：管理大量客户关系的专业人士</li>
            <li><strong>私域运营者</strong>：负责企业微信客户资源运营的团队</li>
            <li><strong>微商从业者</strong>：依赖微信开展业务的个体经营者</li>
        </ul>
    </div>

    <section>
        <h2>一、基础SEO配置规范</h2>
        
        <div class="feature-card">
            <h3>1. 页面标题优化</h3>
            <pre><code>&lt;title&gt;微信智能营销系统 - AI自动评论助手｜智能聊天机器人｜品牌名&lt;/title&gt;</code></pre>
            <p>优化要点：</p>
            <ul>
                <li>品牌名称放在最后，避免过度优化</li>
                <li>核心功能关键词控制在3个以内</li>
                <li>使用中文竖线"｜"分隔关键词</li>
            </ul>
        </div>
        
        <div class="feature-card">
            <h3>2. 元描述优化</h3>
            <pre><code>&lt;meta name="description" content="专业微信营销工具：AI智能朋友圈评论系统+全场景聊天助手，帮助销售、微商和私域运营者提升客户互动效率，激活沉睡客户资源。"&gt;</code></pre>
            <p>内容要求：</p>
            <ul>
                <li>控制在150个字符以内</li>
                <li>包含主要功能点和目标用户</li>
                <li>使用自然流畅的语句</li>
            </ul>
        </div>
    </section>

    <section>
        <h2>二、核心功能结构化标记</h2>
        
        <div class="feature-card">
            <h3>1. 朋友圈智能评论系统</h3>
            <pre><code>&lt;section&gt;
    &lt;h2&gt;AI智能朋友圈互动系统&lt;/h2&gt;
    &lt;p&gt;基于&lt;mark&gt;自然语言处理技术&lt;/mark&gt;实现拟人化自动评论：&lt;/p&gt;
    &lt;ul&gt;
        &lt;li&gt;智能分析朋友圈内容语义&lt;/li&gt;
        &lt;li&gt;生成个性化互动评论&lt;/li&gt;
        &lt;li&gt;支持情感倾向匹配&lt;/li&gt;
    &lt;/ul&gt;
&lt;/section&gt;</code></pre>
        </div>
        
        <div class="feature-card">
            <h3>2. 智能聊天助手</h3>
            <pre><code>&lt;section&gt;
    &lt;h2&gt;全场景聊天助手&lt;/h2&gt;
    &lt;div&gt;
        &lt;h3&gt;核心功能&lt;/h3&gt;
        &lt;ul&gt;
            &lt;li&gt;&lt;strong&gt;智能自动回复&lt;/strong&gt;：处理常见咨询&lt;/li&gt;
            &lt;li&gt;&lt;strong&gt;商务洽谈辅助&lt;/strong&gt;：提供话术建议&lt;/li&gt;
            &lt;li&gt;&lt;strong&gt;重要消息提醒&lt;/strong&gt;：监控关键信息&lt;/li&gt;
        &lt;/ul&gt;
    &lt;/div&gt;
&lt;/section&gt;</code></pre>
        </div>
    </section>

    <section>
        <h2>三、技术优化实施要点</h2>
        <div class="feature-card">
            <ul>
                <li>使用<code>&lt;time datetime="2025-05-19"&gt;2025年5月19日&lt;/time&gt;</code>标记重要更新时间</li>
                <li>所有外部链接添加<code>rel="nofollow"</code>属性</li>
                <li>功能截图添加详细的<code>alt</code>描述文本</li>
                <li>重要功能点使用<code>&lt;mark&gt;</code>高亮标记</li>
                <li>避免使用JavaScript渲染核心内容</li>
            </ul>
        </div>
    </section>

    <p class="update-info">最后更新：<time datetime="2025-05-19">2025年5月19日</time></p>

</body>
</html>
```

![](https://cdn.jsdelivr.net/gh/2042159221/image_bed//iamges/20250519142532245.png)

### 最佳实践

**<!DOCTYPE html>**

- **场景**：所有 HTML5 文档的开头
- **最佳实践**：始终作为文档的第一行

**<html>**

- **场景**：整个 HTML 文档的根元素
- **最佳实践**：始终包含 `lang` 属性指定语言

