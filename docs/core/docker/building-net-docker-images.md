---
title: Создание образов Docker для .NET Core
description: Общие сведения об образах Docker и .NET Core
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: e48a263334ebb93a5d281032336aeb4073d8467c
ms.sourcegitcommit: d955cb4c681d68cf301d410925d83f25172ece86
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2018
ms.locfileid: "34827343"
---
# <a name="building-docker-images-for-net-core-applications"></a><span data-ttu-id="3ab7e-103">Создание образов Docker для приложений .NET Core</span><span class="sxs-lookup"><span data-stu-id="3ab7e-103">Building Docker Images for .NET Core Applications</span></span>

 <span data-ttu-id="3ab7e-104">Это руководство посвящено использованию .NET Core в Docker.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-104">In this tutorial, We focus on how to use .NET Core on Docker.</span></span> <span data-ttu-id="3ab7e-105">Сначала мы рассмотрим различные образы Docker, предоставляемые и поддерживаемые корпорацией Майкрософт, а также варианты их использования.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-105">First, we explore the different Docker images offered and maintained by Microsoft, and use cases.</span></span> <span data-ttu-id="3ab7e-106">Потом мы научимся создавать и добавлять в Docker приложение ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-106">We then learn how to build and dockerize an ASP.NET Core app.</span></span>

<span data-ttu-id="3ab7e-107">В ходе работы с этим руководством вы:</span><span class="sxs-lookup"><span data-stu-id="3ab7e-107">During the course of this tutorial, you learn:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="3ab7e-108">узнаете о создании образов Docker для Microsoft .NET Core;</span><span class="sxs-lookup"><span data-stu-id="3ab7e-108">Learn about Microsoft .NET Core Docker images</span></span> 
> * <span data-ttu-id="3ab7e-109">получите пример приложения ASP.NET Core для добавления в Docker;</span><span class="sxs-lookup"><span data-stu-id="3ab7e-109">Get an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="3ab7e-110">запустите пример приложения ASP.NET локально;</span><span class="sxs-lookup"><span data-stu-id="3ab7e-110">Run the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="3ab7e-111">создадите и запустите пример с Docker для контейнеров Linux;</span><span class="sxs-lookup"><span data-stu-id="3ab7e-111">Build and run the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="3ab7e-112">Создание и запуск примера с Docker для контейнеров Windows</span><span class="sxs-lookup"><span data-stu-id="3ab7e-112">Build and run the sample with Docker for Windows containers</span></span>

## <a name="docker-image-optimizations"></a><span data-ttu-id="3ab7e-113">Оптимизация образов Docker</span><span class="sxs-lookup"><span data-stu-id="3ab7e-113">Docker Image Optimizations</span></span>

<span data-ttu-id="3ab7e-114">При создании образов Docker для разработчиков мы сосредоточились на трех основных сценариях:</span><span class="sxs-lookup"><span data-stu-id="3ab7e-114">When building Docker images for developers, we focused on three main scenarios:</span></span>

* <span data-ttu-id="3ab7e-115">образы, используемые для разработки приложений .NET Core;</span><span class="sxs-lookup"><span data-stu-id="3ab7e-115">Images used to develop .NET Core apps</span></span>
* <span data-ttu-id="3ab7e-116">образы, используемые для сборки приложений .NET Core;</span><span class="sxs-lookup"><span data-stu-id="3ab7e-116">Images used to build .NET Core apps</span></span>
* <span data-ttu-id="3ab7e-117">образы, используемые для выполнения приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-117">Images used to run .NET Core apps</span></span>

<span data-ttu-id="3ab7e-118">Зачем нужны три образа</span><span class="sxs-lookup"><span data-stu-id="3ab7e-118">Why three images?</span></span>
<span data-ttu-id="3ab7e-119">При разработке, сборке и выполнении приложений в контейнерах приоритеты будут разными.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-119">When developing, building, and running containerized applications, we have different priorities.</span></span>

