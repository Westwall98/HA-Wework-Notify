# HA-Wework-Notify
HomeAssistant企业微信推送

## 安装

* 将此 repo (https://github.com/Westwall98/HA-Wework-Notify) 添加到 [HACS](https://hacs.xyz/)

## 配置
```yaml
notify:
  - platform: wework_notify
    name: wework          # 实体ID  比如这个出来就是notify.wework
    corpid:               # 这个是企业微信的企业id
    agentId: "1000002"    # 这个是企业微信里面新建应用的应用id
    secret:               # 这个是企业微信里面新建应用的应用secret
    touser: '@all'        # 全体成员
```

## 使用
```yaml
service: notify.wework
data:
  message: 发送纯文本消息

service: notify.wework
data:
  message: 发送带标题和分隔线的纯文本消息
  title: 这是标题

service: notify.wework
data:
  message: ' '
  title: 发送带标题的链接卡片
  data:
    type: news
    url: 'http://www.sogou.com'
    
service: notify.wework
data:
  message: 发送带标题和内容的链接卡片
  title: 这是标题
  data:
    type: textcard
    url: 'http://www.sogou.com'
    
service: notify.wework
data:
  message: 发送带标题、内容和头图的链接卡片
  title: 这是标题
  data:
    type: news
    url: 'http://www.sogou.com'
    picurl: 'https://bbs.hassbian.com/static/image/common/logo.png'
```
