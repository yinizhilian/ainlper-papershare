#### 人工反馈强化学习（RLHF）

##### 1、[斯坦福 发布 AlpacaFarm (羊驼农场)，可将RLHF人工成本降低45倍！(开源)](https://mp.weixin.qq.com/s/CIF2F5Vx_RSN1-LwU_ppOQ) 

<p align="center"><img src="assets/image-20230525141242754.png" alt="image-20230525141242754" style="zoom:25%;" height="50px" /> </p>

**AlpacaFarm: A Simulation Framework for Methods that Learn from Human Feedback**

AlpacaFarm（羊驼农场）的模拟器，旨在降低训练语言模型的成本，且比人工成本低45倍，并表现出与人类反馈的高度一致性，同时也为RLHF的研究开辟了新的道路。[[paper](https://tatsu-lab.github.io/alpaca_farm_paper.pdf)]，[[code](https://github.com/tatsu-lab/alpaca_farm)]

##### 2、[Meta最新模型：LIMA-65B，没有RLHF，模型效果远胜Alpaca！！](https://mp.weixin.qq.com/s/cA6HoPsLhPdQ_ntlL2MKDw)

**LIMA: Less Is More for Alignment**

Meta发布的最新研究成果：即，在没有任何RLHF的情况下，使用1000个精心筛选的提示和响应对LLaMA-65B进行微调得到了LIMA模型，实验表明该模型展现出了非常强大的性能，最后作者指出几乎所有大型语言模型的知识都是在预训练期间学习的，仅需要有限的指导调整数据来教模型产生高质量的输出。[[paper](https://arxiv.org/pdf/2305.11206.pdf)]



#### 大语言模型调优

**1、[QLoRA：一种高效LLMs微调方法，48G内存可调LLaMA-65B (开源)](https://mp.weixin.qq.com/s/U9uHJrg3FbUprlZ46dptTQ)**

**QLORA: Efficient Finetuning of Quantized LLMs**

QLoRA是一种**「高效的微调方法」**，可以在保持完整的16位微调任务性能的情况下，将内存使用降低到足以**「在单个48GB GPU上微调650亿参数模型」**。作者公布了他们训练的系列模型Guanaco，与之前公开发布的所有模型相比，在Vicuna基准测试中表现更好，**「只需要在单个GPU上微调24小时就能达到ChatGPT性能水平的99.3%」**。[[paper](https://arxiv.org/pdf/2305.14314.pdf)]，[[code](https://github.com/artidoro/qlora)]

