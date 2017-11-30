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
ms.openlocfilehash: 3ec2d5a58b46e332de41b618f1c3fac663b29bee
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2017
---
# <a name="building-docker-images-for-net-core-applications"></a><span data-ttu-id="aab68-104">Создание образов Docker для приложений .NET Core</span><span class="sxs-lookup"><span data-stu-id="aab68-104">Building Docker Images for .NET Core Applications</span></span>

 <span data-ttu-id="aab68-105">В этом учебнике рассматривается использование .NET Core на Docker.</span><span class="sxs-lookup"><span data-stu-id="aab68-105">In this tutorial, We focus on how to use .NET Core on Docker.</span></span> <span data-ttu-id="aab68-106">Во-первых мы исследуем различные изображения Docker предлагаемых и поддерживаются корпорацией Майкрософт и вариантов использования.</span><span class="sxs-lookup"><span data-stu-id="aab68-106">First, we explore the different Docker images offered and maintained by Microsoft, and use cases.</span></span> <span data-ttu-id="aab68-107">Затем рассказано способ построения и dockerize приложения ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="aab68-107">We then learn how to build and dockerize an ASP.NET Core app.</span></span>

<span data-ttu-id="aab68-108">В ходе этого учебника вы узнаете:</span><span class="sxs-lookup"><span data-stu-id="aab68-108">During the course of this tutorial, you learn:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="aab68-109">Дополнительные сведения о Microsoft .NET Core Docker images</span><span class="sxs-lookup"><span data-stu-id="aab68-109">Learn about Microsoft .NET Core Docker images</span></span> 
> * <span data-ttu-id="aab68-110">Получить ASP.NET Core примера приложения для Dockerize</span><span class="sxs-lookup"><span data-stu-id="aab68-110">Get an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="aab68-111">Пример приложения ASP.NET запускаются</span><span class="sxs-lookup"><span data-stu-id="aab68-111">Run the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="aab68-112">Построение и запуск образца с помощью Docker для контейнеров Linux</span><span class="sxs-lookup"><span data-stu-id="aab68-112">Build and run the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="aab68-113">Построение и запуск образца с помощью контейнеров Docker для Windows</span><span class="sxs-lookup"><span data-stu-id="aab68-113">Build and run the sample with Docker for Windows containers</span></span>

## <a name="docker-image-optimizations"></a><span data-ttu-id="aab68-114">Оптимизация образов Docker</span><span class="sxs-lookup"><span data-stu-id="aab68-114">Docker Image Optimizations</span></span>

<span data-ttu-id="aab68-115">При создании образов Docker для разработчиков мы сосредоточились на трех основных сценариях:</span><span class="sxs-lookup"><span data-stu-id="aab68-115">When building Docker images for developers, we focused on three main scenarios:</span></span>

* <span data-ttu-id="aab68-116">образы, используемые для разработки приложений .NET Core;</span><span class="sxs-lookup"><span data-stu-id="aab68-116">Images used to develop .NET Core apps</span></span>
* <span data-ttu-id="aab68-117">образы, используемые для сборки приложений .NET Core;</span><span class="sxs-lookup"><span data-stu-id="aab68-117">Images used to build .NET Core apps</span></span>
* <span data-ttu-id="aab68-118">образы, используемые для выполнения приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="aab68-118">Images used to run .NET Core apps</span></span>

<span data-ttu-id="aab68-119">Зачем нужны три образа</span><span class="sxs-lookup"><span data-stu-id="aab68-119">Why three images?</span></span>
<span data-ttu-id="aab68-120">При разработке, построении и запуске приложений в контейнерах, у нас есть различные приоритеты.</span><span class="sxs-lookup"><span data-stu-id="aab68-120">When developing, building, and running containerized applications, we have different priorities.</span></span>

* <span data-ttu-id="aab68-121">**Разработка:** приоритет уделяется быстро перечисления изменений, а также возможность отладки изменения.</span><span class="sxs-lookup"><span data-stu-id="aab68-121">**Development:**  The priority focuses on quickly iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="aab68-122">Размер изображения не столь важно, вместо этого можно внести изменения в код и быстро просматривать их?</span><span class="sxs-lookup"><span data-stu-id="aab68-122">The size of the image isn't as important, rather can you make changes to your code and see them quickly?</span></span>

