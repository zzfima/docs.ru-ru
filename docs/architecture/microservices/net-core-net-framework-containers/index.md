---
title: Выбор между .NET Core и .NET Framework для контейнеров Docker
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Выбор между .NET Core и .NET Framework для контейнеров Docker
ms.date: 09/11/2018
ms.openlocfilehash: 771d23cf4610e5778f0a144386754ce10d6ae144
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "70295219"
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="56d03-103">Выбор между .NET Core и .NET Framework для контейнеров Docker</span><span class="sxs-lookup"><span data-stu-id="56d03-103">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="56d03-104">Серверные контейнерные приложения Docker можно разрабатывать на двух поддерживаемых платформах .NET: [.NET Framework и .NET Core](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="56d03-104">There are two supported frameworks for building server-side containerized Docker applications with .NET: [.NET Framework and .NET Core](https://www.microsoft.com/net/download).</span></span> <span data-ttu-id="56d03-105">В них используется множество одинаковых компонентов платформы .NET, а код можно использовать как в одной среде, так и в другой.</span><span class="sxs-lookup"><span data-stu-id="56d03-105">They share many .NET platform components, and you can share code across the two.</span></span> <span data-ttu-id="56d03-106">Но между этими двумя платформами также существуют и фундаментальные различия. Поэтому ваш выбор будет зависеть от поставленной задачи.</span><span class="sxs-lookup"><span data-stu-id="56d03-106">However, there are fundamental differences between them, and which framework you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="56d03-107">В этом разделе приводятся рекомендации по выбору каждой из платформ.</span><span class="sxs-lookup"><span data-stu-id="56d03-107">This section provides guidance on when to choose each framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="56d03-108">[Назад](../container-docker-introduction/docker-containers-images-registries.md)
>[Вперед](general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="56d03-108">[Previous](../container-docker-introduction/docker-containers-images-registries.md)
[Next](general-guidance.md)</span></span>
