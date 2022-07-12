<div><a href="https://space.bilibili.com/383551518?spm_id_from=333.1007.0.0" style="text-decoration: none; color: rgba(7, 137, 224, 1)" target="_blank">博客配套视频链接: https://space.bilibili.com/383551518?spm_id_from=333.1007.0.0  b 站直接看</a></div>

<div><a href="https://github.com/nickchen121/Pre-training-language-model" style="text-decoration: none; color: rgba(7, 137, 224, 1)" target="_blank">配套 github 链接：https://github.com/nickchen121/Pre-training-language-model</a></div>

<div><a href="https://www.cnblogs.com/nickchen121/p/16470443.html" style="text-decoration: none; color: rgba(7, 137, 224, 1)" target="_blank">配套博客链接：https://www.cnblogs.com/nickchen121/p/15105048.html</a></div><br>

# 上节课回顾

《Attention is all you need》

## Attention

<img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/masked-attention.jpg" alt="img" style="zoom:50%;" />

# Self-Attention（Self--》自--》QKV 同源）

句法结构，语义结构

<img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/%E6%B3%A8%E6%84%8F%E5%8A%9B%E6%9C%BA%E5%88%B6%E7%9F%A9%E9%98%B5%E5%9B%BE.jpg" alt="img" style="zoom:50%;" />

自注意力机制明确的知道这句话有多少个单词，并且一次性给足，而掩码是分批次给，最后一次才给足

# Masked（掩码） Self-Attention--》在自注意力模型上面做了改进

为什么要做这个改进：生成模型，生成单词，一个一个生成的

当我们做生成任务的时候，我们也想对生成的这个单词做注意力计算，但是，生成的句子是一个一个单词生成的



I have a dream



1. I  第一次注意力计算，只有 I

2. I have 第二次，只有 I 和 have

3. I have a

4. I have a dream
5. I have a dream \<eos\>



掩码自注意力机制应运而生



掩码后 1

<img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/mask-attention-map.jpg" alt="img" style="zoom:50%;" />

掩码后2

<img src="https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/mask-attention-map-softmax.jpg" alt="img" style="zoom:50%;" />

未来我们讲 Transformer 的时候会详细讲！

Multi-head Self-Attention。