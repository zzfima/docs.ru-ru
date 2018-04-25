---
title: Введение в .NET и Docker
description: Общие сведения о Docker и .NET Core
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
ms.workload:
- dotnetcore
ms.openlocfilehash: 75c631cf0abac543889cb7387f6fc3fdb2624512
ms.sourcegitcommit: 68b60d38043e50104ccc90c76f8599b1ffe18346
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="introduction-to-net-and-docker"></a><span data-ttu-id="bc84f-104">Введение в .NET и Docker</span><span class="sxs-lookup"><span data-stu-id="bc84f-104">Introduction to .NET and Docker</span></span>

<span data-ttu-id="bc84f-105">В этой статье приводятся вводные сведения и основные понятия, касающиеся работы с .NET в Docker.</span><span class="sxs-lookup"><span data-stu-id="bc84f-105">This article provides an introduction and conceptual background to working with .NET on Docker.</span></span>

## <a name="docker-packaging-your-apps-to-deploy-and-run-anywhere"></a><span data-ttu-id="bc84f-106">Docker: упаковка приложений для развертывания и выполнения в любом месте</span><span class="sxs-lookup"><span data-stu-id="bc84f-106">Docker: Packaging your apps to deploy and run anywhere</span></span>

<span data-ttu-id="bc84f-107">[Docker](../../standard/microservices-architecture/container-docker-introduction/docker-defined.md) — это открытая платформа, которая позволяет разработчикам и администраторам создавать [образы](https://docs.docker.com/glossary/?term=image), а также доставлять и запускать распределенные приложения в слабо изолированной среде, называемой [контейнером](https://www.docker.com/what-container).</span><span class="sxs-lookup"><span data-stu-id="bc84f-107">[Docker](../../standard/microservices-architecture/container-docker-introduction/docker-defined.md) is an open platform that enables developers and administrators to build [images](https://docs.docker.com/glossary/?term=image), ship, and run distributed applications in a loosely isolated environment called a [container](https://www.docker.com/what-container).</span></span> <span data-ttu-id="bc84f-108">Такой подход позволяет эффективно управлять жизненным циклом приложений в средах разработки и контроля качества, а также в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="bc84f-108">This approach enables efficient application lifecycle management between development, QA, and production environments.</span></span>
 
<span data-ttu-id="bc84f-109">[Платформа Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) использует [подсистему Docker](https://docs.docker.com/engine/docker-overview/#docker-engine), чтобы обеспечить быстрое создание и упаковку приложений в виде [образов Docker](https://docs.docker.com/glossary/?term=image), созданных с помощью файлов в формате [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile), которые затем развертываются и запускаются в [многослойном контейнере](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span><span class="sxs-lookup"><span data-stu-id="bc84f-109">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image) created using files written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format that then is deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>

<span data-ttu-id="bc84f-110">Вы можете создавать собственные [многослойные образы](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) в виде файлов Dockerfile или использовать существующие образы из [реестра](https://docs.docker.com/glossary/?term=registry), например [Docker Hub](https://docs.docker.com/glossary/?term=Docker%20Hub).</span><span class="sxs-lookup"><span data-stu-id="bc84f-110">You can either create your own [layered images](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) as dockerfiles or use existing ones from a [registry](https://docs.docker.com/glossary/?term=registry), like [Docker Hub](https://docs.docker.com/glossary/?term=Docker%20Hub).</span></span>

<span data-ttu-id="bc84f-111">[Связь между контейнерами, образами и реестрами Docker](../../standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries.md) — это важный элемент в [разработке архитектуры и создании контейнерных приложений или микрослужб](../../standard/microservices-architecture/architect-microservice-container-applications/index.md).</span><span class="sxs-lookup"><span data-stu-id="bc84f-111">The [relationship between Docker containers, images, and registries](../../standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries.md) is an important concept when [architecting and building containerized applications or microservices](../../standard/microservices-architecture/architect-microservice-container-applications/index.md).</span></span> <span data-ttu-id="bc84f-112">Этой подход значительно сокращает время между разработкой и развертыванием.</span><span class="sxs-lookup"><span data-stu-id="bc84f-112">This approach greatly shortens the time between development and deployment.</span></span>

### <a name="further-reading-and-watching"></a><span data-ttu-id="bc84f-113">Дополнительные ресурсы и видеоматериалы</span><span class="sxs-lookup"><span data-stu-id="bc84f-113">Further reading (and watching)</span></span>

* <span data-ttu-id="bc84f-114">[Windows-based containers: Modern app development with enterprise-grade control](https://www.youtube.com/watch?v=Ryx3o0rD5lY&feature=youtu.be) (Контейнеры для Windows. Разработка современных приложений с управлением на уровне организации)</span><span class="sxs-lookup"><span data-stu-id="bc84f-114">[Windows-based containers: Modern app development with enterprise-grade control.](https://www.youtube.com/watch?v=Ryx3o0rD5lY&feature=youtu.be)</span></span>
* <span data-ttu-id="bc84f-115">[Docker overview](https://docs.docker.com/engine/docker-overview/) (Общие сведения о Docker)</span><span class="sxs-lookup"><span data-stu-id="bc84f-115">[Docker overview](https://docs.docker.com/engine/docker-overview/)</span></span>
* [<span data-ttu-id="bc84f-116">Dockerfile в контейнерах Windows</span><span class="sxs-lookup"><span data-stu-id="bc84f-116">Dockerfile on Windows Containers</span></span>](/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* <span data-ttu-id="bc84f-117">[Best practices for writing Dockerfiles](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/) (Рекомендации по созданию файлов Dockerfile)</span><span class="sxs-lookup"><span data-stu-id="bc84f-117">[Best practices for writing Dockerfiles](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)</span></span>
* [<span data-ttu-id="bc84f-118">Создание образов Docker для приложений .NET Core</span><span class="sxs-lookup"><span data-stu-id="bc84f-118">Building Docker Images for .NET Core applications</span></span>](../docker/building-net-docker-images.md)


### <a name="getting-net-docker-images"></a><span data-ttu-id="bc84f-119">Получение образов Docker для .NET</span><span class="sxs-lookup"><span data-stu-id="bc84f-119">Getting .NET Docker images</span></span>

<span data-ttu-id="bc84f-120">Корпорация Майкрософт создает и оптимизирует официальные образы Docker для .NET.</span><span class="sxs-lookup"><span data-stu-id="bc84f-120">The Official .NET Docker images are created and optimized by Microsoft.</span></span> <span data-ttu-id="bc84f-121">Они доступны для всех в репозиториях Майкрософт в Docker Hub.</span><span class="sxs-lookup"><span data-stu-id="bc84f-121">They are publicly available in the Microsoft repositories on Docker Hub.</span></span> <span data-ttu-id="bc84f-122">Каждый репозиторий может содержать несколько образов в зависимости от версий .NET и версий ОС.</span><span class="sxs-lookup"><span data-stu-id="bc84f-122">Each repository can contain multiple images, depending on .NET versions, and on OS versions.</span></span> <span data-ttu-id="bc84f-123">Большинство репозиториев образов предоставляют широкие возможности по использованию тегов, чтобы облегчить выбор конкретной версии платформы и ОС (дистрибутива Linux или версии Windows).</span><span class="sxs-lookup"><span data-stu-id="bc84f-123">Most image repos provide extensive tagging to help you select both a specific framework version and an OS (Linux distro or Windows version).</span></span>

## <a name="scenario-based-guidance"></a><span data-ttu-id="bc84f-124">Рекомендации на основе сценариев</span><span class="sxs-lookup"><span data-stu-id="bc84f-124">Scenario based guidance</span></span>

<span data-ttu-id="bc84f-125">Корпорация Майкрософт стремится создавать подробные специализированные репозитории .NET, представляющие конкретный сценарий или рабочую нагрузку.</span><span class="sxs-lookup"><span data-stu-id="bc84f-125">Microsoft’s intent for .NET repositories is to have granular and focused repos, which represent a specific scenario or workload.</span></span>

<span data-ttu-id="bc84f-126">Образы `microsoft/aspnetcore` оптимизированы для приложений ASP.NET Core в Docker, что позволяет запускать контейнеры быстрее.</span><span class="sxs-lookup"><span data-stu-id="bc84f-126">The `microsoft/aspnetcore` images are optimized for ASP.NET Core apps on Docker, so containers can start faster.</span></span>

<span data-ttu-id="bc84f-127">Образы .NET Core (`microsoft/dotnet`) предназначены для консольных приложений на базе .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bc84f-127">The .NET Core images (`microsoft/dotnet`) are intended for console apps based on .NET Core.</span></span> <span data-ttu-id="bc84f-128">Например, для процессов пакетной обработки, веб-заданий Azure и других консольных сценариев следует использовать оптимизированные образы .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bc84f-128">For example, batch processes, Azure WebJobs, and other console scenarios should use optimized .NET Core images.</span></span>

<span data-ttu-id="bc84f-129">Наиболее очевидным однотипным сценарием использования приложений Docker и .NET является развертывание в рабочей среде и размещение.</span><span class="sxs-lookup"><span data-stu-id="bc84f-129">The most obvious horizontal scenario for using Docker and .NET applications is for production deployment and hosting.</span></span> <span data-ttu-id="bc84f-130">Как оказывается, разработка — это всего лишь один из сценариев. Остальные не менее практичны.</span><span class="sxs-lookup"><span data-stu-id="bc84f-130">It turns out that production is just one scenario and the other ones are equally useful.</span></span> <span data-ttu-id="bc84f-131">Эти сценарии можно применять для большинства платформ разработки, а не только для .NET.</span><span class="sxs-lookup"><span data-stu-id="bc84f-131">These scenarios are not specific to .NET, but should apply to most developer platforms.</span></span>

* <span data-ttu-id="bc84f-132">**Установка по пути наименьшего сопротивления.** Можно опробовать .NET без локальной установки.</span><span class="sxs-lookup"><span data-stu-id="bc84f-132">**Low friction install** — You can try out .NET without a local install.</span></span> <span data-ttu-id="bc84f-133">Просто скачайте образ Docker с .NET.</span><span class="sxs-lookup"><span data-stu-id="bc84f-133">Just download a Docker image with .NET in it.</span></span>

* <span data-ttu-id="bc84f-134">**Разработка в контейнере.** Вы можете выполнять разработку в согласованной среде, создав рабочую среду, аналогичную среде разработки (это позволяет избежать такой проблемы, как глобальное состояние на компьютерах для разработки).</span><span class="sxs-lookup"><span data-stu-id="bc84f-134">**Develop in a container** — You can develop in a consistent environment, making development and production environments similar (avoiding issues like global state on developer machines).</span></span> <span data-ttu-id="bc84f-135">Средства Visual Studio для Docker даже позволяют запускать контейнеры прямо из Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bc84f-135">Visual Studio Tools for Docker even enable you to start a container directly from Visual Studio.</span></span>

* <span data-ttu-id="bc84f-136">**Тестирование в контейнере.** Тестирование можно проводить в контейнере, благодаря чему уменьшается число сбоев из-за неправильно настроенной среды или других изменений, оставшихся после последнего тестирования.</span><span class="sxs-lookup"><span data-stu-id="bc84f-136">**Test in a container** — You can test in a container, reducing failures due to incorrectly configured environments or other changes left behind from the last test.</span></span>

* <span data-ttu-id="bc84f-137">**Сборка в контейнере.** Вы можете выполнить сборку кода в контейнере, чтобы не настраивать общие компьютеры сборки для нескольких сред, а перейти на подход BYOC (использование собственного контейнера).</span><span class="sxs-lookup"><span data-stu-id="bc84f-137">**Build in a container** — You can build code in a container, avoiding the need to correctly configure shared build machines for multiple environments but instead move to a “BYOC” (bring your own container) approach.</span></span>

* <span data-ttu-id="bc84f-138">**Развертывание во всех средах.** Вы можете развернуть образ во всех своих средах.</span><span class="sxs-lookup"><span data-stu-id="bc84f-138">**Deployment in all environments** — You can deploy an image through all of your environments.</span></span> <span data-ttu-id="bc84f-139">Этот подход позволяет сократить число сбоев из-за различий в настройках. Как правило, поведение образа меняется через внешнюю конфигурацию (например, внедренные переменные среды).</span><span class="sxs-lookup"><span data-stu-id="bc84f-139">This approach reduces failures due to configuration differences, typically changing the image behavior via external configuration (for example, injected environment variables).</span></span>

<span data-ttu-id="bc84f-140">[Общие рекомендации](../../standard/microservices-architecture/net-core-net-framework-containers/general-guidance.md) по выбору между .NET Core и .NET Framework для разработки контейнеров Docker.</span><span class="sxs-lookup"><span data-stu-id="bc84f-140">[General guidance](../../standard/microservices-architecture/net-core-net-framework-containers/general-guidance.md) for deciding between .NET Core and .NET Framework for Docker container development.</span></span>

### <a name="common-docker-development-scenarios"></a><span data-ttu-id="bc84f-141">Распространенные сценарии разработки Docker</span><span class="sxs-lookup"><span data-stu-id="bc84f-141">Common Docker development scenarios</span></span>

#### <a name="net-core"></a><span data-ttu-id="bc84f-142">.NET Core</span><span class="sxs-lookup"><span data-stu-id="bc84f-142">.NET Core</span></span>

<span data-ttu-id="bc84f-143">**Ресурсы .NET Core**</span><span class="sxs-lookup"><span data-stu-id="bc84f-143">**.NET Core resources**</span></span>

 <span data-ttu-id="bc84f-144">Выберите примеры .NET Core, которые соответствуют вашему сценарию.</span><span class="sxs-lookup"><span data-stu-id="bc84f-144">Pick the .NET Core samples that fit your scenarios of interest.</span></span> <span data-ttu-id="bc84f-145">Во всех инструкциях в примерах описывается, как использовать образы Docker для Windows или Linux в качестве целевых сред на узлах Windows, Linux или macOS.</span><span class="sxs-lookup"><span data-stu-id="bc84f-145">All sample instructions describe how to target Windows or Linux Docker images from Windows, Linux, or macOS hosts.</span></span>

<span data-ttu-id="bc84f-146">В примерах используется .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="bc84f-146">The samples use .NET Core 2.0.</span></span> <span data-ttu-id="bc84f-147">В примерах при необходимости используется [многоэтапная сборка](https://github.com/dotnet/announcements/issues/18) и [теги для разных архитектур](https://github.com/dotnet/announcements/issues/14) Docker.</span><span class="sxs-lookup"><span data-stu-id="bc84f-147">They use Docker [multi-stage build](https://github.com/dotnet/announcements/issues/18) and [multi-arch tags](https://github.com/dotnet/announcements/issues/14) where appropriate.</span></span>

* [<span data-ttu-id="bc84f-148">Образы для .NET Core в Docker Hub</span><span class="sxs-lookup"><span data-stu-id="bc84f-148">.NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/dotnet/)

* [<span data-ttu-id="bc84f-149">Добавление приложения .NET Core в Docker</span><span class="sxs-lookup"><span data-stu-id="bc84f-149">Dockerize a .NET Core application</span></span>](https://docs.docker.com/engine/examples/dotnetcore/)

* <span data-ttu-id="bc84f-150">В этом примере Docker для .NET Core показано, как [использовать Docker в процессе разработки .NET Core](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev).</span><span class="sxs-lookup"><span data-stu-id="bc84f-150">This .NET Core Docker sample demonstrates how to [use Docker in your .NET Core development process](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev).</span></span> <span data-ttu-id="bc84f-151">Этот пример поддерживается в контейнерах Linux и Windows.</span><span class="sxs-lookup"><span data-stu-id="bc84f-151">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="bc84f-152">В этом примере Docker для .NET Core демонстрируется рекомендуемый шаблон [создания образов Docker для приложений .NET Core в рабочей среде](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod).</span><span class="sxs-lookup"><span data-stu-id="bc84f-152">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span></span> <span data-ttu-id="bc84f-153">Этот пример поддерживается в контейнерах Linux и Windows.</span><span class="sxs-lookup"><span data-stu-id="bc84f-153">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="bc84f-154">В этом [примере Docker для .NET Core](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained) демонстрируется рекомендуемый шаблон для создания образов Docker для [автономных приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="bc84f-154">This [.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained) demonstrates a best practice pattern for building Docker images for [self-contained .NET Core applications](../deploying/index.md).</span></span> <span data-ttu-id="bc84f-155">Используется для наименьшего контейнера без возможности [предоставлять контейнерам общий доступ к базовым образам](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/).</span><span class="sxs-lookup"><span data-stu-id="bc84f-155">Used for the smallest production container without a benefit from [sharing base images between containers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/).</span></span> <span data-ttu-id="bc84f-156">Но слои Docker могут использоваться совместно.</span><span class="sxs-lookup"><span data-stu-id="bc84f-156">However, lower Docker layers could be shared.</span></span>

#### <a name="arm32--raspberry-pi"></a><span data-ttu-id="bc84f-157">ARM32 или Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="bc84f-157">ARM32 / Raspberry Pi</span></span>

* [<span data-ttu-id="bc84f-158">Объявление о доступности сборок ARM32 для среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="bc84f-158">.NET Core Runtime ARM32 builds announcement</span></span>](https://github.com/dotnet/announcements/issues/29)

* [<span data-ttu-id="bc84f-159">Образы ARM32 и Raspberry Pi для .NET Core в Docker Hub</span><span class="sxs-lookup"><span data-stu-id="bc84f-159">ARM32 / Raspberry Pi .NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/dotnet/)

* [<span data-ttu-id="bc84f-160">Примеры ARM32 и Raspberry Pi для .NET Core в GitHub</span><span class="sxs-lookup"><span data-stu-id="bc84f-160">ARM32 / Raspberry Pi .NET Core Docker Samples on GitHub</span></span>](https://github.com/dotnet/dotnet-docker-samples#arm32--raspberry-pi)

#### <a name="net-framework"></a><span data-ttu-id="bc84f-161">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="bc84f-161">.NET Framework</span></span>

* [<span data-ttu-id="bc84f-162">Образы .NET Framework в Docker Hub</span><span class="sxs-lookup"><span data-stu-id="bc84f-162">.NET Framework images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/dotnet-framework/)

<span data-ttu-id="bc84f-163">Этот репозиторий содержит примеры различных конфигураций Docker для .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bc84f-163">This repo contain samples that demonstrate various .NET Framework Docker configurations.</span></span> <span data-ttu-id="bc84f-164">Вы можете использовать эти образы в качестве основы для своих образов Docker.</span><span class="sxs-lookup"><span data-stu-id="bc84f-164">You can use these images as the basis of your own Docker images.</span></span>

<span data-ttu-id="bc84f-165">**.NET Framework 4.7**</span><span class="sxs-lookup"><span data-stu-id="bc84f-165">**.NET Framework 4.7**</span></span>

<span data-ttu-id="bc84f-166">Пример [dotnet-framework:4.7](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7) демонстрирует использование базового приложения Hello World на платформе [.NET Framework 4.7](../../framework/whats-new/index.md#v47).</span><span class="sxs-lookup"><span data-stu-id="bc84f-166">The [dotnet-framework:4.7 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7) demonstrates basic "hello world" usage of the [.NET Framework 4.7](../../framework/whats-new/index.md#v47).</span></span> <span data-ttu-id="bc84f-167">Также в нем показано, как создать и развернуть приложение на основе [образа Docker для .NET Framework 4.7](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-4.7/Dockerfile).</span><span class="sxs-lookup"><span data-stu-id="bc84f-167">It shows you how you can build and deploy the app relying on the [.NET Framework 4.7 docker image](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-4.7/Dockerfile).</span></span>

<span data-ttu-id="bc84f-168">**.NET Framework 4.6.2**</span><span class="sxs-lookup"><span data-stu-id="bc84f-168">**.NET Framework 4.6.2**</span></span>

<span data-ttu-id="bc84f-169">В примере [dotnet-framework:4.6.2](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2) демонстрируется использование базового приложения Hello World на платформе [.NET Framework 4.6.2](../../framework/whats-new/index.md#v462).</span><span class="sxs-lookup"><span data-stu-id="bc84f-169">The [dotnet-framework:4.6.2 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2) demonstrates basic "hello world" usage of the [.NET Framework 4.6.2](../../framework/whats-new/index.md#v462).</span></span> <span data-ttu-id="bc84f-170">Также в нем показано, как создать и развернуть приложение на основе [образа Docker для .NET Framework 4.6.2](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-4.6.2/Dockerfile)</span><span class="sxs-lookup"><span data-stu-id="bc84f-170">It shows you how you can build and deploy the app relying on the [.NET Framework 4.6.2 docker image](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-4.6.2/Dockerfile).</span></span>

<span data-ttu-id="bc84f-171">**.NET Framework 3.5**</span><span class="sxs-lookup"><span data-stu-id="bc84f-171">**.NET Framework 3.5**</span></span>

 <span data-ttu-id="bc84f-172">В примере [dotnet-framework:3.5](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5) демонстрируется использование базового приложения Hello World на платформе [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-3.5/dotnetapp-3.5/Dockerfile).</span><span class="sxs-lookup"><span data-stu-id="bc84f-172">The [dotnet-framework:3.5 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5) demonstrates basic "hello world" usage of [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-3.5/dotnetapp-3.5/Dockerfile).</span></span> <span data-ttu-id="bc84f-173">Также в нем показано, как создать и развернуть проект на основе .NET Framework 3.5 в Docker.</span><span class="sxs-lookup"><span data-stu-id="bc84f-173">It shows you how you can build and deploy a project relying on .NET Framework 3.5 in Docker.</span></span>

#### <a name="aspnet-core"></a><span data-ttu-id="bc84f-174">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bc84f-174">ASP.NET Core</span></span>

* <span data-ttu-id="bc84f-175">[В этом примере Docker для ASP.NET Core](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) демонстрируется рекомендуемый шаблон создания образов Docker для приложений ASP.NET Core в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="bc84f-175">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="bc84f-176">Этот пример поддерживается в контейнерах Linux и Windows.</span><span class="sxs-lookup"><span data-stu-id="bc84f-176">The sample works with both Linux and Windows containers.</span></span>

* [<span data-ttu-id="bc84f-177">Образы для ASP.NET Core в Docker Hub</span><span class="sxs-lookup"><span data-stu-id="bc84f-177">ASP.NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnetcore-build/)

* [<span data-ttu-id="bc84f-178">Образы для ASP.NET Core в GitHub</span><span class="sxs-lookup"><span data-stu-id="bc84f-178">ASP.NET Core images on GitHub</span></span>](https://github.com/aspnet/aspnet-docker)

#### <a name="aspnet-framework"></a><span data-ttu-id="bc84f-179">ASP.NET Framework</span><span class="sxs-lookup"><span data-stu-id="bc84f-179">ASP.NET Framework</span></span>

* [<span data-ttu-id="bc84f-180">Образы для ASP.NET Framework в Docker Hub</span><span class="sxs-lookup"><span data-stu-id="bc84f-180">ASP.NET Framework images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnet/)

* [<span data-ttu-id="bc84f-181">Пример приложения веб-форм ASP.NET в .NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="bc84f-181">ASP.NET Web Forms app on .NET Framework 4.6.2 sample</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/aspnetapp)

#### <a name="windows-communication-framework-wcf"></a><span data-ttu-id="bc84f-182">Windows Communication Framework (WCF)</span><span class="sxs-lookup"><span data-stu-id="bc84f-182">Windows Communication Framework (WCF)</span></span>

* [<span data-ttu-id="bc84f-183">Образы для WCF в Docker Hub</span><span class="sxs-lookup"><span data-stu-id="bc84f-183">Windows Communication Framework (WCF) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/wcf/)

* [<span data-ttu-id="bc84f-184">Образы для WCF в GitHub</span><span class="sxs-lookup"><span data-stu-id="bc84f-184">Windows Communication Framework (WCF) images on GitHub</span></span>](https://github.com/microsoft/wcf-docker)

* [<span data-ttu-id="bc84f-185">Примеры Docker для WCF с использованием .NET Full Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="bc84f-185">Windows Communication Framework (WCF) Docker samples using .NET Full Framework 4.6.2</span></span>](https://github.com/Microsoft/wcf-docker-samples)

#### <a name="internet-information-server-iis"></a><span data-ttu-id="bc84f-186">Internet Information Server (IIS)</span><span class="sxs-lookup"><span data-stu-id="bc84f-186">Internet Information Server (IIS)</span></span>

* [<span data-ttu-id="bc84f-187">Образы для IIS в Docker Hub</span><span class="sxs-lookup"><span data-stu-id="bc84f-187">Internet Information Server (IIS) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/iis/)

* [<span data-ttu-id="bc84f-188">Образы для IIS в GitHub</span><span class="sxs-lookup"><span data-stu-id="bc84f-188">Internet Information Server (IIS) images on GitHub</span></span>](https://github.com/microsoft/iis-docker)

### <a name="interact-with-other-microsoft-stack-container-images"></a><span data-ttu-id="bc84f-189">Взаимодействие с другими образами контейнеров стека Microsoft</span><span class="sxs-lookup"><span data-stu-id="bc84f-189">Interact with other Microsoft stack container images</span></span>

#### <a name="microsoft-sql-server"></a><span data-ttu-id="bc84f-190">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="bc84f-190">Microsoft SQL Server</span></span>

* [<span data-ttu-id="bc84f-191">Краткое руководство по запуску образа контейнера Microsoft SQL Server для Linux 2017 с помощью Docker</span><span class="sxs-lookup"><span data-stu-id="bc84f-191">Run the Microsoft SQL Server for Linux 2017 container image with Docker Quickstart</span></span>](https://docs.microsoft.com/sql/linux/quickstart-install-connect-docker)

* [<span data-ttu-id="bc84f-192">Образы Microsoft SQL Server для Linux в Docker Hub</span><span class="sxs-lookup"><span data-stu-id="bc84f-192">Microsoft SQL Server for Linux images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-linux/)

* [<span data-ttu-id="bc84f-193">Образы для выпуска Microsoft SQL Server Express для контейнеров Windows в Docker Hub</span><span class="sxs-lookup"><span data-stu-id="bc84f-193">Microsoft SQL Server Express Edition images for Windows Containers on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows-express/)

* [<span data-ttu-id="bc84f-194">Образы для выпуска Microsoft SQL Server Developer для контейнеров Windows в Docker Hub</span><span class="sxs-lookup"><span data-stu-id="bc84f-194">Microsoft SQL Server Developer Edition images for Windows Containers on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows-developer/)

#### <a name="visual-studio-team-services-vsts-agent"></a><span data-ttu-id="bc84f-195">Агент Visual Studio Team Services (VSTS)</span><span class="sxs-lookup"><span data-stu-id="bc84f-195">Visual Studio Team Services (VSTS) agent</span></span>

* [<span data-ttu-id="bc84f-196">Образы для агента VSTS в Docker Hub</span><span class="sxs-lookup"><span data-stu-id="bc84f-196">Visual Studio Team Services (VSTS) agent images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/vsts-agent/)

* [<span data-ttu-id="bc84f-197">Образы для агента VSTS в GitHub</span><span class="sxs-lookup"><span data-stu-id="bc84f-197">Visual Studio Team Services (VSTS) agent images on GitHub</span></span>](https://github.com/Microsoft/vsts-agent-docker)

#### <a name="operations-management-suite-oms-linux-agent"></a><span data-ttu-id="bc84f-198">Агент Operations Management Suite (OMS) для Linux</span><span class="sxs-lookup"><span data-stu-id="bc84f-198">Operations Management Suite (OMS) Linux agent</span></span>

* [<span data-ttu-id="bc84f-199">Обзор агента OMS для Linux</span><span class="sxs-lookup"><span data-stu-id="bc84f-199">Operations Management Suite (OMS) Linux agent overview</span></span>](https://github.com/Microsoft/OMS-Agent-for-Linux/blob/master/docs/Docker-Instructions.md)

* [<span data-ttu-id="bc84f-200">Образы для агента OMS для Linux в Docker Hub</span><span class="sxs-lookup"><span data-stu-id="bc84f-200">Operations Management Suite (OMS) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/oms/)

* [<span data-ttu-id="bc84f-201">Образы для агента OMS в GitHub</span><span class="sxs-lookup"><span data-stu-id="bc84f-201">Operations Management Suite (OMS) images on GitHub</span></span>](https://github.com/Microsoft/OMS-docker)

#### <a name="microsoft-azure-command-line-interface-cli"></a><span data-ttu-id="bc84f-202">Интерфейс командной строки Microsoft Azure (CLI)</span><span class="sxs-lookup"><span data-stu-id="bc84f-202">Microsoft Azure Command Line Interface (CLI)</span></span>

* [<span data-ttu-id="bc84f-203">Образы для Microsoft Azure CLI в Docker Hub</span><span class="sxs-lookup"><span data-stu-id="bc84f-203">Microsoft Azure Command Line Interface (CLI) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/azure-cli/) 

* [<span data-ttu-id="bc84f-204">Образы для Microsoft Azure CLI в GitHub</span><span class="sxs-lookup"><span data-stu-id="bc84f-204">Microsoft Azure Command-Line Interface (CLI) images on GitHub</span></span>](https://github.com/Azure/azure-cli#Docker)

> [!NOTE]
> <span data-ttu-id="bc84f-205">Если у вас нет подписки Azure, [зарегистрируйте сейчас](https://azure.microsoft.com/free/?b=16.48) бесплатную учетную запись на 30 дней и получите 200 долл. США на счет в Azure, чтобы опробовать любое сочетание служб Azure.</span><span class="sxs-lookup"><span data-stu-id="bc84f-205">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>

#### <a name="microsoft-azure-cosmos-db-emulator-windows-containers-only"></a><span data-ttu-id="bc84f-206">Эмулятор Microsoft Azure Cosmos DB (только для контейнеров Windows)</span><span class="sxs-lookup"><span data-stu-id="bc84f-206">Microsoft Azure Cosmos DB Emulator (Windows Containers only)</span></span>

* [<span data-ttu-id="bc84f-207">Образы для эмулятора Microsoft Azure Cosmos DB в Docker Hub</span><span class="sxs-lookup"><span data-stu-id="bc84f-207">Microsoft Azure Cosmos DB Emulator images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator) 

* [<span data-ttu-id="bc84f-208">Использование эмулятора Azure Cosmos DB для разработки и тестирования в локальной среде</span><span class="sxs-lookup"><span data-stu-id="bc84f-208">Use the Azure Cosmos DB Emulator for local development and testing</span></span>](/azure/cosmos-db/local-emulator#developing-with-the-emulator)

## <a name="exploring-the-rich-docker-development-ecosystem"></a><span data-ttu-id="bc84f-209">Изучение обширной экосистемы разработки Docker</span><span class="sxs-lookup"><span data-stu-id="bc84f-209">Exploring the rich Docker development ecosystem</span></span>

<span data-ttu-id="bc84f-210">Теперь, когда вы узнали о платформе Docker и различных образах Docker, мы перейдем к изучению обширной экосистемы Docker.</span><span class="sxs-lookup"><span data-stu-id="bc84f-210">Now that you have learned about the Docker platform and different Docker images, the next step is to explore the rich Docker ecosystem.</span></span> <span data-ttu-id="bc84f-211">Из указанных ниже ресурсов вы узнаете, как средства Майкрософт дополняют средства разработки контейнеров.</span><span class="sxs-lookup"><span data-stu-id="bc84f-211">The following links show you how the Microsoft tools complement container development.</span></span>

* <span data-ttu-id="bc84f-212">[Using .NET and Docker Together](https://blogs.msdn.microsoft.com/dotnet/2017/05/25/using-net-and-docker-together/) (Совместное использование .NET и Docker)</span><span class="sxs-lookup"><span data-stu-id="bc84f-212">[Using .NET and Docker together](https://blogs.msdn.microsoft.com/dotnet/2017/05/25/using-net-and-docker-together/)</span></span>
* [<span data-ttu-id="bc84f-213">Проектирование и разработка приложений .NET на основе множества контейнеров и микрослужб</span><span class="sxs-lookup"><span data-stu-id="bc84f-213">Designing and Developing Multi-Container and Microservice-Based .NET Applications</span></span>](../../standard/microservices-architecture/multi-container-microservice-net-applications/index.md)
* [<span data-ttu-id="bc84f-214">Расширение Docker для Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="bc84f-214">Visual Studio Code Docker extension</span></span>](https://code.visualstudio.com/docs/languages/dockerfile)
* [<span data-ttu-id="bc84f-215">Сведения об использовании Azure Service Fabric</span><span class="sxs-lookup"><span data-stu-id="bc84f-215">Learn how to use Azure Service Fabric</span></span>](/azure/service-fabric/index)
* <span data-ttu-id="bc84f-216">[Service Fabric Getting Started Sample](https://azure.microsoft.com/resources/samples/service-fabric-dotnet-getting-started/) (Пример начала работы с Service Fabric)</span><span class="sxs-lookup"><span data-stu-id="bc84f-216">[Service Fabric Getting Started Sample](https://azure.microsoft.com/resources/samples/service-fabric-dotnet-getting-started/)</span></span>
* [<span data-ttu-id="bc84f-217">Преимущества контейнеров Windows</span><span class="sxs-lookup"><span data-stu-id="bc84f-217">Benefits of Windows Containers</span></span>](/virtualization/windowscontainers/about/index#video-overview)
* [<span data-ttu-id="bc84f-218">Работа со средствами Visual Studio для Docker</span><span class="sxs-lookup"><span data-stu-id="bc84f-218">Working with Visual Studio Docker Tools</span></span>](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker)
* <span data-ttu-id="bc84f-219">[Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/) (Развертывание образов Docker из реестра контейнеров Azure в службе "Экземпляры контейнеров Azure")</span><span class="sxs-lookup"><span data-stu-id="bc84f-219">[Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)</span></span>
* [<span data-ttu-id="bc84f-220">Отладка с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="bc84f-220">Debugging with Visual Studio Code</span></span>](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container)
* <span data-ttu-id="bc84f-221">[Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments) (Получение практических навыков по работе с Visual Studio для Mac, контейнерами и бессерверным кодом в облаке)</span><span class="sxs-lookup"><span data-stu-id="bc84f-221">[Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)</span></span>
* <span data-ttu-id="bc84f-222">[Getting started integrating with Docker containers in Visual Studio for Mac](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started) (Приступая к интеграции с контейнерами Docker в Visual Studio для Mac)</span><span class="sxs-lookup"><span data-stu-id="bc84f-222">[Getting Started with Docker and Visual Studio for Mac Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)</span></span>

## <a name="next-steps"></a><span data-ttu-id="bc84f-223">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="bc84f-223">Next steps</span></span>

* [<span data-ttu-id="bc84f-224">Основы работы с Docker с помощью .NET Core</span><span class="sxs-lookup"><span data-stu-id="bc84f-224">Learn Docker Basics with .NET Core</span></span>](docker-basics-dotnet-core.md)
* [<span data-ttu-id="bc84f-225">Создание образов Docker для приложений .NET Core</span><span class="sxs-lookup"><span data-stu-id="bc84f-225">Building .NET Core Docker Images</span></span>](building-net-docker-images.md)
