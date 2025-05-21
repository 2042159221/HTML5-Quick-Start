# HTML5快速入门之-表格标签

------

**✅ HTML 表格标签：系统总结 + 实战技巧**

------

## 1️⃣ 表格基本结构标签

| 标签        | 描述                           |
| ----------- | ------------------------------ |
| `<table>`   | 定义表格容器                   |
| `<caption>` | 表格标题（第一个子元素）       |
| `<tr>`      | 表格行（Table Row）            |
| `<th>`      | 表头单元格，默认加粗居中       |
| `<td>`      | 普通单元格，表格数据内容       |
| `<thead>`   | 表格页眉，通常用于列标题       |
| `<tbody>`   | 表格主体内容                   |
| `<tfoot>`   | 表格页脚，通常用于合计、备注等 |

------

### ✅ 示例：

```html
<table>
  <caption>通讯录</caption>
  <thead>
    <tr>
      <th>姓名</th>
      <th>性别</th>
      <th>年龄</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>张三</td>
      <td>男</td>
      <td>20</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td colspan="3">数据更新时间：2025年</td>
    </tr>
  </tfoot>
</table>
```

------

## 2️⃣ 表格属性（传统 HTML 属性，**推荐用 CSS 替代**）

| 属性          | 描述                 | 替代方案                  |
| ------------- | -------------------- | ------------------------- |
| `border`      | 设置边框             | 用 `CSS: border:`         |
| `width`       | 表格宽度             | 用 `CSS: width:`          |
| `cellpadding` | 单元格内容与边框间距 | 用 `CSS: padding:`        |
| `cellspacing` | 单元格间距           | 用 `CSS: border-spacing:` |

💡 **HTML5 中建议全部使用 CSS 控制样式**，更灵活、语义清晰。

------

## 3️⃣ 表格跨列 `colspan` & 跨行 `rowspan`

| 属性      | 说明           |
| --------- | -------------- |
| `colspan` | 单元格横跨多列 |
| `rowspan` | 单元格纵跨多行 |

### ✅ 跨列示例：

```html
<tr>
  <th colspan="4">学生基本信息</th>
</tr>
```

### ✅ 跨行示例：

```html
<tr>
  <td rowspan="2">功能模块</td>
  <td>任务 A</td>
</tr>
<tr>
  <td>任务 B</td>
</tr>
```

------

## 4️⃣ thead / tbody / tfoot 的语义化结构

- `<thead>`：表格的列标题部分
- `<tbody>`：主要数据部分
- `<tfoot>`：结尾备注或统计，优先加载时优化性能排序

### ✅ 实战：

```html
<table border="1">
  <thead>
    <tr>
      <th>专业</th>
      <th>姓名</th>
      <th>性别</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>计算机</td>
      <td>李雷</td>
      <td>男</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td colspan="3">共 1 人</td>
    </tr>
  </tfoot>
</table>
```

------

## 5️⃣ 实战强化：复杂表格案例

### 🧾 表格：跨行 + 跨列 + 多层表头

```html
<table border="1" width="800">
  <caption>版本规划任务分配表</caption>
  <tr>
    <th colspan="2">需求：V0.3版本规划</th>
    <th>优先级</th>
    <th>任务分解</th>
    <th>负责人</th>
  </tr>
  <tr>
    <td rowspan="3">功能模块1</td>
    <td>具体事项1</td>
    <td>3</td>
    <td>任务1</td>
    <td rowspan="3">@翠花</td>
  </tr>
  <tr>
    <td rowspan="2">具体事项2</td>
    <td>4</td>
    <td>任务2</td>
  </tr>
  <tr>
    <td>1</td>
    <td>任务3</td>
  </tr>
</table>
```

------

## 6️⃣ 表格最佳实践建议

