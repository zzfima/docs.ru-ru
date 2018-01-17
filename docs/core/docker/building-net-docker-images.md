---
title: "Создание образов Docker для .NET Core"
description: "Общие сведения об образах Docker и .NET Core"
keywords: .NET, .NET Core, Docker
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
ms.custom: mvc
manager: wpickett
ms.workload: dotnetcore
ms.openlocfilehash: cb438957a6519cf503e5bcaf85f2bc82fa18a047
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="building-docker-images-for-net-core-applications"></a><span data-ttu-id="b257e-104">Создание образов Docker для приложений .NET Core</span><span class="sxs-lookup"><span data-stu-id="b257e-104">Building Docker Images for .NET Core Applications</span></span>

 <span data-ttu-id="b257e-105">Это руководство посвящено использованию .NET Core в Docker.</span><span class="sxs-lookup"><span data-stu-id="b257e-105">In this tutorial, We focus on how to use .NET Core on Docker.</span></span> <span data-ttu-id="b257e-106">Сначала мы рассмотрим различные образы Docker, предоставляемые и поддерживаемые корпорацией Майкрософт, а также варианты их использования.</span><span class="sxs-lookup"><span data-stu-id="b257e-106">First, we explore the different Docker images offered and maintained by Microsoft, and use cases.</span></span> <span data-ttu-id="b257e-107">Потом мы научимся создавать и добавлять в Docker приложение ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="b257e-107">We then learn how to build and dockerize an ASP.NET Core app.</span></span>

<span data-ttu-id="b257e-108">В ходе работы с этим руководством вы:</span><span class="sxs-lookup"><span data-stu-id="b257e-108">During the course of this tutorial, you learn:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="b257e-109">узнаете о создании образов Docker для Microsoft .NET Core;</span><span class="sxs-lookup"><span data-stu-id="b257e-109">Learn about Microsoft .NET Core Docker images</span></span> 
> * <span data-ttu-id="b257e-110">получите пример приложения ASP.NET Core для добавления в Docker;</span><span class="sxs-lookup"><span data-stu-id="b257e-110">Get an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="b257e-111">запустите пример приложения ASP.NET локально;</span><span class="sxs-lookup"><span data-stu-id="b257e-111">Run the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="b257e-112">создадите и запустите пример с Docker для контейнеров Linux;</span><span class="sxs-lookup"><span data-stu-id="b257e-112">Build and run the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="b257e-113">создадите и запустите пример с Docker для контейнеров Windows.</span><span class="sxs-lookup"><span data-stu-id="b257e-113">Build and run the sample with Docker for Windows containers</span></span>

## <a name="docker-image-optimizations"></a><span data-ttu-id="b257e-114">Оптимизация образов Docker</span><span class="sxs-lookup"><span data-stu-id="b257e-114">Docker Image Optimizations</span></span>

<span data-ttu-id="b257e-115">При создании образов Docker для разработчиков мы сосредоточились на трех основных сценариях:</span><span class="sxs-lookup"><span data-stu-id="b257e-115">When building Docker images for developers, we focused on three main scenarios:</span></span>

* <span data-ttu-id="b257e-116">образы, используемые для разработки приложений .NET Core;</span><span class="sxs-lookup"><span data-stu-id="b257e-116">Images used to develop .NET Core apps</span></span>
* <span data-ttu-id="b257e-117">образы, используемые для сборки приложений .NET Core;</span><span class="sxs-lookup"><span data-stu-id="b257e-117">Images used to build .NET Core apps</span></span>
* <span data-ttu-id="b257e-118">образы, используемые для выполнения приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b257e-118">Images used to run .NET Core apps</span></span>

<span data-ttu-id="b257e-119">Зачем нужны три образа</span><span class="sxs-lookup"><span data-stu-id="b257e-119">Why three images?</span></span>
<span data-ttu-id="b257e-120">При разработке, сборке и выполнении приложений в контейнерах приоритеты будут разными.</span><span class="sxs-lookup"><span data-stu-id="b257e-120">When developing, building, and running containerized applications, we have different priorities.</span></span>

