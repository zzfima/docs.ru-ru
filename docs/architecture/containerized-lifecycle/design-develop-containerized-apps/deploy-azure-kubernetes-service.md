---
title: Управление микрослужбами и многоконтейнерными приложениями для обеспечения высокого уровня масштабируемости и доступности
description: Сведения о развертывании приложения с помощью службы Azure Kubernetes.
ms.date: 02/15/2019
ms.openlocfilehash: 0aa2f83fbf8f9a8815d65730002943cca748643d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "71182372"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a><span data-ttu-id="bdf2a-103">Развертывание в службе Azure Kubernetes (AKS)</span><span class="sxs-lookup"><span data-stu-id="bdf2a-103">Deploy to Azure Kubernetes Service (AKS)</span></span>

<span data-ttu-id="bdf2a-104">Взаимодействовать со службой AKS можно с помощью предпочтительной клиентской операционной системы. В этой статье показано, как это можно делать с помощью Microsoft Windows и встроенной версии Ubuntu Linux в Windows с использованием команд Bash.</span><span class="sxs-lookup"><span data-stu-id="bdf2a-104">You can interact with AKS using your preferred client operating system, here we show how to do it with Microsoft Windows and an embedded version of Ubuntu Linux in Windows, using Bash commands.</span></span>

<span data-ttu-id="bdf2a-105">Предварительные требования для использования AKS:</span><span class="sxs-lookup"><span data-stu-id="bdf2a-105">Prerequisites to have before using AKS are:</span></span>

- <span data-ttu-id="bdf2a-106">Компьютер разработки с Linux или Mac</span><span class="sxs-lookup"><span data-stu-id="bdf2a-106">Linux or Mac development machine</span></span>
- <span data-ttu-id="bdf2a-107">Компьютер разработки Windows</span><span class="sxs-lookup"><span data-stu-id="bdf2a-107">Windows development machine</span></span>
  - <span data-ttu-id="bdf2a-108">Включенный режим разработчика в Windows</span><span class="sxs-lookup"><span data-stu-id="bdf2a-108">Developer Mode enabled on Windows</span></span>
  - <span data-ttu-id="bdf2a-109">Подсистема Windows для Linux</span><span class="sxs-lookup"><span data-stu-id="bdf2a-109">Windows Subsystem for Linux</span></span>