* <span data-ttu-id="aab68-123">**Сборка:** этот образ содержит все необходимое для компиляции приложения, включая компилятор и другие зависимости, для оптимизации двоичных файлов.</span><span class="sxs-lookup"><span data-stu-id="aab68-123">**Build:** This image contains everything needed to compile your app, which includes the compiler and any other dependencies to optimize the binaries.</span></span>  <span data-ttu-id="aab68-124">Вы используете образ сборки для создания активов, размещаемых в рабочей среде образ.</span><span class="sxs-lookup"><span data-stu-id="aab68-124">You use the build image to create the assets you place into a production image.</span></span> <span data-ttu-id="aab68-125">Образ сборки будет использоваться для непрерывной интеграции или в среде построения.</span><span class="sxs-lookup"><span data-stu-id="aab68-125">The build image would be used for continuous integration, or in a build environment.</span></span> <span data-ttu-id="aab68-126">Такой подход позволяет агент сборки для компиляции и построения приложения (с необходимые зависимости) в экземпляре сборки образа.</span><span class="sxs-lookup"><span data-stu-id="aab68-126">This approach allows a build agent to compile and build the application (with all the required dependencies) in a build image instance.</span></span> <span data-ttu-id="aab68-127">Агенту сборки необходимо знать только, как запускать этот образ Docker.</span><span class="sxs-lookup"><span data-stu-id="aab68-127">Your build agent only needs to know how to run this Docker image.</span></span>

* <span data-ttu-id="aab68-128">**Порождение:** как быстро развернуть и запустить образ?</span><span class="sxs-lookup"><span data-stu-id="aab68-128">**Production:** How fast you can deploy and start your image?</span></span> <span data-ttu-id="aab68-129">Этот образ мал, поэтому производительность сети из реестра Docker на узлах Docker оптимизирован.</span><span class="sxs-lookup"><span data-stu-id="aab68-129">This image is small so network performance from your Docker Registry to your Docker hosts is optimized.</span></span> <span data-ttu-id="aab68-130">Содержимое готово к запуску, поэтому период времени от запуска Docker до обработки результатов минимален.</span><span class="sxs-lookup"><span data-stu-id="aab68-130">The contents are ready to run enabling the fastest time from Docker run to processing results.</span></span> <span data-ttu-id="aab68-131">В модели Docker динамической компиляции кода не требуется.</span><span class="sxs-lookup"><span data-stu-id="aab68-131">Dynamic code compilation isn't needed in the Docker model.</span></span> <span data-ttu-id="aab68-132">Содержимое, помещаемое в этот образ, ограничено двоичными файлами и содержимым, которые необходимы для работы приложения.</span><span class="sxs-lookup"><span data-stu-id="aab68-132">The content you place in this image would be limited to the binaries and content needed to run the application.</span></span>

    <span data-ttu-id="aab68-133">Например `dotnet publish` содержит выходные данные:</span><span class="sxs-lookup"><span data-stu-id="aab68-133">For example, the `dotnet publish` output contains:</span></span>

    * <span data-ttu-id="aab68-134">скомпилированные двоичные файлы</span><span class="sxs-lookup"><span data-stu-id="aab68-134">the compiled binaries</span></span>
    * <span data-ttu-id="aab68-135">.js и CSS-файлы</span><span class="sxs-lookup"><span data-stu-id="aab68-135">.js and .css files</span></span>


<span data-ttu-id="aab68-136">Причина для включения `dotnet publish` будут сохранены выходные данные команды в рабочей среде образ его "размер до минимума.</span><span class="sxs-lookup"><span data-stu-id="aab68-136">The reason to include the `dotnet publish` command output in your production image is to keep its' size to a minimum.</span></span>

