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
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="2675c-103">Модернизация жизненного цикла приложений с помощью конвейеров непрерывной Интеграции и Развертывания и инструменты DevOps в облаке</span><span class="sxs-lookup"><span data-stu-id="2675c-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="2675c-104">Современные компании требуется для внедрения инноваций в быстром темпе для повышения конкурентоспособности на рынке.</span><span class="sxs-lookup"><span data-stu-id="2675c-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="2675c-105">Чтобы обеспечить высокое качество, современных приложений требуются инструментов и процессов, которые абсолютно необходимы для реализации этого цикла константы инноваций DevOps.</span><span class="sxs-lookup"><span data-stu-id="2675c-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="2675c-106">Используя соответствующие инструменты DevOps разработчики могут упростить непрерывного развертывания и быстро инновационных приложений в руки пользователей.</span><span class="sxs-lookup"><span data-stu-id="2675c-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="2675c-107">Несмотря на то, что широко применяются для непрерывной интеграции и использования опыта развертывания, появлением контейнеры вводит новые вопросы, особенно в том случае, если вы работаете с несколькими контейнерами приложений.</span><span class="sxs-lookup"><span data-stu-id="2675c-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="2675c-108">Службы Azure DevOps поддерживают непрерывную интеграцию и развертывание многоконтейнерных приложений для широкого спектра сред с помощью официальной задачи развертывания служб Azure DevOps:</span><span class="sxs-lookup"><span data-stu-id="2675c-108">Azure DevOps Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Azure DevOps Services deployment tasks:</span></span>

-   <span data-ttu-id="2675c-109">[Развертывание автономных виртуальных Машин узла Docker](https://docs.microsoft.com/azure/devops/build-release/apps/cd/deploy-docker-windowsvm) (Linux или Windows Server 2016 или более поздней версии)</span><span class="sxs-lookup"><span data-stu-id="2675c-109">[Deploy to standalone Docker Host VM](https://docs.microsoft.com/azure/devops/build-release/apps/cd/deploy-docker-windowsvm) (Linux or Windows Server 2016 or later)</span></span>

-   [<span data-ttu-id="2675c-110">Развертывание в Service Fabric</span><span class="sxs-lookup"><span data-stu-id="2675c-110">Deploy to Service Fabric</span></span>](https://docs.microsoft.com/azure/service-fabric/service-fabric-tutorial-deploy-app-with-cicd-vsts)

-   [<span data-ttu-id="2675c-111">Развертывание в службе контейнеров Azure — Kubernetes</span><span class="sxs-lookup"><span data-stu-id="2675c-111">Deploy to Azure Container Service – Kubernetes</span></span>](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

<span data-ttu-id="2675c-112">Но вы также можете развернуть [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) или DC/OS с помощью служб Azure DevOps на основе сценария задач.</span><span class="sxs-lookup"><span data-stu-id="2675c-112">But you also can deploy to [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) or DC/OS by using Azure DevOps Services script-based tasks.</span></span>

<span data-ttu-id="2675c-113">Чтобы продолжить, облегчая гибкость развертывания, эти средства предоставляют прекрасный dev к теста — в рабочей среде развертывания, взаимодействие для рабочих нагрузок контейнера, благодаря чему разработки и непрерывной Интеграции и Развертывания решений.</span><span class="sxs-lookup"><span data-stu-id="2675c-113">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="2675c-114">Рис. 4-12 показано конвейер непрерывного развертывания, который развертывает кластер Kubernetes в службе контейнеров Azure.</span><span class="sxs-lookup"><span data-stu-id="2675c-114">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Azure конвейере непрерывного развертывания службы DevOps, развертывание в кластер Kubernetes](./media/image12.png)

> <span data-ttu-id="2675c-116">**Рис. 4-12.**</span><span class="sxs-lookup"><span data-stu-id="2675c-116">**Figure 4-12.**</span></span> <span data-ttu-id="2675c-117">Azure конвейере непрерывного развертывания службы DevOps, развертывание в кластер Kubernetes</span><span class="sxs-lookup"><span data-stu-id="2675c-117">Azure DevOps Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="2675c-118">[Назад](modernize-your-apps-with-monitoring-and-telemetry.md)
[Вперед](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="2675c-118">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
