---
title: Приложения SOA
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 7f88daaf0787cf780e7ab9602f35ae4e6ab8308c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155318"
---
# <a name="soa-applications"></a><span data-ttu-id="258c1-103">Приложения SOA</span><span class="sxs-lookup"><span data-stu-id="258c1-103">SOA applications</span></span>

<span data-ttu-id="258c1-104">SOA, было это большой нагрузкой термин и предназначен множество разные вещи для разных людей.</span><span class="sxs-lookup"><span data-stu-id="258c1-104">SOA was an overused term and meant so many different things to different people.</span></span> <span data-ttu-id="258c1-105">Но как минимум и как общий знаменатель, SOA, или ориентации на службы, среднее структура архитектуры приложения путем разделения его в нескольких службах (чаще всего в качестве HTTP-службы), которые можно разделить на различные типы, такие как подсистемы Кроме того, в других случаях, как и на уровнях.</span><span class="sxs-lookup"><span data-stu-id="258c1-105">But at a minimum and as a common denominator, SOA, or service orientation, mean that you structure the architecture of your application by decomposing it in multiple services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="258c1-106">В настоящее время эти службы можно развернуть как контейнеры Docker, который решает проблем, связанных с развертыванием, поскольку все зависимости, которые будут входить в образ контейнера.</span><span class="sxs-lookup"><span data-stu-id="258c1-106">Today, you can deploy those services as Docker containers, which solves deployment-related issues because all of the dependencies are included within the container image.</span></span> <span data-ttu-id="258c1-107">Тем не менее когда необходимо горизонтальное масштабирование SOA, могут возникнуть трудности при развертывании на основе отдельных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="258c1-107">However, when you need to scale-out SOAs, you might encounter challenges if you are deploying based on single instances.</span></span> <span data-ttu-id="258c1-108">Это где кластеризации программного обеспечения или оркестратора Docker помогут вам.</span><span class="sxs-lookup"><span data-stu-id="258c1-108">This is where a Docker clustering software or orchestrator will help you.</span></span> <span data-ttu-id="258c1-109">Мы рассмотрим это более подробно в следующем разделе при рассмотрении микрослужбы.</span><span class="sxs-lookup"><span data-stu-id="258c1-109">We'll look at this in greater detail in the next section when we examine microservices approaches.</span></span>

<span data-ttu-id="258c1-110">В конце дня кластерные решения контейнера полезны для обоих традиционной архитектуры SOA или более сложные архитектуры микрослужб, в котором каждая микрослужба имеет свою модель данных.</span><span class="sxs-lookup"><span data-stu-id="258c1-110">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture or for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="258c1-111">И, благодаря нескольких баз данных, вы также можете развернуть на уровне данных, а не для работы с монолитных базами данных, совместно использоваться службами SOA.</span><span class="sxs-lookup"><span data-stu-id="258c1-111">And, thanks to multiple databases, you also can scale-out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="258c1-112">Тем не менее рассказ о разделении данных является чисто об архитектуре и разработке.</span><span class="sxs-lookup"><span data-stu-id="258c1-112">However, the discussion about splitting the data is purely about architecture and design.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="258c1-113">[Назад](state-and-data-in-docker-applications.md)
>[Вперед](orchestrate-high-scalability-availability.md)</span><span class="sxs-lookup"><span data-stu-id="258c1-113">[Previous](state-and-data-in-docker-applications.md)
[Next](orchestrate-high-scalability-availability.md)</span></span>