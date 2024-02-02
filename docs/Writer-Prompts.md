下列 prompt 示例基于 RWKV-5-World-7B 模型的续写模式，随着模型版本和 API 参数的调整，生成的结果可能会产生变化。

## 结构化

### ⭐ 提取用户输入关键词并输出 JSON 

--- 

**输入 prompts:**
```
Instruction: You are an expert assistant responsible for extracting destination and day information from user input and producing valid JSON in the following format:
{
"location": "the location name, Nan if there is no adjustment",
"num_day": "the num day is the number of days, 0 if there is no adjustment",
}

user input: 我要去日本5天

Response:
```

**参考输出：**
> {
    "location": "Japan",
    "num_day": 5,
    }


### ⭐ 通过搜索引擎查找餐厅推荐菜品

**输入 prompts:**

```
User: What's the phone number of "Riverside Grill"
Available Tools:
- `print(str)`: print the string.
- `search_web(str)`: search the web with the given string, returning raw web page data.
- `extract_information(str, key)`: extract the key information in the web data.

Assistant:
Thoughts:
- I need to find the restaurant's information from a search engine.
- I need to extract the phone number of the restaurant.
- I need to print the phone number of the restaurant.
Reasoning:
- `search_web` can search the web for the restaurant's information.
- `extract_information` can extract the phone number from the search result. The key should be "phone number".
- `print` can print the phone number to the output.
Execution:
    ```
    web_result = search_web("Riverside Grill")
    phone_number = extract_information(web_result, "phone number")
    print(phone_number)
    ```

User: Recommend a local restaurant and one of its best dishes.
Available Tools:
- `print(str)`: print the string.
- `search_web(str)`: search the web with the given string, returning raw web page data.
- `extract_information(str, key)`: extract the key information in the web data.

Assistant:
Thoughts:
```
**参考输出**

```
- I need to find a local restaurant that serves good food.
- I need to recommend a specific dish from that restaurant.
Reasoning:
- `search_web` can search for local restaurants in the area.
- `extract_information` can extract information about a specific dish from a search result, such as its name or description.
- `print` can print the recommended dish to the output.
Execution:
    ```
    search_result = search_web("local restaurants")
    recommended_dish = extract_information(search_result, "name of recommended dish")
    print(recommended_dish)
    ```
```

### ⭐ 提取对话信息并转化为 JSON 
---
**输入 prompts:**
```
Instruction: You are an expert assitant for summarizing and extracting insights from sales call transcripts
Generate a valid JSON in the following format:
{
    "summary": "Summary of the call transcript. ",
    "products": ["product 1", "product 2"],
    "rep_name": "Name of the sales rep",
    "prospect_name": "Name of the prospect",
    "action_items": ["action item 1", "action item 2"],
}

Input: [Phone rings]

John: Hello, this is John.

Sarah: Hi John, this is Sarah from XYZ Company. I'm calling to discuss our new product, the XYZ Widget, and see if it might be a good fit for your business.

John: Hi Sarah, thanks for reaching out. I'm definitely interested in learning more about the XYZ Widget. Can you give me a quick overview of what it does?

Sarah: Of course! The XYZ Widget is a cutting-edge tool that helps businesses streamline their workflow and improve productivity.

John: That sounds really interesting. I can see how that could benefit our team. Do you have any case studies or success stories from other companies who have used the XYZ Widget?

Sarah: Absolutely, we have several case studies that I can share with you. I'll send those over along with some additional information about the product. I'd also love to schedule a demo for you and your team to see the XYZ Widget in action.

John: That would be great. I'll make sure to review the case studies and then we can set up a time for the demo. In the meantime, are there any specific action items or next steps we should take?

Sarah: Yes, I'll send over the information and then follow up with you to schedule the demo. In the meantime, feel free to reach out if you have any questions or need further information.

John: Sounds good, I appreciate your help Sarah. I'm looking forward to learning more about the XYZ Widget and seeing how it can benefit our business.

Sarah: Thank you, John.

John: You too, bye.

Response:
```
**参考输出：**
```json
{
    "summary": "John is interested in learning more about a new product called the XYZ Widget. He asks for a case study and information about pricing. Sarah agrees to send over information and set up a demo.",
    "products": ["XYZ Widget"],
    "rep_name": "Sarah",
    "prospect_name": "John",
    "action_items": ["send case study, schedule demo"]
}
```
>


