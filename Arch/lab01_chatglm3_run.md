# run chatglm3 on cpu


https://zhaozhiming.github.io/2023/10/31/chatglm3-deploy/



从本地加载模型
以上代码会由 transformers 自动下载模型实现和参数。完整的模型实现在 Hugging Face Hub。如果你的网络环境较差，下载模型参数可能会花费较长时间甚至失败。此时可以先将模型下载到本地，然后从本地加载。

从 Hugging Face Hub 下载模型需要先安装Git LFS，然后运行

git clone THUDM/chatglm3-6b · Hugging Face

如果从你从 HuggingFace 下载比较慢，也可以从ModelScope中下载。


https://modelscope.cn/models/ZhipuAI/chatglm3-6b/summary




## pyTorch 


## Transformer


## Streamlit 




## kb: run 

```bash
[root@pcentos chatglm3-docker]# docker logs chatglm3-docker-py-1 -f 

Collecting usage statistics. To deactivate, set browser.gatherUsageStats to False.


  You can now view your Streamlit app in your browser.

  Network URL: http://172.19.0.2:8501
  External URL: http://45.32.15.48:8501

tokenizer_config.json: 100%|██████████| 518/518 [00:00<00:00, 1.81MB/s]
tokenization_chatglm.py: 100%|██████████| 13.0k/13.0k [00:00<00:00, 42.7MB/s]
A new version of the following files was downloaded from https://huggingface.co/THUDM/chatglm3-6b:
- tokenization_chatglm.py
. Make sure to double-check they do not contain any added malicious code. To avoid downloading new versions of the code file, you can pin a revision.
tokenizer.model: 100%|██████████| 1.02M/1.02M [00:01<00:00, 976kB/s]
config.json: 100%|██████████| 1.32k/1.32k [00:00<00:00, 5.11MB/s]
configuration_chatglm.py: 100%|██████████| 2.33k/2.33k [00:00<00:00, 8.92MB/s]
A new version of the following files was downloaded from https://huggingface.co/THUDM/chatglm3-6b:
- configuration_chatglm.py
. Make sure to double-check they do not contain any added malicious code. To avoid downloading new versions of the code file, you can pin a revision.
modeling_chatglm.py: 100%|██████████| 55.7k/55.7k [00:00<00:00, 242kB/s]
quantization.py: 100%|██████████| 14.7k/14.7k [00:00<00:00, 11.3MB/s]
A new version of the following files was downloaded from https://huggingface.co/THUDM/chatglm3-6b:
- quantization.py
. Make sure to double-check they do not contain any added malicious code. To avoid downloading new versions of the code file, you can pin a revision.
A new version of the following files was downloaded from https://huggingface.co/THUDM/chatglm3-6b:
- modeling_chatglm.py
- quantization.py
. Make sure to double-check they do not contain any added malicious code. To avoid downloading new versions of the code file, you can pin a revision.
model.safetensors.index.json: 100%|██████████| 21.2k/21.2k [00:00<00:00, 2.73MB/s]
model-00001-of-00007.safetensors: 100%|██████████| 1.83G/1.83G [02:46<00:00, 11.0MB/s]
Downloading shards:  14%|█▍        | 1/7 [02:47<16:47, 167.86s/it]:46<00:00, 10.9MB/s]
model-00002-of-00007.safetensors:  17%|█▋        | 336M/1.97G [00:30<02:33, 10.7MB/s] 

```


