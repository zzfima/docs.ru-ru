---
title: Выбор между .NET Core и .NET Framework для контейнеров Docker
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Выбор между .NET Core и .NET Framework для контейнеров Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/11/2018
ms.openlocfilehash: 9abff2614e4022408a069be25440196111db19ab
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "46562113"
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="f785e-103">Выбор между .NET Core и .NET Framework для контейнеров Docker</span><span class="sxs-lookup"><span data-stu-id="f785e-103">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="f785e-104">Серверные контейнерные приложения Docker можно разрабатывать на двух поддерживаемых платформах .NET: [.NET Framework и .NET Core](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="f785e-104">There are two supported frameworks for building server-side containerized Docker applications with .NET: [.NET Framework and .NET Core](https://www.microsoft.com/net/download).</span></span> <span data-ttu-id="f785e-105">В них используется множество одинаковых компонентов платформы .NET, а код можно использовать как в одной среде, так и в другой.</span><span class="sxs-lookup"><span data-stu-id="f785e-105">They share many .NET platform components, and you can share code across the two.</span></span> <span data-ttu-id="f785e-106">Но между этими двумя платформами также существуют и фундаментальные различия. Поэтому ваш выбор будет зависеть от поставленной задачи.</span><span class="sxs-lookup"><span data-stu-id="f785e-106">However, there are fundamental differences between them, and which framework you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="f785e-107">В этом разделе приводятся рекомендации по выбору каждой из платформ.</span><span class="sxs-lookup"><span data-stu-id="f785e-107">This section provides guidance on when to choose each framework.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="f785e-108">[Назад](../container-docker-introduction/docker-containers-images-registries.md)
[Вперед](general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="f785e-108">[Previous](../container-docker-introduction/docker-containers-images-registries.md)
[Next](general-guidance.md)</span></span>
