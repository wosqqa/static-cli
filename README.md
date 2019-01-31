# MPA

基于 webpack 的多页面应用框架

## 使用说明

```bash
# 开发
npm run dev # 或 npm start
# 访问方式
# http://localhost:8888/index.html
# http://localhost:8888/about.html
# http://localhost:8888/contact.html

# 预发布（用于上测试服）打包
npm run pre

# 上线打包
npm run build
# 上线打包可视化分析
npm run builda

# 代码格式校验
npm run lint

# 代码格式自动修复
npm run fix
```

## 目录结构说明

```bash
.
├── .eslintrc.js  # eslint配置文件
├── .prettierrc.js  # prettier配置文件
├── build # webpack配置文件目录
│   ├── config.js
│   ├── webpack.common.js
│   ├── webpack.dev.js
│   └── webpack.prod.js
├── dist # 上线打包目录
├── pre # 预发布打包目录
└── src
    ├── api # 公共接口、日志处理目录（代码组织方式供参考）
    │   ├── config.js
    │   ├── data.js
    │   ├── index.js
    │   └── log.js
    ├── common  # 公共资源目录
    │   ├── css # 公共样式资源
    │   │   ├── _base.scss
    │   │   ├── _common.scss
    │   │   ├── _index.scss
    │   │   └── _mixin.scss
    │   └── js  # 公共js资源
    │       ├── SL-es.js
    │       ├── SLAPP-es.js
    │       └── responsive.js
    └── pages # 多页目录，每个页面一个目录，注意：每个页面目录下只允许有一个模板html和一个入口js，否则会影响打包。
        ├── about
        │   ├── about.html  # 模板html
        │   ├── about.js  # 入口js
        │   ├── about.scss  # 页面样式
        │   ├── img
        │   └── js  # 其他专用模块js
        ├── contact
        │   ├── contact.html  # 模板html
        │   ├── contact.js  # 入口js
        │   ├── contact.scss  # 页面样式
        │   ├── img
        │   └── js  # 其他专用模块js
        └── index
            ├── img
            ├── index.html  # 模板html
            ├── index.js  # 入口js
            ├── index.scss  # 页面样式
            └── js  # 其他专用模块js
                ├── math.js
                └── print.js
```

**注意：每个页面目录下只允许有一个模板 html 和一个入口 js，否则会影响打包。**

## 浏览器兼容

原则上是根据 `package.json` 中 `browserslist` 配置来打包兼容，未详细测试验证，如发现有问题，请提 issue 或 pr

```json
// package.json中配置
{
  "browserslist": [">= 1%", "last 2 version", "iOS >= 8", "Android >= 4.4"]
}
```

```bash
# 查看结果
npx browserslist

and_chr 69
and_ff 62
and_qq 1.2
and_uc 11.8
android 67
android 4.4.3-4.4.4
android 4.4
baidu 7.12
bb 10
bb 7
chrome 69
chrome 68
edge 17
edge 16
firefox 62
firefox 61
ie 11
ie 10
ie_mob 11
ie_mob 10
ios_saf 11.3-11.4
ios_saf 11.0-11.2
ios_saf 10.3
ios_saf 10.0-10.2
ios_saf 9.3
ios_saf 9.0-9.2
ios_saf 8.1-8.4
ios_saf 8
op_mini all
op_mob 46
op_mob 12.1
opera 55
opera 54
safari 12
safari 11.1
samsung 7.2
samsung 6.2
```

## 贡献

如发现有 bug 或有更好的 idea，欢迎提 PR。
