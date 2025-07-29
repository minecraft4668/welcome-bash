新手建库，还请各位大佬多多指教！

## 项目简介

本项目包含一个 Bash 脚本 ".welcome"，用于在终端登录时显示系统信息、网络状态检测及每日一言。脚本支持彩色输出，适用于 Windows 下的 Bash 环境（如 Git Bash、WSL）。

## 功能说明

- 显示操作系统(TODO)、Git 版本、主机名、当前用户及登录时间
- 检测网络连接（默认目标为 8.8.8.8，可自定义）
- 成功联网时，调用 [Hitokoto API](https://hitokoto.cn/) 获取每日一言
- 网络不可用时，尝试从本地一言库 `~/.hitokoto_lib` 获取内容
- 彩色输出，支持多种背景和前景色
- 终端颜色测试展示

## TODO

1. 完善本地一言库脚本
2. 死网快测啊！！！！（bushi

## 使用方法

1. 执行以下脚本：
Windows:
````cmd
git clone https://github.com/minecraft4668/Unknown.git %USERPROFILE%/
````
Linux
````bash
git clone https://github.com/minecraft4668/Unknown.git ~/
````

2. 在 用户目录下找到Bash 启动脚本（如Linux中的 `~/.bashrc` 或 `~/.profile`及Windows中 `C:\Users\xxx(用户名)\.bashrc`）（Windows用户可能需要下载其他模拟终端（如Git））末行添加如下内容：

    ````bash
    [ -f ~/.welcome ] && source ~/.welcome
    ````

## 参数配置

- `TARGET`：网络检测目标 IP 或域名
- `PING_COUNT`：ping 测试次数
- `TIMEOUT`：ping 超时时间（秒）
- `CURL_TIMEOUT`：API 请求超时时间（秒）
- `TRACEROUTE_HOPS`：traceroute 最大跳数

## 依赖

- Bash
- `ping`、`curl`、`git` 命令

## 致谢

- 每日一言 API：[Hitokoto.cn](https://hitokoto.cn/)
- 彩色输出参考 ANSI 转义码
