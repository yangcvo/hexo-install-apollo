![hexo-theme-apollo](https://cloud.githubusercontent.com/assets/9530963/13026956/08e76eca-d277-11e5-8bfc-2e80cea20a0d.png)

## 文档

- [中文文档](https://github.com/yangcvo/hexo-install-apollo/blob/master/doc%2Fdoc-zh.md)
- [Document](https://github.com/yangcvo/hexo-install-apollo/blob/master/doc%2Fdoc-en.md)

ps. hexo-theme-apollo 的定位是简洁和专注于内容，所以将不再接受新功能的 pull request，如果有新的想法，那将会是另一个主题。

ps. hexo-theme-apollo will no longer accept new features for focusing on content and keeping clean, so don't pull request. If there are new features in my mind, it will become a new theme.

## 安装

[![asciicast](https://asciinema.org/a/emrvroa9054hz6k8ise0uxh2u.png)](https://asciinema.org/a/emrvroa9054hz6k8ise0uxh2u)

``` bash
hexo init Blog 
cd Blog 
npm install
npm install --save hexo-renderer-jade hexo-generator-feed hexo-generator-sitemap hexo-browsersync hexo-generator-archive
git clone https://github.com/pinggod/hexo-theme-apollo.git themes/apollo
```

## 启用

修改 `_config.yml` 的 `theme` 配置项为 `apollo`:

```yaml
theme: apollo

# 在归档页面显示所有文章
# 需要上面安装的 hexo-generator-archive 插件支持
archive_generator:
    per_page: 0
    yearly: false
    monthly: false
    daily: false
```

## 更新

``` bash
cd themes/apollo 
git pull
```

### 主机替换更新

这里只需要git我这里的主题，然后执行hexo g 然后在提交hexo d 发布到github上面。
这里提交hexo g 如果会出现： `的ERROR Process failed: layout/_partial/.DS_Store`

 解决Hexo博客 ERROR Process failed: layout/_partial/.DS_Store问题来源
```
在用Hexo搭的博客在执行hexo g 的时候，会出现错误：

ERROR Process failed: layout/.DS_Store TypeError: Cannot read 
property 'compile' of undefined 还有

ERROR Process failed: layout/_partial/.DS_Store TypeError: Cannot 
read property 'compile' of undefined

虽然不影响生成文件与使用，但是一直error让人很不舒服；
.DS_Store是什么：

1、这种文件存在于众多的OS文件目录中，Finder自动隐藏它们，所以用户不会感到其存在。.DS_Store几乎存在于每个文件当中。它是Finder记录客户定制文件夹显示方式的一种元数据文件（metadata）用于控制一个文件夹的显示方式（列表、图标、分栏和CoverFlow）和背景图标等。 
2、与别人交换文件或做的网页需要上传的时候，最好把 .DS_Store 文件删除。
与.DS_Store相关的设置

禁止.DS_Store生成

defaults write com.apple.desktopservices DSDontWriteNetworkStores true
恢复.DS_Store生成

defaults delete com.apple.desktopservices DSDontWriteNetworkStores
直接解决的方法：

1、删除所有.DS_Store文件，在terminal中输入:

sudo find / -name ".DS_Store" -depth -exec rm {} \;

2、cd 进到你使用的theme对应的目录，再进到layout/和layout/_partial/下, 分别执行

rm .DS_Store
```

也可参考：http://blog.csdn.net/u014491743/article/details/51340609
这里我删除所有的.DS_store


## License

MIT
