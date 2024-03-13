

![Kubernetes](https://img.shields.io/badge/kubernetes-%23326ce5.svg?style=flat&logo=kubernetes&logoColor=white)
![release](https://img.shields.io/badge/version-0.1.0-blue)
![fine-tuning](https://img.shields.io/badge/fine--tuning-8B3E3)
# Welcome 👋

***DataTunerX (DTX)*** is designed as a cloud-native solution integrated with distributed computing frameworks. Leveraging scalable *GPU* resources, it's a platform built for efficient fine-tuning *LLMs* with a focus on practical utility. Its core strength lies in facilitating batch fine-tuning tasks, enabling users to conduct multiple tasks concurrently within a single ***experiment***. ***DTX*** encompasses essential capabilities such as ***dataset management***, ***hyperparameter control***, ***fine-tuning workflows***, ***model management***, ***model evaluation***, ***model comparison inference***, and a ***modular plugin system***.

**Technology stack**: 

***DTX*** is built on cloud-native principles, employing a variety of [*Operators*](https://www.redhat.com/en/topics/containers/what-is-a-kubernetes-operator) that consist of distinct *Custom Resource Definitions (CRDs)* and *Controller* logic. Developed primarily in *Go*, the implementation utilizes the [*operator-sdk*](https://github.com/operator-framework/operator-sdk) toolkit. Operating within a [*Kubernetes (K8s)*](https://github.com/kubernetes/kubernetes) environment, ***DTX*** relies on the operator pattern for *CRD* development and management. Furthermore, ***DTX*** integrates with [*kuberay*](https://github.com/ray-project/kuberay) to harness distributed execution and inference capabilities.

**Status**:  

*v0.1.0* - Early development phase. [CHANGELOG](CHANGELOG.md) for details on recent updates.

**Quick Demo & More Documentation**:  

- Demo
<div align="center">
      <a href="https://www.youtube.com/watch?v=NvOzKj67oRQ">
         <img src="https://img.youtube.com/vi/NvOzKj67oRQ/maxresdefault.jpg" style="width:50%;">
      </a>
</div>

- [Documentation](https://github.com/DataTunerX/datatunerx-controller) (COMING SOON)

**Screenshot**:

![**DTX Screenshot**](https://raw.githubusercontent.com/DataTunerX/datatunerx-controller/main/assets/screenshot/Job_Details.png)

# What DTX can do? 💪

***DTX*** empowers users with a robust set of features designed for efficient fine-tuning of large language models. Dive into the capabilities that make ***DTX*** a versatile platform:

## 1. Dataset Management 🗄️
Effortlessly manage datasets by supporting both *S3* protocol (*http* is coming) and local dataset uploads. Datasets are organized with splits such as test, validation, and training. Additionally, feature mapping enhances flexibility for fine-tuning jobs.
<div align="center">
  <img src="https://raw.githubusercontent.com/DataTunerX/datatunerx-controller/main/assets/design/datasetplugindark.png" alt="FineTune" width="30%" height="30%" />
</div>

## 2. Fine-Tuning Experiments 🧪
Conduct fine-tuning experiments by creating multiple fine-tuning jobs. Each job can employ different llms, datasets, and hyperparameters. Evaluate the fine-tuned models uniformly through the experiment's evaluation unit to identify the fine-tuning results.
<div align="center">
  <img src="https://raw.githubusercontent.com/DataTunerX/datatunerx-controller/main/assets/design/finetunedark.png" alt="FineTune" width="30%" />
  <img src="https://raw.githubusercontent.com/DataTunerX/datatunerx-controller/main/assets/design/finetunejobdark.png" alt="FineTuneJob" width="30%" />
  <img src="https://raw.githubusercontent.com/DataTunerX/datatunerx-controller/main/assets/design/finetuneexdark.png" alt="FineTuneExperiment" width="30%" />
</div>

## 3. Job Insights 📊
Gain detailed insights into each fine-tuning job within an experiment. Explore job details, logs, and metric visualizations, including learning rate trends, training loss, and more.

## 4. Model Repository 🗃️
Store LLMs in the model repository, facilitating efficient management and deployment of inference services.
<div align="center">
  <img src="https://raw.githubusercontent.com/DataTunerX/datatunerx-controller/main/assets/design/evaldark.png" alt="FineTune" width="50%" height="70%" />
</div>

## 5. Hyperparameter Group Management 🧰
Utilize a rich parameter configuration system with support for diverse parameters and template-based differentiation.

## 6. Inference Services 🚀
Deploy inference services for multiple models simultaneously, enabling straightforward comparison and selection of the best-performing model.

## 7. Plugin System 🧩
Leverage the plugin system for datasets and evaluation units, allowing users to integrate specialized datasets and evaluation methods tailored to their unique requirements.

## 8. More Coming 🤹‍♀️
***DTX*** offers a comprehensive suite of tools, ensuring a seamless fine-tuning experience with flexibility and powerful functionality. Explore each feature to tailor your fine-tuning tasks according to your specific needs.

# Why DTX? 🤔

***DTX*** stands out as the preferred choice for fine-tuning large language models, offering distinct advantages that address critical challenges in natural language processing:

## 1. Optimized Resource Utilization 🚀
- **Efficient GPU Integration:** Seamlessly integrates with distributed computing frameworks, ensuring optimal utilization of scalable GPU resources, even in resource-constrained environments.

## 2. Streamlined Batch Fine-Tuning 🔄
- **Concurrent Task Execution:** Excels in batch fine-tuning, enabling concurrent execution of multiple tasks within a single experiment. This enhances workflow efficiency and overall productivity.
<div align="center">
  <img src="https://raw.githubusercontent.com/DataTunerX/datatunerx-controller/main/assets/design/batchdark.png" alt="FineTuneExperiment" width="60%" />
</div>

## 3. Robust Feature Set for Varied Needs 🧰
- **Diverse Capabilities:** From dataset management to model management, ***DTX*** provides a comprehensive feature set catering to diverse fine-tuning requirements.

## 4. Simplified Experimentation with Lower Entry Barriers 🧪
- **User-Friendly Experimentation:** Empowers users to effortlessly conduct fine-tuning experiments with varying models, datasets, and hyperparameters. This lowers the entry barriers for users with varying skill levels.

In summary, ***DTX*** strategically addresses challenges in resource optimization, data management, workflow efficiency, and accessibility, making it an ideal solution for efficient natural language processing tasks.

# Architecture 🏛️

Introducing the architectural design provides an overview of how DataTunerX is structured. This includes details on key components, their interactions, and how they contribute to the system's functionality.

# Installation 📦

Detailed instructions on how to install, configure, and run the project are available in the [*INSTALL*](INSTALL.md) document.

# Usage 🖥️

Provide clear instructions on how to use the software, including code snippets where appropriate. (COMING SOON)

# Known issues 🚨

Document any known significant shortcomings with the software.

# Getting help ❓

If you have questions, concerns, or bug reports, please file an issue in this repository's [*Issue Tracker*](https://github.com/DataTunerX/datatunerx-controller/issues).

# Getting involved 🤝

We welcome contributions! Check out our [*CONTRIBUTING*](CONTRIBUTING.md) guidelines to get started. Share your feedback, report bugs, or contribute to ongoing discussions.

----

# Credits and References 🙌

1. **Kubernetes (k8s):** 
   - [*Kubernetes*](https://kubernetes.io/): An open-source container orchestration platform for automating the deployment, scaling, and management of containerized applications.

2. **Ray:**
   - [*Ray Project*](https://ray.io/): An open-source distributed computing framework that makes it easy to scale and parallelize applications.

3. **KubeRay:**
   - [*KubeRay*](https://github.com/kuberay/kuberay): An integration of Ray with Kubernetes, enabling efficient distributed computing on Kubernetes clusters.

4. **Operator SDK:**
   - [*Operator SDK*](https://sdk.operatorframework.io/): A toolkit for building Kubernetes Operators, which are applications that automate the management of custom resources in a Kubernetes cluster.

5. **LLaMA-Factory:**
   - [*LLaMA-Factory*](https://github.com/hiyouga/LLaMA-Factory): An easy-to-use llm fine-tuning framework.

Feel free to explore these projects to deepen your understanding of the technologies and concepts that may have influenced or inspired this project.
