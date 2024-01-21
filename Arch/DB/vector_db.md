# 向量数据库

什么是向量数据库？
简单下个定义，因为喂给Transformer的知识首先需要做embedding，所以用于存储embedding之后数据的数据库即可称为向量数据库。

向量数据库需要解决什么问题？因为向量数据库是基于embedding之后的向量的存储与检索。所以首先需要提供存储能力，其次更重要的是检索。 即如何根据一个query快速找到相关的embedding内容。 关于检索，主要是计算两个向量之间的相似度。

推荐的计算两个向量之间距离推荐的算法为： 余弦相似度函数，参见 [主流向量数据库一览](https://zhuanlan.zhihu.com/p/628148081) 


向量数据库的特点：
1. 支持向量相似性搜索
2. 支持不同类型的相似性度量
3. 支持各种类型的数据源，例如文本，图像，音频，视频。 

[10个最流行的向量数据库【AI】](https://blog.csdn.net/shebao3333/article/details/130438194)


https://zhuanlan.zhihu.com/p/628148081



## Milvus 

国产，[Milvus中文文档](https://www.milvus-io.com/)



## Pinecone 

国外

## Faiss

Meta的Faiss是一个用于高效相似性搜索和密集向量聚类的库。 它包含搜索任意大小的向量集的算法，直到可能不适合 RAM 的向量集。 它还包含用于评估和参数调整的支持代码。

