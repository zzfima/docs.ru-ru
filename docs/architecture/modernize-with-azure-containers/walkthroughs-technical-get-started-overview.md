---
title: Обзор пошаговых руководств и технических описаний по началу работы
description: Модернизировать существующих приложений .NET с помощью Azure Cloud and Windows Containers | Обзор пошаговых руководств и руководства по началу работы
ms.date: 04/28/2018
ms.openlocfilehash: 190b33c4307b09bab0543d481e66ac9328074a0d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69660886"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="7d6d7-103">Обзор пошаговых руководств и технических описаний по началу работы</span><span class="sxs-lookup"><span data-stu-id="7d6d7-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="7d6d7-104">Чтобы ограничить размер электронной книги, дополнительная техническая документация и все пошаговые руководства были сделаны доступными в репозитории GitHub.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="7d6d7-105">В интерактивной серии пошаговых руководств, описанных в этой главе, описывается пошаговая Настройка нескольких сред, основанных на контейнерах Windows, и развертывание в Azure.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="7d6d7-106">В следующих разделах объясняется, что такое пошаговое руководство, его цели и концепция высокого уровня, а также приводится схема связанных задач.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="7d6d7-107">Пошаговые руководства можно получить в вики-сайте репозитория GitHub *eShopModernizing* Apps по <https://github.com/dotnet-architecture/eShopModernizing/wiki>адресу.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at <https://github.com/dotnet-architecture/eShopModernizing/wiki>.</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="7d6d7-108">Список технических пошаговых руководств</span><span class="sxs-lookup"><span data-stu-id="7d6d7-108">Technical walkthrough list</span></span>

<span data-ttu-id="7d6d7-109">Приведенные ниже пошаговые руководства по началу работы предоставляют единообразные и исчерпывающие технические рекомендации для примеров приложений, которые можно передвигать и перемещать с помощью контейнеров, а затем переместить с помощью нескольких вариантов развертывания в Azure.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="7d6d7-110">В каждом из следующих пошаговых руководств используются новые примеры приложений Ешоплегаци и eShopModernizing, которые доступны на сайте GitHub <https://github.com/dotnet-architecture/eShopModernizing>по адресу.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at <https://github.com/dotnet-architecture/eShopModernizing>.</span></span>

- <span data-ttu-id="7d6d7-111">**Обзор устаревших приложений Ешоп (базовые приложения для модернизировать)**</span><span class="sxs-lookup"><span data-stu-id="7d6d7-111">**Tour of eShop legacy apps (baseline apps to modernize)**</span></span>

- <span data-ttu-id="7d6d7-112">**Контейнеризовать существующих веб-приложений ASP.NET (WebForms & MVC) с контейнерами Windows**</span><span class="sxs-lookup"><span data-stu-id="7d6d7-112">**Containerize your existing ASP.NET web apps (WebForms & MVC) with Windows Containers**</span></span>

- <span data-ttu-id="7d6d7-113">**Контейнеризовать существующие службы WCF (N-уровневые приложения) с контейнерами Windows**</span><span class="sxs-lookup"><span data-stu-id="7d6d7-113">**Containerize your existing WCF services (N-Tier apps) with Windows Containers**</span></span>

- <span data-ttu-id="7d6d7-114">**Развертывание приложения на основе контейнеров Windows на виртуальных машинах Azure**</span><span class="sxs-lookup"><span data-stu-id="7d6d7-114">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="7d6d7-115">**Развертывание приложений на основе контейнеров Windows в Kubernetes в службе контейнеров Azure**</span><span class="sxs-lookup"><span data-stu-id="7d6d7-115">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="7d6d7-116">Пошаговое руководство 1. Обзор устаревших приложений Ешоп</span><span class="sxs-lookup"><span data-stu-id="7d6d7-116">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="7d6d7-117">Техническое руководство по доступности</span><span class="sxs-lookup"><span data-stu-id="7d6d7-117">Technical walkthrough availability</span></span>

<span data-ttu-id="7d6d7-118">Полное техническое руководство доступно на вики-сайте репозитория eShopModernizing GitHub:</span><span class="sxs-lookup"><span data-stu-id="7d6d7-118">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="7d6d7-119">Пошаговые руководства по eShopModernizing wiki</span><span class="sxs-lookup"><span data-stu-id="7d6d7-119">eShopModernizing wiki walkthroughs</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a><span data-ttu-id="7d6d7-120">Обзор</span><span class="sxs-lookup"><span data-stu-id="7d6d7-120">Overview</span></span>

