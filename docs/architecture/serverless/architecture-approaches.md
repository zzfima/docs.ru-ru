---
title: Подходы к архитектуре — бессерверные приложения
description: Введение в архитектурные подходы для создания облачных корпоративных приложений, от N-уровневой архитектуры до бессерверных.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 74de96bef48f16ced4adf82855a740aa0afcdf1d
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522897"
---
# <a name="architecture-approaches"></a><span data-ttu-id="4864f-103">Подходы к архитектуре</span><span class="sxs-lookup"><span data-stu-id="4864f-103">Architecture approaches</span></span>

<span data-ttu-id="4864f-104">Понимание существующих подходов к проектированию корпоративных приложений помогает прояснить роль, которая воспроизводится бессерверным.</span><span class="sxs-lookup"><span data-stu-id="4864f-104">Understanding existing approaches to architecting enterprise apps helps clarify the role played by serverless.</span></span> <span data-ttu-id="4864f-105">Существует множество подходов и шаблонов, которые развивались в течение десятков лет разработки программного обеспечения и имеют свои собственные достоинства и недостатки.</span><span class="sxs-lookup"><span data-stu-id="4864f-105">There are many approaches and patterns that evolved over decades of software development, and all have their own pros and cons.</span></span> <span data-ttu-id="4864f-106">Во многих случаях решение с одним подходом может не содержать решения, но может интегрировать несколько подходов.</span><span class="sxs-lookup"><span data-stu-id="4864f-106">In many cases, the ultimate solution may not involve deciding on a single approach but may integrate several approaches.</span></span> <span data-ttu-id="4864f-107">Сценарии миграции часто подразумевают переход от одного подхода архитектуры к другому с помощью гибридного подхода.</span><span class="sxs-lookup"><span data-stu-id="4864f-107">Migration scenarios often involve shifting from one architecture approach to another through a hybrid approach.</span></span>

<span data-ttu-id="4864f-108">В этой главе представлен обзор как логических, так и физических шаблонов архитектуры для корпоративных приложений.</span><span class="sxs-lookup"><span data-stu-id="4864f-108">This chapter provides an overview of both logical and physical architecture patterns for enterprise applications.</span></span>

## <a name="architecture-patterns"></a><span data-ttu-id="4864f-109">Шаблоны архитектуры</span><span class="sxs-lookup"><span data-stu-id="4864f-109">Architecture patterns</span></span>

<span data-ttu-id="4864f-110">Современные бизнес-приложения используют различные шаблоны архитектуры.</span><span class="sxs-lookup"><span data-stu-id="4864f-110">Modern business applications follow a variety of architecture patterns.</span></span> <span data-ttu-id="4864f-111">В этом разделе представлен опрос распространенных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="4864f-111">This section represents a survey of common patterns.</span></span> <span data-ttu-id="4864f-112">Приведенные здесь шаблоны не обязательно являются всеми рекомендациями, но иллюстрируют различные подходы.</span><span class="sxs-lookup"><span data-stu-id="4864f-112">The patterns listed here aren't necessarily all best practices, but illustrate different approaches.</span></span>

