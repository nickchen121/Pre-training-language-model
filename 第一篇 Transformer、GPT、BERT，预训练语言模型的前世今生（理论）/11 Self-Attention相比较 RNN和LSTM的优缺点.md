<div><a href="https://space.bilibili.com/383551518?spm_id_from=333.1007.0.0" style="text-decoration: none; color: rgba(7, 137, 224, 1)" target="_blank">博客配套视频链接: https://space.bilibili.com/383551518?spm_id_from=333.1007.0.0  b 站直接看</a></div>

<div><a href="https://github.com/nickchen121/Pre-training-language-model" style="text-decoration: none; color: rgba(7, 137, 224, 1)" target="_blank">配套 github 链接：https://github.com/nickchen121/Pre-training-language-model</a></div>

<div><a href="https://www.cnblogs.com/nickchen121/p/16470443.html" style="text-decoration: none; color: rgba(7, 137, 224, 1)" target="_blank">配套博客链接：https://www.cnblogs.com/nickchen121/p/15105048.html</a></div><br>

# RNN

![img](https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/RNN-unrolled.png)

无法做长序列，当一段话达到 50 个字，效果很差了

# LSTM

![img](https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/LSTM%E6%A8%A1%E5%9E%8B%E7%BB%93%E6%9E%84.jpg)

LSTM 通过各种门，遗忘门，选择性的可以记忆之前的信息（200 词）

# Self-Attention 和 RNNs 的区别

RNNs 长序列依赖问题，无法做并行

Self-Attention 得到的新的词向量具有句法特征和语义特征（词向量的表征更完善）

## 句法特征

<img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/self-attention-%E5%A5%BD%E5%A4%841.jpg" alt="img" style="zoom:67%;" />

## 语义特征

<img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/self-attention-%E5%A5%BD%E5%A4%842.jpg" alt="img" style="zoom:50%;" />

# 并行计算

<img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/qk-softmax.jpg" alt="img" style="zoom:50%;" />