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
