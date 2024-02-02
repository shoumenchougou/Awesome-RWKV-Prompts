此仓库中的 prompt 示例使用 RWKV-5-7B-World 模型，随着模型版本和参数的调整，生成的结果可能会产生变化。

你可以通过调整 API 参数改变示例 Prompts 的生成效果。

## API 参数介绍

主要 API 参数对应的效果如下：

| 参数  | 效果 |
| ---  | --- |
| Temperature | 采样温度，就像给模型喝酒，数值越大随机性越强，更具创造力，数值越小则越保守稳定。 |
| Top_P | 就像给模型喂镇静剂，优先考虑前 n% 概率质量的结果。如设置成 0.1 则考虑前 10% , 生成内容质量更高但更保守。如设置成 1 ，则考虑所有质量结果，质量降低但更多样。 |
| Presence Penalty | 存在惩罚，正值根据“新 token 在至今的文本中是否出现过”来对其进行惩罚，从而增加了模型涉及新话题的可能性。 |
| Frequency Penalty | 频率惩罚，正值根据新 token 在至今的文本中出现的频率/次数来对其进行惩罚，从而减少模型原封不动地重复相同句子的可能性 |

其中 Temperature 和 Top_P 两个参数对生成效果的影响最大。

## 推荐参数配置

我们为不同的任务提供了一些推荐的参数：

续写小说和对话，需要模型可以尝试以下四种参数搭配：
- Temperature 1.2 ，Top_P 0.5
- Temperature 1.4 ，Top_P 0.4 
- Temperature 1.4 ，Top_P 0.3
- Temperature 1.4 ，Top_P 0.2 

完成相对机械的任务，例如材料问答、文章摘要等，则可将参数设为：

- Temperature 1 ，Top_P 0.2
- Temperature 1 ，Top_P 0.1
- Temperature 1 ，Top_P 0 

举个例子，如果你正在执行像关键词提取之类的机械任务，不需要模型进行任何开放性思考，则可以将 Temperature 设为 1 ，Top_P、Presence Penalty、Frequency Penalty 都设为 0 。