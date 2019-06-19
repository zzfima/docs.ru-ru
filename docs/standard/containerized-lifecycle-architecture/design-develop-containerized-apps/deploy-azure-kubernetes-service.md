---
title: Управление микрослужбами и многоконтейнерными приложениями для обеспечения высокого уровня масштабируемости и доступности
description: Сведения о развертывании приложения с помощью службы Azure Kubernetes.
ms.date: 02/15/2019
ms.openlocfilehash: 88e76b4b0a3686f4227a6aee1b7fbd2bfe55fdcc
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/13/2019
ms.locfileid: "65644665"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a>Развертывание в службе Azure Kubernetes (AKS)

Взаимодействовать со службой AKS можно с помощью предпочтительной клиентской операционной системы. В этой статье показано, как это можно делать с помощью Microsoft Windows и встроенной версии Ubuntu Linux в Windows с использованием команд Bash.

Предварительные требования для использования AKS:

- Компьютер разработки с Linux или Mac
- Компьютер разработки Windows
  - Включенный режим разработчика в Windows
  - Подсистема Windows для Linux
- Интерфейс Azure CLI, установленный в [Windows, Mac или Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)

> [!NOTE]
> На следующих страницах можно найти полную информацию об этих компонентах:
>
> Azure CLI: <https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest>
>
> Подсистема Windows для Linux: <https://docs.microsoft.com/windows/wsl/about>

## <a name="create-the-aks-environment-in-azure"></a>Создание среды AKS в Azure

Создать среду AKS можно несколькими способами. Это можно сделать с помощью команд Azure CLI или портала Azure.

Здесь можно ознакомиться с рядом примеров использования Azure CLI для создания кластера и просмотра результатов на портале Azure. На компьютере разработки также должны быть установлены Kubectl и Docker.  

## <a name="create-the-aks-cluster"></a>Создание кластера AKS

Создайте кластер AKS с помощью следующей команды:

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

Когда задание завершится, созданную службу AKS можно увидеть на портале Azure:

Группа ресурсов:

![Группа ресурсов Azure AKS в браузере.](media/aks-resource-group-view.png)

**Рис. 4-17**. Группа ресурсов AKS в Azure.

Кластер AKS:

![Группа ресурсов AKS в браузере.](media/aks-cluster-view.png)

**Рис. 4-18**. Служба AKS в Azure.

Созданный узел можно также просмотреть с помощью `Azure-CLI` и `Kubectl`.

Сначала получите учетные данные:

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![Выходные данные указанной выше команды в консоли: Произведено слияние MsSampleK8Cluster в качестве текущего контекста в /root/.kube/config.](media/get-credentials-command-result.png)

**Рис. 4-19**. Результат команды `aks get-credentials`.

Затем получите узлы из Kubectl:

```console
kubectl get nodes
```

![Выходные данные указанной выше команды в консоли: Список узлов с состоянием, возрастом (временем выполнения) и версией](media/kubectl-get-nodes-command-result.png)

**Рис. 4-20**. Результат команды `kubectl get nodes`.

>[!div class="step-by-step"]
>[Назад](orchestrate-high-scalability-availability.md)
>[Вперед](docker-apps-development-environment.md)
