---
title: Когда следует развертывать контейнеры Windows в службе контейнеров Azure (т. е. Kubernetes)
description: Модернизировать существующих приложений .NET с помощью Azure Cloud and Windows Containers | Когда следует развертывать контейнеры Windows в службе контейнеров Azure (т. е. Kubernetes)
ms.date: 04/30/2018
ms.openlocfilehash: 903082deba635dd0dfc22d0186fbc589f8d05b92
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577947"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="9ccc7-103">Когда следует развертывать контейнеры Windows в службе контейнеров Azure (т. е. Kubernetes)</span><span class="sxs-lookup"><span data-stu-id="9ccc7-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="9ccc7-104">Служба контейнеров Azure оптимизирует настройку популярных средств и технологий с открытым кодом специально для Azure.</span><span class="sxs-lookup"><span data-stu-id="9ccc7-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="9ccc7-105">Вы получаете открытое решение, которое обеспечивает переносимость как для контейнеров, так и для конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="9ccc7-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="9ccc7-106">Вы выбрали размер, число узлов и средства Orchestrator.</span><span class="sxs-lookup"><span data-stu-id="9ccc7-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="9ccc7-107">Служба контейнеров Azure обрабатывает инфраструктуру.</span><span class="sxs-lookup"><span data-stu-id="9ccc7-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="9ccc7-108">Если вы уже работаете с оркестрации с открытым кодом, например Kubernetes, Docker Swarm или DC/OS, вам не нужно изменять существующие методы управления для перемещения рабочих нагрузок контейнера в облако.</span><span class="sxs-lookup"><span data-stu-id="9ccc7-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="9ccc7-109">Используйте средства управления приложениями, с которыми вы уже знакомы, и подключитесь через стандартные конечные точки API для вашей программы Orchestrator по своему усмотрению.</span><span class="sxs-lookup"><span data-stu-id="9ccc7-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="9ccc7-110">Все эти оркестрации являются зрелыми средами, если вы используете контейнеры DOCKER для Linux, но они могут находиться только в состоянии предварительной версии для контейнеров Windows.</span><span class="sxs-lookup"><span data-stu-id="9ccc7-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="9ccc7-111">Например, в Kubernetes поддержка контейнеров является собственной (членом-членом первого класса), поэтому использование контейнеров Windows в Kubernetes также эффективно (в предварительной версии в ACS в начале 2018).</span><span class="sxs-lookup"><span data-stu-id="9ccc7-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="9ccc7-112">Важное замечание. Эволюция и более подробная версия службы ACS (служба контейнеров Azure) для Kubernetes — AKS (служба Azure Kubernetes), однако контейнеры Windows по-прежнему не поддерживаются в Q2 2018, но скоро они будут поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="9ccc7-112">Important note: The evolved and “more PaaS” version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9ccc7-113">[Назад](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[Вперед](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="9ccc7-113">[Previous](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>
