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
# <a name="monitoring-in-azure-kubernetes-services"></a><span data-ttu-id="4b4e5-103">Мониторинг в Службах Azure Kubernetes</span><span class="sxs-lookup"><span data-stu-id="4b4e5-103">Monitoring in Azure Kubernetes Services</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="4b4e5-104">Встроенным ведением журнала в Kubernetes является примитив.</span><span class="sxs-lookup"><span data-stu-id="4b4e5-104">The built-in logging in Kubernetes is primitive.</span></span> <span data-ttu-id="4b4e5-105">Однако существуют некоторые отличные варианты извлечения журналов из Kubernetes и в место, где их можно анализировать надлежащим образом.</span><span class="sxs-lookup"><span data-stu-id="4b4e5-105">However, there are some great options for getting the logs out of Kubernetes and into a place where they can be properly analyzed.</span></span> <span data-ttu-id="4b4e5-106">Если вам нужно отслеживать кластеры AKS, Настройка эластичного стека для Kubernetes является отличным решением.</span><span class="sxs-lookup"><span data-stu-id="4b4e5-106">If you need to monitor your AKS clusters, configuring Elastic Stack for Kubernetes is a great solution.</span></span>

## <a name="elastic-stack"></a><span data-ttu-id="4b4e5-107">Эластичный стек</span><span class="sxs-lookup"><span data-stu-id="4b4e5-107">Elastic Stack</span></span>

<span data-ttu-id="4b4e5-108">Эластичный стек — это мощный вариант для сбора информации из кластера Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="4b4e5-108">The Elastic Stack is a powerful option for gathering information from a Kubernetes cluster.</span></span> <span data-ttu-id="4b4e5-109">Kubernetes поддерживает отправку журналов в конечную точку Elasticsearch, и в [большинстве случаев](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/)все, что необходимо для начала работы, — задать переменные среды, как показано на рис. 7-5:</span><span class="sxs-lookup"><span data-stu-id="4b4e5-109">Kubernetes supports sending logs to an Elasticsearch endpoint, and for the [most part](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/), all you need to get started is to set the environment variables as shown in Figure 7-5:</span></span>

```kubernetes
KUBE_LOGGING_DESTINATION=elasticsearch
KUBE_ENABLE_NODE_LOGGING=true
```

<span data-ttu-id="4b4e5-110">**Рис. 7-5** . переменные конфигурации для Kubernetes</span><span class="sxs-lookup"><span data-stu-id="4b4e5-110">**Figure 7-5** - Configuration variables for Kubernetes</span></span>

<span data-ttu-id="4b4e5-111">Это приведет к установке Elasticsearch в кластере и цели отправки всех журналов кластера на него.</span><span class="sxs-lookup"><span data-stu-id="4b4e5-111">This will install Elasticsearch on the cluster and target sending all the cluster logs to it.</span></span>

<span data-ttu-id="4b4e5-112">![пример панели мониторинга Kibana, в которой показаны результаты запроса к журналам, полученным от Kubernetes](./media/kibana-dashboard.png)
**рис. 7-6**.</span><span class="sxs-lookup"><span data-stu-id="4b4e5-112">![An example of a Kibana dashboard showing the results of a query against logs ingested from Kubernetes](./media/kibana-dashboard.png)
**Figure 7-6**.</span></span> <span data-ttu-id="4b4e5-113">Пример панели мониторинга Kibana, в которой показаны результаты запроса к журналам, принимаемым из Kubernetes</span><span class="sxs-lookup"><span data-stu-id="4b4e5-113">An example of a Kibana dashboard showing the results of a query against logs that are ingested from Kubernetes</span></span>

## <a name="azure-container-monitoring"></a><span data-ttu-id="4b4e5-114">Мониторинг контейнеров Azure</span><span class="sxs-lookup"><span data-stu-id="4b4e5-114">Azure Container Monitoring</span></span>

<span data-ttu-id="4b4e5-115">Мониторинг контейнеров Azure поддерживает использование журналов не только Kubernetes, но и других механизмов оркестрации, таких как DC/OS, Docker Swarm и Red Hat OpenShift.</span><span class="sxs-lookup"><span data-stu-id="4b4e5-115">Azure Container Monitoring supports consuming logs from not just Kubernetes but also from other orchestration engines such as DC/OS, Docker Swarm, and Red Hat OpenShift.</span></span>

