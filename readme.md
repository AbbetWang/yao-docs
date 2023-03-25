# 开发过程中的一些问题与技巧收集

收集的一些与 Yao 开发相关的文档，文档使用`vitepress`制作，并自动发布到`github page`上。直接访问地址：

[https://wwsheng009.github.io/yao-docs](https://wwsheng009.github.io/yao-docs)

## 文档编写与构建

文档使用`markdown`格式编写。存放目录`/docs`。

在文档发布之前先本地构建一次检查有没有错误。

```sh
pnpm run build
```

## `vitepress`配置文件自动生成

`vitepress`配置文件`/docs/.vitepress/sidebar.ts`使用脚本`/src/generate_config.js`根据目录结构自动生成。

监听文件变更，自动生成`vitepress`配置文件

```sh
node src/index.js
```

## `index.md`文件的更新

当一个目录中新增/修改/删除文件后，索引文件`index.md`并不会自动的更新。

当运行脚本`pnpm run build`或是`pnpm run generate`后，会生成一个`_index.md`，这个新文件会包含最新的所有的文件列表。需要手动合并变更。
