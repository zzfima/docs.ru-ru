---
title: Управление рабочими средами Docker
description: Сведения о ключевых аспектах управления рабочей средой на базе контейнеров.
ms.date: 02/15/2019
ms.openlocfilehash: 26e7a3319afe593d75e2384d023c901a389245dc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "71834507"
---
# <a name="manage-production-docker-environments"></a>Управление рабочими средами Docker

Управление кластером и оркестрация представляют собой процесс управления группой узлов. Это может включать в себя добавление и удаление узлов в кластере, получение сведений о текущем состоянии узлов и контейнеров, а также запуск и остановку процессов. Управление кластером и оркестрация тесно связаны с планированием, так как планировщику необходим доступ к каждому узлу в кластере, чтобы запланировать работу служб. Поэтому для обеих задач часто используется одно и то же средство.

## <a name="container-service-and-management-tools"></a>Служба контейнеров и средства управления

Служба контейнеров предусматривает быстрое развертывание популярных решений с открытым кодом для кластеризации и оркестрации контейнеров. Она использует образы Docker, чтобы гарантировать полную переносимость контейнеров приложений. Служба контейнеров позволяет развертывать кластеры DC/OS (основанные на Mesosphere и Apache Mesos) и Docker Swarm, используя шаблоны Azure Resource Manager или портал Azure, чтобы эти приложения можно было масштабировать до тысяч и даже десятков тысяч контейнеров.

Эти кластеры развертываются с помощью наборов масштабирования виртуальных машин Azure. Они также могут использовать возможности сети и хранилища Azure. Для доступа к службе контейнеров нужна подписка Azure. Служба контейнеров позволяет пользоваться функциями Azure корпоративного уровня, сохраняя при этом переносимость приложений, в том числе на уровнях оркестрации.

В таблице 6-1 перечислены стандартные инструменты управления, связанные с оркестраторами, планировщиками и платформой кластеризации.

**Таблица 6-1**. Средства управления Docker

| Средства управления | Описание: | Связанные оркестраторы |
|------------------|-------------|-----------------------|
| [Azure Monitor для контейнеров](https://docs.microsoft.com/azure/monitoring/monitoring-container-insights-overview) | Выделенное средство управления Kubernetes в Azure | Службы Azure Kubernetes (AKS) |
| [Пользовательский веб-интерфейс Kubernetes (панель мониторинга)](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) | Средство управления Kubernetes, позволяющее отслеживать локальный кластер Kubernetes и управлять им | Служба Azure Kubernetes (AKS)<br/>Локальные средства Kubernetes |
| [Портал Azure для Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal)<br/>[Azure Service Fabric Explorer](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) | Классическая и интернет-версия для управления кластерами Service Fabric в Azure, локальной среде, локальном развертывании и других облаках | Azure Service Fabric |
| [Мониторинг контейнеров (Azure Monitor)](https://docs.microsoft.com/azure/azure-monitor/insights/containers) | Решение для общего отслеживания контейнеров и управления ими. Позволяет управлять кластерами Kubernetes через [Azure Monitor для контейнеров](https://docs.microsoft.com/azure/monitoring/monitoring-container-insights-overview). | Azure Service Fabric<br/>Служба Azure Kubernetes (AKS)<br/>Mesosphere DC/OS и другие. |

## <a name="azure-service-fabric"></a>Azure Service Fabric

Другим вариантом для развертывания кластера и управления им является Azure Service Fabric. [Service Fabric](https://azure.microsoft.com/services/service-fabric/) — это платформа микрослужб Майкрософт, которая включает в себя оркестрацию контейнеров, а также модели программирования для разработчиков, позволяя создавать приложения микрослужб с высокой степенью масштабируемости. Service Fabric поддерживает Docker в контейнерах Windows и Linux и может работать на серверах Windows и Linux.

Ниже приведены средства управления Service Fabric:

- [Портал Azure для Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal) служит для выполнения операций с кластером (создание/изменение/удаление) или настройки его инфраструктуры (виртуальных машин, подсистемы балансировки нагрузки, сетевого взаимодействия и т. д.)

- [Azure Service Fabric Explorer](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) — это многоплатформенное средство, представленное классическим приложением и пользовательским веб-интерфейсом, которое предоставляет определенные ценные сведения о кластере Service Fabric и позволяет выполнять с ним определенные операции на уровне узлов и виртуальных машин, а также на уровне служб и приложений.

>[!div class="step-by-step"]
>[Назад](run-microservices-based-applications-in-production.md)
>[Вперед](monitor-containerized-application-services.md)
