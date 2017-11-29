---
title: "Проектирование и разработка приложений .NET на основе множества контейнеров и микрослужб"
description: "Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Проектирование и разработка приложений .NET на основе множества контейнеров и микрослужб"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 46d2859fa3b739b1a2a8b1502d4e418fab204648
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="designing-and-developing-multi-container-and-microservice-based-net-applications"></a><span data-ttu-id="dc4ac-104">Проектирование и разработка приложений .NET на основе множества контейнеров и микрослужб</span><span class="sxs-lookup"><span data-stu-id="dc4ac-104">Designing and Developing Multi-Container and Microservice-Based .NET Applications</span></span>

<span data-ttu-id="dc4ac-105">*Разработка контейнерных приложений на основе микрослужб предполагает создание приложений с несколькими контейнерами. Но приложение с несколькими контейнерами может быть и проще (например, трехуровневое приложение) и может быть основано не на архитектуре микрослужб.*</span><span class="sxs-lookup"><span data-stu-id="dc4ac-105">*Developing containerized microservice applications means you are building multi-container applications. However, a multi-container application could also be simpler—for example, a three-tier application—and might not be built using a microservice architecture.*</span></span>

<span data-ttu-id="dc4ac-106">Ранее мы ставили вопрос: "Является ли использование Docker обязательным при разработке архитектуры микрослужб?"</span><span class="sxs-lookup"><span data-stu-id="dc4ac-106">Earlier we raised the question “Is Docker necessary when building a microservice architecture?”</span></span> <span data-ttu-id="dc4ac-107">Ответ был отрицательным.</span><span class="sxs-lookup"><span data-stu-id="dc4ac-107">The answer is a clear no.</span></span> <span data-ttu-id="dc4ac-108">Docker может давать существенные преимущества, но контейнеры и Docker не являются строгим требованием для микрослужб.</span><span class="sxs-lookup"><span data-stu-id="dc4ac-108">Docker is an enabler and can provide significant benefits, but containers and Docker are not a hard requirement for microservices.</span></span> <span data-ttu-id="dc4ac-109">Например, можно создать приложение на основе микрослужб со средством Docker или без него при использовании платформы Azure Service Fabric, которая поддерживает выполнение микрослужб как обычных процессов или контейнеров Docker.</span><span class="sxs-lookup"><span data-stu-id="dc4ac-109">As an example, you could create a microservices-based application with or without Docker when using Azure Service Fabric, which supports microservices running as simple processes or as Docker containers.</span></span>

<span data-ttu-id="dc4ac-110">Но если вы умеете проектировать и разрабатывать приложения на основе микрослужб с использованием контейнеров Docker, то вы также сможете разработать приложение на основе любой другой более простой модели.</span><span class="sxs-lookup"><span data-stu-id="dc4ac-110">However, if you know how to design and develop a microservices-based application that is also based on Docker containers, you will be able to design and develop any other, simpler application model.</span></span> <span data-ttu-id="dc4ac-111">Например, вы можете спроектировать трехуровневое приложение, которое также требует нескольких контейнеров.</span><span class="sxs-lookup"><span data-stu-id="dc4ac-111">For example, you might design a three-tier application that also requires a multi-container approach.</span></span> <span data-ttu-id="dc4ac-112">По этой причине, а также из-за растущей популярности архитектур на основе микрослужб в этом разделе основное внимание будет уделено реализации архитектуры на основе микрослужб с использованием контейнеров Docker.</span><span class="sxs-lookup"><span data-stu-id="dc4ac-112">Because of that, and because microservice architectures are an important trend within the container world, this section focuses on a microservice architecture implementation using Docker containers.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="dc4ac-113">[Назад] (../containerize-net-framework-applications/index.md) [Далее] (microservice-application-design.md)</span><span class="sxs-lookup"><span data-stu-id="dc4ac-113">[Previous] (../containerize-net-framework-applications/index.md) [Next] (microservice-application-design.md)</span></span>
