---
title: "Общие сведения о .NET и Docker"
description: "Основные сведения о Docker и .NET Core"
keywords: .NET, .NET Core, Docker
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
manager: wpickett
ms.custom: mvc
ms.openlocfilehash: 1c9ce7a008c86d1c245ce8b7d616e05fcb3d4bbc
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="introduction-to-net-and-docker"></a><span data-ttu-id="33256-104">Общие сведения о .NET и Docker</span><span class="sxs-lookup"><span data-stu-id="33256-104">Introduction to .NET and Docker</span></span>

 <span data-ttu-id="33256-105">Эта статья содержит введение и концептуальную основу для работы с .NET в Docker.</span><span class="sxs-lookup"><span data-stu-id="33256-105">This article provides an introduction and conceptual background to working with .NET on Docker.</span></span> 

## <a name="docker-packaging-your-apps-to-deploy-and-run-anywhere"></a><span data-ttu-id="33256-106">Docker: Упаковка приложений для развертывания и выполнения в любом месте</span><span class="sxs-lookup"><span data-stu-id="33256-106">Docker: Packaging your apps to deploy and run anywhere</span></span>

<span data-ttu-id="33256-107">[Docker](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-defined) – это открытая платформа, которая позволяет разработчикам и администраторам для построения [изображения](https://docs.docker.com/glossary/?term=image), распространять и выполнения распределенных приложений в слабо изолированной среде называется [контейнера](https://www.docker.com/what-container).</span><span class="sxs-lookup"><span data-stu-id="33256-107">[Docker](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-defined) is an open platform that enables developers and administrators to build [images](https://docs.docker.com/glossary/?term=image), ship, and run distributed applications in a loosely isolated environment called a [container](https://www.docker.com/what-container).</span></span> <span data-ttu-id="33256-108">Такой подход позволяет эффективно использование управления жизненным циклом разработки, контроля Качества и рабочих средах.</span><span class="sxs-lookup"><span data-stu-id="33256-108">This approach enables efficient application lifecycle management between development, QA, and production environments.</span></span>
 
<span data-ttu-id="33256-109">[Платформа Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) использует [подсистемы Docker](https://docs.docker.com/engine/docker-overview/#docker-engine) быстро построить и пакет приложения в качестве [Docker images](https://docs.docker.com/glossary/?term=image) создан с помощью файлов, записанных [Dockerfile ](https://docs.docker.com/glossary/?term=Dockerfile) формат, который затем развертывается и запускается [многоуровневая контейнер](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span><span class="sxs-lookup"><span data-stu-id="33256-109">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image) created using files written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format that then is deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>

<span data-ttu-id="33256-110">Можно создать собственные [многоуровневая изображения](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) файлов dockerfile или использование существующих из [реестра](https://docs.docker.com/glossary/?term=registry), таких как [Docker Hub](https://docs.docker.com/glossary/?term=Docker%20Hub).</span><span class="sxs-lookup"><span data-stu-id="33256-110">You can either create your own [layered images](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) as dockerfiles or use existing ones from a [registry](https://docs.docker.com/glossary/?term=registry), like [Docker Hub](https://docs.docker.com/glossary/?term=Docker%20Hub).</span></span>

<span data-ttu-id="33256-111">[Связь между контейнеры Docker, изображения и реестров](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries) — это важная концепция при [архитектуры и проектирование контейнерных приложений или микрослужбами](https://docs.microsoft.com/dotnet/standard/microservices-architecture/architect-microservice-container-applications/).</span><span class="sxs-lookup"><span data-stu-id="33256-111">The [relationship between Docker containers, images, and registries](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries) is an important concept when [architecting and building containerized applications or microservices](https://docs.microsoft.com/dotnet/standard/microservices-architecture/architect-microservice-container-applications/).</span></span> <span data-ttu-id="33256-112">Такой подход значительно сокращает время между разработки и развертывания.</span><span class="sxs-lookup"><span data-stu-id="33256-112">This approach greatly shortens the time between development and deployment.</span></span>

### <a name="further-reading-and-watching"></a><span data-ttu-id="33256-113">Дополнительные сведения (и просмотр)</span><span class="sxs-lookup"><span data-stu-id="33256-113">Further reading (and watching)</span></span>

* [<span data-ttu-id="33256-114">Контейнеры на основе Windows: Разработка современных приложений с корпоративным уровнем управления.</span><span class="sxs-lookup"><span data-stu-id="33256-114">Windows-based containers: Modern app development with enterprise-grade control.</span></span>](https://www.youtube.com/watch?v=Ryx3o0rD5lY&feature=youtu.be)
* [<span data-ttu-id="33256-115">Общие сведения о docker</span><span class="sxs-lookup"><span data-stu-id="33256-115">Docker overview</span></span>](https://docs.docker.com/engine/docker-overview/)
* [<span data-ttu-id="33256-116">Dockerfile в контейнерах Windows</span><span class="sxs-lookup"><span data-stu-id="33256-116">Dockerfile on Windows Containers</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [<span data-ttu-id="33256-117">Советы и рекомендации по составлению файлов Dockerfile</span><span class="sxs-lookup"><span data-stu-id="33256-117">Best practices for writing Dockerfiles</span></span>](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)
* [<span data-ttu-id="33256-118">Сборка Docker Images для приложений .NET Core</span><span class="sxs-lookup"><span data-stu-id="33256-118">Building Docker Images for .NET Core applications</span></span>](../docker/building-net-docker-images.md)


### <a name="getting-net-docker-images"></a><span data-ttu-id="33256-119">Получение образов Docker .NET</span><span class="sxs-lookup"><span data-stu-id="33256-119">Getting .NET Docker Images</span></span>

<span data-ttu-id="33256-120">Образы Docker официальный .NET созданы и оптимизированы корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="33256-120">The Official .NET Docker images are created and optimized by Microsoft.</span></span> <span data-ttu-id="33256-121">Они доступны публично в репозиториях Microsoft в концентраторе Docker.</span><span class="sxs-lookup"><span data-stu-id="33256-121">They are publicly available in the Microsoft repositories on Docker Hub.</span></span> <span data-ttu-id="33256-122">Каждого репозитория может содержать несколько образов, в зависимости от версии платформы .NET и версии ОС.</span><span class="sxs-lookup"><span data-stu-id="33256-122">Each repository can contain multiple images, depending on .NET versions, and on OS versions.</span></span> <span data-ttu-id="33256-123">Большинство репозиториев изображения предоставляют широко тегов, чтобы облегчить выбор версии конкретной платформы и ОС (дистрибутив Linux или версии Windows).</span><span class="sxs-lookup"><span data-stu-id="33256-123">Most image repos provide extensive tagging to help you select both a specific framework version and an OS (Linux distro or Windows version).</span></span>

## <a name="scenario-based-guidance"></a><span data-ttu-id="33256-124">Сценарий на основе рекомендации</span><span class="sxs-lookup"><span data-stu-id="33256-124">Scenario Based Guidance</span></span>

<span data-ttu-id="33256-125">Корпорации Майкрософт для .NET репозиториев призван имеют репозиториев организованную и имеющего фокус, представляющие конкретному сценарию или рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="33256-125">Microsoft’s intent for .NET repositories is to have granular and focused repos, which represent a specific scenario or workload.</span></span>

<span data-ttu-id="33256-126">`microsoft/aspnetcore` Изображения оптимизированы для приложений ASP.NET Core для Docker, поэтому контейнеры можно запустить быстрее.</span><span class="sxs-lookup"><span data-stu-id="33256-126">The `microsoft/aspnetcore` images are optimized for ASP.NET Core apps on Docker, so containers can start faster.</span></span>

<span data-ttu-id="33256-127">.NET Core изображений (`microsoft/dotnet`), предназначены для приложений консоли, в зависимости от .NET Core.</span><span class="sxs-lookup"><span data-stu-id="33256-127">The .NET Core images (`microsoft/dotnet`) are intended for console apps based on .NET Core.</span></span> <span data-ttu-id="33256-128">Например процессы пакетной обработки, веб-заданий Azure и других сценариев консоли следует использовать оптимизированные изображения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="33256-128">For example, batch processes, Azure WebJobs, and other console scenarios should use optimized .NET Core images.</span></span>

<span data-ttu-id="33256-129">Наиболее очевидным горизонтальной сценария по использованию приложений Docker и .NET — для рабочего развертывания и размещения.</span><span class="sxs-lookup"><span data-stu-id="33256-129">The most obvious horizontal scenario for using Docker and .NET applications is for production deployment and hosting.</span></span> <span data-ttu-id="33256-130">Оказывается, что производства — всего лишь одного сценария, и остальные одинаково полезны.</span><span class="sxs-lookup"><span data-stu-id="33256-130">It turns out that production is just one scenario and the other ones are equally useful.</span></span> <span data-ttu-id="33256-131">Эти сценарии не являются специфичными для .NET, но также применимы для большинства платформ разработки.</span><span class="sxs-lookup"><span data-stu-id="33256-131">These scenarios are not specific to .NET, but should apply to most developer platforms.</span></span>

* <span data-ttu-id="33256-132">**Установка низкого трения** — можно опробовать .NET без локальной установки.</span><span class="sxs-lookup"><span data-stu-id="33256-132">**Low friction install** — You can try out .NET without a local install.</span></span> <span data-ttu-id="33256-133">Просто загрузите образа Docker с помощью .NET в нем.</span><span class="sxs-lookup"><span data-stu-id="33256-133">Just download a Docker image with .NET in it.</span></span>

* <span data-ttu-id="33256-134">**Разработка в контейнере** — можно разрабатывать в согласованной среде, выполняющего аналогичные (Предотвращение проблем, таких как глобальное состояние на компьютерах разработчиков) разработки и рабочих средах.</span><span class="sxs-lookup"><span data-stu-id="33256-134">**Develop in a container** — You can develop in a consistent environment, making development and production environments similar (avoiding issues like global state on developer machines).</span></span> <span data-ttu-id="33256-135">Visual Studio Tools для Docker даже позволяют запускать контейнер непосредственно из Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="33256-135">Visual Studio Tools for Docker even enable you to start a container directly from Visual Studio.</span></span>

* <span data-ttu-id="33256-136">**Тестирование в контейнере** — можно проверить в контейнере, уменьшая сбои из-за неправильно настроенной среды или другие изменения, оставшиеся от последнего теста.</span><span class="sxs-lookup"><span data-stu-id="33256-136">**Test in a container** — You can test in a container, reducing failures due to incorrectly configured environments or other changes left behind from the last test.</span></span>

* <span data-ttu-id="33256-137">**Сборки в контейнере** — вы можете создать код в контейнере, устраняя необходимость правильно настроить на компьютерах сборки, общего для нескольких сред, но вместо этого переместить «BYOC» (Используйте собственный контейнер) подход.</span><span class="sxs-lookup"><span data-stu-id="33256-137">**Build in a container** — You can build code in a container, avoiding the need to correctly configure shared build machines for multiple environments but instead move to a “BYOC” (bring your own container) approach.</span></span>

* <span data-ttu-id="33256-138">**Развертывания в любых средах** — можно развертывать образ с помощью всех сред.</span><span class="sxs-lookup"><span data-stu-id="33256-138">**Deployment in all environments** — You can deploy an image through all of your environments.</span></span> <span data-ttu-id="33256-139">Этот подход уменьшает сбои из-за различий в настройках, обычно изменения поведения изображения через внешнюю конфигурацию (например, введенный переменные).</span><span class="sxs-lookup"><span data-stu-id="33256-139">This approach reduces failures due to configuration differences, typically changing the image behavior via external configuration (for example, injected environment variables).</span></span>

<span data-ttu-id="33256-140">[Общие рекомендации](https://docs.microsoft.com/dotnet/standard/microservices-architecture/net-core-net-framework-containers/general-guidance) для Выбор между .NET Core и .NET Framework для разработки контейнер Docker.</span><span class="sxs-lookup"><span data-stu-id="33256-140">[General guidance](https://docs.microsoft.com/dotnet/standard/microservices-architecture/net-core-net-framework-containers/general-guidance) for deciding between .NET Core and .NET Framework for Docker container development.</span></span>

### <a name="common-docker-development-scenarios"></a><span data-ttu-id="33256-141">Распространенные сценарии разработки Docker</span><span class="sxs-lookup"><span data-stu-id="33256-141">Common Docker development scenarios</span></span>

#### <a name="net-core"></a><span data-ttu-id="33256-142">.NET Core</span><span class="sxs-lookup"><span data-stu-id="33256-142">.NET Core</span></span>

<span data-ttu-id="33256-143">**Ресурсы .NET core**</span><span class="sxs-lookup"><span data-stu-id="33256-143">**.NET Core resources**</span></span>

 <span data-ttu-id="33256-144">Выберите подходящие сценарии процент образцы .NET Core.</span><span class="sxs-lookup"><span data-stu-id="33256-144">Pick the .NET Core samples that fit your scenarios of interest.</span></span> <span data-ttu-id="33256-145">Все инструкции образец описываются способы нацеливания Windows или Linux Docker образы из Windows, Linux и macOS узлов.</span><span class="sxs-lookup"><span data-stu-id="33256-145">All sample instructions describe how to target Windows or Linux Docker images from Windows, Linux, or macOS hosts.</span></span>

<span data-ttu-id="33256-146">Примеры использования .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="33256-146">The samples use .NET Core 2.0.</span></span> <span data-ttu-id="33256-147">Они используют Docker [построения многоэтапным](https://github.com/dotnet/announcements/issues/18) и [несколькими arch теги](https://github.com/dotnet/announcements/issues/14) в случае необходимости.</span><span class="sxs-lookup"><span data-stu-id="33256-147">They use Docker [multi-stage build](https://github.com/dotnet/announcements/issues/18) and [multi-arch tags](https://github.com/dotnet/announcements/issues/14) where appropriate.</span></span>

* [<span data-ttu-id="33256-148">.NET core изображений на DockerHub</span><span class="sxs-lookup"><span data-stu-id="33256-148">.NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/dotnet/)

* [<span data-ttu-id="33256-149">Dockerize приложения .NET Core</span><span class="sxs-lookup"><span data-stu-id="33256-149">Dockerize a .NET Core application</span></span>](https://docs.docker.com/engine/examples/dotnetcore/)

* <span data-ttu-id="33256-150">В этом образце .NET Core Docker показано как [использовать Docker в процессе разработки .NET Core](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev).</span><span class="sxs-lookup"><span data-stu-id="33256-150">This .NET Core Docker sample demonstrates how to [use Docker in your .NET Core development process](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev).</span></span> <span data-ttu-id="33256-151">Образец работает с контейнерами Windows и Linux.</span><span class="sxs-lookup"><span data-stu-id="33256-151">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="33256-152">В этом примере .NET Core Docker демонстрируется лучше всего рекомендаций для [построения образов Docker для приложений .NET Core для рабочей среды.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span><span class="sxs-lookup"><span data-stu-id="33256-152">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span></span> <span data-ttu-id="33256-153">Образец работает с контейнерами Windows и Linux.</span><span class="sxs-lookup"><span data-stu-id="33256-153">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="33256-154">Это [образец .NET Core Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained) показан шаблон лучший подход для создания образов Docker для [автономные приложения .NET Core](https://docs.microsoft.com/dotnet/core/deploying/).</span><span class="sxs-lookup"><span data-stu-id="33256-154">This [.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained) demonstrates a best practice pattern for building Docker images for [self-contained .NET Core applications](https://docs.microsoft.com/dotnet/core/deploying/).</span></span> <span data-ttu-id="33256-155">Для наименьшего контейнера рабочей среде без выгода от [базовые образы между контейнерами для управления доступом](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/).</span><span class="sxs-lookup"><span data-stu-id="33256-155">Used for the smallest production container without a benefit from [sharing base images between containers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/).</span></span> <span data-ttu-id="33256-156">Однако нижних слоев Docker может использоваться совместно.</span><span class="sxs-lookup"><span data-stu-id="33256-156">However, lower Docker layers could be shared.</span></span>

#### <a name="arm32--raspberry-pi"></a><span data-ttu-id="33256-157">ARM32 / Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="33256-157">ARM32 / Raspberry Pi</span></span>

* [<span data-ttu-id="33256-158">Объявление построений ARM32 среды выполнения .NET core</span><span class="sxs-lookup"><span data-stu-id="33256-158">.NET Core Runtime ARM32 builds announcement</span></span>](https://github.com/dotnet/announcements/issues/29)

* [<span data-ttu-id="33256-159">ARM32 / images Raspberry Pi .NET Core на DockerHub</span><span class="sxs-lookup"><span data-stu-id="33256-159">ARM32 / Raspberry Pi .NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/dotnet/)

* [<span data-ttu-id="33256-160">ARM32 / Samples малиновая Pi .NET Core Docker на GitHub</span><span class="sxs-lookup"><span data-stu-id="33256-160">ARM32 / Raspberry Pi .NET Core Docker Samples on GitHub</span></span>](https://github.com/dotnet/dotnet-docker-samples#arm32--raspberry-pi)

#### <a name="net-framework"></a><span data-ttu-id="33256-161">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="33256-161">.NET Framework</span></span>

* <span data-ttu-id="33256-162">[.NET framework изображений на DockerHub](https://hub.docker.com/r/microsoft/dotnet-framework/) этого репозитория содержит образцы, демонстрирующие различные конфигурации .NET Framework Docker.</span><span class="sxs-lookup"><span data-stu-id="33256-162">[.NET Framework images on DockerHub](https://hub.docker.com/r/microsoft/dotnet-framework/) This repo contain samples that demonstrate various .NET Framework Docker configurations.</span></span> <span data-ttu-id="33256-163">Эти образы можно использовать как основу для образов Docker.</span><span class="sxs-lookup"><span data-stu-id="33256-163">You can use these images as the basis of your own Docker images.</span></span>

<span data-ttu-id="33256-164">**.NET framework 4.7**</span><span class="sxs-lookup"><span data-stu-id="33256-164">**.NET Framework 4.7**</span></span>

<span data-ttu-id="33256-165">[ [Dotnet-образец framework: 4.7](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7) демонстрирует основные «hello world» использование [.NET Framework 4.7](https://docs.microsoft.com/dotnet/framework/whats-new/index#introducing-the-net-framework-47).</span><span class="sxs-lookup"><span data-stu-id="33256-165">[The [dotnet-framework:4.7 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7) demonstrates basic "hello world" usage of the [.NET Framework 4.7](https://docs.microsoft.com/dotnet/framework/whats-new/index#introducing-the-net-framework-47).</span></span> <span data-ttu-id="33256-166">Он показано, как построить и развернуть приложение, полагаясь на [образа docker .NET Framework 4.7](https://github.com/Microsoft/dotnet-framework-docker/blob/master/4.7/Dockerfile).</span><span class="sxs-lookup"><span data-stu-id="33256-166">It shows you how you can build and deploy the app relying on the [.NET Framework 4.7 docker image](https://github.com/Microsoft/dotnet-framework-docker/blob/master/4.7/Dockerfile).</span></span>

<span data-ttu-id="33256-167">**.NET framework 4.6.2**</span><span class="sxs-lookup"><span data-stu-id="33256-167">**.NET Framework 4.6.2**</span></span>

<span data-ttu-id="33256-168">[Dotnet-образец framework: 4.6.2](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2) демонстрирует основные «hello world» использование [.NET Framework 4.6.2](https://docs.microsoft.com/dotnet/framework/whats-new/index#whats-new-in-the-net-framework-462).</span><span class="sxs-lookup"><span data-stu-id="33256-168">The [dotnet-framework:4.6.2 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2) demonstrates basic "hello world" usage of the [.NET Framework 4.6.2](https://docs.microsoft.com/dotnet/framework/whats-new/index#whats-new-in-the-net-framework-462).</span></span> <span data-ttu-id="33256-169">Он показано, как построить и развернуть приложение, полагаясь на [образа docker .NET Framework 4.6.2](https://github.com/Microsoft/dotnet-framework-docker/tree/master/4.6.2).</span><span class="sxs-lookup"><span data-stu-id="33256-169">It shows you how you can build and deploy the app relying on the [.NET Framework 4.6.2 docker image](https://github.com/Microsoft/dotnet-framework-docker/tree/master/4.6.2).</span></span>

<span data-ttu-id="33256-170">**Платформа .NET framework 3.5**</span><span class="sxs-lookup"><span data-stu-id="33256-170">**.NET Framework 3.5**</span></span>

 <span data-ttu-id="33256-171">[Dotnet-образец framework: 3.5](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5) демонстрирует основные «hello world» использование [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker/tree/master/3.5).</span><span class="sxs-lookup"><span data-stu-id="33256-171">The [dotnet-framework:3.5 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5) demonstrates basic "hello world" usage of [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker/tree/master/3.5).</span></span> <span data-ttu-id="33256-172">Он показывает, как построить и развернуть проект на .NET Framework 3.5 в Docker.</span><span class="sxs-lookup"><span data-stu-id="33256-172">It shows you how you can build and deploy a project relying on .NET Framework 3.5 in Docker.</span></span>

#### <a name="aspnet-core"></a><span data-ttu-id="33256-173">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="33256-173">ASP.NET Core</span></span>

* <span data-ttu-id="33256-174">[В этом примере ASP.NET Core Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) показан шаблон лучший подход для создания образов Docker для ASP.NET Core приложений для рабочей среды.</span><span class="sxs-lookup"><span data-stu-id="33256-174">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="33256-175">Образец работает с контейнерами Windows и Linux.</span><span class="sxs-lookup"><span data-stu-id="33256-175">The sample works with both Linux and Windows containers.</span></span>

* [<span data-ttu-id="33256-176">ASP.NET Core изображений на DockerHub</span><span class="sxs-lookup"><span data-stu-id="33256-176">ASP.NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnetcore-build/)

* [<span data-ttu-id="33256-177">ASP.NET Core изображения на GitHub</span><span class="sxs-lookup"><span data-stu-id="33256-177">ASP.NET Core images on GitHub</span></span>](https://github.com/aspnet/aspnet-docker)

#### <a name="aspnet-framework"></a><span data-ttu-id="33256-178">Платформа ASP.NET</span><span class="sxs-lookup"><span data-stu-id="33256-178">ASP.NET Framework</span></span> 

* [<span data-ttu-id="33256-179">Платформа ASP.NET изображений на DockerHub</span><span class="sxs-lookup"><span data-stu-id="33256-179">ASP.NET Framework images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnet/)

* [<span data-ttu-id="33256-180">Приложение веб-форм ASP.NET на примеры .NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="33256-180">ASP.NET Web Forms app on .NET Framework 4.6.2 sample</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/aspnetapp)

#### <a name="windows-communication-framework-wcf"></a><span data-ttu-id="33256-181">Windows Communication Framework (WCF)</span><span class="sxs-lookup"><span data-stu-id="33256-181">Windows Communication Framework (WCF)</span></span>

* [<span data-ttu-id="33256-182">Образы Windows Communication Framework (WCF) на DockerHub</span><span class="sxs-lookup"><span data-stu-id="33256-182">Windows Communication Framework (WCF) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/wcf/)

* [<span data-ttu-id="33256-183">Образы Windows Communication Framework (WCF) на сайте GitHub</span><span class="sxs-lookup"><span data-stu-id="33256-183">Windows Communication Framework (WCF) images on GitHub</span></span>](https://github.com/microsoft/iis-docker)

* [<span data-ttu-id="33256-184">Образцы Windows Communication Framework (WCF) Docker на основе .NET Full Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="33256-184">Windows Communication Framework (WCF) Docker samples using .NET Full Framework 4.6.2</span></span>](https://github.com/Microsoft/wcf-docker-samples)

#### <a name="internet-information-server-iis"></a><span data-ttu-id="33256-185">Internet Information Server (IIS)</span><span class="sxs-lookup"><span data-stu-id="33256-185">Internet Information Server (IIS)</span></span>

* [<span data-ttu-id="33256-186">Образы Internet Information Server (IIS) на DockerHub</span><span class="sxs-lookup"><span data-stu-id="33256-186">Internet Information Server (IIS) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/iis/)

* [<span data-ttu-id="33256-187">Образы Internet Information Server (IIS) на сайте GitHub</span><span class="sxs-lookup"><span data-stu-id="33256-187">Internet Information Server (IIS) images on GitHub</span></span>](https://github.com/microsoft/wcf-docker)

### <a name="interact-with-other-microsoft-stack-container-images"></a><span data-ttu-id="33256-188">Взаимодействие с другими образы контейнеров стека Microsoft</span><span class="sxs-lookup"><span data-stu-id="33256-188">Interact with other Microsoft stack container images</span></span>

#### <a name="microsoft-sql-server"></a><span data-ttu-id="33256-189">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="33256-189">Microsoft SQL Server</span></span>

* [<span data-ttu-id="33256-190">Запустите Microsoft SQL Server для Linux 2017 г образа контейнера с Docker начало работы</span><span class="sxs-lookup"><span data-stu-id="33256-190">Run the Microsoft SQL Server for Linux 2017 container image with Docker Quickstart</span></span>](https://docs.microsoft.com/sql/linux/quickstart-install-connect-docker)

* [<span data-ttu-id="33256-191">Microsoft SQL Server для образов Linux на DockerHub</span><span class="sxs-lookup"><span data-stu-id="33256-191">Microsoft SQL Server for Linux images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [<span data-ttu-id="33256-192">Microsoft SQL Server для контейнеров Windows изображений на DockerHub</span><span class="sxs-lookup"><span data-stu-id="33256-192">Microsoft SQL Server for Windows Containers images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [<span data-ttu-id="33256-193">Microsoft SQL Server, экспресс-выпуск образов для контейнеров Windows на DockerHub</span><span class="sxs-lookup"><span data-stu-id="33256-193">Microsoft SQL Server Express Edition images for Windows Containers on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows-express/)

* [<span data-ttu-id="33256-194">Microsoft SQL Server Developer Edition образов для контейнеров Windows на DockerHub</span><span class="sxs-lookup"><span data-stu-id="33256-194">Microsoft SQL Server Developer Edition images for Windows Containers on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows-developer/)

#### <a name="visual-studio-team-services-vsts-agent"></a><span data-ttu-id="33256-195">Агент Visual Studio Team Services (VSTS)</span><span class="sxs-lookup"><span data-stu-id="33256-195">Visual Studio Team Services (VSTS) agent</span></span>

* [<span data-ttu-id="33256-196">Изображений в Visual Studio Team Services (VSTS) агента на DockerHub</span><span class="sxs-lookup"><span data-stu-id="33256-196">Visual Studio Team Services (VSTS) agent images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/vsts-agent/)

* [<span data-ttu-id="33256-197">Образы в Visual Studio Team Services (VSTS) агента на GitHub</span><span class="sxs-lookup"><span data-stu-id="33256-197">Visual Studio Team Services (VSTS) agent images on GitHub</span></span>](https://github.com/Microsoft/vsts-agent-docker)

#### <a name="operations-management-suite-oms-linux-agent"></a><span data-ttu-id="33256-198">Агент Operations Management Suite (OMS) Linux</span><span class="sxs-lookup"><span data-stu-id="33256-198">Operations Management Suite (OMS) Linux agent</span></span>

* [<span data-ttu-id="33256-199">Общие сведения об агенте Operations Management Suite (OMS) Linux</span><span class="sxs-lookup"><span data-stu-id="33256-199">Operations Management Suite (OMS) Linux agent overview</span></span>](https://github.com/Microsoft/OMS-Agent-for-Linux/blob/master/docs/Docker-Instructions.md#overview)

* [<span data-ttu-id="33256-200">Operations Management Suite (OMS) изображений на DockerHub</span><span class="sxs-lookup"><span data-stu-id="33256-200">Operations Management Suite (OMS) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/vsts-agent/) 

* [<span data-ttu-id="33256-201">Образы Operations Management Suite (OMS) на сайте GitHub</span><span class="sxs-lookup"><span data-stu-id="33256-201">Operations Management Suite (OMS) images on GitHub</span></span>](https://github.com/Microsoft/OMS-docker)

#### <a name="microsoft-azure-command-line-interface-cli"></a><span data-ttu-id="33256-202">Microsoft Azure командной строки (CLI)</span><span class="sxs-lookup"><span data-stu-id="33256-202">Microsoft Azure Command Line Interface (CLI)</span></span>

* [<span data-ttu-id="33256-203">Microsoft Azure интерфейс командной строки (CLI) изображений на DockerHub</span><span class="sxs-lookup"><span data-stu-id="33256-203">Microsoft Azure Command Line Interface (CLI) images on DockerHub</span></span>](Docker image for Microsoft Azure Command Line Interface) 

* [<span data-ttu-id="33256-204">Microsoft Azure интерфейс командной строки (CLI) изображений на GitHub</span><span class="sxs-lookup"><span data-stu-id="33256-204">Microsoft Azure Command Line Interface (CLI) images on GitHub</span></span>](https://github.com/Microsoft/OMS-docker)

> [!Note]
> <span data-ttu-id="33256-205">Если у вас подписка на Azure, [Зарегистрируйтесь](https://azure.microsoft.com/free/?b=16.48) для бесплатной 30-дневной учетной записи и get 200 в кредиты Azure, чтобы испытать любое сочетание служб Azure.</span><span class="sxs-lookup"><span data-stu-id="33256-205">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>
>

#### <a name="microsoft-azure-cosmos-db-emulator-windows-containers-only"></a><span data-ttu-id="33256-206">Эмулятор Microsoft Azure Cosmos DB (только для контейнеров Windows)</span><span class="sxs-lookup"><span data-stu-id="33256-206">Microsoft Azure Cosmos DB Emulator (Windows Containers only)</span></span>

* [<span data-ttu-id="33256-207">Эмулятор Microsoft Azure Cosmos DB изображений на DockerHub</span><span class="sxs-lookup"><span data-stu-id="33256-207">Microsoft Azure Cosmos DB Emulator images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator) 

* [<span data-ttu-id="33256-208">Использование эмулятора Azure Cosmos DB локальной разработки и тестирования</span><span class="sxs-lookup"><span data-stu-id="33256-208">Use the Azure Cosmos DB Emulator for local development and testing</span></span>](https://docs.microsoft.com/azure/cosmos-db/local-emulator#developing-with-the-emulator)

## <a name="exploring-the-rich-docker-development-ecosystem"></a><span data-ttu-id="33256-209">Изучение экосистеме разработки многофункциональных Docker</span><span class="sxs-lookup"><span data-stu-id="33256-209">Exploring the rich Docker development ecosystem</span></span>

<span data-ttu-id="33256-210">Теперь, когда вы изучили платформы Docker и различные изображения Docker, следующим шагом является исследование форматированного экосистеме Docker.</span><span class="sxs-lookup"><span data-stu-id="33256-210">Now that you have learned about the Docker platform and different Docker images, the next step is to explore the rich Docker ecosystem.</span></span> <span data-ttu-id="33256-211">Следующие ссылки покажут, как средства Microsoft дополняют разработки контейнера.</span><span class="sxs-lookup"><span data-stu-id="33256-211">The following links show you how the Microsoft tools complement container development.</span></span>

* [<span data-ttu-id="33256-212">Совместное использование .NET и Docker</span><span class="sxs-lookup"><span data-stu-id="33256-212">Using .NET and Docker together</span></span>](https://blogs.msdn.microsoft.com/dotnet/2017/05/25/using-net-and-docker-together/) 
* [<span data-ttu-id="33256-213">Проектирование и разработка приложений на основе Микрослужбу и несколькими контейнера .NET</span><span class="sxs-lookup"><span data-stu-id="33256-213">Designing and Developing Multi-Container and Microservice-Based .NET Applications</span></span>](../standard/microservices-architecture/multi-container-microservice-net-applications)
* [<span data-ttu-id="33256-214">Расширение Visual Studio код Docker</span><span class="sxs-lookup"><span data-stu-id="33256-214">Visual Studio Code Docker extension</span></span>](https://code.visualstudio.com/docs/languages/dockerfile) 
* [<span data-ttu-id="33256-215">Использование Azure Service Fabric</span><span class="sxs-lookup"><span data-stu-id="33256-215">Learn how to use Azure Service Fabric</span></span>](https://docs.microsoft.com/azure/service-fabric/) 
* [<span data-ttu-id="33256-216">Пример работы начало Service Fabric</span><span class="sxs-lookup"><span data-stu-id="33256-216">Service Fabric Getting Started Sample</span></span>](https://azure.microsoft.com/resources/samples/service-fabric-dotnet-getting-started/)
* [<span data-ttu-id="33256-217">Преимущества контейнеров Windows</span><span class="sxs-lookup"><span data-stu-id="33256-217">Benefits of Windows Containers</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/about/index#video-overview)
* [<span data-ttu-id="33256-218">Работа со средствами Visual Studio Docker</span><span class="sxs-lookup"><span data-stu-id="33256-218">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="33256-219">Развертывание образов Docker из реестра контейнер Azure с экземплярами Azure контейнера</span><span class="sxs-lookup"><span data-stu-id="33256-219">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [<span data-ttu-id="33256-220">Отладка с кодом Visual Studio</span><span class="sxs-lookup"><span data-stu-id="33256-220">Debugging with Visual Studio Code</span></span>](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [<span data-ttu-id="33256-221">Получение руки по с помощью Visual Studio для Mac, контейнеры и без сервера кода в облаке</span><span class="sxs-lookup"><span data-stu-id="33256-221">Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud</span></span>](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [<span data-ttu-id="33256-222">Начало работы с Docker и Visual Studio для Mac лаборатории</span><span class="sxs-lookup"><span data-stu-id="33256-222">Getting Started with Docker and Visual Studio for Mac Lab</span></span>](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

## <a name="next-steps"></a><span data-ttu-id="33256-223">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="33256-223">Next Steps</span></span>

* [<span data-ttu-id="33256-224">Основы Docker с помощью .NET Core</span><span class="sxs-lookup"><span data-stu-id="33256-224">Learn Docker Basics with .NET Core</span></span>](../docker/docker-basics-dotnet-core.md)
* [<span data-ttu-id="33256-225">Создание образов Docker .NET Core</span><span class="sxs-lookup"><span data-stu-id="33256-225">Building .NET Core Docker Images</span></span>](../docker/building-net-docker-images)