<span data-ttu-id="7d6d7-121">В этом пошаговом руководстве можно изучить первоначальную реализацию трех примеров устаревших приложений.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-121">In this walkthrough, you can explore the initial implementation of three sample legacy applications.</span></span> <span data-ttu-id="7d6d7-122">Первые два примера веб-приложений имеют монолитную архитектуру и созданы с помощью классической ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-122">The first two sample web apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="7d6d7-123">Одно приложение основано на ASP.NET 4. x MVC; второе приложение основано на веб-формах ASP.NET 4. x.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-123">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span>
<span data-ttu-id="7d6d7-124">Третье приложение — это 3-уровневое приложение, состоящее из клиентского приложения WinForms и службы [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-124">The third app is a 3-Tier app composed by a client WinForms app and a server-side [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) service.</span></span>

<span data-ttu-id="7d6d7-125">Все эти приложения доступны в репозитории [EShopModernizing GitHub](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="7d6d7-125">All these applications are available at the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

### <a name="goals"></a><span data-ttu-id="7d6d7-126">Цели</span><span class="sxs-lookup"><span data-stu-id="7d6d7-126">Goals</span></span>

<span data-ttu-id="7d6d7-127">Основной целью этого пошагового руководства является простое знакомство с этими приложениями, а также с их кодом и конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-127">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="7d6d7-128">Можно настроить приложения таким образом, чтобы они создавали и использовали фиктивные данные без использования базы данных SQL в целях тестирования.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-128">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="7d6d7-129">Эта необязательная конфигурация основана на внедрении зависимостей в несвязанном виде.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-129">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario-1-aspnet-web-apps"></a><span data-ttu-id="7d6d7-130">Сценарий 1. Веб-приложения ASP.NET</span><span class="sxs-lookup"><span data-stu-id="7d6d7-130">Scenario 1: ASP.NET Web apps</span></span>

<span data-ttu-id="7d6d7-131">На рисунке ниже показан простой сценарий исходных веб-приложений ASP.NET прежних версий.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-131">The figure below shows the simple scenario of the original legacy ASP.NET web applications.</span></span>

![Простой сценарий архитектуры исходных веб-приложений ASP.NET прежних версий](./media/image5-1.png)

<span data-ttu-id="7d6d7-133">С точки зрения бизнес-домена оба приложения предлагают одни и те же функции управления каталогом.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-133">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="7d6d7-134">Участники группы Ешоп Enterprise будут использовать приложение для просмотра и редактирования каталога продуктов.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-134">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span>

<span data-ttu-id="7d6d7-135">На следующем рисунке показаны первоначальные снимки экрана приложения.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-135">The next figure shows the initial app screenshots.</span></span>

![Приложения веб-форм ASP.NET MVC и ASP.NET (существующие и устаревшие технологии)](./media/image5-2.png)

<span data-ttu-id="7d6d7-137">Зависимости в ASP.NET 4. x или более ранних версиях (для MVC или для веб-форм) означает, что эти приложения не будут работать в .NET Core, если код не будет полностью переписан с помощью ASP.NET Core MVC.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-137">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won’t run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span>

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a><span data-ttu-id="7d6d7-138">Сценарий 2. Служба WCF и клиентское приложение WinForms (3-уровневое приложение)</span><span class="sxs-lookup"><span data-stu-id="7d6d7-138">Scenario 2: WCF service and WinForms client app (3-Tier app)</span></span>

<span data-ttu-id="7d6d7-139">На рисунке ниже показан простой сценарий исходного приложения из трех уровней.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-139">The figure below shows the simple scenario of the original 3-Tier legacy application.</span></span>

![Простой сценарий архитектуры исходного приложения в 3-уровневой версии с помощью службы WCF и клиентского приложения WinForms](./media/image5-1.5.png)

### <a name="benefits"></a><span data-ttu-id="7d6d7-141">Преимущества</span><span class="sxs-lookup"><span data-stu-id="7d6d7-141">Benefits</span></span>

<span data-ttu-id="7d6d7-142">Преимущества этого пошагового руководства просты: Ознакомьтесь с кодом и начальными приложениями.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-142">The benefits of this walkthrough are simple: Just get familiar with the code and initial apps.</span></span>

### <a name="next-steps"></a><span data-ttu-id="7d6d7-143">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="7d6d7-143">Next steps</span></span>

<span data-ttu-id="7d6d7-144">Подробное изучение этого содержимого на вики-сайте GitHub:</span><span class="sxs-lookup"><span data-stu-id="7d6d7-144">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="7d6d7-145">Обзор по базовым ASP.NET MVC и веб-формам "устаревшие" приложения</span><span class="sxs-lookup"><span data-stu-id="7d6d7-145">Tour on the baseline ASP.NET MVC and Web Forms “legacy” apps</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [<span data-ttu-id="7d6d7-146">Обзор базовых служб WCF и WinForms (3-уровневого) приложения "Legacy"</span><span class="sxs-lookup"><span data-stu-id="7d6d7-146">Tour on the baseline WCF service and WinForms (3-Tier) “legacy” app</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="7d6d7-147">Пошаговое руководство 2. Контейнеризовать существующие приложения .NET с контейнерами Windows</span><span class="sxs-lookup"><span data-stu-id="7d6d7-147">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="overview"></a><span data-ttu-id="7d6d7-148">Обзор</span><span class="sxs-lookup"><span data-stu-id="7d6d7-148">Overview</span></span>

<span data-ttu-id="7d6d7-149">Используйте контейнеры Windows для улучшения развертывания существующих приложений .NET, например, на основе MVC, веб-форм или WCF, в рабочей среде, разработке и тестировании.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-149">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="7d6d7-150">Цели</span><span class="sxs-lookup"><span data-stu-id="7d6d7-150">Goals</span></span>

<span data-ttu-id="7d6d7-151">Цель этого пошагового руководства — продемонстрировать несколько вариантов для контейнеризация существующего приложения .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-151">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="7d6d7-152">Можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7d6d7-152">You can:</span></span>

- <span data-ttu-id="7d6d7-153">Контейнеризовать приложение с помощью [средств Visual studio 2017 для DOCKER](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (visual Studio 2017 или более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="7d6d7-153">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="7d6d7-154">Контейнеризовать приложение, добавив [Dockerfile](https://docs.docker.com/engine/reference/builder/)вручную, а затем используя [DOCKER CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span><span class="sxs-lookup"><span data-stu-id="7d6d7-154">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="7d6d7-155">Контейнеризовать приложение с помощью средства [Img2Docker](https://github.com/docker/communitytools-image2docker-win) (средство с открытым исходным кодом из DOCKER).</span><span class="sxs-lookup"><span data-stu-id="7d6d7-155">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="7d6d7-156">В этом пошаговом руководстве рассматривается подход к использованию средств Visual Studio 2017 для DOCKER, но два других подхода довольно похожи в отношении использования файлы dockerfile.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-156">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario-1-containerized-aspnet-web-apps"></a><span data-ttu-id="7d6d7-157">Сценарий 1. Контейнерные веб-приложения ASP.NET</span><span class="sxs-lookup"><span data-stu-id="7d6d7-157">Scenario 1: Containerized ASP.NET web apps</span></span>

<span data-ttu-id="7d6d7-158">На рисунке ниже показан сценарий для контейнерных Ешоп устаревших приложений веб-приложений.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-158">Figure below shows the scenario for containerized eShop legacy web apps applications.</span></span>

![Упрощенная схема использования контейнерных ASP.NET приложений в среде разработки](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a><span data-ttu-id="7d6d7-160">Сценарий 2. Контейнерная служба WCF</span><span class="sxs-lookup"><span data-stu-id="7d6d7-160">Scenario 2: Containerized WCF service</span></span>

<span data-ttu-id="7d6d7-161">На рисунке ниже показан сценарий для 3-уровневого приложения с контейнерной службой WCF.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-161">Figure below shows the scenario for a 3-Tier app with a containerized WCF service.</span></span>

![Упрощенная схема работы контейнерной службы WCF в среде разработки](./media/image5-3.5.png)

### <a name="benefits"></a><span data-ttu-id="7d6d7-163">Преимущества</span><span class="sxs-lookup"><span data-stu-id="7d6d7-163">Benefits</span></span>

<span data-ttu-id="7d6d7-164">Выполнение монолитного приложения в контейнере имеет свои преимущества.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-164">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="7d6d7-165">Сначала необходимо создать образ для приложения.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-165">First, you create an image for the application.</span></span> <span data-ttu-id="7d6d7-166">С этого момента каждое развертывание выполняется в одной среде.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-166">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="7d6d7-167">Каждый контейнер использует одну и ту же версию операционной системы, имеет одинаковую версию установленных зависимостей, использует одну и ту же версию .NET Framework и создается с помощью того же процесса.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-167">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="7d6d7-168">По сути, вы управляете зависимостями приложения с помощью образа DOCKER.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-168">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="7d6d7-169">Зависимости передаются вместе с приложением при развертывании контейнеров.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-169">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="7d6d7-170">Дополнительное преимущество заключается в том, что разработчики могут запускать приложение в единообразной среде, предоставляемой контейнерами Windows.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-170">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="7d6d7-171">Проблемы, возникающие только с определенными версиями, можно сразу же получить, а не отображая в промежуточной или рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-171">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="7d6d7-172">Различия в средах разработки, которые используются членами группы разработки, меньше, когда приложения работают в контейнерах.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-172">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="7d6d7-173">Контейнерные приложения также имеют кривую горизонтального масштабирования Flatter.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-173">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="7d6d7-174">Контейнерные приложения позволяют использовать больше экземпляров приложений и служб (на основе контейнеров) на ВИРТУАЛЬНОЙ машине или физическом компьютере по сравнению с обычными развертываниями приложений на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-174">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="7d6d7-175">Это преобразуется в более высокую плотность и меньшее количество требуемых ресурсов, особенно при использовании оркестрации, например Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-175">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes.</span></span>

<span data-ttu-id="7d6d7-176">В идеале в идеальном случае не требуется вносить изменения в код приложения (C\#).</span><span class="sxs-lookup"><span data-stu-id="7d6d7-176">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="7d6d7-177">В большинстве случаев требуются только файлы метаданных развертывания DOCKER (файлы файлы dockerfile и Docker Compose).</span><span class="sxs-lookup"><span data-stu-id="7d6d7-177">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="7d6d7-178">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="7d6d7-178">Next steps</span></span>

<span data-ttu-id="7d6d7-179">Подробное изучение этого содержимого на вики-сайте GitHub:</span><span class="sxs-lookup"><span data-stu-id="7d6d7-179">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="7d6d7-180">Как контейнеризовать веб-приложения .NET Framework с помощью контейнеров Windows и DOCKER</span><span class="sxs-lookup"><span data-stu-id="7d6d7-180">How to containerize the .NET Framework web apps with Windows Containers and Docker</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [<span data-ttu-id="7d6d7-181">Добавление поддержки DOCKER в службу WCF</span><span class="sxs-lookup"><span data-stu-id="7d6d7-181">Adding Docker Support to a WCF service</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="7d6d7-182">Пошаговое руководство 3. Развертывание приложения на основе контейнеров Windows на виртуальных машинах Azure</span><span class="sxs-lookup"><span data-stu-id="7d6d7-182">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="7d6d7-183">Техническое руководство по доступности</span><span class="sxs-lookup"><span data-stu-id="7d6d7-183">Technical walkthrough availability</span></span>

<span data-ttu-id="7d6d7-184">Полное техническое руководство доступно на вики-сайте репозитория eShopModernizing GitHub:<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="7d6d7-184">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span></span>

### <a name="overview"></a><span data-ttu-id="7d6d7-185">Обзор</span><span class="sxs-lookup"><span data-stu-id="7d6d7-185">Overview</span></span>

<span data-ttu-id="7d6d7-186">Развертывание на узле DOCKER на виртуальной машине Windows Server 2016 (ВМ) в Azure позволяет быстро настроить среды разработки, тестирования и промежуточного хранения.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-186">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="7d6d7-187">Она также позволяет тестерам или бизнес-пользователям часто проверять приложение.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-187">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="7d6d7-188">Виртуальные машины также могут быть допустимыми рабочими средами "инфраструктура как услуга" (IaaS).</span><span class="sxs-lookup"><span data-stu-id="7d6d7-188">VMs also can be valid Infrastructure as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="7d6d7-189">Цели</span><span class="sxs-lookup"><span data-stu-id="7d6d7-189">Goals</span></span>

<span data-ttu-id="7d6d7-190">Цель этого пошагового руководства — продемонстрировать несколько вариантов, которые вы используете при развертывании контейнеров Windows на виртуальных машинах Azure, основанных на Windows Server 2016 или более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-190">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="7d6d7-191">Сценарии</span><span class="sxs-lookup"><span data-stu-id="7d6d7-191">Scenarios</span></span>

<span data-ttu-id="7d6d7-192">В этом пошаговом руководстве рассматривается несколько сценариев.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-192">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="7d6d7-193">Сценарий а. Развертывание на виртуальной машине Azure с компьютера для разработки с помощью подключения к подсистеме DOCKER</span><span class="sxs-lookup"><span data-stu-id="7d6d7-193">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![Развертывание на виртуальной машине Azure с компьютера для разработки через подключение к подсистеме DOCKER](./media/image5-4.png)

<span data-ttu-id="7d6d7-195">**Рис. 5-4.**</span><span class="sxs-lookup"><span data-stu-id="7d6d7-195">**Figure 5-4.**</span></span> <span data-ttu-id="7d6d7-196">Развертывание на виртуальной машине Azure с компьютера для разработки через подключение к подсистеме DOCKER</span><span class="sxs-lookup"><span data-stu-id="7d6d7-196">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="7d6d7-197">Сценарий б. Развертывание на виртуальной машине Azure с помощью реестра DOCKER</span><span class="sxs-lookup"><span data-stu-id="7d6d7-197">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![Развертывание на виртуальной машине Azure с помощью реестра DOCKER](./media/image5-5.png)

<span data-ttu-id="7d6d7-199">**Рис. 5-5.**</span><span class="sxs-lookup"><span data-stu-id="7d6d7-199">**Figure 5-5.**</span></span> <span data-ttu-id="7d6d7-200">Развертывание на виртуальной машине Azure с помощью реестра DOCKER</span><span class="sxs-lookup"><span data-stu-id="7d6d7-200">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="7d6d7-201">Сценарий в: Развертывание в виртуальной машине Azure из конвейеров CI/CD в Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="7d6d7-201">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

![Развертывание в виртуальной машине Azure из конвейеров CI/CD в Azure DevOps Services](./media/image5-6.png)

<span data-ttu-id="7d6d7-203">**Рис. 5-6**.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-203">**Figure 5-6.**</span></span> <span data-ttu-id="7d6d7-204">Развертывание в виртуальной машине Azure из конвейеров CI/CD в Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="7d6d7-204">Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="7d6d7-205">Виртуальные машины Azure для контейнеров Windows</span><span class="sxs-lookup"><span data-stu-id="7d6d7-205">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="7d6d7-206">Виртуальные машины Azure для контейнеров Windows — это виртуальные машины на основе Windows Server 2016, Windows 10 или более поздних версий с установленным подсистемой DOCKER.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-206">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="7d6d7-207">В большинстве случаев Windows Server 2016 используется на виртуальных машинах Azure.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-207">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="7d6d7-208">В настоящее время Azure предоставляет виртуальную машину под названием **Windows Server 2016 с контейнерами**.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-208">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="7d6d7-209">Эту виртуальную машину можно использовать для использования новой функции контейнера Windows Server с Windows Server Core или Windows Nano Server.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-209">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="7d6d7-210">Образы ОС контейнера устанавливаются, а затем виртуальная машина готова к использованию с DOCKER.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-210">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="7d6d7-211">Преимущества</span><span class="sxs-lookup"><span data-stu-id="7d6d7-211">Benefits</span></span>

<span data-ttu-id="7d6d7-212">Несмотря на то, что контейнеры Windows можно развертывать на локальных виртуальных машинах Windows Server 2016, при развертывании в Azure вы получаете более простой способ начать работу, используя готовые к использованию виртуальные машины контейнера Windows Server.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-212">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="7d6d7-213">Вы также получаете общее сетевое расположение, доступное для инженеров-тестировщиков, и автоматическое масштабирование с помощью масштабируемых наборов виртуальных машин Azure.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-213">You also get a common online location that’s accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="7d6d7-214">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="7d6d7-214">Next steps</span></span>

<span data-ttu-id="7d6d7-215">Подробное изучение этого содержимого на вики-сайте GitHub:</span><span class="sxs-lookup"><span data-stu-id="7d6d7-215">Explore this content more in-depth on the GitHub wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a><span data-ttu-id="7d6d7-216">Пошаговое руководство 4. Развертывание приложений на основе контейнеров Windows в службе "экземпляры контейнеров Azure" (ACI)</span><span class="sxs-lookup"><span data-stu-id="7d6d7-216">Walkthrough 4: Deploy your Windows Containers-based apps to Azure Container Instances (ACI)</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="7d6d7-217">Техническое руководство по доступности</span><span class="sxs-lookup"><span data-stu-id="7d6d7-217">Technical walkthrough availability</span></span>

<span data-ttu-id="7d6d7-218">Полное техническое руководство доступно на вики-сайте репозитория eShopModernizing GitHub:</span><span class="sxs-lookup"><span data-stu-id="7d6d7-218">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="7d6d7-219">[Развертывание приложений в ACI (службы "экземпляры контейнеров Azure")](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span><span class="sxs-lookup"><span data-stu-id="7d6d7-219">[Deploying the Apps to ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span></span>

### <a name="overview"></a><span data-ttu-id="7d6d7-220">Обзор</span><span class="sxs-lookup"><span data-stu-id="7d6d7-220">Overview</span></span>

<span data-ttu-id="7d6d7-221">Служба " [экземпляры контейнеров Azure" (ACI)](https://docs.microsoft.com/azure/container-instances/) — это самый быстрый способ использовать среду разработки, тестирования и промежуточного хранения контейнеров, где можно развернуть отдельные экземпляры контейнеров.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-221">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) is the quickest way to have a Containers dev/test/staging environment where you can deploy single instances of containers.</span></span>

### <a name="goals"></a><span data-ttu-id="7d6d7-222">Цели</span><span class="sxs-lookup"><span data-stu-id="7d6d7-222">Goals</span></span>

<span data-ttu-id="7d6d7-223">В этом пошаговом руководстве показаны основные сценарии развертывания контейнеров Windows в службе "экземпляры контейнеров Azure" (ACI), а также способы развертывания приложений eShopModernizing в ACI.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-223">This walkthrough shows you the main scenarios when deploying Windows Containers to Azure Container Instances (ACI) and how you can deploy eShopModernizing Apps into ACI.</span></span>

### <a name="scenarios"></a><span data-ttu-id="7d6d7-224">Сценарии</span><span class="sxs-lookup"><span data-stu-id="7d6d7-224">Scenarios</span></span>

<span data-ttu-id="7d6d7-225">В ACI могут быть варианты развертывания приложений eShopModernizing, например развертывание только одного или всех приложений (приложение MVC, веб-формы или служба WCF).</span><span class="sxs-lookup"><span data-stu-id="7d6d7-225">There can be variations about deploying the eShopModernizing apps into ACI such as deploying just one or all of the apps (MVC app, WebForms app or WCF service).</span></span> <span data-ttu-id="7d6d7-226">В приведенном ниже сценарии можно увидеть приложение ASP.NET MVC и контейнер SQL Server, развернутые в виде контейнеров в ACI (экземпляры контейнеров Azure).</span><span class="sxs-lookup"><span data-stu-id="7d6d7-226">In the following scenario shown below you can see the ASP.NET MVC app plus the SQL Server container both of them deployed as containers into ACI (Azure Container Instances).</span></span>

![Развертывание в ACI из среды разработки](./media/image5-3.5.6.png)

### <a name="benefits"></a><span data-ttu-id="7d6d7-228">Преимущества</span><span class="sxs-lookup"><span data-stu-id="7d6d7-228">Benefits</span></span>

<span data-ttu-id="7d6d7-229">Служба "экземпляры контейнеров Azure" упрощает создание контейнеров DOCKER в Azure и управление ими без необходимости подготавливать виртуальные машины или применять службу более высокого уровня.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-229">Azure Container Instances makes it easy to create and manage Docker containers in Azure, without having to provision virtual machines or adopt a higher-level service.</span></span> <span data-ttu-id="7d6d7-230">С помощью ACI можно напрямую развернуть контейнер Windows в Azure и предоставить его в Интернете с полным доменным именем (FQDN) в течение нескольких секунд (при условии, что образ контейнера Windows готов в реестре DOCKER, например в центре DOCKER или контейнере Azure). Реестр).</span><span class="sxs-lookup"><span data-stu-id="7d6d7-230">With ACI, you can directly deploy a Windows container in Azure and expose it to the internet with a fully qualified domain name (FQDN) in a matter of seconds (Provided that you have the Windows Container image ready in a Docker registry like Docker Hub or Azure Container Registry).</span></span>

### <a name="considerations"></a><span data-ttu-id="7d6d7-231">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="7d6d7-231">Considerations</span></span>

<span data-ttu-id="7d6d7-232">Развертывание контейнеров Windows с полным .NET Framework, ASP.NET или SQL Server в службе "экземпляры контейнеров Azure" (ACI) не так быстро, как развертывание на обычном узле DOCKER (например, Windows Server 2016 с контейнерами Windows), так как образ DOCKER должен быть Загрузка (извлекаются из реестра DOCKER) каждый раз и размеры образа контейнера SQL (15,1 ГБ) и образа контейнера ASP.NET (13,9 ГБ) значительно велики, однако это гораздо дешевле, чем поддержание собственного узла DOCKER (постоянно в интерактивном виде). Windows Server 2016 с виртуальной машиной контейнеров Windows в Azure) не может упомянуть о всей Orchestrator, например Kubernetes в Azure (AKS), что, с другой стороны, отлично подходит для рабочих развертываний.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-232">Deploying Windows Containers with either full .NET Framework / ASP.NET or SQL Server into Azure Container Instances (ACI) is not quite as fast as deploying to a regular Docker Host (like a Windows Server 2016 with Windows Containers) because the Docker image has to be downloaded (pulled from the Docker registry) every time and the sizes of the SQL container image (15.1 GB) and the ASP.NET container image (13.9 GB) are significantly large, however it is much cheaper than maintaining your own docker host (permanently on-line Windows Server 2016 with Windows Containers VM in Azure) not to mention a whole orchestrator like Kubernetes in Azure (AKS) which is, on the other hand, a great choice for production deployments.</span></span>

<span data-ttu-id="7d6d7-233">Как основное заключение, использование службы "экземпляры контейнеров Azure" является очень привлекательным вариантом для сценариев разработки и тестирования, а также для конвейеров CI/CD.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-233">As main conclusion, using Azure Container Instances is a very compelling option for Dev/Test scenarios and for CI/CD pipelines.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7d6d7-234">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="7d6d7-234">Next steps</span></span>

<span data-ttu-id="7d6d7-235">Подробное изучение этого содержимого на вики-сайте GitHub:</span><span class="sxs-lookup"><span data-stu-id="7d6d7-235">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="7d6d7-236">Пошаговое руководство 5. Развертывание приложений на основе контейнеров Windows в Kubernetes в службе контейнеров Azure</span><span class="sxs-lookup"><span data-stu-id="7d6d7-236">Walkthrough 5: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="7d6d7-237">Техническое руководство по доступности</span><span class="sxs-lookup"><span data-stu-id="7d6d7-237">Technical walkthrough availability</span></span>

<span data-ttu-id="7d6d7-238">Полное техническое руководство доступно на вики-сайте репозитория eShopModernizing GitHub:</span><span class="sxs-lookup"><span data-stu-id="7d6d7-238">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

### <a name="overview"></a><span data-ttu-id="7d6d7-239">Обзор</span><span class="sxs-lookup"><span data-stu-id="7d6d7-239">Overview</span></span>

<span data-ttu-id="7d6d7-240">Приложение, основанное на контейнерах Windows, будет быстро использовать платформы, перенося их из виртуальных машин IaaS в другую систему.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-240">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="7d6d7-241">Это необходимо для простого обеспечения высокой масштабируемости и улучшенной масштабируемости, а для значительного улучшения автоматизированных развертываний и управления версиями.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-241">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="7d6d7-242">Эти цели можно достичь с помощью Orchestrator [Kubernetes](https://kubernetes.io/), доступного в [службе контейнеров Azure](https://azure.microsoft.com/services/container-service/).</span><span class="sxs-lookup"><span data-stu-id="7d6d7-242">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="7d6d7-243">Цели</span><span class="sxs-lookup"><span data-stu-id="7d6d7-243">Goals</span></span>

<span data-ttu-id="7d6d7-244">Цель этого пошагового руководства — узнать, как развернуть приложение на основе контейнера Windows в Kubernetes (другое название — *K8s*) в службе контейнеров Azure.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-244">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="7d6d7-245">Развертывание в Kubernetes с нуля состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="7d6d7-245">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1. <span data-ttu-id="7d6d7-246">Развертывание кластера Kubernetes в службе контейнеров Azure.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-246">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2. <span data-ttu-id="7d6d7-247">Разверните приложение и связанные ресурсы в кластере Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-247">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="7d6d7-248">Сценарии</span><span class="sxs-lookup"><span data-stu-id="7d6d7-248">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="7d6d7-249">Сценарий а. Развертывание непосредственно в кластере Kubernetes из среды разработки</span><span class="sxs-lookup"><span data-stu-id="7d6d7-249">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![Развертывание непосредственно в кластере Kubernetes из среды разработки](./media/image5-7.png)

<span data-ttu-id="7d6d7-251">**Рис. 5-7.**</span><span class="sxs-lookup"><span data-stu-id="7d6d7-251">**Figure 5-7.**</span></span> <span data-ttu-id="7d6d7-252">Развертывание непосредственно в кластере Kubernetes из среды разработки</span><span class="sxs-lookup"><span data-stu-id="7d6d7-252">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="7d6d7-253">Сценарий б. Развертывание в кластер Kubernetes из конвейеров CI/CD в Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="7d6d7-253">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

![Развертывание в кластер Kubernetes из конвейеров CI/CD в Azure DevOps Services](./media/image5-8.png)

<span data-ttu-id="7d6d7-255">**Рис. 5-8.**</span><span class="sxs-lookup"><span data-stu-id="7d6d7-255">**Figure 5-8.**</span></span> <span data-ttu-id="7d6d7-256">Развертывание в кластер Kubernetes из конвейеров CI/CD в Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="7d6d7-256">Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="benefits"></a><span data-ttu-id="7d6d7-257">Преимущества</span><span class="sxs-lookup"><span data-stu-id="7d6d7-257">Benefits</span></span>

<span data-ttu-id="7d6d7-258">Развертывание в кластер в Kubernetes имеет множество преимуществ.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-258">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="7d6d7-259">Самое главное преимущество заключается в том, что вы получаете готовую среду, в которой можно масштабировать приложение на основе количества экземпляров контейнеров, которые вы хотите использовать (внутренняя масштабируемость в существующих узлах), и в зависимости от количества узлов или виртуальных машин в кластере ( Глобальная масштабируемость кластера).</span><span class="sxs-lookup"><span data-stu-id="7d6d7-259">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="7d6d7-260">Служба контейнеров Azure оптимизирует популярные средства и технологии с открытым кодом специально для Azure.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-260">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="7d6d7-261">Вы получаете открытое решение, которое предлагает переносимость для контейнеров и для конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-261">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="7d6d7-262">Вы выбрали размер, число узлов, а служба Orchestrator Tools-Container Service обрабатывает все остальное.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-262">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="7d6d7-263">С помощью Kubernetes разработчики могут подумать о физических и виртуальных машинах, чтобы спланировать инфраструктуру, основанную на контейнерах, которая упрощает следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="7d6d7-263">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="7d6d7-264">Приложения, основанные на нескольких контейнерах</span><span class="sxs-lookup"><span data-stu-id="7d6d7-264">Applications based on multiple containers</span></span>

- <span data-ttu-id="7d6d7-265">Репликация экземпляров контейнеров и горизонтальное Автомасштабирование</span><span class="sxs-lookup"><span data-stu-id="7d6d7-265">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="7d6d7-266">Именование и обнаружение (например, внутренняя служба DNS)</span><span class="sxs-lookup"><span data-stu-id="7d6d7-266">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="7d6d7-267">Балансировка нагрузки</span><span class="sxs-lookup"><span data-stu-id="7d6d7-267">Balancing loads</span></span>

- <span data-ttu-id="7d6d7-268">Последовательные обновления</span><span class="sxs-lookup"><span data-stu-id="7d6d7-268">Rolling updates</span></span>

- <span data-ttu-id="7d6d7-269">Распространение секретов</span><span class="sxs-lookup"><span data-stu-id="7d6d7-269">Distributing secrets</span></span>

- <span data-ttu-id="7d6d7-270">Проверки работоспособности приложений</span><span class="sxs-lookup"><span data-stu-id="7d6d7-270">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="7d6d7-271">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="7d6d7-271">Next steps</span></span>

<span data-ttu-id="7d6d7-272">Подробное изучение этого содержимого на вики-сайте GitHub:<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="7d6d7-272">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)></span></span>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-app-service-for-containers"></a><span data-ttu-id="7d6d7-273">Пошаговое руководство 6. Развертывание приложений на основе контейнеров Windows в службе приложений Azure для контейнеров</span><span class="sxs-lookup"><span data-stu-id="7d6d7-273">Walkthrough 6: Deploy your Windows Containers-based apps to Azure App Service for Containers</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="7d6d7-274">Техническое руководство по доступности</span><span class="sxs-lookup"><span data-stu-id="7d6d7-274">Technical walkthrough availability</span></span>

<span data-ttu-id="7d6d7-275">Полное техническое руководство доступно на вики-сайте репозитория eShopModernizing GitHub:</span><span class="sxs-lookup"><span data-stu-id="7d6d7-275">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

### <a name="overview"></a><span data-ttu-id="7d6d7-276">Обзор</span><span class="sxs-lookup"><span data-stu-id="7d6d7-276">Overview</span></span>

<span data-ttu-id="7d6d7-277">Простое контейнерное приложение, использующее контейнеры Windows, можно легко развернуть в службе приложений Azure для контейнеров.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-277">A simple containerized application using Windows Containers can easily be deployed to Azure App Service for Containers.</span></span> <span data-ttu-id="7d6d7-278">Это рекомендуемый подход для большинства приложений на основе контейнеров Windows.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-278">This is the recommended approach for most Windows Container-based applications.</span></span>

### <a name="goals"></a><span data-ttu-id="7d6d7-279">Цели</span><span class="sxs-lookup"><span data-stu-id="7d6d7-279">Goals</span></span>

<span data-ttu-id="7d6d7-280">Цель этого пошагового руководства — узнать, как развернуть приложение на основе контейнера Windows в службе приложений Azure для контейнеров из реестра (DOCKER HUB или реестра контейнеров Azure).</span><span class="sxs-lookup"><span data-stu-id="7d6d7-280">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Azure App Service for Containers from a registry (Docker Hub or Azure Container Registry).</span></span>

### <a name="scenario"></a><span data-ttu-id="7d6d7-281">Сценарий</span><span class="sxs-lookup"><span data-stu-id="7d6d7-281">Scenario</span></span>

![Развертывание приложения на основе контейнера Windows в службе приложений Azure для контейнеров](./media/image5-11.png)

### <a name="benefits"></a><span data-ttu-id="7d6d7-283">Преимущества</span><span class="sxs-lookup"><span data-stu-id="7d6d7-283">Benefits</span></span>

<span data-ttu-id="7d6d7-284">Развертывание в службе приложений Azure для контейнеров предоставляет преимущества контейнеров, связанных с преимуществами PaaS службы приложений Azure.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-284">Deploying to Azure App Service for Containers offers the benefits of containers paired with the PaaS benefits of Azure App Service.</span></span> <span data-ttu-id="7d6d7-285">Службу приложений можно легко масштабировать как по вертикали, так и по горизонтали. ее можно настроить для автоматического масштабирования в соответствии с изменяющимися потребностями.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-285">The app service can easily be scaled both vertically and horizontally, and can be configured to autoscale to meet changing demands.</span></span> <span data-ttu-id="7d6d7-286">Обновления могут выполняться с нулевым временем простоя и конфигурацией непрерывного развертывания из реестра.</span><span class="sxs-lookup"><span data-stu-id="7d6d7-286">Updates can be performed with zero downtime and configuration of continuous deployment from a registry is easily configured as well.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7d6d7-287">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="7d6d7-287">Next steps</span></span>

<span data-ttu-id="7d6d7-288">Подробное изучение этого содержимого на вики-сайте GitHub:<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service></span><span class="sxs-lookup"><span data-stu-id="7d6d7-288">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service></span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="7d6d7-289">[Назад](modernize-existing-apps-to-cloud-optimized/migrate-to-hybrid-cloud-scenarios.md)
> [Вперед](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="7d6d7-289">[Previous](modernize-existing-apps-to-cloud-optimized/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span> <!-- Next Chapter -->
