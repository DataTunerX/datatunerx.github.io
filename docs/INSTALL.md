
# DataTunerX 全面部署指南

本指南提供了在在线和离线环境中部署 DataTunerX 的详细说明。在进行部署之前，请确保满足以下所有前提条件。

## 前提条件

开始之前，请确保您的系统符合以下要求：

- **Kubernetes v1.19+**: 容器编排系统，用于自动化软件部署、扩展和管理。
- **Minio** 或其他兼容 S3 的对象存储：用于存储大型数据集和模型。
- **Harbor**  或其他容器镜像注册表： 用于安全地存储和管理容器镜像。
- **Helm**:  Kubernetes 应用程序的包管理器，用于部署和管理应用程序。

## 部署工件

所需工件：

- `dtx-ctl` DataTunerX 部署工具。
- `images-ai.tar`: 可选的 llm 离线镜像包（图像大小为 47.1GB）。
- `images.tar`: 可选的业务组件离线镜像包。

## 在线部署

### 1. 下载 `dtx-ctl` 工具

```bash
wget https://github.com/DataTunerX/dtx-ctl/releases/download/v0.1.0/dtx-ctl.tar.gz
```

### 2. 部署 DataTunerX

使用默认设置部署：

```bash
dtx-ctl install
```

或者，使用自定义设置部署：


```bash
dtx-ctl install <name> -n <namespace> --set [Your-Custom-Settings]
```

或者，使用配置文件部署：


```bash
dtx-ctl install <name> -f /path/to/your/config.yaml
```

## 离线部署


按照在线部署步骤下载 `dtx-ctl` 工具和基础镜像。另外，按照以下步骤处理业务组件镜像：

### 1. 下载  `dtx-ctl` 工具

```bash
wget https://github.com/DataTunerX/dtx-ctl/releases/download/v0.1.0/dtx-ctl.tar.gz
```

### 2. 下载基础镜像

```bash
# Placeholder for the actual command to download the base AI images, currently the link is valid for 24 hours, if you need to apply for the download package please mention issuer
wget https://public-download.daocloud.io/datatunerx/v0.1.0/images?e=1708664238&token=MHV7x1flrG19kzrdBNfPPO7JpBjTr__AMGzOtlq1:sZrIxT02pubO4BhPunS3sky3Fss=
```

### 3. 下载基础 AI 镜像

```bash
# Placeholder for the actual command to download the base AI images, currently the link is valid for 24 hours, if you need to apply for the download package please mention issuer
wget https://public-download.daocloud.io/datatunerx/v0.1.0/images-ai?e=1708594433&token=MHV7x1flrG19kzrdBNfPPO7JpBjTr__AMGzOtlq1:DySesLobN0I7NeCBcYuZ74P8osA=
```

### 4. 解压并导入业务镜像包

```bash
tar -zxcf images.tar -C /path/to/unzip
cd /path/to/unzip/images
```

对于 Docker:

```bash
docker load -i /path/to/image.tar
```

对于 Containerd:

```bash
ctr -n k8s.io images import /path/to/image.tar
```

### 5. 修改镜像标签并推送到您的镜像仓库

```bash
docker tag source_image:tag target_repository/target_image:tag
docker push target_repository/target_image:tag
```

### 6. 部署 DataTunerX

使用自定义设置配置您的镜像仓库部署：

```bash
dtx-ctl install <name> -n <namespace> --registry=your_registry --repository=your_repository
```

或者，使用配置文件：


```bash
dtx-ctl install <name> -f /path/to/your/config.yaml
```

## 命令行命令列表

与 `dtx-ctl`交互的命令，包括安装和管理的标志和子命令：

```bash
# 一般用法
dtx-ctl [command]

# 可用命令
completion  为指定的 shell 生成自动完成脚本
help        获取有关任何命令的帮助
install     在 Kubernetes 上安装 DataTunerX
uninstall   从 Kubernetes 中卸载 DataTunerX

# 安装标志
--chart-directory string     Helm 图表目录
--dry-run                    模拟安装
--image-file-dir string      指定镜像文件目录
--image-pull-policy string   镜像拉取策略
--image-pull-secret string   镜像拉取密钥
--registry string            容器注册表
--repository string          容器仓库
--set stringArray            设置 Helm 值
--set-file stringArray       从文件设置 Helm 值
--set-string stringArray     设置 Helm 字符串值
-f, --values strings         在 YAML 文件中指定 Helm 值
--version string             图表版本
--wait                       等待安装完成
--wait-duration duration     最长等待资源准备就绪的时间
```

请根据需要替换占位符和实际值以及下载链接。





