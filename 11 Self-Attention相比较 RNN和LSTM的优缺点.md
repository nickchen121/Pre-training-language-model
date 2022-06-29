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