- <span data-ttu-id="bdf2a-110">Интерфейс Azure CLI, установленный в [Windows, Mac или Linux](https://docs.microsoft.com/cli/azure/install-azure-cli)</span><span class="sxs-lookup"><span data-stu-id="bdf2a-110">Azure-CLI installed on [Windows, Mac or Linux](https://docs.microsoft.com/cli/azure/install-azure-cli)</span></span>

> [!NOTE]
> <span data-ttu-id="bdf2a-111">На следующих страницах можно найти полную информацию об этих компонентах:</span><span class="sxs-lookup"><span data-stu-id="bdf2a-111">To find complete information about:</span></span>
>
> <span data-ttu-id="bdf2a-112">Azure CLI: <https://docs.microsoft.com/cli/azure/index></span><span class="sxs-lookup"><span data-stu-id="bdf2a-112">Azure-CLI: <https://docs.microsoft.com/cli/azure/index></span></span>
>
> <span data-ttu-id="bdf2a-113">Подсистема Windows для Linux: <https://docs.microsoft.com/windows/wsl/about></span><span class="sxs-lookup"><span data-stu-id="bdf2a-113">Windows Subsystem for Linux: <https://docs.microsoft.com/windows/wsl/about></span></span>

## <a name="create-the-aks-environment-in-azure"></a><span data-ttu-id="bdf2a-114">Создание среды AKS в Azure</span><span class="sxs-lookup"><span data-stu-id="bdf2a-114">Create the AKS environment in Azure</span></span>

<span data-ttu-id="bdf2a-115">Создать среду AKS можно несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="bdf2a-115">There are several ways to create the AKS Environment.</span></span> <span data-ttu-id="bdf2a-116">Это можно сделать с помощью команд Azure CLI или портала Azure.</span><span class="sxs-lookup"><span data-stu-id="bdf2a-116">It can be done by using Azure-CLI commands or by using the Azure portal.</span></span>

<span data-ttu-id="bdf2a-117">Здесь можно ознакомиться с рядом примеров использования Azure CLI для создания кластера и просмотра результатов на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="bdf2a-117">Here you can explore some examples using the Azure-CLI to create the cluster and the Azure portal to review the results.</span></span> <span data-ttu-id="bdf2a-118">На компьютере разработки также должны быть установлены Kubectl и Docker.</span><span class="sxs-lookup"><span data-stu-id="bdf2a-118">You also need to have Kubectl and Docker in your development machine.</span></span>  

## <a name="create-the-aks-cluster"></a><span data-ttu-id="bdf2a-119">Создание кластера AKS</span><span class="sxs-lookup"><span data-stu-id="bdf2a-119">Create the AKS cluster</span></span>

<span data-ttu-id="bdf2a-120">Создайте кластер AKS с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="bdf2a-120">Create the AKS cluster using this command:</span></span>

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

<span data-ttu-id="bdf2a-121">Когда задание завершится, созданную службу AKS можно увидеть на портале Azure:</span><span class="sxs-lookup"><span data-stu-id="bdf2a-121">After the creation job finishes, you can see the AKS created in the Azure portal:</span></span>

<span data-ttu-id="bdf2a-122">Группа ресурсов:</span><span class="sxs-lookup"><span data-stu-id="bdf2a-122">The resource group:</span></span>

![Группа ресурсов Azure AKS в браузере.](media/aks-resource-group-view.png)

<span data-ttu-id="bdf2a-124">**Рис. 4-17**.</span><span class="sxs-lookup"><span data-stu-id="bdf2a-124">**Figure 4-17**.</span></span> <span data-ttu-id="bdf2a-125">Группа ресурсов AKS в Azure.</span><span class="sxs-lookup"><span data-stu-id="bdf2a-125">AKS Resource Group view from Azure.</span></span>

<span data-ttu-id="bdf2a-126">Кластер AKS:</span><span class="sxs-lookup"><span data-stu-id="bdf2a-126">The AKS cluster:</span></span>

![Группа ресурсов AKS в браузере.](media/aks-cluster-view.png)

<span data-ttu-id="bdf2a-128">**Рис. 4-18**.</span><span class="sxs-lookup"><span data-stu-id="bdf2a-128">**Figure 4-18**.</span></span> <span data-ttu-id="bdf2a-129">Служба AKS в Azure.</span><span class="sxs-lookup"><span data-stu-id="bdf2a-129">AKS view from Azure.</span></span>

<span data-ttu-id="bdf2a-130">Созданный узел можно также просмотреть с помощью `Azure-CLI` и `Kubectl`.</span><span class="sxs-lookup"><span data-stu-id="bdf2a-130">You can also view the node created using `Azure-CLI` and `Kubectl`.</span></span>

<span data-ttu-id="bdf2a-131">Сначала получите учетные данные:</span><span class="sxs-lookup"><span data-stu-id="bdf2a-131">First, getting the credentials:</span></span>

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![Выходные данные указанной выше команды в консоли: Произведено слияние MsSampleK8Cluster в качестве текущего контекста в /root/.kube/config.](media/get-credentials-command-result.png)

<span data-ttu-id="bdf2a-133">**Рис. 4-19**.</span><span class="sxs-lookup"><span data-stu-id="bdf2a-133">**Figure 4-19**.</span></span> <span data-ttu-id="bdf2a-134">Результат команды `aks get-credentials`.</span><span class="sxs-lookup"><span data-stu-id="bdf2a-134">`aks get-credentials` command result.</span></span>

<span data-ttu-id="bdf2a-135">Затем получите узлы из Kubectl:</span><span class="sxs-lookup"><span data-stu-id="bdf2a-135">And then, getting nodes from Kubectl:</span></span>

```console
kubectl get nodes
```

![Выходные данные указанной выше команды в консоли: Список узлов с состоянием, возрастом (временем выполнения) и версией](media/kubectl-get-nodes-command-result.png)

<span data-ttu-id="bdf2a-137">**Рис. 4-20**.</span><span class="sxs-lookup"><span data-stu-id="bdf2a-137">**Figure 4-20**.</span></span> <span data-ttu-id="bdf2a-138">Результат команды `kubectl get nodes`.</span><span class="sxs-lookup"><span data-stu-id="bdf2a-138">`kubectl get nodes` command result.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bdf2a-139">[Назад](orchestrate-high-scalability-availability.md)
>[Вперед](docker-apps-development-environment.md)</span><span class="sxs-lookup"><span data-stu-id="bdf2a-139">[Previous](orchestrate-high-scalability-availability.md)
[Next](docker-apps-development-environment.md)</span></span>
