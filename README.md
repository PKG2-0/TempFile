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

【注意事项】：
1. 请尽可能多地提供实施例，这对扩大本发明的保护范围非常重要。
2. 请围绕发明点清楚、完整、正确地描述本发明技术方的实现细节，达到以下要求：
（1）清楚：
–	对于方法，详细描述每个动作具体由哪个网元/组件做什么（What），何时做（When），在何种场景下做（Where），如何做（How）；
–	对于硬件类发明，详细描述执行发明点的产品的组成部分和各组成部分之间的连接关系，以及各组成部分的特征和作用，并描述产品内部架构中的哪个硬件元器件/单元的改进以及各组成部分如何执行本发明；
–	对于软件类发明，描述执行发明点的产品的组成部分和各组成部分之间的连接关系，及各组成部分如何执行本发明；    
（2）完整：每个单独的技术方案应当都是完整的，包含发明点以及实现发明的其他必要的非发明点特征，并对每个特征都进行充分说明；
  （3）正确：实施例方案的描述不存在方案错误、前后矛盾、技术方案不可实施等技术方面的问题。3. 应当提供本发明技术方案必需的附图，附图应符合产品实际形态和产品实际交互流程，有助于读者快速理解技术方案；
附图应为黑白图且没有灰度、清晰并且可编辑，如果需要填充底纹，则应使用图样；
附图的种类包括但不限于系统图、装置图、流程图、原理框图、电路图、时序图等。                                             
4.请采用自然语言撰写，不得仅用协议语言、程序语言描述技术方案。应尽量避免使用产品源代码描述发明方案。

