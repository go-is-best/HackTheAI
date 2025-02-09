# 常用网站

- <https://chat.lmsys.org/> AI 模型的 benchmarks🏆

# 基础名词解释[^source1][^source2][^source3]

[^source1]:<https://aigc.phodal.com/6-llm-glossary.html>
[^source2]:<https://zhuanlan.zhihu.com/p/615074572>
[^source3]:<https://pub.towardsai.net/tokens-and-models-understanding-langchain-%EF%B8%8F-part-3-e471aececf19>

## LLM

LLM（Large Language Model，大规模语言模型）是基于深度学习技术构建的人工智能模型，由具有数以亿计参数的人工神经网络组成，通过自监督学习或半监督学习在大量无标签文本上进行训练。

LLM 于 2018 年左右出现，并在各种任务上表现出色。这改变了自然语言处理研究的重点，使其不再是以训练特定任务的专门监督模型为范式。

## AIGC

AIGC（AI-Generated Content，AI 生成内容）通过对已有数据进行学习和模式识别，以适当的泛化能力生成相关内容的技术。

AIGC 技术的核心思想是利用人工智能算法生成具有一定创意和质量的内容。通过训练模型和大量数据的学习，AIGC 可以根据输入的条件或指导，生成与之相关的内容。

## Prompt

Prompt（提示词）是指给定的一段文本或问题，用于引导和启发人工智能模型生成相关的回答或内容。 Prompt 可以设定任务目标、要求模型回答特定问题、完成特定任务，或者给模型提供背景信息以进行更准确的生成。

需要注意的是，Prompt 本身并不包含问题的答案或具体的内容，它只是一种指导模型生成文本的方式。模型的输出仍然是基于其训练数据和学习到的模式进行生成的。

## GPT

GPT（Generative Pre-trained Transformer，生成对抗网络）是一种基于深度学习的大规模语言模型。最初由 OpenAI 开发，旨在通过训练模型预测下一个单词或字符来学习自然语言的统计规律和上下文信息。

GPT 使用 Transformer 模型架构，它由多个编码器 - 解码器堆叠而成，通过自注意力机制来处理输入序列和生成输出。模型的训练采用了无监督学习的方法，使用大量的文本数据进行预训练，使模型具备了广泛的语言理解和生成能力。

## Token

Token 是指在自然语言处理和文本处理任务中，将文本分解成较小单元的基本单位。这些单元可以是单词、字符、子词或其他语言单位，具体取决于任务和处理方式。

分割文本成 Token 有助于进行文本处理和分析，例如词频统计、语言模型训练、机器翻译、文本分类等任务。将文本分解成 Token 的过程可以提供更细粒度的语义信息，并为模型理解和处理文本提供基础。

Token 涉及到计费以及能生成多少返回。OpenAI的模型参数中有一项名为 MAX TOKENS，它限制了在一个请求中可以产生的 tokens 数量。MAX TOKENS 的限制包括 Prompt 和完成两个方面。这意味着，如果你的 Prompt 是 1000 个 token，你最多只能生成 3000 个 token 的完成文本。第二，MAX TOKENS的限制是由 OpenAI 的服务器执行的。如果你试图生成超过限制的文本，你的请求将被拒绝。

一般经验是 100 token = 75 英文单词，openai 提供了准确的测量网页：<https://platform.openai.com/tokenizer> 编程中，使用 <https://github.com/openai/tiktoken> 库

## LoRA

LoRA（Low-Rank Adaptation of LLM，即插件式的微调）用于对大语言模型进行个性化和特定任务的定制。LoRA 通过将模型的权重矩阵分解为低秩的近似矩阵，降低了参数空间的复杂性，从而减少了微调的计算成本和模型存储需求。

传统的微调方法通常需要在整个模型上进行参数优化，这可能会导致训练时间长、计算资源消耗大，并且需要大量的标注数据。而低秩适应方法则提供了一种更高效的微调策略，基于对原始模型的分析，选择性地微调模型的某些部分，使其更适应于特定的任务或数据。

## 矢量数据库

矢量数据库（Vector Database）是一种用于存储和检索矢量数据的数据库。矢量数据库可以存储和管理大量的矢量数据，例如图像、视频、音频、文本等，同时提供高效的检索功能。

矢量数据库通常基于矢量搜索引擎实现，它可以将矢量数据转换为向量表示，并将其存储在数据库中。在查询时，矢量搜索引擎可以将查询数据转换为向量表示，并在数据库中进行相似度匹配，从而找到与之最相似的数据。

## 数据蒸馏

数据蒸馏（Knowledge Distillation）旨在将给定的一个原始的大数据集浓缩并生成一个小型数据集，使得在这一小数据集上训练出的模型，和在原数据集上训练得到的模型表现相似

