# 天气特效系统

基于 Minecraft 风格的纯 CSS 天气特效，经过增强以支持更多天气类型和动态速度控制。

## 功能特性

### 多种天气类型
- **晴天** (clear) - 阳光明媚
- **小雨** (rain-light) - 毛毛雨，慢速下落
- **阵雨** (rain-shower) - 骤雨，中速下落
- **细雨** (rain-drizzle) - 微雨，较慢下落
- **阴雨** (rain-cloudy) - 阴天小雨
- **小雪** (snow-light) - 飘雪，缓慢飘落
- **飞雪** (snow-float) - 雪花飘舞
- **大雪** (snow-heavy) - 暴雪，快速飘落
- **雪舞** (snow-dance) - 漫天飞雪，超快速度
- **雷暴** (rain-storm) - 强对流天气，超快下落
- **暴雨** (rain-heavy) - 特大暴雨，快速密集

### 动态速度控制
每种天气类型都有独特的动画速度：
- 小雨：3s / 2.5s
- 阵雨：1.5s / 1s
- 细雨：4s / 3s
- 阴雨：2.5s / 2s
- 雷暴：0.8s / 0.6s（最快）
- 暴雨：1s / 0.8s
- 小雪：8s / 6s
- 飞雪：6s / 4.5s
- 大雪：4s / 3s
- 雪舞：3s / 2s

### 智能天气系统
- 基于日期的种子生成，同一天天气相同
- 模仿河南气候特点
  - 春季（3-5月）：晴天为主，偶有小雨
  - 夏季（6-8月）：多雨，有雷暴和暴雨
  - 秋季（9-11月）：晴朗为主，少量降雨
  - 冬季（12-2月）：晴朗，偶有降雪
- 8% 概率出现极端天气（雷暴、暴雨、大雪）

### 用户控制
- 天气特效开关，可随时开启/关闭
- 状态保存到 localStorage
- 刷新页面后保持设置

## 使用方法

### 1. 引入 CSS 文件
在 HTML `<head>` 标签中添加：
```html
<link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/gh/Thexiaoyuqaq/weather.css@master/weather.min.css">
```

### 2. 应用天气效果
在任意容器上添加 `weather` 类和天气类型类：
```html
<!-- 下雨 -->
<body class="weather rain-light">
<body class="weather rain-shower">
<body class="weather rain-storm">

<!-- 下雪 -->
<body class="weather snow-light">
<body class="weather snow-heavy">
<body class="weather snow-dance">

<!-- 晴天 -->
<body class="weather clear">
```

### 3. 关闭天气特效
```html
<body class="weather-effect-disabled">
```

## 技术细节

### CSS 动画原理
- 使用 `::before` 和 `::after` 伪元素创建双层效果
- 通过 `background-image` 使用 base64 编码的雨滴/雪花图片
- `animation-duration` 控制下落速度
- `transform: rotate(10deg)` 模拟斜向落下的效果

### 性能优化
- 使用 `pointer-events: none` 避免干扰交互
- `image-rendering: pixelated` 保持像素风格
- 通过 CSS 类控制显示/隐藏，无需重新加载

### 浏览器兼容性
- 支持现代浏览器
- 包含 `-webkit-` 前缀以支持 Safari
- 使用标准 CSS 动画 API

## 文件说明

- `weather.css` - 增强版天气特效，支持多种天气类型
- `README.md` - 本文档

## 示例效果

- **小雨**：温和的雨滴，适合阅读
- **雷暴**：快速密集的雨滴，营造紧张感
- **小雪**：缓慢飘落的雪花，浪漫氛围
- **雪舞**：快速飞舞的雪花，动感十足

## 注意事项

1. 天气效果会覆盖整个视口
2. 建议在深色背景下使用以获得最佳视觉效果
3. 可以通过 CSS 变量自定义动画速度
4. 关闭天气特效时，所有动画都会停止

## 许可证

MIT License - 基于原始 weather.css 修改
