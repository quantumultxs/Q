# 威锋网 (APP)

## 配置

```properties
[MITM]
hostname = 49.234.36.200:9091

[rewrite_local]
# 威锋网获取cookie
^http:\/\/49.234.36.200:9091\/v1\/auth\/signin url script-request-body https://ghproxy.com/https://raw.githubusercontent.com/quantumultxs/Q/m/task/feng/feng.cookie.js

[task_local]
1 0 * * * https://ghproxy.com/https://raw.githubusercontent.com/quantumultxs/Q/m/task/feng/feng.js, tag=喜马拉雅, img-url=https://ghproxy.com/https://raw.githubusercontent.com/quantumultxs/Q/m/icons/Orz-3/feng.png, enabled=true
```

## 说明

1. 先把`hostname`加到`[MITM]`
2. 再配置重写规则:修改`[rewrite_local]`和`[task_local]`
3. 在 `威锋网` APP 下使用`账号密码`方式登录
4. 提示 `获取会话: 成功`
5. 最后把`[rewrite_local]`注释掉
