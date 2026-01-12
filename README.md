# ShipAny Template Two

## Getting Started

read [ShipAny Document](https://shipany.ai/docs/quick-start) to start your AI SaaS project.

## Buy Templates

check [ShipAny Templates](https://shipany.ai/templates) to buy Business Templates.

## Feedback

submit your feedbacks on [Github Issues](https://github.com/shipanyai/shipany-template-two/issues)

## LICENSE

!!! Please do not publicly release ShipAny's Code. Illegal use will be prosecuted

[ShipAny LICENSE](./LICENSE)


1.落地页配置改成只渲染 hero，
也就是 show_sections 只保留 hero。现在首页只会加载 hero 区块，其它区块被过滤；Header/Footer 仍由布局渲染。

修改位置：index.json
修改位置：index.json
过滤逻辑在：dynamic-page.tsx
头尾布局在：landing.tsx 和 layout.tsx

配置说明
我为您创建了 
src/themes/promp/pages/dynamic-page.tsx
 文件。这个文件的工作原理是：

定义了一个 ALLOWED_SECTIONS 数组，目前只包含 'hero'
在渲染页面时，会检查每个 section 是否在允许列表中
只有在列表中的 section 才会被渲染，其他全部被过滤
使用方法：

将 
.env.development
 中的 NEXT_PUBLIC_THEME 改为 "promp"：
NEXT_PUBLIC_THEME = "promp"
如果后续想添加更多区块，只需修改 
dynamic-page.tsx
 中的 ALLOWED_SECTIONS 数组：
typescript
const ALLOWED_SECTIONS = ['hero', 'logos', 'cta'];  // 添加更多
这样，当您切换到 promp 主题时，首页只会显示 Hero 区块。而语言包中的其他配置保持不变，方便您后续切换回 default 主题时恢复完整页面。

['hero', 'faq', 'cta','features','logos','introduce','benefits','usage','stats','testimonials'];


2.样式
https://tweakcn.com/editor/theme
code -> copy
位置：全部替换 src/config/styles/theme.css

3.logo
https://www.design.com/logo-maker
替换 puclic/logo.png  favicon.ico

4.修改项目名称
# app
NEXT_PUBLIC_APP_URL = "http://localhost:3000"
NEXT_PUBLIC_APP_NAME = "VideoPrompThub"

5.站点地图
puclic/sitemap.xml

  <url>
    <loc>https://videoprompthub.com/</loc>
    <lastmod>2026-01-11T10:00:00+00:00</lastmod>
  </url>
  <url>
    <loc>https://videoprompthub.com/blog</loc>
    <lastmod>2026-01-11T10:00:00+00:00</lastmod>
  </url>
  <url>
    <loc>https://videoprompthub.com/showcases</loc>
    <lastmod>2026-01-11T10:00:00+00:00</lastmod>

6.网站协议


7.修改落地页内容
src/config/locale/messages/zh/landing.json
src/config/locale/messages/en/landing.json  

landing.json
 
landing.json
 
请根据我的新项目，修改这个文件，我的项目名称是VideoPrompThub，这是一个AI 视频提示词生成平台，可以体验各种AI功能。项目域名是:videoprompthub.com ,支持邮箱现在还没有

8.标题栏 价格、博客等功能

src/config/locale/messages/zh/landing.json
src/config/locale/messages/en/landing.json  
"nav": {
    //文件做了备份，为空是先隐藏掉
    },


    "show_sign": true, // 显示切换主题，亮色暗色
    "show_theme": true,// 显示语言切换按钮 中文 英文
    "show_locale": true,// 显示登录按钮


9.首页文案 隐藏这一行
src/config/locale/messages/zh/pages/index.json
999+ creators are using VideoPrompThub

"show_avatars": true,
去除tip
"tip": "🎁 Free trial for new users",

去除图片
"image": {
          "src": "/imgs/features/admin.png",
          "alt": "hero",
          "width": 1200,
          "height": 800
        },
        "image_invert": {
          "src": "/imgs/features/admin-dark.png",
          "alt": "hero",
          "width": 1200,
          "height": 800
        },

Footer 区域配置说明
在 
src/config/locale/messages/en/landing.json
 和 
zh/landing.json
 中的 footer 部分：

1. 导航链接（About, Resources, Friends）
位于第 54-106 行：

    "show_theme": false,
    "show_locale": false
Footer 区域配置说明
在 
src/config/locale/messages/en/landing.json
 和 
zh/landing.json
 中的 footer 部分：

1. 导航链接（About, Resources, Friends）
位于第 54-106 行：

json
"nav": {
  "items": [
    {
      "title": "About",         // 第一列标题
      "children": [...]         // 下面的链接
    },
    {
      "title": "Resources",     // 第二列标题
      "children": [...]
    },
    {
      "title": "Friends",       // 第三列标题
      "children": [...]
    }
  ]
}
2. 主题切换和语言切换按钮
位于第 142-143 行：

json
"show_theme": true,   // 主题切换（亮色/暗色）
"show_locale": true   // 语言切换


aitdk headings 关键词密度
pages/index.json
 中所有剩余的 ShipAny 引用：


请根据我的项目，修改common.json这个文件，我的项目名称叫VideoPrompThub，这是一个AI一站式生成平台，可以体验各种视频提示词，项目域名是：videoprompthub.com，支持邮箱是support@videoprompthub.com


10.关闭多语言中的中文
src/config/locale/index.ts

11.删除掉hero 上方的标题 "title": "🎉 VideoPrompThub is Live!",
src/config/locale/messages/en/pages/index.json

"announcement": {
          "badge": "New",
          "title": "🎉 VideoPrompThub is Live!",
          "url": "/pricing"
        },


{
            "title": "Read Document",
            "icon": "BookOpenText",
            "url": "/docs",
            "target": "_blank",
            "variant": "outline"
          }

11.背景图在哪里改、怎么换
你截图里首页（Landing 页）的背景图，是 Hero 区块的 background_image 控制的：

配置位置（首页）
src/config/locale/messages/en/pages/index.json
src/config/locale/messages/zh/pages/index.json
这两个文件里都有：

json
"background_image": {
  "src": "/imgs/bg/tree.jpg",
  "alt": "hero"
}