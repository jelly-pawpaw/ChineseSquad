## ChineseSquad

  中文机器阅读理解数据集，本数据集通过机器翻译加人工校正的方式从原始Squad转换而来，其中包括V1.1 和V2.0。由于部分翻译无法找到原文中的答案（短答案翻译和文档翻译有出入），故数据量对比原始英文版SQuAD 有所减少。

### NEWS

- 2020.01.13 将V 1.1 和V2.0 两个中文版本进行合并，详情请参考正式版的  squad-zen V 1.0。能通过[huggingface](https://github.com/huggingface) 的transfomers 加载，便于研究人员利用本数据集和大量预训练模型测试和验证自己的中文机器阅读理解模型。



### 为什么这么做？

现有中文**抽取式**机器阅读理解数据集存在数据量较小，或者领域专一的特点

- **CMRC 2018** 数据集较小，只有能回答的问题，问题类型比较单一。里面还有空格，[huggingface](https://github.com/huggingface) 的transfomers不能正常读取。
- **Dureader** 2019 数据集规模较大，但是数据文本质量不敢赞誉，优秀的数据预处理方法可以提升好几个百分点。只要数据清理的好，结果就不差
- **CAIL 2019** 法研杯机器阅读理解，数据领域性比较强，文本质量很高。
- **中国军事机器阅读理解** 数据领域性比较强，数据未公开。
- **DRCD**  繁体版中文表述和简体中文表述存在一定的差异。



### 数据集



|    数据集  |   有答案   |  无答案    |   总数   |下载链接      |
| ---- | ---- | ---- | ---- | ---- |
| **squad-zen 1.0 train** | 68213 | 43498| 110k | [squad-zen 1.0 train](https://github.com/zengjunjun/ChineseSquad/blob/master/squad-zen/train-zen-v1.0.json) |
| **squad-zen 1.0 dev** | 8326 | 5954 | 14k | [squad-zen 1.0 dev](https://github.com/zengjunjun/ChineseSquad/blob/master/squad-zen/dev-zen-v1.0.json) |
| ~~squad 2.0 train~~  | 46530 | 43498 | 90K | [squad 2.0 train](https://github.com/zengjunjun/ChineseSquad/blob/master/squad_2.0/train-v2.0-zh.json) |
| ~~squad 2.0 dev~~ | 3391   | 5945 | 9K | [squad 2.0 dev](https://github.com/zengjunjun/ChineseSquad/blob/master/squad_2.0/dev-v2.0-zh.json) |
| squad 1.1 dev | 7679 | - | 7k | [squad 1.1 dev](https://github.com/zengjunjun/ChineseSquad/blob/master/squad_1.1/dev-v1.1-zh.json) |
| squad 1.1 train | 55526 | - | 55k | [squad 1.1 train](https://github.com/zengjunjun/ChineseSquad/blob/master/squad_1.1/train-v1.1-zh.json) |






### 实验结果

| model     | data | dev-EM                          | dev-F1                           |
| --------- | ---- | ------------------------------- | -------------------------------- |
| BERT-base | v1.1 | 56.74                           | 56.79                            |
| BERT-base | V2.0 | 61.14 | 61.17 |
| BERT-base | zen 1.0 | 70.84 | 70.86 |
| RoBERTa-large   | zen 1.0    | **72.94**                         | **72.97**                          |




### 参考

[SQuAD 2.0:The Stanford Question Answering Dataset](https://rajpurkar.github.io/SQuAD-explorer/)

[CNSD：中文自然语言推理数据集](https://github.com/zengjunjun/CNSD)

### 致谢

感谢百度云提供计算服务

### 声明

该数据集只能用于学术研究，请勿商用。
