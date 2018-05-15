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
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="760bb-103">Модернизировать жизненного цикла приложения с помощью средств DevOps в облаке и конвейеры CI или компакт-диска</span><span class="sxs-lookup"><span data-stu-id="760bb-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="760bb-104">Современных предприятий должны инновации в быструю темпе, для повышения конкурентоспособности на рынке.</span><span class="sxs-lookup"><span data-stu-id="760bb-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="760bb-105">Доставка высокого качества, современных приложений требуется DevOps средства и процессы, которые абсолютно необходимы для реализации этого цикла константой инноваций.</span><span class="sxs-lookup"><span data-stu-id="760bb-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="760bb-106">Средства DevOps вправо разработчики могут упростить непрерывного развертывания и быстро инновационными приложениями в руки пользователей.</span><span class="sxs-lookup"><span data-stu-id="760bb-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="760bb-107">Несмотря на то, что непрерывной интеграции и развертывания и рекомендации, широко, введение контейнеров появился ряд особенностей, особенно в том случае, если вы работаете с несколькими контейнера приложений.</span><span class="sxs-lookup"><span data-stu-id="760bb-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="760bb-108">Visual Studio Team Services поддерживает непрерывной интеграции и развертывания контейнера для нескольких приложений для различных сред с помощью официальный задачи развертывания Team Services:</span><span class="sxs-lookup"><span data-stu-id="760bb-108">Visual Studio Team Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Team Services deployment tasks:</span></span>

-   <span data-ttu-id="760bb-109">[Развертывание для автономной виртуальной Машины узла Docker](https://docs.microsoft.com/vsts/build-release/apps/cd/deploy-docker-windowsvm) (Linux или Windows Server 2016 или более поздней версии)</span><span class="sxs-lookup"><span data-stu-id="760bb-109">[Deploy to standalone Docker Host VM](https://docs.microsoft.com/vsts/build-release/apps/cd/deploy-docker-windowsvm) (Linux or Windows Server 2016 or later)</span></span>

-   [<span data-ttu-id="760bb-110">Развертывание Service Fabric</span><span class="sxs-lookup"><span data-stu-id="760bb-110">Deploy to Service Fabric</span></span>](https://docs.microsoft.com/azure/service-fabric/service-fabric-tutorial-deploy-app-with-cicd-vsts)

-   [<span data-ttu-id="760bb-111">Развертывание службы контейнер Azure — Kubernetes</span><span class="sxs-lookup"><span data-stu-id="760bb-111">Deploy to Azure Container Service – Kubernetes</span></span>](https://docs.microsoft.com/vsts/build-release/apps/cd/azure/deploy-container-kubernetes)

<span data-ttu-id="760bb-112">Но также можно развернуть на [помощью Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) или DC/OS с помощью задач на основе сценария Team Services.</span><span class="sxs-lookup"><span data-stu-id="760bb-112">But you also can deploy to [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) or DC/OS by using Team Services script-based tasks.</span></span>

<span data-ttu-id="760bb-113">Чтобы продолжить, проведению гибкость развертывания, эти средства предоставляют взаимодействие с отличным разработки к к тестовой развертывания для рабочих нагрузок контейнера, с выбором разработки и решениях CI/CD.</span><span class="sxs-lookup"><span data-stu-id="760bb-113">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="760bb-114">Рис. 4-12 показано конвейера непрерывного развертывания, который развертывает Kubernetes кластера в службе контейнера Azure.</span><span class="sxs-lookup"><span data-stu-id="760bb-114">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Конвейер непрерывного развертывания Visual Studio Team Services, развертывание в кластере Kubernetes](./media/image12.png)

> <span data-ttu-id="760bb-116">**Рис. 4-12.**</span><span class="sxs-lookup"><span data-stu-id="760bb-116">**Figure 4-12.**</span></span> <span data-ttu-id="760bb-117">Конвейер непрерывного развертывания Visual Studio Team Services, развертывание в кластере Kubernetes</span><span class="sxs-lookup"><span data-stu-id="760bb-117">Visual Studio Team Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="760bb-118">[Назад](modernize-your-apps-with-monitoring-and-telemetry.md)
[Вперед](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="760bb-118">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
