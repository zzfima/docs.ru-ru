---
title: Обзор пошаговых руководств и технических описаний по началу работы
description: Модернизация существующих приложений .NET с помощью облака Azure и контейнеров Windows | Пошаговые руководства и Технический обзор работы
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 2202e2f972951e4074ed1941f0a0cfe352ab4b85
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612957"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="80ad3-103">Обзор пошаговых руководств и технических описаний по началу работы</span><span class="sxs-lookup"><span data-stu-id="80ad3-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="80ad3-104">Чтобы ограничить размер этой электронной книге, Дополнительная техническая документация и полные руководства содержат были доступны в репозитории GitHub.</span><span class="sxs-lookup"><span data-stu-id="80ad3-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="80ad3-105">Online ряд пошаговых руководств, описанный в этой главе рассматриваются пошаговой настройки нескольких сред, основанных на контейнеры Windows и развертывания в Azure.</span><span class="sxs-lookup"><span data-stu-id="80ad3-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="80ad3-106">Что каждого пошагового руководства о его цели и высокоуровневые концепции и предоставляет схему задачи, которые участвуют в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="80ad3-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="80ad3-107">Вы можете получить пошаговые руководства, самостоятельно в *eShopModernizing* вики-сайт репозитория GitHub приложения в <https://github.com/dotnet-architecture/eShopModernizing/wiki>.</span><span class="sxs-lookup"><span data-stu-id="80ad3-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at <https://github.com/dotnet-architecture/eShopModernizing/wiki>.</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="80ad3-108">Список техническим руководством</span><span class="sxs-lookup"><span data-stu-id="80ad3-108">Technical walkthrough list</span></span>

<span data-ttu-id="80ad3-109">Следующие пошаговые руководства начало предоставить согласованный и всесторонний обзор Технические рекомендации для примеров приложений, которые можно перенести и shift с помощью контейнеров, а затем переместите с помощью нескольких вариантов развертывания в Azure.</span><span class="sxs-lookup"><span data-stu-id="80ad3-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="80ad3-110">Каждый из приведенных ниже пошаговых руководств использует новые примеры eShopLegacy и eShopModernizing приложений, которые доступны на сайте GitHub в <https://github.com/dotnet-architecture/eShopModernizing>.</span><span class="sxs-lookup"><span data-stu-id="80ad3-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at <https://github.com/dotnet-architecture/eShopModernizing>.</span></span>

- <span data-ttu-id="80ad3-111">**Обзор eShop устаревших приложений (приложения для базовых показателей для модернизации)**</span><span class="sxs-lookup"><span data-stu-id="80ad3-111">**Tour of eShop legacy apps (baseline apps to modernize)**</span></span>

- <span data-ttu-id="80ad3-112">**Контейнеризация существующего веб-приложений ASP.NET (веб-форм и MVC) с контейнерами Windows**</span><span class="sxs-lookup"><span data-stu-id="80ad3-112">**Containerize your existing ASP.NET web apps (WebForms & MVC) with Windows Containers**</span></span>

- <span data-ttu-id="80ad3-113">**Контейнеризация существующего служб WCF (N-уровневого приложения) с контейнерами Windows**</span><span class="sxs-lookup"><span data-stu-id="80ad3-113">**Containerize your existing WCF services (N-Tier apps) with Windows Containers**</span></span>

- <span data-ttu-id="80ad3-114">**Развертывание приложения на базе контейнеров Windows в виртуальных машинах Azure**</span><span class="sxs-lookup"><span data-stu-id="80ad3-114">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="80ad3-115">**Развертывание приложений на базе контейнеров Windows в Kubernetes в службе контейнеров Azure**</span><span class="sxs-lookup"><span data-stu-id="80ad3-115">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

- <span data-ttu-id="80ad3-116">**Развертывание приложений на базе контейнеров Windows в Azure Service Fabric**</span><span class="sxs-lookup"><span data-stu-id="80ad3-116">**Deploy your Windows Containers-based apps to Azure Service Fabric**</span></span>

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="80ad3-117">Пошаговое руководство 1. Обзор приложений прежних версий eShop</span><span class="sxs-lookup"><span data-stu-id="80ad3-117">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="80ad3-118">Доступность техническим руководством</span><span class="sxs-lookup"><span data-stu-id="80ad3-118">Technical walkthrough availability</span></span>

<span data-ttu-id="80ad3-119">Полной технической руководство доступно в репозитории GitHub eShopModernizing вики-сайте:</span><span class="sxs-lookup"><span data-stu-id="80ad3-119">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="80ad3-120">Пошаговые руководства вики-сайте eShopModernizing</span><span class="sxs-lookup"><span data-stu-id="80ad3-120">eShopModernizing wiki walkthroughs</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a><span data-ttu-id="80ad3-121">Обзор</span><span class="sxs-lookup"><span data-stu-id="80ad3-121">Overview</span></span>

<span data-ttu-id="80ad3-122">В этом пошаговом руководстве вы можете изучить начальная реализация из трех примеров приложений прежних версий.</span><span class="sxs-lookup"><span data-stu-id="80ad3-122">In this walkthrough, you can explore the initial implementation of three sample legacy applications.</span></span> <span data-ttu-id="80ad3-123">Первые два примера веб-приложений имеют монолитная архитектура и были созданы с помощью Классическая ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="80ad3-123">The first two sample web apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="80ad3-124">Одно приложение на базе ASP.NET 4.x MVC; второе приложение зависит от веб-форм ASP.NET 4.x.</span><span class="sxs-lookup"><span data-stu-id="80ad3-124">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span>
<span data-ttu-id="80ad3-125">Третий приложение является приложением уровня 3, состоящих из клиентского приложения WinForms и на стороне сервера [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) службы.</span><span class="sxs-lookup"><span data-stu-id="80ad3-125">The third app is a 3-Tier app composed by a client WinForms app and a server-side [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) service.</span></span>

