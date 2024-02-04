Welcome to "Awesome-RWKV-Prompts"! We provide best practices for RWKV prompts and invite everyone to submit their own well-crafted RWKV prompt practices to the repository.

[RWKV](https://www.rwkv.com/) is an innovative 100% attention-free deep learning network architecture that combines the strengths of both Transformer and RNN, achieving highly parallelized training and efficient inference.

The latest version of the RWKV model is [RWKV-5-World 7B](https://huggingface.co/BlinkDL/rwkv-5-world/blob/main/RWKV-5-World-7B-v2-20240128-ctx4096.pth).

Every RWKV prompt example in this repository is ready to use. You can copy the prompt examples from the code blocks and paste them into any RWKV client(Such as [RWKV Runner](https://github.com/josStorer/RWKV-Runner) , [RWKV-server](https://github.com/cgisky1980/ai00_rwkv_server)) for immediate use.

--- 
> ⚠️ **Due to Hugging Face's RWKV online demo being a completion model, if you are experiencing the RWKV model in [Hugging Face gradio](https://huggingface.co/spaces/BlinkDL/RWKV-Gradio-2) ,please make sure to input prompts in the following format:**
>
```
User: hi

Assistant: Hi. I am your assistant and I will provide expert full response in full details. Please feel free to ask any question and I will always answer it.

User: (Your question)

Assistant:
```

