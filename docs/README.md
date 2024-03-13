![Kubernetes](https://img.shields.io/badge/kubernetes-%23326ce5.svg?style=flat&logo=kubernetes&logoColor=white)
![release](https://img.shields.io/badge/version-0.1.0-blue)
![fine-tuning](https://img.shields.io/badge/fine--tuning-8B3E3)
# Welcome 👋
# 概述 📋
***DataTunerX (DTX)*** 被设计为与分布式计算框架集成的云原生解决方案。利用可扩展的 *GPU* 资源, i是一个专注于高效微调 *LLMs*的平台，重点放在实用性上。 其核心优势在于促进批量微调任务，使用户能够在单个***实验***中同时进行多个任务。 ***DTX*** 包含了 ***数据集管理***、***超参数控制***、***微调工作流***、***模型管理***、***模型评估***、***模型比较推断*** 和 ***模块化插件系统*** 等基本功能。


**状态**:  

*v0.1.0* - 早期开发阶段。 请查看[CHANGELOG](./CHANGELOG.md) 以获取最近更新的详细信息。

**操作演示视频**:  

<div align="center">
      <a href="https://www.youtube.com/watch?v=NvOzKj67oRQ">
         <img src="https://img.youtube.com/vi/NvOzKj67oRQ/maxresdefault.jpg" style="width:50%;">
      </a>
</div>


[//]: # (**Screenshot**:)

[//]: # ()
[//]: # (![**DTX Screenshot**]&#40;https://raw.githubusercontent.com/DataTunerX/datatunerx-controller/main/assets/screenshot/Job_Details.png&#41;)

----
# 主要功能 💪
***DTX*** 为用户提供了一组强大的功能，旨在有效地微调大型语言模型。深入了解使 ***DTX*** 成为多功能平台的功能：

**1.数据集管理：**

* 支持通过 *S3* 协议（ *http* 即将到来）和本地数据集上传，轻松管理数据集。
* 数据集按照测试、验证和训练等划分进行组织。
* 特征映射提高了微调任务的灵活性。
* 根据训练的数据地址，验证的数据地址，测试的数据地址等信息定义数据集。
* 修改数据集的信息。
* 展示数据集的列表信息和详细信息。
* 删除已经存在的数据集。
* 支持使用数据集插件的方式创建数据集。

<div align="center">
  <img src="https://raw.githubusercontent.com/DataTunerX/datatunerx-controller/main/assets/design/datasetplugindark.png" alt="FineTune" width="30%" height="30%" />
</div>

**2. 微调实验：**

* 通过创建多个微调作业来进行微调实验。
* 每个作业可以使用不同的LLM、数据集和超参数。
* 支持设置一个微调实验使用的评估方式，以相同的评估方式给这次实验的所有任务进行模型评估，得到本次实验的最佳微调模型。
* 支持查看每一个微调实验中的每一个微调任务的详情、日志、监控信息。
* 目前支持 lora 的方式进行大模型的微调能力。
* 目前支持 llama2 的模型微调能力。

<div align="center">
  <img src="https://raw.githubusercontent.com/DataTunerX/datatunerx-controller/main/assets/design/finetunedark.png" alt="FineTune" width="30%" />
  <img src="https://raw.githubusercontent.com/DataTunerX/datatunerx-controller/main/assets/design/finetunejobdark.png" alt="FineTuneJob" width="30%" />
  <img src="https://raw.githubusercontent.com/DataTunerX/datatunerx-controller/main/assets/design/finetuneexdark.png" alt="FineTuneExperiment" width="30%" />
</div>

**3. 作业洞察：**

深入了解实验中每个微调作业的详细信息。探索作业详情、日志和度量可视化，包括学习率趋势、训练损失等。

**4.模型评估：**

* 创建一个评估对象，内置支持设置相关的问题和期望的答案，基于此来评估微调出来的模型的评分。
* 查看、修改、删除评估对象。
* 支持使用评估插件的方式创建评估对象。

**5. 模型仓库：**

* 将LLM存储在模型仓库中，便于高效管理和部署推理服务。
* 显示所有实验微调出来的模型。
* 利用微调出来的模型进行部署推理服务。
* 支持根据分类进行过滤。

<div align="center">

  <img src="https://raw.githubusercontent.com/DataTunerX/datatunerx-controller/main/assets/design/evaldark.png" alt="FineTune" width="50%" height="70%" />
</div>

**6. 超参数组管理：**

利用丰富的参数配置系统，支持多样化的参数和基于模板的区分。

**7. 推理服务：**

* 同时部署多个模型的推理服务，实现简单直观地比较和选择性能最佳的模型。
* 显示从模型仓库创建出来的推理服务，包括列表的方式显示以及详情。
* 选择多个推理服务，使用相同的问题，让所有选择的推理服务同时回答这个问题，对比不同模型的推理服务的回答效果。支持在对比的过程中，展示计算性能数据，包括回复的 token 总数、每秒生成的 token 数、总的耗时是多少等性能数据。

**8. 插件系统：**

* 利用插件系统为数据集和评估单元提供支持，使用户能够集成专门的数据集和评估方法，以满足其独特需求。
* 创建一个数据集的插件。
* 查看、修改、删除数据集的插件。
* 支持开发自己的数据插件，同时在数据集创建的时候进行使用。
* 创建一个评估的插件。
* 查看、修改、删除评估的插件。
* 支持开发自己的评估插件，同时在微调实验创建的时候进行使用。

**9. 更多(Coming Soon)️：**

***DTX*** 提供了一套全面的工具，确保您在微调过程中拥有灵活性和强大功能。根据您的特定需求去探索每个特征定制您的微调任务。

----
# 关键特点 ✨
**一站式自动化：**
全流程通过可视化管理界面的方式展示大模型微调中涉及到的数据管理、超参优化、微调任务、模型评估及推理验证。

**并行微调流水线：**
支持配置不同的数据集、参数组、基础大语言模型混合组合的方式构建大语言模型的微调流水线，并行执行微调实验并自动化评估微调效果。

**推理对比：**
支持基于微调出来的大语言模型部署推理服务，并对选择需要对比的推理服务使用相同的问题进行对比，以此来分析模型的表现。

**灵活可扩展：**
支持使用插件的方式扩展数据的处理能力，同时也支持使用插件的方式扩展评估的处理方式。

**分布式训练：**
提供灵活扩展的分布式训练能力，可以灵活应对单机单卡，单机多卡，多机多卡的模型微调。基于 Ray、KubeRay、DeepSpeed 等技术实现分布式训练/微调的能力。

**可扩展架构：**
使用云原生的技术，为大模型微调提供统一的、可弹性扩展的 GPU 能力和其它资源的能力。

**云原生能力：**
云原生方式构建了大模型的微调能力。标准、高效的算力资源调度和管理能力。

----

# 为什么选择 DTX？ 🤔

***DTX*** 成为优选的大型语言模型微调解决方案，具有以下突出优势，解决了自然语言处理中的关键挑战：

## 1. 优化资源利用 🚀
- **高效 GPU 集成:** 与分布式计算框架无缝集成，确保在资源受限环境中也能充分利用可扩展的 GPU 资源。

## 2. 流程化批量微调 🔄
- **并行任务执行:** 在批量微调方面表现突出，实现了在单个实验中并行执行多个任务。这提高了工作流效率和整体生产力。
<div align="center">
  <img src="https://raw.githubusercontent.com/DataTunerX/datatunerx-controller/main/assets/design/batchdark.png" alt="FineTuneExperiment" width="60%" />
</div>

## 3. 丰富的功能集满足多样化需求 🧰
- **多样化功能:** 从数据集管理到模型管理， ***DTX*** 提供了全面的功能集，满足各种微调需求。

## 4. 简化实验过程和低实验门槛 🧪
- **用户友好的实验:** 用户可以轻松进行不同模型、数据集和超参数的微调实验。这降低了不同技能水平用户的进入门槛。

总之， ***DTX*** 在资源优化、数据管理、工作流效率和可访问性方面都有针对性地解决了挑战，使其成为高效处理自然语言任务的理想解决方案。






