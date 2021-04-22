# 飞客茶馆

## 配置

```properties
[MITM]
hostname = www.flyertea.com

[rewrite_local]
# 飞客茶馆获取cookie
^https:\/\/www\.flyertea\.com\/source\/plugin\/mobile\/mobile\.php\?module=getdata&.* url script-request-header https://ghproxy.com/https://raw.githubusercontent.com/quantumultxs/Q/m/task/flyertea/flyertea.cookie.js

[task_local]
1 0 * * * https://ghproxy.com/https://raw.githubusercontent.com/quantumultxs/Q/m/task/flyertea/flyertea.js, tag=飞客茶馆, img-url=https://ghproxy.com/https://raw.githubusercontent.com/quantumultxs/Q/m/icons/Orz-3/flyertea.png, enabled=true
```

## 说明

1. 先把`hostname`加到`[MITM]`
2. 再配置重写规则:修改`[rewrite_local]`和`[task_local]`
3. 打开 APP, 访问下`个人中心`
4. 系统提示: `获取Cookie: 成功` （如果不提示获取成功, 尝试杀进程再进个人中心）
5. 最后把`[rewrite_local]`注释掉