* <span data-ttu-id="b257e-121">**Разработка**. Основное внимание уделяется быстрой итерации по изменениям и возможности их отладки.</span><span class="sxs-lookup"><span data-stu-id="b257e-121">**Development:**  The priority focuses on quickly iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="b257e-122">Размер образа не так важен, как возможность быстро вносить изменения в код и просматривать их.</span><span class="sxs-lookup"><span data-stu-id="b257e-122">The size of the image isn't as important, rather can you make changes to your code and see them quickly?</span></span>

* <span data-ttu-id="b257e-123">**Сборка**. Этот образ содержит все необходимое для компиляции приложения, включая компилятор и другие зависимости для оптимизации двоичных файлов.</span><span class="sxs-lookup"><span data-stu-id="b257e-123">**Build:** This image contains everything needed to compile your app, which includes the compiler and any other dependencies to optimize the binaries.</span></span>  <span data-ttu-id="b257e-124">Образ сборки нужен для создания ресурсов, помещаемых в рабочий образ.</span><span class="sxs-lookup"><span data-stu-id="b257e-124">You use the build image to create the assets you place into a production image.</span></span> <span data-ttu-id="b257e-125">Этот образ будет применяться при непрерывной интеграции или в среде сборки.</span><span class="sxs-lookup"><span data-stu-id="b257e-125">The build image would be used for continuous integration, or in a build environment.</span></span> <span data-ttu-id="b257e-126">Такой подход позволяет агенту сборки компилировать и собрать приложение (со всеми необходимыми зависимостями) в экземпляре образа сборки.</span><span class="sxs-lookup"><span data-stu-id="b257e-126">This approach allows a build agent to compile and build the application (with all the required dependencies) in a build image instance.</span></span> <span data-ttu-id="b257e-127">Агенту сборки необходимо знать только, как запускать этот образ Docker.</span><span class="sxs-lookup"><span data-stu-id="b257e-127">Your build agent only needs to know how to run this Docker image.</span></span>

* <span data-ttu-id="b257e-128">**Рабочая среда**. Как можно быстро развернуть и запустить образ.</span><span class="sxs-lookup"><span data-stu-id="b257e-128">**Production:** How fast you can deploy and start your image?</span></span> <span data-ttu-id="b257e-129">Этот образ имеет небольшой размер, что позволяет оптимизировать передачу по сети из реестра Docker на узлы Docker.</span><span class="sxs-lookup"><span data-stu-id="b257e-129">This image is small so network performance from your Docker Registry to your Docker hosts is optimized.</span></span> <span data-ttu-id="b257e-130">Содержимое готово к запуску, поэтому период времени от запуска Docker до обработки результатов минимален.</span><span class="sxs-lookup"><span data-stu-id="b257e-130">The contents are ready to run enabling the fastest time from Docker run to processing results.</span></span> <span data-ttu-id="b257e-131">В модели Docker динамическая компиляция кода не требуется.</span><span class="sxs-lookup"><span data-stu-id="b257e-131">Dynamic code compilation isn't needed in the Docker model.</span></span> <span data-ttu-id="b257e-132">Содержимое, помещаемое в этот образ, ограничено двоичными файлами и содержимым, которые необходимы для работы приложения.</span><span class="sxs-lookup"><span data-stu-id="b257e-132">The content you place in this image would be limited to the binaries and content needed to run the application.</span></span>

    <span data-ttu-id="b257e-133">Например, выходные данные `dotnet publish` содержат:</span><span class="sxs-lookup"><span data-stu-id="b257e-133">For example, the `dotnet publish` output contains:</span></span>

    * <span data-ttu-id="b257e-134">скомпилированные двоичные файлы;</span><span class="sxs-lookup"><span data-stu-id="b257e-134">the compiled binaries</span></span>
    * <span data-ttu-id="b257e-135">файлы JS и CSS.</span><span class="sxs-lookup"><span data-stu-id="b257e-135">.js and .css files</span></span>


<span data-ttu-id="b257e-136">Причиной для включения выходных данных команды `dotnet publish` в рабочий образ является стремление свести его размер к минимуму.</span><span class="sxs-lookup"><span data-stu-id="b257e-136">The reason to include the `dotnet publish` command output in your production image is to keep its' size to a minimum.</span></span>

