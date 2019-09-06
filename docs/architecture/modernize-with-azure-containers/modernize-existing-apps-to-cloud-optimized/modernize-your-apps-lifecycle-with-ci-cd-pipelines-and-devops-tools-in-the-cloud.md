---
title: Модернизация жизненного цикла приложений с помощью конвейеров непрерывной интеграции и непрерывного развертывания и средств DevOps в облаке
description: Модернизировать существующих приложений .NET с помощью Azure Cloud and Windows Containers | Модернизировать жизненный цикл приложения с помощью конвейеров CI/CD и средств DevOps в облаке
ms.date: 04/30/2018
ms.openlocfilehash: 62b6c541780ed3bf82c55e576fa485f811b55b17
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2019
ms.locfileid: "70374142"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="9959b-103">Модернизация жизненного цикла приложений с помощью конвейеров непрерывной интеграции и непрерывного развертывания и средств DevOps в облаке</span><span class="sxs-lookup"><span data-stu-id="9959b-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="9959b-104">Современные компании нуждаются в новшестве на быстром темпе, чтобы быть конкурентоспособным в Marketplace.</span><span class="sxs-lookup"><span data-stu-id="9959b-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="9959b-105">Для предоставления высококачественных современных приложений требуются средства и процессы DevOps, которые важны для реализации этого постоянного цикла инноваций.</span><span class="sxs-lookup"><span data-stu-id="9959b-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="9959b-106">С помощью правильных средств DevOps разработчики могут упростить непрерывное развертывание и быстро получать инновационные приложения в руки пользователей.</span><span class="sxs-lookup"><span data-stu-id="9959b-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="9959b-107">Несмотря на то что непрерывная интеграция и рекомендации по развертыванию хорошо установлены, введение контейнеров включает в себя новые соображения, особенно при работе с многоконтейнерными приложениями.</span><span class="sxs-lookup"><span data-stu-id="9959b-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="9959b-108">Azure DevOps Services поддерживает непрерывную интеграцию и развертывание приложений с несколькими контейнерами в различных средах с помощью официальных задач развертывания Azure DevOps Services.</span><span class="sxs-lookup"><span data-stu-id="9959b-108">Azure DevOps Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Azure DevOps Services deployment tasks:</span></span>

- [<span data-ttu-id="9959b-109">Развертывание в Веб-приложение для контейнеров Azure</span><span class="sxs-lookup"><span data-stu-id="9959b-109">Deploy to an Azure Web App for Containers</span></span>](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-docker-webapp?view=azure-devops)

- [<span data-ttu-id="9959b-110">Развертывание в службе контейнеров Azure — Kubernetes</span><span class="sxs-lookup"><span data-stu-id="9959b-110">Deploy to Azure Container Service – Kubernetes</span></span>](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

<span data-ttu-id="9959b-111">Но вы также можете выполнить развертывание в [DOCKER Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) или DC/OS с помощью Azure DevOps Services задач на основе сценариев.</span><span class="sxs-lookup"><span data-stu-id="9959b-111">But you also can deploy to [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) or DC/OS by using Azure DevOps Services script-based tasks.</span></span>

<span data-ttu-id="9959b-112">Чтобы продолжить обеспечение гибкости развертывания, эти средства предоставляют отличные возможности разработки и тестирования для рабочих нагрузок контейнеров, а также решения для разработки и непрерывной интеграции и компакт-дисков.</span><span class="sxs-lookup"><span data-stu-id="9959b-112">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="9959b-113">На рис. 4-12 показан конвейер непрерывного развертывания, который развертывается в кластере Kubernetes в службе контейнеров Azure.</span><span class="sxs-lookup"><span data-stu-id="9959b-113">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Azure DevOps Services конвейера непрерывного развертывания, развертывание в кластере Kubernetes](./media/image12.png)

<span data-ttu-id="9959b-115">**Рис. 4-12.**</span><span class="sxs-lookup"><span data-stu-id="9959b-115">**Figure 4-12.**</span></span> <span data-ttu-id="9959b-116">Azure DevOps Services конвейера непрерывного развертывания, развертывание в кластере Kubernetes</span><span class="sxs-lookup"><span data-stu-id="9959b-116">Azure DevOps Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9959b-117">[Назад](modernize-your-apps-with-monitoring-and-telemetry.md)
>[Вперед](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="9959b-117">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