| 建议                                                 | 原因                                   |
| ---------------------------------------------------- | -------------------------------------- |
| 使用 `<thead>` / `<tbody>` / `<tfoot>`               | 提高语义结构和浏览器兼容性             |
| 避免 `width`, `cellpadding`, `border` 等 HTML 属性   | 改用 CSS 控制样式                      |
| 表头用 `<th>` 表示，提高可访问性                     | 屏幕阅读器和语义更清晰                 |
| 不滥用表格布局                                       | 表格用于展示结构化数据，不用于布局结构 |
| 必要时使用 `scope="col"` 或 `scope="row"` 增强可读性 | 可提升可访问性 (Accessibility)         |

------

## 7️⃣ 表格+CSS 简单美化示例

```html
<style>
  table {
    border-collapse: collapse;
    width: 100%;
  }
  caption {
    font-weight: bold;
    margin-bottom: 8px;
  }
  th, td {
    border: 1px solid #999;
    padding: 8px 12px;
    text-align: center;
  }
  thead {
    background-color: #f2f2f2;
  }
</style>
```

------

## 🎯 总结表：HTML 表格核心标签 & 属性一览

| 分类          | 标签 / 属性   | 描述                       |
| ------------- | ------------- | -------------------------- |
| 容器          | `<table>`     | 表格容器                   |
| 结构          | `<caption>`   | 表格标题                   |
|               | `<tr>`        | 表格行                     |
|               | `<td>`        | 普通单元格                 |
|               | `<th>`        | 表头单元格                 |
|               | `<thead>`     | 表格页眉                   |
|               | `<tbody>`     | 表格主体                   |
|               | `<tfoot>`     | 表格页脚                   |
| 合并单元格    | `colspan`     | 横向合并列                 |
|               | `rowspan`     | 纵向合并行                 |
| (旧) 样式属性 | `border`      | 边框（推荐使用 CSS）       |
|               | `cellpadding` | 内容与边距（CSS 替代）     |
|               | `cellspacing` | 单元格之间间距（CSS 替代） |

