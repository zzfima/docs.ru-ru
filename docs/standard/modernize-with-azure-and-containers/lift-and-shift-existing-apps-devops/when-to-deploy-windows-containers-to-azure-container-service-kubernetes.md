---
title: "Если развернуть контейнеры Windows Azure контейнер службе (то есть, Kubernetes)"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Если развернуть контейнеры Windows Azure контейнер службе (то есть, Kubernetes)"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: f5ba7aa2cf14e7ca9f3a1f3eb12bbe236dca7e97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="73951-103">Если развернуть контейнеры Windows Azure контейнер службе (то есть, Kubernetes)</span><span class="sxs-lookup"><span data-stu-id="73951-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="73951-104">Служба Azure контейнера оптимизирует конфигурации популярных средств с открытым исходным кодом и технологии специально для Azure.</span><span class="sxs-lookup"><span data-stu-id="73951-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="73951-105">Вы получаете открытое решение, который обеспечивает совместимость для вашего контейнеров и конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="73951-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="73951-106">Выбрать размер, количество узлов и средств orchestrator.</span><span class="sxs-lookup"><span data-stu-id="73951-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="73951-107">Служба Azure контейнера обрабатывает инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="73951-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="73951-108">Если вы уже работаете с открытым исходным кодом orchestrators как Kubernetes помощью Docker Swarm и контроллера домена/OS, не нужно изменять существующие методик управления для перемещения рабочих нагрузок контейнера в облако.</span><span class="sxs-lookup"><span data-stu-id="73951-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="73951-109">Используйте средства управления приложения, вы уже знакомы с и подключения через стандартные конечные точки API для orchestrator по своему усмотрению.</span><span class="sxs-lookup"><span data-stu-id="73951-109">Use the application management tools that you're already familiar with, and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="73951-110">Эти orchestrators — зрелой среды при использовании контейнеров Linux Docker, но они также поддержка контейнеров Windows как части 2017 г. (некоторые более ранней версии, некоторые в последнее время в зависимости от orchestrator).</span><span class="sxs-lookup"><span data-stu-id="73951-110">All these orchestrators are mature environments if you are using Linux Docker containers, but they also support Windows Containers as of 2017 (some earlier, some more recently, depending on the orchestrator).</span></span>

<span data-ttu-id="73951-111">Например, в Kubernetes, поддержка контейнеров является машинный код (высокоприоритетным) с помощью контейнеров Windows на Kubernetes также очень эффективный и надежный (в режиме предварительного просмотра, пока не раньше попадают 2017 г.).</span><span class="sxs-lookup"><span data-stu-id="73951-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also very effective and reliable (in preview until early fall 2017).</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="73951-112">[Назад](when-to-deploy-windows-containers-to-service-fabric.md)
[Вперед](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="73951-112">[Previous](when-to-deploy-windows-containers-to-service-fabric.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
