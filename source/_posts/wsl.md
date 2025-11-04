---
title: WSL2 安装
---
简单安装WSL2


<!-- more -->


## 准备工作

下面两处打勾 [适用于 Linux 的 Windows 子系统] 和[虚拟机平台]

{% asset_img 1.png %}

## 设置默认为WSL2

用管理员身份打开 powershell

```bash
$ wsl --set-default-version 2
```

## 下载Ubuntu

```bash
$ wsl --install -d Ubuntu
```

### 若出现报错例如：

```bash
Installing, this may take a few minutes... WslRegisterDistribution failed with error: 0x800701bc Err
```

将 `LxssManager 服务`修改为自动启动从服务中修改会提示“拒绝访问”，所以从[注册表](https://so.csdn.net/so/search?q=%E6%B3%A8%E5%86%8C%E8%A1%A8&spm=1001.2101.3001.7020)改 `win + R -> regedit -> \HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\LxssManager -> 右键 Start 项 -> 将值修改为 2  `再输入 ``wsl --update``即可
