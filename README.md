# -word-vectors-bert
毕业设计  
###划分单词前缀后缀
* wiki语料库[https://dumps.wikimedia.org/enwiki/latest/]  
首先将xml的wiki数据转换为text格式，通过这个脚本(process_wiki.py)实现。
* 构建Trie树
这个就是leetcode208. 实现 Trie (前缀树)：本质上是字典按字母迭代      
在两次insert插入后，迭代出来的字典会有如下表达，end表示：在这个字母的位置存在某个单词的结尾  
> apple:{'a': {'p': {'p': {'l': {'e': {'end': True}}}}}}             #第一次insert，最后一个'e'存在结束'end'  
> app:  {'a': {'p': {'p': {'l': {'e': {'end': True}}, 'end': True}}}}#第二次insert，第二个'p'存在结束'end'
然后insert词缀表,构建Trie树  
这里的startsWith函数进行修改，源码是判断是否为前缀，经过最长字符匹配修改后，则是获取单词的词缀。  
* 处理txt文章
1. 去空格，化为单词行
2. 去重复，保序
3. 输入到startsWith函数，导出前缀。
* 遇见的问题  
均可Google解决，不少都是python语法问题。


