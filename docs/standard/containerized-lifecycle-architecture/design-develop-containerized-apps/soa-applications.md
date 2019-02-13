---
title: Приложения SOA
description: Имейте в виду, что контейнеры могут быть также это вариант развертывания полезных приложений SOA.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 4fd39e075c5730cf7fddb0138cdb5267a914c91f
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221268"
---
# <a name="soa-applications"></a><span data-ttu-id="2751d-103">Приложения SOA</span><span class="sxs-lookup"><span data-stu-id="2751d-103">SOA applications</span></span>

<span data-ttu-id="2751d-104">SOA, было это большой нагрузкой термин и предназначен множество разные вещи для разных людей.</span><span class="sxs-lookup"><span data-stu-id="2751d-104">SOA was an overused term and meant so many different things to different people.</span></span> <span data-ttu-id="2751d-105">Но как минимум и как общий знаменатель, SOA, или ориентации на службы, среднее структура архитектуры приложения путем разделения его в нескольких службах (чаще всего в качестве HTTP-службы), которые можно разделить на различные типы, такие как подсистемы Кроме того, в других случаях, как и на уровнях.</span><span class="sxs-lookup"><span data-stu-id="2751d-105">But at a minimum and as a common denominator, SOA, or service orientation, mean that you structure the architecture of your application by decomposing it in multiple services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="2751d-106">В настоящее время эти службы можно развернуть как контейнеры Docker, который решает проблем, связанных с развертыванием, поскольку все зависимости, которые будут входить в образ контейнера.</span><span class="sxs-lookup"><span data-stu-id="2751d-106">Today, you can deploy those services as Docker containers, which solves deployment-related issues because all of the dependencies are included within the container image.</span></span> <span data-ttu-id="2751d-107">Тем не менее когда необходимо горизонтальное масштабирование SOA, могут возникнуть трудности при развертывании на основе отдельных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="2751d-107">However, when you need to scale-out SOAs, you might encounter challenges if you are deploying based on single instances.</span></span> <span data-ttu-id="2751d-108">Это где кластеризации программного обеспечения или оркестратора Docker помогут вам.</span><span class="sxs-lookup"><span data-stu-id="2751d-108">This is where a Docker clustering software or orchestrator will help you.</span></span> <span data-ttu-id="2751d-109">Мы рассмотрим это более подробно в следующем разделе при рассмотрении микрослужбы.</span><span class="sxs-lookup"><span data-stu-id="2751d-109">We'll look at this in greater detail in the next section when we examine microservices approaches.</span></span>

<span data-ttu-id="2751d-110">В конце дня кластерные решения контейнера полезны для обоих традиционной архитектуры SOA или более сложные архитектуры микрослужб, в котором каждая микрослужба имеет свою модель данных.</span><span class="sxs-lookup"><span data-stu-id="2751d-110">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture or for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="2751d-111">И, благодаря нескольких баз данных, вы также можете развернуть на уровне данных, а не для работы с монолитных базами данных, совместно использоваться службами SOA.</span><span class="sxs-lookup"><span data-stu-id="2751d-111">And, thanks to multiple databases, you also can scale-out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="2751d-112">Тем не менее рассказ о разделении данных является чисто об архитектуре и разработке.</span><span class="sxs-lookup"><span data-stu-id="2751d-112">However, the discussion about splitting the data is purely about architecture and design.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2751d-113">[Назад](state-and-data-in-docker-applications.md)
>[Вперед](orchestrate-high-scalability-availability.md)</span><span class="sxs-lookup"><span data-stu-id="2751d-113">[Previous](state-and-data-in-docker-applications.md)
[Next](orchestrate-high-scalability-availability.md)</span></span>