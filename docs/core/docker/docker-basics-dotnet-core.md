---
title: "Основы работы с Docker с помощью .NET Core"
description: "Базовое руководство по Docker и .NET Core"
keywords: ".NET, .NET Core, Docker, руководство"
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
ms.openlocfilehash: 79ded2ce5de5100c18301127a2654f8791b8ed76
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="learn-docker-basics-with-net-core"></a><span data-ttu-id="8eaad-104">Основы работы с Docker с помощью .NET Core</span><span class="sxs-lookup"><span data-stu-id="8eaad-104">Learn Docker Basics with .NET Core</span></span>

<span data-ttu-id="8eaad-105">Это руководство описывает задачи сборки и развертывания контейнера Docker для приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8eaad-105">This tutorial teaches the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="8eaad-106">В ходе работы с этим руководством вы узнаете:</span><span class="sxs-lookup"><span data-stu-id="8eaad-106">During the course of this tutorial, you learn:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="8eaad-107">как создать Dockerfile;</span><span class="sxs-lookup"><span data-stu-id="8eaad-107">How to create a Dockerfile</span></span>
> * <span data-ttu-id="8eaad-108">как создать приложение .NET Core;</span><span class="sxs-lookup"><span data-stu-id="8eaad-108">How to create a .NET Core app.</span></span>
> * <span data-ttu-id="8eaad-109">как развертывать приложение в контейнер Docker.</span><span class="sxs-lookup"><span data-stu-id="8eaad-109">How to deploy your app into a Docker container.</span></span>

