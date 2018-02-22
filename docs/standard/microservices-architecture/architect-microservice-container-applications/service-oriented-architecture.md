---
title: "Сервисноориентированная архитектура"
description: "Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Сервисноориентированная архитектура"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6a5f0f53f4208c9944adea33fe1aa3f35fed81ab
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="service-oriented-architecture"></a><span data-ttu-id="ed6f6-104">Сервисноориентированная архитектура</span><span class="sxs-lookup"><span data-stu-id="ed6f6-104">Service-oriented architecture</span></span> 

<span data-ttu-id="ed6f6-105">Термин "сервисноориентированная архитектура" (SOA) перегружен значениями и для разных людей означает разные понятия.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-105">Service-oriented architecture (SOA) was an overused term and has meant different things to different people.</span></span> <span data-ttu-id="ed6f6-106">Но в качестве общего знаменателя термин SOA подразумевает структурирование приложения путем разделения его на несколько служб (наиболее часто HTTP-службы), которые можно классифицировать различными способами, например как подсистемы или уровни.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-106">But as a common denominator, SOA means that you structure your application by decomposing it into multiple services (most commonly as HTTP services) that can be classified as different types like subsystems or tiers.</span></span>

<span data-ttu-id="ed6f6-107">Теперь эти службы можно развернуть как контейнеры Docker, которые помогают решать проблемы развертывания, так как в образ контейнера включены все зависимости.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-107">Those services can now be deployed as Docker containers, which solves deployment issues, because all the dependencies are included in the container image.</span></span> <span data-ttu-id="ed6f6-108">Однако, если вы используете отдельные узлы Docker, то при необходимости масштабирования приложений SOA вы столкнетесь с проблемами масштабируемости и доступности.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-108">However, when you need to scale up SOA applications, you might have scalability and availability challenges if you are deploying based on single Docker hosts.</span></span> <span data-ttu-id="ed6f6-109">Именно для решения таких проблем предназначено программное обеспечение для кластеризации Docker, или оркестратор, которое описано в следующих разделах, где мы расскажем о способах развертывания микрослужб.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-109">This is where Docker clustering software or an orchestrator will help you out, as explained in later sections where we describe deployment approaches for microservices.</span></span>

<span data-ttu-id="ed6f6-110">Контейнеры Docker являются полезным (но необязательным) элементом как для традиционных архитектур, ориентированных на службы, так и более сложных архитектур с микрослужбами.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-110">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="ed6f6-111">Микрослужбы являются производными от архитектуры SOA, но эти архитектуры отличаются друг от друга.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-111">Microservices derive from SOA, but SOA is different from microservices architecture.</span></span> <span data-ttu-id="ed6f6-112">Для архитектуры SOA являются типичными такие компоненты, как большие центральные брокеры и центральные оркестраторы на уровне организации, а также [сервисная шина предприятия (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus).</span><span class="sxs-lookup"><span data-stu-id="ed6f6-112">Features like big central brokers, central orchestrators at the organization level, and the [Enterprise Service Bus (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) are typical in SOA.</span></span> <span data-ttu-id="ed6f6-113">Но для архитектуры микрослужб в большинстве случаев они являются признаком дурного тона.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-113">But in most cases, these are anti-patterns in the microservice community.</span></span> <span data-ttu-id="ed6f6-114">Некоторые специалисты даже утверждают, что "архитектура микрослужб — это правильно сделанный SOA".</span><span class="sxs-lookup"><span data-stu-id="ed6f6-114">In fact, some people argue that “The microservice architecture is SOA done right.”</span></span>

<span data-ttu-id="ed6f6-115">Это руководство посвящено описанию микрослужб, поскольку подход SOA менее требователен по сравнению с требованиями и техниками архитектуры микрослужб.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-115">This guide focuses on microservices, because a SOA approach is less prescriptive than the requirements and techniques used in a microservice architecture.</span></span> <span data-ttu-id="ed6f6-116">Если вы знаете, как создать приложение на основе технологии микрослужб, то вы сможете создать и простое сервисноориентированное приложение.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-116">If you know how to build a microservice-based application, you also know how to build a simpler service-oriented application.</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="ed6f6-117">[Назад] (docker-application-state-data.md) [Далее] (microservices-architecture.md)</span><span class="sxs-lookup"><span data-stu-id="ed6f6-117">[Previous] (docker-application-state-data.md) [Next] (microservices-architecture.md)</span></span>
