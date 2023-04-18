
## 快速新建项目模板
https://arco.design/vue/docs/pro/start

### 环境
开始开发之前，请确认本地环境中安装好了 node， git 和 arco cli。

其中 arco cli 是安装项目模版的工具，请运行以下命令安装：
```
npm i -g arco-cli
```

### 技术栈
本项目的技术栈为 vue + ES2015+ + TypeScript + Arco Design 和 echarts等，提前学习和了解这些知识将帮助你更好地上手我们的项目。

### 安装
这一步是以 Arco Design Pro 为模版创建一个新的项目，请按照以下步骤进行：

进入到一个文件夹，新建项目
```
cd someDir
arco init hello-arco-pro
```

选择 技术栈
```
? 请选择你希望使用的技术栈
   React
 ❯ Vue
```

选择 arco-design-pro 分类
```
? 请选择一个分类
   业务组件
   组件库
   Lerna Menorepo 项目
 ❯ Arco Pro 项目
```
等待安装依赖。。。

看到以下输出就是创建成功了

### 我的安装
首次安装失败，缺少依赖
```sh
? 请选择你希望使用的技术栈 Vue
? 请选择所要创建项目的类型 Arco Pro 项目
? 请选择 Arco Pro 模板 完整版（包含所有页面）

正在初始化项目于 D:\WebStormProject\web-notebook
√ 获取项目模板成功
√ 模板内容拷贝完成
√ 模板内容适配完成
√ 项目依赖安装完成
 arco-init  项目初始化失败！
Error: spawnSync pnpm.cmd ENOENT
```

安装依赖
```
D:\WebStormProject>npm i -g pnpm

added 1 package in 2s

D:\WebStormProject>where pnpm
C:\Users\lenovo\AppData\Roaming\npm\pnpm
C:\Users\lenovo\AppData\Roaming\npm\pnpm.cmd
```

重写初始化
```
D:\WebStormProject>arco init web-notebook

        ___                    ____            _
       /   |  ______________  / __ \___  _____(_)___ _____
      / /| | / ___/ ___/ __ \/ / / / _ \/ ___/ / __ `/ __ \
     / ___ |/ /  / /__/ /_/ / /_/ /  __(__  ) / /_/ / / / /
    /_/  |_/_/   \___/\____/_____/\___/____/_/\__, /_/ /_/
                                             /____/

                                                v1.27.5

? 路径已经存在，确认要覆盖它吗？ D:\WebStormProject\web-notebook Yes
? 请选择你希望使用的技术栈 Vue
? 请选择所要创建项目的类型 Arco Pro 项目
? 请选择 Arco Pro 模板 完整版（包含所有页面）

正在初始化项目于 D:\WebStormProject\web-notebook
√ 获取项目模板成功
√ 模板内容拷贝完成
√ 模板内容适配完成
√ 项目依赖安装完成
******************************************************************************
  Read README.md for help information. Execute following command to start
    $ cd web-notebook
    $ pnpm run dev
******************************************************************************

D:\WebStormProject>
```

### 启动
```
D:\WebStormProject>cd web-notebook

D:\WebStormProject\web-notebook>pnpm run dev

> arco-design-pro-vue@1.0.0 dev D:\WebStormProject\web-notebook
> vite --config ./config/vite.config.dev.ts


  VITE v3.2.5  ready in 1178 ms

  ➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
```
web访问http://localhost:5173/即可



```

```