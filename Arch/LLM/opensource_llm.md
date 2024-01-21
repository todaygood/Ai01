本文作者盘点了一些组织或者个人开源的模型。

ChatGPT爆火出圈，国内很多高校、研究机构和企业都发出类似ChatGPT的发布计划。ChatGPT没有开源，复现难度极大，即使到现在GPT3的完全能力也没有任何一个单位或者企业进行了复现。刚刚，OpenAI又官宣发布了图文多模态的GPT4模型，能力相对ChatGPT又是大幅提升，似乎闻到了以通用人工智能主导的第四次工业革命的味道。

无论是国外还是国内，目前距离OpenAI的差距越来越大，大家都在紧锣密鼓的追赶，以致于在这场技术革新中处于一定的优势地位，目前很多大型企业的研发基本上都是走闭源路线，ChatGPT和GPT4官方公布的细节很少，也不像之前发个几十页的论文介绍，OpenAI的商业化时代已经到来，当OpenAI不在Open，那么如何打破技术枷锁，那就只能寻求开源模型替代。为此，作者盘点了一些组织或者个人开源的模型具体汇总如下：

ChatYuan

ChatYuan（元语AI）是由元语智能开发团队开发和发布的，自称第一个国内最早的一个功能型对话大模型，可以写文章、写作业、写诗歌、做中英文间的翻译；一些法律等特定领域问题也可以提供相关信息。该模型目前只支持中文。

从披露的技术细节看，底层采用7亿参数规模的T5模型，并基于PromptClue进行了监督微调形成了ChatYuan。该模型基本上是ChatGPT技术路线的三步的第一步，没有实现奖励模型训练和PPO强化学习训练。

GitHub链接：

https://github.com/clue-ai/ChatYuan

Colossal AI

最近，ColossalAI开源了他们的ChatGPT实现。分享了他们的三步策略，完整实现了ChatGPT核心的技术路线。

本人基于该项目，更加明确了三步策略，并进行了分享：

第一阶段（stage1_sft.py）：SFT监督微调阶段，该开源项目没有实现，这个比较简单，因为ColossalAI无缝支持Huggingface，本人直接用Huggingface的Trainer函数几行代码轻松实现，在这里我用了一个gpt2模型，从其实现上看，其支持GPT2、OPT和BLOOM模型；

第二阶段（stage2_rm.py）：奖励模型（RM）训练阶段，即项目Examples里train_reward_model.py部分；

第三阶段（stage3_ppo.py）：强化学习（RLHF）阶段，即项目train_prompts.py。

三个文件的执行需要放在ColossalAI项目中，其中代码中的cores即原始工程中的chatgpt，cores.nn在原始工程中变成了chatgpt.models。

GitHub链接：

https://github.com/hpcaitech/ColossalAI

ChatGLM

ChatGLM是清华技术成果转化的公司智谱AI开源的GLM系列的对话模型，支持中英两个语种，目前开源了其62亿参数量的模型。其继承了GLM之前的优势，在模型架构上进行了优化，从而使得部署和应用门槛变低，实现大模型在消费级显卡上的推理应用。

从技术路线上看，其实现了ChatGPT强化学习人类对齐策略，使得生成效果更佳贴近人类价值，其目前能力域主要包括自我认知、提纲写作、文案写作、邮件写作助手、信息抽取、角色扮演、评论比较、旅游建议等，目前其已经开发了正在内测的1300亿的超大模型，算是目前开源平替里面参数规模较大的对话大模型。

详细技术可以参考其GitHub：

https://github.com/THUDM/ChatGLM-6B

LLaMa

LLaMA是由Facebook 母公司Meta发布的全新人工智能大型语言模型，在生成文本、对话、总结书面材料、证明数学定理或预测蛋白质结构等任务上方面表现良好。LLaMA模型支持20种语言，包括拉丁语和西里尔字母语言，目前看原始模型并不支持中文。

LLaMA目前比较火的两个顶流开源项目是ChatLLaMA和stanford_alpaca。

ChatLLaMA是由Nebuly+AI推出的基于人类反馈强化学习的LLaMA+AI聊天机器人的开源实现，它的技术路线类似 ChatGPT，该项目上线刚刚 2 天，狂揽 5.2K 星。

GitHub链接：

https://github.com/nebuly-ai/nebullvm/tree/main/apps/accelerate/chatllama

ChatLLaMA 训练过程算法实现主打比 ChatGPT 训练更快、更便宜，据说能快近15倍，主要特色有：

完整的开源实现，允许用户基于预训练的 LLaMA 模型构建 ChatGPT 风格的服务；

LLaMA 架构更小，使得训练过程和推理速度更快，成本更低；

内置了对 DeepSpeed ZERO 的支持，以加速微调过程；

支持各种尺寸的 LLaMA 模型架构，用户可以根据自身偏好对模型进行微调。

