---
title: "Выводы"
description: "Модернизировать существующие приложения .NET с облако Azure и контейнеров Windows | выводы"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 0bcc330a5970ab923b48d8790c4de93171283d94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="conclusions"></a><span data-ttu-id="2e86a-103">Выводы</span><span class="sxs-lookup"><span data-stu-id="2e86a-103">Conclusions</span></span>

-   <span data-ttu-id="2e86a-104">Решения на основе контейнера в конечном счете обеспечивают сокращение экономии затрат.</span><span class="sxs-lookup"><span data-stu-id="2e86a-104">Container-based solutions ultimately provide cost savings benefits.</span></span> <span data-ttu-id="2e86a-105">Контейнеры являются решения проблем развертывания, так как они удаляют трения, причиной отсутствия зависимостей в производственных средах.</span><span class="sxs-lookup"><span data-stu-id="2e86a-105">Containers are a solution to deployment problems because they remove the friction caused by an absence of dependencies in production environments.</span></span> <span data-ttu-id="2e86a-106">При удалении таких проблем, его разработки и тестирования, DevOps и производственных операций значительно повышается.</span><span class="sxs-lookup"><span data-stu-id="2e86a-106">By removing those issues, it improves Dev/Test, DevOps and production operations significantly.</span></span>

-   <span data-ttu-id="2e86a-107">Контейнер Docker становится стандартной единицей развертывания для любого серверного приложения или службы.</span><span class="sxs-lookup"><span data-stu-id="2e86a-107">A Docker container is becoming the standard unit of deployment for any server-based application or service.</span></span>

-   <span data-ttu-id="2e86a-108">В рабочей среде следует использовать orchestrator (например, Service Fabric или Kubernetes) для размещения масштабируемых приложений на основе контейнеров Windows.</span><span class="sxs-lookup"><span data-stu-id="2e86a-108">For production environments, you should use an orchestrator (like Service Fabric or Kubernetes) to host scalable Windows Containers­­–based applications.</span></span>

-   <span data-ttu-id="2e86a-109">Размещение контейнеры виртуальных машинах Azure — это быстрый и простой способ создания небольших сред разработки и тестирования в облаке.</span><span class="sxs-lookup"><span data-stu-id="2e86a-109">Azure VMs hosting containers are a fast and simple way to create small Dev/Test environments in the cloud.</span></span>

-   <span data-ttu-id="2e86a-110">Экземпляр управляемого базы данных Azure SQL по умолчанию рекомендуется использовать при миграции реляционных базах данных с существующие приложения в Azure.</span><span class="sxs-lookup"><span data-stu-id="2e86a-110">Azure SQL Database Managed Instance is recommended by default when migrating your relational databases from existing applications to Azure.</span></span>

-   <span data-ttu-id="2e86a-111">Visual Studio 2017 г. и Image2Docker являются основные средства начать модернизация существующие приложения .NET с помощью контейнеров Windows по ускорению началу работы обучения.</span><span class="sxs-lookup"><span data-stu-id="2e86a-111">Visual Studio 2017 and Image2Docker are basic tools for you to start modernizing your existing .NET applications with Windows Containers by accelerating the getting started learning curve.</span></span>

-   <span data-ttu-id="2e86a-112">При размещении приложений в контейнерах в рабочей среде необходимо всегда создавать или внедрить средства DevOps для элемента конфигурации/CD конвейеров, например Visual Studio Team Services или Jenkins DevOps язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="2e86a-112">When placing containerized applications in production you will always create or adopt a DevOps culture and DevOps tools for CI/CD pipelines, like Visual Studio Team Services or Jenkins.</span></span>

-   <span data-ttu-id="2e86a-113">Microsoft Azure предоставляет наиболее полные и завершения среды модернизировать существующие приложения .NET Framework с контейнерами Windows, облачной инфраструктуры и служб PaaS.</span><span class="sxs-lookup"><span data-stu-id="2e86a-113">Microsoft Azure provides the most comprehensive and complete environment to modernize your existing .NET Framework applications with Windows Containers, cloud infrastructure and PaaS services.</span></span>

>[!div class="step-by-step"]
[<span data-ttu-id="2e86a-114">Назад</span><span class="sxs-lookup"><span data-stu-id="2e86a-114">Previous</span></span>](walkthroughs-technical-get-started-overview.md)