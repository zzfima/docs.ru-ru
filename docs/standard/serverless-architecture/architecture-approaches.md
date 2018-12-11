---
title: Подходы к архитектуре - Бессерверных приложений
description: Введение в архитектуру подходы для создания корпоративных облачных приложений, из N-уровневые архитектуры для бессерверной.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 04ad383586f974bb2dccc4623a9a254f5668dab4
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53126749"
---
# <a name="architecture-approaches"></a><span data-ttu-id="e61c0-103">Подходы к архитектуре</span><span class="sxs-lookup"><span data-stu-id="e61c0-103">Architecture approaches</span></span>

<span data-ttu-id="e61c0-104">Основные сведения о существующих подходах к разработке архитектуры корпоративных приложений поможет внести ясность роль, которую выполняет без сервера.</span><span class="sxs-lookup"><span data-stu-id="e61c0-104">Understanding existing approaches to architecting enterprise apps helps clarify the role played by serverless.</span></span> <span data-ttu-id="e61c0-105">Существует много подходов и шаблоны, которые развиваются за последние десять лет разработки программного обеспечения, и все имеют свои преимущества и недостатки.</span><span class="sxs-lookup"><span data-stu-id="e61c0-105">There are many approaches and patterns that evolved over decades of software development, and all have their own pros and cons.</span></span> <span data-ttu-id="e61c0-106">Во многих случаях гарантированное решение не может включать выбор единый подход, но могут сочетаться несколько подходов.</span><span class="sxs-lookup"><span data-stu-id="e61c0-106">In many cases, the ultimate solution may not involve deciding on a single approach but may integrate several approaches.</span></span> <span data-ttu-id="e61c0-107">Сценарии миграции часто включают в себя перехода от одного архитектурного подхода к другому через гибридный подход.</span><span class="sxs-lookup"><span data-stu-id="e61c0-107">Migration scenarios often involve shifting from one architecture approach to another through a hybrid approach.</span></span>

<span data-ttu-id="e61c0-108">В этой главе содержится обзор обоих шаблонов логическая и физическая архитектура для корпоративных приложений.</span><span class="sxs-lookup"><span data-stu-id="e61c0-108">This chapter provides an overview of both logical and physical architecture patterns for enterprise applications.</span></span>

## <a name="architecture-patterns"></a><span data-ttu-id="e61c0-109">Шаблоны архитектуры</span><span class="sxs-lookup"><span data-stu-id="e61c0-109">Architecture patterns</span></span>

<span data-ttu-id="e61c0-110">Современные бизнес-приложения выполните различные шаблоны архитектуры.</span><span class="sxs-lookup"><span data-stu-id="e61c0-110">Modern business applications follow a variety of architecture patterns.</span></span> <span data-ttu-id="e61c0-111">Этот раздел представляет обзор общих шаблонов.</span><span class="sxs-lookup"><span data-stu-id="e61c0-111">This section represents a survey of common patterns.</span></span> <span data-ttu-id="e61c0-112">Шаблоны, перечисленные здесь не обязательно все рекомендации, а также показаны различные подходы.</span><span class="sxs-lookup"><span data-stu-id="e61c0-112">The patterns listed here aren't necessarily all best practices, but illustrate different approaches.</span></span>

