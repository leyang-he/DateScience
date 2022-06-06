# DateScience

## 小组信息：

| 学号      | 姓名   | 邮箱                 | 分工             |
| --------- | ------ | -------------------- | ---------------- |
| 211250010 | 毛树杰 | 2486668027@qq.com    | 数据爬取（组长） |
| 211250009 | 严浩翔 | 1171372127@qq.com    | 数据扩增         |
| 211250138 | 何乐阳 | heleyang0311@163.com | 数据验证         |

## 代码开源地址：

### GitHub仓库

**https://github.com/leyang-he/DateScience.git**

### 模型&源数据：

https://www.aliyundrive.com/s/fZcS2dw994t

## 研究方法：

### 数据据分析方法：

#### 数据爬取：

- **爬虫**从相关政务网站获取原始数据

#### 数据扩增：

##### 实现方式：

注册成为百度翻译高级个人开发者，申请并通过了百度翻译通用翻译开发模式，使用个人APPID与密钥组合方式，连接百度翻译API进行文本的双向回译。设计传递模式为txt文本形式，爬虫后经筛选程序导出i.txt(i＝1,2...)文本文件，再通过多种语言的双向回译，导出结果为outputi.txt(i＝1,2...)，后续将进一步优化文本扩展方式，期望实现深度学习文本扩展方式。最后以对应式方法，进行文本扩展有效性的测算与反馈。

- 用**百度翻译API回译** *（已实现）*
- **BERT模型**进行同义词、根据上下文模糊词替换*（实现中）*

#### 数据验证：

##### 验证方式：

- 处理数据是中文文本，所以需要对数据进行**分词**，分隔成短文本，更加易于处理。使用python的jieba库。

- 由前两步得到原始数据和扩增数据，使用**Word2Vec库**计算两个数据的**相似度**验证扩增的有效性

##### 优缺点分析：

###### 	优势：

​	Word2Vec可以将文本映射到向量，把自然语言中的每一个词，表示成一个统一意义统一维度的短向量。相比文本，向量显然更容易处理，数据科学处理方法丰富。	基于神经网络，强化训练效果。

###### 	劣势：

​	模型训练时间长，模型效果比较依赖语料库的效果，对初始文本量要求大。因此对专有名词处理效果差。内存消耗大，需要存储词向量矩阵。依赖词汇表，对未登录词(OOV)处理困难，只能加量训练。

##### 后续改进：

使用Bert模型进行优化。对准确度和相似度给出更加具体的指标。提升运行速度。

### 数据集：

- 原始数据集：[Wikipedia Zh 中文维基百科](https://zh.m.wikipedia.org/zh-hans/%E8%AF%AD%E6%96%99%E5%BA%93)
- 加量训练：用爬取的数据和扩增后数据扩展Word2vec模型的词汇表









