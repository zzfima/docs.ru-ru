---
title: "Создание образов Docker для .NET Core"
description: "Общие сведения об образах Docker и .NET Core"
keywords: .NET, .NET Core, Docker
author: spboyer
ms.author: shboyer
ms.date: 08/29/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
ms.translationtype: HT
ms.sourcegitcommit: 9dc52f3a8c74c1aa575a83cb3bbd579b93fae9ae
ms.openlocfilehash: 0e679ffc22f52de5e2ce8194942efbb2f5299ee4
ms.contentlocale: ru-ru
ms.lasthandoff: 09/06/2017

---

#<a name="building-docker-images-for-net-core-applications"></a><span data-ttu-id="46ffa-104">Создание образов Docker для приложений .NET Core</span><span class="sxs-lookup"><span data-stu-id="46ffa-104">Building Docker Images for .NET Core Applications</span></span>

 
> [!IMPORTANT]
> <span data-ttu-id="46ffa-105">Сейчас мы обновляем .NET Core до версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="46ffa-105">We are in the process of updating for .NET Core 2.0.</span></span> <span data-ttu-id="46ffa-106">Поэтому приведенные ниже инструкции устарели.</span><span class="sxs-lookup"><span data-stu-id="46ffa-106">The instructions below are out of date.</span></span> <span data-ttu-id="46ffa-107">Приносим свои искренние извинения за неудобства.</span><span class="sxs-lookup"><span data-stu-id="46ffa-107">We sincerely apologize for any inconvenience!</span></span>

<span data-ttu-id="46ffa-108">Чтобы понять, как можно использовать .NET Core и Docker вместе, сначала нужно ознакомиться с различными образами Docker и подходящими ситуациями для их применения.</span><span class="sxs-lookup"><span data-stu-id="46ffa-108">In order to get an understanding of how to use .NET Core and Docker together, we must first get to know the different Docker images that are offered and when is the right use case for them.</span></span> <span data-ttu-id="46ffa-109">В этой статье мы по порядку разберем предлагаемые варианты, создадим веб-интерфейс API ASP.NET Core, используем средства Yeoman Docker для создания отлаживаемого контейнера, а также посмотрим, как Visual Studio Code может помочь нам в решении этих задач.</span><span class="sxs-lookup"><span data-stu-id="46ffa-109">Here we will walk through the variations offered, build an ASP.NET Core Web API, use the Yeoman Docker tools to create a debuggable container as well as peek at how Visual Studio Code can assist in the process.</span></span> 

## <a name="docker-image-optimizations"></a><span data-ttu-id="46ffa-110">Оптимизация образов Docker</span><span class="sxs-lookup"><span data-stu-id="46ffa-110">Docker Image Optimizations</span></span>

<span data-ttu-id="46ffa-111">При создании образов Docker для разработчиков мы сосредоточились на трех основных сценариях:</span><span class="sxs-lookup"><span data-stu-id="46ffa-111">When building Docker images for developers, we focused on three main scenarios:</span></span>

- <span data-ttu-id="46ffa-112">образы, используемые для разработки приложений .NET Core;</span><span class="sxs-lookup"><span data-stu-id="46ffa-112">Images used to develop .NET Core apps</span></span>
- <span data-ttu-id="46ffa-113">образы, используемые для сборки приложений .NET Core;</span><span class="sxs-lookup"><span data-stu-id="46ffa-113">Images used to build .NET Core apps</span></span>
- <span data-ttu-id="46ffa-114">образы, используемые для выполнения приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="46ffa-114">Images used to run .NET Core apps</span></span>