## 续写小说

### ⭐ 续写《三体》小说情节
--- 
**输入 prompts:**
```
user: 已知: “当然可以，大宇宙不会因为这五公斤就不坍缩了。”关一帆说，他还有一个没说出来的想法：也许大宇宙真的会因为相差一个原子的质量而由封闭转为开放。大自然的精巧有时超出想象，比如生命的诞生，就需要各项宇宙参数在几亿亿分之一精度上的精确配合。但程心仍然可以留下她的生态球，因为在那无数文明创造的无数小宇宙中，肯定有相当一部分不响应回归运动的号召，所以，大宇宙最终被夺走的质量至少有几亿吨，甚至可能是几亿亿亿吨。 但愿大宇宙能够忽略这个误差。 程心和关一帆进入了飞船，智子最后也进来了。她早就不再穿那身华丽的和服了，她现在身着迷彩服，再次成为一名轻捷精悍的战士，她的身上佩带着许多武器和生存装备，最引人注目的是那把插在背后的武士刀。 “放心，我在，你们就在！”智子对两位人类朋友说。 聚变发动机启动了，推进器发出幽幽的蓝光，飞船缓缓地穿过了宇宙之门。 小宇宙中只剩下漂流瓶和生态球。漂流瓶隐没于黑暗里，在一千米见方的宇宙中，只有生态球里的小太阳发出一点光芒。在这个小小的生命世界中，几只清澈的水球在零重力环境中静静地飘浮着，有一条小鱼从一只水球中蹦出，跃入另一只水球，轻盈地穿游于绿藻之间。在一小块陆地上的草丛中，有一滴露珠从一片草叶上脱离，旋转着飘起，向太空中折射出一缕晶莹的阳光。续写，智子爆炸过程，飞船外观，程心与关一帆的心理描写

Assistant:
```
**参考续写结果：**

> 智子爆炸过程中发出了强烈而耀眼的光芒，整个小宇宙都被照亮了。在这种强烈的光芒下，飞船外观变得模糊不清，只剩下几个点状物体在闪烁着微弱的光芒。
>
> “我们已经进入黑暗区域了吗？”关一帆问道。
>
> “不知道……”程心回答道。
>
> 两人沉默地坐在驾驶舱里，静静地等待着结果。他们感觉到自己正处于一种极度危险的境地之中，但同时也充满了对未来的期待和希望。
> 
> 随着时间推移，飞船开始逐渐失去重力感应器所接收到的信号。这意味着他们已经进入了真空区域中——那里没有任何物质存在。
> 
> “我们还能坚持多久？”关一帆问道。
> 
> “我不知道……”程心回答道，她感觉自己已经快要支撑不住了。
> 
> 就在这时候，智子爆炸产生的强烈光芒突然出现在他们面前。两人惊讶地看着那个巨大而耀眼的火球——它像是从宇宙深处喷涌而出一样。
> 
> “太神奇了！”关一帆赞叹道。
> 
> 随着火球逐渐消失，飞船开始恢复重力感应器所接收到的信号。两人松了口气，同时也感受到自己身体内部传来的微弱震动——这是飞船重新进入真空区域后产生的效果。
> 
> 整个小宇宙中只剩下漂流瓶和生态球。漂流瓶隐没于黑暗里，在一千米见方的宇宙中只有几个点状物体在闪烁着微弱的光芒。而生态球里则只剩下零重力环境中静静地飘浮着几条小鱼和清澈水晶般透明的绿藻之间游动着一条小鱼。
> 
> 程心和关一帆坐在驾驶舱里，静静地等待着结果。他们感觉到自己正处于黑暗区域中，但同时也充满了对未来的期待和希望。他们知道这次旅行虽然充满了危险和挑战，但也带给他们无尽的启示和思考。



