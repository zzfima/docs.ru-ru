---
title: "Пошаговые руководства и технические получить обзор работы"
description: "Модернизировать существующие приложения .NET с облако Azure и контейнеров Windows | Пошаговые руководства и технические получить обзор работы"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6a2abda3949c1fffc4d731b01e35e58e7c56dac0
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2018
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="4a202-103">Пошаговые руководства и технические получить обзор работы</span><span class="sxs-lookup"><span data-stu-id="4a202-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="4a202-104">Для ограничения размера эта электронная книга, дополнительную техническую документацию и полный пошаговые руководства были доступны в репозитории GitHub.</span><span class="sxs-lookup"><span data-stu-id="4a202-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="4a202-105">Online ряд пошаговых руководств, описанный в этой главе описываются пошаговые установки нескольких сред, которые основаны на контейнеры Windows и развертывания в Azure.</span><span class="sxs-lookup"><span data-stu-id="4a202-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="4a202-106">Что каждого пошагового руководства о его целями и высокоуровневые концепции и предоставляет схему задачи, которые участвуют в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="4a202-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="4a202-107">Вы можете получить пошаговые руководства, сами в *eShopModernizing* wiki репозитория GitHub приложений на [https://github.com/dotnet-architecture/eShopModernizing/wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki).</span><span class="sxs-lookup"><span data-stu-id="4a202-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at [https://github.com/dotnet-architecture/eShopModernizing/wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki).</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="4a202-108">Список примеров технические</span><span class="sxs-lookup"><span data-stu-id="4a202-108">Technical walkthrough list</span></span>

<span data-ttu-id="4a202-109">Следующие пошаговые руководства работы get содержат согласованное и комплексное техническое руководство для образца приложения, которые можно точности прогнозов и с помощью контейнеры shift, а затем переместите с помощью нескольких вариантов развертывания в Azure.</span><span class="sxs-lookup"><span data-stu-id="4a202-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="4a202-110">Для каждой из указанных ниже пошаговых руководствах используется новый образец eShopLegacy и eShopModernizing приложений, которые можно найти на github на сайте [https://github.com/dotnet-architecture/eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="4a202-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at [https://github.com/dotnet-architecture/eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

- <span data-ttu-id="4a202-111">**Обзор приложений прежних версий eShop**</span><span class="sxs-lookup"><span data-stu-id="4a202-111">**Tour of eShop legacy apps**</span></span>

- <span data-ttu-id="4a202-112">**Упаковываете существующие приложения .NET с помощью контейнеров Windows**</span><span class="sxs-lookup"><span data-stu-id="4a202-112">**Containerize your existing .NET applications with Windows Containers**</span></span>

- <span data-ttu-id="4a202-113">**Развертывание приложения на основе контейнеров Windows на виртуальных машинах Azure**</span><span class="sxs-lookup"><span data-stu-id="4a202-113">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="4a202-114">**Развертывание приложений на основе контейнеров Windows на Kubernetes в службе контейнера Azure**</span><span class="sxs-lookup"><span data-stu-id="4a202-114">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

- <span data-ttu-id="4a202-115">**Развернуть приложения на основе контейнеров Windows Azure Service Fabric**</span><span class="sxs-lookup"><span data-stu-id="4a202-115">**Deploy your Windows Containers-based apps to Azure Service Fabric**</span></span>

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="4a202-116">Пошаговое руководство 1: Обзор eShop приложений прежних версий</span><span class="sxs-lookup"><span data-stu-id="4a202-116">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="4a202-117">Технические руководства доступности</span><span class="sxs-lookup"><span data-stu-id="4a202-117">Technical walkthrough availability</span></span>

<span data-ttu-id="4a202-118">Полные технические пошагового руководства можно найти в репозитории GitHub eShopModernizing вики-сайте:</span><span class="sxs-lookup"><span data-stu-id="4a202-118">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="4a202-119">https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code</span><span class="sxs-lookup"><span data-stu-id="4a202-119">https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code)

### <a name="overview"></a><span data-ttu-id="4a202-120">Обзор</span><span class="sxs-lookup"><span data-stu-id="4a202-120">Overview</span></span>

<span data-ttu-id="4a202-121">В этом пошаговом руководстве можно исследовать начальной реализацию двух примеров приложений прежних версий.</span><span class="sxs-lookup"><span data-stu-id="4a202-121">In this walkthrough, you can explore the initial implementation of two sample legacy applications.</span></span> <span data-ttu-id="4a202-122">Оба образца приложения монолитные архитектуры и были созданы с помощью классической платформе ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="4a202-122">Both sample apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="4a202-123">Одно приложение на базе ASP.NET 4.x MVC; второе приложение зависит от веб-форм ASP.NET 4.x.</span><span class="sxs-lookup"><span data-stu-id="4a202-123">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span> <span data-ttu-id="4a202-124">Оба приложения находятся в [eShopModernizing в репозитории GitHub](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="4a202-124">Both applications are in the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

<span data-ttu-id="4a202-125">Можно упаковываете оба образца приложения, подобно тому, как можно упаковываете классические [Windows Communication Foundation](../../framework/wcf/whats-wcf.md) приложения (WCF) в качестве классического приложения.</span><span class="sxs-lookup"><span data-stu-id="4a202-125">You can containerize both sample apps, similar to the way you can containerize a classic [Windows Communication Foundation](../../framework/wcf/whats-wcf.md) (WCF) application to be consumed as a desktop application.</span></span> <span data-ttu-id="4a202-126">Пример см. в разделе [eShopModernizingWCFWinForms](https://github.com/dotnet-architecture/eShopModernizingWCFWinForms).</span><span class="sxs-lookup"><span data-stu-id="4a202-126">For an example, see [eShopModernizingWCFWinForms](https://github.com/dotnet-architecture/eShopModernizingWCFWinForms).</span></span>

### <a name="goals"></a><span data-ttu-id="4a202-127">Цели</span><span class="sxs-lookup"><span data-stu-id="4a202-127">Goals</span></span>

<span data-ttu-id="4a202-128">Основная цель данного пошагового руководства, достаточно ознакомиться с этими приложениями и их кода и конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4a202-128">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="4a202-129">Можно настроить приложения, которые они создания и фиктивных данных без использования базы данных SQL в целях тестирования.</span><span class="sxs-lookup"><span data-stu-id="4a202-129">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="4a202-130">Это необязательная конфигурация основана на внедрение зависимостей несвязанной способом.</span><span class="sxs-lookup"><span data-stu-id="4a202-130">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario"></a><span data-ttu-id="4a202-131">Сценарий</span><span class="sxs-lookup"><span data-stu-id="4a202-131">Scenario</span></span>

<span data-ttu-id="4a202-132">Рис. 5-1 показывает простой сценарий исходного приложений прежних версий.</span><span class="sxs-lookup"><span data-stu-id="4a202-132">Figure 5-1 shows the simple scenario of the original legacy applications.</span></span>

> ![Сценарий простой архитектуры исходного прежних версий приложений](./media/image5-1.png)
>
> <span data-ttu-id="4a202-134">**Рис. 5-1**.</span><span class="sxs-lookup"><span data-stu-id="4a202-134">**Figure 5-1.**</span></span> <span data-ttu-id="4a202-135">Сценарий простой архитектуры исходного прежних версий приложений</span><span class="sxs-lookup"><span data-stu-id="4a202-135">Simple architecture scenario of the original legacy applications</span></span>

<span data-ttu-id="4a202-136">С точки зрения бизнеса домен оба приложения обеспечивают одного каталога функции управления.</span><span class="sxs-lookup"><span data-stu-id="4a202-136">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="4a202-137">Члены команды enterprise eShop будет использовать приложение для просмотра и изменения каталога продуктов.</span><span class="sxs-lookup"><span data-stu-id="4a202-137">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span> <span data-ttu-id="4a202-138">Рис. 5-2 показано на снимках экрана начального приложения.</span><span class="sxs-lookup"><span data-stu-id="4a202-138">Figure 5-2 shows the initial app screenshots.</span></span>

![Приложения ASP.NET MVC и веб-форм ASP.NET (существующих устаревших технологии)](./media/image5-2.png)

> <span data-ttu-id="4a202-140">**Рис. 5-2.**</span><span class="sxs-lookup"><span data-stu-id="4a202-140">**Figure 5-2.**</span></span> <span data-ttu-id="4a202-141">Приложения ASP.NET MVC и веб-форм ASP.NET (существующих устаревших технологии)</span><span class="sxs-lookup"><span data-stu-id="4a202-141">ASP.NET MVC and ASP.NET Web Forms applications (existing/legacy technologies)</span></span>

<span data-ttu-id="4a202-142">Это веб-приложений, которые используются для просмотра и изменения записей каталога.</span><span class="sxs-lookup"><span data-stu-id="4a202-142">These are web applications that are used to browse and modify catalog entries.</span></span> <span data-ttu-id="4a202-143">Тот факт, что оба приложения поставлять же бизнеса и функциональные возможности не просто для сравнения.</span><span class="sxs-lookup"><span data-stu-id="4a202-143">The fact that both apps deliver the same business/functional features is simply for comparison purposes.</span></span> <span data-ttu-id="4a202-144">Вы увидите аналогичный процесс изменения для приложений, созданных с помощью платформы ASP.NET MVC и веб-форм ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="4a202-144">You can see a similar modernization process for apps that were created by using the ASP.NET MVC and ASP.NET Web Forms frameworks.</span></span>

<span data-ttu-id="4a202-145">Зависимости в ASP.NET 4.x или более ранних версий (либо для MVC для веб-форм) означает, эти приложения, которые не будут работать в .NET Core, если код полностью переписан с помощью ASP.NET Core MVC.</span><span class="sxs-lookup"><span data-stu-id="4a202-145">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won't run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span> <span data-ttu-id="4a202-146">Этот пример демонстрирует точки, если вы не хотите повторно создать архитектуру или переписать код, можно упаковываете существующих приложений и по-прежнему использовать те же технологии .NET и тот же код.</span><span class="sxs-lookup"><span data-stu-id="4a202-146">This demonstrates the point that if you don't want to re-architect or rewrite code, you can containerize existing applications, and still use the same .NET technologies and the same code.</span></span> <span data-ttu-id="4a202-147">Вы увидите, как запустить такие контейнеры, без изменений для устаревшего кода приложения.</span><span class="sxs-lookup"><span data-stu-id="4a202-147">You can see how you can run applications like these in containers, without any changes to legacy code.</span></span>

### <a name="benefits"></a><span data-ttu-id="4a202-148">Преимущества</span><span class="sxs-lookup"><span data-stu-id="4a202-148">Benefits</span></span>

<span data-ttu-id="4a202-149">Преимущества этого пошагового руководства, простой: просто ознакомиться с конфигурацией код и приложения, в зависимости от внедрения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="4a202-149">The benefits of this walkthrough are simple: Just get familiar with the code and application configuration, based on dependency injection.</span></span> <span data-ttu-id="4a202-150">Затем можно поэкспериментировать с такой подход при упаковываете и развертывания в различных средах, в будущем.</span><span class="sxs-lookup"><span data-stu-id="4a202-150">Then, you can experiment with this approach when you containerize and deploy to multiple environments in the future.</span></span>

### <a name="next-steps"></a><span data-ttu-id="4a202-151">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="4a202-151">Next steps</span></span>

<span data-ttu-id="4a202-152">Это содержимое более подробное изучение на вики-сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="4a202-152">Explore this content more in-depth on the GitHub wiki:</span></span>

[<span data-ttu-id="4a202-153">https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code</span><span class="sxs-lookup"><span data-stu-id="4a202-153">https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="4a202-154">Пример 2: Упаковываете существующие приложения .NET с помощью контейнеров Windows</span><span class="sxs-lookup"><span data-stu-id="4a202-154">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="4a202-155">Технические руководства доступности</span><span class="sxs-lookup"><span data-stu-id="4a202-155">Technical walkthrough availability</span></span>

<span data-ttu-id="4a202-156">Полные технические пошагового руководства можно найти в репозитории GitHub eShopModernizing вики-сайте:</span><span class="sxs-lookup"><span data-stu-id="4a202-156">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="4a202-157">https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker</span><span class="sxs-lookup"><span data-stu-id="4a202-157">https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)

### <a name="overview"></a><span data-ttu-id="4a202-158">Обзор</span><span class="sxs-lookup"><span data-stu-id="4a202-158">Overview</span></span>

<span data-ttu-id="4a202-159">Контейнеры Windows используются для улучшения существующих приложений .NET, как и на базе MVC, веб-формы или WCF, производства, разработки и тестовой среды развертывания.</span><span class="sxs-lookup"><span data-stu-id="4a202-159">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="4a202-160">Цели</span><span class="sxs-lookup"><span data-stu-id="4a202-160">Goals</span></span>

<span data-ttu-id="4a202-161">Цель данного руководства — Показать несколько вариантов containerizing существующего приложения .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4a202-161">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="4a202-162">Можно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="4a202-162">You can:</span></span>

- <span data-ttu-id="4a202-163">Упаковываете приложение с помощью [2017 г средств Visual Studio для Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 г. или более поздней версии).</span><span class="sxs-lookup"><span data-stu-id="4a202-163">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="4a202-164">Упаковываете приложение, вручную добавив [Dockerfile](https://docs.docker.com/engine/reference/builder/), а затем с помощью [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span><span class="sxs-lookup"><span data-stu-id="4a202-164">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="4a202-165">Упаковываете приложение с помощью [Img2Docker](https://github.com/docker/communitytools-image2docker-win) инструмента (инструмент открытым исходным кодом из Docker).</span><span class="sxs-lookup"><span data-stu-id="4a202-165">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="4a202-166">В этом пошаговом руководстве уделяется средств Visual Studio 2017 г. для Docker подход, но другие два способа реализации во многом аналогичны отношении с помощью файлов Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="4a202-166">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario"></a><span data-ttu-id="4a202-167">Сценарий</span><span class="sxs-lookup"><span data-stu-id="4a202-167">Scenario</span></span>

<span data-ttu-id="4a202-168">Рис. 5-3 показан сценарий, для приложений прежних версий контейнерного eShop.</span><span class="sxs-lookup"><span data-stu-id="4a202-168">Figure 5-3 shows the scenario for containerized eShop legacy applications.</span></span>

> ![Схема упрощенной архитектуры приложений в контейнерах в среде разработки](./media/image5-3.png)
>
> <span data-ttu-id="4a202-170">**Рис.**</span><span class="sxs-lookup"><span data-stu-id="4a202-170">**Figure 5-3.**</span></span> <span data-ttu-id="4a202-171">Схема упрощенной архитектуры приложений в контейнерах в среде разработки</span><span class="sxs-lookup"><span data-stu-id="4a202-171">Simplified architecture diagram of containerized applications in a development environment</span></span>

### <a name="benefits"></a><span data-ttu-id="4a202-172">Преимущества</span><span class="sxs-lookup"><span data-stu-id="4a202-172">Benefits</span></span>

<span data-ttu-id="4a202-173">Существуют преимущества для запуска монолитные приложения в контейнере.</span><span class="sxs-lookup"><span data-stu-id="4a202-173">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="4a202-174">Во-первых можно создать изображение приложения.</span><span class="sxs-lookup"><span data-stu-id="4a202-174">First, you create an image for the application.</span></span> <span data-ttu-id="4a202-175">С этого момента каждое развертывание выполняется в той же среде.</span><span class="sxs-lookup"><span data-stu-id="4a202-175">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="4a202-176">Каждый контейнер использует ту же версию операционной системы, имеет ту же версию установить зависимости, использует ту же версию .NET framework и создается с помощью тот же процесс.</span><span class="sxs-lookup"><span data-stu-id="4a202-176">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="4a202-177">По сути вы управляете зависимости приложения с помощью образа Docker.</span><span class="sxs-lookup"><span data-stu-id="4a202-177">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="4a202-178">Зависимости перемещаются вместе с приложением при развертывании контейнеров.</span><span class="sxs-lookup"><span data-stu-id="4a202-178">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="4a202-179">Дополнительным преимуществом является разработчикам возможность выполнения приложения в среде согласованной, предоставляемая контейнеров Windows.</span><span class="sxs-lookup"><span data-stu-id="4a202-179">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="4a202-180">Проблемы, которые отображаются только в определенных версиях можно заметили немедленно, вместо распределение результатов в промежуточной или рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="4a202-180">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="4a202-181">Различия в средах разработки, членам команды разработчиков имеет меньше значения при запуске приложений в контейнерах.</span><span class="sxs-lookup"><span data-stu-id="4a202-181">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="4a202-182">Контейнерного приложения также имеют плоское кривой горизонтального масштабирования.</span><span class="sxs-lookup"><span data-stu-id="4a202-182">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="4a202-183">Контейнерного приложения позволяют имеют несколько приложений и экземпляров службы (с учетом контейнеров) в виртуальной Машины или физического компьютера, по сравнению с развертывания регулярных приложений на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4a202-183">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="4a202-184">Это приводит к более поздней версии плотность и меньше требуется ресурсов, особенно при использовании orchestrators как Kubernetes или Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="4a202-184">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes or Service Fabric.</span></span>

<span data-ttu-id="4a202-185">Создание контейнеров в ситуациях, идеальным, не требует внесения изменений в код приложения (C\#).</span><span class="sxs-lookup"><span data-stu-id="4a202-185">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="4a202-186">В большинстве случаев необходимо просто Docker развертывания метаданных файлы (файлы Dockerfile и Docker Compose).</span><span class="sxs-lookup"><span data-stu-id="4a202-186">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="4a202-187">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="4a202-187">Next steps</span></span>

<span data-ttu-id="4a202-188">Просмотр этого содержимого углубленные на вики-сайте GitHub: [https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)</span><span class="sxs-lookup"><span data-stu-id="4a202-188">Explore this content more in-depth on the GitHub wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)</span></span>

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="4a202-189">Пример 3: Развертывание приложения Windows контейнеры на виртуальных машинах Azure</span><span class="sxs-lookup"><span data-stu-id="4a202-189">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="4a202-190">Технические руководства доступности</span><span class="sxs-lookup"><span data-stu-id="4a202-190">Technical walkthrough availability</span></span>

<span data-ttu-id="4a202-191">Полные технические пошагового руководства можно найти в репозитории GitHub eShopModernizing вики-сайте:</span><span class="sxs-lookup"><span data-stu-id="4a202-191">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="4a202-192">[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))</span><span class="sxs-lookup"><span data-stu-id="4a202-192">[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))</span></span>

### <a name="overview"></a><span data-ttu-id="4a202-193">Обзор</span><span class="sxs-lookup"><span data-stu-id="4a202-193">Overview</span></span>

<span data-ttu-id="4a202-194">Развертывание на узле Docker в Windows Server 2016 виртуальной машины (VM) в Azure позволяет быстро настроить разработки, тестирования и промежуточные среды.</span><span class="sxs-lookup"><span data-stu-id="4a202-194">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="4a202-195">Он также предоставляет единый механизм для тест-инженеры или бизнес-пользователей, для проверки приложения.</span><span class="sxs-lookup"><span data-stu-id="4a202-195">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="4a202-196">Виртуальные машины также может быть допустимым Infrastucture как услуги (IaaS) рабочих средах.</span><span class="sxs-lookup"><span data-stu-id="4a202-196">VMs also can be valid Infrastucture as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="4a202-197">Цели</span><span class="sxs-lookup"><span data-stu-id="4a202-197">Goals</span></span>

<span data-ttu-id="4a202-198">Цель данного руководства — Показать несколькими альтернативами вами при развертывании контейнеров Windows на виртуальных машинах Azure, которые основаны на Windows Server 2016 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="4a202-198">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="4a202-199">Сценарии</span><span class="sxs-lookup"><span data-stu-id="4a202-199">Scenarios</span></span>

<span data-ttu-id="4a202-200">В этом пошаговом руководстве рассмотрены несколько сценариев.</span><span class="sxs-lookup"><span data-stu-id="4a202-200">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="4a202-201">Сценарий а развернуть в виртуальной Машине Azure из разработки ПК через подключение подсистемы Docker</span><span class="sxs-lookup"><span data-stu-id="4a202-201">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![Развертывание на Виртуальной машине Azure из разработки ПК через подключение подсистемы Docker](./media/image5-4.png)

> <span data-ttu-id="4a202-203">**Рис.**</span><span class="sxs-lookup"><span data-stu-id="4a202-203">**Figure 5-4.**</span></span> <span data-ttu-id="4a202-204">Развертывание на Виртуальной машине Azure из разработки ПК через подключение подсистемы Docker</span><span class="sxs-lookup"><span data-stu-id="4a202-204">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="4a202-205">Сценарий б. развертывание на Виртуальной машине Azure через реестр Docker</span><span class="sxs-lookup"><span data-stu-id="4a202-205">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![Развертывание на Виртуальной машине Azure через реестр Docker](./media/image5-5.png)

> <span data-ttu-id="4a202-207">**Рис.**</span><span class="sxs-lookup"><span data-stu-id="4a202-207">**Figure 5-5.**</span></span> <span data-ttu-id="4a202-208">Развертывание на Виртуальной машине Azure через реестр Docker</span><span class="sxs-lookup"><span data-stu-id="4a202-208">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-visual-studio-team-services"></a><span data-ttu-id="4a202-209">Сценарий C: развертывание на Виртуальной машине Azure из элемента конфигурации/CD конвейеры в Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="4a202-209">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Visual Studio Team Services</span></span>

![Развертывание на Виртуальной машине Azure из элемента конфигурации/CD конвейеры в Visual Studio Team Services](./media/image5-6.png)

> <span data-ttu-id="4a202-211">**Рис. 5-6**.</span><span class="sxs-lookup"><span data-stu-id="4a202-211">**Figure 5-6.**</span></span> <span data-ttu-id="4a202-212">Развертывание на Виртуальной машине Azure из элемента конфигурации/CD конвейеры в Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="4a202-212">Deploy to an Azure VM from CI/CD pipelines in Visual Studio Team Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="4a202-213">Виртуальные машины Azure для контейнеров Windows</span><span class="sxs-lookup"><span data-stu-id="4a202-213">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="4a202-214">Azure виртуальные машины для контейнеров Windows — это виртуальные машины на основе Windows Server 2016, Windows 10 или более поздних версий, и с подсистемой Dосker Настройка.</span><span class="sxs-lookup"><span data-stu-id="4a202-214">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="4a202-215">В большинстве случаев в виртуальных машинах Azure используется Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="4a202-215">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="4a202-216">В настоящее время в Azure предоставляет Виртуальную машину с именем **Windows Server 2016 с контейнерами**.</span><span class="sxs-lookup"><span data-stu-id="4a202-216">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="4a202-217">Можно использовать эту виртуальную Машину для испытания функции нового контейнера Windows Server с Windows Server Core или Nano Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4a202-217">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="4a202-218">Образы ОС контейнеров устанавливаются, и затем виртуальная машина будет готова для использования с помощью Docker.</span><span class="sxs-lookup"><span data-stu-id="4a202-218">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="4a202-219">Преимущества</span><span class="sxs-lookup"><span data-stu-id="4a202-219">Benefits</span></span>

<span data-ttu-id="4a202-220">Несмотря на то, что контейнеры Windows можно развернуть для локальных 2016 виртуальных машин Windows Server, при развертывании в Azure, вы получаете более простой способ начать с виртуальных машин контейнера готовые к использованию Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4a202-220">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="4a202-221">Можно также получить расположение общей сети, доступной для инженеров-испытателей и автоматического масштабируемости с помощью набора масштабирования виртуальной машины Azure.</span><span class="sxs-lookup"><span data-stu-id="4a202-221">You also get a common online location that’s accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="4a202-222">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="4a202-222">Next steps</span></span>

<span data-ttu-id="4a202-223">Это содержимое более подробное изучение на вики-сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="4a202-223">Explore this content more in-depth on the GitHub wiki:</span></span>

<span data-ttu-id="4a202-224">[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))</span><span class="sxs-lookup"><span data-stu-id="4a202-224">[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))</span></span>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="4a202-225">Пошаговое руководство по 4 развертывания приложений на основе контейнеров Windows на Kubernetes в контейнер Azure службы</span><span class="sxs-lookup"><span data-stu-id="4a202-225">Walkthrough 4: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="4a202-226">Технические руководства доступности</span><span class="sxs-lookup"><span data-stu-id="4a202-226">Technical walkthrough availability</span></span>

