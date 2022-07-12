<div><a href="https://space.bilibili.com/383551518?spm_id_from=333.1007.0.0" style="text-decoration: none; color: rgba(7, 137, 224, 1)" target="_blank">博客配套视频链接: https://space.bilibili.com/383551518?spm_id_from=333.1007.0.0  b 站直接看</a></div>

<div><a href="https://github.com/nickchen121/Pre-training-language-model" style="text-decoration: none; color: rgba(7, 137, 224, 1)" target="_blank">配套 github 链接：https://github.com/nickchen121/Pre-training-language-model</a></div>

<div><a href="https://www.cnblogs.com/nickchen121/p/16470443.html" style="text-decoration: none; color: rgba(7, 137, 224, 1)" target="_blank">配套博客链接：https://www.cnblogs.com/nickchen121/p/15105048.html</a></div><br>

# Transformer 编码器

编码器在干吗：词向量、图片向量，总而言之，编码器就是让计算机能够更合理地（不确定性的）认识人类世界客观存在的一些东西

# Transformer 解码器

解码器会接收编码器生成的词向量，然后通过这个词向量去生成翻译的结果。

<img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/ed-%E7%BB%86%E5%88%86.jpg" alt="img" style="zoom:80%;" />

解码器的 Self-Attention 在编码已经生成的单词

假如目标词“我是一个学生”---》masked Self-Attention

训练阶段：目标词“我是一个学生”是已知的，然后 Self-Attention 是对“我是一个学生” 做计算

如果不做 masked，每次训练阶段，都会获得全部的信息

如果做 masked，Self-Attention 第一次对“我”做计算

Self-Attention 第二次对“我是”做计算

……

测试阶段：

1. 目标词未知，假设目标词是“我是一个学生”（未知），Self-Attention 第一次对“我”做计算
2. 第二次对“我是”做计算
3. ……

而测试阶段，没生成一点，获得一点

# 生成词

<img src="../../ed-交互.jpg" alt="img" style="zoom:80%;" />



Linear 层转换成词表的维度

softmax 得到最大词的概率



softmax 细话

<img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/tf-%E6%9C%80%E5%90%8E%E8%BE%93%E5%87%BA.jpg" alt="img" style="zoom:80%;" />

单词表

<img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/tf-%E6%9C%80%E7%BB%88%E8%BE%93%E5%87%BA%E7%BB%93%E6%9E%9C.jpg" alt="img" style="zoom:80%;" />