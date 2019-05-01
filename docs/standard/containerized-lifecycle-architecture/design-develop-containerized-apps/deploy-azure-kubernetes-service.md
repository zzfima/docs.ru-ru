---
title: Управление микрослужбами и многоконтейнерными приложениями для обеспечения высокого уровня масштабируемости и доступности
description: Сведения о развертывании приложения с помощью службы Azure Kubernetes.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 82a1cf7f3cc367bfb8b8f67a130600815f2a21c4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62006547"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a>Развертывание в службе Azure Kubernetes (AKS)

Вы можете взаимодействовать с AKS с помощью основной клиентской операционной системы, здесь мы покажем, как сделать это с помощью Microsoft Windows и встроенная версия Ubuntu Linux в Windows, с помощью команд Bash.

Перечислены предварительные условия, чтобы перед использованием AKS.

- Компьютер разработки Mac или Linux
- Компьютер разработки Windows
  - В Windows включен режим разработчика
  - Подсистема Windows для Linux
- Установлен на Azure-CLI [Windows, Mac или Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)

> [!NOTE]
> Чтобы найти подробные сведения о:
>
> Azure CLI: <https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest>
>
> Подсистема Windows для Linux: <https://docs.microsoft.com/windows/wsl/about>

## <a name="create-the-aks-environment-in-azure"></a>Создание среды AKS в Azure

Чтобы создать среду для AKS несколькими способами. Это можно сделать с помощью команд интерфейса командной строки Azure или с помощью портала Azure.

Здесь вы можете изучить некоторые примеры использования Azure CLI для создания кластера и на портале Azure, чтобы ознакомиться с результатами. Необходимо также иметь Kubectl и Docker на компьютере разработки.  

## <a name="create-the-aks-cluster"></a>Создание кластера AKS

Создайте кластер AKS с помощью следующей команды:

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

После завершения создания задания, вы увидите AKS, созданные на портале Azure.

Группа ресурсов:

![Представление группы ресурсов Azure AKS в браузере.](media/aks-resource-group-view.png)

**Рис. 4-17**. Представление группы ресурсов AKS из Azure.

Кластер AKS:

![Представление группы ресурсов AKS в браузере.](media/aks-cluster-view.png)

**Рис. 4-18**. Представление AKS из Azure.

Вы также можете просмотреть узел, созданных с помощью `Azure-CLI` и `Kubectl`.

Во-первых получение учетных данных:

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![Выходные данные этой команды консоли: Объединенный «MsSampleK8Cluster как текущий контекст в /root/.kube/config.](media/get-credentials-command-result.png)

**Рис. 4-19**. `aks get-credentials` результат команды.

Затем, эффективное использование Kubectl узлов:

```console
kubectl get nodes
```

![Выходные данные выше командной консоли: Список узлов с состоянием, возраст (времени выполнения) и версии](media/kubectl-get-nodes-command-result.png)

**Рис. 4-20**. `kubectl get nodes` результат команды.

>[!div class="step-by-step"]
>[Назад](orchestrate-high-scalability-availability.md)
>[Вперед](docker-apps-development-environment.md)
