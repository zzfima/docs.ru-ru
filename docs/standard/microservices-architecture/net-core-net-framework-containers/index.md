---
title: "Выбор между .NET Core и .NET Framework для контейнеров Docker"
description: "Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Выбор между .NET Core и .NET Framework для контейнеров Docker"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f7a5fee26f4d138ae22f3551a25a674b22a2f6d1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="6640e-104">Выбор между .NET Core и .NET Framework для контейнеров Docker</span><span class="sxs-lookup"><span data-stu-id="6640e-104">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="6640e-105">Серверные контейнерные приложения Docker на платформе .NET можно разрабатывать в двух поддерживаемых реализациях: [.NET Framework](https://www.microsoft.com/net/download/framework) и [.NET Core](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="6640e-105">There are two supported implementations for building server-side containerized Docker applications with .NET: [.NET Framework](https://www.microsoft.com/net/download/framework) and [.NET Core](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="6640e-106">В них используется множество одинаковых стандартных компонентов .NET, а код можно использовать как в одной среде, так и в другой.</span><span class="sxs-lookup"><span data-stu-id="6640e-106">They share many .NET Standard components, and you can share code across the two.</span></span> <span data-ttu-id="6640e-107">Но между этими двумя средами также существуют и фундаментальные различия. Поэтому ваш выбор будет зависеть от поставленной задачи.</span><span class="sxs-lookup"><span data-stu-id="6640e-107">However, there are fundamental differences between them, and which implementation you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="6640e-108">В этом разделе приводятся рекомендации по выбору каждой из реализаций.</span><span class="sxs-lookup"><span data-stu-id="6640e-108">This section provides guidance on when to choose each implementation.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="6640e-109">[Назад] (../container-docker-introduction/docker-containers-images-registries.md) [Далее] (general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="6640e-109">[Previous] (../container-docker-introduction/docker-containers-images-registries.md) [Next] (general-guidance.md)</span></span>