<span data-ttu-id="e61c0-113">Дополнительные сведения см. в разделе [руководство по архитектуре приложений Azure](https://docs.microsoft.com/azure/architecture/guide/).</span><span class="sxs-lookup"><span data-stu-id="e61c0-113">For more information, see [Azure application architecture guide](https://docs.microsoft.com/azure/architecture/guide/).</span></span>

## <a name="monoliths"></a><span data-ttu-id="e61c0-114">Монолитных структур</span><span class="sxs-lookup"><span data-stu-id="e61c0-114">Monoliths</span></span>

<span data-ttu-id="e61c0-115">Многие бизнес-приложения соответствуют шаблону монолитного приложения.</span><span class="sxs-lookup"><span data-stu-id="e61c0-115">Many business applications follow a monolith pattern.</span></span> <span data-ttu-id="e61c0-116">Устаревшие приложения часто реализуются как монолитных структур.</span><span class="sxs-lookup"><span data-stu-id="e61c0-116">Legacy applications are often implemented as monoliths.</span></span> <span data-ttu-id="e61c0-117">В шаблоне монолитного приложения все проблемы приложения содержатся в одном развертывании.</span><span class="sxs-lookup"><span data-stu-id="e61c0-117">In the monolith pattern, all application concerns are contained in a single deployment.</span></span> <span data-ttu-id="e61c0-118">Все из пользовательского интерфейса для вызовов базы данных уже включено в той же базой кода.</span><span class="sxs-lookup"><span data-stu-id="e61c0-118">Everything from user interface to database calls is included in the same codebase.</span></span>

![Архитектура монолитного приложения](./media/monolith-architecture.png)

<span data-ttu-id="e61c0-120">Существует несколько преимуществ подхода монолитного приложения.</span><span class="sxs-lookup"><span data-stu-id="e61c0-120">There are several advantages to the monolith approach.</span></span> <span data-ttu-id="e61c0-121">Часто бывает проще развернуть единую базу кода и приступить к работе.</span><span class="sxs-lookup"><span data-stu-id="e61c0-121">It's often easy to pull down a single code base and start working.</span></span> <span data-ttu-id="e61c0-122">Дополнительное время может быть меньше, и создание тестовых сред сложнее, чем предоставляет новую копию.</span><span class="sxs-lookup"><span data-stu-id="e61c0-122">Ramp up time may be less, and creating test environments is as simple as providing a new copy.</span></span> <span data-ttu-id="e61c0-123">При разработке монолитного приложения может включать несколько компонентов и приложений.</span><span class="sxs-lookup"><span data-stu-id="e61c0-123">The monolith may be designed to include multiple components and applications.</span></span>

<span data-ttu-id="e61c0-124">К сожалению шаблон монолитного приложения обычно разбить в нужном масштабе.</span><span class="sxs-lookup"><span data-stu-id="e61c0-124">Unfortunately, the monolith pattern tends to break down at scale.</span></span> <span data-ttu-id="e61c0-125">Основные недостатки монолитного приложения включают:</span><span class="sxs-lookup"><span data-stu-id="e61c0-125">Major disadvantages of the monolith approach include:</span></span>

* <span data-ttu-id="e61c0-126">Трудно работать параллельно в той же базе кода.</span><span class="sxs-lookup"><span data-stu-id="e61c0-126">Difficult to work in parallel in the same code base.</span></span>
* <span data-ttu-id="e61c0-127">Любое изменение, независимо от того, как тривиальный, требуется развертывание новой версии приложения.</span><span class="sxs-lookup"><span data-stu-id="e61c0-127">Any change, no matter how trivial, requires deploying a new version of the entire application.</span></span>
* <span data-ttu-id="e61c0-128">Рефакторинг потенциально влияет на все приложение.</span><span class="sxs-lookup"><span data-stu-id="e61c0-128">Refactoring potentially impacts the entire application.</span></span>
* <span data-ttu-id="e61c0-129">Часто является единственным решением для масштабирования для создания нескольких копий ресурсоемкий монолитного приложения.</span><span class="sxs-lookup"><span data-stu-id="e61c0-129">Often the only solution to scale is to create multiple, resource-intensive copies of the monolith.</span></span>
* <span data-ttu-id="e61c0-130">Как развернуть систем или полученные другим системам, интеграции может быть затруднено.</span><span class="sxs-lookup"><span data-stu-id="e61c0-130">As systems expand or other systems are acquired, integration can be difficult.</span></span>
* <span data-ttu-id="e61c0-131">Возможно, трудно тестировать из-за необходимость в настройке всей монолитного приложения.</span><span class="sxs-lookup"><span data-stu-id="e61c0-131">It may be difficult to test due to the need to configure the entire monolith.</span></span>
* <span data-ttu-id="e61c0-132">Повторное использование кода сложна и часто других приложений в итоге использования собственных копий кода.</span><span class="sxs-lookup"><span data-stu-id="e61c0-132">Code reuse is challenging and often other apps end up having their own copies of code.</span></span>

<span data-ttu-id="e61c0-133">Многие компании обращаться в облако как возможность переноса приложений монолитного приложения и в то же время рефакторинг их в другие шаблоны можно использовать.</span><span class="sxs-lookup"><span data-stu-id="e61c0-133">Many businesses look to the cloud as an opportunity to migrate monolith applications and at the same time refactor them to more usable patterns.</span></span> <span data-ttu-id="e61c0-134">Довольно часто для разделения отдельных приложений и компонентов, чтобы они могли поддерживать, развертывать и масштабировать отдельно.</span><span class="sxs-lookup"><span data-stu-id="e61c0-134">It's common to break out the individual applications and components to allow them to be maintained, deployed, and scaled separately.</span></span>

## <a name="n-layer-applications"></a><span data-ttu-id="e61c0-135">N-Слойных приложений</span><span class="sxs-lookup"><span data-stu-id="e61c0-135">N-Layer applications</span></span>

<span data-ttu-id="e61c0-136">Логика приложения секции N-слойных приложений на определенных уровнях.</span><span class="sxs-lookup"><span data-stu-id="e61c0-136">N-layer application partition application logic into specific layers.</span></span> <span data-ttu-id="e61c0-137">Наиболее распространенные слои включают:</span><span class="sxs-lookup"><span data-stu-id="e61c0-137">The most common layers include:</span></span>

* <span data-ttu-id="e61c0-138">Пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="e61c0-138">User interface</span></span>
* <span data-ttu-id="e61c0-139">бизнес-логики</span><span class="sxs-lookup"><span data-stu-id="e61c0-139">Business logic</span></span>
* <span data-ttu-id="e61c0-140">Доступ к данным</span><span class="sxs-lookup"><span data-stu-id="e61c0-140">Data access</span></span>

<span data-ttu-id="e61c0-141">По промежуточного слоя, пакетная обработка и API, может включать других слоев.</span><span class="sxs-lookup"><span data-stu-id="e61c0-141">Other layers may include middleware, batch processing, and API.</span></span> <span data-ttu-id="e61c0-142">Это важно отметить, что слои являются логическими.</span><span class="sxs-lookup"><span data-stu-id="e61c0-142">It's important to note the layers are logical.</span></span> <span data-ttu-id="e61c0-143">Несмотря на то, что разработали изолированно, их все можно развернуть для одной целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="e61c0-143">Although they're developed in isolation, they may all be deployed to the same target platform.</span></span>

![Архитектура уровня N](./media/n-layer-architecture.png)

<span data-ttu-id="e61c0-145">Существует несколько преимуществ в методе с N-Слойных, включая:</span><span class="sxs-lookup"><span data-stu-id="e61c0-145">There are several advantages to the N-Layer approach, including:</span></span>

* <span data-ttu-id="e61c0-146">Рефакторинг — это изолированное со слоем.</span><span class="sxs-lookup"><span data-stu-id="e61c0-146">Refactoring is isolated to a layer.</span></span>
* <span data-ttu-id="e61c0-147">Команды можно независимо друг от друга построение, тестирование, развертывание и обслуживание отдельные слои.</span><span class="sxs-lookup"><span data-stu-id="e61c0-147">Teams can independently build, test, deploy, and maintain separate layers.</span></span>
* <span data-ttu-id="e61c0-148">Слои можно выгрузить, например на уровне данных могут получить доступ к нескольким базам данных без внесения изменений на уровне пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e61c0-148">Layers can be swapped out, for example the data layer may access multiple databases without requiring changes to the UI layer.</span></span>

<span data-ttu-id="e61c0-149">Без использования сервера может использоваться для реализации один или несколько слоев.</span><span class="sxs-lookup"><span data-stu-id="e61c0-149">Serverless may be used to implement one or more layers.</span></span>

## <a name="microservices"></a><span data-ttu-id="e61c0-150">Микрослужбы</span><span class="sxs-lookup"><span data-stu-id="e61c0-150">Microservices</span></span>

<span data-ttu-id="e61c0-151">**[Микрослужбы](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)**  архитектуры содержат общие характеристики, которые включают:</span><span class="sxs-lookup"><span data-stu-id="e61c0-151">**[Microservices](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** architectures contain common characteristics that include:</span></span>

* <span data-ttu-id="e61c0-152">Приложения состоят из нескольких небольших служб.</span><span class="sxs-lookup"><span data-stu-id="e61c0-152">Applications are composed of several small services.</span></span>
* <span data-ttu-id="e61c0-153">Каждая служба выполняется в своем собственном процессе.</span><span class="sxs-lookup"><span data-stu-id="e61c0-153">Each service runs in its own process.</span></span>
* <span data-ttu-id="e61c0-154">Службы выравниваются вокруг бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e61c0-154">Services are aligned around business domains.</span></span>
* <span data-ttu-id="e61c0-155">Службы взаимодействуют через упрощенный API, обычно с помощью HTTP как транспорт.</span><span class="sxs-lookup"><span data-stu-id="e61c0-155">Services communicate over lightweight APIs, typically using HTTP as the transport.</span></span>
* <span data-ttu-id="e61c0-156">Службы можно развернуть и обновить независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="e61c0-156">Services can be deployed and upgraded independently.</span></span>
* <span data-ttu-id="e61c0-157">Службы не зависят от едином хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="e61c0-157">Services aren't dependent on a single data store.</span></span>
* <span data-ttu-id="e61c0-158">Система разработана с ошибкой в виду, и приложение может по-прежнему работать, даже в том случае, если происходит сбой определенных служб.</span><span class="sxs-lookup"><span data-stu-id="e61c0-158">The system is designed with failure in mind, and the app may still run even when certain services fail.</span></span>

<span data-ttu-id="e61c0-159">Микрослужбы не нужно быть взаимоисключающими, чтобы другие подходы к архитектуре.</span><span class="sxs-lookup"><span data-stu-id="e61c0-159">Microservices don't have to be mutually exclusive to other architecture approaches.</span></span> <span data-ttu-id="e61c0-160">Например в N-уровневой архитектуре может использовать микрослужб для среднего уровня.</span><span class="sxs-lookup"><span data-stu-id="e61c0-160">For example, an N-Tier architecture may use microservices for the middle tier.</span></span> <span data-ttu-id="e61c0-161">Это также можно реализовать различными способами, включая виртуальные каталоги на узлах IIS к контейнерам микрослужб.</span><span class="sxs-lookup"><span data-stu-id="e61c0-161">It's also possible to implement microservices in a variety of ways, from virtual directories on IIS hosts to containers.</span></span> <span data-ttu-id="e61c0-162">Характеристик микрослужб, делает их особенно идеальным для бессерверной реализаций.</span><span class="sxs-lookup"><span data-stu-id="e61c0-162">The characteristics of microservices make them especially ideal for serverless implementations.</span></span>

![Архитектура микрослужб](./media/microservices-architecture.png)

<span data-ttu-id="e61c0-164">Ниже перечислены преимущества архитектуры микрослужб.</span><span class="sxs-lookup"><span data-stu-id="e61c0-164">The pros of microservices architectures include:</span></span>

* <span data-ttu-id="e61c0-165">Рефакторинг изолируется часто к одному экземпляру службы.</span><span class="sxs-lookup"><span data-stu-id="e61c0-165">Refactoring is often isolated to a single service.</span></span>
* <span data-ttu-id="e61c0-166">Службы могут обновляться независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="e61c0-166">Services can be upgraded independently of each other.</span></span>
* <span data-ttu-id="e61c0-167">Чтобы потребности отдельных служб, можно оптимизировать устойчивости и гибкости.</span><span class="sxs-lookup"><span data-stu-id="e61c0-167">Resiliency and elasticity can be tuned to the demands of individual services.</span></span>
* <span data-ttu-id="e61c0-168">Разработки может произойти в параллельном режиме для различных команд и платформ.</span><span class="sxs-lookup"><span data-stu-id="e61c0-168">Development can happen in parallel across disparate teams and platforms.</span></span>
* <span data-ttu-id="e61c0-169">Стало проще создавать комплексные тесты для изолированной службы.</span><span class="sxs-lookup"><span data-stu-id="e61c0-169">It's easier to write comprehensive tests for isolated services.</span></span>

<span data-ttu-id="e61c0-170">Микрослужбы в состав собственных задач, включая:</span><span class="sxs-lookup"><span data-stu-id="e61c0-170">Microservices come with their own challenges, including:</span></span>

* <span data-ttu-id="e61c0-171">Определение, какие службы доступны и способах их вызова.</span><span class="sxs-lookup"><span data-stu-id="e61c0-171">Determining what services are available and how to call them.</span></span>
* <span data-ttu-id="e61c0-172">Управление жизненным циклом службы.</span><span class="sxs-lookup"><span data-stu-id="e61c0-172">Managing the lifecycle of services.</span></span>
* <span data-ttu-id="e61c0-173">Понимание того, как службы взаимодействуют в приложение в целом.</span><span class="sxs-lookup"><span data-stu-id="e61c0-173">Understanding how services fit together in the overall application.</span></span>
* <span data-ttu-id="e61c0-174">Вызовы между службами разрозненных тестирование всей системы.</span><span class="sxs-lookup"><span data-stu-id="e61c0-174">Full system testing of calls made across disparate services.</span></span>

<span data-ttu-id="e61c0-175">В конечном счете существуют решения, чтобы удовлетворить все эти проблемы, включая освоение преимущества бессерверных приложений, которые рассматриваются в более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="e61c0-175">Ultimately there are solutions to address all of these challenges, including tapping into the benefits of serverless that are discussed later.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e61c0-176">[Назад](index.md)
>[Вперед](architecture-deployment-approaches.md)</span><span class="sxs-lookup"><span data-stu-id="e61c0-176">[Previous](index.md)
[Next](architecture-deployment-approaches.md)</span></span>