<span data-ttu-id="4b4e5-116">![использования журналов из различных контейнеров](./media/containers-diagram.png)
**рис. 7-7**.</span><span class="sxs-lookup"><span data-stu-id="4b4e5-116">![Consuming logs from various containers](./media/containers-diagram.png)
**Figure 7-7**.</span></span>  <span data-ttu-id="4b4e5-117">Использование журналов из различных контейнеров</span><span class="sxs-lookup"><span data-stu-id="4b4e5-117">Consuming logs from various containers</span></span>

<span data-ttu-id="4b4e5-118">Сведения о журналах и метриках собираются не только из контейнеров, запущенных в кластере, но и с самих узлов кластера.</span><span class="sxs-lookup"><span data-stu-id="4b4e5-118">Log and metric information is gathered not just from the containers running in the cluster but also from the cluster hosts themselves.</span></span> <span data-ttu-id="4b4e5-119">Это позволяет сопоставлять данные журнала из двух способов, что значительно упрощает отслеживание ошибки.</span><span class="sxs-lookup"><span data-stu-id="4b4e5-119">It allows correlating log information from the two making it much easier to track down an error.</span></span>

<span data-ttu-id="4b4e5-120">Установка регистраторов различается в кластерах [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) и [Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) .</span><span class="sxs-lookup"><span data-stu-id="4b4e5-120">Installing the log collectors differs on [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) and [Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) clusters.</span></span> <span data-ttu-id="4b4e5-121">Но в обоих случаях сбор журналов реализуется как набор [управляющих](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/)программ Kubernetes, что означает, что сборщик журналов выполняется как контейнер на каждом узле.</span><span class="sxs-lookup"><span data-stu-id="4b4e5-121">But in both cases the log collection is implemented as a Kubernetes [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/), meaning that the log collector is run as a container on each of the nodes.</span></span>

<span data-ttu-id="4b4e5-122">Независимо от того, в какой Orchestrator или операционной системе работает управляющая программа Azure Monitor, данные журнала перенаправляются в те же Azure Monitor средства, с которыми пользователи знакомы.</span><span class="sxs-lookup"><span data-stu-id="4b4e5-122">No matter which orchestrator or operating system is running the Azure Monitor daemon, the log information is forwarded to the same Azure Monitor tools with which users are familiar.</span></span> <span data-ttu-id="4b4e5-123">Это обеспечивает параллельное взаимодействие в средах, в которых сочетаются различные источники журналов, такие как гибридная среда Kubernetes/функции Azure.</span><span class="sxs-lookup"><span data-stu-id="4b4e5-123">This ensures a parallel experience in environments that mix different log sources such as a hybrid Kubernetes/Azure Functions environment.</span></span>

<span data-ttu-id="4b4e5-124">![пример панели мониторинга, в которой показаны данные журнала и метрики из нескольких работающих контейнеров.](./media/containers-dashboard.png)
**рис. 7-8**.</span><span class="sxs-lookup"><span data-stu-id="4b4e5-124">![A sample dashboard showing logging and metric information from a number of running containers.](./media/containers-dashboard.png)
**Figure 7-8**.</span></span> <span data-ttu-id="4b4e5-125">Пример панели мониторинга, в которой показаны данные журнала и метрики из нескольких работающих контейнеров.</span><span class="sxs-lookup"><span data-stu-id="4b4e5-125">A sample dashboard showing logging and metric information from a number of running containers.</span></span>

## <a name="logfinalize"></a><span data-ttu-id="4b4e5-126">Log. Finalize ()</span><span class="sxs-lookup"><span data-stu-id="4b4e5-126">Log.Finalize()</span></span>

<span data-ttu-id="4b4e5-127">Ведение журнала является одним из наиболее подвернутых и, однако, наиболее важных частей развертывания любого приложения в масштабе.</span><span class="sxs-lookup"><span data-stu-id="4b4e5-127">Logging is one of the most overlooked and yet most important parts of deploying any application at scale.</span></span> <span data-ttu-id="4b4e5-128">По мере увеличения размера и сложности приложений это усложняет их отладку.</span><span class="sxs-lookup"><span data-stu-id="4b4e5-128">As the size and complexity of applications increase, then so does the difficulty of debugging them.</span></span> <span data-ttu-id="4b4e5-129">Наличие высококачественных журналов значительно упрощает отладку и перемещает их из области "почти невозможной" в "приятный".</span><span class="sxs-lookup"><span data-stu-id="4b4e5-129">Having top quality logs available makes debugging much easier and moves it from the realm of "nearly impossible" to "a pleasant experience".</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4b4e5-130">[Назад](logging-with-elastic-stack.md)
>[Вперед](azure-monitor.md)</span><span class="sxs-lookup"><span data-stu-id="4b4e5-130">[Previous](logging-with-elastic-stack.md)
[Next](azure-monitor.md)</span></span>
