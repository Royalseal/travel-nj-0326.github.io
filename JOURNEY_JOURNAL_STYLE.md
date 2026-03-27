# 「Journey Journal」旅行日志风格 设计规范

> 用于生成旅行行程展示页面的统一设计风格

---

## 1. 设计理念

一种精致、现代的旅行行程展示风格，融合东方美学与现代设计。参考旅行杂志的版式设计，通过优雅的排版和细腻的动画，打造清新舒适的阅读体验。

---

## 2. 视觉特点

| 特点 | 说明 |
|------|------|
| 风格 | 精致旅行杂志风格 |
| 布局 | 卡片式 + 手风琴展开效果 |
| 动画 | 页面滚动淡入、展开收起过渡 |
| 适配 | 完全响应式（手机/平板/桌面） |

---

## 3. 配色方案

### 主色调

```css
--color-bg: #FAF8F5;           /* 页面背景 - 米白色 */
--color-bg-card: #FFFFFF;     /* 卡片背景 */
--color-text: #2C2C2C;        /* 主文字 */
--color-text-light: #6B6B6B;  /* 次要文字 */
```

### 强调色

```css
--color-accent: #C45A3B;       /* 赭石红 - 主要强调色 */
--color-accent-light: #E8D5CE;

--color-sage: #7A8B6E;        /* 鼠尾草绿 - 交通/巴士 */
--color-sage-light: #E8EDE5;

--color-gold: #B8956E;        /* 金棕色 - 高铁/火车 */
--color-gold-light: #F5EFE5;

--color-ocean: #4A7C8C;       /* 海洋蓝 - 航班 */
--color-ocean-light: #E3EEF2;
```

---

## 4. 字体

```html
<link href="https://fonts.googleapis.com/css2?family=Noto+Serif+SC:wght@400;600;700&family=Noto+Sans+SC:wght@300;400;500;600&display=swap" rel="stylesheet">
```

| 用途 | 字体 | 字重 |
|------|------|------|
| 标题 | Noto Serif SC | 600 / 700 |
| 日期标签 | Noto Serif SC | 600 |
| 正文 | Noto Sans SC | 300 / 400 / 500 |

---

## 5. 页面结构

### 5.1 Hero 头部区域

- 顶部徽章（Travel Itinerary）
- 主标题（目的地名称）
- 副标题（行程天数 + 日期）
- 元信息（日期、人数、城市）

### 5.2 行程卡片区

每个 Day 为一个可展开/收起的卡片：
- 左侧：DAY XX + 行程标题
- 右侧：展开/收起箭头按钮

### 5.3 内容块类型

每张卡片内包含若干 info-block，用左侧彩色条区分类型：

| 类型 | 类名 | 背景色 | 强调色 |
|------|------|--------|--------|
| 高铁/火车 | train | #F5EFE5 | #B8956E |
| 市内交通 | transport | #E8EDE5 | #7A8B6E |
| 酒店 | hotel | #F5F0EB | #8B7355 |
| 美食 | food | #FEF0E8 | #D4573B |
| 景点 | attraction | #E8D5CE | #C45A3B |
| 航班 | flight | #E3EEF2 | #4A7C8C |

### 5.4 Footer

底部祝福语 + 图标

---

## 6. 交互行为

### 手风琴效果
- 点击某一天的标题展开详情
- 展开时自动折叠其他天
- 再次点击同一标题可收起

### 滚动动画
- 页面滚动时卡片依次淡入
- 动画延迟逐个递增

---

## 7. 响应式断点

```css
/* 移动端 < 768px */
- Hero 区域减小内边距
- 元信息垂直排列
- 卡片内容区域自适应
```

---

## 8. 模板代码

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>行程名称</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Serif+SC:wght@400;600;700&family=Noto+Sans+SC:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        /* 见下方 CSS 部分 */
    </style>
</head>
<body>
    <!-- Hero -->
    <header class="hero">...</header>

    <!-- Main -->
    <main class="container">
        <article class="day-card">
            <div class="day-header">...</div>
            <div class="day-content">
                <div class="day-body">
                    <div class="info-block train">...</div>
                    <div class="info-block transport">...</div>
                    <div class="info-block hotel">...</div>
                    <div class="info-block food">...</div>
                    <div class="info-block attraction">...</div>
                </div>
            </div>
        </article>
    </main>

    <!-- Footer -->
    <footer class="footer">...</footer>

    <script>
        // 手风琴 + 滚动动画
    </script>
</body>
</html>
```

---

## 9. 使用说明

1. 将行程内容填入对应位置
2. 根据内容类型选择合适的 info-block 类名
3. 保留地图链接（target="_blank"）
4. 推送到 GitHub Pages 即可访问

---

*文档版本：v1.0*
*最后更新：2026-03-27*