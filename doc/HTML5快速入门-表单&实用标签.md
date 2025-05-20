# HTML5快速入门-表单&实用标签

## 表单元素

### 基本用法

TIP

- 所有的 HTML 表单都是以一个 `<form>`元素包裹
- `action`属性：提交表单时向何处发送表单数据
- `method`属性：规定用于发送表单数据的 HTTP 方法

```html
<h1>HTML的form表单</h1>

<form action="/user/login" method="get">......</form>
```

###  HTML 单行文本框详解总结

单行文本框是最常用的输入控件，允许用户在网页中输入一行纯文本。

使用方式:

<input type="text">

**📖 单行文本框常用属性一览：**

| 属性名         | 说明                                                   |
| -------------- | ------------------------------------------------------ |
| `type="text"`  | 设置为单行文本框                                       |
| `value=""`     | 设置默认值（即初始时输入框内显示的值）                 |
| `placeholder`  | 提示文本：显示在文本框内的灰色说明文字，用户输入后消失 |
| `disabled`     | 禁用状态，用户无法点击或输入                           |
| `readonly`     | 只读状态，内容可选中但不可编辑                         |
| `name`         | 表单提交时该字段的键（key），用于后台接收              |
| `maxlength`    | 限制用户输入的最大字符数量                             |
| `required`     | 设置为必填项，表单提交时必须填写                       |
| `autocomplete` | 控制是否允许浏览器自动填写本输入框（`on` / `off`）     |

**示例**

```html
<form action="/user" method="POST">
  <p>用户名：
    <input 
      type="text" 
      name="username"
    />
  </p>
  
  <p>真实姓名：
    <input 
      type="text" 
      name="realname"
      placeholder="请输入您的真实姓名 ..."
    />
  </p>
  
  <p>所在城市：
    <input 
      type="text" 
      name="city"
      value="北京市海淀区"
      disabled
    />
  </p>
</form>

```

**☑️ 分析结果：**

- 第一项：基本输入框，无初始值
- 第二项：带 `placeholder` 的输入框，用于引导用户填写
- 第三项：设置了 `value` 默认值 + `disabled` 禁用（展示但不可操作）

**tip**

- `disabled` 表单不会被提交
- `readonly` 会被提交但不能改
- 使用 `placeholder` 时不要忘记设置 `name`，否则后台接收不到数据
- 若输入框重要建议加 `required` 限制防止为空提交

### 密码框：`<input type="password">`

```html
<input type="password" name="password" required placeholder="请输入密码" />

```

💡 和文本框用法一致，但输入内容会以 `●●●` 隐藏，提升安全性。

### 单选按钮：`<input type="radio">`

```html
<label><input type="radio" name="sex" value="男" /> 男</label>
<label><input type="radio" name="sex" value="女" /> 女</label>
<label><input type="radio" name="sex" value="保密" checked /> 保密</label>

```

| 属性      | 描述                         |
| --------- | ---------------------------- |
| `name`    | 相同 `name` 的单选按钮会互斥 |
| `value`   | 提交值                       |
| `checked` | 设置默认选中                 |

### 复选框：`<input type="checkbox">`'

```html
<label><input type="checkbox" name="hobby" value="篮球" checked /> 篮球</label>
<label><input type="checkbox" name="hobby" value="书法" /> 书法</label>

```

| 属性      | 描述                  |
| --------- | --------------------- |
| `name`    | 复选项应设置相同 name |
| `value`   | 多个值以数组方式提交  |
| `checked` | 默认选中              |

###  label 标签：增强可用性

**html5写法**

```html
<label><input type="radio" name="city" value="北京" /> 北京</label>

```

**html4写法**

```html
<input type="radio" name="city" id="beijing" />
<label for="beijing">北京</label>

```

📌 **优势**：点击文字也可选中对应控件，提升用户体验。

### 表单分组：`<fieldset>` + `<legend>`

```html
<fieldset>
  <legend>个人信息</legend>
  <label for="fname">名：</label>
  <input type="text" id="fname" name="fname" />
</fieldset>

```

用途：逻辑分组 + 辅助样式 + 语义结构提升



### 下拉框：`<select> + <option>` + `<optgroup>`

**普通下拉框**

```html
<select name="province">
  <option value="湖北省">湖北省</option>
  <option value="湖南省">湖南省</option>
</select>

```

**分组下拉菜单**

