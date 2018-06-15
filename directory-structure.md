# 前端推荐代码目录结构

**现代流行推荐的纯前端工程代码目录结构**

>下列 `Jquery + LayUI + Bootstrap` 技术栈为例。

```shell
├─ src # 前端目录根节点
    │ 
    ├─ apis                                # 全局Ajax APIs Http请求封装函数
    │  ├─ ajax.js                          # -- 通过 `axios` 统一拦截处理包装ajax
    │  ├─ login.js                         # -- 例如：业务 `login` 登录类Ajax请求函数集合
    │  └─ ...
    │ 
    ├─ assets                               # 全局静态资源（图片、图标）
    │  ├─ svg                               # -- svg文件夹，只准存放 *.svg 文件
    │  │  ├─ delete.svg                     # ---- 例如：`删除` svg图标
    │  │  └─ ...
    │  ├─ blank.png                         # -- 例如：`空白` 通用资源图
    │  └─ ...
    │
    ├─ config                               # 全局配置文件
    │  ├─ index.js                          # -- 配置文件入口，文件以标准的JSON对象，方便读取
    │  └─ ...
    │ 
    ├─ fonts                                # 全局字体文件（字体图标、中英文艺术字体等）
    │  ├─ fontawesome                       # -- `fontawesome`字体图标
    │  │  ├─ fontawesome.eot
    │  │  ├─ fontawesome.woff
    │  │  ├─ fontawesome.ttf
    │  │  └─ fontawesome.svg
    │  ├─ iconfont                          # -- `iconfont`字体图标
    │  │  ├─ iconfont.eot
    │  │  ├─ iconfont.woff
    │  │  ├─ iconfont.ttf
    │  │  └─ iconfont.svg
    │  └─ ...
    │ 
    ├─ pages                                # 业务页面入口（为保证服务访问地址美观，可将 `pages` 修改为对应产品名称 `webapp` | `geoios`）
    │  ├─ login                             # -- 登录页面（文件夹名称以高可读性命名）
    │  │  ├─ index.html                     # ---- 统一使用 `index.html` 命名HTML文件
    │  │  ├─ index.js                       # ---- 统一使用 `index.js` 命名页面业务入口JS文件
    │  │  └─ index.css                      # ---- 统一使用 `index.css` 命名页面单独CSS样式 
    │  ├─ home                              # -- 主框架页面，主要为Layout IFrame布局
    │  │  ├─ modules                        # ---- 需要模块化拆分时，可创建此文件夹；页面模块化拆分后可保证各模块可读性与维护性
    │  │  │  ├─ header.js                   # ------ 例如：`页头` 业务操作模块 
    │  │  │  ├─ footer.js                   # ------ 例如：`页脚` 业务操作模块
    │  │  │  └─ ...
    │  │  ├─ index.html
    │  │  ├─ index.js
    │  │  └─ index.css
    │  ├─ frames                            # -- IFrame内页页面文件夹
    │  │  ├─ page1                          # ---- 例如：页面1
    │  │  │  ├─ index.html
    │  │  │  ├─ index.js
    │  │  │  └─ index.css
    │  │  ├─ page2                          # ---- 例如：页面2
    │  │  │  ├─ index.html
    │  │  │  ├─ index.js
    │  │  │  └─ index.css
    │  │  └─ ... 
    │ 
    ├─ plugins                              # 全局通用第三方插件库
    │  ├─ axios                             # -- Ajax Http请求库（建议采用axios请求ajax，因为可扩展拦截request和response，方便统一处理token令牌验证或请求错误处理等）
    │  │  └─ axios.0.18.0.min.js
    │  ├─ bootstrap                         # -- Bootstrap库
    │  │  ├─ bootstrap.4.0.0.min.css
    │  │  └─ bootstrap.4.0.0.min.js
    │  ├─ jquery                            # -- JQuery库
    │  │  ├─ jquery.3.3.1.slim.min.js       # ---- 只支持H5浏览器，且只保留常用功能，适合只需要基础功能，体积小
    │  │  └─ jquery.1.12.4.min.js           # ---- 支持IE老式浏览器，功能臃肿，体积大
    │  ├─ jquery.validate                   # -- JQuery扩展表单验证插件
    │  │  └─ jquery.validate.1.16.0.min.js
    │  ├─ layui                             # -- LayUI库，含有基础的UI控件
    │  │  ├─ layui.2.3.0.min.css
    │  │  └─ layui.all.2.3.0.min.js
    │  ├─ layui.geo                         # -- 基于LayUI自主二次封装
    │  │  ├─ layui.geo.min.css
    │  │  └─ layui.geo.min.js
    │  ├─ lodash                            # -- Lodash 基础类库，包含（String、Array、Object、Function、Math、Lang等各对象的兼容扩展）
    │  │  └─ lodash.4.17.10.min.js
    │  ├─ moment                            # -- Moment 时间类库，包含 Date对象的各类操作函数
    │  │  └─ moment.2.22.2.min.js
    │  └─ ...
    │ 
    ├─ styles                               # 全局 Styles 样式文件夹
    │  ├─ normalize.css                     # -- normalize.css 浏览器默认值初始化样式表，所有页面必须引入，且需放在所有样式的最前面
    │  │  └─ normalize.css
    │  └─ ...
    │ 
    ├─ themes                               # 皮肤文件夹
    │  ├─ theme.blue.css                    # -- 例如：蓝色风格皮肤
    │  └─ ...
    │ 
    ├─ utils                                # 全局工具类库（可编写各类处理函数，严禁不准包含业务处理逻辑）
    │  ├─ format.js                         # -- 例如：格式化处理工具函数集
    │  └─ ...
    │ 
    └─ index.html                           # 地址访问默认入口（无 css body 内容，空白页面，只准增加自动跳转到业务地址代码）
```
