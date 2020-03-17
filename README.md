# HAN-keras
层次注意力机制用于文本分类


为什么选择了HAN做文本分类？
①　最开始尝试了TFIDF和TextCNN。TFIDF主要是基于词频的特征构建，然后用逻辑回归作为分类器，不管是特征构建还是分类器都是比较简单的、线性的，其一般作为算法选择的baseline，用于项目初期的尝试。
②　在这个基础上又尝试了TextCNN来做分类，但TextCNN有一个很明显的缺点，尤其是对于我们的数据-结构比较规范的管理文档。TextCNN算法中的GlobalMaxPooling操作会失去文章的结构化信息，而恰恰这些结构化特征对于我们的文本来说是重要的，因此其效果并不是太理想。一般认为TextCNN比较适合于文章类别可以通过一些重要的关键词或关键短语来识别的数据情况。
③　之所以选择HAN即层次注意力模型，是因为该算法从两方面保证了文章完整的结构和语义信息提取1、 单词级别的注意力机制。可以有效地抽取出一句话中的重要单词或短语。2、句子级别的注意力机制。把文章分句之后，学习句子的重要程度，有效提取关键句子。这两方面的特征构建方式，使得模型具备更强的特征抽取能力，保证最终的分类效果。
此外，在实际的算法工作中，模型的可解释性也是算法选择时的一个重要考量甚至在某些时候决定了实际上线的模型。通过对HAN在单词和句子层面的注意力权重可视化，很好地提升了模型的可解释性。
![atten_vis](https://devopedia.org/images/article/237/8404.1573837211.png)
