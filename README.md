# Pepper_Server
## 中文微博情感分类语料库
带标签的微博语料数量: 10000+500
我本科毕业设计做微博情感NLP,需要对微博文本进行正负情感二分类.  
但网上相关语料库的质量都太低了,追求完美的我一气之下就写了个爬虫,一边标注一边爬.  
因为是自己的毕设,所以标注是相当认真的,还请了朋友帮忙校验,其间还过滤掉了广告/太短/太长/表意不明等语料,语料质量是绝对可以保证的.  
现在把它开源出来, 仅供做NLP的各位朋友学习、交流使用.

### 标注说明
文档的每一行代表一条语料.  
第一个数据为微博的mid,是每条微博的唯一标签,可以通过"https://m.weibo.cn/status/" + mid 访问到该条微博的网页.  
每行的第二个数据为情感标签,0表示负面情感, 1表示正面情感.  
其余部分都是微博文本.  
所有微博表情都被转义成`[xx]`的格式(如`[二哈]`), 所有的微博话题/地理定位/视频、文本超链接等都转义成了`{%xxxx%}`的格式，以便与普通文本区分.

### 文件说明
`weibos.txt`:
* 10000条语料, 根据情感倾向二分类标注;
* 对负面语料轻轻地进行了过采样, 正: 负 = 5497:4503;
* 作为训练集.

`weibos_test.txt`:
* 500条语料, 依据情感倾向二分类标注;
* 随机采样, 正: 负 = 7:3;
* 作为测试集.

`XXX.txt`:
* 100条语料, 未进行情感分类标注(当时还不会分布式爬虫, 所以爬的比较少QAQ);
* 以XXX为主题的相关微博;
* 可用于舆情分析测试.

### Author
欢迎交流  
email:dengxiuqi@163.com  
wechat:dengxiuqi007  
2018.6