<span data-ttu-id="8eaad-110">[Платформа Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) использует [подсистему Docker](https://docs.docker.com/engine/docker-overview/#docker-engine) для быстрой сборки и упаковки приложений в качестве [образов Docker](https://docs.docker.com/glossary/?term=image).</span><span class="sxs-lookup"><span data-stu-id="8eaad-110">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image).</span></span> <span data-ttu-id="8eaad-111">Эти образы имеют формат [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) и предназначены для развертывания и запуска в [многоуровневом контейнере](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span><span class="sxs-lookup"><span data-stu-id="8eaad-111">These images are written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format to be deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>

## <a name="net-core-easiest-way-to-get-started"></a><span data-ttu-id="8eaad-112">.NET Core: самый простой способ начать работу</span><span class="sxs-lookup"><span data-stu-id="8eaad-112">.NET Core: Easiest way to get started</span></span>

<span data-ttu-id="8eaad-113">Перед созданием образа Docker вам потребуется приложение для упаковки в контейнер.</span><span class="sxs-lookup"><span data-stu-id="8eaad-113">Before creating the Docker image, you need an application to containerize.</span></span> <span data-ttu-id="8eaad-114">Его можно создать в Windows, Linux или MacOS.</span><span class="sxs-lookup"><span data-stu-id="8eaad-114">You can create it on Linux, MacOS, or Windows.</span></span> <span data-ttu-id="8eaad-115">Самый быстрый и простой способ — использовать .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8eaad-115">The quickest and easiest way to do that is to use .NET Core.</span></span>

<span data-ttu-id="8eaad-116">Если вы не знакомы с набором средств CLI .NET Core, прочитайте [обзор пакета SDK для .NET Core](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="8eaad-116">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

<span data-ttu-id="8eaad-117">Вы можете создать контейнеры Windows и Linux с использованием [тегов на основе мультиархитектурности](https://github.com/dotnet/announcements/issues/14).</span><span class="sxs-lookup"><span data-stu-id="8eaad-117">You can build both Windows and Linux containers with [multi-arch based tags](https://github.com/dotnet/announcements/issues/14).</span></span>

## <a name="your-first-net-core-docker-app"></a><span data-ttu-id="8eaad-118">Ваше первое приложение Docker для .NET Core</span><span class="sxs-lookup"><span data-stu-id="8eaad-118">Your first .NET Core Docker app</span></span>

### <a name="prerequisites"></a><span data-ttu-id="8eaad-119">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="8eaad-119">Prerequisites</span></span>

<span data-ttu-id="8eaad-120">Для работы с этим руководством вам понадобится следующее:</span><span class="sxs-lookup"><span data-stu-id="8eaad-120">To complete this tutorial:</span></span>

#### <a name="net-core-20-sdk"></a><span data-ttu-id="8eaad-121">Пакет SDK для .NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="8eaad-121">.NET Core 2.0 SDK</span></span>

* <span data-ttu-id="8eaad-122">Установите [пакет SDK для .NET Core 2.0](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="8eaad-122">Install [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span></span>

<span data-ttu-id="8eaad-123">Полный список операционных систем, поддерживаемых .NET Core 2.x, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [Версии ОС, поддерживаемые .NET Core 2.x](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="8eaad-123">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

* <span data-ttu-id="8eaad-124">Установите любой привычный для вас редактор кода, если еще не сделали этого.</span><span class="sxs-lookup"><span data-stu-id="8eaad-124">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="8eaad-125">Нужно ли устанавливать редактор кода?</span><span class="sxs-lookup"><span data-stu-id="8eaad-125">Need to install a code editor?</span></span> <span data-ttu-id="8eaad-126">Попробуйте использовать [Visual Studio](https://visualstudio.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="8eaad-126">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="8eaad-127">Установка клиента Docker</span><span class="sxs-lookup"><span data-stu-id="8eaad-127">Installing Docker Client</span></span>

<span data-ttu-id="8eaad-128">Установите клиент [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="8eaad-128">Install [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="8eaad-129">Клиент Docker можно установить в:</span><span class="sxs-lookup"><span data-stu-id="8eaad-129">The Docker client can be installed in:</span></span>

* <span data-ttu-id="8eaad-130">Дистрибутивах Linux</span><span class="sxs-lookup"><span data-stu-id="8eaad-130">Linux distributions</span></span>

   * [<span data-ttu-id="8eaad-131">CentOS</span><span class="sxs-lookup"><span data-stu-id="8eaad-131">CentOS</span></span>](https://www.docker.com/docker-centos-distribution)

   * [<span data-ttu-id="8eaad-132">Debian</span><span class="sxs-lookup"><span data-stu-id="8eaad-132">Debian</span></span>](https://www.docker.com/docker-debian)

   * [<span data-ttu-id="8eaad-133">Fedora</span><span class="sxs-lookup"><span data-stu-id="8eaad-133">Fedora</span></span>](https://www.docker.com/docker-fedora)

   * [<span data-ttu-id="8eaad-134">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="8eaad-134">Ubuntu</span></span>](https://www.docker.com/docker-ubuntu)

* [<span data-ttu-id="8eaad-135">macOS</span><span class="sxs-lookup"><span data-stu-id="8eaad-135">macOS</span></span>](https://docs.docker.com/docker-for-mac/)

* <span data-ttu-id="8eaad-136">[Windows](https://docs.docker.com/docker-for-windows/)</span><span class="sxs-lookup"><span data-stu-id="8eaad-136">[Windows](https://docs.docker.com/docker-for-windows/).</span></span>

### <a name="create-a-net-core-20-console-app-for-dockerization"></a><span data-ttu-id="8eaad-137">Создание консольного приложения .NET Core 2.0 для добавления в Docker</span><span class="sxs-lookup"><span data-stu-id="8eaad-137">Create a .NET Core 2.0 console app for Dockerization</span></span>

<span data-ttu-id="8eaad-138">Откройте командную строку и создайте папку с именем *Hello*.</span><span class="sxs-lookup"><span data-stu-id="8eaad-138">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="8eaad-139">Перейдите в созданную папку и введите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="8eaad-139">Navigate to the folder you created and type the following commands:</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="8eaad-140">Вкратце рассмотрим эти команды.</span><span class="sxs-lookup"><span data-stu-id="8eaad-140">Let's do a quick walkthrough:</span></span>

1. `$ dotnet new console`

   <span data-ttu-id="8eaad-141">[`dotnet new`](../tools/dotnet-new.md) создает актуальный файл проекта `Hello.csproj` с зависимостями, необходимыми для создания консольного приложения.</span><span class="sxs-lookup"><span data-stu-id="8eaad-141">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="8eaad-142">Эта команда также создает `Program.cs` — простой файл, содержащий точку входа для приложения.</span><span class="sxs-lookup"><span data-stu-id="8eaad-142">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>
   
   <span data-ttu-id="8eaad-143">`Hello.csproj`:</span><span class="sxs-lookup"><span data-stu-id="8eaad-143">`Hello.csproj`:</span></span>

   <span data-ttu-id="8eaad-144">В файле проекта указываются все данные, необходимые для восстановления зависимостей и создания программы.</span><span class="sxs-lookup"><span data-stu-id="8eaad-144">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="8eaad-145">Тег `OutputType` указывает, что мы создаем исполняемый файл — другими словами, консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="8eaad-145">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="8eaad-146">Тег `TargetFramework` указывает, какая реализация.NET является целевой.</span><span class="sxs-lookup"><span data-stu-id="8eaad-146">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="8eaad-147">В расширенном сценарии обработки можно указать несколько целевых платформ и выполнить сборку в них за одну операцию.</span><span class="sxs-lookup"><span data-stu-id="8eaad-147">In an advanced scenario, you can specify multiple target frameworks and build to the specified frameworks in a single operation.</span></span> <span data-ttu-id="8eaad-148">В этом руководстве мы выполняем сборку для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="8eaad-148">In this tutorial, we build for .NET Core 2.0.</span></span>

   <span data-ttu-id="8eaad-149">`Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="8eaad-149">`Program.cs`:</span></span>

   <span data-ttu-id="8eaad-150">Программа начинается с команды `using System`.</span><span class="sxs-lookup"><span data-stu-id="8eaad-150">The program starts by `using System`.</span></span> <span data-ttu-id="8eaad-151">Это означает "добавить все данные пространства имен `System` в область видимости для этого файла".</span><span class="sxs-lookup"><span data-stu-id="8eaad-151">This statement means, "Bring everything in the `System` namespace into scope for this file."</span></span> <span data-ttu-id="8eaad-152">Пространство имен `System` содержит основные конструкции, такие как `string`, или числовые типы.</span><span class="sxs-lookup"><span data-stu-id="8eaad-152">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="8eaad-153">Затем мы определяем пространство имен с именем `Hello`.</span><span class="sxs-lookup"><span data-stu-id="8eaad-153">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="8eaad-154">Вы можете сменить это пространство имен на любое другое.</span><span class="sxs-lookup"><span data-stu-id="8eaad-154">You can change namespace to anything you want.</span></span> <span data-ttu-id="8eaad-155">Класс `Program` определяется в этом пространстве имен с использованием метода `Main`, который принимает массив строк в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="8eaad-155">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="8eaad-156">Этот массив содержит список аргументов, передаваемых при вызове скомпилированной программы.</span><span class="sxs-lookup"><span data-stu-id="8eaad-156">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="8eaad-157">В нашем примере программа просто выводит "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="8eaad-157">In our example, the program only writes "Hello World!"</span></span> <span data-ttu-id="8eaad-158">в консоль.</span><span class="sxs-lookup"><span data-stu-id="8eaad-158">to the console.</span></span>

2. `$ dotnet restore`

   <span data-ttu-id="8eaad-159">В .NET Core 2.x **dotnet new** запускает команду [`dotnet restore`](../tools/dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="8eaad-159">In .NET Core 2.x, **dotnet new** runs the [`dotnet restore`](../tools/dotnet-restore.md) command.</span></span> <span data-ttu-id="8eaad-160">**Dotnet restore** восстанавливает дерево зависимостей с помощью вызова [NuGet](https://www.nuget.org/) (диспетчер пакетов .NET).</span><span class="sxs-lookup"><span data-stu-id="8eaad-160">**Dotnet restore** restores the tree of dependencies with a [NuGet](https://www.nuget.org/)(.NET package manager) call.</span></span>
   <span data-ttu-id="8eaad-161">NuGet выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="8eaad-161">NuGet performs the following tasks:</span></span>
   * <span data-ttu-id="8eaad-162">анализирует файл *Hello.csproj*;</span><span class="sxs-lookup"><span data-stu-id="8eaad-162">analyzes the *Hello.csproj* file</span></span> 
   * <span data-ttu-id="8eaad-163">скачивает файл зависимостей (или получает его из кэша компьютера);</span><span class="sxs-lookup"><span data-stu-id="8eaad-163">downloads the file dependencies (or grabs from your machine cache)</span></span>
   * <span data-ttu-id="8eaad-164">записывает файл *obj/project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="8eaad-164">writes the *obj/project.assets.json* file</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
   
   <span data-ttu-id="8eaad-165">Файл *project.assets.json* содержит полную схему зависимостей NuGet, разрешения привязок и другие метаданные приложения.</span><span class="sxs-lookup"><span data-stu-id="8eaad-165">The *project.assets.json* file is a complete set of the NuGet dependencies graph, binding resolutions, and other app metadata.</span></span> <span data-ttu-id="8eaad-166">Этот обязательный файл используется другими средствами, например [`dotnet build`](../tools/dotnet-build.md) и [`dotnet run`](../tools/dotnet-run.md), для правильной обработки исходного кода.</span><span class="sxs-lookup"><span data-stu-id="8eaad-166">This required file is used by other tools, such as [`dotnet build`](../tools/dotnet-build.md) and [`dotnet run`](../tools/dotnet-run.md), to correctly process the source code.</span></span>
   
3. `$ dotnet run`

   <span data-ttu-id="8eaad-167">[`dotnet run`](../tools/dotnet-run.md) вызывает [`dotnet build`](../tools/dotnet-build.md) для подтверждения успешной сборки, а затем `dotnet <assembly.dll>` для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="8eaad-167">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to confirm a successful build, and then calls `dotnet <assembly.dll>` to run the application.</span></span>
   
    ```console
    $ dotnet run
    
    Hello World!
    ```

    <span data-ttu-id="8eaad-168">Сведения о более сложных сценариях см. в статье [Развертывание приложений .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="8eaad-168">For advanced scenarios,  see [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

## <a name="dockerize-the-net-core-application"></a><span data-ttu-id="8eaad-169">Добавление приложения .NET Core в Docker</span><span class="sxs-lookup"><span data-stu-id="8eaad-169">Dockerize the .NET Core application</span></span>

<span data-ttu-id="8eaad-170">Консольное приложение Hello .NET Core успешно выполняется локально.</span><span class="sxs-lookup"><span data-stu-id="8eaad-170">The Hello .NET Core console app successfully runs locally.</span></span> <span data-ttu-id="8eaad-171">Теперь продвинемся на шаг вперед, чтобы собрать и запустить приложение в Docker.</span><span class="sxs-lookup"><span data-stu-id="8eaad-171">Now let's take it a step further and build and run the app in Docker.</span></span>

### <a name="your-first-dockerfile"></a><span data-ttu-id="8eaad-172">Ваш первый Dockerfile</span><span class="sxs-lookup"><span data-stu-id="8eaad-172">Your first Dockerfile</span></span>

<span data-ttu-id="8eaad-173">Для начала работы откройте текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="8eaad-173">Open your text editor and let's get started!</span></span> <span data-ttu-id="8eaad-174">Мы все еще работаем из каталога Hello, где создали приложение.</span><span class="sxs-lookup"><span data-stu-id="8eaad-174">We're still working from the Hello directory we built the app in.</span></span>

<span data-ttu-id="8eaad-175">Добавьте в новый файл приведенные ниже инструкции Docker для [контейнеров Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) или Linux.</span><span class="sxs-lookup"><span data-stu-id="8eaad-175">Add the following Docker instructions for either Linux or [Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/) to a new file.</span></span> <span data-ttu-id="8eaad-176">По завершении сохраните его в корне каталога Hello в виде **Dockerfile** без разрешения (вам может потребоваться задать тип файла `All types (*.*)` или другой аналогичный).</span><span class="sxs-lookup"><span data-stu-id="8eaad-176">When finished, save it in the root of your Hello directory as **Dockerfile**, with no extension (You may need to set your file type to `All types (*.*)` or something similar).</span></span>

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
WORKDIR /app

# copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# copy and build everything else
COPY . ./
RUN dotnet publish -c Release -o out
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="8eaad-177">Dockerfile содержит инструкции сборки Docker, выполняемые последовательно.</span><span class="sxs-lookup"><span data-stu-id="8eaad-177">The Dockerfile contains Docker build instructions that run sequentially.</span></span>

<span data-ttu-id="8eaad-178">Первой инструкцией должна быть [**FROM**](https://docs.docker.com/engine/reference/builder/#from).</span><span class="sxs-lookup"><span data-stu-id="8eaad-178">The first instruction must be [**FROM**](https://docs.docker.com/engine/reference/builder/#from).</span></span> <span data-ttu-id="8eaad-179">Она инициализирует новый этап сборки и задает базовый образ для остальных инструкций.</span><span class="sxs-lookup"><span data-stu-id="8eaad-179">This instruction initializes a new build stage and sets the Base Image for the remaining instructions.</span></span> <span data-ttu-id="8eaad-180">Теги мультиархитектурности запрашивают контейнеры Windows или Linux в зависимости от [режима контейнеров](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers) Docker для Windows.</span><span class="sxs-lookup"><span data-stu-id="8eaad-180">The multi-arch tags pull either Windows or Linux containers depending on the Docker for Windows [container mode](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).</span></span> <span data-ttu-id="8eaad-181">Базовым образом для нашего примера является 2.0-sdk из репозитория microsoft/dotnet.</span><span class="sxs-lookup"><span data-stu-id="8eaad-181">The Base Image for our sample is the 2.0-sdk image from the microsoft/dotnet repository,</span></span>

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
```

<span data-ttu-id="8eaad-182">Инструкция [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) задает рабочий каталог для всех оставшихся инструкций RUN, CMD, ENTRYPOINT, COPY и ADD в Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="8eaad-182">The [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) instruction sets the working directory for any remaining RUN, CMD, ENTRYPOINT, COPY, and ADD Dockerfile instructions.</span></span> <span data-ttu-id="8eaad-183">Если этот каталог не существует, он создается.</span><span class="sxs-lookup"><span data-stu-id="8eaad-183">If the directory doesn't exist, it's created.</span></span> <span data-ttu-id="8eaad-184">В этом случае WORKDIR задает каталог приложения.</span><span class="sxs-lookup"><span data-stu-id="8eaad-184">In this case, WORKDIR is set to the app directory.</span></span>

```Dockerfile
WORKDIR /app
```

<span data-ttu-id="8eaad-185">Инструкция [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) копирует новые файлы или каталоги из исходного пути и добавляет их в файловую систему конечного контейнера.</span><span class="sxs-lookup"><span data-stu-id="8eaad-185">The [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) instruction copies new files or directories from the source path and adds them to the destination container filesystem.</span></span> <span data-ttu-id="8eaad-186">С этой инструкции мы копируем файл проекта C# в контейнер.</span><span class="sxs-lookup"><span data-stu-id="8eaad-186">With this instruction, we are copying the C# project file to the container.</span></span>

```Dockerfile
COPY *.csproj ./
```

<span data-ttu-id="8eaad-187">Инструкция [**RUN**](https://docs.docker.com/engine/reference/builder/#run) выполняет все команды в новом слое поверх текущего образа и фиксирует результаты.</span><span class="sxs-lookup"><span data-stu-id="8eaad-187">The [**RUN**](https://docs.docker.com/engine/reference/builder/#run) instruction executes any commands in a new layer on top of the current image and commit the results.</span></span> <span data-ttu-id="8eaad-188">Полученный зафиксированный образ используется на следующем шаге в Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="8eaad-188">The resulting committed image is used for the next step in the Dockerfile.</span></span> <span data-ttu-id="8eaad-189">Мы запускаем **dotnet restore**, чтобы получить нужные зависимости файла проекта C#.</span><span class="sxs-lookup"><span data-stu-id="8eaad-189">We are running **dotnet restore** to get the needed dependencies of the C# project file.</span></span> 

```Dockerfile
RUN dotnet restore
```

<span data-ttu-id="8eaad-190">Инструкция **COPY** копирует остальные файлы в контейнер на новые [слои](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span><span class="sxs-lookup"><span data-stu-id="8eaad-190">This **COPY** instruction copies the rest of the files into our container into new [layers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span></span>

```Dockerfile
COPY . ./
```

<span data-ttu-id="8eaad-191">Мы публикуем приложение с помощью этой инструкции **RUN**.</span><span class="sxs-lookup"><span data-stu-id="8eaad-191">We are publishing the app with this **RUN** instruction.</span></span> <span data-ttu-id="8eaad-192">Команда [**dotnet publish**](../tools/dotnet-publish.md) компилирует приложение, считывает его зависимости, указанные в файле проекта, и публикует итоговый набор файлов в каталоге.</span><span class="sxs-lookup"><span data-stu-id="8eaad-192">The [**dotnet publish**](../tools/dotnet-publish.md) command compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="8eaad-193">Наше приложение публикуется с конфигурацией **выпуска** и выводит данные в каталог по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8eaad-193">Our app is published with a **Release** configuration and output to the default directory.</span></span>

```Dockerfile
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="8eaad-194">Инструкция [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) предоставляет возможность запускать контейнер как исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="8eaad-194">The [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) instruction allows the container to run as an executable.</span></span>

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="8eaad-195">Теперь у вас есть Dockerfile, который:</span><span class="sxs-lookup"><span data-stu-id="8eaad-195">Now you have a Dockerfile that:</span></span>

* <span data-ttu-id="8eaad-196">копирует приложение в образ;</span><span class="sxs-lookup"><span data-stu-id="8eaad-196">copies your app to the image</span></span>
* <span data-ttu-id="8eaad-197">копирует зависимости приложения в образ;</span><span class="sxs-lookup"><span data-stu-id="8eaad-197">your app's dependencies to the image</span></span>
* <span data-ttu-id="8eaad-198">выполняет сборку приложения так, чтобы оно выполнялось как исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="8eaad-198">builds the app to run as an executable</span></span>

### <a name="build-and-run-the-hello-net-core-20-app"></a><span data-ttu-id="8eaad-199">Сборка и запуск приложения Hello .NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="8eaad-199">Build and run the Hello .NET Core 2.0 app</span></span>

#### <a name="essential-docker-commands"></a><span data-ttu-id="8eaad-200">Основные команды Docker</span><span class="sxs-lookup"><span data-stu-id="8eaad-200">Essential Docker commands</span></span>

<span data-ttu-id="8eaad-201">Ниже указаны основные команды Docker:</span><span class="sxs-lookup"><span data-stu-id="8eaad-201">These Docker commands are essential:</span></span>

* [<span data-ttu-id="8eaad-202">docker build</span><span class="sxs-lookup"><span data-stu-id="8eaad-202">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="8eaad-203">docker run</span><span class="sxs-lookup"><span data-stu-id="8eaad-203">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="8eaad-204">docker ps</span><span class="sxs-lookup"><span data-stu-id="8eaad-204">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="8eaad-205">docker stop</span><span class="sxs-lookup"><span data-stu-id="8eaad-205">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="8eaad-206">docker rm</span><span class="sxs-lookup"><span data-stu-id="8eaad-206">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="8eaad-207">docker rmi</span><span class="sxs-lookup"><span data-stu-id="8eaad-207">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="8eaad-208">docker image</span><span class="sxs-lookup"><span data-stu-id="8eaad-208">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a><span data-ttu-id="8eaad-209">Сборка и запуск</span><span class="sxs-lookup"><span data-stu-id="8eaad-209">Build and run</span></span>

<span data-ttu-id="8eaad-210">Вы написали Dockerfile, теперь Docker создает приложение и затем запускает контейнер.</span><span class="sxs-lookup"><span data-stu-id="8eaad-210">You wrote the dockerfile; now Docker builds your app and then runs the container.</span></span>

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

<span data-ttu-id="8eaad-211">Выходные данные команды `docker build` должны быть аналогичны приведенным далее выходным данным консоли:</span><span class="sxs-lookup"><span data-stu-id="8eaad-211">The output from the `docker build` command should be similar to the following console output:</span></span>

```console
Sending build context to Docker daemon   72.7kB
Step 1/7 : FROM microsoft/dotnet:2.0-sdk
 ---> d84f64b126a6
Step 2/7 : WORKDIR /app
 ---> Using cache
 ---> 9af1fbdc7972
Step 3/7 : COPY *.csproj ./
 ---> Using cache
 ---> 86c8c332d4b3
Step 4/7 : RUN dotnet restore
 ---> Using cache
 ---> 86fcd7dd0ea4
Step 5/7 : COPY . ./
 ---> Using cache
 ---> 6faf0a53607f
Step 6/7 : RUN dotnet publish -c Release -o out
 ---> Using cache
 ---> f972328318c8
Step 7/7 : ENTRYPOINT dotnet out/Hello.dll
 ---> Using cache
 ---> 53c337887e18
Successfully built 53c337887e18
Successfully tagged dotnetapp-dev:latest
```

<span data-ttu-id="8eaad-212">Как видно из выходных данных, подсистема Docker использует Dockerfile для создания контейнера.</span><span class="sxs-lookup"><span data-stu-id="8eaad-212">As you can see from the output, the Docker Engine used the Dockerfile to build our container.</span></span>

<span data-ttu-id="8eaad-213">Выходные данные команды `docker run` должны быть аналогичны приведенным далее выходным данным консоли:</span><span class="sxs-lookup"><span data-stu-id="8eaad-213">The output from the `docker run` command should be similar to the following console output:</span></span>

```console
Hello World!
```

<span data-ttu-id="8eaad-214">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="8eaad-214">Congratulations!</span></span> <span data-ttu-id="8eaad-215">Вы только что:</span><span class="sxs-lookup"><span data-stu-id="8eaad-215">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="8eaad-216">создали локальное приложение .NET Core;</span><span class="sxs-lookup"><span data-stu-id="8eaad-216">Created a local .NET Core app</span></span>
> * <span data-ttu-id="8eaad-217">создали Dockerfile для сборки первого контейнера;</span><span class="sxs-lookup"><span data-stu-id="8eaad-217">Created a Dockerfile to build your first container</span></span>
> * <span data-ttu-id="8eaad-218">создали и запустили приложение, добавленное в Docker.</span><span class="sxs-lookup"><span data-stu-id="8eaad-218">Built and ran your Dockerized app</span></span>



## <a name="next-steps"></a><span data-ttu-id="8eaad-219">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="8eaad-219">Next Steps</span></span>

<span data-ttu-id="8eaad-220">Ниже приведены некоторые действия, которые можно предпринять:</span><span class="sxs-lookup"><span data-stu-id="8eaad-220">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="8eaad-221">Вводный видеоролик об образах Docker для .NET</span><span class="sxs-lookup"><span data-stu-id="8eaad-221">Introduction to .NET Docker Images Video</span></span>](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [<span data-ttu-id="8eaad-222">Преимущества совместного использования Visual Studio, Docker и экземпляров контейнеров Azure</span><span class="sxs-lookup"><span data-stu-id="8eaad-222">Visual Studio, Docker & Azure Container Instances better together!</span></span>](https://blogs.msdn.microsoft.com/alimaz/2017/08/17/visual-studio-docker-azure-container-instances-better-together/)
* [<span data-ttu-id="8eaad-223">Краткие руководства по Docker для Azure</span><span class="sxs-lookup"><span data-stu-id="8eaad-223">Docker for Azure Quickstarts</span></span>](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [<span data-ttu-id="8eaad-224">Развертывание приложения в Docker для Azure</span><span class="sxs-lookup"><span data-stu-id="8eaad-224">Deploy your app on Docker for Azure</span></span>](https://docs.docker.com/docker-for-azure/deploy/)

> [!Note]
> <span data-ttu-id="8eaad-225">Если у вас нет подписки Azure, [зарегистрируйте сейчас](https://azure.microsoft.com/free/?b=16.48) бесплатную учетную запись на 30 дней и получите 200 долл. США на счет в Azure, чтобы опробовать любое сочетание служб Azure.</span><span class="sxs-lookup"><span data-stu-id="8eaad-225">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>

## <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="8eaad-226">Образы Docker, используемые в этом примере</span><span class="sxs-lookup"><span data-stu-id="8eaad-226">Docker Images used in this sample</span></span>

<span data-ttu-id="8eaad-227">В этом примере используются следующие образы Docker:</span><span class="sxs-lookup"><span data-stu-id="8eaad-227">The following Docker images are used in this sample</span></span>

* [`microsoft/dotnet:2.0-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a><span data-ttu-id="8eaad-228">Связанные ресурсы</span><span class="sxs-lookup"><span data-stu-id="8eaad-228">Related Resources</span></span>

* [<span data-ttu-id="8eaad-229">Примеры Docker для .NET Core</span><span class="sxs-lookup"><span data-stu-id="8eaad-229">.NET Core Docker samples</span></span>](https://github.com/dotnet/dotnet-docker-samples/README.md)
* [<span data-ttu-id="8eaad-230">Dockerfile в контейнерах Windows</span><span class="sxs-lookup"><span data-stu-id="8eaad-230">Dockerfile on Windows Containers</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [<span data-ttu-id="8eaad-231">Примеры Docker для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8eaad-231">.NET Framework Docker samples</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [<span data-ttu-id="8eaad-232">ASP.NET Core в центре Docker</span><span class="sxs-lookup"><span data-stu-id="8eaad-232">ASP.NET Core on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnetcore/)
* [<span data-ttu-id="8eaad-233">Добавление приложения .NET Core в Docker — руководство</span><span class="sxs-lookup"><span data-stu-id="8eaad-233">Dockerize a .NET Core application - Docker Tutorial</span></span>](https://docs.docker.com/engine/examples/dotnetcore/)
* [<span data-ttu-id="8eaad-234">Работа со средствами Visual Studio для Docker</span><span class="sxs-lookup"><span data-stu-id="8eaad-234">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* <span data-ttu-id="8eaad-235">[Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/) (Развертывание образов Docker из реестра контейнеров Azure в службе "Экземпляры контейнеров Azure")</span><span class="sxs-lookup"><span data-stu-id="8eaad-235">[Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)</span></span>