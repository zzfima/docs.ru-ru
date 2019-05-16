---
title: Приложения SOA
description: Имейте в виду, что контейнеры могут быть также это вариант развертывания полезных приложений SOA.
ms.date: 02/15/2019
ms.openlocfilehash: aa56ada7b14a465fb3dafd02b03b815782ac765b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644764"
---
# <a name="service-oriented-applications"></a><span data-ttu-id="b200b-103">Сервис ориентированных приложений</span><span class="sxs-lookup"><span data-stu-id="b200b-103">Service-oriented applications</span></span>

<span data-ttu-id="b200b-104">Сервис-ориентированной архитектуры (SOA) был это большой нагрузкой термин, который означает множество разных вещей для разных людей.</span><span class="sxs-lookup"><span data-stu-id="b200b-104">Service-Oriented Architecture (SOA) was an overused term that meant many different things to different people.</span></span> <span data-ttu-id="b200b-105">Но в качестве общего знаменателя термин SOA подразумевает структурирование архитектуры приложения путем его разделения на несколько служб (чаще всего в качестве HTTP-службы), которые можно классифицировать различными типами, такие как подсистемы или в других случаях, как уровни.</span><span class="sxs-lookup"><span data-stu-id="b200b-105">But as a common denominator, SOA means that you structure the architecture of your application by decomposing it into several services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="b200b-106">В настоящее время эти службы можно развернуть как контейнеры Docker, средства решения проблем, связанных с развертыванием, так как в образ контейнера включены все зависимости.</span><span class="sxs-lookup"><span data-stu-id="b200b-106">Today, you can deploy those services as Docker containers, which solve deployment-related issues because all of the dependencies are included in the container image.</span></span> <span data-ttu-id="b200b-107">Тем не менее когда необходимо горизонтальное масштабирование SOA, могут возникнуть трудности при развертывании на основе отдельных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="b200b-107">However, when you need to scale out SOAs, you might encounter challenges if you're deploying based on single instances.</span></span> <span data-ttu-id="b200b-108">Этот запрос может обрабатываться с помощью кластеризации программного обеспечения или оркестратор Docker.</span><span class="sxs-lookup"><span data-stu-id="b200b-108">This challenge can be handled using Docker clustering software or an orchestrator.</span></span> <span data-ttu-id="b200b-109">Мы рассмотрим оркестраторы более подробно в следующем разделе, при изучении микрослужбы.</span><span class="sxs-lookup"><span data-stu-id="b200b-109">We'll look at orchestrators in greater detail in the next section, when we explore microservices approaches.</span></span>

<span data-ttu-id="b200b-110">Контейнеры Docker являются полезным (но необязательным) элементом как для традиционных архитектур, ориентированных на службы, так и более сложных архитектур с микрослужбами.</span><span class="sxs-lookup"><span data-stu-id="b200b-110">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="b200b-111">В конце дня кластерные решения контейнера удобно для обоих традиционной архитектуры SOA, а также более сложные архитектуры микрослужб, в котором каждая микрослужба имеет свою модель данных.</span><span class="sxs-lookup"><span data-stu-id="b200b-111">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture and for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="b200b-112">И благодаря нескольких баз данных, также можно масштабировать уровень данных, а не для работы с монолитных базами данных, совместно использоваться службами SOA.</span><span class="sxs-lookup"><span data-stu-id="b200b-112">And thanks to multiple databases, you also can scale out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="b200b-113">Тем не менее рассказ о разделении данных является чисто об архитектуре и разработке.</span><span class="sxs-lookup"><span data-stu-id="b200b-113">However, the discussion about splitting the data is purely about architecture and design.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b200b-114">[Назад](state-and-data-in-docker-applications.md)
>[Вперед](orchestrate-high-scalability-availability.md)</span><span class="sxs-lookup"><span data-stu-id="b200b-114">[Previous](state-and-data-in-docker-applications.md)
[Next](orchestrate-high-scalability-availability.md)</span></span>
