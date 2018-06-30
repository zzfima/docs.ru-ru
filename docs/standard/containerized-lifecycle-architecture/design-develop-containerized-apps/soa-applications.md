---
title: SOA приложений
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 276071a5d55015f2feecc27020ad614684907b4c
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105215"
---
# <a name="soa-applications"></a><span data-ttu-id="dc951-103">SOA приложений</span><span class="sxs-lookup"><span data-stu-id="dc951-103">SOA applications</span></span>

<span data-ttu-id="dc951-104">SOA был перегрузке термин и предназначен так много разных вещей для разных людей.</span><span class="sxs-lookup"><span data-stu-id="dc951-104">SOA was an overused term and meant so many different things to different people.</span></span> <span data-ttu-id="dc951-105">Но по крайней мере и как общий знаменатель, SOA, или ориентации на службы, среднее структуры архитектуры приложения сегментируя несколько служб (чаще всего в качестве службы HTTP), которые могут быть классифицированы различных типов, такие как подсистемы или в других случаях, как и уровнями.</span><span class="sxs-lookup"><span data-stu-id="dc951-105">But at a minimum and as a common denominator, SOA, or service orientation, mean that you structure the architecture of your application by decomposing it in multiple services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="dc951-106">В настоящее время эти службы можно развернуть как контейнеры Docker, которая решает проблем, связанных с развертыванием, поскольку все зависимости, входят в образе контейнера.</span><span class="sxs-lookup"><span data-stu-id="dc951-106">Today, you can deploy those services as Docker containers, which solves deployment-related issues because all of the dependencies are included within the container image.</span></span> <span data-ttu-id="dc951-107">Тем не менее при необходимости масштабирования SOA, могут возникнуть трудности при развертывании на основе отдельные экземпляры.</span><span class="sxs-lookup"><span data-stu-id="dc951-107">However, when you need to scale-out SOAs, you might encounter challenges if you are deploying based on single instances.</span></span> <span data-ttu-id="dc951-108">Это происходит, где Docker кластеризации программного обеспечения или orchestrator поможет вам.</span><span class="sxs-lookup"><span data-stu-id="dc951-108">This is where a Docker clustering software or orchestrator will help you.</span></span> <span data-ttu-id="dc951-109">Мы рассмотрим это более подробно в следующем разделе после тщательного изучения микрослужбами подходов.</span><span class="sxs-lookup"><span data-stu-id="dc951-109">We'll look at this in greater detail in the next section when we examine microservices approaches.</span></span>

<span data-ttu-id="dc951-110">В конце дня кластерные решения контейнера удобны для обоих традиционной архитектуры SOA и для более сложных микрослужбами архитектуры, в которой каждый микрослужбу владеет его модели данных.</span><span class="sxs-lookup"><span data-stu-id="dc951-110">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture or for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="dc951-111">И, благодаря несколько баз данных, вы также можно горизонтально масштабировать уровень данных вместо работы с базами данных монолитные, совместно используемые службами SOA.</span><span class="sxs-lookup"><span data-stu-id="dc951-111">And, thanks to multiple databases, you also can scale-out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="dc951-112">Тем не менее сведения о разделении данных — исключительно об архитектуре и разработке.</span><span class="sxs-lookup"><span data-stu-id="dc951-112">However, the discussion about splitting the data is purely about architecture and design.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="dc951-113">[Назад](state-and-data-in-docker-applications.md)
[Вперед](orchestrate-high-scalability-availability.md)</span><span class="sxs-lookup"><span data-stu-id="dc951-113">[Previous](state-and-data-in-docker-applications.md)
[Next](orchestrate-high-scalability-availability.md)</span></span>