* <span data-ttu-id="3ab7e-120">**Разработка**. Основное внимание уделяется быстрой итерации по изменениям и возможности их отладки.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-120">**Development:**  The priority focuses on quickly iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="3ab7e-121">Размер образа не так важен, как возможность быстро вносить изменения в код и просматривать их.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-121">The size of the image isn't as important, rather can you make changes to your code and see them quickly?</span></span>

* <span data-ttu-id="3ab7e-122">**Сборка**. Этот образ содержит все необходимое для компиляции приложения, включая компилятор и другие зависимости для оптимизации двоичных файлов.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-122">**Build:** This image contains everything needed to compile your app, which includes the compiler and any other dependencies to optimize the binaries.</span></span>  <span data-ttu-id="3ab7e-123">Образ сборки нужен для создания ресурсов, помещаемых в рабочий образ.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-123">You use the build image to create the assets you place into a production image.</span></span> <span data-ttu-id="3ab7e-124">Этот образ будет применяться при непрерывной интеграции или в среде сборки.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-124">The build image would be used for continuous integration, or in a build environment.</span></span> <span data-ttu-id="3ab7e-125">Такой подход позволяет агенту сборки компилировать и собрать приложение (со всеми необходимыми зависимостями) в экземпляре образа сборки.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-125">This approach allows a build agent to compile and build the application (with all the required dependencies) in a build image instance.</span></span> <span data-ttu-id="3ab7e-126">Агенту сборки необходимо знать только, как запускать этот образ Docker.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-126">Your build agent only needs to know how to run this Docker image.</span></span>

* <span data-ttu-id="3ab7e-127">**Рабочая среда**. Как можно быстро развернуть и запустить образ.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-127">**Production:** How fast you can deploy and start your image?</span></span> <span data-ttu-id="3ab7e-128">Этот образ имеет небольшой размер, что позволяет оптимизировать передачу по сети из реестра Docker на узлы Docker.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-128">This image is small so network performance from your Docker Registry to your Docker hosts is optimized.</span></span> <span data-ttu-id="3ab7e-129">Содержимое готово к запуску, поэтому период времени от запуска Docker до обработки результатов минимален.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-129">The contents are ready to run enabling the fastest time from Docker run to processing results.</span></span> <span data-ttu-id="3ab7e-130">В модели Docker динамическая компиляция кода не требуется.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-130">Dynamic code compilation isn't needed in the Docker model.</span></span> <span data-ttu-id="3ab7e-131">Содержимое, помещаемое в этот образ, ограничено двоичными файлами и содержимым, которые необходимы для работы приложения.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-131">The content you place in this image would be limited to the binaries and content needed to run the application.</span></span>

    <span data-ttu-id="3ab7e-132">Например, выходные данные `dotnet publish` содержат:</span><span class="sxs-lookup"><span data-stu-id="3ab7e-132">For example, the `dotnet publish` output contains:</span></span>

    * <span data-ttu-id="3ab7e-133">скомпилированные двоичные файлы;</span><span class="sxs-lookup"><span data-stu-id="3ab7e-133">the compiled binaries</span></span>
    * <span data-ttu-id="3ab7e-134">файлы JS и CSS.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-134">.js and .css files</span></span>


<span data-ttu-id="3ab7e-135">Выходные данные команды `dotnet publish` нужно включить в рабочий образ, чтобы свести его размер к минимуму.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-135">The reason to include the `dotnet publish` command output in your production image is to keep its size to a minimum.</span></span>

<span data-ttu-id="3ab7e-136">Некоторые образы .NET Core совместно используют слои между разными тегами, поэтому скачивание последнего тега осуществляется довольно просто.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-136">Some .NET Core images share layers between different tags so downloading the latest tag is a relatively lightweight process.</span></span> <span data-ttu-id="3ab7e-137">Если на компьютере уже есть более старая версия, эта архитектура снижает необходимое дисковое пространство.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-137">If you already have an older version on your machine, this architecture decreases the needed disk space.</span></span>

