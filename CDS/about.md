## 关于Custom Distributed Spider
这是一个关于青荇搜索的分布式爬虫服务，主要是因为现阶段青荇搜索的设备不足，于是需要大量的民间成员共同爬虫，用redis作为缓存端
然后用python脚本实现redis+mysql对接  
接着每天固定凌晨三点进行mysql刷新和搜索引擎重启

## 关于接下来青荇搜索的解决方向
1. 首先实现分布式爬虫
2. 紧接着对搜索结果点击量进行权值加分
3. 实现站长平台的管理(主动提交链接)
4. 对青荇搜索展现出来的结果对CSDN等大型编程类结果进行加分
5. 实现16进制的ID索引优化
6. 实现分割索引数据库
7. 实现多维保存不同的倒排索引库
8. 实现定时自动排序和特殊关键词的倒排索引库


## 目前需要解决的bug有
1. 在多样关键词搜索中，发现权值排序失效，于是决定在分布式爬虫内的排序取消，改成脚本定时排序，并且多样化搜索提出结果并将关键词加入jieba分词内，并且将数据库的倒排索引新增索引关键词，并且同时实现排序并且输出

2. 目前在数据管理能实现的范围仍然有限，需要强大的优化和定期的删除
3. 需要实现对csdn相似内容的管控
4. 需要对不同的网页实现不同的定制化爬虫方案，并且定期更新在markdown内
5. 对关键词搜索次数进行一个权值排序，当有相似关键词推荐的时候就用sql语句查询出结果并且进行排序