<span data-ttu-id="b257e-137">Некоторые образы .NET Core совместно используют слои между разными тегами, поэтому скачивание последнего тега осуществляется довольно просто.</span><span class="sxs-lookup"><span data-stu-id="b257e-137">Some .NET Core images share layers between different tags so downloading the latest tag is a relatively lightweight process.</span></span> <span data-ttu-id="b257e-138">Если на компьютере уже есть более старая версия, эта архитектура снижает необходимое дисковое пространство.</span><span class="sxs-lookup"><span data-stu-id="b257e-138">If you already have an older version on your machine, this architecture decreases the needed disk space.</span></span>

<span data-ttu-id="b257e-139">Когда несколько приложений используют общие образы на одном компьютере, память используется этими общими образами совместно.</span><span class="sxs-lookup"><span data-stu-id="b257e-139">When multiple applications use common images on the same machine, memory is shared between the common images.</span></span> <span data-ttu-id="b257e-140">Для совместного использования образы должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="b257e-140">The images must be the same to be shared.</span></span>

## <a name="docker-image-variations"></a><span data-ttu-id="b257e-141">Варианты образов Docker</span><span class="sxs-lookup"><span data-stu-id="b257e-141">Docker image variations</span></span>

<span data-ttu-id="b257e-142">Для достижения указанных выше целей мы предоставляет варианты образов в [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="b257e-142">To achieve the goals above, we provide image variants under [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

* <span data-ttu-id="b257e-143">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) Этот образ содержит пакет SDK для .NET Core, который включает платформу .NET Core и программы командной строки (CLI).</span><span class="sxs-lookup"><span data-stu-id="b257e-143">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) This image contains the .NET Core SDK, which includes the .NET Core and Command Line Tools (CLI).</span></span> <span data-ttu-id="b257e-144">Этот образ соответствует **сценарию развертывания**.</span><span class="sxs-lookup"><span data-stu-id="b257e-144">This image maps to the **development scenario**.</span></span> <span data-ttu-id="b257e-145">Он используется для локальной разработки, отладки и модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="b257e-145">You use this image for local development, debugging, and unit testing.</span></span> <span data-ttu-id="b257e-146">Этот образ также можно использовать для сценариев **сборки**.</span><span class="sxs-lookup"><span data-stu-id="b257e-146">This image can also be used for your **build** scenarios.</span></span> <span data-ttu-id="b257e-147">Использование `microsoft/dotnet:sdk` всегда предоставляет последнюю версию.</span><span class="sxs-lookup"><span data-stu-id="b257e-147">Using `microsoft/dotnet:sdk` always gives you the latest version.</span></span>

> [!TIP]
> <span data-ttu-id="b257e-148">Если вы точно не знаете о своих потребностях, рекомендуется использовать образ `microsoft/dotnet:<version>-sdk`.</span><span class="sxs-lookup"><span data-stu-id="b257e-148">If you are unsure about your needs, you want to use the `microsoft/dotnet:<version>-sdk` image.</span></span> <span data-ttu-id="b257e-149">Являясь образом "де-факто", он предназначен для использования в качестве одноразового контейнера (подключите исходный код и запустите контейнер для запуска приложения) и в качестве базового образа для создания других образов.</span><span class="sxs-lookup"><span data-stu-id="b257e-149">As the "de facto" image, it's designed to be used as a throw away container (mount your source code and start the container to start your app), and as the base image to build other images from.</span></span>

* <span data-ttu-id="b257e-150">`microsoft/dotnet:<version>-runtime`. Этот образ содержит .NET Core (среду выполнения и библиотеки) и оптимизирован для запуска приложений .NET Core в **рабочей среде**.</span><span class="sxs-lookup"><span data-stu-id="b257e-150">`microsoft/dotnet:<version>-runtime`: This image contains the .NET Core (runtime and libraries) and is optimized for running .NET Core apps in **production**.</span></span>

## <a name="alternative-images"></a><span data-ttu-id="b257e-151">Альтернативные образы</span><span class="sxs-lookup"><span data-stu-id="b257e-151">Alternative images</span></span>

