---
title: "Выводы"
description: "Модернизировать существующие приложения .NET с облако Azure и контейнеров Windows | выводы"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9ab627793ac45510aba6ce76fdb87834b02e55f8
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2018
---
# <a name="conclusions"></a><span data-ttu-id="30137-103">Выводы</span><span class="sxs-lookup"><span data-stu-id="30137-103">Conclusions</span></span>

- <span data-ttu-id="30137-104">Решения на основе контейнера в конечном счете обеспечивают сокращение экономии затрат.</span><span class="sxs-lookup"><span data-stu-id="30137-104">Container-based solutions ultimately provide cost savings benefits.</span></span> <span data-ttu-id="30137-105">Контейнеры являются решения проблем развертывания, так как они удаляют трения, причиной отсутствия зависимостей в производственных средах.</span><span class="sxs-lookup"><span data-stu-id="30137-105">Containers are a solution to deployment problems because they remove the friction caused by an absence of dependencies in production environments.</span></span> <span data-ttu-id="30137-106">При удалении таких проблем, его разработки и тестирования, DevOps и производственных операций значительно повышается.</span><span class="sxs-lookup"><span data-stu-id="30137-106">By removing those issues, it improves Dev/Test, DevOps, and production operations significantly.</span></span>

- <span data-ttu-id="30137-107">Контейнер Docker превращается в стандартную единицу развертывания любого серверного приложения или службы.</span><span class="sxs-lookup"><span data-stu-id="30137-107">A Docker container is becoming the standard unit of deployment for any server-based application or service.</span></span>

- <span data-ttu-id="30137-108">В рабочей среде следует использовать orchestrator (например, Service Fabric или Kubernetes) для размещения масштабируемых приложений на основе контейнеров Windows.</span><span class="sxs-lookup"><span data-stu-id="30137-108">For production environments, you should use an orchestrator (like Service Fabric or Kubernetes) to host scalable Windows Containers­­–based applications.</span></span>

- <span data-ttu-id="30137-109">Размещение контейнеры виртуальных машинах Azure — это быстрый и простой способ создания небольших сред разработки и тестирования в облаке.</span><span class="sxs-lookup"><span data-stu-id="30137-109">Azure VMs hosting containers are a fast and simple way to create small Dev/Test environments in the cloud.</span></span>

- <span data-ttu-id="30137-110">Экземпляр управляемого базы данных Azure SQL по умолчанию рекомендуется использовать при миграции реляционных базах данных с существующие приложения в Azure.</span><span class="sxs-lookup"><span data-stu-id="30137-110">Azure SQL Database Managed Instance is recommended by default when migrating your relational databases from existing applications to Azure.</span></span>

- <span data-ttu-id="30137-111">Visual Studio 2017 г. и Image2Docker являются основные средства начать модернизация существующие приложения .NET с помощью контейнеров Windows по ускорению началу работы обучения.</span><span class="sxs-lookup"><span data-stu-id="30137-111">Visual Studio 2017 and Image2Docker are basic tools for you to start modernizing your existing .NET applications with Windows Containers by accelerating the getting started learning curve.</span></span>

- <span data-ttu-id="30137-112">При размещении приложений в контейнерах в рабочей среде необходимо всегда создавать или внедрить средства DevOps для элемента конфигурации/CD конвейеров, например Visual Studio Team Services или Jenkins DevOps язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="30137-112">When placing containerized applications in production you will always create or adopt a DevOps culture and DevOps tools for CI/CD pipelines, like Visual Studio Team Services or Jenkins.</span></span>

- <span data-ttu-id="30137-113">Microsoft Azure предоставляет наиболее полные и завершения среды модернизировать существующие приложения .NET Framework с контейнерами Windows, облачной инфраструктуры и служб PaaS.</span><span class="sxs-lookup"><span data-stu-id="30137-113">Microsoft Azure provides the most comprehensive and complete environment to modernize your existing .NET Framework applications with Windows Containers, cloud infrastructure and PaaS services.</span></span>

>[!div class="step-by-step"]
[<span data-ttu-id="30137-114">Назад</span><span class="sxs-lookup"><span data-stu-id="30137-114">Previous</span></span>](walkthroughs-technical-get-started-overview.md)