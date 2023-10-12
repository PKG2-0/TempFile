# TempFile

***

我们按照安卓的标准来吧，然后把重要的信息拎出来
https://developer.android.com/guide/topics/providers/calendar-provider?hl=zh-cn
https://developer.android.com/guide/topics/ui/notifiers/notifications?hl=zh-cn#limits
https://developer.android.com/guide/topics/providers/contacts-provider?hl=zh-cn
备忘录，粘贴板就是String，剪贴板本身用户复制会触发，所以可以记录一个复制时间，备忘录的最后修改时间是否需要

短信数据库里面常用的字段是address 发件人号码
person 联系人姓名列表
date 短信日期
body 短信内容
type 短信类型（ALL=0，INBOX=1,SEND=2,DRAFT = 3，OUTBOX = 4，FAILED = 5，QUEUED = 6）

联系人的
https://developer.android.google.cn/reference/android/provider/ContactsContract.Data
 ![image](https://github.com/PKG2-0/TempFile/assets/37244096/bf49a91f-f59e-4b44-a088-619b45781c02)
每个里面展开也有不同类型，我们可以按需求来看要不要展开
 ![image](https://github.com/PKG2-0/TempFile/assets/37244096/ea01e63d-bcbc-46fd-82d1-4b9be52057ff)
test

关于方案设计想要了解的问题及10.30对demo的要求：
1. 端侧信息如何存储？
a) 当前是使用结构化数据库进行的存储？
b) 如何避免存储信息冗余？
c) 如何压缩存储信息（端侧数据库规模不能太大）
d) 后续信息查询中，如何构建查询语句？如何查询多跳关联信息？
2. 端云通讯
a) 端侧信息预处理（强隐私特性预处理？）
b) 端云协同时的通信时延问题？
c) 云侧单条信息抽取？如何并发？
3. Demo雏形
a) 端侧输入
b) 原始信息传输到云端进行抽取
i. 云侧使用运行在本地的服务器进行抽取
ii. 不能简单调用API
iii. 抽取结果有数值化评测指标
c) 返回值存入端侧数据库
d) 端侧进行查询
i. 查询结果有数值化评测指标
e) 将查询结果写入端侧APP
i. 可视化呈现
