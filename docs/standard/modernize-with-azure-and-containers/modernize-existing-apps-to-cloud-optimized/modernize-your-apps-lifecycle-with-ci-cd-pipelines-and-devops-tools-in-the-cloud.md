---
title: Модернизация жизненного цикла приложений с помощью конвейеров непрерывной Интеграции и Развертывания и инструменты DevOps в облаке
description: Модернизация существующих приложений .NET с помощью облака Azure и Windows контейнерах | Модернизация жизненного цикла приложений с помощью конвейеров непрерывной Интеграции и Развертывания и инструменты DevOps в облаке
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: c4d3eaa50f6c7645c954ca65bf42c6c1eab3a68d
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "46532055"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a>Модернизация жизненного цикла приложений с помощью конвейеров непрерывной Интеграции и Развертывания и инструменты DevOps в облаке

Современные компании требуется для внедрения инноваций в быстром темпе для повышения конкурентоспособности на рынке. Чтобы обеспечить высокое качество, современных приложений требуются инструментов и процессов, которые абсолютно необходимы для реализации этого цикла константы инноваций DevOps. Используя соответствующие инструменты DevOps разработчики могут упростить непрерывного развертывания и быстро инновационных приложений в руки пользователей.

Несмотря на то, что широко применяются для непрерывной интеграции и использования опыта развертывания, появлением контейнеры вводит новые вопросы, особенно в том случае, если вы работаете с несколькими контейнерами приложений.

Службы Azure DevOps поддерживают непрерывную интеграцию и развертывание многоконтейнерных приложений для широкого спектра сред с помощью официальной задачи развертывания служб Azure DevOps:

-   [Развертывание автономных виртуальных Машин узла Docker](https://docs.microsoft.com/azure/devops/build-release/apps/cd/deploy-docker-windowsvm) (Linux или Windows Server 2016 или более поздней версии)

-   [Развертывание в Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-tutorial-deploy-app-with-cicd-vsts)

-   [Развертывание в службе контейнеров Azure — Kubernetes](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

Но вы также можете развернуть [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) или DC/OS с помощью служб Azure DevOps на основе сценария задач.

Чтобы продолжить, облегчая гибкость развертывания, эти средства предоставляют прекрасный dev к теста — в рабочей среде развертывания, взаимодействие для рабочих нагрузок контейнера, благодаря чему разработки и непрерывной Интеграции и Развертывания решений.

Рис. 4-12 показано конвейер непрерывного развертывания, который развертывает кластер Kubernetes в службе контейнеров Azure.

![Azure конвейере непрерывного развертывания службы DevOps, развертывание в кластер Kubernetes](./media/image12.png)

> **Рис. 4-12.** Azure конвейере непрерывного развертывания службы DevOps, развертывание в кластер Kubernetes

>[!div class="step-by-step"]
[Назад](modernize-your-apps-with-monitoring-and-telemetry.md)
[Вперед](migrate-to-hybrid-cloud-scenarios.md)