<span data-ttu-id="4864f-113">Дополнительные сведения см. в статье [рекомендации по архитектуре приложений Azure](https://docs.microsoft.com/azure/architecture/guide/).</span><span class="sxs-lookup"><span data-stu-id="4864f-113">For more information, see [Azure application architecture guide](https://docs.microsoft.com/azure/architecture/guide/).</span></span>

## <a name="monoliths"></a><span data-ttu-id="4864f-114">Монолитных структур</span><span class="sxs-lookup"><span data-stu-id="4864f-114">Monoliths</span></span>

<span data-ttu-id="4864f-115">Многие бизнес-приложения используют монолитный шаблон.</span><span class="sxs-lookup"><span data-stu-id="4864f-115">Many business applications follow a monolith pattern.</span></span> <span data-ttu-id="4864f-116">Устаревшие приложения часто реализуются как монолитные.</span><span class="sxs-lookup"><span data-stu-id="4864f-116">Legacy applications are often implemented as monoliths.</span></span> <span data-ttu-id="4864f-117">В шаблоне монолита все проблемы с приложениями содержатся в одном развертывании.</span><span class="sxs-lookup"><span data-stu-id="4864f-117">In the monolith pattern, all application concerns are contained in a single deployment.</span></span> <span data-ttu-id="4864f-118">Все, от пользовательского интерфейса до вызовов базы данных, включается в одну и ту же базу кода.</span><span class="sxs-lookup"><span data-stu-id="4864f-118">Everything from user interface to database calls is included in the same codebase.</span></span>

![Монолитная архитектура](./media/monolith-architecture.png)

<span data-ttu-id="4864f-120">Для монолитного подхода существует несколько преимуществ.</span><span class="sxs-lookup"><span data-stu-id="4864f-120">There are several advantages to the monolith approach.</span></span> <span data-ttu-id="4864f-121">Часто бывает легко извлечь одну базу кода и начать работу.</span><span class="sxs-lookup"><span data-stu-id="4864f-121">It's often easy to pull down a single code base and start working.</span></span> <span data-ttu-id="4864f-122">Увеличение времени увеличения может быть меньше, а создание тестовых сред — так же просто, как предоставление новой копии.</span><span class="sxs-lookup"><span data-stu-id="4864f-122">Ramp up time may be less, and creating test environments is as simple as providing a new copy.</span></span> <span data-ttu-id="4864f-123">Монолит может быть разработан для включения нескольких компонентов и приложений.</span><span class="sxs-lookup"><span data-stu-id="4864f-123">The monolith may be designed to include multiple components and applications.</span></span>

<span data-ttu-id="4864f-124">К сожалению, шаблон монолита, как правило, разбивается на шкалу.</span><span class="sxs-lookup"><span data-stu-id="4864f-124">Unfortunately, the monolith pattern tends to break down at scale.</span></span> <span data-ttu-id="4864f-125">К основным недостаткам монолитного подхода относятся:</span><span class="sxs-lookup"><span data-stu-id="4864f-125">Major disadvantages of the monolith approach include:</span></span>

- <span data-ttu-id="4864f-126">Трудно работать параллельно в одной базе кода.</span><span class="sxs-lookup"><span data-stu-id="4864f-126">Difficult to work in parallel in the same code base.</span></span>
- <span data-ttu-id="4864f-127">Любое изменение, независимо от того, насколько тривиальны, требует развертывания новой версии всего приложения.</span><span class="sxs-lookup"><span data-stu-id="4864f-127">Any change, no matter how trivial, requires deploying a new version of the entire application.</span></span>
- <span data-ttu-id="4864f-128">Рефакторинг потенциально влияет на все приложение.</span><span class="sxs-lookup"><span data-stu-id="4864f-128">Refactoring potentially impacts the entire application.</span></span>
- <span data-ttu-id="4864f-129">Часто единственным решением для масштабирования является создание нескольких ресурсоемких копий монолитных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="4864f-129">Often the only solution to scale is to create multiple, resource-intensive copies of the monolith.</span></span>
- <span data-ttu-id="4864f-130">По мере приобретения систем или других систем интеграция может оказаться сложной.</span><span class="sxs-lookup"><span data-stu-id="4864f-130">As systems expand or other systems are acquired, integration can be difficult.</span></span>
- <span data-ttu-id="4864f-131">Тестирование может быть трудно тестировать из-за необходимости настройки всего монолита.</span><span class="sxs-lookup"><span data-stu-id="4864f-131">It may be difficult to test due to the need to configure the entire monolith.</span></span>
- <span data-ttu-id="4864f-132">Повторное использование кода — это сложная задача, и часто другие приложения имеют собственные копии кода.</span><span class="sxs-lookup"><span data-stu-id="4864f-132">Code reuse is challenging and often other apps end up having their own copies of code.</span></span>

<span data-ttu-id="4864f-133">Многие компании ищут облако в качестве возможности для переноса монолитных приложений и в то же время оптимизируют их до более удобных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="4864f-133">Many businesses look to the cloud as an opportunity to migrate monolith applications and at the same time refactor them to more usable patterns.</span></span> <span data-ttu-id="4864f-134">Обычно вы можете разбить отдельные приложения и компоненты, чтобы они поддерживались, развертываться и масштабироваться отдельно.</span><span class="sxs-lookup"><span data-stu-id="4864f-134">It's common to break out the individual applications and components to allow them to be maintained, deployed, and scaled separately.</span></span>

## <a name="n-layer-applications"></a><span data-ttu-id="4864f-135">N-уровневые приложения</span><span class="sxs-lookup"><span data-stu-id="4864f-135">N-Layer applications</span></span>

<span data-ttu-id="4864f-136">N-уровневое приложение разделяет логику приложения на определенные слои.</span><span class="sxs-lookup"><span data-stu-id="4864f-136">N-layer application partition application logic into specific layers.</span></span> <span data-ttu-id="4864f-137">Ниже перечислены наиболее распространенные слои.</span><span class="sxs-lookup"><span data-stu-id="4864f-137">The most common layers include:</span></span>

- <span data-ttu-id="4864f-138">Пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="4864f-138">User interface</span></span>
- <span data-ttu-id="4864f-139">Бизнес-логика</span><span class="sxs-lookup"><span data-stu-id="4864f-139">Business logic</span></span>
- <span data-ttu-id="4864f-140">Доступ к данным</span><span class="sxs-lookup"><span data-stu-id="4864f-140">Data access</span></span>

<span data-ttu-id="4864f-141">Другие слои могут включать по промежуточного слоя, пакетную обработку и API.</span><span class="sxs-lookup"><span data-stu-id="4864f-141">Other layers may include middleware, batch processing, and API.</span></span> <span data-ttu-id="4864f-142">Важно отметить, что слои являются логическими.</span><span class="sxs-lookup"><span data-stu-id="4864f-142">It's important to note the layers are logical.</span></span> <span data-ttu-id="4864f-143">Хотя они разрабатываются изолированно, их можно развертывать на одной целевой платформе.</span><span class="sxs-lookup"><span data-stu-id="4864f-143">Although they're developed in isolation, they may all be deployed to the same target platform.</span></span>

![N-уровневая архитектура](./media/n-layer-architecture.png)

<span data-ttu-id="4864f-145">Существует несколько преимуществ подхода N-Layer, в том числе:</span><span class="sxs-lookup"><span data-stu-id="4864f-145">There are several advantages to the N-Layer approach, including:</span></span>

- <span data-ttu-id="4864f-146">Рефакторинг является изолированным для слоя.</span><span class="sxs-lookup"><span data-stu-id="4864f-146">Refactoring is isolated to a layer.</span></span>
- <span data-ttu-id="4864f-147">Команды могут независимо создавать, тестировать, развертывать и обслуживать отдельные слои.</span><span class="sxs-lookup"><span data-stu-id="4864f-147">Teams can independently build, test, deploy, and maintain separate layers.</span></span>
- <span data-ttu-id="4864f-148">Слои можно переключать, например, уровень данных может обращаться к нескольким базам данных, не требуя внесения изменений в слой пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4864f-148">Layers can be swapped out, for example the data layer may access multiple databases without requiring changes to the UI layer.</span></span>

<span data-ttu-id="4864f-149">Бессерверный интерфейс можно использовать для реализации одного или нескольких уровней.</span><span class="sxs-lookup"><span data-stu-id="4864f-149">Serverless may be used to implement one or more layers.</span></span>

## <a name="microservices"></a><span data-ttu-id="4864f-150">Микрослужбы</span><span class="sxs-lookup"><span data-stu-id="4864f-150">Microservices</span></span>

<span data-ttu-id="4864f-151">Архитектуры **[микрослужб](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** содержат общие характеристики, которые включают:</span><span class="sxs-lookup"><span data-stu-id="4864f-151">**[Microservices](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** architectures contain common characteristics that include:</span></span>

- <span data-ttu-id="4864f-152">Приложения состоят из нескольких небольших служб.</span><span class="sxs-lookup"><span data-stu-id="4864f-152">Applications are composed of several small services.</span></span>
- <span data-ttu-id="4864f-153">Каждая служба выполняется в собственном процессе.</span><span class="sxs-lookup"><span data-stu-id="4864f-153">Each service runs in its own process.</span></span>
- <span data-ttu-id="4864f-154">Службы обрабатываются в соответствии с доменами бизнеса.</span><span class="sxs-lookup"><span data-stu-id="4864f-154">Services are aligned around business domains.</span></span>
- <span data-ttu-id="4864f-155">Службы обмениваются данными через упрощенные API, обычно использующие HTTP в качестве транспорта.</span><span class="sxs-lookup"><span data-stu-id="4864f-155">Services communicate over lightweight APIs, typically using HTTP as the transport.</span></span>
- <span data-ttu-id="4864f-156">Службы можно развертывать и обновлять независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="4864f-156">Services can be deployed and upgraded independently.</span></span>
- <span data-ttu-id="4864f-157">Службы не зависят от одного хранилища данных.</span><span class="sxs-lookup"><span data-stu-id="4864f-157">Services aren't dependent on a single data store.</span></span>
- <span data-ttu-id="4864f-158">Система разработана с учетом сбоев, и приложение может работать даже в случае сбоя определенных служб.</span><span class="sxs-lookup"><span data-stu-id="4864f-158">The system is designed with failure in mind, and the app may still run even when certain services fail.</span></span>

<span data-ttu-id="4864f-159">Микрослужбы не обязательно должны быть взаимоисключающими с другими подходами к архитектуре.</span><span class="sxs-lookup"><span data-stu-id="4864f-159">Microservices don't have to be mutually exclusive to other architecture approaches.</span></span> <span data-ttu-id="4864f-160">Например, N-уровневая архитектура может использовать микрослужбы для среднего уровня.</span><span class="sxs-lookup"><span data-stu-id="4864f-160">For example, an N-Tier architecture may use microservices for the middle tier.</span></span> <span data-ttu-id="4864f-161">Микрослужбы также можно реализовать различными способами — от виртуальных каталогов на узлах IIS до контейнеров.</span><span class="sxs-lookup"><span data-stu-id="4864f-161">It's also possible to implement microservices in a variety of ways, from virtual directories on IIS hosts to containers.</span></span> <span data-ttu-id="4864f-162">Характеристики микрослужб делают их особенно идеальными для бессерверных реализаций.</span><span class="sxs-lookup"><span data-stu-id="4864f-162">The characteristics of microservices make them especially ideal for serverless implementations.</span></span>

![Архитектура микрослужб](./media/microservices-architecture.png)

<span data-ttu-id="4864f-164">К преимуществам архитектуры микрослужб относятся:</span><span class="sxs-lookup"><span data-stu-id="4864f-164">The pros of microservices architectures include:</span></span>

- <span data-ttu-id="4864f-165">Рефакторинг часто является изолированным для одной службы.</span><span class="sxs-lookup"><span data-stu-id="4864f-165">Refactoring is often isolated to a single service.</span></span>
- <span data-ttu-id="4864f-166">Службы можно обновлять независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="4864f-166">Services can be upgraded independently of each other.</span></span>
- <span data-ttu-id="4864f-167">Устойчивость и эластичность могут быть настроены на требования отдельных служб.</span><span class="sxs-lookup"><span data-stu-id="4864f-167">Resiliency and elasticity can be tuned to the demands of individual services.</span></span>
- <span data-ttu-id="4864f-168">Разработка может выполняться параллельно на различных командах и платформах.</span><span class="sxs-lookup"><span data-stu-id="4864f-168">Development can happen in parallel across disparate teams and platforms.</span></span>
- <span data-ttu-id="4864f-169">Проще писать комплексные тесты для изолированных служб.</span><span class="sxs-lookup"><span data-stu-id="4864f-169">It's easier to write comprehensive tests for isolated services.</span></span>

<span data-ttu-id="4864f-170">Микрослужбы поставляются с собственными проблемами, в том числе:</span><span class="sxs-lookup"><span data-stu-id="4864f-170">Microservices come with their own challenges, including:</span></span>

- <span data-ttu-id="4864f-171">Определение доступных служб и их вызов.</span><span class="sxs-lookup"><span data-stu-id="4864f-171">Determining what services are available and how to call them.</span></span>
- <span data-ttu-id="4864f-172">Управление жизненным циклом служб.</span><span class="sxs-lookup"><span data-stu-id="4864f-172">Managing the lifecycle of services.</span></span>
- <span data-ttu-id="4864f-173">Понимание того, как службы объединяются в общем приложении.</span><span class="sxs-lookup"><span data-stu-id="4864f-173">Understanding how services fit together in the overall application.</span></span>
- <span data-ttu-id="4864f-174">Полное тестирование системы вызовов, выполненных в разнородных службах.</span><span class="sxs-lookup"><span data-stu-id="4864f-174">Full system testing of calls made across disparate services.</span></span>

<span data-ttu-id="4864f-175">В конечном итоге существуют решения, позволяющие устранить все эти проблемы, включая преимущества бессерверных решений, которые обсуждаются далее.</span><span class="sxs-lookup"><span data-stu-id="4864f-175">Ultimately there are solutions to address all of these challenges, including tapping into the benefits of serverless that are discussed later.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4864f-176">[Назад](index.md)
>[Вперед](architecture-deployment-approaches.md)</span><span class="sxs-lookup"><span data-stu-id="4864f-176">[Previous](index.md)
[Next](architecture-deployment-approaches.md)</span></span>
