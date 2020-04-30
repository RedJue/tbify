# tbify

使用 [淘宝 NPM 镜像](https://developer.aliyun.com/mirror/NPM) 加速包管理工具安装依赖的速度。

## 实现原理

基于环境变量对国内请求速度欠佳的资源地址进行了替换，具体分为两点：

- 通过环境变量令包管理工具使用淘宝源安装依赖；
- 通过环境变量令诸如 `nvm`、 `node-sass`、`Electron`、`Puppeteer` 等包使用淘宝镜像安装其自身所需资源。

以上，本工具对包管理工具本身零侵入，同时，对环境变量的设置也是一次性的，并不会产生任何的副作用，请放心使用。

## 安装

```bash
# npm
npm install tbify --global

# yarn
yarn global add tbify

# pnpm
pnpm add --global tbify
```

## 使用

对于常用的包管理命令，`tbify` 提供了使用淘宝 NPM 镜像的等价命令，除了发布包到 npm 时必须使用 `npm publish` 外，都可以使用等价命令进行相关操作：

| 原命令 | 使用淘宝 NPM 镜像的命令 | 示例                 |
| ------ | ----------------------- | -------------------- |
| npm    | tnm                     | `tnm install react`  |
| npx    | tnx                     | `tnx kill-port 3000` |
| yarn   | tyn                     | `tyn add react`      |
| pnpm   | tpm                     | `tpm add react`      |
| pnpx   | tpx                     | `tpx kill-port 3000` |

对于其他命令，在使用时加上 `tbify` 前缀即可，比如：

```bash
tbify printenv npm_config_registry
# -> https://r.npm.taobao.org
```

## 鸣谢

感谢 [淘宝 NPM 团队](https://github.com/cnpm) 提供的优质镜像，解救广大前端同胞于水火！👍

同时本工具从 [@yiminghe](https://github.com/yiminghe) 大佬的 [tyarn](https://github.com/yiminghe/tyarn) 项目借鉴了很多思路，一并表示感谢！💐

## 许可

Jay Fong (c) MIT
