---
title: Приложения SOA
description: Имейте в виду, что контейнеры могут быть удобным вариантом развертывания для приложений SOA.
ms.date: 02/15/2019
ms.openlocfilehash: aa56ada7b14a465fb3dafd02b03b815782ac765b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "68672361"
---
# <a name="service-oriented-applications"></a><span data-ttu-id="7e501-103">Сервисноориентированные приложения</span><span class="sxs-lookup"><span data-stu-id="7e501-103">Service-oriented applications</span></span>

<span data-ttu-id="7e501-104">Термин "сервисноориентированная архитектура" (SOA) перегружен значениями и для разных людей означает разные понятия.</span><span class="sxs-lookup"><span data-stu-id="7e501-104">Service-Oriented Architecture (SOA) was an overused term that meant many different things to different people.</span></span> <span data-ttu-id="7e501-105">Однако общий момент заключается в том, что термин SOA подразумевает структурирование архитектуры приложения путем разделения ее на несколько служб (чаще всего HTTP-службы), которые можно классифицировать различными способами, например как подсистемы или уровни.</span><span class="sxs-lookup"><span data-stu-id="7e501-105">But as a common denominator, SOA means that you structure the architecture of your application by decomposing it into several services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="7e501-106">Сейчас эти службы можно развернуть как контейнеры Docker, которые помогают решать проблемы развертывания, так как в образ контейнера включены все зависимости.</span><span class="sxs-lookup"><span data-stu-id="7e501-106">Today, you can deploy those services as Docker containers, which solve deployment-related issues because all of the dependencies are included in the container image.</span></span> <span data-ttu-id="7e501-107">Однако, если при развертывании вы используете отдельные экземпляры, то при необходимости масштабирования приложений SOA вы столкнетесь с проблемами.</span><span class="sxs-lookup"><span data-stu-id="7e501-107">However, when you need to scale out SOAs, you might encounter challenges if you're deploying based on single instances.</span></span> <span data-ttu-id="7e501-108">Эту проблему можно решить с помощью программного обеспечения кластеризации Docker или оркестратора.</span><span class="sxs-lookup"><span data-stu-id="7e501-108">This challenge can be handled using Docker clustering software or an orchestrator.</span></span> <span data-ttu-id="7e501-109">Мы рассмотрим оркестраторы более подробно в следующем разделе, при изучении подходов на основе микрослужб.</span><span class="sxs-lookup"><span data-stu-id="7e501-109">We'll look at orchestrators in greater detail in the next section, when we explore microservices approaches.</span></span>

<span data-ttu-id="7e501-110">Контейнеры Docker являются полезным (но необязательным) элементом как для традиционных архитектур, ориентированных на службы, так и более сложных архитектур с микрослужбами.</span><span class="sxs-lookup"><span data-stu-id="7e501-110">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="7e501-111">В целом решения кластеризации на базе контейнеров удобны как для традиционной архитектуры SOA, так и для более сложной архитектуры микрослужб, где каждая микрослужба имеет свою модель данных.</span><span class="sxs-lookup"><span data-stu-id="7e501-111">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture and for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="7e501-112">А благодаря нескольким базам данных вы также можете масштабировать уровень данных вместо работы с монолитных базами данных, совместно используемыми службами SOA.</span><span class="sxs-lookup"><span data-stu-id="7e501-112">And thanks to multiple databases, you also can scale out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="7e501-113">Однако обсуждение разделения данных касается исключительно архитектуры и проектирования.</span><span class="sxs-lookup"><span data-stu-id="7e501-113">However, the discussion about splitting the data is purely about architecture and design.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7e501-114">[Назад](state-and-data-in-docker-applications.md)
>[Вперед](orchestrate-high-scalability-availability.md)</span><span class="sxs-lookup"><span data-stu-id="7e501-114">[Previous](state-and-data-in-docker-applications.md)
[Next](orchestrate-high-scalability-availability.md)</span></span>
