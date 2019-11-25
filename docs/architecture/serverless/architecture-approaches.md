---
title: 'Подходы к реализации архитектуры: бессерверные приложения'
description: Общие сведения о подходах к реализации архитектуры для создания облачных корпоративных приложений — от n-уровневой архитектуры до бессерверных решений.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 74de96bef48f16ced4adf82855a740aa0afcdf1d
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2019
ms.locfileid: "72522897"
---
# <a name="architecture-approaches"></a><span data-ttu-id="6921b-103">Подходы к архитектуре</span><span class="sxs-lookup"><span data-stu-id="6921b-103">Architecture approaches</span></span>

<span data-ttu-id="6921b-104">Понимание имеющихся подходов к созданию архитектуры корпоративных приложений помогает прояснить роль, которую играют бессерверные приложения.</span><span class="sxs-lookup"><span data-stu-id="6921b-104">Understanding existing approaches to architecting enterprise apps helps clarify the role played by serverless.</span></span> <span data-ttu-id="6921b-105">Существует множество подходов и шаблонов, которые развивались в течение десятков лет разработки программного обеспечения. Каждый из них обладает своими достоинствами и недостатками.</span><span class="sxs-lookup"><span data-stu-id="6921b-105">There are many approaches and patterns that evolved over decades of software development, and all have their own pros and cons.</span></span> <span data-ttu-id="6921b-106">Во многих случаях окончательное решение может заключаться не в выборе одного подхода, а в объединении нескольких подходов.</span><span class="sxs-lookup"><span data-stu-id="6921b-106">In many cases, the ultimate solution may not involve deciding on a single approach but may integrate several approaches.</span></span> <span data-ttu-id="6921b-107">Сценарии миграции часто подразумевают переход от одного типа реализации архитектуры к другому с помощью гибридного подхода.</span><span class="sxs-lookup"><span data-stu-id="6921b-107">Migration scenarios often involve shifting from one architecture approach to another through a hybrid approach.</span></span>

<span data-ttu-id="6921b-108">В этой главе представлен обзор как логических, так и физических шаблонов архитектуры для корпоративных приложений.</span><span class="sxs-lookup"><span data-stu-id="6921b-108">This chapter provides an overview of both logical and physical architecture patterns for enterprise applications.</span></span>

## <a name="architecture-patterns"></a><span data-ttu-id="6921b-109">Шаблоны архитектуры</span><span class="sxs-lookup"><span data-stu-id="6921b-109">Architecture patterns</span></span>

<span data-ttu-id="6921b-110">Современные бизнес-приложения используют различные шаблоны архитектуры.</span><span class="sxs-lookup"><span data-stu-id="6921b-110">Modern business applications follow a variety of architecture patterns.</span></span> <span data-ttu-id="6921b-111">В этом разделе представлен обзор распространенных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="6921b-111">This section represents a survey of common patterns.</span></span> <span data-ttu-id="6921b-112">Перечисленные здесь шаблоны не обязательно являются рекомендуемыми. Они иллюстрируют различные подходы.</span><span class="sxs-lookup"><span data-stu-id="6921b-112">The patterns listed here aren't necessarily all best practices, but illustrate different approaches.</span></span>

