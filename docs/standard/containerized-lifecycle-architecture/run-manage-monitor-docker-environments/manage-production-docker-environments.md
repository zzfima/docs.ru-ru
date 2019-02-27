---
title: Управление рабочими средами Docker
description: Узнайте о ключевые аспекты управления на базе контейнеров рабочей среде.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: f3cf9bc281e94f342cecb1083d886daba03c019d
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2019
ms.locfileid: "56836621"
---
# <a name="manage-production-docker-environments"></a>Управление рабочими средами Docker

Управление кластером и оркестрация — это процесс управления группой узлов. Для этого может потребоваться добавление и удаление узлов из кластера, получение сведений о текущем состоянии узлов и контейнеров и запуск и остановка процессов. Управление кластером и оркестрация тесно связаны с планированием, так как планировщик необходимо иметь доступ к каждому узлу в кластере Чтобы запланировать служб. По этой причине для обоих целей часто используется тот же инструмент.

## <a name="container-service-and-management-tools"></a>Контейнер службы и средства управления

Служба контейнеров предоставляет быстрое развертывание решения кластеризации и оркестрации популярный контейнер открытым исходным кодом. Чтобы убедиться, что контейнеры приложений можно полностью перенести в нем образов Docker. С помощью службы контейнеров, можно развернуть (на платформе, Mesosphere и Apache Mesos) DC/OS и Docker Swarm кластеров под управлением Windows с помощью шаблонов Azure Resource Manager или портала Azure, чтобы убедиться, что можно масштабировать эти приложения до тысяч — даже десятков тысяч — из контейнеры.

Эти кластеры развертываются с помощью масштабируемых наборов виртуальных машин Azure и кластеров воспользоваться предложениями сети и хранилища Azure. Для доступа к службе контейнеров, требуется подписка Azure. Со службой контейнеров можно воспользоваться преимуществами функций корпоративного уровня Azure сохраняя при этом переносимость приложений, в том числе на уровнях оркестрации.

В таблице 6-1 перечислены стандартные инструменты управления, относящиеся к их оркестраторы, планировщики и кластеризации платформы.

**В таблице 6-1**. Средства управления docker

| Средства управления | Описание: | Связанные оркестраторов |
|------------------|-------------|-----------------------|
| [Azure Monitor для контейнеров](https://docs.microsoft.com/azure/monitoring/monitoring-container-insights-overview) | Azure уровня dedicated средство управления Kubernetes | Службы Azure Kubernetes (AKS) |
| [Веб-интерфейса Kubernetes (панель мониторинга)](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) | Средства управления Kubernetes, можно отслеживать и управлять локального кластера Kubernetes | Служба Azure Kubernetes (AKS)<br/>Локальный Kubernetes |
| [Портал Azure для Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal)<br/>[Azure Service Fabric Explorer](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) | Версия Online и рабочего стола для кластеров Service Fabric в Azure, локально, локальной разработки, а также других облаках | Azure Service Fabric |
| [Контейнер мониторинга (Log Analytics)](https://docs.microsoft.com/azure/azure-monitor/insights/containers) | Y управления общие контейнера решение для мониторинга. Позволяет управлять кластерами Kubernetes через [Azure Monitor для контейнеров](https://docs.microsoft.com/azure/monitoring/monitoring-container-insights-overview). | Azure Service Fabric<br/>Служба Azure Kubernetes (AKS)<br/>Mesosphere DC/OS и другим пользователям. |

## <a name="azure-service-fabric"></a>Azure Service Fabric

Другим вариантом для управления и развертывания кластера является Azure Service Fabric. [Service Fabric](https://azure.microsoft.com/services/service-fabric/) — платформа Майкрософт включает в себя оркестрации контейнера, а также разработчиков программирования модели для создания приложений с высокой степенью масштабируемости микрослужбы. Service Fabric поддерживает Docker в Linux и контейнеров Windows и может работать в серверах Windows и Linux.

Ниже приведены средства управления Service Fabric:

- [Портал Azure для Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal) операции, относящиеся к кластеру (создания/обновления/удаления) кластера или настроить его инфраструктурой (виртуальными машинами, подсистемы балансировки нагрузки, сети и т. д.)

- [Azure Service Fabric Explorer](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) является специализированным веб-интерфейса и рабочего стола нескольких платформ, позволяющим insights и определенных операций в кластере Service Fabric, с точки зрения узлы или виртуальные машины и службы приложений и с точки зрения.

>[!div class="step-by-step"]
>[Назад](run-microservices-based-applications-in-production.md)
>[Вперед](monitor-containerized-application-services.md)
