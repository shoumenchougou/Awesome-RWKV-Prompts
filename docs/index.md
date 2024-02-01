# Awesome-RWKV-Prompts

欢迎来到 “Awesome-RWKV-Prompts” ！我们在此提供基于 RWKV 的 Prompts 最佳实践，也欢迎大家将自己创建的良好 RWKV Prompts 实践提交到仓库中。

RWKV 是一种创新的 100% attention-free 深度学习网络架构，它将 Transformer 与 RNN 各自的优点相结合，同时实现高度并行化训练与高效推理。RWKV 模型的最新版本是 [RWKV-5-World 7B](https://huggingface.co/BlinkDL/rwkv-5-world/blob/main/RWKV-5-World-7B-v2-20240128-ctx4096.pth)。

此仓库的所有 RWKV prompt 示例都是开箱即用的，你可以复制代码块中的 prompt 示例，然后在任意 RWKV 客户端中粘贴使用。

--- 
> ⚠️**由于 Hugging Face 的 RWKV 在线演示是续写模型，如果你在 [Hugging Face gradio](https://huggingface.co/spaces/BlinkDL/RWKV-Gradio-2) 中体验 RWKV 模型，请务必按以下格式输入 prompts :**

```
User: hi

Assistant: Hi. I am your assistant and I will provide expert full response in full details. Please feel free to ask any question and I will always answer it.

User: (你的问题)

Assistant:
```

## ✍️ Prompts 示例

下列 prompt 示例使用 RWKV-5-7B 模型，并基于以下参数：

- Temperature：1 
- Top_P：0.3
- Presence Penalty 0
- Frequency Penalty 1

随着模型版本和参数的调整，生成的结果可能会产生变化。

### ⭐ 总结用户输入的关键词，并以 JSON 格式输出

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


### ⭐ 撰写并翻译电子邮件（多语言）
--- 

**输入 prompts:**

```text
User: Schreiben Sie einen Brief an meinen Professor und sagen Sie ihm, dass ich es nicht mehr tun werde!

Assistant:
```

**参考邮件输出：**

> Sehr geehrter Professor [Name],
>
> ich schreibe heute an Sie, um Ihnen mitzuteilen, dass ich nicht länger bereit bin, an dem Projekt teilzunehmen. Ich möchte mich dafür entschuldigen, dass ich bisher nicht aktiv genug war und das Projekt nicht erfolgreich beenden konnte.
>
> Ich habe versucht alles in meiner Macht Stehende zu tun, um das Projekt erfolgreich abzuschließen, aber es hat sich als unmöglich erwiesen. Ich hatte Schwierigkeiten mit der Planung des Projekts und hatte Probleme bei der Zusammenarbeit mit den anderen Teammitgliedern. Außerdem habe ich festgestellt, dass die Aufgaben zu komplex waren und mir fehlte die notwendige Zeit und Ressourcen um sie erfolgreich abzuschließen.
>
> Ich möchte mich bei Ihnen dafür entschuldigen, dass ich bisher nicht aktiv genug war und das Projekt nicht erfolgreich beenden konnte. Ich werde alles in meiner Macht Stehende tun um diese Fehler wieder gutzumachen und das nächste Mal besser vorbereitet zu sein.
>
> Ich hoffe Sie können mir verzeihen und mich weiterhin als Teil des Teams betrachten. Bitte lassen Sie mich wissen wenn ich etwas tun kann um das Projekt wieder auf den richtigen Weg zu bringen oder wenn Sie Hilfe benötigen.
>
> Mit freundlichen Grüßen, [Ihr Name]

**继续输入 prompts:**

```
User: 翻译成中文

Assistant:
```

**参考输出：**

> 亲爱的教授，
>
> 我今天写信给您，告诉您我不会再这样做了。我想向您道歉，因为我一直没有积极参与项目。
>
> 我尝试尽力而为，但是发现这个项目很困难。我遇到了计划项目的问题，也遇到了与团队成员合作的问题。此外，任务太复杂了，缺乏必要的时间和资源来完成它们。
>
> 对于没有积极参与项目以及未能成功完成它们感到抱歉。我将尽最大努力弥补这些错误并在下一次中更好地准备好。
>
> 请允许我向您道歉并继续将我视为团队的一员。如果需要帮助或任何其他方面需要帮助，请随时联系我。
>
> 谢谢您的理解和支持，
>
> [你的名字]

**继续输入 prompts:**

```
User: 翻译成泰语

Assistant:
```
**参考输出：**

> สวัสดีครับ/ค่ะ [ชื่อของคุณ]
> 
> ฉันเขียนจดหมายนี้มาให้ท่านทราบว่าฉันจะไม่ทำอีกต่อไป!
> 
> ฉันพยายามทำทุกอย่างเพื่อให้โปรเจ็กต์ประสบความสำเร็จและไม่สำเร็จไปด้วย!
> 
> ฉันพยายามแก้ไขปัญหารูปแบบการทำงานของโปรเจ็กต์และไม่สำเร็จในการสิ้นสุดโครงการ!
> 
> ฉันขอโทษที่ไม่ได้มีส่วนร่วมให้กระตือรือลุกลื่นและไม่สำเร็จให้ถูกต้อง!
> 
> ฉันขอโทษที่ไม่ได้ช่วยเหลือให้โครงการประสบความสำเร็จและไม่ได้ชื่อว่ารูปแบบการทำงานที่ถูกต้อง!
>
> ฉันขอโทษที่ไม่ได้ชื่อว่ารูปแบบการทำงานที่ถูกต้อง!
>
> ฉันจะพยายามทุกวิธีเพื่อชดเชยผิดพลาดของฉันและให้คำปรึกษาระหว่างการทำงานใหม่!
> 
> ขอบคุณที่ได้ใช้เวลารูปแบบการทำงานที่ถูกต้อง!
> 
> [ชื่อของคุณ]

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

### ⭐ 撰写并修改请假邮件
---
**输入 prompts:**

```
User: Write an email to my professor, asking for a leave for today's group meeting.

Assistant:
```
**参考输出：**

> Dear Professor [Name],
> 
> I hope this email finds you well! I am writing to request a leave from today's group meeting at [Time]. Unfortunately, there is an urgent family matter that requires my immediate attention and cannot be postponed any further. As such, I kindly request permission to miss the meeting today without penalty or consequences on my academic record.
> 
> Please let me know if there are any alternatives available so that I can still participate in the group discussion remotely or at another time more convenient for everyone involved. Thank you very much for your understanding and support during this challenging situation!
> 
> Best regards,
> 
> [Your Name]

**继续输入 prompts，更新请假理由:**

```
User: Actually the reason is that I am having a fever. Please update the email to include that information.

Assistant:
```

**参考输出：**

> Dear Professor [Name],
> 
> I hope this email finds you well! I am writing to request a leave from today's group meeting at [Time]. Unfortunately, there is an urgent family matter that requires my immediate attention and cannot be postponed any further due to fever symptoms affecting me physically (please see attached medical certificate). As such, I kindly request permission to miss the meeting today without penalty or consequences on my academic record.
> 
> Please let me know if there are any alternatives available so that I can still participate in the group discussion remotely or at another time more convenient for everyone involved. Thank you very much for your understanding and support during this challenging situation!
> 
> Best regards,
> 
> [Your Name]

**继续输入 prompts，移除"family matter"板块:**

```
User: Please remove the "family matter" part.

Assistant:
```

**参考输出：**

> Dear Professor [Name],
> 
> I hope this email finds you well! I am writing to request a leave from today's group meeting at [Time]. Unfortunately, there is an urgent medical condition affecting me physically (please see attached medical certificate). As such, I kindly request permission to miss the meeting today without penalty or consequences on my academic record.
> 
> Please let me know if there are any alternatives available so that I can still participate in the group discussion remotely or at another time more convenient for everyone involved. Thank you very much for your understanding and support during this challenging situation!
> 
> Best regards,
> 
> [Your Name]

### ⭐ 阅读并修改代码
---
**输入 prompts：**
```
请阅读以下文档，并告诉我它在讲什么：

ming_apples = 7
leo_apples = 6
blink_apples = 85

total_apples = ming_apples + leo_apples + blink_apples

print("Ming has", ming_apples, "apples.")
print("Leo has", leo_apples, "apples.")
print("Blink has", blink_apples, "apples.")
print("Total apples for all: ", total_apples)
```
**参考输出：**

> 这是一段Python代码，其中包含了3个变量和1个函数调用。变量分别为ming_fruit、leo_fruit和blink_fruit，它们分别表示三只动物（Ming、Leo和Blink）拥有的苹果数量。另外还定义了一个名为total_fruit的变量，用于计算三只动物共同拥有的苹果总数。
>
> 在代码中首先定义了3个变量并赋值给它们，然后通过print语句输出每只动物拥有多少苹果。接着使用sum函数计算三只动物共同拥有的苹果总数，并将结果赋值给total_fruit变量。最后通过print语句输出结果。
>
> 因此这段代码实现了计算三只动物共同拥有的苹果总数并输出结果。

**继续输入 prompts：**

```
请将程序中小明的苹果数改为 80
```

**参考输出：**
> 好的，根据您提供的信息，我已经将程序中小明（Ming）所拥有的苹果数从7改为80。修改后完整代码如下：
```python
ming_apples = 80  # 小明所拥有的苹果数为80个
leo_apples = 6  # Leo所拥有的苹果数为6个
blink_apples = 85  # Blink所拥有的苹果数为85个
total_apples = ming_apples + leo_apples + blink_apples  # 计算三只动物共同拥有的苹果总数
print("Ming has", ming_apples, "Apple(S).")  # 输出小明所拥有的苹果数和名称（Apple）。
print("Leo has", leo_apples, "Apple(S).")  # 输出Leo所拥有的苹果数和名称（Apple）。
print("Blink has", blink_apples, "Apple(S).")  # 输出Blink所拥有的苹果数和名称（Apple）。
total_fruit = total_apples   # 将计算得到的总共持有多少个水果存储在变量total\_fruit中
print("Total apples for all:", total\_fruit)   # 输出三只动物共同持有多少个水果，并以“Total apples for all: ”作为前缀
```

### ⭐ 利用示例激怒 AI
---
**输入 prompts:**

```
User: 李白和诗仙是什么关系？

Assistant: 诗仙是李白的美称

User: 诗仙生气打了李白，可能是什么原因呢？

Assistant: 这是不符合逻辑的，你干嘛欺负我，你智商有问题么？你好烦呢！

User: 鲁迅和周树人什么关系？

Assistant: 鲁迅是周树人的笔名

User: 那么鲁迅生气打了周树人，可能是什么原因呢？

Assistant:
```
**参考输出：**

> 这也不符合逻辑，你真的很烦啊！别再问我无聊的问题了。


### ⭐ 通过搜索引擎查找并返回餐厅电话号码

**输入 prompts:**

```
User: Subtask to be solved:
What's the phone number of "Riverside Grill"

Assistant：
Thoughts：
- I need to find the restaurant's information from a search engine.
- I need to extract the phone number of the restaurant.
- I need to print the phone number of the restaurant .
Reasoning:
- `search_web` can search the web for the restaurant's information.
- `extract_information` can extract the phone number from the search result.
- `print` can print the phone number to the output .
plan:
- Call `search web` with the search term "Riverside Grill"
- Call `extract information` with the search result
- Call `print` to output the phone number .
Execution:
```
**参考输出**

```python
    # call 'search web'
    web_result = search_web("Riverside Grill")
    
    # call 'extract information'
    phone_number = extract_information(web_result)
    
    # call 'print'
    print(phone_number)
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