另外一个比较火的是最近刚发布的alpaca（羊驼模型），是由斯坦福基于 Meta 的 LLaMA 7B 模型微调出一个新模型，其基本原理是让 OpenAI 的 text-davinci-003 模型以 self-instruct 方式生成 52K 指令样本，以此来微调LLaMA。该项目已将训练数据、生成训练数据的代码和超参数开源，模型文件尚未开源，以一天多达到5.6K星的关注度，估计很快会开源其模型文件供大家使用。

GitHub链接：

https://github.com/tatsu-lab/stanford_alpaca

DEMO地址：

https://alpaca-ai-custom6.ngrok.io

OpenChatKitk

OpenChatKit由前OpenAI研究员所在的Together团队，以及LAION、Ontocord.ai团队共同打造。OpenChatKit包含200亿个参数，用GPT-3的开源版本GPT-NoX-20B进行微调。同时，不同ChatGPT的强化学习，OpenChatKit采用一个60亿参数的审核模型，对不合适或者是有害的信息进行过滤，确保生成内容的安全和质量。

GitHub链接：

https://github.com/togethercomputer/OpenChatKit

BELLE

基于 Stanford Alpaca ，实现基于Bloom、LLama的监督微调。Stanford Alpaca 的种子任务都是英语，收集的数据也都是英文，该开源项目是促进中文对话大模型开源社区的发展，针对中文做了优化，模型调优仅使用由ChatGPT生产的数据（不包含任何其他数据）。项目包含以下内容：

175个中文种子任务；

生成数据的代码；

10M生成的数据，目前开源了1.5M、0.25M数学指令数据集和0.8M多轮任务对话数据集；

基于BLOOMZ-7B1-mt、LLama-7B优化后的模型。

GitHub链接：

https://github.com/LianjiaTech/BELLE

PaLM-rlhf-pytorch

其号称首个开源ChatGPT平替项目，其基本思路是基于谷歌语言大模型PaLM架构，以及使用从人类反馈中强化学习的方法（RLHF）。PaLM是谷歌在今年4月发布的5400亿参数全能大模型，基于Pathways系统训练。其可以完成写代码、聊天、语言理解等任务，并且在大多数任务上具有强大的少样本学习性能。同时采用了ChatGPT一样的强化学习机制，能让AI的回答更加符合情景要求，降低模型毒性。

GitHub链接：

https://github.com/lucidrains/PaLM-rlhf-pytorch

alpaca-lora

alpaca-lora是斯坦福大学的另一个巨作，其使用LoRA（low-rank adaptation）技术复现了Alpaca的结果，用了一个更加低成本的方法，只在一块RTX 4090显卡上训练5个小时得到了一个Alpaca水平相当的模型。而且，该模型可以在树莓派上运行。在该项目中，其使用了Hugging Face的PEFT来实现廉价高效的微调。PEFT 是一个库（LoRA 是其支持的技术之一），可以让你使用各种基于 Transformer的语言模型并使用LoRA对其进行微调，从而使得在一般的硬件上廉价而有效地微调模型。

GitHub链接：

https://github.com/tloen/alpaca-lora

尽管 Alpaca和alpaca-lora取得了较大的提升，但其种子任务都是英语，缺乏对中文的支持。一方面除了以上提到Belle收集到了大量的中文语料，另一方面基于alpaca-lora等前人工作，来自华中师范大学等机构的三位个人开发者开源的中文语言模型骆驼 (Luotuo)，单卡就能完成训练部署。目前该项目释放了两个模型 luotuo-lora-7b-0.1、luotuo-lora-7b-0.3，还有一个模型在计划中。

‍‍‍‍‍‍  

GitHub链接：

https://github.com/LC1332/Chinese-alpaca-lora

Dolly

Dolly在Alpaca的启发下，用Alpaca数据集，在GPT-J-6B上实现微调，由于Dolly本身是一个模型的“克隆”，所以团队最终决定将其命名为“多莉”。这种克隆式在Alpaca启发下越来越多，总结起来大致采用Alpaca开源的数据获取方式，在6B或者7B规模大小的旧模型上进行指令微调，获得类似ChatGPT的的效果。这种思想很经济，也能迅速模仿出ChatGPT的韵味来，广受欢迎，一经推出star爆棚。

GitHub链接：

https://github.com/databrickslabs/dolly

Vicuna 和 Chinese-Vicuna

斯坦福学者继推出alpaca后，联手CMU、UC伯克利等，推出一个全新模型——130亿参数的Vicuna（俗称小羊驼、骆马）。仅需300美元就能实现ChatGPT 90%的性能。Vicuna是通过在ShareGPT收集的用户共享对话上对LLaMA进行微调训练而来，测试过程使用GPT-4作为评判标准，结果显示Vicuna-13B在超过90%的情况下实现了与ChatGPT和Bard相匹敌的能力。

UC伯克利LMSys org近期又发布了70亿参数的Vicuna，不仅体积小、效率高、能力强，而且只需两行命令就能在M1/M2芯片的Mac上运行，还能开启GPU加速！

GitHub链接：

https://github.com/lm-sys/FastChat/

Chinese-Vicuna GitHub地址：

https://github.com/Facico/Chinese-Vicuna

LMFLOW