数据蒸馏技术在深度学习领域中被广泛应用，特别是在模型压缩和模型部署方面。它可以帮助将复杂的模型转化为更轻量级的模型，并能够促进模型的迁移学习和模型集成，提高模型的鲁棒性和泛化能力。

## 模型中的 175B、60B、540B 等

这些一般指参数的个数，B 是 Billion / 十亿的意思，175B 是 1750 亿参数，这是 ChatGPT 大约的参数规模。

## 强化学习

（Reinforcement Learning）一种机器学习的方法，通过从外部获得激励来校正学习方向从而获得一种自适应的学习能力。

## 基于人工反馈的强化学习（RLHF）

（Reinforcement Learning from Human Feedback）构建人类反馈数据集，训练一个激励模型，模仿人类偏好对结果打分，这是 GPT-3 后时代大语言模型越来越像人类对话核心技术。

## 涌现

（Emergence）或称创发、突现、呈展、演生，是一种现象。许多小实体相互作用后产生了大实体，而这个大实体展现了组成它的小实体所不具有的特性。研究发现，模型规模达到一定阈值以上后，会在多步算术、大学考试、单词释义等场景的准确性显著提升，称为涌现。

## 泛化

（Generalization）模型泛化是指一些模型可以应用（泛化）到其他场景，通常为采用迁移学习、微调等手段实现泛化。

## 微调

（FineTuning）针对大量数据训练出来的预训练模型，后期采用业务相关数据进一步训练原先模型的相关部分，得到准确度更高的模型，或者更好的泛化。

## 指令微调

（Instruction FineTuning），针对已经存在的预训练模型，给出额外的指令或者标注数据集来提升模型的性能。

## 思维链

（Chain-of-Thought，CoT）。通过让大语言模型（LLM）将一个问题拆解为多个步骤，一步一步分析，逐步得出正确答案。需指出，针对复杂问题，LLM 直接给出错误答案的概率比较高。思维链可以看成是一种指令微调。

## 量化等级

（Quantization Aware Training）量化训练是指在训练过程中，将模型的参数转换为低精度的数据类型，例如 8 位整数、16 位浮点数等，从而减少模型的存储空间和计算量。

（Quantization Level）模型量化等级是指模型的精度，通常为 8 位、16 位、32 位等。

### 不同量化等级的区别

不同量化等级之间的区别主要在于模型的精度和所需的存储空间与计算量。

1. 32位浮点数（FP32）：这是最常见的模型表示形式，参数和计算都以32位浮点数进行存储和计算。它提供了最高的模型精度和计算精度，但需要更多的存储空间和计算资源。

2. 16位浮点数（FP16）：使用16位浮点数进行模型参数和计算的表示。相比于32位浮点数，它减少了存储空间和计算量，但可能会引入一些精度损失。在某些情况下，使用FP16可以在保持相对较高模型精度的同时，提高训练和推理的速度。

3. 8位整数（INT8）：使用8位整数进行模型参数和计算的表示。相比于浮点数，INT8进一步减少了存储空间和计算量，但引入了更大的精度损失。在一些场景下，INT8量化可以显著降低模型的计算需求，加快推理速度，并节省存储空间。

需要注意的是，量化等级的选择需要根据具体应用的需求和硬件平台的支持来确定。较低的量化等级可以带来存储空间和计算效率的提升，但也可能会牺牲一定的模型精度。因此，在选择量化等级时，需要进行权衡和评估，以确保在满足性能需求的同时不过度降低模型的精度。

# AI中的工具链

## 常用命令

1. 查看 GPU 信息

```bash
nvidia-smi
```

## NVIDIA Container Toolkit

[NVIDIA Container Toolkit](https://github.com/NVIDIA/nvidia-container-toolkit)

NVIDIA Container Toolkit 是一个用于 GPU 加速的容器运行时，它可以帮助开发者在容器中使用 GPU 进行计算。NVIDIA Container Toolkit 包含了 nvidia-docker 和 NVIDIA Container Runtime，可以帮助开发者在容器中使用 GPU 进行计算。

![container-toolkit](https://cloud.githubusercontent.com/assets/3028125/12213714/5b208976-b632-11e5-8406-38d379ec46aa.png)

安装指南:

<https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html>

## CUDA Toollkit

CUDA Toolkit 是一个用于 GPU 加速的开发平台，它包含了 GPU 加速的库、编译器、开发工具以及 CUDA 运行时。CUDA Toolkit 可以帮助开发者在 NVIDIA GPU 上进行并行计算，从而加速应用程序的运行速度。

## JupyterLab

[JupyterLab](<https://jupyter.org/>) 是一个基于 Web 的交互式开发环境，它可以帮助开发者在浏览器中编写代码、运行代码、查看结果，并且可以将代码、图表、文档等内容整合在一起，形成一个完整的笔记本。
