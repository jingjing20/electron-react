# electron-react
Electron+React+七牛云 实战跨平台桌面应用 使用 Github 的 Electron，开发一款自动云同步的 Markdown 文件管理软件

## 1、进程与线程

### 概念
线程是操作系统能够进行运算调度的最小单位。它被包含在进程之中，是进程中实际运作单位。

### 区别

#### 内存使用方面的区别
- 进程拥有操作系统分配给它的单独的内存，默认情况一个进程的分配的内存无法给另一个进程共享。
- 一个进程里面的所有线程可以共享进程内存。

#### 通信机制方面的区别
- 进程之间很难互通，可以通过 IPC （进程间通信）。
- 线程之间共用一块内存，通信方便快捷。

#### 量级方面的区别
- 线程相对于进程创建起来更轻、更快，使用的资源更少。

## 2、nodemon 使用
`"start": "nodemon --watch main.js --exec \"electron .\""`
- --watch 监听哪个文件
- --exec 执行哪个文件
- 用 \ 转义""

## 3、concurrently 和 wait-on

- concurrently 可以同时执行多个命令
- wait-on 可以等某个操作完成后继续下一个命令

```js
"dev": "concurrently \"wait-on http://localhost:3000 && electron .\" \"cross-env BROWSER=none npm start\"",
```