### ⭐ 生成《三体》小说续写大纲
---
```
user: 已知: “当然可以，大宇宙不会因为这五公斤就不坍缩了。”关一帆说，他还有一个没说出来的想法：也许大宇宙真的会因为相差一个原子的质量而由封闭转为开放。大自然的精巧有时超出想象，比如生命的诞生，就需要各项宇宙参数在几亿亿分之一精度上的精确配合。但程心仍然可以留下她的生态球，因为在那无数文明创造的无数小宇宙中，肯定有相当一部分不响应回归运动的号召，所以，大宇宙最终被夺走的质量至少有几亿吨，甚至可能是几亿亿亿吨。 但愿大宇宙能够忽略这个误差。 程心和关一帆进入了飞船，智子最后也进来了。她早就不再穿那身华丽的和服了，她现在身着迷彩服，再次成为一名轻捷精悍的战士，她的身上佩带着许多武器和生存装备，最引人注目的是那把插在背后的武士刀。 “放心，我在，你们就在！”智子对两位人类朋友说。 聚变发动机启动了，推进器发出幽幽的蓝光，飞船缓缓地穿过了宇宙之门。 小宇宙中只剩下漂流瓶和生态球。漂流瓶隐没于黑暗里，在一千米见方的宇宙中，只有生态球里的小太阳发出一点光芒。在这个小小的生命世界中，几只清澈的水球在零重力环境中静静地飘浮着，有一条小鱼从一只水球中蹦出，跃入另一只水球，轻盈地穿游于绿藻之间。在一小块陆地上的草丛中，有一滴露珠从一片草叶上脱离，旋转着飘起，向太空中折射出一缕晶莹的阳光。生成续写的小说名，小说大纲

Assistant:
```

**参考小说大纲输出：**

> 《重力之外》
> 第二章：回归运动
> 
> 程心和关一帆进入了飞船后开始启动聚变发动机并穿越宇宙之门返回地球。
然而他们很快就发现自己面临着前所未有的挑战——回归运动！
原来当两个文明相互接触时会产生“回归运动”现象：如果两个文明彼此都拥有相同或类似于另外一个文明所拥有技术或科学成果时就会产生这种现象。
程心和关一帆意识到他们需要尽快解决这个问题才能安全返航。
> 
> 第三章：智子与人类
> 
> 随着飞船越来越接近地球，智子开始向程心和关一帆透露她对人类社会的看法。
她认为人类是宇宙中最具创造力和适应性的物种之一。但同时也存在着许多问题需要解决。
> 
> 第四章：大宇宙与小宇宙
> 
> 程心和关一帆通过探索发现了更多关于大宇宙和小宇宙之间相互作用的信息。
他们发现在某些情况下，两个文明可以共存并且互相影响。但同时也存在着很多潜在风险需要注意。
> 
> 第五章：未来展望
> 
> 程心和关一帆回到地球后开始思考如何将他们所学到的知识应用于实际生活中。他们希望能够通过科技手段改善人类社会面临的各种问题并推动人类文明向更高层次发展。
> 
> 第六章：结局
> 
> 经过数年努力，程心和关一帆成功地将智子引导至人类社会中并帮助她适应新环境。同时他们也利用自己掌握的知识为地球上其他国家提供了更好的科技支持。
随着时间推移，智子逐渐融入了人类社会并成为了一名优秀的科学家。她还继续探索宇宙之门背后隐藏的秘密，并与其他文明保持联系以促进全球合作。
最终，程心和关一帆意识到虽然宇宙之门带来了许多挑战和危险，但它也给予了人类无限可能性。

