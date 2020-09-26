# docsify 指南

## 环境

建议使用nvm进行node版本管理. 先去https://nodejs.org/en/ 下载稳定版本node，再去 https://github.com/coreybutler/nvm-windows 下载最新版nvm，安装时指定nodejs路径.

```bash
nvm ls # 查看安装的npm版本
nvm use 8.11.3 # 切换node 8.11.3版本
nvm install 6 # 安装6的最新版本
nvm use 6.0.0  # 使用旧版本6.0.0
nvm alias default <version>  # 如： nvm alias default v11.1.0

# 全局安装 docsify-cli
npm i docsify-cli -g
```

## 使用

### 初始化

生成三个文件.

```bash
docsify init ./docs
```

- `index.html`：入口文件
- `README.md`：将作为主页渲染
- `.nojekyll`：阻止 Github Pages 忽略以下划线开头的文件

### 启动本地服务器

```bash
docsify serve docs
```

### 路由与文件夹

```shell
docs/README.md        => http://domain.com
docs/guide.md         => http://domain.com/guide
docs/zh-cn/README.md  => http://domain.com/zh-cn/
docs/zh-cn/guide.md   => http://domain.com/zh-cn/guide
```

### 导航栏

即右上角的顶部导航条，可以简单的直接在index.html中的body加.

```html
<body>
  <nav>
    <a href="#/">LeetCode 题解</a>
    <a href="http://jalan.space" target="_blank">我的博客</a>
  </nav>
  <div id="app"></div>
</body>
```

也可以先配置loadNavbar为true

```html
<script>
  window.$docsify = {
    loadNavbar: true
  }
</script>
<script src="//unpkg.com/docsify"></script>
```

创建`_navbar.md` 文，如

```markdown
* 导航1
    * [子导航](nav1/child/)
* [导航2](nav2/)
```



### 侧边栏

默认情况下，侧边栏会根据当前文章的标题生成目录. 但通常情况下，我们会通过markdown配置.

```html
<script>
  window.$docsify = {
    loadSidebar: true
  }
</script>
<script src="//unpkg.com/docsify"></script>
```

创建`_sidebar.md`，然后指定文件路径即可.

### coverpage

创建`_coverpage.md`，作为主页. 先开启`coverpage`.

```html
<script>
  window.$docsify = {
      coverpage: true,
  }
</script>
<script src="//unpkg.com/docsify"></script>
```

```markdown
![logo](assets/favicon.png)

# docsify 指南

> 🍀Docsify: A magical documentation site generator.

* 优雅
* 高效
* 敏捷

[GitHub](https://github.com/docsifyjs/docsify)
[演示地址](https://docsify.js.org/#/)

![color](#f0f0f0)
```