<span data-ttu-id="aab68-137">Некоторые образы .NET Core Общие слои между различия в тегах, загружает последние тег является довольно простой.</span><span class="sxs-lookup"><span data-stu-id="aab68-137">Some .NET Core images share layers between different tags so downloading the latest tag is a relatively lightweight process.</span></span> <span data-ttu-id="aab68-138">Если уже имеется более старой версии на компьютере, эта архитектура снижает необходимое дисковое пространство.</span><span class="sxs-lookup"><span data-stu-id="aab68-138">If you already have an older version on your machine, this architecture decreases the needed disk space.</span></span>

<span data-ttu-id="aab68-139">Если несколько приложений используют общие образы на том же компьютере, память распределяется между общие образы.</span><span class="sxs-lookup"><span data-stu-id="aab68-139">When multiple applications use common images on the same machine, memory is shared between the common images.</span></span> <span data-ttu-id="aab68-140">Изображения должны совпадать для совместного использования.</span><span class="sxs-lookup"><span data-stu-id="aab68-140">The images must be the same to be shared.</span></span>

## <a name="docker-image-variations"></a><span data-ttu-id="aab68-141">Варианты образов Docker</span><span class="sxs-lookup"><span data-stu-id="aab68-141">Docker image variations</span></span>

<span data-ttu-id="aab68-142">Для достижения целей выше, мы предоставляем варианты образа в разделе [ `microsoft/dotnet` ](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="aab68-142">To achieve the goals above, we provide image variants under [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

* <span data-ttu-id="aab68-143">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) Этот образ содержит Core SDK .NET, включая .NET Core и средства командной строки (CLI).</span><span class="sxs-lookup"><span data-stu-id="aab68-143">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) This image contains the .NET Core SDK, which includes the .NET Core and Command Line Tools (CLI).</span></span> <span data-ttu-id="aab68-144">Этот образ соответствует **сценарию развертывания**.</span><span class="sxs-lookup"><span data-stu-id="aab68-144">This image maps to the **development scenario**.</span></span> <span data-ttu-id="aab68-145">Использование этого образа для локальной разработки, отладки и тестирования модулей.</span><span class="sxs-lookup"><span data-stu-id="aab68-145">You use this image for local development, debugging, and unit testing.</span></span> <span data-ttu-id="aab68-146">Этот образ также можно использовать для сценариев **сборки**.</span><span class="sxs-lookup"><span data-stu-id="aab68-146">This image can also be used for your **build** scenarios.</span></span> <span data-ttu-id="aab68-147">С помощью `microsoft/dotnet:sdk` всегда позволяет получить последнюю версию.</span><span class="sxs-lookup"><span data-stu-id="aab68-147">Using `microsoft/dotnet:sdk` always gives you the latest version.</span></span>

> [!TIP]
> <span data-ttu-id="aab68-148">Если вы не знаете о вашим потребностям, вы хотите использовать `microsoft/dotnet:<version>-sdk` изображения.</span><span class="sxs-lookup"><span data-stu-id="aab68-148">If you are unsure about your needs, you want to use the `microsoft/dotnet:<version>-sdk` image.</span></span> <span data-ttu-id="aab68-149">Как «фактически» изображение, она предназначена для использования в качестве исключения размещения контейнера (подключить исходный код и запустите контейнер для запуска приложения) и в качестве базового образа для создания других образов из.</span><span class="sxs-lookup"><span data-stu-id="aab68-149">As the "de facto" image, it's designed to be used as a throw away container (mount your source code and start the container to start your app), and as the base image to build other images from.</span></span>

* <span data-ttu-id="aab68-150">`microsoft/dotnet:<version>-runtime`: Этот образ содержит основные функции .NET (среды выполнения и библиотек) и оптимизирован для запущенных приложений .NET Core **рабочей**.</span><span class="sxs-lookup"><span data-stu-id="aab68-150">`microsoft/dotnet:<version>-runtime`: This image contains the .NET Core (runtime and libraries) and is optimized for running .NET Core apps in **production**.</span></span>

## <a name="alternative-images"></a><span data-ttu-id="aab68-151">Альтернативные образы</span><span class="sxs-lookup"><span data-stu-id="aab68-151">Alternative images</span></span>

