# AI-Writer-On-Action
详细请参考BlinkDL大佬仓库[[点击直达]](https://github.com/BlinkDL/AI-Writer/)

## 注意
1. 模型的训练数据全部来自网文，缺乏生活常识。***生成的文字仅供娱乐。请遵守法律法规。***
2. 由于暂时没有同志和我一起进行小说语料的清洗，清洗工作量大，网络小说鱼龙混杂，包括但不限于出现乱码(概率很小)、广告、奇怪的符号的情况属于正常现象，轻喷(我尽力了:disappointed_relieved:)。
3. 第一次炼丹，可能数据集没有准备太好，质量稍微会差，但我会尽力的。

## 食用方法
直接action运行，等到出现bore提示即可使用。

考虑到GitHub Action没有GPU，故采用CPU加载模型。

## 药草
***2022-12-23***

共计130本网络小说，整理清洗(粗处理)后约为1.1G
**(测试)**

***yyyy-MM-dd***

整理清洗(粗处理)后约为2G *(未来)*

## 炼丹炉
*两张Tesla T4。第一张显存压榨干净，第二张还差一些(大概剩余3G显存)。*

## 丹药
### 第一炉毒药*2022-12-23*
#### 属性

| **epoch** | **ppl** | **loss** | **iter** |                          **sha256**                          |
| :-------: | :-----: | :------: | :------: | :----------------------------------------------------------: |
|    128    |  9.22   |  2.2217  |   263    | 3a7d19d75bdf63f69dbe431aee464ec349894367151d650e269e2f59438553bc |

#### 个人评价
还是很~~沙雕~~不错...笑死:rofl:

直接上图

![trained-epoch128-1-16](./assets/trained-epoch128-1-16.png)

#### 改进地方

1. 加大语料。
2. 如果可能加大epoch次数到256(相应的，训练时间会增长。)

### 第二炉毒药(xxx)

#### 属性
(未来这会有个表格)

#### 个人评价
(未来这会有个评价)

## 参数设置
采用**RWKV-V1**
![参数设置](./assets/param.svg)

## 准备自己的数据集
### 要求
1. 耐心

2. 足够大的硬盘

3. 够好的视力(没有可以用正则表达式处理)

4. 知道在哪里下载网文

### 准备
1. 适当掩码(mask)
2. 段和段之间空行，小说和小说直接空行
3. **标点符号尽量统一**,*比如将`，`改为`,`、将`：`改为`:`*
4. 删去“今天三更”、“感谢打赏”、表情、网址、广告等无用信息

### 开始
把准备好的数据集(药草)放入炼丹炉，最后是仙丹(一个非常好的模型，像大佬的一样)还是毒药(垃圾模型，像我的一样)就看数据集、参数设置、算法选择和脸了。