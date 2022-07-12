<div><a href="https://space.bilibili.com/383551518?spm_id_from=333.1007.0.0" style="text-decoration: none; color: rgba(7, 137, 224, 1)" target="_blank">博客配套视频链接: https://space.bilibili.com/383551518?spm_id_from=333.1007.0.0  b 站直接看</a></div>

<div><a href="https://github.com/nickchen121/Pre-training-language-model" style="text-decoration: none; color: rgba(7, 137, 224, 1)" target="_blank">配套 github 链接：https://github.com/nickchen121/Pre-training-language-model</a></div>

<div><a href="https://www.cnblogs.com/nickchen121/p/16470443.html" style="text-decoration: none; color: rgba(7, 137, 224, 1)" target="_blank">配套博客链接：https://www.cnblogs.com/nickchen121/p/15105048.html</a></div><br>

# 预训练有什么用

机器学习：偏数学（《统计学习方法》-李航）

深度学习（人工智能）的项目：大数据支持（主流）



我们很多项目没有大数据支持（小数据）

猫狗分类任务：100 张猫和狗的图片 --》给你一张图片，分出是猫还是狗（无法解决的一个问题，精度很低）



100000 张鹅和鸭的图片（已知，有人做过的，通过这10w 张图片做了一个模型 A）



![img](https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/%E5%9B%BE%E5%83%8F%E9%A2%84%E8%AE%AD%E7%BB%83%E7%A4%BA%E4%BE%8B.jpg)

有人发现，浅层通用的（横竖撇捺）



我通过10w个鹅和鸭训练了一个模型 A，100 层的 CNN



任务 B：100 张猫和狗的图片，分类 --》 训练处 100层的 CNN，不可能实现的



尝试使用 A 的前 50 层，使用 100 层去完成任务 B



![img](https://imgmd.oss-cn-shanghai.aliyuncs.com/BERT_IMG/%E9%A2%84%E8%AE%AD%E7%BB%83%E7%9A%84%E5%BA%94%E7%94%A8.jpg)

1. 冻结：浅层参数不变
2. 微调：浅层参数会跟着任务 B 训练而改变





# 预训练是什么

通过一个已经训练好的模型 A，去完成一个小数据量的任务 B（使用了模型 A 的浅层参数）

任务 A 和任务 B 极其相似

# 预训练怎么用

fairseq 、transformers 库

# 总结

一个任务 A，一个任务 B，两者极其相似，任务 A 已经训练处一个模型 A，使用模型 A 的浅层参数去训练任务 B，得到模型 B，1.