## 实战代码

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>微信AI兴趣用户信息表格</title>
    <meta name="description" content="专业微信营销工具：AI智能朋友圈评论系统+全场景聊天助手，帮助销售、微商和私域运营者提升客户互动效率，激活沉睡客户资源。" />
    <meta name="keywords" content="微信营销工具,朋友圈自动评论,微信聊天机器人,私域流量管理,客户关系维护" />
    <link rel="icon" href="../Demo/logo/roboter.ico" type="image/x-icon">
    <style>
        body {
            font-family: Arial, sans-serif;
            padding:40px;
            background-color: #f7f7f7;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 30px;
            background-color: #fff;
        }
        caption {
            caption-side: top;
            text-align:center;
            font-size: 1.5em;
            font-weight: bold;
            padding: 10px;
            color: #0e4a7e;
        }
        th,td {
            border: 1px solid #ccc;
            padding: 12px 10px;
            text-align: center;
        }
        thead {
            background: #f0f8ff;
        }
        tfoot {
            background-color: #fafafa;
            font-weight: bold;
        }
        tr:hover {
            background-color: #f1f1f1;
        }
        input[type="text"] {
            margin-bottom: 15px;
            padding: 6px;
            width: 300px;
            border:1px solid #ccc;
        }
        ruby rt {
            font-size: 0.8em;
            color: #999;
        }
        summary {
            font-size: bold;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <h1 style="text-align: center;">微信AI兴趣用户信息表格</h1>
    <input type="text" id="filterInput" placeholder="🔍 请输入关键词进行过滤...">
    <table id="userTable">
        <caption>微信AI用户兴趣信息一览</caption>
        <thead>
            <tr>
                <th>姓名</th>
                <th>性别</th>
                <th>职业</th>
                <th>地区</th>
                <th>兴趣点</th>
                <th>感兴趣功能</th>
                <th>联系方式</th>
                <th>AI适应度</th>
                <th colspan="2">身份证明</th>
            </tr>
        </thead>
        <tbody id="userTableBody">
            <!-- 数据行将在这里插入 -->
             <tr>
                <td>张三</td>
                <td>男</td>
                <td>程序员</td>
                <td>北京</td>
                <td>
                    内容创作<br>自动客服
                </td>
                <td>
                    图像生成<br>
                    对话式AI
                </td>
                <td>zhangsan@example.com<br>13653062121</td>
                <td>
                    <meter value="0.85" min="0" max="1">85%</meter><br>
                    <progress value="85" max="100"></progress>
                </td>
                <td colspan="2">实名认证成功</td>
            </tr>
            <tr>
                <td>李四</td>
                <td>女</td>
                <td>产品经理</td>
                <td>上海</td>
                <td>
                  AI绘图<br>语音识别
                </td>
                <td>
                  翻译助手
                </td>
                <td>lisi@weixin.com<br>139****5678</td>
                <td>
                  <meter value="0.65" min="0" max="1">65%</meter><br>
                  <progress value="65" max="100"></progress>
                </td>
                <td >等待验证</td>
                <td >未提交</td>
              </tr>
              <tr>
                <td>王五</td>
                <td>保密</td>
                <td>市场运营</td>
                <td>北京</td>
                <td>
                  内容创作
                </td>
                <td>
                  语音讲解
                </td>
                <td>wangwu@demo.com<br>137****8888</td>
                <td>
                  <meter value="0.95" min="0" max="1">95%</meter><br>
                  <progress value="95" max="100"></progress>
                </td>
                <td >等待验证</td>
                <td >已提交</td>
              </tr>
        </tbody>
        <tfoot>
            <tr>
                <td colspan="10">
                    本表共收录 3 条用户数据<br>
                    数据来源：微信AI兴趣用户信息收集表
                </td>
            </tr>
        </tfoot>
    </table>

    <details style="margin-top: 30px;">
        <summary>📌 表格说明（点击展开）</summary>
        <p>本表格展示来源于微信AI兴趣收集表单，展示了用户填写的职业、地区、兴趣点和联系方式等信息。</p>
        <p>“AI适应度”为系统模拟得分，以进度条与度量条两种方式展示。</p>
        <p>部分关键词使用 `<ruby>` 注音辅助，提升产品易懂性。</p>
      </details>
    <script>
        // 过滤功能
        const input = document.getElementById("filterInput");
        const table = document.getElementById("userTable");
        input.addEventListener("keyup", function () {
        const filter = input.value.toLowerCase();
        const rows = table.getElementsByTagName("tbody")[0].getElementsByTagName("tr");
        for (let row of rows) {
            const text = row.innerText.toLowerCase();
            row.style.display = text.includes(filter) ? "" : "none";
        }
        });
       // 点击表头排序（简单实现）
        const headers = table.querySelectorAll("thead th");
        headers.forEach((th, idx) => {
        th.addEventListener("click", () => {
            const tbody = table.querySelector("tbody");
            const rows = Array.from(tbody.querySelectorAll("tr"));
            const sorted = rows.sort((a, b) => {
            const valA = a.children[idx]?.innerText || "";
            const valB = b.children[idx]?.innerText || "";
            return valA.localeCompare(valB);
            });
            tbody.innerHTML = "";
            sorted.forEach(row => tbody.appendChild(row));
        });
        });
    </script>
</body>
</html>
```

**✅ 应用点总结**

| 特性                          | 使用说明        |
| ----------------------------- | --------------- |
| `<caption>`                   | 表格标题        |
| `<thead> / <tbody> / <tfoot>` | 语义化结构      |
| `<td colspan> / <td rowspan>` | 跨列/跨行布局   |
| `<meter>` / `<progress>`      | 数值可视化      |
| `<ruby> / <rt> / <rp>`        | 注音增强        |
| `<details>` + `<summary>`     | 展示说明        |
| JavaScript 交互               | 搜索 + 排序功能 |