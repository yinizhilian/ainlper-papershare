定期更新最新NLP研究进展，涉及NLP领域的各个方向。此项目长期不定时更新，欢迎watch和fork！不过给个star⭐就更好了❤️。

知乎地址：[**ShuYini**](https://www.zhihu.com/people/wangjini521/activities)

微信公众号: [**AINLPer**（每日更新，欢迎关注）](https://mp.weixin.qq.com/s?__biz=MzUzOTgwNDMzOQ==&mid=2247487079&idx=1&sn=4aa0c38c7701148f28f67bc66a291b00&chksm=fac399bbcdb410ad4517460b96a071c08c3854d67d1beafa4caa424e9c12791dc1955be1f56e&token=802874842&lang=zh_CN#rd)

#### 人工反馈强化学习（RLHF）

**1、[斯坦福 发布 AlpacaFarm (羊驼农场)，可将RLHF人工成本降低45倍！(开源)](https://mp.weixin.qq.com/s/CIF2F5Vx_RSN1-LwU_ppOQ)** 

<p align="center"><img src="assets/image-20230525141242754.png" alt="image-20230525141242754" style="zoom:25%;" height="50px" /> </p>

**AlpacaFarm: A Simulation Framework for Methods that Learn from Human Feedback**

AlpacaFarm（羊驼农场）的模拟器，旨在降低训练语言模型的成本，且比人工成本低45倍，并表现出与人类反馈的高度一致性，同时也为RLHF的研究开辟了新的道路。[[paper](https://tatsu-lab.github.io/alpaca_farm_paper.pdf)]，[[code](https://github.com/tatsu-lab/alpaca_farm)]

**2、[Meta最新模型：LIMA-65B，没有RLHF，模型效果远胜Alpaca！！](https://mp.weixin.qq.com/s/cA6HoPsLhPdQ_ntlL2MKDw)**

**LIMA: Less Is More for Alignment**

Meta发布的最新研究成果：即，在没有任何RLHF的情况下，使用1000个精心筛选的提示和响应对LLaMA-65B进行微调得到了LIMA模型，实验表明该模型展现出了非常强大的性能，最后作者指出几乎所有大型语言模型的知识都是在预训练期间学习的，仅需要有限的指导调整数据来教模型产生高质量的输出。[[paper](https://arxiv.org/pdf/2305.11206.pdf)]



#### 大语言模型调优

**1、[QLoRA：一种高效LLMs微调方法，48G内存可调LLaMA-65B (开源)](https://mp.weixin.qq.com/s/U9uHJrg3FbUprlZ46dptTQ)**

**QLORA: Efficient Finetuning of Quantized LLMs**

QLoRA是一种**高效的微调方法**，可以在保持完整的16位微调任务性能的情况下，将内存使用降低到足以**「在单个48GB GPU上微调650亿参数模型」**。作者公布了他们训练的系列模型Guanaco，与之前公开发布的所有模型相比，在Vicuna基准测试中表现更好，**只需要在单个GPU上微调24小时就能达到ChatGPT性能水平的99.3%**。[[paper](https://arxiv.org/pdf/2305.14314.pdf)]，[[code](https://github.com/artidoro/qlora)]

**2、[Adam该换了！斯坦福最新Sophia优化器，比Adam快2倍，几行代码即可实现！](https://mp.weixin.qq.com/s?__biz=MzUzOTgwNDMzOQ==&mid=2247492294&idx=1&sn=1711a9003bcf92d2c9c6afba28fba561&chksm=fac0751acdb7fc0cb3dfa1c8667a1801cbe8fa6e16745386e1e620be79b47a112c9b33789dd8&token=338711096&lang=zh_CN#rd)**

**Sophia: A Scalable Stochastic Second-order Optimizer for Language Model Pre-training**

文章一种新的模型预训练优化器：Sophia（Second-order Clipped Stochastic Optimization），这是一种轻量级二阶优化器，它使用Hessian对角线的廉价随机估计作为预调节器，并通过限幅机制来控制最坏情况下的更新大小。**相比Adam，它在LLM上能够快2倍，可以大幅降低预训练成本**。[[paper](file:///C:/Users/Lenovo/Desktop/0526.pdf)]

