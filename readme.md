# Checkin

GitHub Actions 实现 [GLaDOS][glados] 自动签到

## 使用说明

1. Fork 这个仓库

1. 登录 [GLaDOS][glados] 获取 Cookie(参考[此文章](https://zhuanlan.zhihu.com/p/616919265))

1. 添加 Cookie 到 Secret `GLADOS`

1. 启用 Actions, 每天北京时间 10:30 自动签到

## 高级功能

1. 如有多个帐号, 可以写为多行 Secret `GLADOS`, 每行写一个 Cookie

1. 如需修改时间, 可以修改文件 [run.yml](.github/workflows/run.yml#L7) 中的 `cron` 参数, 格式可参考 [crontab]，GitHub 用的是 UTC 0 时区，北京时间 = UTC +8 小时。如UTC 02:30 = 北京时间 10:30。

1. 如需推送通知, 可配置 Secret `NOTIFY`, 已支持:
    1. [WxPusher][wxpusher]: 格式 `wxpusher:{token}:{uid}`
    1. [PushPlus][pushplus]: 格式 `pushplus:{token}`
    1. Console: 格式 `console:log`, 作为日志输出, 一般用于调试
    1. 如需配置多个, 可以写为多行, 每行写一个

1. 注意: Cookie 以及接口输出数据, 包含帐号敏感信息, 因此不要随意公开；GLaDOS 的 Cookie 有效期可能不长，如失效需要重新获取并更新到 GLADOS Secret 中。
2. 网址：<br>
glados: https://github.com/glados-network/GLaDOS<br>
crontab: https://crontab.guru/<br>
pushplus: https://www.pushplus.plus/<br>
wxpusher: https://wxpusher.zjiecode.com/<br>