```html
<select name="country" required>
  <option value="" disabled selected>请选择国家</option>
  <optgroup label="亚洲">
    <option value="CN">中国</option>
    <option value="JP">日本</option>
  </optgroup>
  <optgroup label="欧洲">
    <option value="FR">法国</option>
  </optgroup>
</select>

```

### 多行文本框：`<textarea>`

```html
<textarea name="comment" rows="5" cols="50" placeholder="请输入评论..."></textarea>

```

TIP

- `<textarea>` 表示多行文本框
- 有 `rows`和`cols`属性，用于定义多行文本框的行数和列数

### 按钮种类

```html
<input type="submit" value="提交" />
<input type="reset" value="重置" />
<input type="button" value="普通按钮" />
<button>button标签</button>

```



### HTML5 新增表单控件（现代浏览器推荐）

```html
<form>
  <input type="color" />
  <input type="date" />
  <input type="time" />
  <input type="email" required />
  <input type="number" min="1" max="10" />
  <input type="range" min="10" max="50" />
  <input type="search" />
  <input type="url" />
</form>

```

| 类型     | 描述             |
| -------- | ---------------- |
| `color`  | 颜色选择器       |
| `date`   | 日期选择器       |
| `time`   | 时间选择器       |
| `email`  | 邮箱格式校验     |
| `number` | 限定范围数字输入 |
| `range`  | 滑动条           |
| `search` | 带清除按钮搜索框 |
| `url`    | 网址验证         |

### 智能提示输入：`<datalist>`

```html
<input type="text" list="languages" />
<datalist id="languages">
  <option value="JavaScript" />
  <option value="Python" />
  <option value="Go" />
</datalist>

```



### 常用总表

| 控件类型   | 标签结构                  | 功能描述       |
| ---------- | ------------------------- | -------------- |
| 文本框     | `<input type="text">`     | 单行输入       |
| 密码框     | `<input type="password">` | 隐藏输入       |
| 单选按钮   | `<input type="radio">`    | 单选互斥       |
| 复选框     | `<input type="checkbox">` | 多选           |
| 下拉框     | `<select> + <option>`     | 单选列表       |
| 多行文本框 | `<textarea>`              | 多行输入       |
| 提交按钮   | `<input type="submit">`   | 提交表单       |
| 重置按钮   | `<input type="reset">`    | 重置所有输入   |
| 普通按钮   | `<input type="button">`   | 自定义事件按钮 |
| 文件上传   | `<input type="file">`     | 上传文件       |
| 日期控件   | `<input type="date">`     | 选择日期       |

### tips

有 `<input>` 应配 `name` 属性，否则后端接收不到值

单选、复选必须配合 `value`，否则传值为空

`required` + `placeholder` 是用户体验 + 验证基本保障

文件上传记得设置：`enctype="multipart/form-data"`



## 实用标签

###  `<details>` 和 `<summary>` —— 折叠式内容展示

💡 **作用**：无需 JavaScript，实现 FAQ 折叠展开内容。

```html
<details open>
  <summary>点击查看详情</summary>
  <p>这里是隐藏的内容，点击摘要时会展开。</p>
</details>

```

| 标签        | 功能                                   |
| ----------- | -------------------------------------- |
| `<details>` | 创建可折叠的块（可加 `open` 默认展开） |
| `<summary>` | 折叠块的标题（点击展开/折叠）          |



✅ **场景**：FAQ 页面、协议条款说明、隐藏内容区域等。

###  `<progress>` 和 `<meter>` —— 图形化数据进度/指标

`<progress>`：**未知总量的进度（如加载中）**

```html
<label for="download">下载进度：</label>
<progress id="download" value="70" max="100">70%</progress>

```

 `<meter>`：**已知总量的度量（如评分、电量）**

```html
<label for="score">磁盘使用：</label>
<meter id="score" value="0.6">60%</meter>
```

| 标签         | 用途                                           |
| ------------ | ---------------------------------------------- |
| `<progress>` | 表示某项进度（加载进度）                       |
| `<meter>`    | 表示某个数值在范围内的位置（性能指标、电量等） |

###  `<output>` —— 表达计算或结果显示区

💡 常与 JavaScript 或 `<form oninput>` 搭配，用于展示结果。

```html
<form oninput="result.value=parseInt(a.value)+parseInt(b.value)">
  <input type="number" id="a" value="0" /> +
  <input type="number" id="b" value="0" /> =
  <output name="result">0</output>
</form>

```

| 属性           | 说明                |
| -------------- | ------------------- |
| `name`         | 可提交结果          |
| `for`（HTML5） | 可指明关联的控件 ID |

