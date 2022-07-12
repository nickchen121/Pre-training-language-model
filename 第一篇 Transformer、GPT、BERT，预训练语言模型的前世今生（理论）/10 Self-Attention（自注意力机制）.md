<div><a href="https://space.bilibili.com/383551518?spm_id_from=333.1007.0.0" style="text-decoration: none; color: rgba(7, 137, 224, 1)" target="_blank">博客配套视频链接: https://space.bilibili.com/383551518?spm_id_from=333.1007.0.0  b 站直接看</a></div>

<div><a href="https://github.com/nickchen121/Pre-training-language-model" style="text-decoration: none; color: rgba(7, 137, 224, 1)" target="_blank">配套 github 链接：https://github.com/nickchen121/Pre-training-language-model</a></div>

<div><a href="https://www.cnblogs.com/nickchen121/p/16470443.html" style="text-decoration: none; color: rgba(7, 137, 224, 1)" target="_blank">配套博客链接：https://www.cnblogs.com/nickchen121/p/15105048.html</a></div><br>

# 注意力机制

看一个物体的时候，我们倾向于一些重点，把我们的焦点放到更重要的信息上

<img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/%E4%BA%BA%E7%B1%BB%E7%9A%84%E8%A7%86%E8%A7%89%E6%B3%A8%E6%84%8F%E5%8A%9B.jpg" alt="img" style="zoom:50%;" />

第一眼看到这个图，不会说把所有的信息全部看完

<img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/self-attention.jpg" alt="img" style="zoom:50%;" />

QK 相乘求相似度，做一个 scale（未来做 softmax 的时候避免出现极端情况）

然后做 Softmax 得到概率

新的向量表示了K 和 V（K==V），然后这种表示还暗含了 Q 的信息（于 Q 而言，K 里面重要的信息），也就是说，挑出了 K 里面的关键点

# 自-注意力机制（Self-Attention）（向量）

Self-Attention 的关键点再于，不仅仅是 K$\approx$V$\approx$Q 来源于同一个 X，这三者是同源的

通过 X 找到 X 里面的关键点

并不是 K=V=Q=X，而是通过三个参数 $W_Q,W_K,W_V$

接下来的步骤和注意力机制一模一样

1. Q、K、V的获取
   1. <img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/qkv.jpg" alt="img" style="zoom:50%;" />
2. Matmul：
   1. <img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/Q-K%E4%B9%98%E7%A7%AF.jpg" alt="img" style="zoom:50%;" />

3. Scale+Softmax：
   1. <img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/qk-scale.jpg" alt="img" style="zoom:50%;" />

4. ### Matmul：

   1. <img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/qk-softmax.jpg" alt="img" style="zoom:50%;" />

$z_1$表示的就是 thinking 的新的向量表示

对于 thinking，初始词向量为$x_1$

现在我通过 thinking  machines 这句话去查询这句话里的每一个单词和 thinking 之间的相似度

新的$z_1$依然是 thinking 的词向量表示，只不过这个词向量的表示蕴含了 thinking machines 这句话对于 thinking 而言哪个更重要的信息

<img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/self-attention-%E5%A5%BD%E5%A4%842.jpg" alt="img" style="zoom:67%;" />

不做注意力，its 的词向量就是单纯的 its，没有任何附加信息

# 也就是说 its 有 law 这层意思，而通过自注意力机制得到新的 its 的词向量，则会包含一定的 laws 和 application 的信息

# 自注意力机制（矩阵）

<img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/QKV-%E7%9F%A9%E9%98%B5%E8%A1%A8%E7%A4%BA.jpg" alt="img" style="zoom:50%;" />

<img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/QKVZ-%E7%BB%93%E6%9E%9C.jpg" alt="img" style="zoom:50%;" />

<img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/%E6%B3%A8%E6%84%8F%E5%8A%9B%E6%9C%BA%E5%88%B6%E7%9F%A9%E9%98%B5%E5%9B%BE.jpg" alt="img" style="zoom:50%;" />