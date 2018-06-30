---
title: Выбор между .NET Core и .NET Framework для контейнеров Docker
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Выбор между .NET Core и .NET Framework для контейнеров Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 0f6689468eda1dd1b12c24927e650b2b01381274
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37104446"
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="35b56-103">Выбор между .NET Core и .NET Framework для контейнеров Docker</span><span class="sxs-lookup"><span data-stu-id="35b56-103">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="35b56-104">Серверные контейнерные приложения Docker на платформе .NET можно разрабатывать в двух поддерживаемых реализациях: [.NET Framework](https://www.microsoft.com/net/download/framework) и [.NET Core](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="35b56-104">There are two supported implementations for building server-side containerized Docker applications with .NET: [.NET Framework](https://www.microsoft.com/net/download/framework) and [.NET Core](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="35b56-105">В них используется множество одинаковых стандартных компонентов .NET, а код можно использовать как в одной среде, так и в другой.</span><span class="sxs-lookup"><span data-stu-id="35b56-105">They share many .NET Standard components, and you can share code across the two.</span></span> <span data-ttu-id="35b56-106">Но между этими двумя средами также существуют и фундаментальные различия. Поэтому ваш выбор будет зависеть от поставленной задачи.</span><span class="sxs-lookup"><span data-stu-id="35b56-106">However, there are fundamental differences between them, and which implementation you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="35b56-107">В этом разделе приводятся рекомендации по выбору каждой из реализаций.</span><span class="sxs-lookup"><span data-stu-id="35b56-107">This section provides guidance on when to choose each implementation.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="35b56-108">[Назад](../container-docker-introduction/docker-containers-images-registries.md)
[Вперед](general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="35b56-108">[Previous](../container-docker-introduction/docker-containers-images-registries.md)
[Next](general-guidance.md)</span></span>
