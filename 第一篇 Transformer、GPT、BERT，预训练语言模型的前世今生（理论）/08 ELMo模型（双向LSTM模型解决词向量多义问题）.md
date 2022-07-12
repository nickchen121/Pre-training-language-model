<div><a href="https://space.bilibili.com/383551518?spm_id_from=333.1007.0.0" style="text-decoration: none; color: rgba(7, 137, 224, 1)" target="_blank">博客配套视频链接: https://space.bilibili.com/383551518?spm_id_from=333.1007.0.0  b 站直接看</a></div>

<div><a href="https://github.com/nickchen121/Pre-training-language-model" style="text-decoration: none; color: rgba(7, 137, 224, 1)" target="_blank">配套 github 链接：https://github.com/nickchen121/Pre-training-language-model</a></div>

<div><a href="https://www.cnblogs.com/nickchen121/p/16470443.html" style="text-decoration: none; color: rgba(7, 137, 224, 1)" target="_blank">配套博客链接：https://www.cnblogs.com/nickchen121/p/15105048.html</a></div><br>

# Word2Vec 模型

NNLM 模型（是不是在预测下一个词，副产品是词向量）

Word2Vec 模型：专门做词向量

1. CBOW
2. Skip-gram

![image-20220614193540503](../../Library/Application Support/typora-user-images/image-20220614193540503.png)

apple，苹果，

# ELMo

![img](https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/we%E5%A4%9A%E4%B9%89%E8%AF%8D%E9%97%AE%E9%A2%98.jpg)

elmo 解决多义词问题

![img](https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/word2vec.jpg)



![img](https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/%E5%9F%BA%E4%BA%8E%E4%B8%8A%E4%B8%8B%E6%96%87%E7%9A%84emedding.jpg)

ELMo（专门做词向量，通过预训练）

不只是训练一个 Q 矩阵，我还可以把这个次的上下文信息融入到这个 Q 矩阵中

左边的 LSTM 获取 E2 的上文信息，右边就是下文信息

x1,x2, x4,x5 --> Word2Vec x1+x2+x4+x5 ---> 预测那一个词



获取上下文信息后，把三层的信息进行一个叠加

E1+E2+E3 = K1 一个新的词向量 $\approx$ E1

E2,E3 相当于两个上下文信息

E1+E2+E3+E4

K1 包含了第一个词的词向量包含单词特征、句法特征、语义特征



怎么用

E2，E3 不同，E1+E2+E3 不同

apple --》 我吃了一个 苹果 -- 》 [1,20,10]

apple --》我在用苹果手机 --》[1,10,20]

![img](https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/elmo%E8%AE%AD%E7%BB%83%E5%90%8E%E7%9A%84%E4%BD%BF%E7%94%A8.jpg)

LSTM 无法并行，长期依赖

Attention



