---
title: Общие принципы проектирования контейнера
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6a289cdafc88abe8629638a84eff184829362e16
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="common-container-design-principles"></a><span data-ttu-id="bbbe8-103">Общие принципы проектирования контейнера</span><span class="sxs-lookup"><span data-stu-id="bbbe8-103">Common container design principles</span></span>

<span data-ttu-id="bbbe8-104">Заранее получения в процесс разработки существует несколько основных понятий упомянуть относительно использования контейнеров.</span><span class="sxs-lookup"><span data-stu-id="bbbe8-104">Ahead of getting into the development process there are a few basic concepts worth mentioning with regard to how you use containers.</span></span>

## <a name="container-equals-a-process"></a><span data-ttu-id="bbbe8-105">Контейнер равно процесса</span><span class="sxs-lookup"><span data-stu-id="bbbe8-105">Container equals a process</span></span>

<span data-ttu-id="bbbe8-106">В модели контейнера контейнер представляет один процесс.</span><span class="sxs-lookup"><span data-stu-id="bbbe8-106">In the container model, a container represents a single process.</span></span> <span data-ttu-id="bbbe8-107">Определение контейнера как границ процессов, можно начать создавать примитивы, используемые для масштабирования, или пакетное off, процессы.</span><span class="sxs-lookup"><span data-stu-id="bbbe8-107">By defining a container as a process boundary, you begin to create the primitives used to scale, or batch-off, processes.</span></span> <span data-ttu-id="bbbe8-108">При запуске контейнера Docker, вы увидите [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) определения.</span><span class="sxs-lookup"><span data-stu-id="bbbe8-108">When you run a Docker container, you'll see an [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) definition.</span></span> <span data-ttu-id="bbbe8-109">Этот параметр определяет процесс и временем существования контейнера.</span><span class="sxs-lookup"><span data-stu-id="bbbe8-109">This defines the process and the lifetime of the container.</span></span> <span data-ttu-id="bbbe8-110">По окончании процесса завершает жизненный цикл контейнера.</span><span class="sxs-lookup"><span data-stu-id="bbbe8-110">When the process completes, the container life cycle ends.</span></span> <span data-ttu-id="bbbe8-111">Существуют долго выполняющихся процессов, таких как веб-серверы и уничтожению короткоживущих процессов, таких как пакетного задания, которые могут реализована в виде Microsoft Azure [веб-задания](https://azure.microsoft.com/en-us/documentation/articles/websites-webjobs-resources/).</span><span class="sxs-lookup"><span data-stu-id="bbbe8-111">There are long-running processes, such as web servers, and short-lived processes, such as batch jobs, which might have been implemented as Microsoft Azure [WebJobs](https://azure.microsoft.com/en-us/documentation/articles/websites-webjobs-resources/).</span></span> <span data-ttu-id="bbbe8-112">В случае сбоя процесса работа контейнера завершается и оркестратор принимает управление.</span><span class="sxs-lookup"><span data-stu-id="bbbe8-112">If the process fails, the container ends, and the orchestrator takes over.</span></span> <span data-ttu-id="bbbe8-113">Orchestrator было предложено сохранить пяти экземпляров, работающих в случае возникновения одной ошибки orchestrator создаст другой контейнер для замены сбой процесса.</span><span class="sxs-lookup"><span data-stu-id="bbbe8-113">If the orchestrator was instructed to keep five instances running and one fails, the orchestrator will create another container to replace the failed process.</span></span> <span data-ttu-id="bbbe8-114">В пакетном задании процесс запускается с параметрами.</span><span class="sxs-lookup"><span data-stu-id="bbbe8-114">In a batch job, the process is started with parameters.</span></span> <span data-ttu-id="bbbe8-115">По завершении выполнения процесса работа считается выполненной.</span><span class="sxs-lookup"><span data-stu-id="bbbe8-115">When the process completes, the work is complete.</span></span>

<span data-ttu-id="bbbe8-116">Может оказаться сценария, в которой требуется несколько процессов, запущенных в одном контейнере.</span><span class="sxs-lookup"><span data-stu-id="bbbe8-116">You might find a scenario in which you want multiple processes running in a single container.</span></span> <span data-ttu-id="bbbe8-117">В любом документе архитектура никогда нет «никогда» всегда отсутствует значение «всегда».</span><span class="sxs-lookup"><span data-stu-id="bbbe8-117">In any architecture document, there's never a "never," nor is there always an "always."</span></span> <span data-ttu-id="bbbe8-118">Общий шаблон для сценариев, требующих несколько процессов, является использование [администратора](http://supervisord.org/).</span><span class="sxs-lookup"><span data-stu-id="bbbe8-118">For scenarios requiring multiple processes, a common pattern is to use [Supervisor](http://supervisord.org/).</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="bbbe8-119">[Предыдущие] (конструктора docker-applications.md) [Далее] (монолитные applications.md)</span><span class="sxs-lookup"><span data-stu-id="bbbe8-119">[Previous] (design-docker-applications.md) [Next] (monolithic-applications.md)</span></span>