<span data-ttu-id="46ffa-115">Зачем нужны три образа</span><span class="sxs-lookup"><span data-stu-id="46ffa-115">Why three images?</span></span>
<span data-ttu-id="46ffa-116">При разработке, сборке и выполнении приложений в контейнерах приоритеты будут разными.</span><span class="sxs-lookup"><span data-stu-id="46ffa-116">When developing, building and running containerized applications, we have different priorities.</span></span>
- <span data-ttu-id="46ffa-117">**Разработка**. Как быстро может осуществляться итерация и отладка изменений.</span><span class="sxs-lookup"><span data-stu-id="46ffa-117">**Development:**  How fast can you iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="46ffa-118">Размер образа не так важен, как возможность быстро вносить изменения в код и просматривать их.</span><span class="sxs-lookup"><span data-stu-id="46ffa-118">The size of the image isn't as important, rather can you make changes to your code and see them quickly.</span></span> <span data-ttu-id="46ffa-119">Некоторые из наших средств, например [yo docker](https://aka.ms/yodocker) для использования в Visual Studio Code, применяют этот образ во время разработки.</span><span class="sxs-lookup"><span data-stu-id="46ffa-119">Some of our tools, like [yo docker](https://aka.ms/yodocker) for use in Visual Studio Code use this image during development time.</span></span> 
- <span data-ttu-id="46ffa-120">**Сборка**. Что нужно для компиляции приложения.</span><span class="sxs-lookup"><span data-stu-id="46ffa-120">**Build:** What's needed to compile your app.</span></span> <span data-ttu-id="46ffa-121">Сюда относятся компилятор и другие зависимости для оптимизации двоичных файлов.</span><span class="sxs-lookup"><span data-stu-id="46ffa-121">This includes the compiler and any other dependencies to optimize the binaries.</span></span> <span data-ttu-id="46ffa-122">Это не тот образ, который вы развертываете, а образ, который вы используете для сборки содержимого, помещаемого в рабочий образ.</span><span class="sxs-lookup"><span data-stu-id="46ffa-122">This image isn't the image you deploy, rather it's an image you use to build the content you place into a production image.</span></span> <span data-ttu-id="46ffa-123">Этот образ будет применяться при непрерывной интеграции или в среде сборки.</span><span class="sxs-lookup"><span data-stu-id="46ffa-123">This image would be used in your continuous integration, or build environment.</span></span> <span data-ttu-id="46ffa-124">Например, вместо установки всех зависимостей непосредственно в агенте сборки этот агент создаст экземпляр образа сборки, чтобы скомпилировать приложение со всеми зависимостями, которые необходимы для сборки приложения, содержащегося в образе.</span><span class="sxs-lookup"><span data-stu-id="46ffa-124">For instance, rather than installing all the dependencies directly on a build agent, the build agent would instance a build image to compile the application with all the dependencies required to build the app contained within the image.</span></span> <span data-ttu-id="46ffa-125">Агенту сборки необходимо знать только, как запускать этот образ Docker.</span><span class="sxs-lookup"><span data-stu-id="46ffa-125">Your build agent only needs to know how to run this Docker image.</span></span> 
- <span data-ttu-id="46ffa-126">**Рабочая среда**. Как быстро можно развернуть и запустить образ.</span><span class="sxs-lookup"><span data-stu-id="46ffa-126">**Production:** How fast you can deploy and start your image.</span></span> <span data-ttu-id="46ffa-127">Этот образ имеет небольшой размер, поэтому может быстро передаваться по сети из реестра Docker на узлы Docker.</span><span class="sxs-lookup"><span data-stu-id="46ffa-127">This image is small so it can quickly travel across the network from your Docker Registry to your Docker hosts.</span></span> <span data-ttu-id="46ffa-128">Содержимое готово к запуску, поэтому период времени от запуска Docker до обработки результатов минимален.</span><span class="sxs-lookup"><span data-stu-id="46ffa-128">The contents are ready to run enabling the fastest time from Docker run to processing results.</span></span> <span data-ttu-id="46ffa-129">В неизменяемой модели Docker нет потребности в динамической компиляции кода.</span><span class="sxs-lookup"><span data-stu-id="46ffa-129">In the immutable Docker model, there's no need for dynamic compilation of code.</span></span> <span data-ttu-id="46ffa-130">Содержимое, помещаемое в этот образ, ограничено двоичными файлами и содержимым, которые необходимы для работы приложения.</span><span class="sxs-lookup"><span data-stu-id="46ffa-130">The content you place in this image would be limited to the binaries and content needed to run the application.</span></span> <span data-ttu-id="46ffa-131">Например, это могут быть выходные данные, опубликованные с помощью команды `dotnet publish` и содержащие скомпилированные двоичные файлы, изображения, файлы JS и CSS.</span><span class="sxs-lookup"><span data-stu-id="46ffa-131">For example, the published output using `dotnet publish` which contains the compiled binaries, images, .js and .css files.</span></span> <span data-ttu-id="46ffa-132">Со временем появятся образы, которые содержат пакеты, предварительно скомпилированные JIT-компилятором.</span><span class="sxs-lookup"><span data-stu-id="46ffa-132">Over time, you'll see images that contain pre-jitted packages.</span></span>  

<span data-ttu-id="46ffa-133">Хотя существует несколько версий образа .NET Core, они все имеют один или несколько общих уровней.</span><span class="sxs-lookup"><span data-stu-id="46ffa-133">Though there are multiple versions of the .NET Core image, they all share one or more layers.</span></span> <span data-ttu-id="46ffa-134">Объем дискового пространства для хранения или размер разностных данных, которые нужно извлечь из реестра, гораздо меньше общего размера, так как все образы имеют общий базовый и, возможно, другие общие уровни.</span><span class="sxs-lookup"><span data-stu-id="46ffa-134">The amount of disk space needed to store or the delta to pull from your registry is much smaller than the whole because all of the images share the same base layer and potentially others.</span></span>  

## <a name="docker-image-variations"></a><span data-ttu-id="46ffa-135">Варианты образов Docker</span><span class="sxs-lookup"><span data-stu-id="46ffa-135">Docker image variations</span></span>