<span data-ttu-id="b257e-152">Помимо образов, оптимизированных для разработки, сборки и рабочей среды, мы предоставляем дополнительные образы.</span><span class="sxs-lookup"><span data-stu-id="b257e-152">In addition to the optimized scenarios of development, build and production, we provide additional images:</span></span>

* <span data-ttu-id="b257e-153">`microsoft/dotnet:<version>-runtime-deps`. Образ **runtime-deps** содержит операционную систему со всеми собственными зависимостями, требуемыми платформе .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b257e-153">`microsoft/dotnet:<version>-runtime-deps`: The **runtime-deps** image contains the operating system with all of the native dependencies needed by .NET Core.</span></span> <span data-ttu-id="b257e-154">Этот образ предназначен для [автономных приложений](https://docs.microsoft.com/dotnet/core/deploying/index).</span><span class="sxs-lookup"><span data-stu-id="b257e-154">This image is for [self-contained applications](https://docs.microsoft.com/dotnet/core/deploying/index).</span></span>

<span data-ttu-id="b257e-155">Последние версии каждого варианта:</span><span class="sxs-lookup"><span data-stu-id="b257e-155">Latest versions of each variant:</span></span>

* <span data-ttu-id="b257e-156">`microsoft/dotnet` или `microsoft/dotnet:latest` (псевдоним для образа SDK)</span><span class="sxs-lookup"><span data-stu-id="b257e-156">`microsoft/dotnet` or `microsoft/dotnet:latest` (alias for the SDK image)</span></span>
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a><span data-ttu-id="b257e-157">Примеры для изучения</span><span class="sxs-lookup"><span data-stu-id="b257e-157">Samples to explore</span></span>

* <span data-ttu-id="b257e-158">[В этом примере Docker для ASP.NET Core](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) демонстрируется рекомендуемый шаблон создания образов Docker для приложений ASP.NET Core в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="b257e-158">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="b257e-159">Этот пример поддерживается в контейнерах Linux и Windows.</span><span class="sxs-lookup"><span data-stu-id="b257e-159">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="b257e-160">В этом примере Docker для .NET Core демонстрируется рекомендуемый шаблон [создания образов Docker для приложений .NET Core в рабочей среде](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod).</span><span class="sxs-lookup"><span data-stu-id="b257e-160">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span></span>

## <a name="your-first-aspnet-core-docker-app"></a><span data-ttu-id="b257e-161">Ваше первое приложение Docker для ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b257e-161">Your first ASP.NET Core Docker app</span></span>

<span data-ttu-id="b257e-162">В этом руководстве мы будем использовать пример приложения Docker для ASP.NET Core в качестве приложения, которое хотим добавить в Docker.</span><span class="sxs-lookup"><span data-stu-id="b257e-162">For this tutorial, lets use an ASP.NET Core Docker sample application for the app we want to dockerize.</span></span> <span data-ttu-id="b257e-163">Этот пример приложения Docker для ASP.NET Core демонстрирует рекомендуемый шаблон создания образов Docker для приложений ASP.NET Core в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="b257e-163">This ASP.NET Core Docker sample application demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="b257e-164">Этот пример поддерживается в контейнерах Linux и Windows.</span><span class="sxs-lookup"><span data-stu-id="b257e-164">The sample works with both Linux and Windows containers.</span></span>

<span data-ttu-id="b257e-165">Пример Dockerfile создает образ Docker для приложения ASP.NET Core на основе базового образа Docker для среды выполнения ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="b257e-165">The sample Dockerfile creates an ASP.NET Core application Docker image based off of the ASP.NET Core Runtime Docker base image.</span></span>

<span data-ttu-id="b257e-166">Он использует [функцию многоэтапной сборки Docker](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) для:</span><span class="sxs-lookup"><span data-stu-id="b257e-166">It uses the [Docker multi-stage build feature](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) to:</span></span>