✅ **场景**：计算器、在线问卷即时反馈、表单实时预览

###  `<ruby>` / `<rt>` / `<rp>` / `<rb>` —— 注音标注神器

💡 用于东亚文字拼音/假名标注，尤其在教育类、儿童读物或无障碍阅读中应用广泛。

**基本用法**

```html
<ruby>
  汉<rp>(</rp><rt>Hàn</rt><rp>)</rp>
  字<rp>(</rp><rt>zì</rt><rp>)</rp>
</ruby>

```

**使用 `<rb>` 明确基础文本（可选）：**

```html
<ruby>
  <rb>汉</rb><rp>(</rp><rt>Hàn</rt><rp>)</rp>
  <rb>字</rb><rp>(</rp><rt>zì</rt><rp>)</rp>
</ruby>

```

| 标签     | 说明                                 |
| -------- | ------------------------------------ |
| `<ruby>` | 包裹需注音的文本                     |
| `<rt>`   | 注音（如拼音）                       |
| `<rp>`   | 备用括号，供不支持 ruby 的浏览器使用 |
| `<rb>`   | 明确标注基础文本（可省略）           |

✅ **场景**：拼音识字、日语假名、语言学习网站、儿童读物

### 特别推荐组合标签（HTML5 特色搭配）

| 标签组合              | 功能说明                 | 示例场景                 |
| --------------------- | ------------------------ | ------------------------ |
| `<form>` + `<output>` | 表单实时计算反馈         | 成本计算器、在线报价系统 |
| `<details>` + CSS     | 可定制样式的内容展开收起 | 问答列表、注释说明       |
| `<progress>` + JS     | 动态进度展示（文件上传） | 上传界面、进度提醒       |
| `<ruby>`              | 多语种发音教学、拼音辅助 | 多语言网站、教育平台     |

### 实用标签总表

| 标签         | 功能                             |
| ------------ | -------------------------------- |
| `<details>`  | 可折叠内容（支持 open 默认展开） |
| `<summary>`  | 折叠标题                         |
| `<progress>` | 表示加载/处理进度                |
| `<meter>`    | 表示某个已知范围的度量值         |
| `<output>`   | 表单输出结果显示                 |
| `<ruby>`     | 注音（拼音、假名）标注           |
| `<rt>`       | 注音内容                         |
| `<rp>`       | 备用括号显示                     |
| `<rb>`       | 明确注音对应的文本（非必需）     |

## 实战

