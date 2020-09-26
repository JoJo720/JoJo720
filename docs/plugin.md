# 插件

## 代码高亮

* https://github.com/PrismJS/prism

在index.html中添加，是什么语言就添加什么js

```html
<script src="//unpkg.com/docsify"></script>
<script src="//unpkg.com/prismjs/components/prism-bash.js"></script>
<script src="//unpkg.com/prismjs/components/prism-php.js"></script>
<script src="//unpkg.com/prismjs/components/prism-python.js"></script>
```

## 全局搜索

```html
<script>
    window.$docsify = {
        search: {maxAge: 86400000, paths: 'auto', placeholder: {'/': '搜索'}, noData: {'/': '找不到结果'}, depth: 4}
    };
</script>
<script src="//cdn.staticfile.org/docsify/4.11.3/plugins/search.min.js"></script>
```