<span data-ttu-id="80ad3-126">Все эти приложения можно найти по адресу [репозиторий GitHub eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="80ad3-126">All these applications are available at the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

### <a name="goals"></a><span data-ttu-id="80ad3-127">Цели</span><span class="sxs-lookup"><span data-stu-id="80ad3-127">Goals</span></span>

<span data-ttu-id="80ad3-128">Основная цель этого пошагового руководства, достаточно ознакомиться с этими приложениями и с их кода и конфигурации.</span><span class="sxs-lookup"><span data-stu-id="80ad3-128">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="80ad3-129">Можно настроить приложения, создавать и использовать фиктивные данные без использования базы данных SQL, для целей тестирования.</span><span class="sxs-lookup"><span data-stu-id="80ad3-129">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="80ad3-130">Это необязательная конфигурация основана на внедрение зависимостей, несвязанно.</span><span class="sxs-lookup"><span data-stu-id="80ad3-130">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario-1-aspnet-web-apps"></a><span data-ttu-id="80ad3-131">Сценарий 1. Веб-приложений ASP.NET</span><span class="sxs-lookup"><span data-stu-id="80ad3-131">Scenario 1: ASP.NET Web apps</span></span>

<span data-ttu-id="80ad3-132">На рисунке ниже показан простой сценарий исходного устаревших веб-приложений ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="80ad3-132">The figure below shows the simple scenario of the original legacy ASP.NET web applications.</span></span>

![Простая архитектура сценария исходного устаревших веб-приложений ASP.NET](./media/image5-1.png)

<span data-ttu-id="80ad3-134">С точки зрения бизнеса домена оба приложения предлагают одного каталога функции управления.</span><span class="sxs-lookup"><span data-stu-id="80ad3-134">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="80ad3-135">Члены группы enterprise eShop использует приложение для просмотра и изменения каталога товаров.</span><span class="sxs-lookup"><span data-stu-id="80ad3-135">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span>

<span data-ttu-id="80ad3-136">На следующем рисунке показано на снимках экрана первоначального приложения.</span><span class="sxs-lookup"><span data-stu-id="80ad3-136">The next figure shows the initial app screenshots.</span></span>

![Приложения ASP.NET MVC и веб-форм ASP.NET (существующими или устаревшими технологии)](./media/image5-2.png)

<span data-ttu-id="80ad3-138">Зависимости в ASP.NET 4.x или более ранних версий (либо для MVC или веб-форм) означает, что эти приложения не будут работать на .NET Core, если код полностью переписан с помощью ASP.NET Core MVC.</span><span class="sxs-lookup"><span data-stu-id="80ad3-138">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won’t run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span>

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a><span data-ttu-id="80ad3-139">Сценарий 2. Служба WCF и клиентское приложение WinForms (3-уровневое приложение)</span><span class="sxs-lookup"><span data-stu-id="80ad3-139">Scenario 2: WCF service and WinForms client app (3-Tier app)</span></span>

<span data-ttu-id="80ad3-140">На рисунке ниже показан простой сценарий исходного 3-уровневого приложения прежних версий.</span><span class="sxs-lookup"><span data-stu-id="80ad3-140">The figure below shows the simple scenario of the original 3-Tier legacy application.</span></span>

![Сценарий простой архитектуры оригинальное прежних версий 3-уровневое приложение со службой WCF и клиентского приложения WinForms](./media/image5-1.5.png)

### <a name="benefits"></a><span data-ttu-id="80ad3-142">Преимущества</span><span class="sxs-lookup"><span data-stu-id="80ad3-142">Benefits</span></span>

<span data-ttu-id="80ad3-143">Преимущества в этом пошаговом руководстве, просты: Просто ознакомиться с кодом и начального приложения.</span><span class="sxs-lookup"><span data-stu-id="80ad3-143">The benefits of this walkthrough are simple: Just get familiar with the code and initial apps.</span></span>

### <a name="next-steps"></a><span data-ttu-id="80ad3-144">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="80ad3-144">Next steps</span></span>

<span data-ttu-id="80ad3-145">Это содержимое более подробный обзор на вики-сайте GitHub:</span><span class="sxs-lookup"><span data-stu-id="80ad3-145">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="80ad3-146">Обзор на базовых ASP.NET MVC и веб-форм «устаревшего» приложений</span><span class="sxs-lookup"><span data-stu-id="80ad3-146">Tour on the baseline ASP.NET MVC and Web Forms “legacy” apps</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [<span data-ttu-id="80ad3-147">Обзор базовая служба WCF и «устаревшего» приложение WinForms (3-уровневой)</span><span class="sxs-lookup"><span data-stu-id="80ad3-147">Tour on the baseline WCF service and WinForms (3-Tier) “legacy” app</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="80ad3-148">Пошаговое руководство 2. Контейнеризация существующие приложения .NET с контейнерами Windows</span><span class="sxs-lookup"><span data-stu-id="80ad3-148">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="overview"></a><span data-ttu-id="80ad3-149">Обзор</span><span class="sxs-lookup"><span data-stu-id="80ad3-149">Overview</span></span>

<span data-ttu-id="80ad3-150">Используйте контейнеры Windows для улучшения развертывания существующих приложений .NET, как на основе MVC, веб-форм или WCF, в рабочей среде, разработки, среды и тестирования.</span><span class="sxs-lookup"><span data-stu-id="80ad3-150">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="80ad3-151">Цели</span><span class="sxs-lookup"><span data-stu-id="80ad3-151">Goals</span></span>

<span data-ttu-id="80ad3-152">Цель данного руководства — Показать, несколько вариантов для запуска существующего приложения .NET Framework в контейнерах.</span><span class="sxs-lookup"><span data-stu-id="80ad3-152">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="80ad3-153">Можно выполнить следующие действия: </span><span class="sxs-lookup"><span data-stu-id="80ad3-153">You can:</span></span>

- <span data-ttu-id="80ad3-154">Упаковывайте приложения в контейнеры с помощью [инструменты Visual Studio 2017 для Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 или более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="80ad3-154">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="80ad3-155">Упаковывайте приложения в контейнеры, вручную добавив [Dockerfile](https://docs.docker.com/engine/reference/builder/), а затем с помощью [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span><span class="sxs-lookup"><span data-stu-id="80ad3-155">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="80ad3-156">Упаковывайте приложения в контейнеры с помощью [Img2Docker](https://github.com/docker/communitytools-image2docker-win) инструмента (инструмент с открытым кодом от Docker).</span><span class="sxs-lookup"><span data-stu-id="80ad3-156">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="80ad3-157">В этом пошаговом руководстве рассматриваются инструменты Visual Studio 2017 для Docker подхода, но эти два подхода довольно похожи отношении с помощью файлов Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="80ad3-157">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario-1-containerized-aspnet-web-apps"></a><span data-ttu-id="80ad3-158">Сценарий 1. Контейнерные веб-приложений ASP.NET</span><span class="sxs-lookup"><span data-stu-id="80ad3-158">Scenario 1: Containerized ASP.NET web apps</span></span>

<span data-ttu-id="80ad3-159">На следующем рисунке показан сценарий для контейнерных eShop устаревших веб-приложений, приложений.</span><span class="sxs-lookup"><span data-stu-id="80ad3-159">Figure below shows the scenario for containerized eShop legacy web apps applications.</span></span>

![Схема упрощенной архитектуры контейнерных приложений ASP.NET в среде разработки](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a><span data-ttu-id="80ad3-161">Сценарий 2. Контейнерная служба WCF</span><span class="sxs-lookup"><span data-stu-id="80ad3-161">Scenario 2: Containerized WCF service</span></span>

<span data-ttu-id="80ad3-162">На следующем рисунке показан сценарий для трехуровневого приложения с контейнерная служба WCF.</span><span class="sxs-lookup"><span data-stu-id="80ad3-162">Figure below shows the scenario for a 3-Tier app with a containerized WCF service.</span></span>

![Упрощенная схема архитектуры контейнерные службы WCF в среде разработки](./media/image5-3.5.png)

### <a name="benefits"></a><span data-ttu-id="80ad3-164">Преимущества</span><span class="sxs-lookup"><span data-stu-id="80ad3-164">Benefits</span></span>

<span data-ttu-id="80ad3-165">Существуют преимущества запуска монолитного приложения в контейнере.</span><span class="sxs-lookup"><span data-stu-id="80ad3-165">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="80ad3-166">Во-первых можно создать образ для приложения.</span><span class="sxs-lookup"><span data-stu-id="80ad3-166">First, you create an image for the application.</span></span> <span data-ttu-id="80ad3-167">С этого момента каждое развертывание будет производиться в одной среде.</span><span class="sxs-lookup"><span data-stu-id="80ad3-167">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="80ad3-168">Каждый контейнер использует одну и ту же версию ОС, имеет ту же версию установить зависимости, использует ту же версию .NET framework и создается с тем же способом.</span><span class="sxs-lookup"><span data-stu-id="80ad3-168">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="80ad3-169">По сути вы управляете зависимости приложения с помощью образа Docker.</span><span class="sxs-lookup"><span data-stu-id="80ad3-169">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="80ad3-170">Зависимости перемещаются вместе с приложением при развертывании контейнеров.</span><span class="sxs-lookup"><span data-stu-id="80ad3-170">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="80ad3-171">Дополнительным преимуществом является то, что разработчики могут запустить приложение в согласованную среду, которая предоставляется в контейнерах Windows.</span><span class="sxs-lookup"><span data-stu-id="80ad3-171">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="80ad3-172">Проблемы, которые отображаются только в определенных версиях может быть замечена немедленно, а не отображать в промежуточной или рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="80ad3-172">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="80ad3-173">Различия в средах разработки, используемых членами группы разработки так важны при запуске приложения в контейнерах.</span><span class="sxs-lookup"><span data-stu-id="80ad3-173">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="80ad3-174">Контейнерные приложения также имеют flatter кривую горизонтального масштабирования.</span><span class="sxs-lookup"><span data-stu-id="80ad3-174">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="80ad3-175">Контейнерных приложений обеспечивают возможность иметь несколько экземпляров приложения и службы (с учетом контейнеры) на виртуальной Машине или физическом компьютере, по сравнению с развертываниями обычное приложение на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="80ad3-175">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="80ad3-176">Это преобразуется в более поздней версии плотность и требуется меньше ресурсов, особенно в том случае, при использовании оркестраторов, таком как Kubernetes или Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="80ad3-176">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes or Service Fabric.</span></span>

<span data-ttu-id="80ad3-177">Создание контейнеров, в идеальной ситуации, не требует внесения изменений в код приложения (C\#).</span><span class="sxs-lookup"><span data-stu-id="80ad3-177">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="80ad3-178">В большинстве случаев нужно просто Docker развертывания метаданных файлов (файлов Dockerfile и Docker Compose).</span><span class="sxs-lookup"><span data-stu-id="80ad3-178">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="80ad3-179">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="80ad3-179">Next steps</span></span>

<span data-ttu-id="80ad3-180">Это содержимое более подробный обзор на вики-сайте GitHub:</span><span class="sxs-lookup"><span data-stu-id="80ad3-180">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="80ad3-181">Как контейнеризовать веб-приложения .NET Framework с контейнерами Windows и Docker</span><span class="sxs-lookup"><span data-stu-id="80ad3-181">How to containerize the .NET Framework web apps with Windows Containers and Docker</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [<span data-ttu-id="80ad3-182">Добавление поддержки Docker для службы WCF</span><span class="sxs-lookup"><span data-stu-id="80ad3-182">Adding Docker Support to a WCF service</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="80ad3-183">Пошаговое руководство 3. Развертывание приложения на базе контейнеров Windows в виртуальных машинах Azure</span><span class="sxs-lookup"><span data-stu-id="80ad3-183">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="80ad3-184">Доступность техническим руководством</span><span class="sxs-lookup"><span data-stu-id="80ad3-184">Technical walkthrough availability</span></span>

<span data-ttu-id="80ad3-185">Полной технической руководство доступно в репозитории GitHub eShopModernizing вики-сайте: <https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="80ad3-185">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span></span>

### <a name="overview"></a><span data-ttu-id="80ad3-186">Обзор</span><span class="sxs-lookup"><span data-stu-id="80ad3-186">Overview</span></span>

<span data-ttu-id="80ad3-187">Развертывание на узле Docker на Windows Server 2016 виртуальной машины (ВМ) в Azure позволяет быстро настроить разработки, тестирования и промежуточной сред.</span><span class="sxs-lookup"><span data-stu-id="80ad3-187">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="80ad3-188">Она также предоставляет чаще всего для тест-инженеров или бизнес-пользователей, для проверки приложения.</span><span class="sxs-lookup"><span data-stu-id="80ad3-188">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="80ad3-189">Виртуальные машины также могут быть допустимой инфраструктуры как услуги (IaaS) рабочих средах.</span><span class="sxs-lookup"><span data-stu-id="80ad3-189">VMs also can be valid Infrastructure as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="80ad3-190">Цели</span><span class="sxs-lookup"><span data-stu-id="80ad3-190">Goals</span></span>

<span data-ttu-id="80ad3-191">Цель данного руководства — Показать, несколько альтернативных вариантов, которые возникают при развертывании контейнеров Windows на виртуальных машинах Azure, которые основаны на Windows Server 2016 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="80ad3-191">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="80ad3-192">Сценарии</span><span class="sxs-lookup"><span data-stu-id="80ad3-192">Scenarios</span></span>

<span data-ttu-id="80ad3-193">В этом пошаговом руководстве рассматриваются несколько сценариев.</span><span class="sxs-lookup"><span data-stu-id="80ad3-193">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="80ad3-194">Сценарий а. Развертывание виртуальной Машины Azure из dev ПК через подключение подсистемы Docker</span><span class="sxs-lookup"><span data-stu-id="80ad3-194">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![Развертывание виртуальной Машины Azure из dev ПК через подключение к подсистеме Docker](./media/image5-4.png)

<span data-ttu-id="80ad3-196">**Рис. 5-4.**</span><span class="sxs-lookup"><span data-stu-id="80ad3-196">**Figure 5-4.**</span></span> <span data-ttu-id="80ad3-197">Развертывание виртуальной Машины Azure из dev ПК через подключение к подсистеме Docker</span><span class="sxs-lookup"><span data-stu-id="80ad3-197">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="80ad3-198">Сценарий б Развертывание на виртуальной Машине Azure через реестр Docker</span><span class="sxs-lookup"><span data-stu-id="80ad3-198">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![Развертывание на виртуальной Машине Azure через реестр Docker](./media/image5-5.png)

<span data-ttu-id="80ad3-200">**Рис. 5-5.**</span><span class="sxs-lookup"><span data-stu-id="80ad3-200">**Figure 5-5.**</span></span> <span data-ttu-id="80ad3-201">Развертывание на виртуальной Машине Azure через реестр Docker</span><span class="sxs-lookup"><span data-stu-id="80ad3-201">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="80ad3-202">Сценарий C: Развертывание виртуальной Машины Azure из конвейеров CI/CD в службах Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="80ad3-202">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

![Развертывание виртуальной Машины Azure из конвейеров CI/CD в службах Azure DevOps](./media/image5-6.png)

<span data-ttu-id="80ad3-204">**Рис. 5-6**.</span><span class="sxs-lookup"><span data-stu-id="80ad3-204">**Figure 5-6.**</span></span> <span data-ttu-id="80ad3-205">Развертывание виртуальной Машины Azure из конвейеров CI/CD в службах Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="80ad3-205">Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="80ad3-206">Виртуальные машины Azure для контейнеров Windows</span><span class="sxs-lookup"><span data-stu-id="80ad3-206">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="80ad3-207">Под управлением Azure виртуальные машины для контейнеров Windows на основе Windows Server 2016, Windows 10 или более поздних версий, оба с модулем Docker, настроить.</span><span class="sxs-lookup"><span data-stu-id="80ad3-207">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="80ad3-208">В большинстве случаев используется Windows Server 2016, на виртуальных машинах Azure.</span><span class="sxs-lookup"><span data-stu-id="80ad3-208">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="80ad3-209">Azure в настоящее время предоставляет виртуальная машина с именем **Windows Server 2016 с контейнерами**.</span><span class="sxs-lookup"><span data-stu-id="80ad3-209">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="80ad3-210">Для испытания функции нового контейнера Windows Server с Windows Server Core или Windows Nano Server можно использовать эту виртуальную Машину.</span><span class="sxs-lookup"><span data-stu-id="80ad3-210">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="80ad3-211">Образы ОС контейнеров устанавливаются, и затем виртуальная машина готова к использованию с помощью Docker.</span><span class="sxs-lookup"><span data-stu-id="80ad3-211">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="80ad3-212">Преимущества</span><span class="sxs-lookup"><span data-stu-id="80ad3-212">Benefits</span></span>

<span data-ttu-id="80ad3-213">Несмотря на то, что контейнеры Windows можно развернуть для локальных Windows Server 2016 виртуальных машин, при развертывании в Azure, вы получаете более простой способ начать работу с виртуальными машинами контейнер готовые к использованию Windows Server.</span><span class="sxs-lookup"><span data-stu-id="80ad3-213">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="80ad3-214">Вы также получаете распространенных сетевом расположении, доступном для инженеров-испытателей и автоматического масштабирования через наборы масштабирования виртуальных машин Azure.</span><span class="sxs-lookup"><span data-stu-id="80ad3-214">You also get a common online location that’s accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="80ad3-215">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="80ad3-215">Next steps</span></span>

<span data-ttu-id="80ad3-216">Это содержимое более подробный обзор на вики-сайте GitHub:</span><span class="sxs-lookup"><span data-stu-id="80ad3-216">Explore this content more in-depth on the GitHub wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a><span data-ttu-id="80ad3-217">Пошаговое руководство 4. Развертывание приложений на базе контейнеров Windows в экземпляры контейнеров Azure (ACI)</span><span class="sxs-lookup"><span data-stu-id="80ad3-217">Walkthrough 4: Deploy your Windows Containers-based apps to Azure Container Instances (ACI)</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="80ad3-218">Доступность техническим руководством</span><span class="sxs-lookup"><span data-stu-id="80ad3-218">Technical walkthrough availability</span></span>

<span data-ttu-id="80ad3-219">Полной технической руководство доступно в репозитории GitHub eShopModernizing вики-сайте:</span><span class="sxs-lookup"><span data-stu-id="80ad3-219">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="80ad3-220">[Развертывание приложений в ACI (экземпляры контейнеров Azure)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span><span class="sxs-lookup"><span data-stu-id="80ad3-220">[Deploying the Apps to ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span></span>

### <a name="overview"></a><span data-ttu-id="80ad3-221">Обзор</span><span class="sxs-lookup"><span data-stu-id="80ad3-221">Overview</span></span>

<span data-ttu-id="80ad3-222">[Экземпляры контейнеров Azure (ACI)](https://docs.microsoft.com/azure/container-instances/) — это самый быстрый способ в среде разработки, тестирования и промежуточной контейнеры, где можно развернуть отдельные экземпляры контейнеров.</span><span class="sxs-lookup"><span data-stu-id="80ad3-222">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) is the quickest way to have a Containers dev/test/staging environment where you can deploy single instances of containers.</span></span>

### <a name="goals"></a><span data-ttu-id="80ad3-223">Цели</span><span class="sxs-lookup"><span data-stu-id="80ad3-223">Goals</span></span>

<span data-ttu-id="80ad3-224">В этом пошаговом руководстве показаны основные сценарии, при развертывании контейнеров Windows в экземпляры контейнеров Azure (ACI) и как можно развертывать приложения eShopModernizing в ACI.</span><span class="sxs-lookup"><span data-stu-id="80ad3-224">This walkthrough shows you the main scenarios when deploying Windows Containers to Azure Container Instances (ACI) and how you can deploy eShopModernizing Apps into ACI.</span></span>

### <a name="scenarios"></a><span data-ttu-id="80ad3-225">Сценарии</span><span class="sxs-lookup"><span data-stu-id="80ad3-225">Scenarios</span></span>

<span data-ttu-id="80ad3-226">Может существовать варианты о развертывании приложений eShopModernizing в ACI, таких как развертывание одного или всех приложений (приложение MVC, веб-форм приложение или служба WCF).</span><span class="sxs-lookup"><span data-stu-id="80ad3-226">There can be variations about deploying the eShopModernizing apps into ACI such as deploying just one or all of the apps (MVC app, WebForms app or WCF service).</span></span> <span data-ttu-id="80ad3-227">В следующем сценарии показано ниже вы увидите приложение ASP.NET MVC, а также контейнер SQL Server, из них развертываются как контейнеры в ACI (экземпляры контейнеров Azure).</span><span class="sxs-lookup"><span data-stu-id="80ad3-227">In the following scenario shown below you can see the ASP.NET MVC app plus the SQL Server container both of them deployed as containers into ACI (Azure Container Instances).</span></span>

![Развертывания в ACI из среды разработки](./media/image5-3.5.6.png)

### <a name="benefits"></a><span data-ttu-id="80ad3-229">Преимущества</span><span class="sxs-lookup"><span data-stu-id="80ad3-229">Benefits</span></span>

<span data-ttu-id="80ad3-230">Экземпляры контейнеров Azure позволяет легко создавать и управлять ими контейнеры Docker в Azure, без необходимости подготавливать виртуальные машины или службы более высокого уровня.</span><span class="sxs-lookup"><span data-stu-id="80ad3-230">Azure Container Instances makes it easy to create and manage Docker containers in Azure, without having to provision virtual machines or adopt a higher-level service.</span></span> <span data-ttu-id="80ad3-231">Экземпляры контейнеров Azure можно напрямую развернуть контейнер Windows в Azure и предоставите к нему доступ в Интернете по полное доменное имя (FQDN) за считанные секунды (при условии, что у вас Готово образа контейнера Windows в реестр Docker, например центр Docker или контейнера Azure Реестр).</span><span class="sxs-lookup"><span data-stu-id="80ad3-231">With ACI, you can directly deploy a Windows container in Azure and expose it to the internet with a fully qualified domain name (FQDN) in a matter of seconds (Provided that you have the Windows Container image ready in a Docker registry like Docker Hub or Azure Container Registry).</span></span>

### <a name="considerations"></a><span data-ttu-id="80ad3-232">Особенности</span><span class="sxs-lookup"><span data-stu-id="80ad3-232">Considerations</span></span>

<span data-ttu-id="80ad3-233">Развертывание контейнеров Windows с помощью либо полной версии .NET Framework или ASP.NET или SQL Server в экземплярах контейнеров Azure (ACI) не является довольно быстро, как развертывание обычный узел Docker (например, Windows Server 2016 с контейнерами Windows), так как это должно быть образ Docker загружаются (вытащенные из реестра Docker) каждый раз, и размеры образа контейнера SQL (15.1 ГБ) и образ контейнера ASP.NET (13.9 ГБ) по значительно больших, однако гораздо дешевле, чем сохранение (без возможности восстановления через собственный узел docker Windows Server 2016 с виртуальной Машиной контейнеры Windows в Azure) тем более всего orchestrator как Kubernetes в Azure (AKS или ACS) или Azure Service Fabric, то есть, с другой стороны, отличный выбор для развертывания в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="80ad3-233">Deploying Windows Containers with either full .NET Framework / ASP.NET or SQL Server into Azure Container Instances (ACI) is not quite as fast as deploying to a regular Docker Host (like a Windows Server 2016 with Windows Containers) because the Docker image has to be downloaded (pulled from the Docker registry) every time and the sizes of the SQL container image (15.1 GB) and the ASP.NET container image (13.9 GB) are significantly large, however it is much cheaper than maintaining your own docker host (permanently on-line Windows Server 2016 with Windows Containers VM in Azure) not to mention a whole orchestrator like Kubernetes in Azure (AKS/ACS) or Azure Service Fabric which are, on the other hand, great choices for production deployments.</span></span>

<span data-ttu-id="80ad3-234">Как основной заключение экземпляры контейнеров Azure является очень привлекательным вариантом для сценариев разработки и тестирования, а также для конвейеров CI/CD.</span><span class="sxs-lookup"><span data-stu-id="80ad3-234">As main conclusion, using Azure Container Instances is a very compelling option for Dev/Test scenarios and for CI/CD pipelines.</span></span>

## <a name="next-steps"></a><span data-ttu-id="80ad3-235">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="80ad3-235">Next steps</span></span>

<span data-ttu-id="80ad3-236">Это содержимое более подробный обзор на вики-сайте GitHub:</span><span class="sxs-lookup"><span data-stu-id="80ad3-236">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)TBD)

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="80ad3-237">Пошаговое руководство. 5. Развертывание приложений на базе контейнеров Windows в Kubernetes в службе контейнеров Azure</span><span class="sxs-lookup"><span data-stu-id="80ad3-237">Walkthrough 5: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="80ad3-238">Доступность техническим руководством</span><span class="sxs-lookup"><span data-stu-id="80ad3-238">Technical walkthrough availability</span></span>

<span data-ttu-id="80ad3-239">Полной технической руководство доступно в репозитории GitHub eShopModernizing вики-сайте:</span><span class="sxs-lookup"><span data-stu-id="80ad3-239">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)>

### <a name="overview"></a><span data-ttu-id="80ad3-240">Обзор</span><span class="sxs-lookup"><span data-stu-id="80ad3-240">Overview</span></span>

<span data-ttu-id="80ad3-241">Приложения, основанный на контейнеры Windows быстро потребуется использовать платформы, еще больше сейчас переход от виртуальных машин IaaS.</span><span class="sxs-lookup"><span data-stu-id="80ad3-241">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="80ad3-242">Это требуется легко достичь высокого уровня масштабируемости и лучше автоматизировать масштабируемость и для значительное улучшение автоматического развертывания и управления версиями.</span><span class="sxs-lookup"><span data-stu-id="80ad3-242">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="80ad3-243">Эти цели можно добиться с помощью оркестратора [Kubernetes](https://kubernetes.io/), которые доступны в [службы контейнеров Azure](https://azure.microsoft.com/services/container-service/).</span><span class="sxs-lookup"><span data-stu-id="80ad3-243">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="80ad3-244">Цели</span><span class="sxs-lookup"><span data-stu-id="80ad3-244">Goals</span></span>

<span data-ttu-id="80ad3-245">Цель этого пошагового руководства — Узнайте, как развернуть приложение на основе контейнера Windows в Kubernetes (также называется *K8s*) в службе контейнеров Azure.</span><span class="sxs-lookup"><span data-stu-id="80ad3-245">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="80ad3-246">Развертывание в Kubernetes с нуля осуществляется в два этапа.</span><span class="sxs-lookup"><span data-stu-id="80ad3-246">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1. <span data-ttu-id="80ad3-247">Развертывание кластера Kubernetes в службе контейнеров Azure.</span><span class="sxs-lookup"><span data-stu-id="80ad3-247">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2. <span data-ttu-id="80ad3-248">Развертывание приложения и связанные ресурсы в кластере Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="80ad3-248">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="80ad3-249">Сценарии</span><span class="sxs-lookup"><span data-stu-id="80ad3-249">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="80ad3-250">Сценарий а. Развертывание непосредственно в кластер Kubernetes из среды разработки</span><span class="sxs-lookup"><span data-stu-id="80ad3-250">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![Развертывание непосредственно в кластере Kubernetes из среды разработки](./media/image5-7.png)

<span data-ttu-id="80ad3-252">**Рис. 5-7.**</span><span class="sxs-lookup"><span data-stu-id="80ad3-252">**Figure 5-7.**</span></span> <span data-ttu-id="80ad3-253">Развертывание непосредственно в кластере Kubernetes из среды разработки</span><span class="sxs-lookup"><span data-stu-id="80ad3-253">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="80ad3-254">Сценарий б Развертывание кластера Kubernetes из конвейеров CI/CD в службах Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="80ad3-254">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

![Развертывание кластера Kubernetes из конвейеров CI/CD в службах Azure DevOps](./media/image5-8.png)

<span data-ttu-id="80ad3-256">**Рис. 5-8.**</span><span class="sxs-lookup"><span data-stu-id="80ad3-256">**Figure 5-8.**</span></span> <span data-ttu-id="80ad3-257">Развертывание кластера Kubernetes из конвейеров CI/CD в службах Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="80ad3-257">Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="benefits"></a><span data-ttu-id="80ad3-258">Преимущества</span><span class="sxs-lookup"><span data-stu-id="80ad3-258">Benefits</span></span>

<span data-ttu-id="80ad3-259">Существует множество преимуществ для развертывания в кластере Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="80ad3-259">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="80ad3-260">Самое большое преимущество заключается в получении производственную среду, в которой можно масштабировать приложения, основанного на количество экземпляров контейнера, вы хотите использовать (inner масштабируемости в существующие узлы) и на основе числа узлов или виртуальных машин в кластере ( глобальную масштабируемость кластера).</span><span class="sxs-lookup"><span data-stu-id="80ad3-260">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="80ad3-261">Служба контейнеров Azure оптимизирует популярных средств с открытым исходным кодом и технологий специально для Azure.</span><span class="sxs-lookup"><span data-stu-id="80ad3-261">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="80ad3-262">Вы получаете открытое решение, которое обеспечивает переносимость, как для контейнеров, так и для конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="80ad3-262">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="80ad3-263">Выберите размер, количество узлов, и средства orchestrator-контейнера службы обрабатывает все остальное.</span><span class="sxs-lookup"><span data-stu-id="80ad3-263">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="80ad3-264">С помощью Kubernetes разработчики могут изменяться думать о физических и виртуальных машин, планирования ориентированную на контейнеры инфраструктуру, которая обеспечивает следующие возможности, среди прочего:</span><span class="sxs-lookup"><span data-stu-id="80ad3-264">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="80ad3-265">Приложений, основанную на несколько контейнеров</span><span class="sxs-lookup"><span data-stu-id="80ad3-265">Applications based on multiple containers</span></span>

- <span data-ttu-id="80ad3-266">Репликация экземпляров контейнеров и автоматическое масштабирование по горизонтали</span><span class="sxs-lookup"><span data-stu-id="80ad3-266">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="80ad3-267">Именование и обнаружения (например, внутренняя служба DNS)</span><span class="sxs-lookup"><span data-stu-id="80ad3-267">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="80ad3-268">Балансировка нагрузки</span><span class="sxs-lookup"><span data-stu-id="80ad3-268">Balancing loads</span></span>

- <span data-ttu-id="80ad3-269">Последовательные обновления</span><span class="sxs-lookup"><span data-stu-id="80ad3-269">Rolling updates</span></span>

- <span data-ttu-id="80ad3-270">Распространение секретов</span><span class="sxs-lookup"><span data-stu-id="80ad3-270">Distributing secrets</span></span>

- <span data-ttu-id="80ad3-271">Проверки работоспособности приложения</span><span class="sxs-lookup"><span data-stu-id="80ad3-271">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="80ad3-272">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="80ad3-272">Next steps</span></span>

<span data-ttu-id="80ad3-273">Это содержимое более подробный обзор на вики-сайте GitHub: <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)></span><span class="sxs-lookup"><span data-stu-id="80ad3-273">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)></span></span>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a><span data-ttu-id="80ad3-274">Пошаговое руководство. 6. Развертывание приложений на базе контейнеров Windows в Azure Service Fabric</span><span class="sxs-lookup"><span data-stu-id="80ad3-274">Walkthrough 6: Deploy your Windows Containers-based apps to Azure Service Fabric</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="80ad3-275">Доступность техническим руководством</span><span class="sxs-lookup"><span data-stu-id="80ad3-275">Technical walkthrough availability</span></span>

<span data-ttu-id="80ad3-276">Полной технической руководство доступно в репозитории GitHub eShopModernizing вики-сайте:</span><span class="sxs-lookup"><span data-stu-id="80ad3-276">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)>

### <a name="overview"></a><span data-ttu-id="80ad3-277">Обзор</span><span class="sxs-lookup"><span data-stu-id="80ad3-277">Overview</span></span>

<span data-ttu-id="80ad3-278">Приложение быстро по контейнерам Windows должен использовать платформы, еще больше сейчас переход от виртуальных машин IaaS.</span><span class="sxs-lookup"><span data-stu-id="80ad3-278">An application based on Windows Containers quickly needs to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="80ad3-279">Это требуется легко достичь высокого уровня масштабируемости и лучше автоматизировать масштабируемость и для значительное улучшение автоматического развертывания и управления версиями.</span><span class="sxs-lookup"><span data-stu-id="80ad3-279">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="80ad3-280">С помощью оркестратора Azure Service Fabric, которая находится в облаке Azure, но также можно использовать в локальной, или даже в разных общедоступного облака, можно достичь этих целей.</span><span class="sxs-lookup"><span data-stu-id="80ad3-280">You can achieve these goals by using the orchestrator Azure Service Fabric, which is available in the Azure cloud, but also available to use on-premises, or even in a different public cloud.</span></span>

### <a name="goals"></a><span data-ttu-id="80ad3-281">Цели</span><span class="sxs-lookup"><span data-stu-id="80ad3-281">Goals</span></span>

<span data-ttu-id="80ad3-282">В этом пошаговом руководстве предназначена для того, чтобы узнать, как развернуть приложение на основе контейнера Windows в кластер Service Fabric в Azure.</span><span class="sxs-lookup"><span data-stu-id="80ad3-282">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to a Service Fabric cluster in Azure.</span></span> <span data-ttu-id="80ad3-283">Развертывание в Service Fabric с нуля осуществляется в два этапа.</span><span class="sxs-lookup"><span data-stu-id="80ad3-283">Deploying to Service Fabric from scratch is a two-step process:</span></span>

1. <span data-ttu-id="80ad3-284">Развертывание кластера Service Fabric в Azure (или другую среду).</span><span class="sxs-lookup"><span data-stu-id="80ad3-284">Deploy a Service Fabric cluster to Azure (or to a different environment).</span></span>

2. <span data-ttu-id="80ad3-285">Развертывание приложения и связанные ресурсы в кластере Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="80ad3-285">Deploy the application and related resources to the Service Fabric cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="80ad3-286">Сценарии</span><span class="sxs-lookup"><span data-stu-id="80ad3-286">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a><span data-ttu-id="80ad3-287">Сценарий а. Развертывание непосредственно в кластер Service Fabric из среды разработки</span><span class="sxs-lookup"><span data-stu-id="80ad3-287">Scenario A: Deploy directly to a Service Fabric cluster from a dev environment</span></span>

![Развертывание непосредственно в кластере Service Fabric из среды разработки](./media/image5-9.png)

> <span data-ttu-id="80ad3-289">**Рис. 5-9.**</span><span class="sxs-lookup"><span data-stu-id="80ad3-289">**Figure 5-9.**</span></span> <span data-ttu-id="80ad3-290">Развертывание непосредственно в кластере Service Fabric из среды разработки</span><span class="sxs-lookup"><span data-stu-id="80ad3-290">Deploy directly to a Service Fabric cluster from a development environment</span></span>

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="80ad3-291">Сценарий б Развертывание кластера Service Fabric из конвейеров CI/CD в службах Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="80ad3-291">Scenario B: Deploy to a Service Fabric cluster from CI/CD pipelines in Azure DevOps Services</span></span>

![Развертывание кластера Service Fabric из конвейеров CI/CD в службах Azure DevOps](./media/image5-10.png)

<span data-ttu-id="80ad3-293">**Рис. 5-10.**</span><span class="sxs-lookup"><span data-stu-id="80ad3-293">**Figure 5-10.**</span></span> <span data-ttu-id="80ad3-294">Развертывание кластера Service Fabric из конвейеров CI/CD в службах Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="80ad3-294">Deploy to a Service Fabric cluster from CI/CD pipelines in Azure DevOps Services</span></span>

## <a name="benefits"></a><span data-ttu-id="80ad3-295">Преимущества</span><span class="sxs-lookup"><span data-stu-id="80ad3-295">Benefits</span></span>

<span data-ttu-id="80ad3-296">Преимущества развертывания в кластере Service Fabric аналогичны преимущества использования Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="80ad3-296">The benefits of deploying to a cluster in Service Fabric are similar to the benefits of using Kubernetes.</span></span> <span data-ttu-id="80ad3-297">Одно различие заключается в что Service Fabric — более развитым рабочей среде для приложений Windows, по сравнению с Kubernetes, который находится на этапе бета-версии для контейнеров Windows в Kubernetes версии 1.9 (декабрь 2017 г.).</span><span class="sxs-lookup"><span data-stu-id="80ad3-297">One difference, though, is that Service Fabric is a more mature production environment for Windows applications compared to Kubernetes, which is in a beta phase for Windows Containers in Kubernetes version 1.9 (December 2017).</span></span> <span data-ttu-id="80ad3-298">Kubernetes — это более развитым среда для Linux.</span><span class="sxs-lookup"><span data-stu-id="80ad3-298">Kubernetes is a more mature environment for Linux.</span></span>

<span data-ttu-id="80ad3-299">Является основным преимуществом использования Azure Service Fabric, вы получаете производственную среду, в которой можно масштабировать приложения, основанного на количество экземпляров контейнера, вы хотите использовать (inner масштабируемости в существующие узлы) и на основе числа узлы или виртуальные машины в кластере (глобальную масштабируемость кластера).</span><span class="sxs-lookup"><span data-stu-id="80ad3-299">The main benefit of using Azure Service Fabric is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="80ad3-300">Azure Service Fabric обеспечивает переносимость как контейнеров, так и для конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="80ad3-300">Azure Service Fabric offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="80ad3-301">Может иметь Service Fabric в кластере в Azure, либо установить локально в собственном центре обработки данных.</span><span class="sxs-lookup"><span data-stu-id="80ad3-301">You can have a Service Fabric cluster in Azure, or install it on-premises in your own datacenter.</span></span> <span data-ttu-id="80ad3-302">Кластер Service Fabric можно даже установить в другом облаке, например [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).</span><span class="sxs-lookup"><span data-stu-id="80ad3-302">You can even install a Service Fabric cluster in a different cloud, like [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).</span></span>

<span data-ttu-id="80ad3-303">С Service Fabric разработчики могут изменяться думать о физических и виртуальных машин планирования ориентированную на контейнеры инфраструктуру, которая обеспечивает следующие возможности, среди прочего:</span><span class="sxs-lookup"><span data-stu-id="80ad3-303">With Service Fabric, developers can progress from thinking about physical and virtual machines to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="80ad3-304">Приложений, основанную на несколько контейнеров.</span><span class="sxs-lookup"><span data-stu-id="80ad3-304">Applications based on multiple containers.</span></span>

- <span data-ttu-id="80ad3-305">Репликация экземпляров контейнеров и автоматическое масштабирование по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="80ad3-305">Replicating container instances and horizontal autoscaling.</span></span>

- <span data-ttu-id="80ad3-306">Присвоение имени и обнаружения (например, внутренняя служба DNS).</span><span class="sxs-lookup"><span data-stu-id="80ad3-306">Naming and discovering (for example, internal DNS).</span></span>

- <span data-ttu-id="80ad3-307">Балансировка нагрузки.</span><span class="sxs-lookup"><span data-stu-id="80ad3-307">Balancing loads.</span></span>

- <span data-ttu-id="80ad3-308">Последовательного обновления.</span><span class="sxs-lookup"><span data-stu-id="80ad3-308">Rolling updates.</span></span>

- <span data-ttu-id="80ad3-309">Распространение секреты.</span><span class="sxs-lookup"><span data-stu-id="80ad3-309">Distributing secrets.</span></span>

- <span data-ttu-id="80ad3-310">Проверки работоспособности приложения.</span><span class="sxs-lookup"><span data-stu-id="80ad3-310">Application health checks.</span></span>

<span data-ttu-id="80ad3-311">Следующие возможности являются взаимоисключающими в Service Fabric (по сравнению с других оркестраторов):</span><span class="sxs-lookup"><span data-stu-id="80ad3-311">The following capabilities are exclusive in Service Fabric (compared to other orchestrators):</span></span>

- <span data-ttu-id="80ad3-312">Возможности служб с отслеживанием состояния, через модель приложения Reliable Services.</span><span class="sxs-lookup"><span data-stu-id="80ad3-312">Stateful services capability, through the Reliable Services application model.</span></span>

- <span data-ttu-id="80ad3-313">Шаблон субъектов, с помощью модели приложения Reliable Actors.</span><span class="sxs-lookup"><span data-stu-id="80ad3-313">Actors pattern, through the Reliable Actors application model.</span></span>

- <span data-ttu-id="80ad3-314">Развертывание базовую процессов, а также контейнеры Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="80ad3-314">Deploy bare-bone processes, in addition to Windows or Linux containers.</span></span>

- <span data-ttu-id="80ad3-315">Расширенные последовательные обновления и проверки работоспособности.</span><span class="sxs-lookup"><span data-stu-id="80ad3-315">Advanced rolling updates and health checks.</span></span>

### <a name="next-steps"></a><span data-ttu-id="80ad3-316">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="80ad3-316">Next steps</span></span>

<span data-ttu-id="80ad3-317">Это содержимое более подробный обзор на вики-сайте GitHub:</span><span class="sxs-lookup"><span data-stu-id="80ad3-317">Explore this content more in-depth on the GitHub wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)>

> [!div class="step-by-step"]
> <span data-ttu-id="80ad3-318">[Назад](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
> [Вперед](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="80ad3-318">[Previous](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span>
