我们提供基于 RWKV 模型的、开箱即用的 Prompts 示例,也欢迎大家将自己创建的良好 RWKV Prompts 实践提交到仓库中。

此仓库的所有 RWKV prompt 示例都是开箱即用的，你可以复制代码块中的 prompt 示例，然后在任意 RWKV 客户端(如 [RWKV Runner](https://github.com/josStorer/RWKV-Runner) 、[RWKV-AI00-server](https://github.com/cgisky1980/ai00_rwkv_server))中粘贴使用。

## 如何体验 RWKV 模型

如果你希望在本地部署 RWKV 模型，我们建议采用以下两种工具：

- [RWKV Runner](https://github.com/josStorer/RWKV-Runner)：由社区成员 josStorer 开发的 RWKV 模型启动和管理工具，支持 LoRA 微调等多种功能，可以在 NVIDIA、AMD、Intel 等显卡上运行。
- [AI00 RWKV Server](https://github.com/Ai00-X/ai00_server):一个基于 RWKV 模型的推理 API 服务器，基于 WEB-RWKV 推理引擎进行开发。AI00 Server 支持 Vulkan/Dx12/OpenGL 作为推理后端，无需臃肿的 pytorch、CUDA 等运行环境，小巧身材，开箱即用！

如果你只是想简单尝试一下 RWKV 模型，可以尝试由 RWKV 官方部署在 Hugging Face 的公共 Demo：

- [RWKV-Gradio-1](https://huggingface.co/spaces/BlinkDL/RWKV-Gradio-1) 
- [RWKV-Gradio-2](https://huggingface.co/spaces/BlinkDL/RWKV-Gradio-2) 

## Hugging Face Gradio 用法
--- 
> ⚠️ **由于 Hugging Face 的 RWKV 在线演示是续写模型，如果你在 [Hugging Face gradio](https://huggingface.co/spaces/BlinkDL/RWKV-Gradio-2) 中体验 RWKV 模型，请务必按以下两种格式输入 prompts :**
>
```
User: hi

Assistant: Hi. I am your assistant and I will provide expert full response in full details. Please feel free to ask any question and I will always answer it.

User: (你的问题，比如“请为我推荐三本适合五岁小孩阅读的世界名著” )

Assistant:
```
或者：
```

Instruction: （你希望模型进行什么操作，比如“请将下列瑞典语翻译成中文”）

Input:（你希望模型处理的内容，比如“hur l?ng tid tog det att bygga twin towers”）

Response:
```
## 关于 RWKV 模型

RWKV 是一种创新的 100% attention-free 深度学习网络架构，它将 Transformer 与 RNN 各自的优点相结合，同时实现高度并行化训练与高效推理。

RWKV 模型的最新版本是 [RWKV-7](https://huggingface.co/BlinkDL/rwkv-7-world)，架构图如下：

![image](./_media/rwkv-x070.jpg ':size=500')