<span data-ttu-id="3ab7e-138">Когда несколько приложений используют общие образы на одном компьютере, память используется этими общими образами совместно.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-138">When multiple applications use common images on the same machine, memory is shared between the common images.</span></span> <span data-ttu-id="3ab7e-139">Для совместного использования образы должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-139">The images must be the same to be shared.</span></span>

## <a name="docker-image-variations"></a><span data-ttu-id="3ab7e-140">Варианты образов Docker</span><span class="sxs-lookup"><span data-stu-id="3ab7e-140">Docker image variations</span></span>

<span data-ttu-id="3ab7e-141">Для достижения указанных выше целей мы предоставляет варианты образов в [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="3ab7e-141">To achieve the goals above, we provide image variants under [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

* <span data-ttu-id="3ab7e-142">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.1-sdk`) Этот образ содержит пакет SDK для .NET Core, который включает платформу .NET Core и программы командной строки (CLI).</span><span class="sxs-lookup"><span data-stu-id="3ab7e-142">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.1-sdk`) This image contains the .NET Core SDK, which includes the .NET Core and Command Line Tools (CLI).</span></span> <span data-ttu-id="3ab7e-143">Этот образ соответствует **сценарию развертывания**.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-143">This image maps to the **development scenario**.</span></span> <span data-ttu-id="3ab7e-144">Он используется для локальной разработки, отладки и модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-144">You use this image for local development, debugging, and unit testing.</span></span> <span data-ttu-id="3ab7e-145">Этот образ также можно использовать для сценариев **сборки**.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-145">This image can also be used for your **build** scenarios.</span></span> <span data-ttu-id="3ab7e-146">Использование `microsoft/dotnet:sdk` всегда предоставляет последнюю версию.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-146">Using `microsoft/dotnet:sdk` always gives you the latest version.</span></span>

> [!TIP]
> <span data-ttu-id="3ab7e-147">Если вы точно не знаете о своих потребностях, рекомендуется использовать образ `microsoft/dotnet:<version>-sdk`.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-147">If you are unsure about your needs, you want to use the `microsoft/dotnet:<version>-sdk` image.</span></span> <span data-ttu-id="3ab7e-148">Являясь образом "де-факто", он предназначен для использования в качестве одноразового контейнера (подключите исходный код и запустите контейнер для запуска приложения) и в качестве базового образа для создания других образов.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-148">As the "de facto" image, it's designed to be used as a throw away container (mount your source code and start the container to start your app), and as the base image to build other images from.</span></span>

* <span data-ttu-id="3ab7e-149">`microsoft/dotnet:<version>-runtime`. Этот образ содержит .NET Core (среду выполнения и библиотеки) и оптимизирован для запуска приложений .NET Core в **рабочей среде**.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-149">`microsoft/dotnet:<version>-runtime`: This image contains the .NET Core (runtime and libraries) and is optimized for running .NET Core apps in **production**.</span></span>

## <a name="alternative-images"></a><span data-ttu-id="3ab7e-150">Альтернативные образы</span><span class="sxs-lookup"><span data-stu-id="3ab7e-150">Alternative images</span></span>

<span data-ttu-id="3ab7e-151">Помимо образов, оптимизированных для разработки, сборки и рабочей среды, мы предоставляем дополнительные образы.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-151">In addition to the optimized scenarios of development, build and production, we provide additional images:</span></span>

* <span data-ttu-id="3ab7e-152">`microsoft/dotnet:<version>-runtime-deps`. Образ **runtime-deps** содержит операционную систему со всеми собственными зависимостями, требуемыми платформе .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-152">`microsoft/dotnet:<version>-runtime-deps`: The **runtime-deps** image contains the operating system with all of the native dependencies needed by .NET Core.</span></span> <span data-ttu-id="3ab7e-153">Этот образ предназначен для [автономных приложений](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="3ab7e-153">This image is for [self-contained applications](../deploying/index.md).</span></span>

<span data-ttu-id="3ab7e-154">Последние версии каждого варианта:</span><span class="sxs-lookup"><span data-stu-id="3ab7e-154">Latest versions of each variant:</span></span>

* <span data-ttu-id="3ab7e-155">`microsoft/dotnet` или `microsoft/dotnet:latest` (псевдоним для образа SDK)</span><span class="sxs-lookup"><span data-stu-id="3ab7e-155">`microsoft/dotnet` or `microsoft/dotnet:latest` (alias for the SDK image)</span></span>
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a><span data-ttu-id="3ab7e-156">Примеры для изучения</span><span class="sxs-lookup"><span data-stu-id="3ab7e-156">Samples to explore</span></span>

* <span data-ttu-id="3ab7e-157">[В этом примере Docker для ASP.NET Core](https://github.com/dotnet/dotnet-docker/tree/master/samples/aspnetapp) демонстрируется рекомендуемый шаблон создания образов Docker для приложений ASP.NET Core в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-157">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker/tree/master/samples/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="3ab7e-158">Этот пример поддерживается в контейнерах Linux и Windows.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-158">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="3ab7e-159">В этом примере Docker для .NET Core демонстрируется рекомендуемый шаблон [создания образов Docker для приложений .NET Core в рабочей среде](https://github.com/dotnet/dotnet-docker/tree/master/samples/dotnetapp).</span><span class="sxs-lookup"><span data-stu-id="3ab7e-159">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker/tree/master/samples/dotnetapp)</span></span>

## <a name="your-first-aspnet-core-docker-app"></a><span data-ttu-id="3ab7e-160">Ваше первое приложение Docker для ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3ab7e-160">Your first ASP.NET Core Docker app</span></span>

<span data-ttu-id="3ab7e-161">В этом руководстве мы будем использовать пример приложения Docker для ASP.NET Core в качестве приложения, которое хотим добавить в Docker.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-161">For this tutorial, lets use an ASP.NET Core Docker sample application for the app we want to dockerize.</span></span> <span data-ttu-id="3ab7e-162">Этот пример приложения Docker для ASP.NET Core демонстрирует рекомендуемый шаблон создания образов Docker для приложений ASP.NET Core в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-162">This ASP.NET Core Docker sample application demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="3ab7e-163">Этот пример поддерживается в контейнерах Linux и Windows.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-163">The sample works with both Linux and Windows containers.</span></span>

<span data-ttu-id="3ab7e-164">Пример Dockerfile создает образ Docker для приложения ASP.NET Core на основе базового образа Docker для среды выполнения ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-164">The sample Dockerfile creates an ASP.NET Core application Docker image based off of the ASP.NET Core Runtime Docker base image.</span></span>

<span data-ttu-id="3ab7e-165">Он использует [функцию многоэтапной сборки Docker](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) для:</span><span class="sxs-lookup"><span data-stu-id="3ab7e-165">It uses the [Docker multi-stage build feature](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) to:</span></span>

* <span data-ttu-id="3ab7e-166">сборки примера в контейнере на основе **большего по размеру** базового образа Docker сборки ASP.NET Core;</span><span class="sxs-lookup"><span data-stu-id="3ab7e-166">build the sample in a container based on the **larger** ASP.NET Core Build Docker base image</span></span> 
* <span data-ttu-id="3ab7e-167">копирование итогового результата сборки в образ Docker на основе **меньшего по размеру** базового образа среды выполнения Docker для ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-167">copies the final build result into a Docker image based on the **smaller** ASP.NET Core Docker Runtime base image</span></span>

> [!NOTE]
> <span data-ttu-id="3ab7e-168">Образ сборки содержит необходимые средства для создания приложений, а образ среды выполнения — нет.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-168">The build image contains required tools to build applications while the runtime image does not.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="3ab7e-169">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="3ab7e-169">Prerequisites</span></span>

<span data-ttu-id="3ab7e-170">Чтобы выполнить сборку и запуск, установите следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="3ab7e-170">To build and run, install the following items:</span></span>

#### <a name="net-core-21-sdk"></a><span data-ttu-id="3ab7e-171">Пакет SDK для NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="3ab7e-171">.NET Core 2.1 SDK</span></span>

* <span data-ttu-id="3ab7e-172">Установите [пакет SDK для .NET Core 2.1](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="3ab7e-172">Install [.NET Core SDK 2.1](https://www.microsoft.com/net/core).</span></span>

* <span data-ttu-id="3ab7e-173">Установите любой привычный для вас редактор кода, если еще не сделали этого.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-173">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="3ab7e-174">Нужно ли устанавливать редактор кода?</span><span class="sxs-lookup"><span data-stu-id="3ab7e-174">Need to install a code editor?</span></span> <span data-ttu-id="3ab7e-175">Попробуйте использовать [Visual Studio](https://visualstudio.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="3ab7e-175">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="3ab7e-176">Установка клиента Docker</span><span class="sxs-lookup"><span data-stu-id="3ab7e-176">Installing Docker Client</span></span>

<span data-ttu-id="3ab7e-177">Установите клиент [Docker 18.03](https://docs.docker.com/release-notes/docker-ce/) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-177">Install [Docker 18.03](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="3ab7e-178">Клиент Docker можно установить в:</span><span class="sxs-lookup"><span data-stu-id="3ab7e-178">The Docker client can be installed in:</span></span>

* <span data-ttu-id="3ab7e-179">Дистрибутивах Linux</span><span class="sxs-lookup"><span data-stu-id="3ab7e-179">Linux distributions</span></span>

   * [<span data-ttu-id="3ab7e-180">CentOS</span><span class="sxs-lookup"><span data-stu-id="3ab7e-180">CentOS</span></span>](https://www.docker.com/docker-centos-distribution)

   * [<span data-ttu-id="3ab7e-181">Debian</span><span class="sxs-lookup"><span data-stu-id="3ab7e-181">Debian</span></span>](https://www.docker.com/docker-debian)

   * [<span data-ttu-id="3ab7e-182">Fedora</span><span class="sxs-lookup"><span data-stu-id="3ab7e-182">Fedora</span></span>](https://www.docker.com/docker-fedora)

   * [<span data-ttu-id="3ab7e-183">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="3ab7e-183">Ubuntu</span></span>](https://www.docker.com/docker-ubuntu)

* [<span data-ttu-id="3ab7e-184">macOS</span><span class="sxs-lookup"><span data-stu-id="3ab7e-184">macOS</span></span>](https://docs.docker.com/docker-for-mac/)

* <span data-ttu-id="3ab7e-185">[Windows](https://docs.docker.com/docker-for-windows/)</span><span class="sxs-lookup"><span data-stu-id="3ab7e-185">[Windows](https://docs.docker.com/docker-for-windows/).</span></span>

#### <a name="installing-git-for-sample-repository"></a><span data-ttu-id="3ab7e-186">Установка Git для образца репозитория</span><span class="sxs-lookup"><span data-stu-id="3ab7e-186">Installing Git for sample repository</span></span>

* <span data-ttu-id="3ab7e-187">Установите [git](https://git-scm.com/download), если хотите клонировать репозиторий.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-187">Install [git](https://git-scm.com/download) if you wish to clone the repository.</span></span>

### <a name="getting-the-sample-application"></a><span data-ttu-id="3ab7e-188">Получение примера приложения</span><span class="sxs-lookup"><span data-stu-id="3ab7e-188">Getting the sample application</span></span>

<span data-ttu-id="3ab7e-189">Чтобы получить пример самым простым способоv, клонируйте с сайта Git [репозиторий Docker для .NET Core](https://github.com/dotnet/dotnet-docker), руководствуясь следующими инструкциями:</span><span class="sxs-lookup"><span data-stu-id="3ab7e-189">The easiest way to get the sample is by cloning the [.NET Core Docker repository](https://github.com/dotnet/dotnet-docker) with git, using the following instructions:</span></span> 

```console
git clone https://github.com/dotnet/dotnet-docker
```

<span data-ttu-id="3ab7e-190">Вы также можете скачать этот репозиторий (он довольно небольшой) из репозитория Docker для .NET Core в виде ZIP-файла.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-190">You can also download the repository (it is small) as a zip from the .NET Core Docker repository.</span></span>

### <a name="run-the-aspnet-app-locally"></a><span data-ttu-id="3ab7e-191">Запуск приложения ASP.NET локально</span><span class="sxs-lookup"><span data-stu-id="3ab7e-191">Run the ASP.NET app locally</span></span>

<span data-ttu-id="3ab7e-192">Чтобы получить ориентир, перед упаковкой приложения в контейнер запустите его локально.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-192">For a reference point, before we containerize the application, first run the application locally.</span></span>

<span data-ttu-id="3ab7e-193">Вы можете создать и запустить приложение локально с помощью пакета SDK для .NET Core 2.1, используя следующие команды (в инструкциях предполагается, что вы находитесь в корне репозитория):</span><span class="sxs-lookup"><span data-stu-id="3ab7e-193">You can build and run the application locally with the .NET Core 2.1 SDK using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located
cd aspnetapp // project scope

dotnet run
```

<span data-ttu-id="3ab7e-194">После запуска приложения перейдите по адресу **http://localhost:5000** в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-194">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a><span data-ttu-id="3ab7e-195">Создание и запуск примера с Docker для контейнеров Linux</span><span class="sxs-lookup"><span data-stu-id="3ab7e-195">Build and run the sample with Docker for Linux containers</span></span>

<span data-ttu-id="3ab7e-196">Вы можете создать и запустить пример в Docker с помощью контейнеров Linux, используя следующие команды (в инструкциях предполагается, что вы находитесь в корне репозитория):</span><span class="sxs-lookup"><span data-stu-id="3ab7e-196">You can build and run the sample in Docker using Linux containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located

docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!NOTE]
> <span data-ttu-id="3ab7e-197">Аргумент `docker run` "-p" сопоставляет порт 5000 на локальном компьютере с портом 80 в контейнере (форма сопоставления порта — `host:container`).</span><span class="sxs-lookup"><span data-stu-id="3ab7e-197">The `docker run` '-p' argument maps port 5000 on your local machine to port 80 in the container (the port mapping form is `host:container`).</span></span> <span data-ttu-id="3ab7e-198">Дополнительные сведения см. в справочнике по команде [docker run](https://docs.docker.com/engine/reference/commandline/exec/) с описанием параметров командной строки.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-198">For more information, see the [docker run](https://docs.docker.com/engine/reference/commandline/exec/) reference on command-line parameters.</span></span>

<span data-ttu-id="3ab7e-199">После запуска приложения перейдите по адресу **http://localhost:5000** в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-199">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a><span data-ttu-id="3ab7e-200">Создание и запуск примера с Docker для контейнеров Windows</span><span class="sxs-lookup"><span data-stu-id="3ab7e-200">Build and run the sample with Docker for Windows containers</span></span>

<span data-ttu-id="3ab7e-201">Вы можете создать и запустить пример в Docker с помощью контейнеров Windows, используя следующие команды (в инструкциях предполагается, что вы находитесь в корне репозитория):</span><span class="sxs-lookup"><span data-stu-id="3ab7e-201">You can build and run the sample in Docker using Windows containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located

docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> <span data-ttu-id="3ab7e-202">При использовании контейнеров Windows вам нужно перейти прямо по **IP-адресу контейнера** (а не по адресу http://localhost) в браузере.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-202">You must navigate to the **container IP address** (as opposed to http://localhost) in your browser directly when using Windows containers.</span></span> <span data-ttu-id="3ab7e-203">Вы можете получить IP-адрес контейнера с помощью следующих действий:</span><span class="sxs-lookup"><span data-stu-id="3ab7e-203">You can get the IP address of your container with the following steps:</span></span>

* <span data-ttu-id="3ab7e-204">Откройте другую командную строку.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-204">Open up another command prompt.</span></span>
* <span data-ttu-id="3ab7e-205">Запустите `docker ps` для просмотра запущенных контейнеров.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-205">Run `docker ps` to see your running containers.</span></span> <span data-ttu-id="3ab7e-206">В списке должен присутствовать контейнер "aspnetcore_sample".</span><span class="sxs-lookup"><span data-stu-id="3ab7e-206">The "aspnetcore_sample" container should be there.</span></span>
* <span data-ttu-id="3ab7e-207">Запустите `docker exec aspnetcore_sample ipconfig`.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-207">Run `docker exec aspnetcore_sample ipconfig`.</span></span>
* <span data-ttu-id="3ab7e-208">Скопируйте IP-адрес контейнера и вставьте в адресную строку браузера (например, 172.29.245.43).</span><span class="sxs-lookup"><span data-stu-id="3ab7e-208">Copy the container IP address and paste into your browser (for example, 172.29.245.43).</span></span>

> [!NOTE]
> <span data-ttu-id="3ab7e-209">Исполняемый файл Docker поддерживает идентификацию контейнеров по имени или хэшу.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-209">Docker exec supports identifying containers with name or hash.</span></span> <span data-ttu-id="3ab7e-210">В нашем примере используется имя (aspnetcore_sample).</span><span class="sxs-lookup"><span data-stu-id="3ab7e-210">The name (aspnetcore_sample) is used in our example.</span></span>

<span data-ttu-id="3ab7e-211">См. следующий пример, показывающий, как получить IP-адрес запущенного контейнера Windows.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-211">See the following example of how to get the IP address of a running Windows container.</span></span>

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

> [!NOTE]
> <span data-ttu-id="3ab7e-212">Исполняемый файл Docker выполняет новую команду в запущенном контейнере.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-212">Docker exec runs a new command in a running container.</span></span> <span data-ttu-id="3ab7e-213">Дополнительные сведения см. в справочнике по команде [docker exec](https://docs.docker.com/engine/reference/commandline/exec/) с описанием параметров командной строки.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-213">For more information, see the [docker exec reference](https://docs.docker.com/engine/reference/commandline/exec/) on command-line parameters.</span></span>

<span data-ttu-id="3ab7e-214">Вы можете создать приложение, готовое к развертыванию в рабочей среде, локально с помощью команды [dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="3ab7e-214">You can produce an application that is ready to deploy to production locally using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span>

```console
dotnet publish -c Release -o published
```

> [!NOTE]
> <span data-ttu-id="3ab7e-215">Аргумент выпуска "-c" приводит к сборке приложения в режиме выпуска (по умолчанию используется режим отладки).</span><span class="sxs-lookup"><span data-stu-id="3ab7e-215">The -c Release argument builds the application in release mode (the default is debug mode).</span></span> <span data-ttu-id="3ab7e-216">Дополнительные сведения см. в справочнике по команде [dotnet run](../tools/dotnet-run.md) с описанием параметров командной строки.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-216">For more information, see the [dotnet run reference](../tools/dotnet-run.md) on command-line parameters.</span></span>

<span data-ttu-id="3ab7e-217">Запустить приложение в **Windows** можно с помощью приведенной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-217">You can run the application on **Windows** using the following command.</span></span>

```console
dotnet published\aspnetapp.dll
```

<span data-ttu-id="3ab7e-218">Запустить приложение в **Linux** или **macOS** можно с помощью приведенной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-218">You can run the application on **Linux** or **macOS** using the following command.</span></span>

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="3ab7e-219">Образы Docker, используемые в этом примере</span><span class="sxs-lookup"><span data-stu-id="3ab7e-219">Docker Images used in this sample</span></span>

<span data-ttu-id="3ab7e-220">В этом примере файла Docker используются следующие образы Docker:</span><span class="sxs-lookup"><span data-stu-id="3ab7e-220">The following Docker images are used in this sample's dockerfile.</span></span>

* `microsoft/dotnet:2.1-sdk`
* `microsoft/dotnet:2.1-aspnetcore-runtime`

<span data-ttu-id="3ab7e-221">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="3ab7e-221">Congratulations!</span></span> <span data-ttu-id="3ab7e-222">Вы только что:</span><span class="sxs-lookup"><span data-stu-id="3ab7e-222">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="3ab7e-223">узнали о создании образов Docker для Microsoft .NET Core;</span><span class="sxs-lookup"><span data-stu-id="3ab7e-223">Learned about Microsoft .NET Core Docker images</span></span>
> * <span data-ttu-id="3ab7e-224">получили пример приложения ASP.NET Core для добавления в Docker;</span><span class="sxs-lookup"><span data-stu-id="3ab7e-224">Got an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="3ab7e-225">запустили пример приложения ASP.NET локально;</span><span class="sxs-lookup"><span data-stu-id="3ab7e-225">Ran the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="3ab7e-226">создали и запустили пример с Docker для контейнеров Linux;</span><span class="sxs-lookup"><span data-stu-id="3ab7e-226">Built and ran the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="3ab7e-227">создали и запустили пример с Docker для контейнеров Windows.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-227">Built and ran the sample with Docker for Windows containers</span></span>


<span data-ttu-id="3ab7e-228">**Следующие шаги**</span><span class="sxs-lookup"><span data-stu-id="3ab7e-228">**Next Steps**</span></span>

<span data-ttu-id="3ab7e-229">Ниже приведены некоторые действия, которые можно предпринять:</span><span class="sxs-lookup"><span data-stu-id="3ab7e-229">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="3ab7e-230">Работа со средствами Visual Studio для Docker</span><span class="sxs-lookup"><span data-stu-id="3ab7e-230">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* <span data-ttu-id="3ab7e-231">[Развертывание образов Docker из реестра контейнеров Azure в службе "Экземпляры контейнеров Azure](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/) </span><span class="sxs-lookup"><span data-stu-id="3ab7e-231">[Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)</span></span>
* [<span data-ttu-id="3ab7e-232">Отладка с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3ab7e-232">Debugging with Visual Studio Code</span></span>](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [<span data-ttu-id="3ab7e-233">Получение практических навыков по работе с Visual Studio для Mac, контейнерами и бессерверным кодом в облаке</span><span class="sxs-lookup"><span data-stu-id="3ab7e-233">Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud</span></span>](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* <span data-ttu-id="3ab7e-234">[Getting started integrating with Docker containers in Visual Studio for Mac](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started) (Приступая к интеграции с контейнерами Docker в Visual Studio для Mac)</span><span class="sxs-lookup"><span data-stu-id="3ab7e-234">[Getting Started with Docker and Visual Studio for Mac Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)</span></span>

> [!NOTE]
> <span data-ttu-id="3ab7e-235">Если у вас нет подписки Azure, [зарегистрируйте сейчас](https://azure.microsoft.com/free/?b=16.48) бесплатную учетную запись на 30 дней и получите 200 долл. США на счет в Azure, чтобы опробовать любое сочетание служб Azure.</span><span class="sxs-lookup"><span data-stu-id="3ab7e-235">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>
