---
title: Действия в рабочем процессе внешнего цикла DevOps для приложения Docker
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 2cd769ce9013a8521c53f36b44ea260ceccd48b7
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2019
ms.locfileid: "56834970"
---
# <a name="creating-cicd-pipelines-in-azure-devops-services-for-a-net-core-20-application-on-containers-and-deploying-to-a-kubernetes-cluster"></a><span data-ttu-id="3bb26-103">Создание конвейеров CI/CD в службах Azure DevOps для приложения .NET Core 2.0 для контейнеров и развертывание в кластер Kubernetes</span><span class="sxs-lookup"><span data-stu-id="3bb26-103">Creating CI/CD pipelines in Azure DevOps Services for a .NET Core 2.0 application on Containers and deploying to a Kubernetes cluster</span></span>

<span data-ttu-id="3bb26-104">На рисунке 5-12 показано сценарии DevOps end-to-end, охватывающий управления кода, компиляции кода, сборки образов Docker, отправьте образы Docker в реестр Docker и, наконец, развертывание в кластер Kubernetes в Azure.</span><span class="sxs-lookup"><span data-stu-id="3bb26-104">In Figure 5-12 you can see the end-to-end DevOps scenario covering the code management, code compilation, Docker images build, Docker images push to a Docker registry and finally the deployment to a Kubernetes cluster in Azure.</span></span>

![Рабочий процесс: Запускает на компьютере разработки.](media/docker-workflow-ci-cd-aks.png)

<span data-ttu-id="3bb26-107">**Рис. 5-12**.</span><span class="sxs-lookup"><span data-stu-id="3bb26-107">**Figure 5-12**.</span></span> <span data-ttu-id="3bb26-108">Сценарии Непрерывной интеграции и создание образов Docker, а также развертывание в кластер Kubernetes в Azure</span><span class="sxs-lookup"><span data-stu-id="3bb26-108">CI/CD scenario creating Docker images and deploying to a Kubernetes cluster in Azure</span></span>

<span data-ttu-id="3bb26-109">Это важно обратить внимание, что два конвейера, сборки/непрерывной Интеграции и выпуска и непрерывной Доставки, подключены через реестр Docker (Docker Hub или реестра контейнеров Azure).</span><span class="sxs-lookup"><span data-stu-id="3bb26-109">It is important to highlight that the two pipelines, build/CI, and release/CD, are connected through the Docker Registry (such as Docker Hub or Azure Container Registry).</span></span> <span data-ttu-id="3bb26-110">Реестр Docker является одним из основных различий по сравнению с традиционной процесс Непрерывной интеграции и без Docker.</span><span class="sxs-lookup"><span data-stu-id="3bb26-110">The Docker registry is one of the main differences compared to a traditional CI/CD process without Docker.</span></span>

<span data-ttu-id="3bb26-111">Как показано на рисунке 5-13, первый этап заключается в конвейер сборки и CI.</span><span class="sxs-lookup"><span data-stu-id="3bb26-111">As shown in Figure 5-13, the first phase is the build/CI pipeline.</span></span> <span data-ttu-id="3bb26-112">В службах DevOps Azure можно создать конвейеры Непрерывной сборки, на которые будет скомпилировать код, создание образов Docker и отправки их в реестр Docker, например Docker Hub или реестра контейнеров Azure.</span><span class="sxs-lookup"><span data-stu-id="3bb26-112">In Azure DevOps Services you can create build/CD pipelines that will compile the code, create the Docker images, and push them to a Docker Registry like Docker Hub or Azure Container Registry.</span></span>

![Представление обозревателя Azure DevOps, определение задач процесса сборки.](media/build-ci-pipeline-azure-devops-push-to-docker-registry.png)

<span data-ttu-id="3bb26-114">**Рис. 5-13**.</span><span class="sxs-lookup"><span data-stu-id="3bb26-114">**Figure 5-13**.</span></span> <span data-ttu-id="3bb26-115">Конвейер сборки/непрерывной Интеграции в Azure DevOps, создание образов Docker и отправке образов в реестр Docker</span><span class="sxs-lookup"><span data-stu-id="3bb26-115">Build/CI pipeline in Azure DevOps building Docker images and pushing images to a Docker registry</span></span>

<span data-ttu-id="3bb26-116">Второй этап заключается в создании конвейера развертывания или выпуска.</span><span class="sxs-lookup"><span data-stu-id="3bb26-116">The second phase is to create a deployment/release pipeline.</span></span> <span data-ttu-id="3bb26-117">В службах Azure DevOps можно легко создать конвейер развертывания, предназначенные для кластера Kubernetes с помощью задач Kubernetes для служб Azure DevOps, как показано на рисунке 5-14.</span><span class="sxs-lookup"><span data-stu-id="3bb26-117">In Azure DevOps Services, you can easily create a deployment pipeline targeting a Kubernetes cluster by using the Kubernetes tasks for Azure DevOps Services, as shown in Figure 5-14.</span></span>

![Представление обозревателя Azure DevOps, развертывание в Kubernetes определение задачи.](media/release-cd-pipeline-azure-devops-deploy-to-kubernetes.png)

<span data-ttu-id="3bb26-119">**Рис. 5-14**.</span><span class="sxs-lookup"><span data-stu-id="3bb26-119">**Figure 5-14**.</span></span> <span data-ttu-id="3bb26-120">Конвейер выпуска и непрерывного Развертывания в развертывание служб Azure DevOps в кластере Kubernetes</span><span class="sxs-lookup"><span data-stu-id="3bb26-120">Release/CD pipeline in Azure DevOps Services deploying to a Kubernetes cluster</span></span>

> [! Пошаговое руководство]<span data-ttu-id="3bb26-121"> развертывание eShopModernized Kubernetes:</span><span class="sxs-lookup"><span data-stu-id="3bb26-121"> Deploying eShopModernized to Kubernetes:</span></span>
>
> <span data-ttu-id="3bb26-122">Подробное пошаговое руководство конвейеров Azure DevOps Непрерывной интеграции и развертывания в Kubernetes, см. запись блога: \\</span><span class="sxs-lookup"><span data-stu-id="3bb26-122">For a detailed walkthrough of Azure DevOps CI/CD pipelines deploying to Kubernetes, see this post: \\</span></span>
><https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

>[!div class="step-by-step"]
><span data-ttu-id="3bb26-123">[Назад](docker-application-outer-loop-devops-workflow.md)
>[Вперед](../run-manage-monitor-docker-environments/index.md)</span><span class="sxs-lookup"><span data-stu-id="3bb26-123">[Previous](docker-application-outer-loop-devops-workflow.md)
[Next](../run-manage-monitor-docker-environments/index.md)</span></span>
