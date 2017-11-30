---
title: "Ориентированная на службы архитектура"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Ориентированная на службы архитектура"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 970ff86c77100077d4c7710c0a697d1745d35819
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="service-oriented-architecture"></a><span data-ttu-id="174bb-104">Ориентированная на службы архитектура</span><span class="sxs-lookup"><span data-stu-id="174bb-104">Service-oriented architecture</span></span> 

<span data-ttu-id="174bb-105">Сервисноориентированной архитектуре (SOA) был перегрузке термин и означало разные вещи для разных людей.</span><span class="sxs-lookup"><span data-stu-id="174bb-105">Service-oriented architecture (SOA) was an overused term and has meant different things to different people.</span></span> <span data-ttu-id="174bb-106">Однако как общий знаменатель, SOA структурировать приложение сегментируя в нескольких службы (наиболее часто, как службы HTTP), которые можно классифицировать как различных типов подсистем или уровней.</span><span class="sxs-lookup"><span data-stu-id="174bb-106">But as a common denominator, SOA means that you structure your application by decomposing it into multiple services (most commonly as HTTP services) that can be classified as different types like subsystems or tiers.</span></span>

<span data-ttu-id="174bb-107">Эти службы можно теперь развернуть как контейнеры Docker которого решают проблемы развертывания, так как в образе контейнера включены все зависимости.</span><span class="sxs-lookup"><span data-stu-id="174bb-107">Those services can now be deployed as Docker containers, which solves deployment issues, because all the dependencies are included in the container image.</span></span> <span data-ttu-id="174bb-108">При необходимости осуществлять вертикальное масштабирование приложений SOA, может потребоваться масштабируемости и доступности проблем при развертывании на основании одного узлах Docker.</span><span class="sxs-lookup"><span data-stu-id="174bb-108">However, when you need to scale up SOA applications, you might have scalability and availability challenges if you are deploying based on single Docker hosts.</span></span> <span data-ttu-id="174bb-109">Это где Docker кластеризации программного обеспечения или orchestrator поможет вам, как описано в следующих разделах, в которых описаны способы развертывания микрослужбами.</span><span class="sxs-lookup"><span data-stu-id="174bb-109">This is where Docker clustering software or an orchestrator will help you out, as explained in later sections where we describe deployment approaches for microservices.</span></span>

<span data-ttu-id="174bb-110">Контейнеры docker являются полезным (но не обязательно) для традиционных архитектур, ориентированных на службы и более сложные архитектуры микрослужбами.</span><span class="sxs-lookup"><span data-stu-id="174bb-110">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="174bb-111">Микрослужбами являются производными от SOA, но отличается от микрослужбами архитектуры SOA.</span><span class="sxs-lookup"><span data-stu-id="174bb-111">Microservices derive from SOA, but SOA is different from microservices architecture.</span></span> <span data-ttu-id="174bb-112">Функции, например больших центра брокеров, центральный orchestrators на уровне организации и [шины службы Enterprise (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) обычно создаются в SOA.</span><span class="sxs-lookup"><span data-stu-id="174bb-112">Features like big central brokers, central orchestrators at the organization level, and the [Enterprise Service Bus (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) are typical in SOA.</span></span> <span data-ttu-id="174bb-113">Но в большинстве случаев они антишаблоны в сообществе микрослужбы.</span><span class="sxs-lookup"><span data-stu-id="174bb-113">But in most cases, these are anti-patterns in the microservice community.</span></span> <span data-ttu-id="174bb-114">На самом деле некоторые пользователи утверждать, что «микрослужбу архитектура — правильной SOA.»</span><span class="sxs-lookup"><span data-stu-id="174bb-114">In fact, some people argue that “The microservice architecture is SOA done right.”</span></span>

<span data-ttu-id="174bb-115">Это руководство посвящено микрослужбами, так как такое подробное чем требования и приемы, используемые в архитектуре микрослужбу подхода SOA.</span><span class="sxs-lookup"><span data-stu-id="174bb-115">This guide focuses on microservices, because a SOA approach is less prescriptive than the requirements and techniques used in a microservice architecture.</span></span> <span data-ttu-id="174bb-116">Если вы знаете, как создать приложение на основе микрослужбу, известно также как создать простой приложений, ориентированных на службы.</span><span class="sxs-lookup"><span data-stu-id="174bb-116">If you know how to build a microservice-based application, you also know how to build a simpler service-oriented application.</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="174bb-117">[Предыдущие] (docker приложения состояние data.md) [Далее] (микрослужбами architecture.md)</span><span class="sxs-lookup"><span data-stu-id="174bb-117">[Previous] (docker-application-state-data.md) [Next] (microservices-architecture.md)</span></span>
