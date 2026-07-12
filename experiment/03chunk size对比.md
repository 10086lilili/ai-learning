实验目的:对比不同Chunk Size切分同一段教材文本后的效果，

实验方法:对同一段文本按不同Chunk Size切分，观察切分后每个chunk的完整性（是否在句子中间被切断）、片段数量、以及每个片段是否能独立表达完整语义。

![实验](https://github.com/10086lilili/ai-learning/blob/main/diagrams/03exp%E4%BB%A3%E7%A0%81%E6%88%AA%E5%9B%BE.png?raw=true)

![实验](https://github.com/10086lilili/ai-learning/blob/main/diagrams/03exp%E5%AE%9E%E9%AA%8C%E7%BB%93%E6%9E%9C%E6%88%AA%E5%9B%BE.jpg?raw=true)
实验结果:

| Chunk Size | 切分片段数 | 是否常在句中被切断 | 语义完整性 |
|-----|--------|-------|----|
| 200字 | 7 | 大量句子中途截断 | 差，单段只有零散短句，没有完整知识点	 |
| 400字 | 3 |少量句子截断 | 一般，部分片段刚好覆盖单个定义	 |
| 600字 | 2 |极少截断|良好，单段完整承载一类知识点 |

结果分析：太小的chunk语义不完整，太大的chunk可能一段里混杂多个知识点

