# airdb.bio — 生物圈

> bio = 生命 → 生物行业 · 个人生平。
> airdb.space 仰望星辰大海，airdb.bio 俯身凝视生命。

## 1. 定位

以希腊词根 **bio-（βίος，生命）** 为整站叙事骨架，对应 .bio 域名的两层主流含义：

| 板块 | 词根映射 | 内容锚点 | 规划路由 |
|------|----------|----------|----------|
| 生命科学 | bio·logy | 生物医药、基因、微生物、合成生物学 | `/science` |
| 生平印记 | bio·graphy | 个人名片站、link-in-bio 聚合页（与 airdb.id 呼应） | `/me` |

## 2. 站点结构

```
src/
├── layouts/Layout.astro          # SEO / canonical / hreflang / 页头页脚
├── components/
│   ├── SporeField.astro          # Canvas 孢子粒子（呼吸明灭 · 随主题变色）
│   └── pages/HomePage.astro      # 首页：词根轮换 Hero + 词根考 + 三大板块 + 站群 + 路线图
└── pages/
    ├── index.astro               # 中文（默认）
    └── en/index.astro            # English
```

视觉：浅色「叶绿纸本」/ 深色「夜林荧光」双主题（`prefers-color-scheme` 自动切换）；
Fraunces 衬线（英文展示）+ IBM Plex Sans/Mono；动效遵循 `prefers-reduced-motion`。

## 3. 本地开发

```sh
make install   # pnpm install --frozen-lockfile
make run       # pnpm dev
make build     # pnpm build
```

## 4. 技术方案

| 项 | 选型 | 理由 |
|----|------|------|
| 框架 | **Astro**（静态优先，Islands 按需交互） | 内容型官网首选：零 JS 起步、性能极佳、SEO 友好 |
| 包管理 | pnpm | 已定 |
| 构建/任务 | Makefile（`make install / run / build`） | 已定，保持现状 |
| 样式 | Tailwind CSS + 少量自定义 CSS（动效） | 快速迭代 + 设计一致性 |
| 内容 | Astro Content Collections（Markdown/MDX） | 时间线条目、专题文章都以内容驱动，便于持续更新 |
| 交互点缀 | 原生 Canvas 星空 / 滚动动效（IntersectionObserver） | 不引入重型 3D 依赖，保证加载速度 |
| 部署 | 静态托管（Cloudflare Pages / Vercel / GitHub Pages 任一） | 待定 |

