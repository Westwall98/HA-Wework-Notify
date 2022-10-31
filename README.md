# HA-Wework-Notify
HomeAssistant 企业微信推送

## 安装

* 将此 repo (https://github.com/Westwall98/HA-Wework-Notify) 添加到 [HACS](https://hacs.xyz/)

## 配置
```yaml
notify:
  - platform: wework_notify
    name: wework          # 实体ID
    corpid: "XXXXXXX"     # 企业微信的企业id
    agentId: "1000002"    # 企业微信的应用id
    secret: "XXXXXXX"     # 企业微信的应用secret
    touser: 'A|B|C'       # A&B&C
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
