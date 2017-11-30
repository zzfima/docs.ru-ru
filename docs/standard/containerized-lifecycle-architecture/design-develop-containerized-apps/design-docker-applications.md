---
title: "Проектирование приложений Docker"
description: "Жизненный цикл приложений контейнерного Docker с помощью платформы Майкрософт и средств"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: db8376abf95aab51fad23f4b351cb772351117ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="design-docker-applications"></a><span data-ttu-id="56e2b-104">Проектирование приложений Docker</span><span class="sxs-lookup"><span data-stu-id="56e2b-104">Design Docker applications</span></span>

<span data-ttu-id="56e2b-105">Раздел 1 появилась основные понятия о контейнерах и Docker.</span><span class="sxs-lookup"><span data-stu-id="56e2b-105">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="56e2b-106">Эти сведения будут базовый уровень сведения, необходимые приступить к работе.</span><span class="sxs-lookup"><span data-stu-id="56e2b-106">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="56e2b-107">Но корпоративных приложений могут быть сложными и состоит из нескольких служб, вместо одной службы или контейнера.</span><span class="sxs-lookup"><span data-stu-id="56e2b-107">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="56e2b-108">В тех случаях, необязательного использования необходимо знать дополнительные методы разработки, такие как сервисноориентированной архитектуре (SOA) и более сложных понятиях микрослужбами и контейнер orchestration основные понятия.</span><span class="sxs-lookup"><span data-stu-id="56e2b-108">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="56e2b-109">Не ограничена микрослужбами рамки данного документа, но для жизненного цикла приложения любые Docker, таким образом, он не исследовать микрослужбами архитектуры в глубину потому, что также можно использовать контейнеры и Docker с помощью обычных САН, фоновые задачи или задания, или даже с помощью методов развертывания монолитные приложения.</span><span class="sxs-lookup"><span data-stu-id="56e2b-109">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SAO, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="56e2b-110">Тем не менее прежде чем мы перейдем жизненного цикла приложения и DevOps, важно знать, как вы собираетесь разработки и построения приложения и какие имеются варианты проектирования.</span><span class="sxs-lookup"><span data-stu-id="56e2b-110">However, before we get into the application life cycle and DevOps, it is important to know how you are going to design and construct your application and what are your design choices.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="56e2b-111">[Предыдущие] (index.md) [Далее] (общий контейнера конструктора principles.md)</span><span class="sxs-lookup"><span data-stu-id="56e2b-111">[Previous] (index.md) [Next] (common-container-design-principles.md)</span></span>
