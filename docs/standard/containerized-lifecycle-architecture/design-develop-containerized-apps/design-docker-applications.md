---
title: Проектирование приложений Docker
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 54f6f1ecdd89b85d4f44136da9a5ec9610f170a9
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="design-docker-applications"></a><span data-ttu-id="fedfd-103">Проектирование приложений Docker</span><span class="sxs-lookup"><span data-stu-id="fedfd-103">Design Docker applications</span></span>

<span data-ttu-id="fedfd-104">Раздел 1 появилась основные понятия о контейнерах и Docker.</span><span class="sxs-lookup"><span data-stu-id="fedfd-104">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="fedfd-105">Эти сведения будут базовый уровень сведения, необходимые приступить к работе.</span><span class="sxs-lookup"><span data-stu-id="fedfd-105">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="fedfd-106">Но корпоративных приложений могут быть сложными и состоит из нескольких служб, вместо одной службы или контейнера.</span><span class="sxs-lookup"><span data-stu-id="fedfd-106">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="fedfd-107">В тех случаях, необязательного использования необходимо знать дополнительные методы разработки, такие как сервисноориентированной архитектуре (SOA) и более сложных понятиях микрослужбами и контейнер orchestration основные понятия.</span><span class="sxs-lookup"><span data-stu-id="fedfd-107">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="fedfd-108">Не ограничена микрослужбами рамки данного документа, но для жизненного цикла приложения любые Docker, таким образом, он не исследовать микрослужбами архитектуры в глубину потому, что также можно использовать контейнеры и Docker с помощью обычных САН, фоновые задачи или задания, или даже с помощью методов развертывания монолитные приложения.</span><span class="sxs-lookup"><span data-stu-id="fedfd-108">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SAO, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="fedfd-109">Тем не менее прежде чем мы перейдем жизненного цикла приложения и DevOps, важно знать, как вы собираетесь разработки и построения приложения и какие имеются варианты проектирования.</span><span class="sxs-lookup"><span data-stu-id="fedfd-109">However, before we get into the application life cycle and DevOps, it is important to know how you are going to design and construct your application and what are your design choices.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="fedfd-110">[Предыдущие] (index.md) [Далее] (общий контейнера конструктора principles.md)</span><span class="sxs-lookup"><span data-stu-id="fedfd-110">[Previous] (index.md) [Next] (common-container-design-principles.md)</span></span>
