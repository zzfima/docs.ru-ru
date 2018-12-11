---
title: Когда следует развертывать контейнеры Windows в службе контейнеров Azure (то есть Kubernetes)
description: Модернизация существующих приложений .NET с помощью облака Azure и Windows контейнерах | Когда следует развертывать контейнеры Windows в службе контейнеров Azure (то есть Kubernetes)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 0b803b104f905fddac7939d7b070c206aabffeda
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144797"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="1fe0b-103">Когда следует развертывать контейнеры Windows в службе контейнеров Azure (то есть Kubernetes)</span><span class="sxs-lookup"><span data-stu-id="1fe0b-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="1fe0b-104">Служба контейнеров Azure оптимизирует специально под Azure конфигурацию популярных средств с открытым исходным кодом и технологий.</span><span class="sxs-lookup"><span data-stu-id="1fe0b-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="1fe0b-105">Вы получаете открытое решение, которое обеспечивает переносимость как контейнеров, так и для конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="1fe0b-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="1fe0b-106">Выберите размер, количество узлов и средства управления.</span><span class="sxs-lookup"><span data-stu-id="1fe0b-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="1fe0b-107">Служба контейнеров Azure управляет инфраструктурой для вас.</span><span class="sxs-lookup"><span data-stu-id="1fe0b-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="1fe0b-108">Если вы уже работаете с открытым исходным кодом оркестраторы, например Kubernetes, Docker Swarm или DC/OS, не нужно изменять существующие методы управления для перемещения рабочих нагрузок контейнера в облако.</span><span class="sxs-lookup"><span data-stu-id="1fe0b-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="1fe0b-109">Используйте средства управления приложениями, которые вы уже знакомы с и подключение через стандартные конечные точки API для выбранного оркестратора.</span><span class="sxs-lookup"><span data-stu-id="1fe0b-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="1fe0b-110">Все эти оркестраторы, зрелой средах, если вы используете контейнеры Docker в Linux, но может быть только на этапе предварительной версии для контейнеров Windows.</span><span class="sxs-lookup"><span data-stu-id="1fe0b-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="1fe0b-111">Например, в Kubernetes, поддержка для контейнеров — машинный код (полноправным), поэтому использование контейнеров Windows на платформе Kubernetes может использоваться (в предварительной версии в ACS, по состоянию на начале 2018 года).</span><span class="sxs-lookup"><span data-stu-id="1fe0b-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="1fe0b-112">Важное примечание. Evolved и «дополнительные PaaS» версия ACS (службы контейнеров Azure) для Kubernetes — AKS (служба Azure Kubernetes), однако контейнеры Windows по-прежнему не поддерживаются Q2 2018 года, но скоро будет поддерживать.</span><span class="sxs-lookup"><span data-stu-id="1fe0b-112">Important note: The evolved and “more PaaS” version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1fe0b-113">[Назад](when-to-deploy-windows-containers-to-service-fabric.md)
>[Вперед](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="1fe0b-113">[Previous](when-to-deploy-windows-containers-to-service-fabric.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>