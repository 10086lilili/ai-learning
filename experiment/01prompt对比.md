## 01Prompt对比实验：验证是否需要知识检索

实验目的:验证prompt调用(只给ai简单提问，无附加参考资料及约束条件）是否足以生成符合课程要求的题目，

实验方法：分别用两种Prompt调用deeepseekAPI，对比生成结果。

Prompt A（直接问）：“生成一道AVL树的练习题”

Prompt B（指定教材范围）：“根据《数据结构》教材第五章AVL树的旋转操作，生成一道选择题”

！[代码](https://github.com/10086lilili/ai-learning/blob/main/diagrams/01exp%E4%BB%A3%E7%A0%81%E6%88%AA%E5%9B%BE.png?raw=true))

实验结果

！[实验结果截图](https://github.com/10086lilili/ai-learning/blob/main/diagrams/01exp%E4%BB%A3%E7%A0%81%E7%BB%93%E6%9E%9C%E6%88%AA%E5%9B%BE.jpg?raw=true)


结果分析:

PromptA 生成的题目内容比较泛化，可能涉及教材没有覆盖的知识点；

PromptB 因为指定了具体章节范围，题目更贴合教材课本内容，
但仍然依赖于人工手动指定章节，无法自动检索对应教材内容。

实验结论：仅靠Prompt本身无法自动定位教材内容，需要引入检索环节（Retriever + 知识库），让系统自动找到相关教材片段并注入Prompt，而不是依赖人工手动写死章节信息。

