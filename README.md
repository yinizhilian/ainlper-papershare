本仓库旨在收集NLP最新研究进展，尤其是LLM方面，涉及NLP领域的各个方向，此项目长期不定时更新。

欢迎watch和fork！不过给个star⭐就更好了❤️。

知乎地址：[**ShuYini**](https://www.zhihu.com/people/wangjini521/activities)

微信公众号: [**AINLPer**（每日更新，欢迎关注）](https://mp.weixin.qq.com/s?__biz=MzUzOTgwNDMzOQ==&mid=2247487079&idx=1&sn=4aa0c38c7701148f28f67bc66a291b00&chksm=fac399bbcdb410ad4517460b96a071c08c3854d67d1beafa4caa424e9c12791dc1955be1f56e&token=802874842&lang=zh_CN#rd)

### 目录

[**一、人工反馈强化学习（RLHF）**](#人工反馈强化学习（RLHF）)

[**二、大语言模型（LLMs）调优**](#二、大语言模型（LLMs）调优)

[**三、大语言模型（LLMs）应用**](#三、大语言模型（LLMs）应用)

[四、大语言模型（LLMs）评估](#大语言模型（LLMs）评估)

[**五、大模型(LLMs)周边**](#五、大模型(LLMs)周边)



# 人工反馈强化学习（RLHF）

**1、[斯坦福 发布 AlpacaFarm (羊驼农场)，可将RLHF人工成本降低45倍！(开源)](https://mp.weixin.qq.com/s/CIF2F5Vx_RSN1-LwU_ppOQ)** 

<p align="center"><img src="assets/image-20230525141242754.png" alt="image-20230525141242754" style="zoom:25%;" height="50px" /> </p>

**AlpacaFarm: A Simulation Framework for Methods that Learn from Human Feedback**

AlpacaFarm（羊驼农场）的模拟器，旨在降低训练语言模型的成本，且比人工成本低45倍，并表现出与人类反馈的高度一致性，同时也为RLHF的研究开辟了新的道路。[[paper](https://tatsu-lab.github.io/alpaca_farm_paper.pdf)]，[[code](https://github.com/tatsu-lab/alpaca_farm)]

**2、[Meta最新模型：LIMA-65B，没有RLHF，模型效果远胜Alpaca！！](https://mp.weixin.qq.com/s/cA6HoPsLhPdQ_ntlL2MKDw)**

**LIMA: Less Is More for Alignment**

Meta发布的最新研究成果：即，在没有任何RLHF的情况下，使用1000个精心筛选的提示和响应对LLaMA-65B进行微调得到了LIMA模型，实验表明该模型展现出了非常强大的性能，最后作者指出几乎所有大型语言模型的知识都是在预训练期间学习的，仅需要有限的指导调整数据来教模型产生高质量的输出。[[paper](https://arxiv.org/pdf/2305.11206.pdf)]



# 二、大语言模型（LLMs）调优

**1、[QLoRA：一种高效LLMs微调方法，48G内存可调LLaMA-65B (开源)](https://mp.weixin.qq.com/s/U9uHJrg3FbUprlZ46dptTQ)**

**QLORA: Efficient Finetuning of Quantized LLMs**

QLoRA是一种**高效的微调方法**，可以在保持完整的16位微调任务性能的情况下，将内存使用降低到足以**「在单个48GB GPU上微调650亿参数模型」**。作者公布了他们训练的系列模型Guanaco，与之前公开发布的所有模型相比，在Vicuna基准测试中表现更好，**只需要在单个GPU上微调24小时就能达到ChatGPT性能水平的99.3%**。[[paper](https://arxiv.org/pdf/2305.14314.pdf)]，[[code](https://github.com/artidoro/qlora)]

**2、[Adam该换了！斯坦福最新Sophia优化器，比Adam快2倍，几行代码即可实现！](https://mp.weixin.qq.com/s?__biz=MzUzOTgwNDMzOQ==&mid=2247492294&idx=1&sn=1711a9003bcf92d2c9c6afba28fba561&chksm=fac0751acdb7fc0cb3dfa1c8667a1801cbe8fa6e16745386e1e620be79b47a112c9b33789dd8&token=338711096&lang=zh_CN#rd)**

**Sophia: A Scalable Stochastic Second-order Optimizer for Language Model Pre-training**

文章一种新的模型预训练优化器：Sophia（Second-order Clipped Stochastic Optimization），这是一种轻量级二阶优化器，它使用Hessian对角线的廉价随机估计作为预调节器，并通过限幅机制来控制最坏情况下的更新大小。**相比Adam，它在LLM上能够快2倍，可以大幅降低预训练成本**。[[paper](file:///C:/Users/Lenovo/Desktop/0526.pdf)]

**3、[DTG：一种简单有效的Prompt方法，激发大模型思考判断能力！](https://mp.weixin.qq.com/s/Eio62_Hn0mML3Pfb3G36cA)**

**Deliberate then Generate: Enhanced Prompting Framework for Text Generation**

本文介绍了一种新的大语言模型的提示框架：Deliberate then Generate (DTG)。与现有提示方法不同的是，DTG不仅提供正确信息，而且还会提供包含错误的信息，来引导模型进行自我思考判断。**该技术简单有效，可适用于各种文本生成任务**。[[Paper](https://arxiv.org/pdf/2305.19835.pdf)]

**4、[模块化Prompt多任务预训练，可快速适应下游任务（含源码）](https://mp.weixin.qq.com/s/ytSq_gBb63NhpNOaMcMXew)**

**Multitask Pre-training of Modular Prompt for Chinese Few-Shot Learning**

当面对Few-shot场景时，PT的调优方法还是存在一定的局限性。针对这个问题，复旦提出了**多任务预训练模块化Prompt（简称为：$MP^2$），来提高模型在Few-shot场景下的PT效果，使模型能够快速适应下游任务**。[[paper](https://arxiv.org/pdf/2210.07565.pdf)]、[[code](https://github.com/Hzfinfdu/MPMP)]



# 三、大语言模型（LLMs）应用

**1**、[**伯克利最新研究: Gorilla，赋予LLMs使用工具(API)的能力，实现更复杂计算任务**](https://mp.weixin.qq.com/s/VwkaE_FuUhL3ejhMXpfp9A)

<p align="center"><img src="assets/logo.png" alt="logo" style="zoom:50%" height="50px" /> </p>

**Gorilla: Large Language Model Connected with Massive APIs**

**伯克利的最新研究讨论了如何赋予大型语言模型（LLMs）使用工具的能力**，以便它们可以访问更大、更动态的知识库并完成复杂的计算任务。为推进该领域的研究，他们分享了APIBench数据集，它是一个由TorchHub、TensorHub和HuggingFace API Model Cards构建的综合基准测试；**训练了Gorilla模型，通过使用文档检索器，超越了当前最先进的GPT-4模型在编写API调用方面的表现。同时，Gorilla还能够适应测试时间文档变化，并大大减轻因向LLM直接提示诱发错误提示的问题**。[[paper](https://arxiv.org/pdf/2305.15334v1.pdf)]，[[Code](https://github.com/ShishirPatil/gorilla)]

**2**、**[一个专用于长文档推理的提示框架PEARL，性能比GPT-4高10.5%！](https://mp.weixin.qq.com/s/dQhRiH62Mz9umx7GFeQRvw)**

**PEARL: Prompting Large Language Models to Plan and Execute Actions Over Long Documents**

本文介绍了PEARL框架，旨在提升大型语言模型对长篇文档的理解能力，在Zero-shot情况下，**性能比GPT-4高10.5%**！。PEARL被认为是利用语言模型进行复杂推理的重要步骤，为新的推理可能性打开了大门。[[paper](https://arxiv.org/abs/2305.14564)]、[[Code](https://github.com/SimengSun/pearl)]

**3**、[**近乎完美！最强算术语言模型: Goar-7B，干翻GPT-4，怒越PaLM-540B！24G可训练**](https://mp.weixin.qq.com/s/_haINkHNV4bMszm9F41yXA)

**Goat: Fine-tuned LLaMA Outperforms GPT-4 on Arithmetic Tasks**

前两天，OpenAI对step-by-step数学推理问题发表了最新的研究，指出了**「过程监督优于结果监督」**的结论，旨在提升GPT-4的数学推理能力。这篇文章基于该理论（**「好像比OpenAI要早」**），旨在提升模型大数计算能力，基于LLaMA预训练了Goat模型，Goar-7B在Zero-shot上的准确效果，堪比、甚至超越PaLM-540B模型的Few-shot结果；在大数计算方面远超GPT-4。[[paper](https://arxiv.org/pdf/2305.14201.pdf)]、[[code](https://github.com/liutiedong/goat)]

**4**、[**Amazon | 深入研究LLMs与AutoGPT的结合：揭示出GPT-4惊人的人类决策能力！**](https://mp.weixin.qq.com/s/Gbz7ZVVdeTq64mj1-__aQA)

**Auto-GPT for Online Decision Making: Benchmarks and Additional Opinions**

作者针对决策任务，对Auto-GPT代理进行了全面的基准研究，探索了大型语言模型（LLM）在决策任务中的应用。**「实验结果表明GPT4有了类似于人类的能力，可以从不同的意见中提取有用信息，进行思考和批判然后提高自己的结果」**。[[paper](https://arxiv.org/pdf/2306.02224.pdf)]、[[code](https://github.com/younghuman/LLMAgent)]

**5**、[**FinGPT：一个「专用于金融领域」的开源大语言模型（LLM）框架，源码公开！**](https://mp.weixin.qq.com/s/A9euFin675nxGGciiX6rJQ)

**FinGPT: Open-Source Financial Large Language Models**

本文作者**「提出了一个开源的大语言模型框架FinGPT，专门用于金融领域」**，它采用以数据为中心的方法，为研究人员提供了可访问和资源来开发自己FinLLMs。该框架可用在智能投顾、情绪分析、量化交易、风险管理、破产预测、金融教育培训等方面。[[paper](https://arxiv.org/pdf/2306.06031v1.pdf)]、[[code](https://github.com/ai4finance-foundation/fingpt)]

**6**、[**怒超 GPT-4！LONGMEM：提升大语言模型（LLMs）长文本处理能力，最高可达64k**](https://mp.weixin.qq.com/s/LiWN7iONxgEOIPnJXjYgQw)

**Augmenting Language Models with Long-Term Memory**

本文提出了一种名为**LONGMEM的方法架构**，该方法将长文本序列分块并利用存储器进行处理且无需对模型进行重训练，**最高可支持64k个Token**，**有效的提高了模型长文本处理能力**，相比GPT-4多了一倍。[[paper](https://arxiv.org/pdf/2306.07174v1.pdf)]、[[code](https://github.com/Victorwz/LongMem)]

**7、[微软 & 麻省理工 | 实验结果表明：代码自修复能力仅存在GPT-4！GPT-3.5不具备该能力](https://mp.weixin.qq.com/s/MXKIMXzIkTKLMXYgSNWYBw)**

**Demystifying GPT Self-Repair for Code Generation**

作者探讨了GPT在代码自修复应用场景下的影响，作者引入了一种名为"pass@t"的评估策略，通过对比实验发现，**自我修复的有效性仅在GPT-4中可见，GPT-3.5不具备代码自修复能力**。[[paper](https://arxiv.org/pdf/2306.09896.pdf)]



# 大语言模型（LLMs）评估

**1**、[**潜力发掘！INSTRUCTEVAL：一个专用于的大型语言模型(LLMs)的全面评估方法**](https://mp.weixin.qq.com/s/E6hq0AUy_hItA5HGo2tCAQ)

**INSTRUCTEVAL: Towards Holistic Evaluation of Instruction-Tuned Large Language Models**

本文提出了一个**「专门针对指令调优大型语言模型的全面评估方法INSTRUCTEVAL」**，该评估方法可以从问题解决、写作和人类价值对齐等三个方面对模型进行全面评估。[[paper](https://arxiv.org/pdf/2306.04757.pdf)]、[[code](https://github.com/declare-lab/instruct-eval)]

**2、[PokémonChat | 用 “宝可梦”数据来分析大模型对话能力！！](https://mp.weixin.qq.com/s/1aYGPIyyUHnfVSjo0KTaNQ)**

**PokemonChat: Auditing ChatGPT for Pokémon Universe Knowledge**

**本文基于Pokémon知识来验证ChatGPT的对话能力，并提出了一个可泛化使用的大模型评估会话框架」，**尤其将其用做大语言模型(LLMs)**「在特定领域、特定知识的验证」**会是一个不错的方法。[[paper](https://arxiv.org/pdf/2306.03024.pdf)]、[[code](https://www.pokemon.com/us)]



# 五、大模型(LLMs)周边

**1**、[**大语言模型(LLM)时代，众包数据变得不可靠，呼吁保持数据人性化！**](https://mp.weixin.qq.com/s/tG2w-xy0IUS65CqCG_uHdg)

**Artificial Artificial Artificial Intelligence: Crowd Workers Widely Use Large Language Models for Text Production Tasks**

随着大型语言模型(LLMs)的发展，众包工作人员为增加收入，开始普遍使用LLMs来提高生产效率。由于基于LLMs合成的数据可能会延续偏见和意识形态，这势必会影响众包数据的质量，**「那么未来的众包标注数据还可靠吗」**？[[paper](https://arxiv.org/pdf/2306.07899.pdf)]、[[code](https://github.com/epfl-dlab/GPTurk)]