<span data-ttu-id="4a202-227">Полные технические пошагового руководства можно найти в репозитории GitHub eShopModernizing вики-сайте:</span><span class="sxs-lookup"><span data-stu-id="4a202-227">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="4a202-228">[https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span><span class="sxs-lookup"><span data-stu-id="4a202-228">[https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span></span>

### <a name="overview"></a><span data-ttu-id="4a202-229">Обзор</span><span class="sxs-lookup"><span data-stu-id="4a202-229">Overview</span></span>

<span data-ttu-id="4a202-230">Приложения, основанный на контейнеры Windows быстро нужно будет использовать платформ отсутствовали еще более перемещение из ВМ IaaS.</span><span class="sxs-lookup"><span data-stu-id="4a202-230">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="4a202-231">Это требуется для легко обеспечить высокую масштабируемость лучше автоматического масштабирования и значительные улучшения в автоматического развертывания и управления версиями.</span><span class="sxs-lookup"><span data-stu-id="4a202-231">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="4a202-232">Эти цели можно добиться с помощью orchestrator [Kubernetes](https://kubernetes.io/), которые доступны в [контейнера служб Azure](https://azure.microsoft.com/services/container-service/).</span><span class="sxs-lookup"><span data-stu-id="4a202-232">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="4a202-233">Цели</span><span class="sxs-lookup"><span data-stu-id="4a202-233">Goals</span></span>

<span data-ttu-id="4a202-234">В этом пошаговом руководстве предназначена для того, чтобы узнать о способах развертывания приложения на основе контейнера Windows на Kubernetes (также называемый *K8s*) в службе контейнера Azure.</span><span class="sxs-lookup"><span data-stu-id="4a202-234">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="4a202-235">Развертывание с нуля Kubernetes состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="4a202-235">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1.  <span data-ttu-id="4a202-236">Развертывание кластера Kubernetes контейнера службы Azure.</span><span class="sxs-lookup"><span data-stu-id="4a202-236">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2.  <span data-ttu-id="4a202-237">Развертывание приложения и связанные ресурсы в кластере Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="4a202-237">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="4a202-238">Сценарии</span><span class="sxs-lookup"><span data-stu-id="4a202-238">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="4a202-239">Сценарий а развернуть напрямую к кластеру Kubernetes из среды разработки</span><span class="sxs-lookup"><span data-stu-id="4a202-239">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![Развертывание непосредственно на кластере Kubernetes из среды разработки](./media/image5-7.png)

> <span data-ttu-id="4a202-241">**Рис.**</span><span class="sxs-lookup"><span data-stu-id="4a202-241">**Figure 5-7.**</span></span> <span data-ttu-id="4a202-242">Развертывание непосредственно на кластере Kubernetes из среды разработки</span><span class="sxs-lookup"><span data-stu-id="4a202-242">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-team-services"></a><span data-ttu-id="4a202-243">Сценарий б. развертывание кластера Kubernetes из элемента конфигурации/CD конвейеров в Team Services</span><span class="sxs-lookup"><span data-stu-id="4a202-243">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Team Services</span></span>

![Развертывание кластера Kubernetes из элемента конфигурации/CD конвейеры в Team Services](./media/image5-8.png)

> <span data-ttu-id="4a202-245">**Рис.**</span><span class="sxs-lookup"><span data-stu-id="4a202-245">**Figure 5-8.**</span></span> <span data-ttu-id="4a202-246">Развертывание кластера Kubernetes из элемента конфигурации/CD конвейеры в Team Services</span><span class="sxs-lookup"><span data-stu-id="4a202-246">Deploy to a Kubernetes cluster from CI/CD pipelines in Team Services</span></span>

### <a name="benefits"></a><span data-ttu-id="4a202-247">Преимущества</span><span class="sxs-lookup"><span data-stu-id="4a202-247">Benefits</span></span>

<span data-ttu-id="4a202-248">Есть множество преимуществ для развертывания на кластере в Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="4a202-248">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="4a202-249">Главное преимущество заключается в, чтобы получить готовый среды, в котором можно масштабировать приложение на основе количества экземпляров контейнера, необходимо использовать (inner масштабируемость в существующих узлов) и на основе количества узлов или виртуальных машин в кластере ( глобальные масштабируемость кластера).</span><span class="sxs-lookup"><span data-stu-id="4a202-249">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="4a202-250">Служба Azure контейнера оптимизирует популярных средств с открытым исходным кодом и технологии специально для Azure.</span><span class="sxs-lookup"><span data-stu-id="4a202-250">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="4a202-251">Вы получаете открытое решение, который обеспечивает совместимость для вашего контейнеров и конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="4a202-251">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="4a202-252">Выберите размер, количество узлов, и средства orchestrator-контейнера службы обрабатывает все остальное.</span><span class="sxs-lookup"><span data-stu-id="4a202-252">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="4a202-253">С Kubernetes разработчики можно перейти от обдумывания физических и виртуальных машин к планирования это ориентированное на контейнер инфраструктура, которая обеспечивает следующие возможности, в частности:</span><span class="sxs-lookup"><span data-stu-id="4a202-253">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="4a202-254">Приложений, основанных на несколько контейнеров</span><span class="sxs-lookup"><span data-stu-id="4a202-254">Applications based on multiple containers</span></span>

- <span data-ttu-id="4a202-255">Репликация экземпляров контейнера и горизонтальной автоматического масштабирования</span><span class="sxs-lookup"><span data-stu-id="4a202-255">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="4a202-256">Именование и обнаружения (например, внутренние DNS)</span><span class="sxs-lookup"><span data-stu-id="4a202-256">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="4a202-257">Балансировка нагрузки</span><span class="sxs-lookup"><span data-stu-id="4a202-257">Balancing loads</span></span>

- <span data-ttu-id="4a202-258">Последовательные обновления</span><span class="sxs-lookup"><span data-stu-id="4a202-258">Rolling updates</span></span>

- <span data-ttu-id="4a202-259">Распространение секретов</span><span class="sxs-lookup"><span data-stu-id="4a202-259">Distributing secrets</span></span>

- <span data-ttu-id="4a202-260">Проверку работоспособности приложения</span><span class="sxs-lookup"><span data-stu-id="4a202-260">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="4a202-261">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="4a202-261">Next steps</span></span>

<span data-ttu-id="4a202-262">Просмотр этого содержимого углубленные на вики-сайте GitHub: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-() Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span><span class="sxs-lookup"><span data-stu-id="4a202-262">Explore this content more in-depth on the GitHub wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span></span>

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a><span data-ttu-id="4a202-263">Пошаговое руководство по 5 развертывания приложений на основе контейнеров Windows для Azure Service Fabric</span><span class="sxs-lookup"><span data-stu-id="4a202-263">Walkthrough 5: Deploy your Windows Containers-based apps to Azure Service Fabric</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="4a202-264">Технические руководства доступности</span><span class="sxs-lookup"><span data-stu-id="4a202-264">Technical walkthrough availability</span></span>

<span data-ttu-id="4a202-265">Полные технические пошагового руководства можно найти в репозитории GitHub eShopModernizing вики-сайте:</span><span class="sxs-lookup"><span data-stu-id="4a202-265">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="4a202-266">[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))</span><span class="sxs-lookup"><span data-stu-id="4a202-266">[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))</span></span>

### <a name="overview"></a><span data-ttu-id="4a202-267">Обзор</span><span class="sxs-lookup"><span data-stu-id="4a202-267">Overview</span></span>

<span data-ttu-id="4a202-268">Приложение по контейнерам Windows быстро должен использовать платформ отсутствовали еще более перемещение из ВМ IaaS.</span><span class="sxs-lookup"><span data-stu-id="4a202-268">An application based on Windows Containers quickly needs to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="4a202-269">Это требуется для легко обеспечить высокую масштабируемость лучше автоматического масштабирования и значительные улучшения в автоматического развертывания и управления версиями.</span><span class="sxs-lookup"><span data-stu-id="4a202-269">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="4a202-270">Эти цели можно добиться с помощью orchestrator Azure Service Fabric доступны в облаке Azure, но также можно использовать в локальной среде, или даже в разных общедоступное облако.</span><span class="sxs-lookup"><span data-stu-id="4a202-270">You can achieve these goals by using the orchestrator Azure Service Fabric, which is available in the Azure cloud, but also available to use on-premises, or even in a different public cloud.</span></span>

### <a name="goals"></a><span data-ttu-id="4a202-271">Цели</span><span class="sxs-lookup"><span data-stu-id="4a202-271">Goals</span></span>

<span data-ttu-id="4a202-272">В этом пошаговом руководстве предназначена для того, чтобы узнать, как развертывание приложения на основе контейнера Windows в кластер Service Fabric в Azure.</span><span class="sxs-lookup"><span data-stu-id="4a202-272">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to a Service Fabric cluster in Azure.</span></span> <span data-ttu-id="4a202-273">Развертывание Service Fabric с нуля состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="4a202-273">Deploying to Service Fabric from scratch is a two-step process:</span></span>

1.  <span data-ttu-id="4a202-274">Развертывание кластера Service Fabric в Azure (или в другой среде).</span><span class="sxs-lookup"><span data-stu-id="4a202-274">Deploy a Service Fabric cluster to Azure (or to a different environment).</span></span>

2.  <span data-ttu-id="4a202-275">Развертывание приложения и связанные ресурсы в кластере Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="4a202-275">Deploy the application and related resources to the Service Fabric cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="4a202-276">Сценарии</span><span class="sxs-lookup"><span data-stu-id="4a202-276">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a><span data-ttu-id="4a202-277">Сценарий а развернуть напрямую к кластеру Service Fabric из среды разработки</span><span class="sxs-lookup"><span data-stu-id="4a202-277">Scenario A: Deploy directly to a Service Fabric cluster from a dev environment</span></span>

![Развертывание непосредственно к кластеру Service Fabric из среды разработки](./media/image5-9.png)

> <span data-ttu-id="4a202-279">**Рис. 5-9.**</span><span class="sxs-lookup"><span data-stu-id="4a202-279">**Figure 5-9.**</span></span> <span data-ttu-id="4a202-280">Развертывание непосредственно к кластеру Service Fabric из среды разработки</span><span class="sxs-lookup"><span data-stu-id="4a202-280">Deploy directly to a Service Fabric cluster from a development environment</span></span>

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-team-services"></a><span data-ttu-id="4a202-281">Сценарий б. развертывание кластера Service Fabric из элемента конфигурации/CD конвейеров в Team Services</span><span class="sxs-lookup"><span data-stu-id="4a202-281">Scenario B: Deploy to a Service Fabric cluster from CI/CD pipelines in Team Services</span></span>

![Развертывание кластера Service Fabric из элемента конфигурации/CD конвейеры в Visual Studio Team Services](./media/image5-10.png)

> <span data-ttu-id="4a202-283">**Рис. 5-10.**</span><span class="sxs-lookup"><span data-stu-id="4a202-283">**Figure 5-10.**</span></span> <span data-ttu-id="4a202-284">Развертывание кластера Service Fabric из элемента конфигурации/CD конвейеры в Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="4a202-284">Deploy to a Service Fabric cluster from CI/CD pipelines in Visual Studio Team Services</span></span>

## <a name="benefits"></a><span data-ttu-id="4a202-285">Преимущества</span><span class="sxs-lookup"><span data-stu-id="4a202-285">Benefits</span></span>

<span data-ttu-id="4a202-286">Преимущества развертывания на кластере в Service Fabric аналогичны преимущества использования Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="4a202-286">The benefits of deploying to a cluster in Service Fabric are similar to the benefits of using Kubernetes.</span></span> <span data-ttu-id="4a202-287">Различие, однако является Service Fabric более развитым рабочей среде для приложений Windows, по сравнению с Kubernetes, который находится на этапе бета-версии для контейнеров Windows в Kubernetes версия 1.9 (декабрь 2017 г.).</span><span class="sxs-lookup"><span data-stu-id="4a202-287">One difference, though, is that Service Fabric is a more mature production environment for Windows applications compared to Kubernetes, which is in a beta phase for Windows Containers in Kubernetes version 1.9 (December 2017).</span></span> <span data-ttu-id="4a202-288">Kubernetes представляет собой более развитым среду для Linux.</span><span class="sxs-lookup"><span data-stu-id="4a202-288">Kubernetes is a more mature environment for Linux.</span></span>

<span data-ttu-id="4a202-289">Является основным преимуществом использования Azure Service Fabric, чтобы получить готовый среды, в котором можно масштабировать приложение на основе количества экземпляров контейнера, необходимо использовать (inner масштабируемость в существующих узлов) и на основе количества узлы или виртуальные машины в кластере (глобальный масштабируемость кластера).</span><span class="sxs-lookup"><span data-stu-id="4a202-289">The main benefit of using Azure Service Fabric is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="4a202-290">Azure Service Fabric обеспечивает совместимость для вашего контейнеров и конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="4a202-290">Azure Service Fabric offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="4a202-291">Может иметь Service Fabric кластера в Azure, и устанавливается локально в собственном центре обработки данных.</span><span class="sxs-lookup"><span data-stu-id="4a202-291">You can have a Service Fabric cluster in Azure, or install it on-premises in your own datacenter.</span></span> <span data-ttu-id="4a202-292">Можно даже установке кластера Service Fabric в другом облаке, например [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).</span><span class="sxs-lookup"><span data-stu-id="4a202-292">You can even install a Service Fabric cluster in a different cloud, like [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).</span></span>

<span data-ttu-id="4a202-293">В Service Fabric разработчики можно перейти от обдумывания физических и виртуальных машин к планирования это ориентированное на контейнер инфраструктура, которая обеспечивает следующие возможности, в частности:</span><span class="sxs-lookup"><span data-stu-id="4a202-293">With Service Fabric, developers can progress from thinking about physical and virtual machines to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="4a202-294">Приложений на основании несколько контейнеров.</span><span class="sxs-lookup"><span data-stu-id="4a202-294">Applications based on multiple containers.</span></span>

- <span data-ttu-id="4a202-295">Репликация экземпляров контейнера и горизонтальной автоматическое масштабирование.</span><span class="sxs-lookup"><span data-stu-id="4a202-295">Replicating container instances and horizontal autoscaling.</span></span>

- <span data-ttu-id="4a202-296">Присвоение имени и обнаружения (например, внутренние DNS).</span><span class="sxs-lookup"><span data-stu-id="4a202-296">Naming and discovering (for example, internal DNS).</span></span>

- <span data-ttu-id="4a202-297">Балансировка нагрузки.</span><span class="sxs-lookup"><span data-stu-id="4a202-297">Balancing loads.</span></span>

- <span data-ttu-id="4a202-298">Развертывание обновлений.</span><span class="sxs-lookup"><span data-stu-id="4a202-298">Rolling updates.</span></span>

- <span data-ttu-id="4a202-299">Распространение секретные данные.</span><span class="sxs-lookup"><span data-stu-id="4a202-299">Distributing secrets.</span></span>

- <span data-ttu-id="4a202-300">Проверяет работоспособность приложения.</span><span class="sxs-lookup"><span data-stu-id="4a202-300">Application health checks.</span></span>

<span data-ttu-id="4a202-301">Следующие возможности являются взаимоисключающими в Service Fabric (по сравнению с другими orchestrators):</span><span class="sxs-lookup"><span data-stu-id="4a202-301">The following capabilities are exclusive in Service Fabric (compared to other orchestrators):</span></span>

- <span data-ttu-id="4a202-302">Возможности служб с отслеживанием состояния через модель надежные службы приложения.</span><span class="sxs-lookup"><span data-stu-id="4a202-302">Stateful services capability, through the Reliable Services application model.</span></span>

- <span data-ttu-id="4a202-303">Шаблон субъекты, с помощью службы Reliable Actor модели приложения.</span><span class="sxs-lookup"><span data-stu-id="4a202-303">Actors pattern, through the Reliable Actors application model.</span></span>

- <span data-ttu-id="4a202-304">Развертывание без операционной системы костей процессов, в дополнение к контейнерам Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="4a202-304">Deploy bare-bone processes, in addition to Windows or Linux containers.</span></span>

- <span data-ttu-id="4a202-305">Расширенные последовательного обновления и проверки работоспособности.</span><span class="sxs-lookup"><span data-stu-id="4a202-305">Advanced rolling updates and health checks.</span></span>

### <a name="next-steps"></a><span data-ttu-id="4a202-306">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="4a202-306">Next steps</span></span>

<span data-ttu-id="4a202-307">Это содержимое более подробное изучение на вики-сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="4a202-307">Explore this content more in-depth on the GitHub wiki:</span></span>

<span data-ttu-id="4a202-308">[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))</span><span class="sxs-lookup"><span data-stu-id="4a202-308">[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="4a202-309">[Назад](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Вперед](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="4a202-309">[Previous](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span>
