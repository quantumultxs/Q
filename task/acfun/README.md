# AcFun

## 配置

```properties
[MITM]
hostname = *.acfun.cn

[rewrite_local]
# AcFun获取cookie
^https:\/\/api\-new\.app\.acfun\.cn\/rest\/app\/user\/personalInfo url script-request-header https://ghproxy.com/https://raw.githubusercontent.com/quantumultxs/Q/m/task/acfun/acfun.cookie.js

[task_local]
1 0 * * * https://ghproxy.com/https://raw.githubusercontent.com/quantumultxs/Q/m/task/acfun/acfun.js, tag=喜马拉雅, img-url=https://ghproxy.com/https://raw.githubusercontent.com/quantumultxs/Q/m/icons/Orz-3/acfun.png, enabled=true
```

## 说明

1. 先把`hostname`加到`[MITM]`
2. 再配置重写规则:修改`[rewrite_local]`和`[task_local]`
3. 打开 APP, 访问下`我的`
4. 系统提示: `获取Cookie: 成功` & `获取Token: 成功`（如果不提示获取成功, 尝试杀进程再进`我的`）
5. 最后把`[rewrite_local]`注释掉