<span data-ttu-id="6921b-113">Дополнительные сведения см. в статье [Руководство по архитектуре приложений Azure](https://docs.microsoft.com/azure/architecture/guide/).</span><span class="sxs-lookup"><span data-stu-id="6921b-113">For more information, see [Azure application architecture guide](https://docs.microsoft.com/azure/architecture/guide/).</span></span>

## <a name="monoliths"></a><span data-ttu-id="6921b-114">Монолитные структуры</span><span class="sxs-lookup"><span data-stu-id="6921b-114">Monoliths</span></span>

<span data-ttu-id="6921b-115">Многие бизнес-приложения используют шаблон монолита.</span><span class="sxs-lookup"><span data-stu-id="6921b-115">Many business applications follow a monolith pattern.</span></span> <span data-ttu-id="6921b-116">Устаревшие приложения часто реализуются как монолитные.</span><span class="sxs-lookup"><span data-stu-id="6921b-116">Legacy applications are often implemented as monoliths.</span></span> <span data-ttu-id="6921b-117">В шаблоне монолита все компоненты и операции с приложением содержатся в одном развертывании.</span><span class="sxs-lookup"><span data-stu-id="6921b-117">In the monolith pattern, all application concerns are contained in a single deployment.</span></span> <span data-ttu-id="6921b-118">Все, от пользовательского интерфейса до вызовов базы данных, включается в одну и ту же базу кода.</span><span class="sxs-lookup"><span data-stu-id="6921b-118">Everything from user interface to database calls is included in the same codebase.</span></span>

![Архитектура монолитных структур](./media/monolith-architecture.png)

<span data-ttu-id="6921b-120">У этого подхода есть несколько преимуществ.</span><span class="sxs-lookup"><span data-stu-id="6921b-120">There are several advantages to the monolith approach.</span></span> <span data-ttu-id="6921b-121">Часто извлечь одну базу кода и начать работу бывает легко.</span><span class="sxs-lookup"><span data-stu-id="6921b-121">It's often easy to pull down a single code base and start working.</span></span> <span data-ttu-id="6921b-122">Время перехода к рабочей среде может быть меньше, а создание тестовых сред реализуется просто, как и предоставление новой копии.</span><span class="sxs-lookup"><span data-stu-id="6921b-122">Ramp up time may be less, and creating test environments is as simple as providing a new copy.</span></span> <span data-ttu-id="6921b-123">Монолит можно спроектировать таким образом, чтобы он включал в себя несколько компонентов и приложений.</span><span class="sxs-lookup"><span data-stu-id="6921b-123">The monolith may be designed to include multiple components and applications.</span></span>

<span data-ttu-id="6921b-124">К сожалению, при использовании шаблона монолита, как правило, требуется разделение при масштабировании.</span><span class="sxs-lookup"><span data-stu-id="6921b-124">Unfortunately, the monolith pattern tends to break down at scale.</span></span> <span data-ttu-id="6921b-125">К основным недостаткам монолитного подхода относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="6921b-125">Major disadvantages of the monolith approach include:</span></span>

- <span data-ttu-id="6921b-126">Работать параллельно в одной базе кода довольно трудно.</span><span class="sxs-lookup"><span data-stu-id="6921b-126">Difficult to work in parallel in the same code base.</span></span>
- <span data-ttu-id="6921b-127">Любое изменение, каким бы простым оно ни было, требует развертывания новой версии всего приложения.</span><span class="sxs-lookup"><span data-stu-id="6921b-127">Any change, no matter how trivial, requires deploying a new version of the entire application.</span></span>
- <span data-ttu-id="6921b-128">Рефакторинг потенциально влияет на все приложение.</span><span class="sxs-lookup"><span data-stu-id="6921b-128">Refactoring potentially impacts the entire application.</span></span>
- <span data-ttu-id="6921b-129">Часто единственным решением для масштабирования является создание нескольких ресурсоемких копий монолитных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="6921b-129">Often the only solution to scale is to create multiple, resource-intensive copies of the monolith.</span></span>
- <span data-ttu-id="6921b-130">По мере расширения систем или приобретения других систем интеграция может быть затруднительной.</span><span class="sxs-lookup"><span data-stu-id="6921b-130">As systems expand or other systems are acquired, integration can be difficult.</span></span>
- <span data-ttu-id="6921b-131">Тестирование может быть затруднено из-за необходимости настройки всего монолита.</span><span class="sxs-lookup"><span data-stu-id="6921b-131">It may be difficult to test due to the need to configure the entire monolith.</span></span>
- <span data-ttu-id="6921b-132">Повторное использование кода является сложной задачей, и часто другие приложения в конечном итоге имеют собственные копии кода.</span><span class="sxs-lookup"><span data-stu-id="6921b-132">Code reuse is challenging and often other apps end up having their own copies of code.</span></span>

<span data-ttu-id="6921b-133">Многие компании рассматривают облако как возможность миграции монолитных приложений, а также их рефакторинга на более удобные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="6921b-133">Many businesses look to the cloud as an opportunity to migrate monolith applications and at the same time refactor them to more usable patterns.</span></span> <span data-ttu-id="6921b-134">Общепринятой практикой является разбиение отдельных приложений и компонентов, чтобы они поддерживались, развертывались и масштабировались отдельно.</span><span class="sxs-lookup"><span data-stu-id="6921b-134">It's common to break out the individual applications and components to allow them to be maintained, deployed, and scaled separately.</span></span>

## <a name="n-layer-applications"></a><span data-ttu-id="6921b-135">N-уровневые приложения</span><span class="sxs-lookup"><span data-stu-id="6921b-135">N-Layer applications</span></span>

<span data-ttu-id="6921b-136">N-уровневое приложение разделяет логику приложения на определенные слои,</span><span class="sxs-lookup"><span data-stu-id="6921b-136">N-layer application partition application logic into specific layers.</span></span> <span data-ttu-id="6921b-137">наиболее распространенные из которых:</span><span class="sxs-lookup"><span data-stu-id="6921b-137">The most common layers include:</span></span>

- <span data-ttu-id="6921b-138">Пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="6921b-138">User interface</span></span>
- <span data-ttu-id="6921b-139">бизнес-логика;</span><span class="sxs-lookup"><span data-stu-id="6921b-139">Business logic</span></span>
- <span data-ttu-id="6921b-140">Доступ к данным</span><span class="sxs-lookup"><span data-stu-id="6921b-140">Data access</span></span>

<span data-ttu-id="6921b-141">Другие слои могут включать в себя ПО промежуточного слоя, пакетную обработку и API.</span><span class="sxs-lookup"><span data-stu-id="6921b-141">Other layers may include middleware, batch processing, and API.</span></span> <span data-ttu-id="6921b-142">Важно отметить, что слои являются логическими.</span><span class="sxs-lookup"><span data-stu-id="6921b-142">It's important to note the layers are logical.</span></span> <span data-ttu-id="6921b-143">Хотя они разрабатываются изолированно, их можно развернуть на одной целевой платформе.</span><span class="sxs-lookup"><span data-stu-id="6921b-143">Although they're developed in isolation, they may all be deployed to the same target platform.</span></span>

![N-уровневая архитектура](./media/n-layer-architecture.png)

<span data-ttu-id="6921b-145">У подхода n-уровневой архитектуры есть несколько преимуществ:</span><span class="sxs-lookup"><span data-stu-id="6921b-145">There are several advantages to the N-Layer approach, including:</span></span>

- <span data-ttu-id="6921b-146">Рефакторинг выполняется изолированно для слоя.</span><span class="sxs-lookup"><span data-stu-id="6921b-146">Refactoring is isolated to a layer.</span></span>
- <span data-ttu-id="6921b-147">Команды могут независимо создавать, тестировать, развертывать и обслуживать отдельные слои.</span><span class="sxs-lookup"><span data-stu-id="6921b-147">Teams can independently build, test, deploy, and maintain separate layers.</span></span>
- <span data-ttu-id="6921b-148">Слои можно переключать, например, уровень данных может обращаться к нескольким базам данных без необходимости внесения изменений в слой пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6921b-148">Layers can be swapped out, for example the data layer may access multiple databases without requiring changes to the UI layer.</span></span>

<span data-ttu-id="6921b-149">Бессерверный интерфейс можно использовать для реализации одного или нескольких уровней.</span><span class="sxs-lookup"><span data-stu-id="6921b-149">Serverless may be used to implement one or more layers.</span></span>

## <a name="microservices"></a><span data-ttu-id="6921b-150">Микрослужбы</span><span class="sxs-lookup"><span data-stu-id="6921b-150">Microservices</span></span>

<span data-ttu-id="6921b-151">Архитектуры с **[микрослужбами](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** обладают следующими общими характеристиками:</span><span class="sxs-lookup"><span data-stu-id="6921b-151">**[Microservices](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** architectures contain common characteristics that include:</span></span>

- <span data-ttu-id="6921b-152">Приложения состоят из нескольких небольших служб.</span><span class="sxs-lookup"><span data-stu-id="6921b-152">Applications are composed of several small services.</span></span>
- <span data-ttu-id="6921b-153">Каждая служба работает в своем собственном процессе.</span><span class="sxs-lookup"><span data-stu-id="6921b-153">Each service runs in its own process.</span></span>
- <span data-ttu-id="6921b-154">Службы согласовываются с предметными областями бизнеса.</span><span class="sxs-lookup"><span data-stu-id="6921b-154">Services are aligned around business domains.</span></span>
- <span data-ttu-id="6921b-155">Службы обмениваются данными через упрощенные API, обычно используя HTTP в качестве транспортного протокола.</span><span class="sxs-lookup"><span data-stu-id="6921b-155">Services communicate over lightweight APIs, typically using HTTP as the transport.</span></span>
- <span data-ttu-id="6921b-156">Службы можно развертывать и обновлять независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="6921b-156">Services can be deployed and upgraded independently.</span></span>
- <span data-ttu-id="6921b-157">Службы не зависят от одного хранилища данных.</span><span class="sxs-lookup"><span data-stu-id="6921b-157">Services aren't dependent on a single data store.</span></span>
- <span data-ttu-id="6921b-158">Система разработана с учетом сбоев, и приложение может работать даже в случае сбоя определенных служб.</span><span class="sxs-lookup"><span data-stu-id="6921b-158">The system is designed with failure in mind, and the app may still run even when certain services fail.</span></span>

<span data-ttu-id="6921b-159">Микрослужбы не обязательно должны быть взаимоисключающими по отношению к другим подходам к архитектуре.</span><span class="sxs-lookup"><span data-stu-id="6921b-159">Microservices don't have to be mutually exclusive to other architecture approaches.</span></span> <span data-ttu-id="6921b-160">Например, n-уровневая архитектура может использовать микрослужбы для среднего уровня.</span><span class="sxs-lookup"><span data-stu-id="6921b-160">For example, an N-Tier architecture may use microservices for the middle tier.</span></span> <span data-ttu-id="6921b-161">Микрослужбы также можно реализовать различными способами — от виртуальных каталогов на узлах IIS до контейнеров.</span><span class="sxs-lookup"><span data-stu-id="6921b-161">It's also possible to implement microservices in a variety of ways, from virtual directories on IIS hosts to containers.</span></span> <span data-ttu-id="6921b-162">Благодаря характеристикам микрослужб они практически идеальны для бессерверных реализаций.</span><span class="sxs-lookup"><span data-stu-id="6921b-162">The characteristics of microservices make them especially ideal for serverless implementations.</span></span>

![Архитектура микрослужб](./media/microservices-architecture.png)

<span data-ttu-id="6921b-164">Архитектуры с микрослужбами обладают следующими преимуществами:</span><span class="sxs-lookup"><span data-stu-id="6921b-164">The pros of microservices architectures include:</span></span>

- <span data-ttu-id="6921b-165">Рефакторинг часто выполняется только для одной службы.</span><span class="sxs-lookup"><span data-stu-id="6921b-165">Refactoring is often isolated to a single service.</span></span>
- <span data-ttu-id="6921b-166">Службы можно обновлять независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="6921b-166">Services can be upgraded independently of each other.</span></span>
- <span data-ttu-id="6921b-167">Устойчивость и эластичность можно настроить в соответствии с требованиями отдельных служб.</span><span class="sxs-lookup"><span data-stu-id="6921b-167">Resiliency and elasticity can be tuned to the demands of individual services.</span></span>
- <span data-ttu-id="6921b-168">Разработка может выполняться параллельно различными командами на разных платформах.</span><span class="sxs-lookup"><span data-stu-id="6921b-168">Development can happen in parallel across disparate teams and platforms.</span></span>
- <span data-ttu-id="6921b-169">Проще писать комплексные тесты для изолированных служб.</span><span class="sxs-lookup"><span data-stu-id="6921b-169">It's easier to write comprehensive tests for isolated services.</span></span>

<span data-ttu-id="6921b-170">Микрослужбы имеют свои собственные сложности, в том числе:</span><span class="sxs-lookup"><span data-stu-id="6921b-170">Microservices come with their own challenges, including:</span></span>

- <span data-ttu-id="6921b-171">Определение доступных служб и способа их вызова.</span><span class="sxs-lookup"><span data-stu-id="6921b-171">Determining what services are available and how to call them.</span></span>
- <span data-ttu-id="6921b-172">Управление жизненным циклом служб.</span><span class="sxs-lookup"><span data-stu-id="6921b-172">Managing the lifecycle of services.</span></span>
- <span data-ttu-id="6921b-173">Необходимость понимания того, как службы объединяются в общем приложении.</span><span class="sxs-lookup"><span data-stu-id="6921b-173">Understanding how services fit together in the overall application.</span></span>
- <span data-ttu-id="6921b-174">Требуется полное системное тестирование вызовов, выполненных в разнородных службах.</span><span class="sxs-lookup"><span data-stu-id="6921b-174">Full system testing of calls made across disparate services.</span></span>

<span data-ttu-id="6921b-175">Существуют решения для устранения всех этих проблем, включая использование преимуществ бессерверной архитектуры, которые будут рассмотрены позже.</span><span class="sxs-lookup"><span data-stu-id="6921b-175">Ultimately there are solutions to address all of these challenges, including tapping into the benefits of serverless that are discussed later.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6921b-176">[Назад](index.md)
>[Вперед](architecture-deployment-approaches.md)</span><span class="sxs-lookup"><span data-stu-id="6921b-176">[Previous](index.md)
[Next](architecture-deployment-approaches.md)</span></span>
