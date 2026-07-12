overlap（重叠）：相邻两个文本块之间重复保留一小段相同文字，那段重复内容。

比如：教材原文说AVL树四种旋转：LL、RR、LR、RL。LL失衡右旋，RR失衡左旋。LR先左后右，RL先右后左。平衡因子范围- 1、0、1。

假设chunk_size=30字，overlap=10字

Chunk1：AVL 树四种旋转：LL、RR、LR、RL。LL失衡右旋，RR失衡左旋。

Chunk2：**LL失衡右旋，RR失衡左旋**。 LR 先左后右，RL 先右后左。

加粗部分就是overlap，两块重复共享。

overlap的作用：上下文不割裂，知识点不会被拦腰切断，相邻块共享上下文，不管命中哪一块，都能带上前后关联信息。**RAG必须设overlap**。