```html
<!DOCTYPE html>
<html lang="zh">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <meta name="description" content="专业微信营销工具：AI智能朋友圈评论系统+全场景聊天助手，帮助销售、微商和私域运营者提升客户互动效率，激活沉睡客户资源。" />
  <meta name="keywords" content="微信营销工具,朋友圈自动评论,微信聊天机器人,私域流量管理,客户关系维护" />
  <title>微信AI兴趣用户信息收集表</title>
  <link rel="icon" href="../Demo/logo/roboter.ico" type="image/x-icon">
  <style>
    body { font-family: "微软雅黑", sans-serif; padding: 20px; max-width: 800px; margin: auto; }
    fieldset { margin-bottom: 20px; padding: 20px; border: 1px solid #ccc; }
    legend { font-weight: bold; }
    label { display: block; margin-top: 12px; }
    input, select, textarea { width: 100%; padding: 8px; margin-top: 4px; }
    progress, meter { width: 100%; height: 20px; }
    details { margin-top: 12px; }
  </style>
</head>
<body>

  <h1>微信AI工具兴趣用户信息收集表</h1>

  <form oninput="score.value=parseInt(age.value)">
    
    <!-- 👤 基本信息 -->
    <fieldset>
      <legend>基本资料</legend>

      <label for="name">姓名：</label>
      <input type="text" id="name" name="name" placeholder="请输入姓名" required />

      <label>性别：</label>
      <label><input type="radio" name="gender" value="男" /> 男</label>
      <label><input type="radio" name="gender" value="女" /> 女</label>
      <label><input type="radio" name="gender" value="保密" checked /> 保密</label>

      <label for="job">职业：</label>
      <select name="job" id="job" required>
        <option value="" disabled selected>请选择职业</option>
        <option value="产品经理">产品经理</option>
        <option value="程序员">程序员</option>
        <option value="市场运营">市场运营</option>
        <option value="学生">学生</option>
        <option value="自由职业">自由职业</option>
      </select>
    </fieldset>

    <!-- 🧠 兴趣与偏好 -->
    <fieldset>
      <legend>AI工具偏好</legend>

      <label>你希望通过微信AI实现什么？</label>
      <label><input type="checkbox" name="usecase" value="内容创作" /> 内容创作</label>
      <label><input type="checkbox" name="usecase" value="自动回复客服" /> 自动客服</label>
      <label><input type="checkbox" name="usecase" value="语音识别" /> 语音识别</label>
      <label><input type="checkbox" name="usecase" value="AI绘图" /> AI绘图</label>

      <label for="tools">你感兴趣的微信AI功能：</label>
      <input type="text" list="tool-list" id="tools" name="tools" placeholder="可输入/选择" />
      <datalist id="tool-list">
        <option value="对话式AI" />
        <option value="图像生成" />
        <option value="知识助手" />
        <option value="智能翻译" />
        <option value="语音指令" />
      </datalist>
    </fieldset>

    <!-- 📧 联系方式 -->
    <fieldset>
      <legend>联系方式</legend>

      <label for="email">邮箱地址：</label>
      <input type="email" name="email" id="email" placeholder="example@domain.com" required />

      <label for="phone">手机号：</label>
      <input type="tel" name="phone" id="phone" placeholder="请输入手机号" />
    </fieldset>

    <!-- 📊 年龄+实时评分 -->
    <fieldset>
      <legend>年龄 + AI适应度评分</legend>

      <label for="age">你的年龄（模拟评分）：</label>
      <input type="range" name="age" id="age" min="18" max="60" value="25" />
      当前得分：<output name="score">25</output> 分

      <label>注册完成进度：</label>
      <progress value="80" max="100">80%</progress>

      <label>AI兴趣热度：</label>
      <meter value="0.75" min="0" max="1">75%</meter>
    </fieldset>

    <!-- 📚 拼音演示 -->
    <fieldset>
      <legend>辅助说明：注音演示</legend>
      <p>
        <ruby>
          <rb>智</rb><rp>(</rp><rt>zhì</rt><rp>)</rp>
          <rb>能</rb><rp>(</rp><rt>néng</rt><rp>)</rp>
          <rb>助</rb><rp>(</rp><rt>zhù</rt><rp>)</rp>
          <rb>手</rb><rp>(</rp><rt>shǒu</rt><rp>)</rp>
        </ruby>
      </p>
    </fieldset>

    <!-- 📌 FAQ 折叠 -->
    <fieldset>
      <legend>常见问题（FAQ）</legend>

      <details>
        <summary>提交后我的数据会被怎么使用？</summary>
        <p>数据仅用于产品调研分析，不会泄露。</p>
      </details>

      <details>
        <summary>微信AI未来会有哪些功能？</summary>
        <p>包括对话生成、图像识别、语音助手、自动回复等。</p>
      </details>

      <details>
        <summary>我可以多次提交兴趣表单吗？</summary>
        <p>可以，每次都能帮助我们更准确了解用户需求。</p>
      </details>
    </fieldset>

    <!-- 🧾 地区选择 -->
    <fieldset>
      <legend>所在地区</legend>
      <label for="province">省份：</label>
      <select name="province" id="province" required>
        <option value="" disabled selected>请选择所在省</option>
        <optgroup label="东部">
          <option value="江苏">江苏</option>
          <option value="浙江">浙江</option>
        </optgroup>
        <optgroup label="西部">
          <option value="四川">四川</option>
          <option value="云南">云南</option>
        </optgroup>
      </select>
    </fieldset>

    <!-- 🔘 按钮区 -->
    <p>
      <input type="submit" value="提交信息" />
      <input type="reset" value="重置表单" />
    </p>
  </form>

</body>
</html>

```

**✅ 技术整合亮点：**

| 技术点                    | 使用情况 | 场景说明                      |
| ------------------------- | -------- | ----------------------------- |
| `fieldset` / `legend`     | ✅        | 信息逻辑分区                  |
| 所有 `<input>` 类型       | ✅        | 文本、密码、电话、邮箱、range |
| `<select>` / `<optgroup>` | ✅        | 地区和职业分组                |
| `<datalist>`              | ✅        | 输入联想功能                  |
| `<output>`                | ✅        | 实时显示评分                  |
| `<progress>` / `<meter>`  | ✅        | 进度条、度量图形展示          |
| `<details>` / `<summary>` | ✅        | FAQ 折叠内容                  |
| `<ruby>` 注音标签         | ✅        | 中文拼音教学示例              |