03 - Chunk（文本切分）设计

## 今天研究的问题
教材内容应该按多大的粒度切分成Chunk，才能让Retriever检索出
既相关又有完整上下文的片段？

## 为什么研究
Day2设计的RAG流程里，Retriever要去"知识库"里检索相关片段，
但知识库不是整本教材，而是提前切好的一段一段文本。
切分方式直接影响检索结果的质量，所以需要先设计好切分策略。

## 切分粒度的权衡
- 切得太小（如按句子切）：单个片段信息不完整，缺少上下文，
  LLM拿到片段后可能看不懂讲的是什么
- 切得太大（如按章节切）：单个片段包含太多无关内容，
  检索出来的"相关片段"里夹杂大量噪音，浪费Prompt空间，
  也可能让LLM抓不住重点

---

# Reading

今天阅读：

1.LangChain Text Splitters

2.Pinecone Chunking Strategies

3.Document Loader

---

# Knowledge Summary

今天了解到：

① Chunk是文档切分。

② 每一个Chunk最终都会变成Embedding。

③ Retriever不是搜索整本教材。

④ Retriever搜索Chunk。

⑤ Chunk大小影响检索质量。

---

# My Understanding

我的平台：

教材：

↓

Chunk

↓

Embedding

↓

Retriever

↓

Prompt

↓

讯飞

↓

题目。

如果Chunk设计不好。

Retriever找到错误知识。

生成题目也会错误。

---

# Problems

目前：

还不知道：

Overlap最佳设置。

---

# Achievement

完成：

✅ Chunk学习

✅ Chunk实验

---

# Tomorrow

学习Embedding。


⸻

Chunk_Design.md（技术文档）

# Chunk Design

---

# 为什么需要Chunk？

教材通常几十万字。

LLM无法一次处理。

因此需要切分。

---

# 什么是Chunk？

Chunk：

知识片段。

例如：

数据结构

↓

树

↓

AVL树

↓

平衡调整

每一个都是Chunk。

---

# 为什么不能太小？

例如：

Chunk=50

AVL树一句话。

上下文丢失。

---

# 为什么不能太大？

例如：

Chunk=3000

包含：

树

图

排序

全部一起。

Retriever容易找到无关内容。

---

# 我的平台如何设计？

教材

↓

Chunk

↓

Embedding

↓

Vector Database

↓

Retriever

↓

Question Agent
