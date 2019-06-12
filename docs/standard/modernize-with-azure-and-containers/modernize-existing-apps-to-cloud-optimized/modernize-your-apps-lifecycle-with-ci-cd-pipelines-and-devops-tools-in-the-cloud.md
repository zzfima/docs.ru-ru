---
title: Модернизация жизненного цикла приложений с помощью конвейеров непрерывной интеграции и непрерывного развертывания и средств DevOps в облаке
description: Модернизация существующих приложений .NET с помощью облака Azure и Windows контейнерах | Модернизация жизненного цикла приложений с помощью конвейеров непрерывной Интеграции и Развертывания и инструменты DevOps в облаке
ms.date: 04/30/2018
ms.openlocfilehash: fb4bfab4a891e9c8a73867f18cb8249775f9b7b9
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833956"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="88c28-103">Модернизация жизненного цикла приложений с помощью конвейеров непрерывной интеграции и непрерывного развертывания и средств DevOps в облаке</span><span class="sxs-lookup"><span data-stu-id="88c28-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="88c28-104">Современные компании требуется для внедрения инноваций в быстром темпе для повышения конкурентоспособности на рынке.</span><span class="sxs-lookup"><span data-stu-id="88c28-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="88c28-105">Чтобы обеспечить высокое качество, современных приложений требуются инструментов и процессов, которые абсолютно необходимы для реализации этого цикла константы инноваций DevOps.</span><span class="sxs-lookup"><span data-stu-id="88c28-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="88c28-106">Используя соответствующие инструменты DevOps разработчики могут упростить непрерывного развертывания и быстро инновационных приложений в руки пользователей.</span><span class="sxs-lookup"><span data-stu-id="88c28-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="88c28-107">Несмотря на то, что широко применяются для непрерывной интеграции и использования опыта развертывания, появлением контейнеры вводит новые вопросы, особенно в том случае, если вы работаете с несколькими контейнерами приложений.</span><span class="sxs-lookup"><span data-stu-id="88c28-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="88c28-108">Службы Azure DevOps поддерживают непрерывную интеграцию и развертывание многоконтейнерных приложений для широкого спектра сред с помощью официальной задачи развертывания служб Azure DevOps:</span><span class="sxs-lookup"><span data-stu-id="88c28-108">Azure DevOps Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Azure DevOps Services deployment tasks:</span></span>

- [<span data-ttu-id="88c28-109">Развертывание в веб-приложение Azure для контейнеров</span><span class="sxs-lookup"><span data-stu-id="88c28-109">Deploy to an Azure Web App for Containers</span></span>](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-docker-webapp?view=azure-devops)

- [<span data-ttu-id="88c28-110">Развертывание в службе контейнеров Azure — Kubernetes</span><span class="sxs-lookup"><span data-stu-id="88c28-110">Deploy to Azure Container Service – Kubernetes</span></span>](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

<span data-ttu-id="88c28-111">Но вы также можете развернуть [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) или DC/OS с помощью служб Azure DevOps на основе сценария задач.</span><span class="sxs-lookup"><span data-stu-id="88c28-111">But you also can deploy to [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) or DC/OS by using Azure DevOps Services script-based tasks.</span></span>

<span data-ttu-id="88c28-112">Чтобы продолжить, облегчая гибкость развертывания, эти средства предоставляют прекрасный dev к теста — в рабочей среде развертывания, взаимодействие для рабочих нагрузок контейнера, благодаря чему разработки и непрерывной Интеграции и Развертывания решений.</span><span class="sxs-lookup"><span data-stu-id="88c28-112">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="88c28-113">Рис. 4-12 показано конвейер непрерывного развертывания, который развертывает кластер Kubernetes в службе контейнеров Azure.</span><span class="sxs-lookup"><span data-stu-id="88c28-113">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Azure конвейере непрерывного развертывания службы DevOps, развертывание в кластер Kubernetes](./media/image12.png)

> <span data-ttu-id="88c28-115">**Рис. 4-12.**</span><span class="sxs-lookup"><span data-stu-id="88c28-115">**Figure 4-12.**</span></span> <span data-ttu-id="88c28-116">Azure конвейере непрерывного развертывания службы DevOps, развертывание в кластер Kubernetes</span><span class="sxs-lookup"><span data-stu-id="88c28-116">Azure DevOps Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="88c28-117">[Назад](modernize-your-apps-with-monitoring-and-telemetry.md)
>[Вперед](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="88c28-117">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
