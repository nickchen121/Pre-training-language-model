<div><a href="https://space.bilibili.com/383551518?spm_id_from=333.1007.0.0" style="text-decoration: none; color: rgba(7, 137, 224, 1)" target="_blank">博客配套视频链接: https://space.bilibili.com/383551518?spm_id_from=333.1007.0.0  b 站直接看</a></div>

<div><a href="https://github.com/nickchen121/Pre-training-language-model" style="text-decoration: none; color: rgba(7, 137, 224, 1)" target="_blank">配套 github 链接：https://github.com/nickchen121/Pre-training-language-model</a></div>

<div><a href="https://www.cnblogs.com/nickchen121/p/16470443.html" style="text-decoration: none; color: rgba(7, 137, 224, 1)" target="_blank">配套博客链接：https://www.cnblogs.com/nickchen121/p/15105048.html</a></div><br>

# 厚颜无耻的要个赞

# Attention

优点：

1. 解决了长序列依赖问题
2. 可以并行

缺点：

1. 开销变大了

2. 既然可以并行，也就是说，词与词之间不存在顺序关系（打乱一句话，这句话里的每个词的词向量依然不会变），即无位置关系（既然没有，我就加一个，通过位置编码的形式加）

位置编码的问题

# 为什么需要位置编码

# 位置编码怎么做的

<img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/%E4%BD%8D%E7%BD%AE%E5%90%91%E9%87%8F.jpg" alt="img" style="zoom:50%;" />

# 具体做法

做法 1

<img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/%E4%BD%8D%E7%BD%AE%E7%BC%96%E7%A0%81%E5%85%AC%E5%BC%8F.png" alt="img" style="zoom:50%;" />

做法 2

<img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/%E4%BD%8D%E7%BD%AE%E7%BC%96%E7%A0%81%E5%92%8C%E8%AF%8D%E5%90%91%E9%87%8F%E4%B9%8B%E5%92%8C.png" alt="img" style="zoom:50%;" />

# 为什么这么做有用

pos+K=5，我在计算第 5 个单词的位置编码的时候



pos=1，k=4

pos=2，k=3



<img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/%E4%BD%8D%E7%BD%AE%E5%B5%8C%E5%85%A5%E8%A7%A3%E9%87%8A.png" alt="img" style="zoom:50%;" />