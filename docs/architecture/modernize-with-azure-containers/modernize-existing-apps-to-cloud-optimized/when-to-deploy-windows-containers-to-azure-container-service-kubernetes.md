---
title: Когда следует развертывать контейнеры Windows в Службе контейнеров Azure (то есть, Kubernetes)
description: Модернизация существующих приложений .NET с помощью облака Azure и контейнеров Windows | Когда следует развертывать контейнеры Windows в службе контейнеров Azure (то есть, Kubernetes)
ms.date: 04/30/2018
ms.openlocfilehash: 903082deba635dd0dfc22d0186fbc589f8d05b92
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2019
ms.locfileid: "69577947"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="fcabc-103">Когда следует развертывать контейнеры Windows в Службе контейнеров Azure (то есть, Kubernetes)</span><span class="sxs-lookup"><span data-stu-id="fcabc-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="fcabc-104">Служба контейнеров Azure оптимизирует настройку популярных средств и технологий с открытым кодом для Azure.</span><span class="sxs-lookup"><span data-stu-id="fcabc-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="fcabc-105">Вы получаете открытое решение, которое обеспечивает переносимость как контейнеров, так и конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="fcabc-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="fcabc-106">Вы выбираете размер, число узлов и средства оркестрации.</span><span class="sxs-lookup"><span data-stu-id="fcabc-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="fcabc-107">Служба контейнеров Azure выполняет настройку инфраструктуры за вас.</span><span class="sxs-lookup"><span data-stu-id="fcabc-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="fcabc-108">Если вы уже работаете с оркестраторами с открытым кодом, например, Kubernetes, Docker Swarm или DC/OS, вам не нужно изменять существующие методы управления для перемещения рабочих нагрузок контейнера в облако.</span><span class="sxs-lookup"><span data-stu-id="fcabc-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="fcabc-109">Работайте с уже знакомыми средствами управления и подключайтесь к нужному вам оркестратору через стандартные конечные точки API.</span><span class="sxs-lookup"><span data-stu-id="fcabc-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="fcabc-110">Все эти оркестраторы являются зрелыми средами, если вы используете контейнеры Docker в Linux, но они могут находиться только в состоянии предварительной версии для контейнеров Windows.</span><span class="sxs-lookup"><span data-stu-id="fcabc-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="fcabc-111">Например, в Kubernetes поддержка контейнеров является встроенной (первоклассной), поэтому использование контейнеров Windows в Kubernetes также эффективно (в предварительной версии в ACS по состоянию на начало 2018 г.).</span><span class="sxs-lookup"><span data-stu-id="fcabc-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="fcabc-112">Важное примечание. Усовершенствованной и более PaaS-ориентированной версией службы ACS (Службы контейнеров Azure) для Kubernetes является AKS (Служба Azure Kubernetes), однако контейнеры Windows по-прежнему не поддерживаются по состоянию на второй квартал 2018 года, но скоро будут поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="fcabc-112">Important note: The evolved and “more PaaS” version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="fcabc-113">[Назад](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[Вперед](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="fcabc-113">[Previous](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>