* <span data-ttu-id="b257e-167">сборки примера в контейнере на основе **большего по размеру** базового образа Docker сборки ASP.NET Core;</span><span class="sxs-lookup"><span data-stu-id="b257e-167">build the sample in a container based on the **larger** ASP.NET Core Build Docker base image</span></span> 
* <span data-ttu-id="b257e-168">копирование итогового результата сборки в образ Docker на основе **меньшего по размеру** базового образа среды выполнения Docker для ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="b257e-168">copies the final build result into a Docker image based on the **smaller** ASP.NET Core Docker Runtime base image</span></span>

> [!Note]
> <span data-ttu-id="b257e-169">Образ сборки содержит необходимые средства для создания приложений, а образ среды выполнения — нет.</span><span class="sxs-lookup"><span data-stu-id="b257e-169">The build image contains required tools to build applications while the runtime image does not.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="b257e-170">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="b257e-170">Prerequisites</span></span>

<span data-ttu-id="b257e-171">Чтобы выполнить сборку и запуск, установите следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="b257e-171">To build and run, install the following items:</span></span>

#### <a name="net-core-20-sdk"></a><span data-ttu-id="b257e-172">Пакет SDK для .NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b257e-172">.NET Core 2.0 SDK</span></span>

* <span data-ttu-id="b257e-173">Установите [пакет SDK для .NET Core 2.0](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="b257e-173">Install [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span></span>

* <span data-ttu-id="b257e-174">Установите любой привычный для вас редактор кода, если еще не сделали этого.</span><span class="sxs-lookup"><span data-stu-id="b257e-174">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="b257e-175">Нужно ли устанавливать редактор кода?</span><span class="sxs-lookup"><span data-stu-id="b257e-175">Need to install a code editor?</span></span> <span data-ttu-id="b257e-176">Попробуйте использовать [Visual Studio](https://visualstudio.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="b257e-176">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="b257e-177">Установка клиента Docker</span><span class="sxs-lookup"><span data-stu-id="b257e-177">Installing Docker Client</span></span>

<span data-ttu-id="b257e-178">Установите клиент [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="b257e-178">Install [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="b257e-179">Клиент Docker можно установить в:</span><span class="sxs-lookup"><span data-stu-id="b257e-179">The Docker client can be installed in:</span></span>

* <span data-ttu-id="b257e-180">Дистрибутивах Linux</span><span class="sxs-lookup"><span data-stu-id="b257e-180">Linux distributions</span></span>

   * [<span data-ttu-id="b257e-181">CentOS</span><span class="sxs-lookup"><span data-stu-id="b257e-181">CentOS</span></span>](https://www.docker.com/docker-centos-distribution)

   * [<span data-ttu-id="b257e-182">Debian</span><span class="sxs-lookup"><span data-stu-id="b257e-182">Debian</span></span>](https://www.docker.com/docker-debian)

   * [<span data-ttu-id="b257e-183">Fedora</span><span class="sxs-lookup"><span data-stu-id="b257e-183">Fedora</span></span>](https://www.docker.com/docker-fedora)

   * [<span data-ttu-id="b257e-184">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="b257e-184">Ubuntu</span></span>](https://www.docker.com/docker-ubuntu)

* [<span data-ttu-id="b257e-185">macOS</span><span class="sxs-lookup"><span data-stu-id="b257e-185">macOS</span></span>](https://docs.docker.com/docker-for-mac/)

* <span data-ttu-id="b257e-186">[Windows](https://docs.docker.com/docker-for-windows/)</span><span class="sxs-lookup"><span data-stu-id="b257e-186">[Windows](https://docs.docker.com/docker-for-windows/).</span></span>

#### <a name="installing-git-for-sample-repository"></a><span data-ttu-id="b257e-187">Установка Git для образца репозитория</span><span class="sxs-lookup"><span data-stu-id="b257e-187">Installing Git for sample repository</span></span>

* <span data-ttu-id="b257e-188">Установите [git](https://git-scm.com/download), если хотите клонировать репозиторий.</span><span class="sxs-lookup"><span data-stu-id="b257e-188">Install [git](https://git-scm.com/download) if you wish to clone the repository.</span></span>

### <a name="getting-the-sample-application"></a><span data-ttu-id="b257e-189">Получение примера приложения</span><span class="sxs-lookup"><span data-stu-id="b257e-189">Getting the sample application</span></span>

<span data-ttu-id="b257e-190">Чтобы получить пример, проще всего клонировать [репозиторий с примерами](https://github.com/dotnet/dotnet-docker-samples) с git, руководствуясь следующими инструкциями:</span><span class="sxs-lookup"><span data-stu-id="b257e-190">The easiest way to get the sample is by cloning the [samples repository](https://github.com/dotnet/dotnet-docker-samples) with git, using the following instructions:</span></span> 

```console
git clone https://github.com/dotnet/dotnet-docker-samples/
```

<span data-ttu-id="b257e-191">Вы также можете скачать этот репозиторий (он довольно небольшой) в виде ZIP-файла из репозитория примеров Docker для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b257e-191">You can also download the repository (it is small) as a zip from the .NET Core Docker samples repository.</span></span>

### <a name="run-the-aspnet-app-locally"></a><span data-ttu-id="b257e-192">Запуск приложения ASP.NET локально</span><span class="sxs-lookup"><span data-stu-id="b257e-192">Run the ASP.NET app locally</span></span>

<span data-ttu-id="b257e-193">Чтобы получить ориентир, перед упаковкой приложения в контейнер запустите его локально.</span><span class="sxs-lookup"><span data-stu-id="b257e-193">For a reference point, before we containerize the application, first run the application locally.</span></span>

<span data-ttu-id="b257e-194">Вы можете создать и запустить приложение локально с помощью пакета SDK для .NET Core 2.0, используя следующие команды (в инструкциях предполагается, что вы находитесь в корне репозитория):</span><span class="sxs-lookup"><span data-stu-id="b257e-194">You can build and run the application locally with the .NET Core 2.0 SDK using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
dotnet run
```

<span data-ttu-id="b257e-195">После запуска приложения перейдите по адресу **http://localhost:5000** в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="b257e-195">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a><span data-ttu-id="b257e-196">Создание и запуск примера с Docker для контейнеров Linux</span><span class="sxs-lookup"><span data-stu-id="b257e-196">Build and run the sample with Docker for Linux containers</span></span>

<span data-ttu-id="b257e-197">Вы можете создать и запустить пример в Docker с помощью контейнеров Linux, используя следующие команды (в инструкциях предполагается, что вы находитесь в корне репозитория):</span><span class="sxs-lookup"><span data-stu-id="b257e-197">You can build and run the sample in Docker using Linux containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!Note] <span data-ttu-id="b257e-198">Аргумент `docker run` "-p" сопоставляет порт 5000 на локальном компьютере с портом 80 в контейнере (форма сопоставления порта — `host:container`).</span><span class="sxs-lookup"><span data-stu-id="b257e-198">The `docker run` '-p' argument maps port 5000 on your local machine to port 80 in the container (the port mapping form is `host:container`).</span></span> <span data-ttu-id="b257e-199">Дополнительные сведения см. в справочнике по команде [docker run](https://docs.docker.com/engine/reference/commandline/exec/) с описанием параметров командной строки.</span><span class="sxs-lookup"><span data-stu-id="b257e-199">For more information, see the [docker run](https://docs.docker.com/engine/reference/commandline/exec/) reference on command-line parameters.</span></span>

<span data-ttu-id="b257e-200">После запуска приложения перейдите по адресу **http://localhost:5000** в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="b257e-200">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a><span data-ttu-id="b257e-201">Создание и запуск примера с Docker для контейнеров Windows</span><span class="sxs-lookup"><span data-stu-id="b257e-201">Build and run the sample with Docker for Windows containers</span></span>

<span data-ttu-id="b257e-202">Вы можете создать и запустить пример в Docker с помощью контейнеров Windows, используя следующие команды (в инструкциях предполагается, что вы находитесь в корне репозитория):</span><span class="sxs-lookup"><span data-stu-id="b257e-202">You can build and run the sample in Docker using Windows containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> <span data-ttu-id="b257e-203">При использовании контейнеров Windows вам нужно перейти прямо по **IP-адресу контейнера** (а не по адресу http://localhost) в браузере.</span><span class="sxs-lookup"><span data-stu-id="b257e-203">You must navigate to the **container IP address** (as opposed to http://localhost) in your browser directly when using Windows containers.</span></span> <span data-ttu-id="b257e-204">Вы можете получить IP-адрес контейнера с помощью следующих действий:</span><span class="sxs-lookup"><span data-stu-id="b257e-204">You can get the IP address of your container with the following steps:</span></span>

* <span data-ttu-id="b257e-205">Откройте другую командную строку.</span><span class="sxs-lookup"><span data-stu-id="b257e-205">Open up another command prompt.</span></span>
* <span data-ttu-id="b257e-206">Запустите `docker ps` для просмотра запущенных контейнеров.</span><span class="sxs-lookup"><span data-stu-id="b257e-206">Run `docker ps` to see your running containers.</span></span> <span data-ttu-id="b257e-207">В списке должен присутствовать контейнер "aspnetcore_sample".</span><span class="sxs-lookup"><span data-stu-id="b257e-207">The "aspnetcore_sample" container should be there.</span></span>
* <span data-ttu-id="b257e-208">Запустите `docker exec aspnetcore_sample ipconfig`.</span><span class="sxs-lookup"><span data-stu-id="b257e-208">Run `docker exec aspnetcore_sample ipconfig`.</span></span>
* <span data-ttu-id="b257e-209">Скопируйте IP-адрес контейнера и вставьте в адресную строку браузера (например, 172.29.245.43).</span><span class="sxs-lookup"><span data-stu-id="b257e-209">Copy the container IP address and paste into your browser (for example, 172.29.245.43).</span></span>

> [!Note]
> <span data-ttu-id="b257e-210">Исполняемый файл Docker поддерживает идентификацию контейнеров по имени или хэшу.</span><span class="sxs-lookup"><span data-stu-id="b257e-210">Docker exec supports identifying containers with name or hash.</span></span> <span data-ttu-id="b257e-211">В нашем примере используется имя (aspnetcore_sample).</span><span class="sxs-lookup"><span data-stu-id="b257e-211">The name (aspnetcore_sample) is used in our example.</span></span>

<span data-ttu-id="b257e-212">См. следующий пример, показывающий, как получить IP-адрес запущенного контейнера Windows.</span><span class="sxs-lookup"><span data-stu-id="b257e-212">See the following example of how to get the IP address of a running Windows container.</span></span>

```console
docker exec aspnetcore_sample ipconfig

Windows IP Configuration

Ethernet adapter Ethernet:

   Connection-specific DNS Suffix  . : contoso.com
   Link-local IPv6 Address . . . . . : fe80::1967:6598:124:cfa3%4
   IPv4 Address. . . . . . . . . . . : 172.29.245.43
   Subnet Mask . . . . . . . . . . . : 255.255.240.0
   Default Gateway . . . . . . . . . : 172.29.240.1
```

> [!Note]
> <span data-ttu-id="b257e-213">Исполняемый файл Docker выполняет новую команду в запущенном контейнере.</span><span class="sxs-lookup"><span data-stu-id="b257e-213">Docker exec runs a new command in a running container.</span></span> <span data-ttu-id="b257e-214">Дополнительные сведения см. в справочнике по команде [docker exec](https://docs.docker.com/engine/reference/commandline/exec/) с описанием параметров командной строки.</span><span class="sxs-lookup"><span data-stu-id="b257e-214">For more information, see the [docker exec reference](https://docs.docker.com/engine/reference/commandline/exec/) on command-line parameters.</span></span>

<span data-ttu-id="b257e-215">Вы можете создать приложение, готовое к развертыванию в рабочей среде, локально с помощью команды [dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="b257e-215">You can produce an application that is ready to deploy to production locally using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span>

```console
dotnet publish -c release -o published
```

> [!Note]
> <span data-ttu-id="b257e-216">Аргумент выпуска -c приводит к сборке приложения в режиме выпуска (по умолчанию используется режим отладки).</span><span class="sxs-lookup"><span data-stu-id="b257e-216">The -c release argument builds the application in release mode (the default is debug mode).</span></span> <span data-ttu-id="b257e-217">Дополнительные сведения см. в справочнике по команде [dotnet run](../tools/dotnet-run.md) с описанием параметров командной строки.</span><span class="sxs-lookup"><span data-stu-id="b257e-217">For more information, see the [dotnet run reference](../tools/dotnet-run.md) on command-line parameters.</span></span>

<span data-ttu-id="b257e-218">Запустить приложение в **Windows** можно с помощью приведенной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="b257e-218">You can run the application on **Windows** using the following command.</span></span>

```console
dotnet published\aspnetapp.dll
```

<span data-ttu-id="b257e-219">Запустить приложение в **Linux** или **macOS** можно с помощью приведенной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="b257e-219">You can run the application on **Linux** or **macOS** using the following command.</span></span>

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="b257e-220">Образы Docker, используемые в этом примере</span><span class="sxs-lookup"><span data-stu-id="b257e-220">Docker Images used in this sample</span></span>

<span data-ttu-id="b257e-221">В этом примере используются следующие образы Docker:</span><span class="sxs-lookup"><span data-stu-id="b257e-221">The following Docker images are used in this sample</span></span>

* `microsoft/aspnetcore-build:2.0`
* `microsoft/aspnetcore:2.0`

<span data-ttu-id="b257e-222">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="b257e-222">Congratulations!</span></span> <span data-ttu-id="b257e-223">Вы только что:</span><span class="sxs-lookup"><span data-stu-id="b257e-223">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="b257e-224">узнали о создании образов Docker для Microsoft .NET Core;</span><span class="sxs-lookup"><span data-stu-id="b257e-224">Learned about Microsoft .NET Core Docker images</span></span>
> * <span data-ttu-id="b257e-225">получили пример приложения ASP.NET Core для добавления в Docker;</span><span class="sxs-lookup"><span data-stu-id="b257e-225">Got an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="b257e-226">запустили пример приложения ASP.NET локально;</span><span class="sxs-lookup"><span data-stu-id="b257e-226">Ran the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="b257e-227">создали и запустили пример с Docker для контейнеров Linux;</span><span class="sxs-lookup"><span data-stu-id="b257e-227">Built and ran the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="b257e-228">создали и запустили пример с Docker для контейнеров Windows.</span><span class="sxs-lookup"><span data-stu-id="b257e-228">Built and ran the sample with Docker for Windows containers</span></span>


<span data-ttu-id="b257e-229">**Следующие шаги**</span><span class="sxs-lookup"><span data-stu-id="b257e-229">**Next Steps**</span></span>

<span data-ttu-id="b257e-230">Ниже приведены некоторые действия, которые можно предпринять:</span><span class="sxs-lookup"><span data-stu-id="b257e-230">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="b257e-231">Работа со средствами Visual Studio для Docker</span><span class="sxs-lookup"><span data-stu-id="b257e-231">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* <span data-ttu-id="b257e-232">[Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/) (Развертывание образов Docker из реестра контейнеров Azure в службе "Экземпляры контейнеров Azure")</span><span class="sxs-lookup"><span data-stu-id="b257e-232">[Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)</span></span>
* [<span data-ttu-id="b257e-233">Отладка с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b257e-233">Debugging with Visual Studio Code</span></span>](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* <span data-ttu-id="b257e-234">[Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments) (Получение практических навыков по работе с Visual Studio для Mac, контейнерами и бессерверным кодом в облаке)</span><span class="sxs-lookup"><span data-stu-id="b257e-234">[Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)</span></span>
* <span data-ttu-id="b257e-235">[Getting started integrating with Docker containers in Visual Studio for Mac](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started) (Приступая к интеграции с контейнерами Docker в Visual Studio для Mac)</span><span class="sxs-lookup"><span data-stu-id="b257e-235">[Getting Started with Docker and Visual Studio for Mac Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)</span></span>

> [!Note]
> <span data-ttu-id="b257e-236">Если у вас нет подписки Azure, [зарегистрируйте сейчас](https://azure.microsoft.com/free/?b=16.48) бесплатную учетную запись на 30 дней и получите 200 долл. США на счет в Azure, чтобы опробовать любое сочетание служб Azure.</span><span class="sxs-lookup"><span data-stu-id="b257e-236">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>
