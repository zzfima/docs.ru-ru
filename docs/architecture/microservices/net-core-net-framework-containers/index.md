---
title: Выбор между .NET Core и .NET Framework для контейнеров Docker
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Выбор между .NET Core и .NET Framework для контейнеров Docker
ms.date: 09/11/2018
ms.openlocfilehash: b01aaf25f4071e8e4a07905a12ec9dd0d89a738d
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70849272"
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="13d5a-103">Выбор между .NET Core и .NET Framework для контейнеров Docker</span><span class="sxs-lookup"><span data-stu-id="13d5a-103">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="13d5a-104">Серверные контейнерные приложения Docker можно разрабатывать на двух поддерживаемых платформах .NET: [.NET Framework и .NET Core](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="13d5a-104">There are two supported frameworks for building server-side containerized Docker applications with .NET: [.NET Framework and .NET Core](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="13d5a-105">В них используется множество одинаковых компонентов платформы .NET, а код можно использовать как в одной среде, так и в другой.</span><span class="sxs-lookup"><span data-stu-id="13d5a-105">They share many .NET platform components, and you can share code across the two.</span></span> <span data-ttu-id="13d5a-106">Но между этими двумя платформами также существуют и фундаментальные различия. Поэтому ваш выбор будет зависеть от поставленной задачи.</span><span class="sxs-lookup"><span data-stu-id="13d5a-106">However, there are fundamental differences between them, and which framework you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="13d5a-107">В этом разделе приводятся рекомендации по выбору каждой из платформ.</span><span class="sxs-lookup"><span data-stu-id="13d5a-107">This section provides guidance on when to choose each framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="13d5a-108">[Назад](../container-docker-introduction/docker-containers-images-registries.md)
>[Вперед](general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="13d5a-108">[Previous](../container-docker-introduction/docker-containers-images-registries.md)
[Next](general-guidance.md)</span></span>
