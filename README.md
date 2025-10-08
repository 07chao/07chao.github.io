# 开发者作品集 ⚡️ [![GitHub](https://img.shields.io/github/license/saadpasta/developer-portfolio?color=blue)](https://github.com/saadpasta/developerFolio/blob/master/LICENSE) [![GitHub stars](https://img.shields.io/github/stars/saadpasta/developerFolio)](https://github.com/saadpasta/developerFolio/stargazers)  [![All Contributors](https://img.shields.io/badge/all_contributors-4-orange.svg?style=flat-square)](#contributors)

## 简洁、美观且响应式的开发者作品集模板！


<p align="center">
  <kbd>
<img src="https://user-images.githubusercontent.com/53429438/106779355-e9cd9e80-666c-11eb-9417-8a4b54441bc6.gif"></img>
  </kbd>
</p>


只需修改 `src/portfolio.js` 即可获得您的个人作品集。通过在 `src/_globalColor.scss` 文件中使用您自己的配色方案来自定义作品集主题。您可以随意使用它，或者根据需要进行个性化定制。

如果您想**贡献**并让这个项目对其他用户更好，请查看 [Issues](https://github.com/saadpasta/developerFolio/issues)。

为您的作品集分支创建了令人惊叹的内容并想分享它？欢迎提交 [pull request](https://github.com/saadpasta/developerFolio/pulls)。

## 目录
- [作品集板块](#作品集板块)
- [开始使用](#开始使用)
- [使用方法](#使用方法)
- [链接到 GitHub](#链接到-github)
- [博客板块链接到 Medium](#博客板块链接到-medium)
- [根据需要更改和自定义每个板块](#根据需要更改和自定义每个板块)
- [部署](#部署)
- [使用的技术](#使用的技术)
- [插图](#插图)
- [未来计划](#未来计划)
- [贡献者](#项目维护者)

## 作品集板块
✔️ 个人简介和关于我\
✔️ 技能\
✔️ 教育经历\
✔️ 工作经验\
✔️ 与 GitHub 连接的开源项目\
✔️ 大型项目\
✔️ 成就和认证 🏆\
✔️ 博客\
✔️ 演讲\
✔️ 播客\
✔️ 联系我\
✔️ Twitter 时间线\
✔️ GitHub 个人资料

查看在线示例，**[点击这里](https://developerfolio.js.org/)**。


## 开始使用

这些说明将帮助您在本地计算机上获取项目副本，用于开发和测试目的。

您需要在计算机上安装 [Git](https://git-scm.com) 和 [Node.js](https://nodejs.org/en/download/)（包含 [npm](http://npmjs.com)）或者使用 [Docker](https://www.docker.com/products/docker-desktop)。

```
node@v10.16.0 或更高版本
npm@6.9.0 或更高版本
git@2.17.1 或更高版本
```
### Docker 命令

```
1) 构建镜像 : docker build -t developerfolio:latest .
2) 运行镜像: docker run -t -p 3000:3000 developerfolio:latest
```


## 使用方法

在命令行中，克隆并运行 developerFolio：

```bash
# 克隆此仓库
git clone https://github.com/saadpasta/developerFolio.git

# 进入仓库目录
cd developerFolio

# 设置默认环境变量

# Linux 系统
cp env.example .env
# Windows 系统
copy env.example .env

# 安装依赖项
npm install

# 启动本地开发服务器
npm start
```

## 链接到 GitHub

按照这些 [说明](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token#creating-a-personal-access-token-classic) 生成经典的 GitHub 个人访问令牌（确保不选择任何作用域，只生成一个简单令牌）。如果您使用 [GitHub Actions](#配置-github-actions-推荐) 部署作品集，可以跳过此部分。

1. 在项目根目录下创建一个名为 .env 的文件（如果在 [使用方法](#使用方法) 部分尚未完成）

注意：强烈建议在部署作品集之前配置环境变量，因为某些组件依赖于 API 数据。

```bash
- DeveloperFolio
  - node_modules
  - public
  - src
  - .env         <-- 在这里创建
  - env.example  <-- 这是基础文件
  - .gitignore
  - package-lock.json
  - package.json
```

2. 在 .env 文件中，添加键 `REACT_APP_GITHUB_TOKEN` 并像这样分配您的 GitHub 令牌，同时添加您的用户名作为 `GITHUB_USERNAME`

```env
// .env
REACT_APP_GITHUB_TOKEN = "YOUR GITHUB TOKEN HERE"
GITHUB_USERNAME = "YOUR GITHUB USERNAME"
USE_GITHUB_DATA = "true"
```

设置 `showGithubProfile` 为 true 或 false 以显示使用 GitHub 的联系人资料，默认为 false。

**警告：** 将您的令牌视为密码并保持机密。在使用 API 时，将令牌作为环境变量使用，而不是硬编码到程序中。

注意：开源项目部分仅显示您 GitHub 上的固定项目。
如果您看到如下所示的内容，请按照这些 [说明](https://docs.github.com/en/enterprise/2.13/user/articles/pinning-items-to-your-profile) 操作。

![ERROR](https://i.imgur.com/Hj6mu1K.png)

如果上述解决方案仍然无效，请访问 [wiki 页面](https://github.com/saadpasta/developerFolio/wiki/Github-Setup-For-Open-Source-Projects)。

## 博客板块链接到 Medium

您可以选择将博客板块链接到您的 Medium 用户账户：

* 在 .env 文件中，添加键 `MEDIUM_USERNAME` 并分配您的 Medium 用户名

```env
// .env
MEDIUM_USERNAME = "YOUR MEDIUM USERNAME"
```

* 对于 Github Action，在 `.github/workflows/deploy.yml` 中更改环境变量 `MEDIUM_USERNAME`

在 portfolio.js 中设置 `displayMediumBlogs` 为 true 或 false 以显示获取的 Medium 博客，默认为 true。

## 根据需要更改和自定义每个板块

#### 在 `/src/portfolio.js` 中个性化页面内容并根据需要进行修改。您还需要修改 `index.html` 以更改标题和元数据，为您的个人作品集提供准确的 SEO。

```javascript
/* 修改此文件以获取您的个人作品集 */

const greeting = {
  /* 您的摘要和问候板块 */
  title: "Hi all I'm 许致诚",
  subTitle: emoji("A passionate Full Stack Software Developer 🚀"),
  resumeLink: "https://drive.google.com/file/d/1ofFdKF_mqscH8WvXkSObnVvC9kK7Ldlu/view?usp=sharing"
};

const socialMediaLinks = {
  /* 您的社交媒体链接 */
  github: "https://github.com/07chao",
  linkedin: "https://www.linkedin.com/",
  gmail: "zhichengxu07@gmail.com",
  gitlab: "https://gitlab.com/",
  facebook: "https://www.facebook.com/"
};


const skillsSection = { .... }

const techStack = { .... }

const workExperience = { .... }

const openSource = { .... }

const bigProjects = { .... }

const achievementSection = { .... }

const blogSection = { .... }

const contactInfo = { .... }

const twitterDetails = { ... }

```
#### 简历上传
要上传您自己的简历，只需将 PDF 文件上传到 `src/containers/greeting/resume` 并将 PDF 文件重命名为 `resume.pdf`。

#### 使用表情符号

要在 `Portfolio.js` 的文本中添加表情符号 😃，请使用 `emoji()` 函数并将您需要的文本作为参数传递。这将有助于保持表情符号在不同浏览器和平台上的兼容性。

#### 自定义 Lottie 动画

您可以从 [此类](https://lottiefiles.com/) 网站选择 Lottie 并以 json 格式下载。在 `src/assets/lottie` 中，用相同文件名替换您想要修改的 Lottie json 文件。如果您想更改 Lottie 选项，请转到 `src/components/displayLottie/DisplayLottie.js` 并更改 `defaultOptions` 对象，您可以参考 [lottie-react 文档](https://www.npmjs.com/package/lottie-react) 获取有关 `defaultOptions` 对象的更多信息。

#### 在您的页面中添加 Twitter 时间线
在 `portfolio.js` 中插入您的 Twitter 用户名以在您的页面上显示您的最近活动。

```javascript
const twitterDetails = {
  userName : "Your Twitter Username"
};
```
注意：添加用户名时不要使用 `@` 符号。

## 部署
完成设置后，您应该将网站托管到在线平台。
我们强烈建议您阅读 React 的 [在 GitHub Pages 上部署](https://create-react-app.dev/docs/deployment/#github-pages) 文档。

#### 配置 GitHub Actions (推荐)
首先，您应该为您使用的仓库启用 GitHub Actions。

GitHub 上的个人资料和仓库信息仅在部署时创建，如果需要更新这些信息，则需要重新部署网站。因此，设置了一个可配置的 [CRON 作业](https://docs.github.com/en/actions/reference/events-that-trigger-workflows#scheduled-events)，每周部署一次您的网站，这样一旦您在 GitHub 上更新了个人资料，就会显示在您的作品集中。您也可以使用 `workflow_dispatch` 事件手动触发，参见 [此指南](https://github.blog/changelog/2020-07-06-github-actions-manual-triggers-with-workflow_dispatch) 了解如何操作。

- 完成配置后，我们强烈建议您阅读 [GitHub Actions 配置工作流](https://docs.github.com/en/actions/configuring-and-managing-workflows/configuring-a-workflow) 文档。

#### 部署到 GitHub Pages

本节将指导您将作品集部署到 GitHub Pages。

- 导航到 `package.json`，在 `homepage` 变量中输入您的域名，而不是 `https://developerfolio.js.org/`。例如，如果希望您的网站为 `https://<your-username>.github.io/developerFolio`，请将其添加到 `package.json` 的 homepage 部分。

- 简而言之，您也可以在 `package.json` 中添加 `/devloperFolio`，因为两者完全相同。这样做会告诉 `create-react-app` 相应地添加路径资源。

- 可选地，配置域名。您可以通过在 `public/` 文件夹中添加 `CNAME` 文件来配置 GitHub Pages 的自定义域名。

- 按照官方 CRA 文档中的指南设置 GitHub Pages [这里](https://create-react-app.dev/docs/deployment/#github-pages)。

#### 部署到 Netlify

您也可以通过链接自己的仓库直接在 Netlify 上托管。

[![Deploy To Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/saadpasta/developerFolio)

更多信息，请阅读 [在 Netlify 上托管](https://create-react-app.dev/docs/deployment/#netlify)。


## 使用的技术

- [React](https://reactjs.org/)
- [graphql](https://graphql.org/)
- [apollo-boost](https://www.apollographql.com/docs/react/get-started/)
- [react-twitter-embed](https://github.com/saurabhnemade/react-twitter-embed)
- [react-easy-emoji](https://github.com/appfigures/react-easy-emoji)
- [react-headroom](https://github.com/KyleAMathews/react-headroom)
- [color-thief](https://github.com/lokesh/color-thief)

## 插图
- [UnDraw](https://undraw.co/illustrations)
- [Lottie by Oblikweare](https://lottiefiles.com/oblikweare)


    </tr>
  </tbody>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

---
