---
title: Обзор пошаговых руководств и технических описаний по началу работы
description: Модернизация существующих приложений .NET с помощью облака Azure и контейнеров Windows | Пошаговые руководства и Технический обзор работы
ms.date: 04/28/2018
ms.openlocfilehash: 0b0dbae999e31150a55368d669f718eea0925d51
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758784"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="fadea-103">Обзор пошаговых руководств и технических описаний по началу работы</span><span class="sxs-lookup"><span data-stu-id="fadea-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="fadea-104">Чтобы ограничить размер этой электронной книге, Дополнительная техническая документация и полные руководства содержат были доступны в репозитории GitHub.</span><span class="sxs-lookup"><span data-stu-id="fadea-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="fadea-105">Online ряд пошаговых руководств, описанный в этой главе рассматриваются пошаговой настройки нескольких сред, основанных на контейнеры Windows и развертывания в Azure.</span><span class="sxs-lookup"><span data-stu-id="fadea-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="fadea-106">Что каждого пошагового руководства о его цели и высокоуровневые концепции и предоставляет схему задачи, которые участвуют в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="fadea-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="fadea-107">Вы можете получить пошаговые руководства, самостоятельно в *eShopModernizing* вики-сайт репозитория GitHub приложения в <https://github.com/dotnet-architecture/eShopModernizing/wiki>.</span><span class="sxs-lookup"><span data-stu-id="fadea-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at <https://github.com/dotnet-architecture/eShopModernizing/wiki>.</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="fadea-108">Список техническим руководством</span><span class="sxs-lookup"><span data-stu-id="fadea-108">Technical walkthrough list</span></span>

<span data-ttu-id="fadea-109">Следующие пошаговые руководства начало предоставить согласованный и всесторонний обзор Технические рекомендации для примеров приложений, которые можно перенести и shift с помощью контейнеров, а затем переместите с помощью нескольких вариантов развертывания в Azure.</span><span class="sxs-lookup"><span data-stu-id="fadea-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="fadea-110">Каждый из приведенных ниже пошаговых руководств использует новые примеры eShopLegacy и eShopModernizing приложений, которые доступны на сайте GitHub в <https://github.com/dotnet-architecture/eShopModernizing>.</span><span class="sxs-lookup"><span data-stu-id="fadea-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at <https://github.com/dotnet-architecture/eShopModernizing>.</span></span>

- <span data-ttu-id="fadea-111">**Обзор eShop устаревших приложений (приложения для базовых показателей для модернизации)**</span><span class="sxs-lookup"><span data-stu-id="fadea-111">**Tour of eShop legacy apps (baseline apps to modernize)**</span></span>

- <span data-ttu-id="fadea-112">**Контейнеризация существующего веб-приложений ASP.NET (веб-форм и MVC) с контейнерами Windows**</span><span class="sxs-lookup"><span data-stu-id="fadea-112">**Containerize your existing ASP.NET web apps (WebForms & MVC) with Windows Containers**</span></span>

- <span data-ttu-id="fadea-113">**Контейнеризация существующего служб WCF (N-уровневого приложения) с контейнерами Windows**</span><span class="sxs-lookup"><span data-stu-id="fadea-113">**Containerize your existing WCF services (N-Tier apps) with Windows Containers**</span></span>

- <span data-ttu-id="fadea-114">**Развертывание приложения на базе контейнеров Windows в виртуальных машинах Azure**</span><span class="sxs-lookup"><span data-stu-id="fadea-114">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="fadea-115">**Развертывание приложений на базе контейнеров Windows в Kubernetes в службе контейнеров Azure**</span><span class="sxs-lookup"><span data-stu-id="fadea-115">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="fadea-116">Пошаговое руководство 1. Обзор приложений прежних версий eShop</span><span class="sxs-lookup"><span data-stu-id="fadea-116">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="fadea-117">Доступность техническим руководством</span><span class="sxs-lookup"><span data-stu-id="fadea-117">Technical walkthrough availability</span></span>

<span data-ttu-id="fadea-118">Полной технической руководство доступно в репозитории GitHub eShopModernizing вики-сайте:</span><span class="sxs-lookup"><span data-stu-id="fadea-118">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="fadea-119">Пошаговые руководства вики-сайте eShopModernizing</span><span class="sxs-lookup"><span data-stu-id="fadea-119">eShopModernizing wiki walkthroughs</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a><span data-ttu-id="fadea-120">Обзор</span><span class="sxs-lookup"><span data-stu-id="fadea-120">Overview</span></span>

