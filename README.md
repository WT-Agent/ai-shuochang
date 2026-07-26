<div align="center">

# [网腾无限AI - 说唱押韵与 Rap 词曲填词专家]

**[一个支持说唱黑胶唱片打卡与五种特色说唱流派的说唱押韵与 Rap 词曲填词工具，具备深色玻璃拟态自适应交互与微信端 H5 体验]**

[Vue 3] · [TypeScript] · [Vite] · [Vanilla CSS] · [开源协议 MIT]

[![GitHub stars](https://img.shields.io/github/stars/WT-Agent/ai-shuochang?style=social)](https://github.com/WT-Agent/ai-shuochang)
[![GitHub license](https://img.shields.io/github/license/WT-Agent/ai-shuochang)](https://github.com/WT-Agent/ai-shuochang/blob/main/LICENSE)

[在线演示](#在线演示) · [快速启动](#快速启动) · [参与贡献](#参与贡献) · [支持一下](#支持一下)

</div>

## 关于我们

团队成员均来自 C9 等顶尖学府，在字节、腾讯、阿里的工程师组成，全职创业研发开源 AI 应用产品，让所有人感受 AI 的魅力。

本项目旨在为 Old School、国风 Trap、Melodic 说唱、快嘴切拍及 Battle 爆点说唱群体提供高品质的说唱押韵与 Rap 词曲填词服务。用户只需输入说唱主题与核心金句，AI 即可根据多维科学度看板自动输出 Intro & Beat 节奏定位、Verse 核心段落（带双押/三押标注）、Catchy Hook 唱腔与副歌及 Punchline 金句与切拍 Break。页面内置了支持 Hip-Hop DJ 搓碟音效的“黑胶唱片”印章，协助创作者在 Rap 填词创作中快速完成韵脚对齐与歌曲落地。

**我们不搞概念，不卖课，只写能跑起来的代码。**

欢迎 Star、Fork、提 Issue，一起让这个项目变得更好用。

核心特性：
- **极简自适应交互**：提供毛玻璃质感的深色玻璃拟态自适应 Web 界面，高度适配移动端 H5 微信浏览器与 PC 体验。
- **说唱黑胶唱片打卡印章 (Hip-Hop Scratch Stamp)**：基于前端 Web Audio API 动态合成 Hip-Hop DJ 搓碟音效，点击印章即可累积说唱填词打卡次数并伴随渐隐上升动画。
- **五大说唱流派**：
  - **经典炸场 Old School 与硬核双押流**：重鼓 BoomBap，多重双押三押，强调叙事诗意。
  - **国风 Trap 与意象诗化流**：五声音阶，融入古风意象与典故，重低音 808 碰撞古典韵律。
  - **情感 Melody & 抒情 Hook 甜说唱流**：R&B 旋律说唱，抒情感满载，搭配洗脑 Hook。
  - **极速快嘴 Fast Flow 与切拍怪兽流**：三连音 triplets，快嘴快语，切拍变速。
  - **现场 Battle 与 Punchline 爆点流**：双关梗、谐音梗与高能量炸场。
- **AI 说唱词曲质量看板**：自动提取 AI 回复中的共识数据，以简洁的单轨进度条在前端直观展示切拍节奏感、双押三押密度、金句炸场度、叙事共鸣度及 Hook旋律上头度。
- **演示案例与分享卡片**：内置 30 条不同主题的精选说唱填词精彩演示样例，并支持一键卡片化截图分享。
- **一键零成本部署**：纯前端静态网页结构，支持零成本部署于 Vercel、GitHub Pages 或 CDN/OSS 静态托管服务。
- **安全开发代理**：本地开发支持使用个人 API 密钥发起代理请求，密钥由 Vite 服务器中转，无需担心前端泄露。
- **裂变解锁与留存**：内置微信朋友圈扫码分享拦截与额度重置机制，提升流量转化与留存。

## 快速启动

### 1. 克隆项目
```bash
git clone https://github.com/WT-Agent/ai-shuochang.git
cd ai-shuochang
```

### 2. 安装依赖
项目强制使用 pnpm 作为包管理器：
```bash
pnpm install
```

### 3. 配置本地开发环境变量
复制并修改环境变量配置文件：
```bash
cp .env.example .env
```
根据微应用的功能类型，在 `.env` 中配置您的开发者密钥：
- `DEEPSEEK_API_KEY`: 您的 DeepSeek 开发者 API 密钥（用于文本生成任务）
- `DASHSCOPE_API_KEY`: 您的通义千问/通义万相开发者 API 密钥（用于多模态与生图任务）

### 4. 启动本地开发服务
```bash
pnpm dev
```
启动成功后在浏览器访问控制台输出的地址即可。

### 5. 生产构建打包
```bash
pnpm build
```
打包后生成的 `dist` 目录即为纯静态网页资源，可直接上传部署。

## 脚手架集成说明

本模板由私有总控仓库 `ai.wuxian.xyz` 中的 `@wuxian/cli` 脚手架统一管理，支持以下批量运维操作：

### 初始化或更新单个子项目

```bash
node bin/cli.js ai-shuochang
```

脚手架将自动：
1. 读取子仓库的 `README.md` 首行作为 Prompt 主题。
2. 注入 Vue 3 静态页面结构及标准配置文件。
3. 保留原有的 `.git` 配置与 `README.md`，不覆盖个性化内容。

### 批量同步所有子项目

```bash
node bin/cli.js all
```

将模板 the latest 变更（如 SSO 逻辑、额度控制）一键同步至全部 31 个子项目。

### Agent 配置维护接口

```bash
# 读取子项目配置
node bin/cli.js get ai-shuochang

# 写入/更新配置（支持热更新 prompt、model、title、temperature 等）
node bin/cli.js set ai-shuochang prompt "你是一位资深说唱制作人、地下 Cypher 押韵大师..."
node bin/cli.js set ai-shuochang model deepseek-chat
```

## 联系方式

- GitHub Issues: [提交反馈](https://github.com/WT-Agent/ai-shuochang/issues)
- 邮箱: us@wuxian.xyz

## 打赏支持

如果本项目对您有帮助，欢迎请作者喝杯咖啡。您的支持是持续维护与更新的动力。

<div align="center">

**微信支付** | **支付宝**
:---:|:---:
<img src="./asset/tenpay.png" width="200" alt="微信支付"> | <img src="./asset/alipay.png" width="200" alt="支付宝">

</div>

## 版权与许可

本项目基于 MIT License 开源协议。

Copyright (c) 2026. All rights reserved.
