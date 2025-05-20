# HTML5快速入门-常用标签及其属性(三)

## 音视频标签

### 🎧 `<audio>` 标签 — 插入音频

**基本语法**

```html
<audio controls src="路径/文件名.mp3">
  亲爱的，您的浏览器不支持 audio 标签，请升级您的浏览器哟 ^_^
</audio>

```

| 属性       | 描述                      |
| ---------- | ------------------------- |
| `controls` | 显示播放控件              |
| `src`      | 音频文件路径              |
| `autoplay` | 自动播放（加载即播放）    |
| `loop`     | 播放结束后自动重新播放    |
| `muted`    | 静音播放（配合 autoplay） |

### 使用 `<source>` 提供多格式备选（提高兼容性）

```html
<audio controls autoplay loop>
  <source src="audio/不错哟.mp3" type="audio/mpeg" />
  <source src="audio/不错哟.ogg" type="audio/ogg" />
  <source src="audio/不错哟.wav" type="audio/wav" />
  抱歉，您的浏览器不支持 audio 标签，请升级您的浏览器哟 ^_^
</audio>

```

🧪 **浏览器支持自动选择支持的格式**，顺序优先使用第一个成功加载的音频。

### 🎥 `<video>` 标签 — 插入视频

```html
<video controls width="500">
  <source src="video/1.mp4" type="video/mp4" />
  <source src="video/1.webm" type="video/webm" />
  <source src="video/1.ogv" type="video/ogv" />
  亲爱的，您的浏览器不支持 video 标签，请升级您的浏览器哟 ^_^
</video>

```



| 属性       | 描述                     |
| ---------- | ------------------------ |
| `controls` | 显示播放控件             |
| `width`    | 视频宽度                 |
| `autoplay` | 自动播放（需静音配合）   |
| `loop`     | 循环播放                 |
| `muted`    | 静音播放（支持自动播放） |
| `poster`   | 视频封面图路径           |

### 🎵 常见媒体格式与 MIME 类型

| 媒体类型 | 格式    | MIME Type    | 说明                       |
| -------- | ------- | ------------ | -------------------------- |
| 音频     | `.mp3`  | `audio/mpeg` | 通用压缩格式，支持广泛     |
| 音频     | `.ogg`  | `audio/ogg`  | 免费格式，兼容性稍差       |
| 音频     | `.wav`  | `audio/wav`  | 高保真音频，体积较大       |
| 视频     | `.mp4`  | `video/mp4`  | 推荐使用，兼容性最佳       |
| 视频     | `.webm` | `video/webm` | 开源格式，体积较小         |
| 视频     | `.ogv`  | `video/ogv`  | 基于 Ogg 的视频格式        |
| 视频     | `.avi`  | `video/avi`  | 较老格式，部分浏览器不支持 |

### 🧠 实用建议

✅ 为确保所有用户都能播放音视频，建议使用 `<source>` 标签定义多种格式。
 ✅ 若需静音自动播放，需设置 `muted autoplay`（Chrome/Safari 要求）。
 ✅ 可搭配 `preload`, `poster`（封面图）进行更优加载体验。

1、音频标签：音视频相关API
2、语义化标签：