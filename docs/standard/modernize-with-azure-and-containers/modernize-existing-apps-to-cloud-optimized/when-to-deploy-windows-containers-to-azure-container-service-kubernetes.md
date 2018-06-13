---
title: Если развернуть контейнеры Windows Azure контейнер службе (то есть, Kubernetes)
description: Модернизировать существующие приложения .NET с контейнерами Windows и облако Azure | Если развернуть контейнеры Windows Azure контейнер службе (то есть, Kubernetes)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: b7f106e2b79a2c6bb24733debf7f4828505d66a6
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2018
ms.locfileid: "33958174"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="e65d8-103">Если развернуть контейнеры Windows Azure контейнер службе (то есть, Kubernetes)</span><span class="sxs-lookup"><span data-stu-id="e65d8-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="e65d8-104">Служба Azure контейнера оптимизирует конфигурации популярных средств с открытым исходным кодом и технологии специально для Azure.</span><span class="sxs-lookup"><span data-stu-id="e65d8-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="e65d8-105">Вы получаете открытое решение, который обеспечивает совместимость для вашего контейнеров и конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="e65d8-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="e65d8-106">Выбрать размер, количество узлов и средств orchestrator.</span><span class="sxs-lookup"><span data-stu-id="e65d8-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="e65d8-107">Служба Azure контейнера обрабатывает инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="e65d8-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="e65d8-108">Если вы уже работаете с открытым исходным кодом orchestrators как Kubernetes помощью Docker Swarm и контроллера домена/OS, не нужно изменять существующие методик управления для перемещения рабочих нагрузок контейнера в облако.</span><span class="sxs-lookup"><span data-stu-id="e65d8-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="e65d8-109">Используйте средства управления приложения, которые вы уже знакомы с и подключения через стандартные конечные точки API для orchestrator по своему усмотрению.</span><span class="sxs-lookup"><span data-stu-id="e65d8-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="e65d8-110">Эти orchestrators — зрелой среды, если вы используете контейнеры Linux Docker, но может быть только в состоянии предварительной версии для контейнеров Windows.</span><span class="sxs-lookup"><span data-stu-id="e65d8-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="e65d8-111">Например, в Kubernetes, поддержку контейнеры с помощью контейнеров Windows на Kubernetes машинный код (высокоприоритетным) может использоваться (в предварительной версии в ACS, начиная с ранним 2018).</span><span class="sxs-lookup"><span data-stu-id="e65d8-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="e65d8-112">Важное замечание: доработанной и «дополнительные PaaS» версия ACS (контейнера службы Azure) для Kubernetes — AKS (Kubernetes службы Azure), однако контейнеры Windows по-прежнему не поддерживаются начиная с Q2 2018, но скоро будет поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="e65d8-112">Important note: The evolved and “more PaaS” version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="e65d8-113">[Назад](when-to-deploy-windows-containers-to-service-fabric.md)
[Вперед](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="e65d8-113">[Previous](when-to-deploy-windows-containers-to-service-fabric.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>