<span data-ttu-id="fadea-121">В этом пошаговом руководстве вы можете изучить начальная реализация из трех примеров приложений прежних версий.</span><span class="sxs-lookup"><span data-stu-id="fadea-121">In this walkthrough, you can explore the initial implementation of three sample legacy applications.</span></span> <span data-ttu-id="fadea-122">Первые два примера веб-приложений имеют монолитная архитектура и были созданы с помощью Классическая ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="fadea-122">The first two sample web apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="fadea-123">Одно приложение на базе ASP.NET 4.x MVC; второе приложение зависит от веб-форм ASP.NET 4.x.</span><span class="sxs-lookup"><span data-stu-id="fadea-123">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span>
<span data-ttu-id="fadea-124">Третий приложение является приложением уровня 3, состоящих из клиентского приложения WinForms и на стороне сервера [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) службы.</span><span class="sxs-lookup"><span data-stu-id="fadea-124">The third app is a 3-Tier app composed by a client WinForms app and a server-side [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) service.</span></span>

<span data-ttu-id="fadea-125">Все эти приложения можно найти по адресу [репозиторий GitHub eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="fadea-125">All these applications are available at the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

### <a name="goals"></a><span data-ttu-id="fadea-126">Цели</span><span class="sxs-lookup"><span data-stu-id="fadea-126">Goals</span></span>

<span data-ttu-id="fadea-127">Основная цель этого пошагового руководства, достаточно ознакомиться с этими приложениями и с их кода и конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fadea-127">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="fadea-128">Можно настроить приложения, создавать и использовать фиктивные данные без использования базы данных SQL, для целей тестирования.</span><span class="sxs-lookup"><span data-stu-id="fadea-128">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="fadea-129">Это необязательная конфигурация основана на внедрение зависимостей, несвязанно.</span><span class="sxs-lookup"><span data-stu-id="fadea-129">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario-1-aspnet-web-apps"></a><span data-ttu-id="fadea-130">Сценарий 1. Веб-приложений ASP.NET</span><span class="sxs-lookup"><span data-stu-id="fadea-130">Scenario 1: ASP.NET Web apps</span></span>

<span data-ttu-id="fadea-131">На рисунке ниже показан простой сценарий исходного устаревших веб-приложений ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="fadea-131">The figure below shows the simple scenario of the original legacy ASP.NET web applications.</span></span>

![Простая архитектура сценария исходного устаревших веб-приложений ASP.NET](./media/image5-1.png)

<span data-ttu-id="fadea-133">С точки зрения бизнеса домена оба приложения предлагают одного каталога функции управления.</span><span class="sxs-lookup"><span data-stu-id="fadea-133">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="fadea-134">Члены группы enterprise eShop использует приложение для просмотра и изменения каталога товаров.</span><span class="sxs-lookup"><span data-stu-id="fadea-134">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span>

<span data-ttu-id="fadea-135">На следующем рисунке показано на снимках экрана первоначального приложения.</span><span class="sxs-lookup"><span data-stu-id="fadea-135">The next figure shows the initial app screenshots.</span></span>

![Приложения ASP.NET MVC и веб-форм ASP.NET (существующими или устаревшими технологии)](./media/image5-2.png)

<span data-ttu-id="fadea-137">Зависимости в ASP.NET 4.x или более ранних версий (либо для MVC или веб-форм) означает, что эти приложения не будут работать на .NET Core, если код полностью переписан с помощью ASP.NET Core MVC.</span><span class="sxs-lookup"><span data-stu-id="fadea-137">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won’t run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span>

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a><span data-ttu-id="fadea-138">Сценарий 2. Служба WCF и клиентское приложение WinForms (3-уровневое приложение)</span><span class="sxs-lookup"><span data-stu-id="fadea-138">Scenario 2: WCF service and WinForms client app (3-Tier app)</span></span>

<span data-ttu-id="fadea-139">На рисунке ниже показан простой сценарий исходного 3-уровневого приложения прежних версий.</span><span class="sxs-lookup"><span data-stu-id="fadea-139">The figure below shows the simple scenario of the original 3-Tier legacy application.</span></span>

![Сценарий простой архитектуры оригинальное прежних версий 3-уровневое приложение со службой WCF и клиентского приложения WinForms](./media/image5-1.5.png)

### <a name="benefits"></a><span data-ttu-id="fadea-141">Преимущества</span><span class="sxs-lookup"><span data-stu-id="fadea-141">Benefits</span></span>

<span data-ttu-id="fadea-142">Преимущества в этом пошаговом руководстве, просты: Просто ознакомиться с кодом и начального приложения.</span><span class="sxs-lookup"><span data-stu-id="fadea-142">The benefits of this walkthrough are simple: Just get familiar with the code and initial apps.</span></span>

### <a name="next-steps"></a><span data-ttu-id="fadea-143">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="fadea-143">Next steps</span></span>

<span data-ttu-id="fadea-144">Это содержимое более подробный обзор на вики-сайте GitHub:</span><span class="sxs-lookup"><span data-stu-id="fadea-144">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="fadea-145">Обзор на базовых ASP.NET MVC и веб-форм «устаревшего» приложений</span><span class="sxs-lookup"><span data-stu-id="fadea-145">Tour on the baseline ASP.NET MVC and Web Forms “legacy” apps</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [<span data-ttu-id="fadea-146">Обзор базовая служба WCF и «устаревшего» приложение WinForms (3-уровневой)</span><span class="sxs-lookup"><span data-stu-id="fadea-146">Tour on the baseline WCF service and WinForms (3-Tier) “legacy” app</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="fadea-147">Пошаговое руководство 2. Контейнеризация существующие приложения .NET с контейнерами Windows</span><span class="sxs-lookup"><span data-stu-id="fadea-147">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="overview"></a><span data-ttu-id="fadea-148">Обзор</span><span class="sxs-lookup"><span data-stu-id="fadea-148">Overview</span></span>

<span data-ttu-id="fadea-149">Используйте контейнеры Windows для улучшения развертывания существующих приложений .NET, как на основе MVC, веб-форм или WCF, в рабочей среде, разработки, среды и тестирования.</span><span class="sxs-lookup"><span data-stu-id="fadea-149">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="fadea-150">Цели</span><span class="sxs-lookup"><span data-stu-id="fadea-150">Goals</span></span>

<span data-ttu-id="fadea-151">Цель данного руководства — Показать, несколько вариантов для запуска существующего приложения .NET Framework в контейнерах.</span><span class="sxs-lookup"><span data-stu-id="fadea-151">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="fadea-152">Можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fadea-152">You can:</span></span>

- <span data-ttu-id="fadea-153">Упаковывайте приложения в контейнеры с помощью [инструменты Visual Studio 2017 для Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 или более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="fadea-153">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="fadea-154">Упаковывайте приложения в контейнеры, вручную добавив [Dockerfile](https://docs.docker.com/engine/reference/builder/), а затем с помощью [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span><span class="sxs-lookup"><span data-stu-id="fadea-154">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="fadea-155">Упаковывайте приложения в контейнеры с помощью [Img2Docker](https://github.com/docker/communitytools-image2docker-win) инструмента (инструмент с открытым кодом от Docker).</span><span class="sxs-lookup"><span data-stu-id="fadea-155">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="fadea-156">В этом пошаговом руководстве рассматриваются инструменты Visual Studio 2017 для Docker подхода, но эти два подхода довольно похожи отношении с помощью файлов Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="fadea-156">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario-1-containerized-aspnet-web-apps"></a><span data-ttu-id="fadea-157">Сценарий 1. Контейнерные веб-приложений ASP.NET</span><span class="sxs-lookup"><span data-stu-id="fadea-157">Scenario 1: Containerized ASP.NET web apps</span></span>

<span data-ttu-id="fadea-158">На следующем рисунке показан сценарий для контейнерных eShop устаревших веб-приложений, приложений.</span><span class="sxs-lookup"><span data-stu-id="fadea-158">Figure below shows the scenario for containerized eShop legacy web apps applications.</span></span>

![Схема упрощенной архитектуры контейнерных приложений ASP.NET в среде разработки](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a><span data-ttu-id="fadea-160">Сценарий 2. Контейнерная служба WCF</span><span class="sxs-lookup"><span data-stu-id="fadea-160">Scenario 2: Containerized WCF service</span></span>

<span data-ttu-id="fadea-161">На следующем рисунке показан сценарий для трехуровневого приложения с контейнерная служба WCF.</span><span class="sxs-lookup"><span data-stu-id="fadea-161">Figure below shows the scenario for a 3-Tier app with a containerized WCF service.</span></span>

![Упрощенная схема архитектуры контейнерные службы WCF в среде разработки](./media/image5-3.5.png)

### <a name="benefits"></a><span data-ttu-id="fadea-163">Преимущества</span><span class="sxs-lookup"><span data-stu-id="fadea-163">Benefits</span></span>

<span data-ttu-id="fadea-164">Существуют преимущества запуска монолитного приложения в контейнере.</span><span class="sxs-lookup"><span data-stu-id="fadea-164">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="fadea-165">Во-первых можно создать образ для приложения.</span><span class="sxs-lookup"><span data-stu-id="fadea-165">First, you create an image for the application.</span></span> <span data-ttu-id="fadea-166">С этого момента каждое развертывание будет производиться в одной среде.</span><span class="sxs-lookup"><span data-stu-id="fadea-166">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="fadea-167">Каждый контейнер использует одну и ту же версию ОС, имеет ту же версию установить зависимости, использует ту же версию .NET framework и создается с тем же способом.</span><span class="sxs-lookup"><span data-stu-id="fadea-167">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="fadea-168">По сути вы управляете зависимости приложения с помощью образа Docker.</span><span class="sxs-lookup"><span data-stu-id="fadea-168">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="fadea-169">Зависимости перемещаются вместе с приложением при развертывании контейнеров.</span><span class="sxs-lookup"><span data-stu-id="fadea-169">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="fadea-170">Дополнительным преимуществом является то, что разработчики могут запустить приложение в согласованную среду, которая предоставляется в контейнерах Windows.</span><span class="sxs-lookup"><span data-stu-id="fadea-170">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="fadea-171">Проблемы, которые отображаются только в определенных версиях может быть замечена немедленно, а не отображать в промежуточной или рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="fadea-171">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="fadea-172">Различия в средах разработки, используемых членами группы разработки так важны при запуске приложения в контейнерах.</span><span class="sxs-lookup"><span data-stu-id="fadea-172">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="fadea-173">Контейнерные приложения также имеют flatter кривую горизонтального масштабирования.</span><span class="sxs-lookup"><span data-stu-id="fadea-173">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="fadea-174">Контейнерных приложений обеспечивают возможность иметь несколько экземпляров приложения и службы (с учетом контейнеры) на виртуальной Машине или физическом компьютере, по сравнению с развертываниями обычное приложение на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="fadea-174">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="fadea-175">Это преобразуется в более поздней версии плотность и требуется меньше ресурсов, особенно в том случае, при использовании оркестраторов, как Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="fadea-175">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes.</span></span>

<span data-ttu-id="fadea-176">Создание контейнеров, в идеальной ситуации, не требует внесения изменений в код приложения (C\#).</span><span class="sxs-lookup"><span data-stu-id="fadea-176">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="fadea-177">В большинстве случаев нужно просто Docker развертывания метаданных файлов (файлов Dockerfile и Docker Compose).</span><span class="sxs-lookup"><span data-stu-id="fadea-177">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="fadea-178">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="fadea-178">Next steps</span></span>

<span data-ttu-id="fadea-179">Это содержимое более подробный обзор на вики-сайте GitHub:</span><span class="sxs-lookup"><span data-stu-id="fadea-179">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="fadea-180">Как контейнеризовать веб-приложения .NET Framework с контейнерами Windows и Docker</span><span class="sxs-lookup"><span data-stu-id="fadea-180">How to containerize the .NET Framework web apps with Windows Containers and Docker</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [<span data-ttu-id="fadea-181">Добавление поддержки Docker для службы WCF</span><span class="sxs-lookup"><span data-stu-id="fadea-181">Adding Docker Support to a WCF service</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="fadea-182">Пошаговое руководство 3. Развертывание приложения на базе контейнеров Windows в виртуальных машинах Azure</span><span class="sxs-lookup"><span data-stu-id="fadea-182">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="fadea-183">Доступность техническим руководством</span><span class="sxs-lookup"><span data-stu-id="fadea-183">Technical walkthrough availability</span></span>

<span data-ttu-id="fadea-184">Полной технической руководство доступно в репозитории GitHub eShopModernizing вики-сайте: <https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="fadea-184">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span></span>

### <a name="overview"></a><span data-ttu-id="fadea-185">Обзор</span><span class="sxs-lookup"><span data-stu-id="fadea-185">Overview</span></span>

<span data-ttu-id="fadea-186">Развертывание на узле Docker на Windows Server 2016 виртуальной машины (ВМ) в Azure позволяет быстро настроить разработки, тестирования и промежуточной сред.</span><span class="sxs-lookup"><span data-stu-id="fadea-186">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="fadea-187">Она также предоставляет чаще всего для тест-инженеров или бизнес-пользователей, для проверки приложения.</span><span class="sxs-lookup"><span data-stu-id="fadea-187">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="fadea-188">Виртуальные машины также могут быть допустимой инфраструктуры как услуги (IaaS) рабочих средах.</span><span class="sxs-lookup"><span data-stu-id="fadea-188">VMs also can be valid Infrastructure as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="fadea-189">Цели</span><span class="sxs-lookup"><span data-stu-id="fadea-189">Goals</span></span>

<span data-ttu-id="fadea-190">Цель данного руководства — Показать, несколько альтернативных вариантов, которые возникают при развертывании контейнеров Windows на виртуальных машинах Azure, которые основаны на Windows Server 2016 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="fadea-190">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="fadea-191">Сценарии</span><span class="sxs-lookup"><span data-stu-id="fadea-191">Scenarios</span></span>

<span data-ttu-id="fadea-192">В этом пошаговом руководстве рассматриваются несколько сценариев.</span><span class="sxs-lookup"><span data-stu-id="fadea-192">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="fadea-193">Сценарий а. Развертывание виртуальной Машины Azure из dev ПК через подключение подсистемы Docker</span><span class="sxs-lookup"><span data-stu-id="fadea-193">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![Развертывание виртуальной Машины Azure из dev ПК через подключение к подсистеме Docker](./media/image5-4.png)

<span data-ttu-id="fadea-195">**Рис. 5-4.**</span><span class="sxs-lookup"><span data-stu-id="fadea-195">**Figure 5-4.**</span></span> <span data-ttu-id="fadea-196">Развертывание виртуальной Машины Azure из dev ПК через подключение к подсистеме Docker</span><span class="sxs-lookup"><span data-stu-id="fadea-196">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="fadea-197">Сценарий б Развертывание на виртуальной Машине Azure через реестр Docker</span><span class="sxs-lookup"><span data-stu-id="fadea-197">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![Развертывание на виртуальной Машине Azure через реестр Docker](./media/image5-5.png)

<span data-ttu-id="fadea-199">**Рис. 5-5.**</span><span class="sxs-lookup"><span data-stu-id="fadea-199">**Figure 5-5.**</span></span> <span data-ttu-id="fadea-200">Развертывание на виртуальной Машине Azure через реестр Docker</span><span class="sxs-lookup"><span data-stu-id="fadea-200">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="fadea-201">Сценарий C: Развертывание виртуальной Машины Azure из конвейеров CI/CD в службах Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="fadea-201">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

![Развертывание виртуальной Машины Azure из конвейеров CI/CD в службах Azure DevOps](./media/image5-6.png)

<span data-ttu-id="fadea-203">**Рис. 5-6**.</span><span class="sxs-lookup"><span data-stu-id="fadea-203">**Figure 5-6.**</span></span> <span data-ttu-id="fadea-204">Развертывание виртуальной Машины Azure из конвейеров CI/CD в службах Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="fadea-204">Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="fadea-205">Виртуальные машины Azure для контейнеров Windows</span><span class="sxs-lookup"><span data-stu-id="fadea-205">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="fadea-206">Под управлением Azure виртуальные машины для контейнеров Windows на основе Windows Server 2016, Windows 10 или более поздних версий, оба с модулем Docker, настроить.</span><span class="sxs-lookup"><span data-stu-id="fadea-206">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="fadea-207">В большинстве случаев используется Windows Server 2016, на виртуальных машинах Azure.</span><span class="sxs-lookup"><span data-stu-id="fadea-207">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="fadea-208">Azure в настоящее время предоставляет виртуальная машина с именем **Windows Server 2016 с контейнерами**.</span><span class="sxs-lookup"><span data-stu-id="fadea-208">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="fadea-209">Для испытания функции нового контейнера Windows Server с Windows Server Core или Windows Nano Server можно использовать эту виртуальную Машину.</span><span class="sxs-lookup"><span data-stu-id="fadea-209">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="fadea-210">Образы ОС контейнеров устанавливаются, и затем виртуальная машина готова к использованию с помощью Docker.</span><span class="sxs-lookup"><span data-stu-id="fadea-210">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="fadea-211">Преимущества</span><span class="sxs-lookup"><span data-stu-id="fadea-211">Benefits</span></span>

<span data-ttu-id="fadea-212">Несмотря на то, что контейнеры Windows можно развернуть для локальных Windows Server 2016 виртуальных машин, при развертывании в Azure, вы получаете более простой способ начать работу с виртуальными машинами контейнер готовые к использованию Windows Server.</span><span class="sxs-lookup"><span data-stu-id="fadea-212">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="fadea-213">Вы также получаете распространенных сетевом расположении, доступном для инженеров-испытателей и автоматического масштабирования через наборы масштабирования виртуальных машин Azure.</span><span class="sxs-lookup"><span data-stu-id="fadea-213">You also get a common online location that’s accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="fadea-214">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="fadea-214">Next steps</span></span>

<span data-ttu-id="fadea-215">Это содержимое более подробный обзор на вики-сайте GitHub:</span><span class="sxs-lookup"><span data-stu-id="fadea-215">Explore this content more in-depth on the GitHub wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a><span data-ttu-id="fadea-216">Пошаговое руководство 4. Развертывание приложений на базе контейнеров Windows в экземпляры контейнеров Azure (ACI)</span><span class="sxs-lookup"><span data-stu-id="fadea-216">Walkthrough 4: Deploy your Windows Containers-based apps to Azure Container Instances (ACI)</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="fadea-217">Доступность техническим руководством</span><span class="sxs-lookup"><span data-stu-id="fadea-217">Technical walkthrough availability</span></span>

<span data-ttu-id="fadea-218">Полной технической руководство доступно в репозитории GitHub eShopModernizing вики-сайте:</span><span class="sxs-lookup"><span data-stu-id="fadea-218">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="fadea-219">[Развертывание приложений в ACI (экземпляры контейнеров Azure)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span><span class="sxs-lookup"><span data-stu-id="fadea-219">[Deploying the Apps to ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span></span>

### <a name="overview"></a><span data-ttu-id="fadea-220">Обзор</span><span class="sxs-lookup"><span data-stu-id="fadea-220">Overview</span></span>

<span data-ttu-id="fadea-221">[Экземпляры контейнеров Azure (ACI)](https://docs.microsoft.com/azure/container-instances/) — это самый быстрый способ в среде разработки, тестирования и промежуточной контейнеры, где можно развернуть отдельные экземпляры контейнеров.</span><span class="sxs-lookup"><span data-stu-id="fadea-221">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) is the quickest way to have a Containers dev/test/staging environment where you can deploy single instances of containers.</span></span>

### <a name="goals"></a><span data-ttu-id="fadea-222">Цели</span><span class="sxs-lookup"><span data-stu-id="fadea-222">Goals</span></span>

<span data-ttu-id="fadea-223">В этом пошаговом руководстве показаны основные сценарии, при развертывании контейнеров Windows в экземпляры контейнеров Azure (ACI) и как можно развертывать приложения eShopModernizing в ACI.</span><span class="sxs-lookup"><span data-stu-id="fadea-223">This walkthrough shows you the main scenarios when deploying Windows Containers to Azure Container Instances (ACI) and how you can deploy eShopModernizing Apps into ACI.</span></span>

### <a name="scenarios"></a><span data-ttu-id="fadea-224">Сценарии</span><span class="sxs-lookup"><span data-stu-id="fadea-224">Scenarios</span></span>

<span data-ttu-id="fadea-225">Может существовать варианты о развертывании приложений eShopModernizing в ACI, таких как развертывание одного или всех приложений (приложение MVC, веб-форм приложение или служба WCF).</span><span class="sxs-lookup"><span data-stu-id="fadea-225">There can be variations about deploying the eShopModernizing apps into ACI such as deploying just one or all of the apps (MVC app, WebForms app or WCF service).</span></span> <span data-ttu-id="fadea-226">В следующем сценарии показано ниже вы увидите приложение ASP.NET MVC, а также контейнер SQL Server, из них развертываются как контейнеры в ACI (экземпляры контейнеров Azure).</span><span class="sxs-lookup"><span data-stu-id="fadea-226">In the following scenario shown below you can see the ASP.NET MVC app plus the SQL Server container both of them deployed as containers into ACI (Azure Container Instances).</span></span>

![Развертывания в ACI из среды разработки](./media/image5-3.5.6.png)

### <a name="benefits"></a><span data-ttu-id="fadea-228">Преимущества</span><span class="sxs-lookup"><span data-stu-id="fadea-228">Benefits</span></span>

<span data-ttu-id="fadea-229">Экземпляры контейнеров Azure позволяет легко создавать и управлять ими контейнеры Docker в Azure, без необходимости подготавливать виртуальные машины или службы более высокого уровня.</span><span class="sxs-lookup"><span data-stu-id="fadea-229">Azure Container Instances makes it easy to create and manage Docker containers in Azure, without having to provision virtual machines or adopt a higher-level service.</span></span> <span data-ttu-id="fadea-230">Экземпляры контейнеров Azure можно напрямую развернуть контейнер Windows в Azure и предоставите к нему доступ в Интернете по полное доменное имя (FQDN) за считанные секунды (при условии, что у вас Готово образа контейнера Windows в реестр Docker, например центр Docker или контейнера Azure Реестр).</span><span class="sxs-lookup"><span data-stu-id="fadea-230">With ACI, you can directly deploy a Windows container in Azure and expose it to the internet with a fully qualified domain name (FQDN) in a matter of seconds (Provided that you have the Windows Container image ready in a Docker registry like Docker Hub or Azure Container Registry).</span></span>

### <a name="considerations"></a><span data-ttu-id="fadea-231">Особенности</span><span class="sxs-lookup"><span data-stu-id="fadea-231">Considerations</span></span>

<span data-ttu-id="fadea-232">Развертывание контейнеров Windows с помощью либо полной версии .NET Framework или ASP.NET или SQL Server в экземплярах контейнеров Azure (ACI) не является довольно быстро, как развертывание обычный узел Docker (например, Windows Server 2016 с контейнерами Windows), так как это должно быть образ Docker загружаются (вытащенные из реестра Docker) каждый раз, и размеры образа контейнера SQL (15.1 ГБ) и образ контейнера ASP.NET (13.9 ГБ) по значительно больших, однако гораздо дешевле, чем сохранение (без возможности восстановления через собственный узел docker Windows Server 2016 с виртуальной Машиной контейнеры Windows в Azure) тем более всего orchestrator как Kubernetes в Azure (AKS) являющийся, с другой стороны, отлично подходит для рабочих развертываний.</span><span class="sxs-lookup"><span data-stu-id="fadea-232">Deploying Windows Containers with either full .NET Framework / ASP.NET or SQL Server into Azure Container Instances (ACI) is not quite as fast as deploying to a regular Docker Host (like a Windows Server 2016 with Windows Containers) because the Docker image has to be downloaded (pulled from the Docker registry) every time and the sizes of the SQL container image (15.1 GB) and the ASP.NET container image (13.9 GB) are significantly large, however it is much cheaper than maintaining your own docker host (permanently on-line Windows Server 2016 with Windows Containers VM in Azure) not to mention a whole orchestrator like Kubernetes in Azure (AKS) which is, on the other hand, a great choice for production deployments.</span></span>

<span data-ttu-id="fadea-233">Как основной заключение экземпляры контейнеров Azure является очень привлекательным вариантом для сценариев разработки и тестирования, а также для конвейеров CI/CD.</span><span class="sxs-lookup"><span data-stu-id="fadea-233">As main conclusion, using Azure Container Instances is a very compelling option for Dev/Test scenarios and for CI/CD pipelines.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fadea-234">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="fadea-234">Next steps</span></span>

<span data-ttu-id="fadea-235">Это содержимое более подробный обзор на вики-сайте GitHub:</span><span class="sxs-lookup"><span data-stu-id="fadea-235">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)TBD)

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="fadea-236">Пошаговое руководство. 5. Развертывание приложений на базе контейнеров Windows в Kubernetes в службе контейнеров Azure</span><span class="sxs-lookup"><span data-stu-id="fadea-236">Walkthrough 5: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="fadea-237">Доступность техническим руководством</span><span class="sxs-lookup"><span data-stu-id="fadea-237">Technical walkthrough availability</span></span>

<span data-ttu-id="fadea-238">Полной технической руководство доступно в репозитории GitHub eShopModernizing вики-сайте:</span><span class="sxs-lookup"><span data-stu-id="fadea-238">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)>

### <a name="overview"></a><span data-ttu-id="fadea-239">Обзор</span><span class="sxs-lookup"><span data-stu-id="fadea-239">Overview</span></span>

<span data-ttu-id="fadea-240">Приложения, основанный на контейнеры Windows быстро потребуется использовать платформы, еще больше сейчас переход от виртуальных машин IaaS.</span><span class="sxs-lookup"><span data-stu-id="fadea-240">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="fadea-241">Это требуется легко достичь высокого уровня масштабируемости и лучше автоматизировать масштабируемость и для значительное улучшение автоматического развертывания и управления версиями.</span><span class="sxs-lookup"><span data-stu-id="fadea-241">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="fadea-242">Эти цели можно добиться с помощью оркестратора [Kubernetes](https://kubernetes.io/), которые доступны в [службы контейнеров Azure](https://azure.microsoft.com/services/container-service/).</span><span class="sxs-lookup"><span data-stu-id="fadea-242">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="fadea-243">Цели</span><span class="sxs-lookup"><span data-stu-id="fadea-243">Goals</span></span>

<span data-ttu-id="fadea-244">Цель этого пошагового руководства — Узнайте, как развернуть приложение на основе контейнера Windows в Kubernetes (также называется *K8s*) в службе контейнеров Azure.</span><span class="sxs-lookup"><span data-stu-id="fadea-244">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="fadea-245">Развертывание в Kubernetes с нуля осуществляется в два этапа.</span><span class="sxs-lookup"><span data-stu-id="fadea-245">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1. <span data-ttu-id="fadea-246">Развертывание кластера Kubernetes в службе контейнеров Azure.</span><span class="sxs-lookup"><span data-stu-id="fadea-246">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2. <span data-ttu-id="fadea-247">Развертывание приложения и связанные ресурсы в кластере Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="fadea-247">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="fadea-248">Сценарии</span><span class="sxs-lookup"><span data-stu-id="fadea-248">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="fadea-249">Сценарий а. Развертывание непосредственно в кластер Kubernetes из среды разработки</span><span class="sxs-lookup"><span data-stu-id="fadea-249">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![Развертывание непосредственно в кластере Kubernetes из среды разработки](./media/image5-7.png)

<span data-ttu-id="fadea-251">**Рис. 5-7.**</span><span class="sxs-lookup"><span data-stu-id="fadea-251">**Figure 5-7.**</span></span> <span data-ttu-id="fadea-252">Развертывание непосредственно в кластере Kubernetes из среды разработки</span><span class="sxs-lookup"><span data-stu-id="fadea-252">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="fadea-253">Сценарий б Развертывание кластера Kubernetes из конвейеров CI/CD в службах Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="fadea-253">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

![Развертывание кластера Kubernetes из конвейеров CI/CD в службах Azure DevOps](./media/image5-8.png)

<span data-ttu-id="fadea-255">**Рис. 5-8.**</span><span class="sxs-lookup"><span data-stu-id="fadea-255">**Figure 5-8.**</span></span> <span data-ttu-id="fadea-256">Развертывание кластера Kubernetes из конвейеров CI/CD в службах Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="fadea-256">Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="benefits"></a><span data-ttu-id="fadea-257">Преимущества</span><span class="sxs-lookup"><span data-stu-id="fadea-257">Benefits</span></span>

<span data-ttu-id="fadea-258">Существует множество преимуществ для развертывания в кластере Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="fadea-258">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="fadea-259">Самое большое преимущество заключается в получении производственную среду, в которой можно масштабировать приложения, основанного на количество экземпляров контейнера, вы хотите использовать (inner масштабируемости в существующие узлы) и на основе числа узлов или виртуальных машин в кластере ( глобальную масштабируемость кластера).</span><span class="sxs-lookup"><span data-stu-id="fadea-259">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="fadea-260">Служба контейнеров Azure оптимизирует популярных средств с открытым исходным кодом и технологий специально для Azure.</span><span class="sxs-lookup"><span data-stu-id="fadea-260">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="fadea-261">Вы получаете открытое решение, которое обеспечивает переносимость, как для контейнеров, так и для конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="fadea-261">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="fadea-262">Выберите размер, количество узлов, и средства orchestrator-контейнера службы обрабатывает все остальное.</span><span class="sxs-lookup"><span data-stu-id="fadea-262">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="fadea-263">С помощью Kubernetes разработчики могут изменяться думать о физических и виртуальных машин, планирования ориентированную на контейнеры инфраструктуру, которая обеспечивает следующие возможности, среди прочего:</span><span class="sxs-lookup"><span data-stu-id="fadea-263">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="fadea-264">Приложений, основанную на несколько контейнеров</span><span class="sxs-lookup"><span data-stu-id="fadea-264">Applications based on multiple containers</span></span>

- <span data-ttu-id="fadea-265">Репликация экземпляров контейнеров и автоматическое масштабирование по горизонтали</span><span class="sxs-lookup"><span data-stu-id="fadea-265">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="fadea-266">Именование и обнаружения (например, внутренняя служба DNS)</span><span class="sxs-lookup"><span data-stu-id="fadea-266">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="fadea-267">Балансировка нагрузки</span><span class="sxs-lookup"><span data-stu-id="fadea-267">Balancing loads</span></span>

- <span data-ttu-id="fadea-268">Последовательные обновления</span><span class="sxs-lookup"><span data-stu-id="fadea-268">Rolling updates</span></span>

- <span data-ttu-id="fadea-269">Распространение секретов</span><span class="sxs-lookup"><span data-stu-id="fadea-269">Distributing secrets</span></span>

- <span data-ttu-id="fadea-270">Проверки работоспособности приложения</span><span class="sxs-lookup"><span data-stu-id="fadea-270">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="fadea-271">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="fadea-271">Next steps</span></span>

<span data-ttu-id="fadea-272">Это содержимое более подробный обзор на вики-сайте GitHub: <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)></span><span class="sxs-lookup"><span data-stu-id="fadea-272">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)></span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="fadea-273">[Назад](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
> [Вперед](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="fadea-273">[Previous](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span>