<span data-ttu-id="46ffa-136">Для достижения указанных выше целей мы предоставляет варианты образов в [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="46ffa-136">To achieve the goals above, we provide image variants under [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

- <span data-ttu-id="46ffa-137">`microsoft/dotnet:<version>-sdk`, то есть **microsoft/dotnet:1.0.0-preview2-sdk** — этот образ содержит пакет SDK для .NET Core, который включает платформу .NET Core и программы командной строки (CLI).</span><span class="sxs-lookup"><span data-stu-id="46ffa-137">`microsoft/dotnet:<version>-sdk` : that is **microsoft/dotnet:1.0.0-preview2-sdk**, this image contains the .NET Core SDK which includes the .NET Core and Command Line Tools (CLI).</span></span> <span data-ttu-id="46ffa-138">Этот образ соответствует **сценарию развертывания**.</span><span class="sxs-lookup"><span data-stu-id="46ffa-138">This image maps to the **development scenario**.</span></span> <span data-ttu-id="46ffa-139">Он используется для локальной разработки, отладки и модульного тестирования,</span><span class="sxs-lookup"><span data-stu-id="46ffa-139">You would use this image for local development, debugging and unit testing.</span></span> <span data-ttu-id="46ffa-140">например для всех задач разработки, выполняемых до возврата кода.</span><span class="sxs-lookup"><span data-stu-id="46ffa-140">For example, all the development you do, before you check in your code.</span></span> <span data-ttu-id="46ffa-141">Этот образ также можно использовать для сценариев **сборки**.</span><span class="sxs-lookup"><span data-stu-id="46ffa-141">This image can also be used for your **build** scenarios.</span></span>

- <span data-ttu-id="46ffa-142">`microsoft/dotnet:<version>-core`, то есть **microsoft/dotnet:1.0.0-core** — образ, который выполняет [переносимые приложения .NET Core](../deploying/index.md) и оптимизирован для выполнения приложений в **рабочей среде**.</span><span class="sxs-lookup"><span data-stu-id="46ffa-142">`microsoft/dotnet:<version>-core` : that is **microsoft/dotnet:1.0.0-core**, image which runs [portable .NET Core applications](../deploying/index.md) and it is optimized for running your application in **production**.</span></span> <span data-ttu-id="46ffa-143">Он не содержит пакета SDK и предназначен для получения оптимизированных выходных данных команды `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="46ffa-143">It does not contain the SDK, and is meant to take the optimized output of `dotnet publish`.</span></span> <span data-ttu-id="46ffa-144">Переносимая среда выполнения хорошо подходит для сценариев с контейнерами Docker, так как использование нескольких контейнеров позволяет реализовать преимущество общих уровней образов.</span><span class="sxs-lookup"><span data-stu-id="46ffa-144">The portable runtime is well suited for Docker container scenarios as running multiple containers benefit from shared image layers.</span></span>  

## <a name="alternative-images"></a><span data-ttu-id="46ffa-145">Альтернативные образы</span><span class="sxs-lookup"><span data-stu-id="46ffa-145">Alternative images</span></span>

<span data-ttu-id="46ffa-146">Помимо образов, оптимизированных для разработки, сборки и рабочей среды, мы предоставляем дополнительные образы.</span><span class="sxs-lookup"><span data-stu-id="46ffa-146">In addition to the optimized scenarios of development, build and production, we provide additional images:</span></span>

- <span data-ttu-id="46ffa-147">`microsoft/dotnet:<version>-onbuild`, то есть **microsoft/dotnet:1.0.0-preview2-onbuild**, содержит триггеры [ONBUILD](https://docs.docker.com/engine/reference/builder/#/onbuild).</span><span class="sxs-lookup"><span data-stu-id="46ffa-147">`microsoft/dotnet:<version>-onbuild` : that is **microsoft/dotnet:1.0.0-preview2-onbuild**, contains [ONBUILD](https://docs.docker.com/engine/reference/builder/#/onbuild) triggers.</span></span> <span data-ttu-id="46ffa-148">Сборка копирует ([COPY](https://docs.docker.com/engine/reference/builder/#/copy)) приложение, выполняет команду `dotnet restore` и создает инструкцию [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) `dotnet run` для запуска приложения при запуске образа Docker.</span><span class="sxs-lookup"><span data-stu-id="46ffa-148">The build will [COPY](https://docs.docker.com/engine/reference/builder/#/copy) your application, run `dotnet restore` and create an [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) `dotnet run` instruction to run the application when the Docker image is run.</span></span> <span data-ttu-id="46ffa-149">Хотя этот образ не оптимизирован для рабочей среды, кому-то он может быть полезен для упрощения копирования исходного кода в образ и его выполнения.</span><span class="sxs-lookup"><span data-stu-id="46ffa-149">While not an optimized image for production, some may find it useful to simply copy their source code into an image and run it.</span></span> 

- <span data-ttu-id="46ffa-150">`microsoft/dotnet:<version>-core-deps`, то есть **microsoft/dotnet:1.0.0-core-deps** — используйте этот образ для выполнения автономных приложений.</span><span class="sxs-lookup"><span data-stu-id="46ffa-150">`microsoft/dotnet:<version>-core-deps` : that is **microsoft/dotnet:1.0.0-core-deps**, if you wish to run self-contained applications use this image.</span></span> <span data-ttu-id="46ffa-151">Он содержит операционную систему со всеми собственными зависимостями, требуемыми платформе .NET Core.</span><span class="sxs-lookup"><span data-stu-id="46ffa-151">It contains the operating system with all of the native dependencies needed by .NET Core.</span></span> <span data-ttu-id="46ffa-152">Кроме того, этот образ можно использовать в качестве базового для собственных сборок CoreFX или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="46ffa-152">This image can also be used as a base image for your own custom CoreFX or CoreCLR builds.</span></span> <span data-ttu-id="46ffa-153">Вариант **onbuild** оптимизирован для простого добавления кода в образ и его выполнения, а образ оптимизирован так, что вы получаете только те зависимости операционной системы, которые необходимы для выполнения приложений .NET Core, в состав которых входит упакованная среда выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="46ffa-153">While the **onbuild** variant is optimized to simply place your code in an image and run it, this image is optimized to have only the operating system dependencies required to run .NET Core apps that have the .NET runtime packaged with the application.</span></span> <span data-ttu-id="46ffa-154">Этот образ, как правило, не оптимизирован для запуска нескольких контейнеров .NET Core на одном узле, так как каждый образ содержит среду выполнения .NET Core в приложении и вы не получите преимущество от наличия общих уровней образов.</span><span class="sxs-lookup"><span data-stu-id="46ffa-154">This image isn't generally optimized for running multiple .NET Core containers on the same host, as each image carries the .NET Core runtime within the application, and you will not benefit from image layering.</span></span>   

<span data-ttu-id="46ffa-155">Последние версии каждого варианта:</span><span class="sxs-lookup"><span data-stu-id="46ffa-155">Latest versions of each variant:</span></span>

- <span data-ttu-id="46ffa-156">`microsoft/dotnet` или `microsoft/dotnet:latest` (включает пакет SDK)</span><span class="sxs-lookup"><span data-stu-id="46ffa-156">`microsoft/dotnet` or `microsoft/dotnet:latest` (includes SDK)</span></span>
- `microsoft/dotnet:onbuild`
- `microsoft/dotnet:core`
- `microsoft/dotnet:core-deps`

<span data-ttu-id="46ffa-157">Ниже приведен список образов после выполнения команды `docker pull <imagename>` на компьютере разработки и их размеры.</span><span class="sxs-lookup"><span data-stu-id="46ffa-157">Here is a list of the images after a `docker pull <imagename>` on a development machine to show the various sizes.</span></span> <span data-ttu-id="46ffa-158">Обратите внимание на то, что вариант для разработки и сборки (`microsoft/dotnet:1.0.0-preview2-sdk`) больше, так как он содержит пакет SDK для разработки и сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="46ffa-158">Notice, the development/build variant, `microsoft/dotnet:1.0.0-preview2-sdk` is larger as it contains the SDK to develop and build your application.</span></span> <span data-ttu-id="46ffa-159">Вариант для рабочей среды (`microsoft/dotnet:core`) меньше, так как он содержит только среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="46ffa-159">The production variant, `microsoft/dotnet:core` is smaller, as it only contains the .NET Core runtime.</span></span> <span data-ttu-id="46ffa-160">Минимальный образ `core-deps`, пригодный для использования в Linux, существенно меньше по размеру, но с ним вашему приложению нужно иметь собственную копию среды выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="46ffa-160">The minimal image capable of being used on Linux, `core-deps`, is quite smaller, however your application will need to copy a private copy of the .NET runtime with it.</span></span> <span data-ttu-id="46ffa-161">Так как контейнеры уже обеспечивают изоляцию, это преимущество теряется при выполнении нескольких контейнеров на основе .NET.</span><span class="sxs-lookup"><span data-stu-id="46ffa-161">Since containers are already private isolation barriers, you will lose that optimization when running multiple dotnet based containers.</span></span> 

```
REPOSITORY          TAG                     IMAGE ID            SIZE
microsoft/dotnet    1.0.0-preview2-onbuild  19b6a6c4b1db        540.4 MB
microsoft/dotnet    onbuild                 19b6a6c4b1db        540.4 MB
microsoft/dotnet    1.0.0-preview2-sdk      a92c3d9ad0e7        540.4 MB
microsoft/dotnet    core                    5224a9f2a2aa        253.2 MB
microsoft/dotnet    1.0.0-core-deps         c981a2eebe0e        166.2 MB
microsoft/dotnet    core-deps               c981a2eebe0e        166.2 MB
microsoft/dotnet    latest                  03c10abbd08a        540.4 MB
microsoft/dotnet    1.0.0-core              b8da4a1fd280        253.2 MB
```

## <a name="prerequisites"></a><span data-ttu-id="46ffa-162">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="46ffa-162">Prerequisites</span></span>

<span data-ttu-id="46ffa-163">Для сборки и запуска необходимо установить несколько компонентов.</span><span class="sxs-lookup"><span data-stu-id="46ffa-163">To build and run, you'll need a few things installed:</span></span>

- [<span data-ttu-id="46ffa-164">.NET Core</span><span class="sxs-lookup"><span data-stu-id="46ffa-164">.NET Core</span></span>](http://dot.net)
- <span data-ttu-id="46ffa-165">[Docker](https://www.docker.com/products/docker) для локального выполнения контейнеров Docker</span><span class="sxs-lookup"><span data-stu-id="46ffa-165">[Docker](https://www.docker.com/products/docker) to run your Docker containers locally</span></span>
- [<span data-ttu-id="46ffa-166">Node.js</span><span class="sxs-lookup"><span data-stu-id="46ffa-166">Node.js</span></span>](https://nodejs.org/)
- <span data-ttu-id="46ffa-167">[Генератор Yeoman для ASP.NET](https://github.com/omnisharp/generator-aspnet) для создания приложения веб-интерфейса API</span><span class="sxs-lookup"><span data-stu-id="46ffa-167">[Yeoman generator for ASP.NET](https://github.com/omnisharp/generator-aspnet) for creating the Web API application</span></span>
- <span data-ttu-id="46ffa-168">[Генератор Yeoman для Docker](http://aka.ms/yodocker) от корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="46ffa-168">[Yeoman generator for Docker](http://aka.ms/yodocker) from Microsoft</span></span>

<span data-ttu-id="46ffa-169">Установите генераторы Yeoman для ASP.NET Core и Docker с помощью npm.</span><span class="sxs-lookup"><span data-stu-id="46ffa-169">Install the Yeoman generators for ASP.NET Core and Docker using npm</span></span> 

```
npm install -g yo generator-aspnet generator-docker
```

> [!NOTE]
> <span data-ttu-id="46ffa-170">В этом примере в качестве редактора будет использоваться [Visual Studio Code](http://code.visualstudio.com).</span><span class="sxs-lookup"><span data-stu-id="46ffa-170">This sample will be using [Visual Studio Code](http://code.visualstudio.com) for the editor.</span></span>

## <a name="creating-the-web-api-application"></a><span data-ttu-id="46ffa-171">Создание приложения веб-интерфейса API</span><span class="sxs-lookup"><span data-stu-id="46ffa-171">Creating the Web API application</span></span>

<span data-ttu-id="46ffa-172">Чтобы получить ориентир, перед упаковкой приложения в контейнер запустите его локально.</span><span class="sxs-lookup"><span data-stu-id="46ffa-172">For a reference point, before we containerize the application, first run the application locally.</span></span> 

<span data-ttu-id="46ffa-173">Готовое приложение находится в [репозитории dotnet/docs на сайте GitHub](https://github.com/dotnet/docs/tree/master/samples/core/docker/building-net-docker-images).</span><span class="sxs-lookup"><span data-stu-id="46ffa-173">The finished application is located in the [dotnet/docs repository on GitHub](https://github.com/dotnet/docs/tree/master/samples/core/docker/building-net-docker-images).</span></span> <span data-ttu-id="46ffa-174">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="46ffa-174">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="46ffa-175">Создайте каталог для приложения.</span><span class="sxs-lookup"><span data-stu-id="46ffa-175">Create a directory for your application.</span></span>

<span data-ttu-id="46ffa-176">Откройте сеанс выполнения команд или сеанс терминала в этом каталоге и используйте генератор Yeoman для ASP.NET, введя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="46ffa-176">Open a command or terminal session in that directory and use the ASP.NET Yeoman generator by typing the following:</span></span>
```
yo aspnet
```

<span data-ttu-id="46ffa-177">Выберите **Приложение веб-интерфейса API**, введите **api** в качестве имени приложения и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="46ffa-177">Select **Web API Application** and type **api** for the name of the app and tap enter.</span></span>  <span data-ttu-id="46ffa-178">После создания приложения по шаблону перейдите в каталог `/api` и восстановите зависимости NuGet с помощью команды `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="46ffa-178">Once the application is scaffolded, change to the `/api` directory and restore the NuGet dependencies using `dotnet restore`.</span></span>

```
cd api
dotnet restore
```

<span data-ttu-id="46ffa-179">Протестируйте приложение, выполнив команду `dotnet run` и перейдя по адресу **http://localhost:5000/api/values**.</span><span class="sxs-lookup"><span data-stu-id="46ffa-179">Test the application using `dotnet run` and browsing to **http://localhost:5000/api/values**</span></span>

```javascript
[
    "value1",
    "value2"
]
```

<span data-ttu-id="46ffa-180">Чтобы остановить приложение, нажмите клавишу `Ctrl+C`.</span><span class="sxs-lookup"><span data-stu-id="46ffa-180">Use `Ctrl+C` to stop the application.</span></span>

## <a name="adding-docker-support"></a><span data-ttu-id="46ffa-181">Добавление поддержки Docker</span><span class="sxs-lookup"><span data-stu-id="46ffa-181">Adding Docker support</span></span>

<span data-ttu-id="46ffa-182">Добавление поддержки Docker в проект осуществляется посредством генератора Yeoman от корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="46ffa-182">Adding Docker support to the project is achieved using the Yeoman generator from Microsoft.</span></span> <span data-ttu-id="46ffa-183">В настоящее время он поддерживает проекты .NET Core, Node.js и Go путем создания файла Dockerfile и скриптов, помогающих собирать и выполнять проекты в контейнерах.</span><span class="sxs-lookup"><span data-stu-id="46ffa-183">It currently supports .NET Core, Node.js and Go projects by creating a Dockerfile and scripts that help build and run projects inside containers.</span></span> <span data-ttu-id="46ffa-184">Также добавляются файлы, относящиеся к Visual Studio Code (launch.json, tasks.json), для поддержки отладки и палитры команд редактора.</span><span class="sxs-lookup"><span data-stu-id="46ffa-184">Visual Studio Code specific files are also added (launch.json, tasks.json) for editor debugging and command palette support.</span></span>

```console
$ yo docker

     _-----_     ╭──────────────────────────╮
    |       |    │   Welcome to the Docker  │
    |--(o)--|    │        generator!        │
   `---------´   │     Let's add Docker     │
    ( _´U`_ )    │  container magic to your │
    /___A___\   /│           app!           │
     |  ~  |     ╰──────────────────────────╯
   __'.___.'__
 ´   `  |° ´ Y `

? What language is your project using? (Use arrow keys)
❯ .NET Core
  Golang
  Node.js
```

- <span data-ttu-id="46ffa-185">В качестве типа проекта выберите `.NET Core`.</span><span class="sxs-lookup"><span data-stu-id="46ffa-185">Select `.NET Core` as the project type</span></span>
- <span data-ttu-id="46ffa-186">`rtm` — версия .NET Core</span><span class="sxs-lookup"><span data-stu-id="46ffa-186">`rtm` for the version of .NET Core</span></span>
- <span data-ttu-id="46ffa-187">`Y` — проект использует веб-сервер</span><span class="sxs-lookup"><span data-stu-id="46ffa-187">`Y` the project uses a web server</span></span>
- <span data-ttu-id="46ffa-188">`5000` — порт, который прослушивает приложение веб-интерфейса API (http://localhost:5000)</span><span class="sxs-lookup"><span data-stu-id="46ffa-188">`5000` is the port the Web API application is listening on (http://localhost:5000)</span></span>
- <span data-ttu-id="46ffa-189">`api` — имя образа</span><span class="sxs-lookup"><span data-stu-id="46ffa-189">`api` for the image name</span></span>
- <span data-ttu-id="46ffa-190">`api` — имя службы</span><span class="sxs-lookup"><span data-stu-id="46ffa-190">`api` for the service name</span></span>
- <span data-ttu-id="46ffa-191">`api` — составной проект</span><span class="sxs-lookup"><span data-stu-id="46ffa-191">`api` for the compose project</span></span> 
- <span data-ttu-id="46ffa-192">`Y` — перезапись текущего файла Dockerfile</span><span class="sxs-lookup"><span data-stu-id="46ffa-192">`Y` to overwrite the current Dockerfile</span></span>

<span data-ttu-id="46ffa-193">Когда работа генератора завершится, в проект будут добавлены следующие файлы.</span><span class="sxs-lookup"><span data-stu-id="46ffa-193">When the generator is complete, the following files are added to the project</span></span>

- <span data-ttu-id="46ffa-194">.vscode/launch.json</span><span class="sxs-lookup"><span data-stu-id="46ffa-194">.vscode/launch.json</span></span>
- <span data-ttu-id="46ffa-195">Dockerfile.debug</span><span class="sxs-lookup"><span data-stu-id="46ffa-195">Dockerfile.debug</span></span>
- <span data-ttu-id="46ffa-196">Dockerfile</span><span class="sxs-lookup"><span data-stu-id="46ffa-196">Dockerfile</span></span>
- <span data-ttu-id="46ffa-197">docker-compose.debug.yml</span><span class="sxs-lookup"><span data-stu-id="46ffa-197">docker-compose.debug.yml</span></span>
- <span data-ttu-id="46ffa-198">docker-compose.yml</span><span class="sxs-lookup"><span data-stu-id="46ffa-198">docker-compose.yml</span></span>
- <span data-ttu-id="46ffa-199">dockerTask.ps1</span><span class="sxs-lookup"><span data-stu-id="46ffa-199">dockerTask.ps1</span></span>
- <span data-ttu-id="46ffa-200">dockerTask.sh</span><span class="sxs-lookup"><span data-stu-id="46ffa-200">dockerTask.sh</span></span>
- <span data-ttu-id="46ffa-201">.vscode/tasks.json</span><span class="sxs-lookup"><span data-stu-id="46ffa-201">.vscode/tasks.json</span></span>

<span data-ttu-id="46ffa-202">Генератор создает два файла Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="46ffa-202">The generator creates two Dockerfiles.</span></span>

<span data-ttu-id="46ffa-203">**Dockerfile.debug** — этот файл основан на образе **microsoft/dotnet:1.0.0-preview2-sdk**, который, как можно видеть в списке вариантов образов, включает пакет SDK, интерфейс CLI и платформу .NET Core и будет образом, используемым для разработки и отладки (F5).</span><span class="sxs-lookup"><span data-stu-id="46ffa-203">**Dockerfile.debug** - this file is based on the **microsoft/dotnet:1.0.0-preview2-sdk** image which if you note from the list of image variants, includes the SDK, CLI and .NET Core and will be the image used for development and debugging (F5).</span></span> <span data-ttu-id="46ffa-204">Включение всех этих компонентов увеличивает размер образа приблизительно до 540 МБ.</span><span class="sxs-lookup"><span data-stu-id="46ffa-204">Including all of these components produces a larger image with a size roughly of 540MB.</span></span>

<span data-ttu-id="46ffa-205">**Dockerfile** — это образ выпуска, основанный на **microsoft/dotnet:1.0.0-core**, который следует использовать для рабочей среды.</span><span class="sxs-lookup"><span data-stu-id="46ffa-205">**Dockerfile** - this image is the release image based on **microsoft/dotnet:1.0.0-core** and should be used for production.</span></span> <span data-ttu-id="46ffa-206">После сборки его размер составляет приблизительно 253 МБ.</span><span class="sxs-lookup"><span data-stu-id="46ffa-206">This image when built is approximately 253 MB.</span></span>

### <a name="creating-the-docker-images"></a><span data-ttu-id="46ffa-207">Создание образов Docker</span><span class="sxs-lookup"><span data-stu-id="46ffa-207">Creating the Docker images</span></span>
<span data-ttu-id="46ffa-208">С помощью скрипта `dockerTask.sh` или `dockerTask.ps1` можно выполнить сборку или компоновку образа и контейнера для приложения **api** для определенной среды.</span><span class="sxs-lookup"><span data-stu-id="46ffa-208">Using the `dockerTask.sh` or `dockerTask.ps1` script, we can build or compose the image and container for the **api** application for a specific environment.</span></span> <span data-ttu-id="46ffa-209">Выполните сборку образа **debug**, выполнив приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="46ffa-209">Build the **debug** image by running the following command.</span></span>

```bash
./dockerTask.sh build debug
```

<span data-ttu-id="46ffa-210">Образ выполнит сборку приложения ASP.NET, вызовет команду `dotnet restore`, добавит отладчик в образ, задаст `ENTRYPOINT` и, наконец, скопирует приложение в образ.</span><span class="sxs-lookup"><span data-stu-id="46ffa-210">The image will build the ASP.NET application, run `dotnet restore`, add the debugger to the image, set an `ENTRYPOINT` and finally copy the app to the image.</span></span> <span data-ttu-id="46ffa-211">Результатом будет образ Docker с именем *api* и с тегом (`TAG`) *debug*.</span><span class="sxs-lookup"><span data-stu-id="46ffa-211">The result is a Docker image named *api* with a `TAG` of *debug*.</span></span>  <span data-ttu-id="46ffa-212">Просмотреть образы на компьютере можно с помощью команды `docker images`.</span><span class="sxs-lookup"><span data-stu-id="46ffa-212">See the images on the machine using `docker images`.</span></span>

```bash
docker images

REPOSITORY          TAG                  IMAGE ID            CREATED             SIZE
api                 debug                70e89fbc5dbe        a few seconds ago   779.8 MB
```

<span data-ttu-id="46ffa-213">Другой способ создать образ и запустить приложение в контейнере Docker — открыть приложение в Visual Studio Code и воспользоваться средствами отладки.</span><span class="sxs-lookup"><span data-stu-id="46ffa-213">Another way to generate the image and run the application within the Docker container is to open the application in Visual Studio Code and use the debugging tools.</span></span> 

<span data-ttu-id="46ffa-214">Щелкните значок отладки на панели представлений в левой части окна Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="46ffa-214">Select the debugging icon in the View Bar on the left side of Visual Studio Code.</span></span>

![Значок отладки VS Code](./media/building-net-docker-images/debugging_debugicon.png)

<span data-ttu-id="46ffa-216">Затем щелкните значок воспроизведения или нажмите клавишу F5, чтобы создать образ и запустить приложение в контейнере.</span><span class="sxs-lookup"><span data-stu-id="46ffa-216">Then tap the play icon or F5 to generate the image and start the application within the container.</span></span> <span data-ttu-id="46ffa-217">Приложение веб-интерфейса API будет запущено с помощью веб-браузера по умолчанию по адресу http://localhost:5000.</span><span class="sxs-lookup"><span data-stu-id="46ffa-217">The Web API will be launched using your default web browser at http://localhost:5000.</span></span>

![Средства отладки VS Code для Docker](./media/building-net-docker-images/docker-tools-vscode-f5.png)

<span data-ttu-id="46ffa-219">Вы можете устанавливать точки останова в приложении, выполнять его пошагово и выполнять другие действия, как если бы приложение выполнялось локально на компьютере разработки, а не в контейнере.</span><span class="sxs-lookup"><span data-stu-id="46ffa-219">You may set break points in your application, step through, etc. just as if the application was running locally on your development machine as opposed to inside the container.</span></span> <span data-ttu-id="46ffa-220">Преимущество отладки в контейнере в том, что это тот же образ, который будет развертываться в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="46ffa-220">The benefit to debugging within the container is this is the same image that would be deployed to a production environment.</span></span>

<span data-ttu-id="46ffa-221">Чтобы создать образ выпуска или рабочий образ, достаточно просто выполнить команду в терминале, указав имя среды `release`.</span><span class="sxs-lookup"><span data-stu-id="46ffa-221">Creating the release or production image requires simply running the command from the terminal passing the `release` environment name.</span></span>

```bash
./dockerTask build release
```

<span data-ttu-id="46ffa-222">Команда создает образ на основе базового образа **microsoft/dotnet:core** меньшего размера, открывает ([EXPOSE](https://docs.docker.com/engine/reference/builder/#/expose)) порт 5000, задает точку входа ([ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint)) для `dotnet api.dll` и копирует ее в каталог `/app`.</span><span class="sxs-lookup"><span data-stu-id="46ffa-222">The command creates the image based on the smaller **microsoft/dotnet:core** base image, [EXPOSE](https://docs.docker.com/engine/reference/builder/#/expose) port 5000, sets the [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) for `dotnet api.dll` and copies it to the `/app` directory.</span></span> <span data-ttu-id="46ffa-223">Нет отладчика, пакета SDK, и не выполняется команда `dotnet restore`, благодаря чему размер образа гораздо меньше.</span><span class="sxs-lookup"><span data-stu-id="46ffa-223">There is no debugger, SDK or `dotnet restore` resulting in a much smaller image.</span></span> <span data-ttu-id="46ffa-224">Образ имеет имя **api** и тег (`TAG`) **latest**.</span><span class="sxs-lookup"><span data-stu-id="46ffa-224">The image is named **api** with a `TAG` of **latest**.</span></span>

```
REPOSITORY          TAG                  IMAGE ID            CREATED             SIZE
api                 debug                70e89fbc5dbe        1 hour ago        779.8 MB
api                 latest               ef17184c8de6        1 hour ago        260.7 MB
```

## <a name="summary"></a><span data-ttu-id="46ffa-225">Сводка</span><span class="sxs-lookup"><span data-stu-id="46ffa-225">Summary</span></span>

<span data-ttu-id="46ffa-226">Использование генератора Docker для добавления необходимых файлов в приложение веб-интерфейса API упростило создание версий образов для разработки и рабочей среды.</span><span class="sxs-lookup"><span data-stu-id="46ffa-226">Using the Docker generator to add the necessary files to our Web API application made the process simple to create the development and production versions of the images.</span></span>  <span data-ttu-id="46ffa-227">Кроссплатформенность средств также достигается с помощью скрипта PowerShell, который позволяет получить те же результаты в Windows, а интеграция с Visual Studio Code дает возможность пошаговой отладки приложения в контейнере.</span><span class="sxs-lookup"><span data-stu-id="46ffa-227">The tooling is cross platform by also providing a PowerShell script to accomplish the same results on Windows and Visual Studio Code integration providing step through debugging of the application within the container.</span></span> <span data-ttu-id="46ffa-228">Понимая назначение вариантов образов и целевые сценарии, вы можете оптимизировать внутренний цикл разработки и получить более эффективные образы для рабочих развертываний.</span><span class="sxs-lookup"><span data-stu-id="46ffa-228">By understanding the image variants and the target scenarios, you can optimize your inner-loop development process, while achieving optimized images for production deployments.</span></span>  



