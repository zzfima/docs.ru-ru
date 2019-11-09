---
title: Мониторинг в Службах Azure Kubernetes
description: Мониторинг в Службах Azure Kubernetes
ms.date: 09/23/2019
ms.openlocfilehash: 71192601eac2169db188b25da3dc91b71b860903
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2019
ms.locfileid: "73841129"
---
# <a name="monitoring-in-azure-kubernetes-services"></a>Мониторинг в Службах Azure Kubernetes

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Встроенным ведением журнала в Kubernetes является примитив. Однако существуют некоторые отличные варианты извлечения журналов из Kubernetes и в место, где их можно анализировать надлежащим образом. Если вам нужно отслеживать кластеры AKS, Настройка эластичного стека для Kubernetes является отличным решением.

## <a name="elastic-stack"></a>Эластичный стек

Эластичный стек — это мощный вариант для сбора информации из кластера Kubernetes. Kubernetes поддерживает отправку журналов в конечную точку Elasticsearch, и в [большинстве случаев](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/)все, что необходимо для начала работы, — задать переменные среды, как показано на рис. 7-5:

```kubernetes
KUBE_LOGGING_DESTINATION=elasticsearch
KUBE_ENABLE_NODE_LOGGING=true
```

**Рис. 7-5** . переменные конфигурации для Kubernetes

Это приведет к установке Elasticsearch в кластере и цели отправки всех журналов кластера на него.

![пример панели мониторинга Kibana, в которой показаны результаты запроса к журналам, полученным от Kubernetes](./media/kibana-dashboard.png)
**рис. 7-6**. Пример панели мониторинга Kibana, в которой показаны результаты запроса к журналам, принимаемым из Kubernetes

## <a name="azure-container-monitoring"></a>Мониторинг контейнеров Azure

Мониторинг контейнеров Azure поддерживает использование журналов не только Kubernetes, но и других механизмов оркестрации, таких как DC/OS, Docker Swarm и Red Hat OpenShift.

![использования журналов из различных контейнеров](./media/containers-diagram.png)
**рис. 7-7**.  Использование журналов из различных контейнеров

Сведения о журналах и метриках собираются не только из контейнеров, запущенных в кластере, но и с самих узлов кластера. Это позволяет сопоставлять данные журнала из двух способов, что значительно упрощает отслеживание ошибки.

Установка регистраторов различается в кластерах [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) и [Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) . Но в обоих случаях сбор журналов реализуется как набор [управляющих](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/)программ Kubernetes, что означает, что сборщик журналов выполняется как контейнер на каждом узле.

Независимо от того, в какой Orchestrator или операционной системе работает управляющая программа Azure Monitor, данные журнала перенаправляются в те же Azure Monitor средства, с которыми пользователи знакомы. Это обеспечивает параллельное взаимодействие в средах, в которых сочетаются различные источники журналов, такие как гибридная среда Kubernetes/функции Azure.

![пример панели мониторинга, в которой показаны данные журнала и метрики из нескольких работающих контейнеров.](./media/containers-dashboard.png)
**рис. 7-8**. Пример панели мониторинга, в которой показаны данные журнала и метрики из нескольких работающих контейнеров.

## <a name="logfinalize"></a>Log. Finalize ()

Ведение журнала является одним из наиболее подвернутых и, однако, наиболее важных частей развертывания любого приложения в масштабе. По мере увеличения размера и сложности приложений это усложняет их отладку. Наличие высококачественных журналов значительно упрощает отладку и перемещает их из области "почти невозможной" в "приятный".

>[!div class="step-by-step"]
>[Назад](logging-with-elastic-stack.md)
>[Вперед](azure-monitor.md)
