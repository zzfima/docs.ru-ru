---
title: Модернизировать жизненного цикла приложения с помощью средств DevOps в облаке и конвейеры CI или компакт-диска
description: Модернизировать существующие приложения .NET с контейнерами Windows и облако Azure | Модернизировать жизненного цикла приложения с помощью средств DevOps в облаке и конвейеры CI или компакт-диска
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 63907a1911b4c95f0dbecb2af33964225cf3e7b1
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2018
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a>Модернизировать жизненного цикла приложения с помощью средств DevOps в облаке и конвейеры CI или компакт-диска

Современных предприятий должны инновации в быструю темпе, для повышения конкурентоспособности на рынке. Доставка высокого качества, современных приложений требуется DevOps средства и процессы, которые абсолютно необходимы для реализации этого цикла константой инноваций. Средства DevOps вправо разработчики могут упростить непрерывного развертывания и быстро инновационными приложениями в руки пользователей.

Несмотря на то, что непрерывной интеграции и развертывания и рекомендации, широко, введение контейнеров появился ряд особенностей, особенно в том случае, если вы работаете с несколькими контейнера приложений.

Visual Studio Team Services поддерживает непрерывной интеграции и развертывания контейнера для нескольких приложений для различных сред с помощью официальный задачи развертывания Team Services:

-   [Развертывание для автономной виртуальной Машины узла Docker](https://docs.microsoft.com/vsts/build-release/apps/cd/deploy-docker-windowsvm) (Linux или Windows Server 2016 или более поздней версии)

-   [Развертывание Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-tutorial-deploy-app-with-cicd-vsts)

-   [Развертывание службы контейнер Azure — Kubernetes](https://docs.microsoft.com/vsts/build-release/apps/cd/azure/deploy-container-kubernetes)

Но также можно развернуть на [помощью Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) или DC/OS с помощью задач на основе сценария Team Services.

Чтобы продолжить, проведению гибкость развертывания, эти средства предоставляют взаимодействие с отличным разработки к к тестовой развертывания для рабочих нагрузок контейнера, с выбором разработки и решениях CI/CD.

Рис. 4-12 показано конвейера непрерывного развертывания, который развертывает Kubernetes кластера в службе контейнера Azure.

![Конвейер непрерывного развертывания Visual Studio Team Services, развертывание в кластере Kubernetes](./media/image12.png)

> **Рис. 4-12.** Конвейер непрерывного развертывания Visual Studio Team Services, развертывание в кластере Kubernetes

>[!div class="step-by-step"]
[Назад](modernize-your-apps-with-monitoring-and-telemetry.md)
[Вперед](migrate-to-hybrid-cloud-scenarios.md)