ChatGPT爆火后，都在寻找通往圣殿的快捷之路，一些类ChatGPT开始出现，尤其是低成本效仿ChatGPT成为一个热门途径。LMFlow就是在这种需求场景下诞生的产物，他使得在3090这样的普通显卡上也能炼大模型。该项目由香港科技大学统计和机器学习实验室团队发起，致力于建立一个全开放的大模型研究平台，支持有限机器资源下的各类实验，并且在平台上提升现有的数据利用方式和优化算法效率，让平台发展成一个比之前方法更高效的大模型训练系统。

利用该项目，即便是有限的计算资源，也能让使用者针对专有领域支持个性化训练。例如LLaMA-7B，一张3090耗时 5 个小时即可完成训练，成本大幅降低。该项目还开放了网页端即刻体验问答服务 (lmflow.com)。LMFlow的出现和开源使得普通资源可以训练问答、陪伴、写作、翻译、专家领域咨询等各种任务。目前很多研究者们正在尝试用该项目训练650亿甚至更高参数量的大模型。

GitHub链接：

https://github.com/OptimalScale/LMFlow

GPTrillion

该项目号称开源的最大规模模型，高达1.5万亿，且是多模态的模型。其能力域包括自然语言理解、机器翻译、智能问答、情感分析和图文匹配等。

其开源地址为：

https://huggingface.co/banana-dev/GPTrillion

OpenFlamingo

OpenFlamingo是一个对标GPT-4、支持大型多模态模型训练和评估的框架，由非盈利机构LAION重磅开源发布，其是对DeepMind的Flamingo模型的复现。目前开源的是其基于LLaMA的 OpenFlamingo-9B模型。Flamingo模型在包含交错文本和图像的大规模网络语料库上进行训练，具备上下文少样本学习能力。OpenFlamingo实现了原始Flamingo中提出的相同架构，在一个新的多模态C4数据集的5M样本和LAION-2B的10M样本上训练而来。

该项目的开源地址：

https://github.com/mlfoundations/open_flamingo

Baize白泽

该项目提出了一个自动收集 ChatGPT 对话的方法，让 ChatGPT 自我对话，批量生成高质量多轮对话数据集，分别收集了5万条左右Quora、StackOverflow和MedQA的高质量问答语料，并已经全部开源。同时其改进了LLama模型，效果还不错。白泽同样采用目前低成本的LoRA微调方案，获得白泽-7B、13B 和30B三种不同尺度，以及一个医疗垂直领域的模型。遗憾的是中文名字起的不错，但目前仍然不支持中文，中文的白泽模型据悉在计划中，未来发布。

其开源github地址：

https://github.com/project-baize/baize

Koala考拉

基于LLama的ChatGPT平替继续发酵，UC伯克利的伯克利发布了一个可以在消费级GPU上运行的对话模型Koala，参数达到13B。Koala 的训练数据集包括如下几个部分：ChatGPT数据和开源数据（Open Instruction Generalist (OIG)、斯坦福 Alpaca 模型使用的数据集、Anthropic HH、OpenAI WebGPT、OpenAI Summarization）。Koala模型在EasyLM中使用JAX/Flax实现，用了8 个A100 GPU，完成2轮迭代需要6个小时。评测效果优于Alpaca，达到ChatGPT 50%的性能。

开源地址：

https://github.com/young-geng/EasyLM

StackLLaMA

随着斯坦福Alpaca的出现，一大堆基于LLama的羊驼家族和扩展动物家族开始出现，终于Hugging Face研究人员近期发布了一篇博客StackLLaMA：用RLHF训练LLaMA的实践指南。同时也发布了一个70亿参数的模型——StackLLaMA。这是一个通过人类反馈强化学习在LLaMA-7B微调而来的



## 哈工大-Hua Tuo 

华驼（Hua Tuo）是基于中文医学知识的 LLaMa 指令微调模型，在智能问诊层面表现出色，可生成一些更为可靠的医学知识回答。在生物医学领域，已发布的大语言模型模型因为缺乏一定的医学专业知识语料而表现不佳。4 月 14 日，哈尔滨工业大学一团队发布了其对 LLaMa 模型进行指令微调后得到的、针对医学领域的、开源智能问诊模型 Hua Tuo。



## 大模型迎来「开源季」，盘点过去一个月那些开源的LLM和数据集

https://www.easemob.com/news/10252


### 开源数据

对于开源 AI，过去一个月特别令人兴奋，出现了几个 LLM 的开源实现和一大波开源数据集。这些数据集包括 Databricks Dolly 15k、用于指令微调的 OpenAssistant Conversations (OASST1)、用于预训练的 RedPajama。这些数据集工作尤其值得称赞，因为数据收集和清理占了真实世界机器学习项目的 90％，但很少有人喜欢这项工作。

Databricks-Dolly-15 数据集

Databricks-Dolly-15 是一个用于 LLM 微调的数据集，它由数千名 DataBricks 员工编写了超过 15,000 个指令对（与训练 InstructGPT 和 ChatGPT 等系统类似）。

OASST1 数据集


## hugging face

https://huggingface.co/