<span data-ttu-id="aab68-152">Помимо образов, оптимизированных для разработки, сборки и рабочей среды, мы предоставляем дополнительные образы.</span><span class="sxs-lookup"><span data-stu-id="aab68-152">In addition to the optimized scenarios of development, build and production, we provide additional images:</span></span>

* <span data-ttu-id="aab68-153">`microsoft/dotnet:<version>-runtime-deps`: **Deps среды выполнения** образ содержит операционную систему с все собственного зависимости, необходимые для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="aab68-153">`microsoft/dotnet:<version>-runtime-deps`: The **runtime-deps** image contains the operating system with all of the native dependencies needed by .NET Core.</span></span> <span data-ttu-id="aab68-154">Этот образ является для [автономные приложения](https://docs.microsoft.com/dotnet/core/deploying/index).</span><span class="sxs-lookup"><span data-stu-id="aab68-154">This image is for [self-contained applications](https://docs.microsoft.com/dotnet/core/deploying/index).</span></span>

<span data-ttu-id="aab68-155">Последние версии каждого варианта:</span><span class="sxs-lookup"><span data-stu-id="aab68-155">Latest versions of each variant:</span></span>

* <span data-ttu-id="aab68-156">`microsoft/dotnet`или `microsoft/dotnet:latest` (псевдоним для образа SDK)</span><span class="sxs-lookup"><span data-stu-id="aab68-156">`microsoft/dotnet` or `microsoft/dotnet:latest` (alias for the SDK image)</span></span>
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a><span data-ttu-id="aab68-157">Образцы для исследования</span><span class="sxs-lookup"><span data-stu-id="aab68-157">Samples to explore</span></span>

* <span data-ttu-id="aab68-158">[В этом примере ASP.NET Core Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) показан шаблон лучший подход для создания образов Docker для ASP.NET Core приложений для рабочей среды.</span><span class="sxs-lookup"><span data-stu-id="aab68-158">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="aab68-159">Образец работает с контейнерами Windows и Linux.</span><span class="sxs-lookup"><span data-stu-id="aab68-159">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="aab68-160">В этом примере .NET Core Docker демонстрируется лучше всего рекомендаций для [построения образов Docker для приложений .NET Core для рабочей среды.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span><span class="sxs-lookup"><span data-stu-id="aab68-160">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span></span>

## <a name="your-first-aspnet-core-docker-app"></a><span data-ttu-id="aab68-161">Своего первого приложения ASP.NET Core Docker</span><span class="sxs-lookup"><span data-stu-id="aab68-161">Your first ASP.NET Core Docker app</span></span>

<span data-ttu-id="aab68-162">В этом учебнике позволяет использовать образец приложения ASP.NET Core Docker для приложения, которое мы хотим dockerize.</span><span class="sxs-lookup"><span data-stu-id="aab68-162">For this tutorial, lets use an ASP.NET Core Docker sample application for the app we want to dockerize.</span></span> <span data-ttu-id="aab68-163">В этом образце приложения ASP.NET Core Docker показан шаблон лучший подход для создания образов Docker для ASP.NET Core приложений для рабочей среды.</span><span class="sxs-lookup"><span data-stu-id="aab68-163">This ASP.NET Core Docker sample application demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="aab68-164">Образец работает с контейнерами Windows и Linux.</span><span class="sxs-lookup"><span data-stu-id="aab68-164">The sample works with both Linux and Windows containers.</span></span>

<span data-ttu-id="aab68-165">В образце Dockerfile создается образ Docker приложения ASP.NET Core на основе этих базового образа Docker среды выполнения ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="aab68-165">The sample Dockerfile creates an ASP.NET Core application Docker image based off of the ASP.NET Core Runtime Docker base image.</span></span>

<span data-ttu-id="aab68-166">Она использует [Docker многоэтапным построения функции](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) для:</span><span class="sxs-lookup"><span data-stu-id="aab68-166">It uses the [Docker multi-stage build feature](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) to:</span></span>

* <span data-ttu-id="aab68-167">Построение образца в контейнере на основе **больше** базового образа Docker сборки ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="aab68-167">build the sample in a container based on the **larger** ASP.NET Core Build Docker base image</span></span> 
* <span data-ttu-id="aab68-168">копирует результат последнего построения в Docker изображение на основе **меньше** базового образа среды выполнения ASP.NET Core Docker</span><span class="sxs-lookup"><span data-stu-id="aab68-168">copies the final build result into a Docker image based on the **smaller** ASP.NET Core Docker Runtime base image</span></span>

> [!Note]
> <span data-ttu-id="aab68-169">Образ сборки содержит необходимые средства для создания приложений, а образа среды выполнения — нет.</span><span class="sxs-lookup"><span data-stu-id="aab68-169">The build image contains required tools to build applications while the runtime image does not.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="aab68-170">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="aab68-170">Prerequisites</span></span>

<span data-ttu-id="aab68-171">Построение и запуск, установите следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="aab68-171">To build and run, install the following items:</span></span>

#### <a name="net-core-20-sdk"></a><span data-ttu-id="aab68-172">.NET core 2.0 SDK</span><span class="sxs-lookup"><span data-stu-id="aab68-172">.NET Core 2.0 SDK</span></span>

* <span data-ttu-id="aab68-173">Установка [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="aab68-173">Install [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span></span>

* <span data-ttu-id="aab68-174">Если это еще не сделано, установите редактора избранные кода.</span><span class="sxs-lookup"><span data-stu-id="aab68-174">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="aab68-175">Необходимо установить редактор кода?</span><span class="sxs-lookup"><span data-stu-id="aab68-175">Need to install a code editor?</span></span> <span data-ttu-id="aab68-176">Повторите [Visual Studio](https://visualstudio.com/downloads)!</span><span class="sxs-lookup"><span data-stu-id="aab68-176">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="aab68-177">Установка клиента Docker</span><span class="sxs-lookup"><span data-stu-id="aab68-177">Installing Docker Client</span></span>

<span data-ttu-id="aab68-178">Установка [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) или более поздней версии клиента Docker.</span><span class="sxs-lookup"><span data-stu-id="aab68-178">Install [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="aab68-179">В можно установить клиента Docker.</span><span class="sxs-lookup"><span data-stu-id="aab68-179">The Docker client can be installed in:</span></span>

* <span data-ttu-id="aab68-180">Дистрибутивы Linux</span><span class="sxs-lookup"><span data-stu-id="aab68-180">Linux distributions</span></span>

   * [<span data-ttu-id="aab68-181">CentOS</span><span class="sxs-lookup"><span data-stu-id="aab68-181">CentOS</span></span>](https://www.docker.com/docker-centos-distribution)

   * [<span data-ttu-id="aab68-182">Debian</span><span class="sxs-lookup"><span data-stu-id="aab68-182">Debian</span></span>](https://www.docker.com/docker-debian)

   * [<span data-ttu-id="aab68-183">Fedora</span><span class="sxs-lookup"><span data-stu-id="aab68-183">Fedora</span></span>](https://www.docker.com/docker-fedora)

   * [<span data-ttu-id="aab68-184">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="aab68-184">Ubuntu</span></span>](https://www.docker.com/docker-ubuntu)

* [<span data-ttu-id="aab68-185">macOS</span><span class="sxs-lookup"><span data-stu-id="aab68-185">macOS</span></span>](https://docs.docker.com/docker-for-mac/)

* <span data-ttu-id="aab68-186">[Windows](https://docs.docker.com/docker-for-windows/).</span><span class="sxs-lookup"><span data-stu-id="aab68-186">[Windows](https://docs.docker.com/docker-for-windows/).</span></span>

#### <a name="installing-git-for-sample-repository"></a><span data-ttu-id="aab68-187">Установка Git для образца репозитория</span><span class="sxs-lookup"><span data-stu-id="aab68-187">Installing Git for sample repository</span></span>

* <span data-ttu-id="aab68-188">Установка [git](https://git-scm.com/download) чтобы клонировать репозиторий.</span><span class="sxs-lookup"><span data-stu-id="aab68-188">Install [git](https://git-scm.com/download) if you wish to clone the repository.</span></span>

### <a name="getting-the-sample-application"></a><span data-ttu-id="aab68-189">Получение примера приложения</span><span class="sxs-lookup"><span data-stu-id="aab68-189">Getting the sample application</span></span>

<span data-ttu-id="aab68-190">Самый простой способ получить образец — путем клонирования [репозитории samples](https://github.com/dotnet/dotnet-docker-samples) с git, выполнив следующие инструкции:</span><span class="sxs-lookup"><span data-stu-id="aab68-190">The easiest way to get the sample is by cloning the [samples repository](https://github.com/dotnet/dotnet-docker-samples) with git, using the following instructions:</span></span> 

```console
git clone https://github.com/dotnet/dotnet-docker-samples/
```

<span data-ttu-id="aab68-191">Можно также загрузить хранилище (небольшой) как ZIP-файл, из репозитория примеров .NET Core Docker.</span><span class="sxs-lookup"><span data-stu-id="aab68-191">You can also download the repository (it is small) as a zip from the .NET Core Docker samples repository.</span></span>

### <a name="run-the-aspnet-app-locally"></a><span data-ttu-id="aab68-192">Приложение ASP.NET запускается локально</span><span class="sxs-lookup"><span data-stu-id="aab68-192">Run the ASP.NET app locally</span></span>

<span data-ttu-id="aab68-193">Чтобы получить ориентир, перед упаковкой приложения в контейнер запустите его локально.</span><span class="sxs-lookup"><span data-stu-id="aab68-193">For a reference point, before we containerize the application, first run the application locally.</span></span>

<span data-ttu-id="aab68-194">Можно построить и запустите приложение локально с 2.0 SDK .NET Core с помощью следующих команд (инструкции предполагают корень репозитория):</span><span class="sxs-lookup"><span data-stu-id="aab68-194">You can build and run the application locally with the .NET Core 2.0 SDK using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
dotnet run
```

<span data-ttu-id="aab68-195">После запуска приложения, посетите **http://localhost: 5000** в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="aab68-195">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a><span data-ttu-id="aab68-196">Построение и запуск образца с помощью Docker для контейнеров Linux</span><span class="sxs-lookup"><span data-stu-id="aab68-196">Build and run the sample with Docker for Linux containers</span></span>

<span data-ttu-id="aab68-197">Можно построить и запустите образец в Docker с контейнерами Linux с помощью следующих команд (инструкции предполагают корень репозитория):</span><span class="sxs-lookup"><span data-stu-id="aab68-197">You can build and run the sample in Docker using Linux containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!Note] <span data-ttu-id="aab68-198">`docker run` "-P" аргумент сопоставления порта 5000 на локальном компьютере для порта 80 в контейнере (форма сопоставления порта `host:container`).</span><span class="sxs-lookup"><span data-stu-id="aab68-198">The `docker run` '-p' argument maps port 5000 on your local machine to port 80 in the container (the port mapping form is `host:container`).</span></span> <span data-ttu-id="aab68-199">Дополнительные сведения см. в разделе [запуска docker](https://docs.docker.com/engine/reference/commandline/exec/) ссылки на параметры командной строки.</span><span class="sxs-lookup"><span data-stu-id="aab68-199">For more information, see the [docker run](https://docs.docker.com/engine/reference/commandline/exec/) reference on command-line parameters.</span></span>

<span data-ttu-id="aab68-200">После запуска приложения, посетите **http://localhost: 5000** в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="aab68-200">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a><span data-ttu-id="aab68-201">Построение и запуск образца с помощью контейнеров Docker для Windows</span><span class="sxs-lookup"><span data-stu-id="aab68-201">Build and run the sample with Docker for Windows containers</span></span>

<span data-ttu-id="aab68-202">Можно построить и запустите образец в Docker с помощью контейнеров Windows, с помощью следующих команд (инструкции предполагают корень репозитория):</span><span class="sxs-lookup"><span data-stu-id="aab68-202">You can build and run the sample in Docker using Windows containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> <span data-ttu-id="aab68-203">Необходимо перейти **IP-адрес контейнера** (в отличие от «http://localhost») в браузере напрямую при использовании контейнеров Windows.</span><span class="sxs-lookup"><span data-stu-id="aab68-203">You must navigate to the **container IP address** (as opposed to http://localhost) in your browser directly when using Windows containers.</span></span> <span data-ttu-id="aab68-204">Можно получить IP-адрес контейнера с помощью следующих действий:</span><span class="sxs-lookup"><span data-stu-id="aab68-204">You can get the IP address of your container with the following steps:</span></span>

* <span data-ttu-id="aab68-205">Откройте другую командную строку.</span><span class="sxs-lookup"><span data-stu-id="aab68-205">Open up another command prompt.</span></span>
* <span data-ttu-id="aab68-206">Запустите `docker ps` для просмотра вашего запущенные контейнеры.</span><span class="sxs-lookup"><span data-stu-id="aab68-206">Run `docker ps` to see your running containers.</span></span> <span data-ttu-id="aab68-207">Контейнер «aspnetcore_sample» должно быть существует.</span><span class="sxs-lookup"><span data-stu-id="aab68-207">The "aspnetcore_sample" container should be there.</span></span>
* <span data-ttu-id="aab68-208">Запустите `docker exec aspnetcore_sample ipconfig`.</span><span class="sxs-lookup"><span data-stu-id="aab68-208">Run `docker exec aspnetcore_sample ipconfig`.</span></span>
* <span data-ttu-id="aab68-209">IP-адрес контейнера, скопируйте и вставьте в адресную строку браузера (например, 172.29.245.43).</span><span class="sxs-lookup"><span data-stu-id="aab68-209">Copy the container IP address and paste into your browser (for example, 172.29.245.43).</span></span>

> [!Note]
> <span data-ttu-id="aab68-210">Docker exec поддерживает идентифицирующие контейнеры с именем или hash.</span><span class="sxs-lookup"><span data-stu-id="aab68-210">Docker exec supports identifying containers with name or hash.</span></span> <span data-ttu-id="aab68-211">В нашем примере используется имя (aspnetcore_sample).</span><span class="sxs-lookup"><span data-stu-id="aab68-211">The name (aspnetcore_sample) is used in our example.</span></span>

<span data-ttu-id="aab68-212">См. следующий пример того, как получить IP-адрес из запущенного контейнера Windows.</span><span class="sxs-lookup"><span data-stu-id="aab68-212">See the following example of how to get the IP address of a running Windows container.</span></span>

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
> <span data-ttu-id="aab68-213">Docker exec запускает новую команду в запущенного контейнера.</span><span class="sxs-lookup"><span data-stu-id="aab68-213">Docker exec runs a new command in a running container.</span></span> <span data-ttu-id="aab68-214">Дополнительные сведения см. в разделе [docker exec ссылка](https://docs.docker.com/engine/reference/commandline/exec/) о параметрах командной строки.</span><span class="sxs-lookup"><span data-stu-id="aab68-214">For more information, see the [docker exec reference](https://docs.docker.com/engine/reference/commandline/exec/) on command-line parameters.</span></span>

<span data-ttu-id="aab68-215">Вы можете создавать приложения, которое будет готово к развертыванию в рабочей среде локально с помощью [публикации dotnet](../tools/dotnet-publish.md) команды.</span><span class="sxs-lookup"><span data-stu-id="aab68-215">You can produce an application that is ready to deploy to production locally using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span>

```console
dotnet publish -c release -o published
```

> [!Note]
> <span data-ttu-id="aab68-216">Аргумент - c выпуска построения приложения в режиме выпуска (по умолчанию используется режим отладки).</span><span class="sxs-lookup"><span data-stu-id="aab68-216">The -c release argument builds the application in release mode (the default is debug mode).</span></span> <span data-ttu-id="aab68-217">Дополнительные сведения см. в разделе [dotnet запуска ссылку](../tools/dotnet-run.md) о параметрах командной строки.</span><span class="sxs-lookup"><span data-stu-id="aab68-217">For more information, see the [dotnet run reference](../tools/dotnet-run.md) on command-line parameters.</span></span>

<span data-ttu-id="aab68-218">Приложение можно запустить **Windows** с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="aab68-218">You can run the application on **Windows** using the following command.</span></span>

```console
dotnet published\aspnetapp.dll
```

<span data-ttu-id="aab68-219">Приложение можно запустить **Linux** или **macOS** с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="aab68-219">You can run the application on **Linux** or **macOS** using the following command.</span></span>

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="aab68-220">Docker изображений, используемых в этом образце</span><span class="sxs-lookup"><span data-stu-id="aab68-220">Docker Images used in this sample</span></span>

<span data-ttu-id="aab68-221">В этом образце используются следующие образы Docker</span><span class="sxs-lookup"><span data-stu-id="aab68-221">The following Docker images are used in this sample</span></span>

* `microsoft/aspnetcore-build:2.0`
* `microsoft/aspnetcore:2.0`

<span data-ttu-id="aab68-222">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="aab68-222">Congratulations!</span></span> <span data-ttu-id="aab68-223">у вас есть только:</span><span class="sxs-lookup"><span data-stu-id="aab68-223">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="aab68-224">Узнали о Microsoft .NET Core Docker images</span><span class="sxs-lookup"><span data-stu-id="aab68-224">Learned about Microsoft .NET Core Docker images</span></span>
> * <span data-ttu-id="aab68-225">Получить ASP.NET Core примера приложения для Dockerize</span><span class="sxs-lookup"><span data-stu-id="aab68-225">Got an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="aab68-226">Запускался локально в пример приложения ASP.NET</span><span class="sxs-lookup"><span data-stu-id="aab68-226">Ran the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="aab68-227">Построения и запуска образца с помощью Docker для контейнеров Linux</span><span class="sxs-lookup"><span data-stu-id="aab68-227">Built and ran the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="aab68-228">Построения и запуска образца с помощью контейнеров Docker для Windows</span><span class="sxs-lookup"><span data-stu-id="aab68-228">Built and ran the sample with Docker for Windows containers</span></span>


<span data-ttu-id="aab68-229">**Дальнейшие действия**</span><span class="sxs-lookup"><span data-stu-id="aab68-229">**Next Steps**</span></span>

<span data-ttu-id="aab68-230">Ниже приведены действия, которые можно предпринять.</span><span class="sxs-lookup"><span data-stu-id="aab68-230">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="aab68-231">Работа со средствами Visual Studio Docker</span><span class="sxs-lookup"><span data-stu-id="aab68-231">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="aab68-232">Развертывание образов Docker из реестра контейнер Azure с экземплярами Azure контейнера</span><span class="sxs-lookup"><span data-stu-id="aab68-232">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [<span data-ttu-id="aab68-233">Отладка с кодом Visual Studio</span><span class="sxs-lookup"><span data-stu-id="aab68-233">Debugging with Visual Studio Code</span></span>](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [<span data-ttu-id="aab68-234">Получение руки по с помощью Visual Studio для Mac, контейнеры и без сервера кода в облаке</span><span class="sxs-lookup"><span data-stu-id="aab68-234">Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud</span></span>](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [<span data-ttu-id="aab68-235">Начало работы с Docker и Visual Studio для Mac лаборатории</span><span class="sxs-lookup"><span data-stu-id="aab68-235">Getting Started with Docker and Visual Studio for Mac Lab</span></span>](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

> [!Note]
> <span data-ttu-id="aab68-236">Если у вас подписка на Azure, [Зарегистрируйтесь](https://azure.microsoft.com/free/?b=16.48) для бесплатной 30-дневной учетной записи и get 200 в кредиты Azure, чтобы испытать любое сочетание служб Azure.</span><span class="sxs-lookup"><span data-stu-id="aab68-236">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>
