forked from pandoraes/shadowsocksr-manyuser


# sspanel+节点 B1 后端一键安装配置管理脚本
* 感谢glzjin wulabing提供的代码 
* 适用于glzjin面板ssr后端的一键安装脚本 实现输入配置信息、以及全自动安装，配置一键修改，一键启动暂停等功能 支持 modwebapi 及 glzjinmod（mysql connect）
* 新版(supervisor版本)支持 Ubuntu16.04+ / Centos 6+ / Debian 8+
* 默认安装目录：/usr/local/shadowsocksr
* 请注意：1.03 bate 本版本可能存在严重性问题，如果有问题请提供错误方式。


# 安装方法 （ 2018/02/05 更新）
```
git clone https://github.com/mifaa/shadowsocksr-manyuser.git SSR

cd SSR
```
新版本安装：
```
chmod +x shadowsocks_new.sh

./shadowsocks_new.sh install | tee ss.log
```
# 相关目录

后端默认安装目录：`/usr/local/shadowsocksr`
配置文件默认目录 `/etc/shadowsocksr/config.json`

supervisor 默认配置目录 ：`/etc/supervisor/conf.d/shadowsocks.conf （Centos:/etc/supervisord.conf）`

# 启动方式（）

### 新版本：

* 启动  shadowsocks ：`./shadowsocks_new.sh start`
* 停止  shadowsocks ：`./shadowsocks_new.sh stop`
* 重启  shadowsocks ：`./shadowsocks_new.sh restart`
* 强制停止 shadowsocks ：`./shadowsocks_new.sh fstop`
* 配置信息变更：`./shadowsocks_new.sh modify`
* 添加 supervisor 开机启动： `systemctl enable supervisor (centos6:chkconfig --add supervisord)`
* 日志 ：`tail -f /var/log/ssr.log`

# 更新
## 2018-02-08
* 增加启动脚本ssr
* 修改日至文件为/var/log/ssr.log
* 优化代码

## 2018-02-07
B1.03
* 修改合并配置文件为config.json
* 优化代码提高性能
* 修改DNS

## 2018-02-06
B1.02
* 减少优化manyouser文件。

## 2018-02-05
* 升级命名为B1分支
* 更新libsodium 到1.16稳定版 并且安装到/usr/local/libsodium
* 重新修改manyuser 路径
* 增加脚本所在目录
* 增加基础服务安装 GCC
* 修复bug

## 2017-12-21
V4.0
* 添加 基本init选项，可以直接通过脚本控制后端启动，暂停等基本功能
* 添加 配置信息自助修改功能
* 修复 细节性bug

## 2017-12-12
V3.11
* 修复 easy_install pip 出错后 python-pip 安装的逻辑错误

## 2017-12-10
V3.1
* 添加 部分选项默认配置
* 修复 部分交互提示错误
* 添加 Centos6 支持
* 修复 部分bug

## 2017-12-10
V3.0
### 从本版本开始 仅支持具有 Systemd 特性的发行版系统 并启用 shadowsocks_new.sh 更新，旧版本停止维护

* 1.添加 supervisor 守护程序安装
* 2.添加 选择列表，可以手动选择安装 SSR 或 supervisor 
* 3.修复 webapi模式下运行出现 no module named requests 的情况 （由于缺少 requests 模块）
* 4.改善 部分交互内容

## 2017-08-09
V2.1.2

* 1.调整顺序。优先进行信息输入，然后进入安装流程

## 2017-07-29
V2.1.1

* 1.libsodium 版本由早期 1.0.10 调整至 1.0.13


## 2017-05-07
V2.1

* 1.修复因逻辑问题导致配置文件内容异常从而导致的运行报错
* 2.修复由于 debian 源中有 deb cdrom 而导致的安装中断
* 3.添加了禁用防火墙的相关内容

V2.0

* 1.实现输入配置信息、以及全自动安装，支持 modwebapi 及 glzjinmod（mysql connect）
* 2.修复bug

## 2017-05-06
V1.1

* 1、自动进行相关依赖的安装，支持 ubuntu14.04+ / centos6+ /debian7+ 

