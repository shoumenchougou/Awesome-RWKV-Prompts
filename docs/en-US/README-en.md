
---

Welcome to "Awesome-RWKV-Prompts"! We provide best practices for creating RWKV prompts and invite everyone to submit their own well-crafted RWKV prompt examples to the repository.

Every RWKV prompt example in this repository is ready to use. You can copy the prompt examples from the code blocks and paste them into any RWKV client, such as [RWKV Runner](https://github.com/josStorer/RWKV-Runner) or [RWKV-AI00-server](https://github.com/cgisky1980/ai00_rwkv_server), for immediate use.

## About RWKV LLM

[RWKV](https://www.rwkv.com/) is an innovative, 100% attention-free deep learning network architecture that combines the strengths of both Transformer and RNN models. It achieves highly parallelized training and efficient inference.

The latest version of the RWKV model is [RWKV-7](https://huggingface.co/BlinkDL/rwkv-7-world). Here is an illustration of RWKV v7:

![image](../_media/rwkv-x070.jpg ':size=500')

## Usage with Hugging Face Gradio
--- 
> ⚠️ **Due to Hugging Face's RWKV online demo being a completion model, if you are experimenting with the RWKV model on [Hugging Face Gradio](https://huggingface.co/spaces/BlinkDL/RWKV-Gradio-2), please make sure to input prompts in the following format:**
>
```
User: Hi

Assistant: Hi. I am your assistant and I will provide detailed and expert responses to your questions. Please feel free to ask any question, and I will always answer it thoroughly.

User: (Your question)

Assistant:
```
or
```

Instruction: (What operation do you want the model to perform, such as "Translate the following Swedish text into Chinese"?)

Input: (What content do you want the model to process? For example, "hur lång tid tog det att bygga Twin Towers")

Response:
```

---