<h1 align="center">NLP-Paper</h1>
<div align="center">

[![Blog](https://img.shields.io/badge/blog-@DengBoCong-blue.svg?style=social)](https://www.zhihu.com/people/dengbocong)
[![Paper Support](https://img.shields.io/badge/paper-repo-blue.svg?style=social)](https://github.com/DengBoCong/nlp-paper)
![Stars Thanks](https://img.shields.io/badge/Stars-thanks-brightgreen.svg?style=social&logo=trustpilot)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=social&logo=appveyor)

</div>


更新一些在我学习过程中阅读过的且感觉不错的论文，对于一些经典或思路很新奇的论文，会进行精读，并写一些阅读笔记同步上传更新。(内容同步更新到[知乎](https://www.zhihu.com/people/dengbocong)、[CSDN](https://dengbocong.blog.csdn.net/))，**论文按照时间顺序排放**。

**注：对部分复现论文代码以及NLP其他工具代码放在这 ☞ [paper-code](https://github.com/DengBoCong/paper/tree/master/paper-code)**

# Contents | 内容
+ [综述](#综述)
+ [预训练](预训练)
+ [模型](#模型)
+ [对话系统](#对话系统)
+ [语音系统](#语音系统)
+ [聚类](#聚类)
+ [文本相似度(匹配)](文本相似度(匹配))
+ [向量检索](#向量检索)
+ [深度学习](#深度学习)
+ [机器学习](#机器学习)
+ [数据集](#数据集)
+ [评估](#评估)

# Summarize | 综述
+ [A Survey on Dialogue Systems:Recent Advances and New Frontiers](https://arxiv.org/pdf/1711.01731.pdf)：对话系统的最新研究和方向 | Chen et al,2017

+ [Recent Advances and Challenges in Task-oriented Dialog Systems](https://arxiv.org/pdf/2003.07490.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/260194067)：面向任务型对话系统的最新研究和方向 | Zhang et al,2020

+ [Pre-trained Models for Natural Language Processing: A Survey](https://arxiv.org/pdf/2003.08271.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/352152573)：超详细的NLP预训练语言模型总结清单 | Xipeng Qiu et al,2020

+ [Recent Advances in Deep Learning Based Dialogue Systems: A Systematic Survey](https://arxiv.org/pdf/2105.04387.pdf): 对话系统综述：新进展新前沿 | JinJie Ni et al,2021

+ [A Survey on Neural Network Interpretability](https://arxiv.org/pdf/2012.14261.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/341153242)：关于神经网络可解释性的一篇综述，整理的挺不错的，不过就是相关领域前沿探索不足 | Yu Zhang et al,2020

+ [A Comprehensive Survey and Experimental Comparison of Graph-Based Approximate Nearest Neighbor Search](https://arxiv.org/pdf/2101.12631.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/415320221)：论文是一篇关于graph-base的向量召回综述，聚焦实现了效率和精度最优权衡的近邻图索引，综述了 13 种具有代表性相关算法，包括NSW、HNSW等在内的优秀算法，并提出一个统一评估的pipeline | Mengzhao Wang et al,2021

+ [Data Augmentation Approaches in Natural Language Processing: A Survey](https://arxiv.org/pdf/2110.01852.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/420295576)：哈工大的工作，对15中NLP数据增强方法进行了总结和对比，有详细的优缺点说明，还有一些使用技巧，实用性非常强，需要的时候可以详细的参考原文以及相关的文献的应用细节。几个开源工具：Easy DA、UNsupervised DA、nlpaug、eda_nlp_for_Chinese | Bohan Li et al,2021

# Pretraining | 预训练
+ [Character-Aware Neural Language Models](https://arxiv.org/pdf/1508.06615.pdf)：提供一种功能强大，功能强大的语言模型，其可编码子词相关性，同时解决先前模型的罕见字问题，使用更少的参数获得可比较的表现力。 | Yoon et al,2015

+ [Neural Machine Translation of Rare Words with Subword Units](https://arxiv.org/pdf/1508.07909.pdf)：就是我们所熟知的Byte Pair Encoding，是一种使用一些出现频率高的byte pair来组成新的byte的方法 | Sennrich et al,2015

+ [Achieving Open Vocabulary Neural Machine Translation with Hybrid Word-Character Models](https://arxiv.org/pdf/1604.00788.pdf)：一个非常出色的框架，主要是在word-level进行翻译，但是在有需要的时候可以很方便的使用Character-level的输入。 | Luong et al,2016

+ [Learning Character-level Representations for Part-of-Speech Tagging](http://proceedings.mlr.press/v32/santos14.pdf)：Character-level去构建word-level，该网络结构主要是对字符进行卷积以生成单词嵌入，同时使用固定窗口对PoS标记的字嵌入进行操作。 | Jason et al,2016

+ [A Joint Model for Word Embedding and Word Morphology](https://arxiv.org/pdf/1606.02601.pdf)：该模型的目标与word2vec相同，但是使用的是Character-level的输入，它使用了双向的LSTM结构尝试捕获形态并且能够推断出词根。 | Kris et al,2016

+ [Enriching Word Vectors with Subword Information](https://arxiv.org/pdf/1607.04606.pdf)：word2vec的升级版，对于具有大量形态学的稀有词和语言有更好的表征，它也可以说是带有字符n-gram的w2v skip-gram模型的扩展。 | Piotr et al,2016

+ [Google’s Neural Machine Translation System: Bridging the Gap between Human and Machine Translation](https://arxiv.org/pdf/1609.08144.pdf)：wordpiece作为BERT使用的分词方式，其生成词表的方式和BPE非常相近，区别在于BPE选择频率最高的相邻字符对进行合并，而wordpiece是基于概率生成的。 | Yonghui et al,2016

+ [Fully Character-Level Neural Machine Translation without Explicit Segmentation](https://arxiv.org/pdf/1610.03017.pdf)：比较经典的Character-Level的Subword算法模型 | Jason et al,2016

+ [Subword Regularization: Improving Neural Network Translation Models with Multiple Subword Candidates](https://arxiv.org/pdf/1804.10959.pdf)：unigram在给定词表及对应概率值下，直接以最大化句子的likelihood为目标来直接构建整个词表 | Kudo et al,2018

+ [How to Fine-Tune BERT for Text Classification?](https://arxiv.org/pdf/1905.05583.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/358516009)：BERT在Text Classification上的一些微调实验 | Xipeng Qiu et al,2019

+ [Pretraining Methods for Dialog Context Representation Learning](https://arxiv.org/pdf/1906.00414.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/240742891)：作者列举了四种针对对话上下文表示的预训练方法，其中两种是作者新提出的 | Shikib et al,2019

+ [Pre-trained Models for Natural Language Processing: A Survey](https://arxiv.org/pdf/2003.08271.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/352152573)：超详细的NLP预训练语言模型总结清单 | Xipeng Qiu et al,2020

+ [TOD-BERT: Pre-trained Natural Language Understanding for Task-Oriented Dialogue](https://arxiv.org/pdf/2004.06871.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/377845426)：任务导向型对话的预训练自然语言理解模型 | Chien-Sheng Wu et al,2020

+ [LogME: Practical Assessment of Pre-trained Models for Transfer Learning](https://arxiv.org/pdf/2102.11005.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/358844524)：一种通用且快速的评估选择适合下游任务的预训练模型的打分方法，logME | Kaichao You et al,2021

+ [Are Pre-trained Convolutions Better than Pre-trained Transformers?](https://arxiv.org/pdf/2105.03322.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/380195756)：将Transformer的Attention换成了卷积，尝试预训练模型新方式 | Yi Tay et al,2021

# Model | 模型
+ [Efficient Estimation of Word Representations in Vector Space](https://arxiv.org/pdf/1301.3781.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/26306795)：Word2vec开山之作之一，专门讲训练中的两个trick：hierarchical softmax 和 negative sampling | Tomas Mikolov et al,2013

+ [Distributed Representations of Words and Phrases and their Compositionality](https://arxiv.org/pdf/1310.4546.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/26306795)：Word2vec开山之作之一，在前人基础上提出更精简的语言模型框架并用于生成词向量，这个框架就是 Word2vec | Tomas Mikolov et al,2013

+ [Convolutional Neural Networks for Sentence Classification](https://arxiv.org/pdf/1408.5882.pdf)：经典的TextCNN，static/non-static几种特征向量学习方式 | Yoon Kim et al,2014

+ [Pointer Networks](https://arxiv.org/pdf/1506.03134.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/48959800)：原文是围绕解决凸包而设计的的网络结构，直接使用Attention的权重用于预测，能够适应输入的规模，后面许多网络结构应用发展成了Copying Mechanism来解决OOV问题 | Oriol Vinyals et al,2015

+ [Training Very Deep Networks](https://arxiv.org/pdf/1507.06228.pdf) | [阅读笔记](https://cloud.tencent.com/developer/article/1148375)：经典的Highway networks，基于深层的CNN堆叠网络，使用transform gate和carry gate（其实后来被统一称为Shortcut），将浅层特征信息带到深层中，以此来解决深度网络中梯度发散，难以训练的问题 | Rupesh Kumar Srivastava et al,2015

+ [Deep Residual Learning for Image Recognition](https://openaccess.thecvf.com/content_cvpr_2016/papers/He_Deep_Residual_Learning_CVPR_2016_paper.pdf) [阅读笔记](https://cloud.tencent.com/developer/article/1148375)：经典的ResNet，基于深层的CNN堆叠网络，利用了残差连接（ResNet中是跨越了2层或3层），解决深度模型中的退化问题，最优的残差结构是把BN和ReLU都提前，成为pre-activation | Kaiming He et al,2016

+ [Incorporating Copying Mechanism in Sequence-to-Sequence Learning](https://arxiv.org/pdf/1603.06393.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/415502906)：CopyNet模型，使用Copying Mechanism来缓解未登录词问题的模型，在文本摘要等生成词多含输入词的任务中，效果不错 | Jiatao Gu et al,2016

+ [Language Modeling with Gated Convolutional Networks](https://arxiv.org/pdf/1612.08083.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/395977833)：受LSTM门控机制的启发，将线性门控机制应用于卷积结构，文中对比GLU、GTU等结构性能 | Yann N. Dauphin et al,2016

+ [Densely Connected Convolutional Networks](https://openaccess.thecvf.com/content_cvpr_2017/papers/Huang_Densely_Connected_Convolutional_CVPR_2017_paper.pdf) | [阅读笔记](https://cloud.tencent.com/developer/article/1148375)：CVPR 2017的Best Paper，提出了DenseNet，借鉴highway networks和ResNet的思路，DenseNet将shortcut用到了“极致”——每两层之间都添加shortcut，当然具体实现中使用了一些tricks防止模型过大的问题 | Gao Huang et al,2017

+ [A SIMPLE BUT TOUGH-TO-BEAT BASELINE FOR SENTENCE EMBEDDINGS](https://openreview.net/pdf?id=SyK00v5xx)：Smooth Inverse Frequency，一种简单但是效果好的Sentence Embedding方法 | Sanjeev Arora et al,2017

+ [Get To The Point: Summarization with Pointer-Generator Networks](https://arxiv.org/pdf/1704.04368.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/419659043)：结合Copying Mechanism和Coverage mechanism两种技巧的LSTM-Base模型，一定程度上解决OOV和重复词问题，经典值得一读 | Abigail See et al,2017

+ [Supervised Learning of Universal Sentence Representations from Natural Language Inference Data](https://arxiv.org/pdf/1705.02364.pdf)：InferSent，通过不同的encoder得到Sentence Embedding，并计算两者差值、点乘得到交互向量，从而得到相似度。 | Alexis Conneau et al,2017

+ [Attention Is All You Need](https://arxiv.org/pdf/1706.03762.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/250946855)：Transformer的开山之作，值得精读 | Ashish et al,2017

+ [Unsupervised Random Walk Sentence Embeddings: A Strong but Simple Baseline](https://www.aclweb.org/anthology/W18-3012.pdf)：Unsupervised Smooth Inverse Frequency，USIF改进SIF对句向量长度敏感，在相似度任务上提升很大 | Kawin Ethayarajh Arora et al,2018

+ [Multi-Cast Attention Networks for Retrieval-based Question Answering and Response Prediction](https://arxiv.org/pdf/1806.00778.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/349369847)：一种用于通用序列对建模的整体架构，结合多种注意力机制进行特征增强 | Yi Tay et al,2018

+ [Sliced Recurrent Neural Networks](https://arxiv.org/ftp/arxiv/papers/1807/1807.02291.pdf)：切片RNN网络，尝试突破RNN时序限制的模型 | Zeping Yu et al,2018

+ [BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding](https://arxiv.org/pdf/1810.04805.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/269997771)：BERT的顶顶大名，使用Transformer的Encoder双向架构 | Devlin et al,2018

+ [Pay Less Attention With Lightweight And Dynamic Convolutions](https://arxiv.org/pdf/1901.10430.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/396143249)：论文研究Lightweight、Dynamic Convolutions，卷积结构同样能够达到和Self-Attention媲美的效果 | Felix Wu et al,2019

+ [XLNet: Generalized Autoregressive Pretraining for Language Understanding](https://arxiv.org/pdf/1906.08237.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/361737484)：XLNet--自回归语言模型的复兴，30多项任务超越BERT | Zhilin Yang et al,2019

+ [CTRL: A Conditional Transformer Language Model For Controllable Generation](https://arxiv.org/pdf/1909.05858.pdf)
| [阅读笔记](https://zhuanlan.zhihu.com/p/405493225)：CTRL语言模型，提供Control Code进行定向文本生成，相较于GPT可对文本风格进行控制 | Keskar et al,2019

+ [Reformer: The Efficient Transformer](https://arxiv.org/pdf/2001.04451.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/411882151)：使用LSH Attention、Reversible layers、Chunking FFN layers，降低Transformer计算复杂度和内存空间消耗 | Nikita Kitaev et al,2020

+ [Synthesizer: Rethinking Self-Attention for Transformer Models](https://arxiv.org/pdf/2005.00743.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/380602965)：在Transformer架构下，对Self-Attention计算的探索研究，看完会对Self-Attention有个新认识 | Yi Tay et al,2020

+ [Informer: Beyond Efficient Transformer for Long Sequence Time-Series Forecasting](https://arxiv.org/pdf/2012.07436.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/351321328)：一种效果远超Transformer的长序列预测模型，针对LSTF问题上的研究改进 | Haoyi Zhou et al,2020

# Dialogue | 对话系统
+ [The Hidden Information State model: A practical framework for POMDP-based spoken dialogue management](https://www.sciencedirect.com/science/article/abs/pii/S0885230809000230)：关于对话状态管理的文章，可以用来补充相关背景知识 | Young et al,2010

+ [Context Sensitive Spoken Language Understanding Using Role Dependent LSTM Layers](https://www.merl.com/publications/docs/TR2015-134.pdf)：使用LSTM在SLU方面做的工作，通过agent和client角色划分，能够解决多轮对话中的歧义问题 | Hori et al,2015

+ [A Neural Conversational Model](https://arxiv.org/pdf/1506.05869.pdf)：Seq2Seq结构的对话模型 | Oriol et al,2015

+ [A Network-based End-to-End Trainable Task-oriented Dialogue System](https://arxiv.org/pdf/1604.04562.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/261701071)：非常值得一读的任务型对话模型架构 | Wen et al,2016

+ [Neural Belief Tracker: Data-Driven Dialogue State Tracking](https://arxiv.org/pdf/1606.03777.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/262289823)：NBT框架，理解Belief state和tracking的好文 | Young et al,2016

+ [Attention-Based Recurrent Neural Network Models for Joint Intent Detection and Slot Filling](https://arxiv.org/pdf/1609.01454.pdf)：使用Attention-Based的RNN模型进行联合意图识别和槽位填充，达到不错的效果 | Bing Liu et al,2016

+ [Sequential Matching Network: A New Architecture for Multi-turn Response Selection in Retrieval-Based Chatbots](https://arxiv.org/pdf/1612.01627v2.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/270554147)：SMN检索式对话模型，多层多粒度提取信息 | Devlin et al,2016

+ [Latent Intention Dialogue Models](https://arxiv.org/pdf/1705.10229.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/263034049)：离散潜在变量模型学习对话意图的框架 | Wen et al,2017

+ [An End-to-End Trainable Neural Network Model with Belief Tracking for Task-Oriented Dialog](https://arxiv.org/pdf/1708.05956.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/260345363)：面向任务的对话系统的新型端到端可训练神经网络模型 | Liu et al,2017

+ [Multi-Turn Response Selection for Chatbots with Deep Attention Matching Network](https://www.aclweb.org/anthology/P18-1103.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/306846122)：DAM检索式对话模型，完全基于注意力机制的多层多粒度提取信息 | Xiangyang et al,2018

+ [Slot-Gated Modeling for Joint Slot Filling and Intent Prediction](https://aclanthology.org/N18-2118.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/413261222)：提出了Slot-Gated机制，联合意图识别和槽位填充效果提升 | Chih-Wen Goo et al,2018

+ [Global-Locally Self-Attentive Dialogue State Tracker](https://arxiv.org/pdf/1805.09655.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/266982344)：全局-局部自注意力状态跟踪 | Zhong et al,2018

+ [Sequence-to-Sequence Data Augmentation for Dialogue Language Understanding](https://arxiv.org/pdf/1807.01554.pdf)：使用seq2seq生成模型对语义文本进行数据增强，核心步骤为Delexicalisation->Diversity rank->generation->surface realisation | Yutai Hou et al,2018

+ [Data Augmentation with Atomic Templates for Spoken Language Understanding](https://arxiv.org/pdf/1908.10770.pdf)：使用Atomic Templates（act-slot-value）进行对话数据增强，使用seq2seq生成模型进行语句生成 | Zijian Zhao et al,2019

+ [A Closer Look At Feature Space Data Augmentation For Few-Shot Intent Classification](https://arxiv.org/pdf/1910.04176.pdf)：针对SLU的Intent分类任务，对其文本数据进行数据增强并比较效果，其中Linear+Transfer learning效果最佳 | Varun Kumar et al,2019

+ [Dense Passage Retrieval for Open-Domain Question Answering](https://arxiv.org/pdf/2004.04906.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/403589222)：DPR一种高效的开放域问答检索技术，应用了BERT进行编码 | Karpukhin et al,2020

+ [TOD-BERT: Pre-trained Natural Language Understanding for Task-Oriented Dialogue](https://arxiv.org/pdf/2004.06871.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/377845426)：任务导向型对话的预训练自然语言理解模型 | Chien-Sheng Wu et al,2020

+ [Leveraging Passage Retrieval with Generative Models for Open Domain Question Answering](https://arxiv.org/pdf/2007.01282.pdf)：Fusion-in-Decoder生成式阅读理解模型 | Izacard et al,2020

+ [DISTILLING KNOWLEDGE FROM READER TO RETRIEVER FOR QUESTION ANSWERING](https://openreview.net/pdf?id=NTEz-6wysdb) | [阅读笔记](https://zhuanlan.zhihu.com/p/372694270)：一种模型训练模型的开放域问答方法 | Izacard et al,2021

+ [Retrieve & Memorize: Dialog Policy Learning with Multi-Action Memory](https://arxiv.org/pdf/2106.02317.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/415170940)：联合检索和记忆块的多action的Dialog Policy Learning模型，在action生成和response生成上效果SOTA | Yunhao Li et al,2021

+ [Increasing Faithfulness in Knowledge-Grounded Dialogue with Controllable Features](https://arxiv.org/pdf/2107.06963.pdf)：通过可控特征来增加知识对话系统的学习 | Rashkin et al,2021

+ [Constraint based Knowledge Base Distillation in End-to-End Task Oriented Dialogs](https://arxiv.org/pdf/2109.07396.pdf)：基于KB的End2End的Task-Oriented的对话系统，使用pairwise相似度过滤相关信息来获得KB中的n元结构，就这一点上倒没有什么新奇，只不过相对于之前的方式修改的entity格式。不过在避免检索到部分entity相似但并不是目标的record的情况，作者加入了辅助的损失函数用于embedding constraint，这种做法确实减少了相同entity之间的相似性，从而提高record的可靠性，值得借鉴。基于现有的F1指标的缺点，提出multiset entity F1 | Dinesh Raghu et al,2021

# Speech | 语音系统
+ [Attention-Based Models for Speech Recognition](https://proceedings.neurips.cc/paper/2015/file/1068c6e4c8051cfd4e9ea8072e3189e2-Paper.pdf)：Tacotron2使用的Location Sensitive Attention  |  Chorowski et al,2015

+ [Tacotron: A Fully End-To-End Text-To-Speech Synthesis Model](http://bengio.abracadoudou.com/cv/publications/pdf/wang_2017_arxiv.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/337042442)：Tacotron，端到端的语音合成系统 | Yuxuan et al,2017

+ [Natural TTS Synthesis By Conditioning Wavenet On Mel Spectrogram Predictions](https://arxiv.org/pdf/1712.05884.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/337042442)：Tacotron2，相较于Tacotron有着更好的性能，使用WaveNet作为Vocoder | Jonathan et al,2017

+ [Syllable-Based Sequence-to-Sequence Speech Recognition with the Transformer in Mandarin Chinese](https://arxiv.org/pdf/1804.10752.pdf)：使用Transformer应用在普通话语音识别，数据集是HKUST datasets  |  Shiyu et al,2018

+ [Neural Speech Synthesis with Transformer Network](https://arxiv.org/pdf/1809.08895.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/332316226)：本文受Transformer启发，使用多头自注意力机制取代Tacotron2中的RNN结构和原始注意力机制。 | Naihan et al,2018

+ [A Comparative Study on Transformer vs RNN in Speech Applications](https://arxiv.org/pdf/1909.06317.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/309390439)：Transformer应用在语音领域上与RNN对比的论文，并在ESPnet上面开源了模型代码 | Nanxin et al,2019

# Clustering | 聚类
+ [Accelerating exact k-means algorithms with geometric reasoning](http://portal.acm.org/citation.cfm?doid=312129.312248) | [阅读笔记](https://www.zhihu.com/question/494753171/answer/2204649294)：K-Means引入计算机中的那片论文，K-Means属于Partition-based methods，思想是初始化中心点，然后通过启发式算法，达到”类内的点都足够近，类间的点都足够远“的目标 | et al Dan Pelleg,1999

+ [Mean Shift: A Robust Approach toward Feature Space Analysis](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.76.8968&rep=rep1&type=pdf) | [阅读笔记](https://www.zhihu.com/question/494753171/answer/2204649294)：实现的方法是滑动窗口的算法，在每次迭代中，通过将中心点移动到窗口内所有点的平均值位置（因此得名），将滑动窗口中心移向密度较高的区域。滑动窗口内的密度与其内部的点数成正比。通过转换到窗口内点的平均值位置，窗口将逐渐移动到有着更高点密度的区域。优点：Mean-Shift的最大优势就是可以自动发现簇的数量而不需要人工选择；簇的中心向最大密度点聚合的事实也是非常令人满意的，因为它可被非常直观地理解并很自然地契合数据驱动；可以处理任意形状的簇类；算法只需设置半径这一个参数，半径影响数据集的核密度估计；算法结果稳定，不需要进行类似K均值的样本初始化；缺点：不足就是窗口大小/半径“r”的选择可能是非平凡的；半径设置的太小，收敛太慢，簇类个数过多；半径设置的太大，一些簇类可能会丢失。对于较大的特征空间，计算量非常大 | Dorin Comaniciu et al,2002

+ [k-means++: The Advantages of Careful Seeding](http://ilpubs.stanford.edu:8090/778/1/2006-13.pdf) | [阅读笔记](https://www.zhihu.com/question/494753171/answer/2204649294)：原始K-Means（随机选择簇中心）对于初始化簇中心敏感，因此k-means++进行了改进，随机选择第一个初始中心点，计算其他点与该中心点的距离，按照距离远的以较大的概率被选中来选择第二个初始中心点，一次类推 | et al David Arthur,2006

+ [Clustering by Passing Messages Between Data Points](https://warwick.ac.uk/fac/sci/dcs/research/combi/seminars/freydueck_affinitypropagation_science2007.pdf) | [阅读笔记](https://www.zhihu.com/question/494753171/answer/2204649294)：其基本思想是将全部样本看作网络的节点，然后通过网络中各条边的消息传递计算出各样本的聚类中心。聚类过程中，共有两种消息在各节点间传递，分别是responsibility和availability 。AP算法通过迭代过程不断更新每一个点的吸引度和归属度值，直到产生m个高质量的Exemplar。优点是无需指定聚类“数量”参数；聚类中心点由实际的样本点中产生；初始值不敏感，且对距离矩阵的对称性没要求。AP通过输入相似度矩阵来启动算法，因此允许数据呈非对称，数据适用范围非常大，鲁棒性很好；误差低；缺点是AP聚类应用中需要手动指定Preference和Damping factor，这其实是原有的聚类“数量”控制的变体，且算法复杂度较高 | Brendan J. Frey et al，2007

+ [A Tutorial on Spectral Clustering](https://arxiv.org/pdf/0711.0189.pdf) | [阅读笔记](https://www.zhihu.com/question/494753171/answer/2204649294)：不是原论文，但是这一篇对Spectral Clustering讲的非常好，谱聚类（Spectral Clustering），就是先用Laplacian eigenmaps对数据降维（简单地说，就是先将数据转换成邻接矩阵或相似性矩阵，再转换成Laplacian矩阵，再对Laplacian矩阵进行特征分解，把最小的K个特征向量排列在一起），然后再使用k-means完成聚类。谱聚类是个很好的方法，效果通常比k-means好，计算复杂度还低，这都要归功于降维的作用。优点：谱聚类只需要数据之间的相似度矩阵，因此对于处理稀疏数据的聚类很有效。这点传统聚类算法比如K-Means很难做到；由于使用了降维，因此在处理高维数据聚类时的复杂度比传统聚类算法好。缺点：如果最终聚类的维度非常高，则由于降维的幅度不够，谱聚类的运行速度和最后的聚类效果均不好；聚类效果依赖于相似矩阵，不同的相似矩阵得到的最终聚类效果可能很不同 | Ulrike von Luxburg et al,2007

+ [Scalable K-Means++](https://theory.stanford.edu/~sergei/papers/vldb12-kmpar.pdf) | [阅读笔记](https://www.zhihu.com/question/494753171/answer/2204649294)：K-Means++由于它的采样策略，所以难以并行，限制了其用于大规模数据集上。为了解决这个问题，k-means II 改变取样策略（以oversampling的方式），初始化一个中心点，然后循环log(n)次，每次按照一个概率计算公式选择多个point加入到中心集，最后得到的候选中心集再通过k-means++对候选中心集进行聚类，选出k个簇中心 | Bahman Bahmani et al,2012

+ [Approximate K-Means++ in Sublinear Time](https://www.aaai.org/ocs/index.php/AAAI/AAAI16/paper/viewFile/12147/11759) | [阅读笔记](https://www.zhihu.com/question/494753171/answer/2204649294)：K-MC2区别于k-means II的采样方法，使用MCMC采样，其主要思想是将K-Means++中的采样方法替换为基于MCMC（马尔科夫链蒙特卡洛）采样方法（MCMC的介绍可以参考：[MCMC随机采样](https://zhuanlan.zhihu.com/p/30003899)）。用MCMC的方法采样出长为M的数列，取最后（K-1）个数作为中心点初始化，target distribution是距离的函数，满足距离越远，概率越大(表达的含义同k-means++)，proposal distribution是一个常函数，1/样本数。 | Olivier Bachem et al,2016

+ [Fast and Provably Good Seedings for k-Means](https://proceedings.neurips.cc/paper/2016/file/d67d8ab4f4c10bf22aa353e27879133c-Paper.pdf) | [阅读笔记](https://www.zhihu.com/question/494753171/answer/2204649294)：AFK-MC2基于K-MC2改进，由于K-MC2的proposal distribution是常函数，不够鲁棒，因此AFK-MC2将与距离有关的分布作为一个term加入原始的分布中，优化proposal distribution | Olivier Bachem et al,2016

+ [Robust and Rapid Clustering of KPIs for Large-Scale Anomaly Detection](https://netman.aiops.org/~peidan/ANM2018/8.DependencyDiscovery/LectureCoverage/2018IWQOS_ROCKA.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/50698719)：关于快速时序聚类的文章，提出ROCKA系统架构，包括了数据预处理、基线提取、相似性度量、基于密度的聚类算法。ROCKA算法仅仅是使用了派发策略，单是并未在有效的利用过程中的计算结果，导致在派发过程中复杂度较高 | Zhihan Li et al,2018

# Text Similarity | 文本相似度(匹配)
+ [Siamese Recurrent Architectures for Learning Sentence Similarity](https://scholar.google.com/scholar_url?url=https://ojs.aaai.org/index.php/AAAI/article/view/10350/10209&hl=zh-CN&sa=T&oi=gsb-gga&ct=res&cd=0&d=7393466935379636447&ei=KQWzYNL5OYz4yATXqJ6YCg&scisig=AAGBfm0zNEZZez8zh5ZB_iG7UTrwXmhJWg)：Siamese LSTM，一个用来计算句对相似度的模型 | Jonas Mueller et al,2016

+ [Learning Text Similarity with Siamese Recurrent Networks](https://aclanthology.org/W16-1617.pdf)：网络包含4层BiLSTM（64-d hidden），最后一层的BiLSTM的hidden state和cell state进行concat，然后在timestep维度进行average处理，并接一个Dense层（激活函数为tanh），得到的两个Embedding Space进行Cosine sim计算，得到的相似度分数E用于损失函数计算，损失函数使用对比损失函数，计算方法为，损失函数正例：1/4(1-E)^2，负例：E^2(如果E<m)，否则0 | Paul Neculoiu et al,2016

# Nearest Neighbor | 向量检索
+ [similarity estimation techniques from rounding algorithms](https://www.cs.princeton.edu/courses/archive/spring04/cos598B/bib/CharikarEstim.pdf) | [阅读笔记](http://tangxman.github.io/2015/12/01/simhash/)：论文提出的SimHash是当年Google用来文本去重的算法。主要做法是将文档提取出一定数量的关键词，然后转换成哈希码并按列相加，1+weight，0-weight，得到的结果按照整数为1，负数为0得到最终的哈希码，然后将哈希码分为m个table，并分别记性计算检索 | Moses S. Charikar et al,2002

+ [Product quantization for nearest neighbor search](https://lear.inrialpes.fr/pubs/2011/JDS11/jegou_searching_with_quantization.pdf) | [阅读笔记](http://vividfree.github.io/%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0/2017/08/05/understanding-product-quantization)：这篇PaperPQ算法的成功开始，PQ是一种量化方法，本质上是数据的一种压缩表达方式（本篇论文使用了KMeans算法，得到质心的codebook），先将向量分成m段，每段分别根据codebook转换成压缩向量，然后使用SDC或ADC算法进行相似搜索。不过论文中进一步进行了改进，提出了IVFADC算法，一种基于倒排索引的ADC算法，分两步，第一步是PQ一遍（成为coarse quantizer），然后用向量减去量化后的向量得到残差，第二步就是在所有得到的残差集合上在进行一次PQ，最后用得到的向量建立倒排索引 | Herve Jegou et al,2011

+ [Fast Search in Hamming Space with Multi-Index Hashing](https://www.cs.toronto.edu/~norouzi/research/papers/multi_index_hashing.pdf) | [阅读笔记](https://tangxman.github.io/2015/12/03/mih/)：主要是解决在汉明空间上的R-Neighbors of query和KNN query，论文提出了一种多分段索引的哈希方法，查询效率达到了次线性，做法是r为查询的汉明距离，将汉明码切分成m段，快速找出每段中汉明距离小于r/m的结果，合并所有结果即为候选集 | Mohammad Norouzi et al,2012

+ [Learning Deep Structured Semantic Models for Web Search using Clickthrough Data](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/cikm2013_DSSM_fullversion.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/421944601)：经典的DSSM语义相似度匹配模型，就是通常我们所说的双塔模型。使用Word Hashing的n-gram，在那个时候还是很独到的，其核心思想是将query和doc映射到到共同维度的语义空间中，通过最大化query和doc语义向量之间的余弦相似度，从而训练得到隐含语义模型，达到检索的目的。负采样1:4 | Po-Sen Huang et al,2013

+ [Optimized Product Quantization](https://www.microsoft.com/en-us/research/wp-content/uploads/2013/11/pami13opq.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/213395313)：PQ的做法是直接简单粗暴的分割原始特征向量，并没有去除相关性，而如果去除相关性之后再进行PQ可以使得检索效果更好，OPQ就提供了是的每个子空间信息均衡的方法，即使用一个正交矩阵来对聚类中心进行旋转，并提供了Non-Parametric和Parametric的两种算法思路 | Tiezheng Ge et al,2013

+ [Locally Optimized Product Quantization for Approximate Nearest Neighbor Search](https://openaccess.thecvf.com/content_cvpr_2014/papers/Kalantidis_Locally_Optimized_Product_2014_CVPR_paper.pdf)：LOPQ实在OPQ的基础上进一步优化，OPQ仅考虑了CodeBook的旋转问题，LOPQ考虑的是每个子空间进行不同的旋转 | Yannis Kalantidis et al,2014

+ [Asymmetric LSH (ALSH) for Sublinear Time Maximum Inner Product Search (MIPS)](https://arxiv.org/pdf/1405.5869.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/111502331)：传统的MIPS问题找不到LSH函数，为此论文提出了一种“非对称LSH”的算法，其核心技巧就是通过“非对称变换”构造向量从而消除待查集合X的向量模长对MIPS结果的影响。巧妙的将问题转换为欧氏距离下，通过LSH函数求出NN的近似解的问题 | Anshumali Shrivastava et al,2014

+ [Speeding Up the Xbox Recommender System Using a Euclidean Transformation for Inner-Product Spaces](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/XboxInnerProduct.pdf)：微软的Inner Product快速计算的方法，主要解决的是Inner Product Top-K Search的问题。通过各种公式证明，将问题简化到一个欧氏距离搜索问题后，使用一个PCA-Tree来求解 | Yoram Bachrach et al,2014

+ [Approximate nearest neighbor algorithm based on navigable small world graphs](sciencedirect.com/science/article/abs/pii/S0306437913001300) | [阅读笔记](https://blog.csdn.net/u011233351/article/details/85116719)：经典的NSW算法，在构建近似DG图的基础上，加入Expressway mechanism。构建时，在朴素插入选近邻连接的思路上，使用废弃列表和动态列表提速 Yury Malkov et al,2014

+ [Clustering is Efficient for Approximate Maximum Inner Product Search](https://arxiv.org/pdf/1507.05910.pdf)：K-Means Tree，使用K-Means进行建树 | Alex Auvolat et al,2015

+ [Deep Compression: Ccompressing Deep Neural Networks With Pruning, Trained Quantization And Huffman Coding](https://arxiv.org/pdf/1510.00149.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/21574328)：ICLR的best paper，主要内容是关于深度学习网络参数的压缩。分为三步，Network pruning，即先训练一个网络，然后把一些权重很小的连接进行剪枝（通过阈值来决定），然后retrain网络。第二步，量化权重；第三步则是使用Huffman coding进行无损编码 | Song Han et al,2015

+ [Efficient and robust approximate nearest neighbor search using Hierarchical Navigable Small World graphs](https://arxiv.org/pdf/1603.09320.pdf) | [阅读笔记](https://blog.csdn.net/u011233351/article/details/85116719)：HNSW算法，在NSW的基础上，引入层次结构实现Expressway mechanism，达到顶层粗查，底层细查的思路 | Yu. A. Malkov et al,2016

# Deep Learning | 深度学习
+ [NEURAL MACHINE TRANSLATION BY JOINTLY LEARNING TO ALIGN AND TRANSLATE](https://arxiv.org/pdf/1409.0473.pdf)：Bahdanau Attention的原文 | Bahdanau et al,2014

+ [Convolutional Neural Networks at Constrained Time Cost](https://arxiv.org/pdf/1412.1710.pdf)：针对卷积网络很好地概述了计算成本以及深度，过滤器尺寸之间的权衡 | Kaiming He et al,2014

+ [Batch Normalization: Accelerating Deep Network Training by Reducing Internal Covariate Shift](https://arxiv.org/pdf/1502.03167.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/340219662)：经典的Batch Normalization原论文 | Sergey et al,2015

+ [Learning both Weights and Connections for Efficient Neural Networks](https://arxiv.org/pdf/1506.02626.pdf)：有一张表格，其中列出了计算与内存访问的相对成本，除此之外还讨论了怎么精简神经网络 | Song Han et al,2015

+ [Effective Approaches to Attention-based Neural Machine Translation](https://arxiv.org/pdf/1508.04025.pdf)：Luong Attention的原文 | Luong et al,2015

+ [Strategies for Training Large Vocabulary Neural Language Models](https://arxiv.org/pdf/1512.04906.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/397084135)：主要是对当时的一些Softmax和Sampling进行总结，顺便提出了Differentiated Softmax方法 | Wenlin Chen et al,2015

+ [Exploring the Limits of Language Modeling](https://arxiv.org/pdf/1602.02410.pdf)：CNN Softmax方法，虽然还是离不开原始的Softmax，但是换了一个视角效果很好 | Rafal Jozefowicz et al,2016

+ [Weight Normalization: A Simple Reparameterization to Accelerate Training of Deep Neural Networks](https://arxiv.org/pdf/1602.07868.pdf)：Weight Normalization是一种在权值维度上进行归一化的方法 | Tim Salimans et al,2016

+ [Layer Normalization](https://arxiv.org/pdf/1607.06450.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/258977332)：层归一化方法，针对Batch Normalization的改进 | Jimmy et al,2016

+ [Instance Normalization:The Missing Ingredient for Fast Stylization](https://arxiv.org/pdf/1607.08022.pdf)：Instance Normalization是一种不受限于批量大小的算法专门用于Texture Network中的生成器网络 | Dmitry Ulyanov et al,2016

+ [Efficient softmax approximation for GPUs](https://arxiv.org/pdf/1609.04309.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/397084135)：Adaptive Softmax，针对GPU的矩阵计算，实现了多倍与普通Softmax计算效率的提升，值得一看 | Edouard Grave et al,2016

+ [Categorical Reparameterization With Gumbel-Softmax](https://arxiv.org/pdf/1611.01144.pdf) | [阅读笔记](https://www.zhihu.com/question/422373907/answer/2260975090)：Gumbel Max由来已久，而这篇文章就是基于Gumbel Max，首次提出并应用Gumbel Softmax的。目标就是使用梯度估计的方法，来解决Categorical Distribution中，使用类似argmax操作导致网络不可微的问题。文章主要探讨了部分隐变量是离散型变量的变分推断问题，比如基于VAE的半监督学习 | Eric Jang et al,2016

+ [Large-Margin Softmax Loss for Convolutional Neural Networks](https://arxiv.org/pdf/1612.02295.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/397084135)：L-Softmax在原Softmax的基础上增加了控制系数m，使得类内距离尽可能小，类间距离尽可能大 | Weiyang Liu et al,2016

+ [An empirical analysis of the optimization of deep network loss surfaces](https://arxiv.org/pdf/1612.04010.pdf)：论文中得出一个结论，即Batch Normalization更有利于梯度下降 | Shibani et al,2016

+ [Cosine Normalization: Using Cosine Similarity Instead of Dot Product in Neural Networks](https://arxiv.org/pdf/1702.05870v5.pdf)：Cosine Normalization是一种将unbounded的向量点积换成夹角余弦操作，从而进行归一化的方法 | Luo Chunjie et al, 2017

+ [Massive Exploration of Neural Machine Translation Architectures](https://arxiv.org/pdf/1703.03906.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/328801239)：展示了以NMT架构超参数为例的首次大规模分析，实验为构建和扩展NMT体系结构带来了新颖的见解和实用建议。 | Denny et al,2017

+ [SphereFace: Deep Hypersphere Embedding for Face Recognition](https://arxiv.org/pdf/1704.08063.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/397084135)：A-Softmax，思路和L-Softmax差不多，区别是对权重进行了归一化 | Weiyang Liu et al,2017

+ [ProjectionNet: Learning Efficient On-Device Deep Networks Using Neural Projections](https://arxiv.org/pdf/1708.00630.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/295636122)：一种叫ProjectionNet的联合框架，可以为不同机器学习模型架构训练轻量的设备端模型。 | Google et al,2017

+ [Additive Margin Softmax for Face Verification](https://arxiv.org/pdf/1801.05599.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/397084135)：AM-Softmax在A-Softmax的最大区别是AM是角度距离，A是余弦距离

+ [Self-Attention with Relative Position Representations](https://arxiv.org/pdf/1803.02155.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/268649069)：对Transformer里面用到的位置编码进行讨论，对自注意力进行改造，从而使用相对位置编码代替硬位置编码 | Mihaylova et al,2018

+ [Group Normalization](https://arxiv.org/pdf/1803.08494.pdf)：Group Normalization是将输入的通道分成较小的子组，并根据其均值和方差归一化这些值 | Yuxin Wu et al,2018

+ [How Does Batch Normalization Help Optimization?](https://arxiv.org/pdf/1805.11604.pdf)：讨论Batch Normalization是如何帮助优化器工作的，主要结论是BN层能够让损失函数更加平滑 | Shibani et al,2018

+ [RelGAN: Relational Generative Adversarial Networks For Text Generation](https://openreview.net/pdf?id=rJedV3R5tm) | [阅读笔记](https://zhuanlan.zhihu.com/p/87605995)：提出了新型的生成器和判别器结构，使得直接用Gumbel Softmax训练出的文本GAN大幅度超过了以往的各种文本GAN模型。主要由三个模块组成，分别是：在生成器上，利用relational memory，使得具有更强表达能力和在长文本上更好的模型能力；在离散数据上，训练GAN利用Gumbel-Softmax Relaxation模型，使得模型简化，替代强化学习启发式算法；在判别器上利用多层词向量表示，使得生成器往更具多样性方面更新 Weili Nie et al,2019

+ [Scheduled Sampling for Transformers](https://arxiv.org/pdf/1906.07651.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/267146739)：在Transformer应用Scheduled Sampling | Mihaylova et al,2019

+ [Consistency of a Recurrent Language Model With Respect to Incomplete Decoding](https://arxiv.org/pdf/2002.02492.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/349675973)：讨论Seq2Seq模型解码停不下来的原因 | Sean Welleck et al,2020

+ [PowerNorm: Rethinking Batch Normalization in Transformers](https://arxiv.org/pdf/2003.07845.pdf)：对于Transformer中BN表现不好的原因做了一定的empirical和theoretical的分析 | Sheng Shen et al,2020

+ [Shortcut Learning in Deep Neural Networks](https://arxiv.org/pdf/2004.07780.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/421175552)：对Shortcut Learning问题进行比较详细的解释和剖析，虽然最后没有给出实际的解决方案（Shortcut Learning问题本身就没有一个体系化的策略，需要根据实际任务而定），不过提供了几种解决的视角 | Robert Geirhos et al,2020

+ [Beyond Accuracy: Behavioral Testing of NLP Models with CheckList](https://arxiv.org/pdf/2005.04118.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/421175552)：ACL2020的Best Paper，基于NLP领域提出了测试体系来指导我们了解 NLP 模型的能力，也能够指导我们去理解问题、解决问题。不同于现代 NLP 模型常常仅关注特定的任务，CheckList 希望去评估一个模型的多方面能力，这些能力有的是模型通用的，有的则是面向特定的任务或领域 | Marco Tulio Ribeiro et al,2020

+ [A Theoretical Analysis of the Repetition Problem in Text Generation](https://arxiv.org/pdf/2012.14660.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/349675973)：讨论Seq2Seq模型解码重复生成的原因 | Zihao Fu et al,2020

# Machine Learning | 机器学习

+ [Optimal Whitening and Decorrelation](https://arxiv.org/pdf/1512.00809.pdf)：提供五种白化方法的数学证明 | Agnan Kessy et al,2015

+ [Gaussian Error Linear Units (GELUS)](https://arxiv.org/pdf/1606.08415.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/349492378)：GELU的目标就是希望在激活（拥有非线性拟合的能力）中加入正则化的思想。ReLU会确定性的将输入乘上一个0或者1，Dropout则是随机乘上0。而GELU也是通过将输入乘上0或1来实现这个功能，但是输入是乘以0还是1，是在同时取决于输入自身分布的情况下随机选择的。换句话说，是0还是1取决于当前的输入有多大的概率大于其余的输入。而由于神经元的输入x往往遵循正态分布（尤其是深度网络中普遍存在Normalization），所以GELU就可以被定义为“标准正态分布的累积分布函数”，利用erf就可以得到公式：x/2*(1+erf(x/sqrt(2))) | Dan Hendrycks et al,2016

+ [An overview of gradient descent optimization algorithms](https://arxiv.org/pdf/1609.04747.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/343564175)：对当前主流的梯度下降算法进行概述 | Sebastian Ruder et al,2016

+ [Sigmoid-Weighted Linear Units for Neural Network Function Approximation in Reinforcement Learning](https://arxiv.org/pdf/1702.03118.pdf)：提出SILU激活函数，其实从某种角度讲就是GELU激活的一种近似，x*sigmoid(x) | Stefan Elfwing et al,2017

+ [SWISH: A SELF-GATED ACTIVATION FUNCTION](https://arxiv.org/pdf/1710.05941v1.pdf)：提出的Swish激活函数，通SILU激活函数一样，没啥差别，x*sigmoid(x) | Prajit Ramachandran et al,2017

+ [Covariate Shift: A Review and Analysis on Classifiers](https://ieeexplore.ieee.org/abstract/document/8978471) | [阅读笔记](https://zhuanlan.zhihu.com/p/339719861)：通过几种分类算法，在四种不同的数据集下验证几种方法处理Covariate Shift问题后的性能分析 | Geeta et al,2019

+ [Monte Carlo Gradient Estimation in Machine Learning](https://arxiv.org/pdf/1906.10652.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/110588068)：本文是一篇关于Monte Carlo gradient estimation的survey，本文主要总结的内容是：随机梯度估计方法的相关背景知识，包括蒙特卡洛采样和随机优化；几种经典应用，包括变分推断、强化学习中的Policy gradient、敏感性分析、实验设计；两类经典的梯度估计算法 | Shakir Mohamed et al,2019

# Dataset | 数据集
+ [The Second Dialog State Tracking Challenge](https://www.aclweb.org/anthology/W14-4337.pdf)：DSTC系列语料是专门用于对话状态跟踪的，非常经典，不过它的官网貌似无用了 |  Henderson et al,2014

+ [The Ubuntu Dialogue Corpus: A Large Dataset for Research in Unstructured Multi-Turn Dialogue Systems](https://arxiv.org/pdf/1506.08909.pdf)：Ubuntu 非结构化多轮对话数据集 |  Ryan Lowe et al,2015

+ [DailyDialog: A Manually Labelled Multi-turn Dialogue Dataset](https://arxiv.org/pdf/1710.03957.pdf) | [数据集地址](https://drive.google.com/file/d/1sj3Z_GZfYzrhmleWazA-QawhUEhlNmJd/view?usp=sharing)：包含对话意图和情感信息的多轮对话数据集 | Yanran Li et al, 2017

+ [LCQMC: A Large-scale Chinese Question Matching Corpus](https://aclanthology.org/C18-1166.pdf)：LCQMC，开放域的中文语义相似度语料，更加侧重于intent相似，总共26万的文本对 | Xin Liu et al,2018

+ [The BQ Corpus: A Large-scale Domain-specific Chinese Corpus For Sentence Semantic Equivalence Identification](https://aclanthology.org/D18-1536.pdf)：关于Bank Question的中文语义相似度语料，总共12万的文本对 | Jing Chen et al,2018

+ [CrossWOZ: A Large-Scale Chinese Cross-Domain Task-Oriented Dialogue Dataset](https://arxiv.org/pdf/2002.11893.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/259861746)：第一个大规模的中文跨域任务导向对话数据集 | Qi Zhu et al,2020

+ [Improving Dialog Evaluation with a Multi-reference Adversarial Dataset and Large Scale Pretraining](https://scholar.google.com/scholar_url?url=https://direct.mit.edu/tacl/article-pdf/doi/10.1162/tacl_a_00347/1923874/tacl_a_00347.pdf&hl=zh-CN&sa=T&oi=gsb-gga&ct=res&cd=0&d=13355199831609160829&ei=hXzkYNupCsyO6rQPkrG1wAo&scisig=AAGBfm39FeIrjR-BGf074wiUqDueImjYeA) | [数据集地址](https://github.com/iitmnlp/Dialogue-Evaluation-with-BERT)：DailyDialog数据集的升级版，11K的多轮对话上下文，每个上下文包括五个标准的参考回复、五个不相关的回复、五个随机挑选的回复 | Ananya B. Sai et al, 2020

+ [MuTual: A Dataset for Multi-Turn Dialogue Reasoning](https://arxiv.org/pdf/2004.04494.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/282843192)：MuTual 数据集，用于针对性地评测模型在多轮对话中的推理能力 |  L Cui et al,2020

+ [MultiWOZ 2.2: A Dialogue Dataset with Additional Annotation Corrections and State Tracking Baselines](https://arxiv.org/pdf/2007.12720.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/260097352)：MultiWOZ是一个著名的面向任务的对话数据集，被广泛用作对话状态跟踪的基准，MultiWOZ 2.2是目前最新版本 | Zang et al,2020

# Evaluate | 评估
+ [LogME: Practical Assessment of Pre-trained Models for Transfer Learning](https://arxiv.org/pdf/2102.11005.pdf) | [阅读笔记](https://zhuanlan.zhihu.com/p/358844524)：一种通用且快速的评估选择适合下游任务的预训练模型的打分方法，logME | Kaichao You et al,2021 

+ [Towards Quantifiable Dialogue Coherence Evaluation](https://arxiv.org/pdf/2106.00507.pdf)：QuantiDCE，一种实现可量化的对话连贯性评估指标模型 | Zheng Ye et al,2021
