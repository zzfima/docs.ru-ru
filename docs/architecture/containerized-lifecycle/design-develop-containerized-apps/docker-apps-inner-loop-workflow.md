---
title: Рабочий процесс внутреннего цикла разработки для приложений Docker
description: Сведения о рабочем процессе "внутреннего цикла" при разработке приложений Docker.
ms.date: 02/15/2019
ms.openlocfilehash: 3d2fc889d22dbf02acccfbf9231ad98fca224cff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75936802"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="f1b64-103">Рабочий процесс внутреннего цикла разработки для приложений Docker</span><span class="sxs-lookup"><span data-stu-id="f1b64-103">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="f1b64-104">Рабочий процесс внутреннего цикла, охватывающий весь цикл DevOps, начинается на компьютере каждого разработчика, где разработчик локально пишет код приложения на предпочитаемых языках и платформах, а затем тестирует его (рис. 4-21).</span><span class="sxs-lookup"><span data-stu-id="f1b64-104">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-21).</span></span> <span data-ttu-id="f1b64-105">Независимо от выбранного языка и платформы этот рабочий процесс имеет одну общую черту:</span><span class="sxs-lookup"><span data-stu-id="f1b64-105">But in every case, you'll have an important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="f1b64-106">вы всегда разрабатываете и тестируете контейнеры Docker, но делаете это локально.</span><span class="sxs-lookup"><span data-stu-id="f1b64-106">In this specific workflow, you're always developing and testing Docker containers, but locally.</span></span>

![Схема, показывающая концепцию среды разработки внутреннего цикла](./media/docker-apps-inner-loop-workflow/inner-loop-development-context.png)

<span data-ttu-id="f1b64-108">**Рис. 4-21**.</span><span class="sxs-lookup"><span data-stu-id="f1b64-108">**Figure 4-21**.</span></span> <span data-ttu-id="f1b64-109">Контекст внутреннего цикла разработки</span><span class="sxs-lookup"><span data-stu-id="f1b64-109">Inner-loop development context</span></span>

<span data-ttu-id="f1b64-110">В каждый контейнер или экземпляр образа Docker входят следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="f1b64-110">The container or instance of a Docker image will contain these components:</span></span>

- <span data-ttu-id="f1b64-111">выбранная операционная система (например, Windows или дистрибутив Linux);</span><span class="sxs-lookup"><span data-stu-id="f1b64-111">An operating system selection (for example, a Linux distribution or Windows)</span></span>

- <span data-ttu-id="f1b64-112">файлы, добавленные разработчиком (например, двоичные файлы приложения);</span><span class="sxs-lookup"><span data-stu-id="f1b64-112">Files added by the developer (for example, app binaries)</span></span>

- <span data-ttu-id="f1b64-113">конфигурация (например, параметры среды и зависимости);</span><span class="sxs-lookup"><span data-stu-id="f1b64-113">Configuration (for example, environment settings and dependencies)</span></span>

- <span data-ttu-id="f1b64-114">инструкции касательно того, какие процессы должны выполняться Docker.</span><span class="sxs-lookup"><span data-stu-id="f1b64-114">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="f1b64-115">Рабочий процесс внутреннего цикла разработки на основе Docker можно настроить как процесс (как описано в следующем разделе).</span><span class="sxs-lookup"><span data-stu-id="f1b64-115">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="f1b64-116">Учтите, что начальные этапы настройки среды здесь не рассматриваются, так как они выполняются только один раз.</span><span class="sxs-lookup"><span data-stu-id="f1b64-116">Consider that the initial steps to set up the environment are not included, because you only need to do it once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="f1b64-117">Создание одного приложения в контейнере Docker с помощью Visual Studio Code и интерфейса командной строки (CLI) Docker</span><span class="sxs-lookup"><span data-stu-id="f1b64-117">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="f1b64-118">Приложение состоит из ваших собственных служб и дополнительных библиотек (зависимостей).</span><span class="sxs-lookup"><span data-stu-id="f1b64-118">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="f1b64-119">На рис. 4-22 показаны основные шаги, которые обычно необходимо выполнить при сборке приложения Docker, после чего приводится подробное описание каждого из них.</span><span class="sxs-lookup"><span data-stu-id="f1b64-119">Figure 4-22 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![Схема, на которой показаны семь шагов, необходимых для создания контейнерного приложения.](./media/docker-apps-inner-loop-workflow/life-cycle-containerized-apps-docker-cli.png)

<span data-ttu-id="f1b64-121">**Рис. 4-22**.</span><span class="sxs-lookup"><span data-stu-id="f1b64-121">**Figure 4-22**.</span></span> <span data-ttu-id="f1b64-122">Высокоуровневое представление рабочего процесса для жизненного цикла контейнерных приложений Docker, создаваемых с помощью CLI Docker</span><span class="sxs-lookup"><span data-stu-id="f1b64-122">High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="f1b64-123">Шаг 1. Начало программирования в Visual Studio Code и создание первого приложения или базовой службы</span><span class="sxs-lookup"><span data-stu-id="f1b64-123">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="f1b64-124">Разработка приложения Docker аналогична разработке приложения без Docker.</span><span class="sxs-lookup"><span data-stu-id="f1b64-124">The way you develop your application is similar to the way you do it without Docker.</span></span> <span data-ttu-id="f1b64-125">Разница заключается в том, что при разработке развертывание и тестирование приложения или служб, работающих в контейнерах Docker, выполняется в локальной среде (например, в Windows или виртуальной машине Linux).</span><span class="sxs-lookup"><span data-stu-id="f1b64-125">The difference is that while developing, you're deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="f1b64-126">**Настройка локальной среды**</span><span class="sxs-lookup"><span data-stu-id="f1b64-126">**Setting up your local environment**</span></span>

<span data-ttu-id="f1b64-127">С помощью последних версий Docker для Mac и Windows разрабатывать приложения Docker стало еще легче. Настройка очень проста.</span><span class="sxs-lookup"><span data-stu-id="f1b64-127">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

> [!TIP]
> <span data-ttu-id="f1b64-128">Инструкции по настройке Docker для Windows см. на странице <https://docs.docker.com/docker-for-windows/>.</span><span class="sxs-lookup"><span data-stu-id="f1b64-128">For instructions on setting up Docker for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>
>
><span data-ttu-id="f1b64-129">Инструкции по настройке Docker для Mac см. на странице <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="f1b64-129">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="f1b64-130">Кроме того, вам потребуется редактор кода для разработки приложения с помощью CLI Docker.</span><span class="sxs-lookup"><span data-stu-id="f1b64-130">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="f1b64-131">Корпорация Майкрософт предлагает Visual Studio Code, простой редактор кода, который поддерживается в macOS, Windows и Linux. Он предоставляет технологию IntelliSense с [поддержкой множества языков](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python и большинства современных языков), возможность [отладки](https://code.visualstudio.com/Docs/editor/debugging), [интеграцию с Git](https://code.visualstudio.com/Docs/editor/versioncontrol) и [поддержку расширений](https://code.visualstudio.com/docs/extensions/overview).</span><span class="sxs-lookup"><span data-stu-id="f1b64-131">Microsoft provides Visual Studio Code, which is a lightweight code editor that's supported on Windows, Linux, and macOS, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="f1b64-132">Это средство отлично подойдет разработчикам, использующим macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="f1b64-132">This editor is a great fit for macOS and Linux developers.</span></span> <span data-ttu-id="f1b64-133">В Windows также можно использовать Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f1b64-133">In Windows, you also can use Visual Studio.</span></span>

> [!TIP]
> <span data-ttu-id="f1b64-134">Инструкции по установке Visual Studio Code для Windows, macOS или Linux см. на странице <https://code.visualstudio.com/docs/setup/setup-overview/>.</span><span class="sxs-lookup"><span data-stu-id="f1b64-134">For instructions on installing Visual Studio Code for Windows, Linux, or macOS, go to <https://code.visualstudio.com/docs/setup/setup-overview/>.</span></span>
>
> <span data-ttu-id="f1b64-135">Инструкции по настройке Docker для Mac см. на странице <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="f1b64-135">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="f1b64-136">Вы можете использовать CLI Docker и писать код в любом редакторе кода, однако Visual Studio Code в сочетании с расширением Docker упрощает создание файлов `Dockerfile` и `docker-compose.yml`.</span><span class="sxs-lookup"><span data-stu-id="f1b64-136">You can work with Docker CLI and write your code using any code editor, but using Visual Studio Code with the Docker extension makes it easy to author `Dockerfile` and `docker-compose.yml` files in your workspace.</span></span> <span data-ttu-id="f1b64-137">Вы также можете выполнять задачи и скрипты из интегрированной среды разработки Visual Studio Code для выполнения команд Docker на базе CLI Docker.</span><span class="sxs-lookup"><span data-stu-id="f1b64-137">You can also run tasks and scripts from the Visual Studio Code IDE to execute Docker commands using the Docker CLI underneath.</span></span>

<span data-ttu-id="f1b64-138">Расширение Docker для VS Code предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="f1b64-138">The Docker extension for VS Code provides the following features:</span></span>

- <span data-ttu-id="f1b64-139">автоматическое создание файлов `Dockerfile` и `docker-compose.yml`;</span><span class="sxs-lookup"><span data-stu-id="f1b64-139">Automatic `Dockerfile` and `docker-compose.yml` file generation</span></span>

- <span data-ttu-id="f1b64-140">выделение синтаксических конструкций и подсказки при наведении для файлов `docker-compose.yml` и `Dockerfile`;</span><span class="sxs-lookup"><span data-stu-id="f1b64-140">Syntax highlighting and hover tips for `docker-compose.yml` and `Dockerfile` files</span></span>

- <span data-ttu-id="f1b64-141">IntelliSense (варианты завершения) для файлов `Dockerfile` и `docker-compose.yml`;</span><span class="sxs-lookup"><span data-stu-id="f1b64-141">IntelliSense (completions) for `Dockerfile` and `docker-compose.yml` files</span></span>

- <span data-ttu-id="f1b64-142">статический анализ кода (ошибки и предупреждения) для файлов `Dockerfile`;</span><span class="sxs-lookup"><span data-stu-id="f1b64-142">Linting (errors and warnings) for `Dockerfile` files</span></span>

- <span data-ttu-id="f1b64-143">интеграция палитры команд (F1) с наиболее часто используемыми командами Docker;</span><span class="sxs-lookup"><span data-stu-id="f1b64-143">Command Palette (F1) integration for the most common Docker commands</span></span>

- <span data-ttu-id="f1b64-144">интеграция в обозреватель для управления образами и контейнерами;</span><span class="sxs-lookup"><span data-stu-id="f1b64-144">Explorer integration for managing Images and Containers</span></span>

- <span data-ttu-id="f1b64-145">развертывание образов из DockerHub и реестров контейнеров Azure в службе приложений Azure.</span><span class="sxs-lookup"><span data-stu-id="f1b64-145">Deploy images from DockerHub and Azure Container Registries to Azure App Service</span></span>

<span data-ttu-id="f1b64-146">Чтобы установить расширение Docker, нажмите клавиши CTRL+SHIFT+P, введите `ext install` и выполните команду "Установить расширение", чтобы открыть список расширений в Marketplace.</span><span class="sxs-lookup"><span data-stu-id="f1b64-146">To install the Docker extension, press Ctrl+Shift+P, type `ext install`, and then run the Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="f1b64-147">Затем введите **docker**, чтобы отфильтровать результаты, и выберите расширение поддержки Docker, как показано на рис. 4-23.</span><span class="sxs-lookup"><span data-stu-id="f1b64-147">Next, type **docker** to filter the results, and then select the Docker Support extension, as depicted in Figure 4-23.</span></span>

![Расширение Docker для VS Code.](./media/docker-apps-inner-loop-workflow/install-docker-extension-vs-code.png)

<span data-ttu-id="f1b64-149">**Рис. 4-23**.</span><span class="sxs-lookup"><span data-stu-id="f1b64-149">**Figure 4-23**.</span></span> <span data-ttu-id="f1b64-150">Установка расширения Docker в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f1b64-150">Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="f1b64-151">Шаг 2. Создание файла Dockerfile, связанного с существующим образом (обычная ОС или среды разработки, такие как .NET Core, Node.js и Ruby)</span><span class="sxs-lookup"><span data-stu-id="f1b64-151">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="f1b64-152">Для каждого собираемого образа и каждого развертываемого контейнера требуется файл `DockerFile`.</span><span class="sxs-lookup"><span data-stu-id="f1b64-152">You'll need a `DockerFile` per custom image to be built and per container to be deployed.</span></span> <span data-ttu-id="f1b64-153">Если в приложении имеется только одна пользовательская служба, необходим один файл `DockerFile`.</span><span class="sxs-lookup"><span data-stu-id="f1b64-153">If your app is made up of a single custom service, you'll need a single `DockerFile`.</span></span> <span data-ttu-id="f1b64-154">Но если приложение состоит из нескольких служб (как в архитектуре на основе микрослужб), потребуется по одному файлу `Dockerfile` для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="f1b64-154">But if your app is composed of multiple services (as in a microservices architecture), you'll need one `Dockerfile` per service.</span></span>

<span data-ttu-id="f1b64-155">Файл `DockerFile` обычно находится в корневой папке приложения или службы и содержит команды, которые требуются Docker для настройки и запуска приложения или службы.</span><span class="sxs-lookup"><span data-stu-id="f1b64-155">The `DockerFile` is commonly placed in the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="f1b64-156">Вы можете создать файл `DockerFile` самостоятельно и добавить его в проект вместе с кодом (node.js, .NET Core и т. д.) или, если у вас нет опыта работы со средой, воспользоваться приведенным ниже советом.</span><span class="sxs-lookup"><span data-stu-id="f1b64-156">You can create your `DockerFile` and add it to your project along with your code (node.js, .NET Core, etc.), or, if you're new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
> <span data-ttu-id="f1b64-157">При использовании файлов `Dockerfile` и `docker-compose.yml`, связанных с контейнерами Docker, можно следовать указаниям, которые предоставляются расширением Docker.</span><span class="sxs-lookup"><span data-stu-id="f1b64-157">You can use the Docker extension to guide you when using the `Dockerfile` and `docker-compose.yml` files related to your Docker containers.</span></span> <span data-ttu-id="f1b64-158">Вероятно, в дальнейшем вы будете создавать эти файлы, не прибегая к помощи данного средства, но поначалу оно позволяет ускорить обучение.</span><span class="sxs-lookup"><span data-stu-id="f1b64-158">Eventually, you'll probably write these kinds of files without this tool, but using the Docker extension is a good starting point that will accelerate your learning curve.</span></span>

<span data-ttu-id="f1b64-159">На рисунке 4-24 показано, как добавляется файл docker-compose с помощью расширения Docker для VS Code.</span><span class="sxs-lookup"><span data-stu-id="f1b64-159">In Figure 4-24, you can see how a docker-compose file is added by using the Docker Extension for VS Code.</span></span>

![Консоль расширения Docker для VS Code.](./media/docker-apps-inner-loop-workflow/add-docker-files-to-workspace-command.png)

<span data-ttu-id="f1b64-161">**Рис. 4-24**.</span><span class="sxs-lookup"><span data-stu-id="f1b64-161">**Figure 4-24**.</span></span> <span data-ttu-id="f1b64-162">Добавление файлов Docker с помощью **команды добавления файлов Docker в рабочую область**</span><span class="sxs-lookup"><span data-stu-id="f1b64-162">Docker files added using the **Add Docker files to Workspace command**</span></span>

<span data-ttu-id="f1b64-163">При добавлении файла Dockerfile указывается базовый образ Docker, который необходимо использовать (например, `FROM mcr.microsoft.com/dotnet/core/aspnet`).</span><span class="sxs-lookup"><span data-stu-id="f1b64-163">When you add a DockerFile, you specify what base Docker image you’ll be using (like using `FROM mcr.microsoft.com/dotnet/core/aspnet`).</span></span> <span data-ttu-id="f1b64-164">Обычно пользовательский образ создается на основе базового образа, полученного из официального репозитория в [реестре Docker Hub](https://hub.docker.com/) (например, [образа для .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) или [Node.js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="f1b64-164">You'll usually build your custom image on top of a base image that you get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) or the one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="f1b64-165">***Использование существующего официального образа Docker***</span><span class="sxs-lookup"><span data-stu-id="f1b64-165">***Use an existing official Docker image***</span></span>

<span data-ttu-id="f1b64-166">Использование официального репозитория стека языка с номером версии гарантирует, что на всех компьютерах (включая компьютеры для разработки, тестирования и работы) будут доступны одни и те же функции языка.</span><span class="sxs-lookup"><span data-stu-id="f1b64-166">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="f1b64-167">Вот пример файла Dockerfile для контейнера .NET Core:</span><span class="sxs-lookup"><span data-stu-id="f1b64-167">The following is a sample DockerFile for a .NET Core container:</span></span>

```Dockerfile
# Base Docker image to use  
FROM mcr.microsoft.com/dotnet/core/aspnet:2.2
  
# Set the Working Directory and files to be copied to the image  
ARG source  
WORKDIR /app  
COPY ${source:-bin/Release/PublishOutput} .  
  
# Configure the listening port to 80 (Internal/Secured port within Docker host)  
EXPOSE 80  
  
# Application entry point  
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

<span data-ttu-id="f1b64-168">В этом случае образ основан на версии 2.2 официального образа Docker ASP.NET Core (мультиархитектурного, для Linux и Windows), что следует из строки `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2`.</span><span class="sxs-lookup"><span data-stu-id="f1b64-168">In this case, the image is based on version 2.2 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows), as per the line `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2`.</span></span> <span data-ttu-id="f1b64-169">(Дополнительные сведения по этой теме см. на страницах [Образ Docker ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) и [Образ Docker .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/).)</span><span class="sxs-lookup"><span data-stu-id="f1b64-169">(For more information about this topic, see the [ASP.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) page and the [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) page).</span></span>

<span data-ttu-id="f1b64-170">Кроме того, в файле Dockerfile можно указать, что средство Docker должно прослушивать порт TCP, который будет использоваться во время выполнения (например, порт 80).</span><span class="sxs-lookup"><span data-stu-id="f1b64-170">In the DockerFile, you can also instruct Docker to listen to the TCP port that you'll use at runtime (such as port 80).</span></span>

<span data-ttu-id="f1b64-171">В Dockerfile можно задать дополнительные параметры конфигурации, в зависимости от используемого языка и платформы.</span><span class="sxs-lookup"><span data-stu-id="f1b64-171">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="f1b64-172">Например, строка `ENTRYPOINT` со значением `["dotnet", "MySingleContainerWebApp.dll"]` указывает Docker запускать приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f1b64-172">For instance, the `ENTRYPOINT` line with `["dotnet", "MySingleContainerWebApp.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="f1b64-173">Если для создания и запуска приложения .NET используется пакет SDK и .NET Core CLI (`dotnet CLI`), этот параметр будет другим.</span><span class="sxs-lookup"><span data-stu-id="f1b64-173">If you're using the SDK and the .NET Core CLI (`dotnet CLI`) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="f1b64-174">Ключевой момент здесь заключается в том, что строка ENTRYPOINT и другие параметры зависят от языка и платформы, выбранных для приложения.</span><span class="sxs-lookup"><span data-stu-id="f1b64-174">The key point here is that the ENTRYPOINT line and other settings depend on the language and platform you choose for your application.</span></span>

> [!TIP]
> <span data-ttu-id="f1b64-175">Дополнительные сведения о создании образов Docker для приложений .NET Core см. на странице <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span><span class="sxs-lookup"><span data-stu-id="f1b64-175">For more information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>
>
> <span data-ttu-id="f1b64-176">Дополнительные сведения о создании собственных образов см. на странице <https://docs.docker.com/engine/tutorials/dockerimages/>.</span><span class="sxs-lookup"><span data-stu-id="f1b64-176">To learn more about building your own images, go to <https://docs.docker.com/engine/tutorials/dockerimages/>.</span></span>

<span data-ttu-id="f1b64-177">**Использование репозиториев мультиархитектурных образов**</span><span class="sxs-lookup"><span data-stu-id="f1b64-177">**Use multi-arch image repositories**</span></span>

<span data-ttu-id="f1b64-178">В репозитории могут содержаться варианты одного и того же образа для разных платформ, например образ Linux и образ Windows.</span><span class="sxs-lookup"><span data-stu-id="f1b64-178">A single image name in a repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="f1b64-179">Это позволяет поставщикам, таким как Майкрософт, которые создают базовые образы, создать один репозиторий для охвата нескольких платформ (т. е. Windows и Linux).</span><span class="sxs-lookup"><span data-stu-id="f1b64-179">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is, Linux and Windows).</span></span> <span data-ttu-id="f1b64-180">Например, репозиторий [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) в реестре Docker Hub обеспечивает поддержку Linux и Windows Nano Server при использовании одного и того же имени образа.</span><span class="sxs-lookup"><span data-stu-id="f1b64-180">For example, the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same image name.</span></span>

<span data-ttu-id="f1b64-181">При запросе образа [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) с узла Windows извлекается вариант для Windows, а при запросе образа с тем же именем с узла Linux — вариант для Linux.</span><span class="sxs-lookup"><span data-stu-id="f1b64-181">Pulling the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) image from a Windows host pulls the Windows variant, whereas pulling the same image name from a Linux host pulls the Linux variant.</span></span>

<span data-ttu-id="f1b64-182">***Создание базового образа с нуля***</span><span class="sxs-lookup"><span data-stu-id="f1b64-182">***Create your base image from scratch***</span></span>

<span data-ttu-id="f1b64-183">Вы можете создать собственный базовый образ Docker с нуля, как описано в этой [статье](https://docs.docker.com/engine/userguide/eng-image/baseimages/).</span><span class="sxs-lookup"><span data-stu-id="f1b64-183">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="f1b64-184">Этот сценарий, вероятно, будет не самым лучшим для тех, кто только начинает работать с Docker, но если вы хотите задать определенные биты базового образа, это можно сделать.</span><span class="sxs-lookup"><span data-stu-id="f1b64-184">This scenario is probably not the best for you if you're just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="f1b64-185">Шаг 3. Создание пользовательских образов Docker и внедрение в них собственных служб</span><span class="sxs-lookup"><span data-stu-id="f1b64-185">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="f1b64-186">Для каждой пользовательской службы в приложении необходимо создать связанный образ.</span><span class="sxs-lookup"><span data-stu-id="f1b64-186">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="f1b64-187">Если приложение состоит из одной службы или веб-приложения, достаточно одного образа.</span><span class="sxs-lookup"><span data-stu-id="f1b64-187">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
> <span data-ttu-id="f1b64-188">В рамках "рабочего процесса внешнего цикла DevOps" образы создаются автоматическим процессом сборки при отправке исходного кода в репозиторий Git (непрерывная интеграция), поэтому образы будут создаваться в этой глобальной среде из вашего исходного кода.</span><span class="sxs-lookup"><span data-stu-id="f1b64-188">When taking into account the "outer-loop DevOps workflow", the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration), so the images will be created in that global environment from your source code.</span></span>
>
> <span data-ttu-id="f1b64-189">Однако перед переходом к этому внешнему циклу необходимо убедиться в том, что приложение Docker действительно работает правильно, чтобы в систему управления версиями (Git и т. д.) не передавался неправильно работающий код.</span><span class="sxs-lookup"><span data-stu-id="f1b64-189">But before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>
>
> <span data-ttu-id="f1b64-190">Поэтому каждый разработчик должен вначале полностью выполнить внутренний цикл, чтобы провести тестирование локально, прежде чем отправлять в систему управления версиями полностью готовую функцию или изменение.</span><span class="sxs-lookup"><span data-stu-id="f1b64-190">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="f1b64-191">Чтобы создать образ в локальной среде с помощью Dockerfile, можно использовать команду docker build, как показано на рисунке 4-25 (для приложений, состоящих из нескольких контейнеров или служб, можно также выполнить команду `docker-compose up --build`).</span><span class="sxs-lookup"><span data-stu-id="f1b64-191">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-25 (you also can run `docker-compose up --build` for applications composed by several containers/services).</span></span>

![Снимок экрана, показывающий выходные данные команды docker build в консоли.](./media/docker-apps-inner-loop-workflow/run-docker-build-command.png)

<span data-ttu-id="f1b64-193">**Рис. 4-25**.</span><span class="sxs-lookup"><span data-stu-id="f1b64-193">**Figure 4-25**.</span></span> <span data-ttu-id="f1b64-194">Выполнение команды docker build</span><span class="sxs-lookup"><span data-stu-id="f1b64-194">Running docker build</span></span>

<span data-ttu-id="f1b64-195">При необходимости вместо непосредственного выполнения команды `docker build` из папки проекта можно сначала создать развертываемую папку с нужными библиотеками .NET, выполнив команду `dotnet publish`, а затем использовать команду `docker build`.</span><span class="sxs-lookup"><span data-stu-id="f1b64-195">Optionally, instead of directly running `docker build` from the project folder, you first can generate a deployable folder with the .NET libraries needed by using the run `dotnet publish` command, and then run `docker build`.</span></span>

<span data-ttu-id="f1b64-196">В этом примере создается образ Docker с именем `cesardl/netcore-webapi-microservice-docker:first` (`:first` — это тег, например определенная версия).</span><span class="sxs-lookup"><span data-stu-id="f1b64-196">This example creates a Docker image with the name `cesardl/netcore-webapi-microservice-docker:first` (`:first` is a tag, like a specific version).</span></span> <span data-ttu-id="f1b64-197">Этот шаг можно выполнить для каждого пользовательского образа, который требуется создать для составного приложения Docker с несколькими контейнерами.</span><span class="sxs-lookup"><span data-stu-id="f1b64-197">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="f1b64-198">Вы можете найти образы, имеющиеся в локальном репозитории (на компьютере разработки), с помощью команды docker images, как показано на рисунке 4-26.</span><span class="sxs-lookup"><span data-stu-id="f1b64-198">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-26.</span></span>

![Выходные данные команды docker images в консоли со списком существующих образов.](./media/docker-apps-inner-loop-workflow/view-existing-images-with-docker-images.png)

<span data-ttu-id="f1b64-200">**Рис. 4-26**.</span><span class="sxs-lookup"><span data-stu-id="f1b64-200">**Figure 4-26**.</span></span> <span data-ttu-id="f1b64-201">Просмотр существующих образов с помощью команды docker images</span><span class="sxs-lookup"><span data-stu-id="f1b64-201">Viewing existing images using docker images</span></span>

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="f1b64-202">Шаг 4. Определение служб в файле docker-compose.yml при сборке составного приложения Docker с несколькими службами</span><span class="sxs-lookup"><span data-stu-id="f1b64-202">Step 4: Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="f1b64-203">В файле `docker-compose.yml` можно задать ряд связанных служб для развертывания в качестве составного приложения с помощью команд развертывания, описанных в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="f1b64-203">With the `docker-compose.yml` file, you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="f1b64-204">Создайте этот файл в основной или корневой папке решения. Его содержимое должно быть аналогично приведенному в следующем файле `docker-compose.yml`:</span><span class="sxs-lookup"><span data-stu-id="f1b64-204">Create that file in your main or root solution folder; it should have content similar to that shown in this `docker-compose.yml` file:</span></span>

```yml
version: '3.4'
services:
  web:
    build: .
    ports:
     - "81:80"
    volumes:
     - .:/code
    depends_on:
     - redis
  redis:
    image: redis
```

<span data-ttu-id="f1b64-205">В данном случае в этом файле определены две службы: веб-служба (ваша пользовательская служба) и служба Redis (популярная служба кэширования).</span><span class="sxs-lookup"><span data-stu-id="f1b64-205">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="f1b64-206">Каждая служба развертывается как контейнер, поэтому для каждой из них требуется определенный образ Docker.</span><span class="sxs-lookup"><span data-stu-id="f1b64-206">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="f1b64-207">Для данной веб-службы образ должен выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f1b64-207">For this particular web service, the image will need to do the following:</span></span>

- <span data-ttu-id="f1b64-208">выполнять сборку из файла Dockerfile в текущем каталоге;</span><span class="sxs-lookup"><span data-stu-id="f1b64-208">Build from the DockerFile in the current directory</span></span>

- <span data-ttu-id="f1b64-209">переадресовывать предоставленный порт 80 в контейнере на внешний порт 81 на компьютере узла;</span><span class="sxs-lookup"><span data-stu-id="f1b64-209">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

- <span data-ttu-id="f1b64-210">подключать каталог проекта в узле к /code в контейнере, чтобы код можно было изменять, не перестраивая образ;</span><span class="sxs-lookup"><span data-stu-id="f1b64-210">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

- <span data-ttu-id="f1b64-211">связывать веб-службу со службой Redis.</span><span class="sxs-lookup"><span data-stu-id="f1b64-211">Link the web service to the redis service</span></span>

<span data-ttu-id="f1b64-212">Служба Redis использует [последний общедоступный образ Redis](https://hub.docker.com/_/redis/), извлеченный из реестра Docker Hub.</span><span class="sxs-lookup"><span data-stu-id="f1b64-212">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="f1b64-213">[Redis](https://redis.io/) — это популярная система кэширования для серверных приложений.</span><span class="sxs-lookup"><span data-stu-id="f1b64-213">[redis](https://redis.io/) is a popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="f1b64-214">Шаг 5. Сборка и запуск приложения Docker</span><span class="sxs-lookup"><span data-stu-id="f1b64-214">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="f1b64-215">Если в приложении имеется только один контейнер, его можно запустить путем развертывания на узле Docker (в виртуальной машине или на физическом сервере).</span><span class="sxs-lookup"><span data-stu-id="f1b64-215">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="f1b64-216">Однако если приложение состоит из нескольких служб, его также необходимо *скомпоновать*.</span><span class="sxs-lookup"><span data-stu-id="f1b64-216">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="f1b64-217">Давайте рассмотрим разные варианты.</span><span class="sxs-lookup"><span data-stu-id="f1b64-217">Let's see the different options.</span></span>

<span data-ttu-id="f1b64-218">***Вариант А. Запуск одного контейнера или службы***</span><span class="sxs-lookup"><span data-stu-id="f1b64-218">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="f1b64-219">Образ Docker можно запустить с помощью команды docker run, как показано в этом примере:</span><span class="sxs-lookup"><span data-stu-id="f1b64-219">You can run the Docker image by using the docker run command, as shown here:</span></span>

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="f1b64-220">В случае с этим развертыванием запросы, отправляемые на порт 80, перенаправляются на внутренний порт 5000.</span><span class="sxs-lookup"><span data-stu-id="f1b64-220">For this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="f1b64-221">Теперь приложение ожидает передачи данных через внешний порт 80 на уровне узла.</span><span class="sxs-lookup"><span data-stu-id="f1b64-221">Now the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="f1b64-222">***Вариант Б. Компоновка и запуск многоконтейнерного приложения***</span><span class="sxs-lookup"><span data-stu-id="f1b64-222">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="f1b64-223">В большинстве корпоративных сценариев приложение Docker будет состоять из нескольких служб.</span><span class="sxs-lookup"><span data-stu-id="f1b64-223">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="f1b64-224">В таких случаях можно выполнить команду `docker-compose up` (рис. 4-27), которая использует ранее созданный файл docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="f1b64-224">For these cases, you can run the `docker-compose up` command (Figure 4-27), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="f1b64-225">В результате ее выполнения развертывается скомпонованное приложение со всеми связанными контейнерами.</span><span class="sxs-lookup"><span data-stu-id="f1b64-225">Running this command deploys a composed application with all of its related containers.</span></span>

![Выходные данные команды docker-compose up в консоли.](./media/docker-apps-inner-loop-workflow/results-docker-compose-up.png)

<span data-ttu-id="f1b64-227">**Рис. 4-27**.</span><span class="sxs-lookup"><span data-stu-id="f1b64-227">**Figure 4-27**.</span></span> <span data-ttu-id="f1b64-228">Результаты выполнения команды docker-compose up</span><span class="sxs-lookup"><span data-stu-id="f1b64-228">Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="f1b64-229">После выполнения команды `docker-compose up` приложение и связанные с ним контейнеры развертываются в узле Docker, как показано в представлении виртуальной машины на рисунке 4-28.</span><span class="sxs-lookup"><span data-stu-id="f1b64-229">After you run `docker-compose up`, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-28, in the VM representation.</span></span>

![Виртуальная машина, в которой выполняются многоконтейнерные приложения.](./media/docker-apps-inner-loop-workflow/vm-with-docker-containers-deployed.png)

<span data-ttu-id="f1b64-231">**Рис. 4-28**.</span><span class="sxs-lookup"><span data-stu-id="f1b64-231">**Figure 4-28**.</span></span> <span data-ttu-id="f1b64-232">Виртуальная машина с развернутыми контейнерами Docker</span><span class="sxs-lookup"><span data-stu-id="f1b64-232">VM with Docker containers deployed</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="f1b64-233">Шаг 6. Тестирование приложения Docker (в локальной виртуальной машине для непрерывного развертывания)</span><span class="sxs-lookup"><span data-stu-id="f1b64-233">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="f1b64-234">Этот шаг будет зависеть от того, что делает ваше приложение.</span><span class="sxs-lookup"><span data-stu-id="f1b64-234">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="f1b64-235">В случае простого веб-API Hello World на основе .NET Core, развернутого в виде единственного контейнера или службы, для доступа к службе достаточно указать TCP-порт из файла Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="f1b64-235">In a simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="f1b64-236">Если localhost не включен, то для перехода к службе определите IP-адрес компьютера с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="f1b64-236">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

```console
docker-machine {IP} {YOUR-CONTAINER-NAME}
```

<span data-ttu-id="f1b64-237">В узле Docker откройте браузер и перейдите на этот сайт. Вы должны увидеть работающее приложение или службу, как показано на рисунке 4-29.</span><span class="sxs-lookup"><span data-stu-id="f1b64-237">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-29.</span></span>

![Ответ от localhost/API/values в браузере.](./media/docker-apps-inner-loop-workflow/test-docker-app-locally-localhost.png)

<span data-ttu-id="f1b64-239">**Рис. 4-29**.</span><span class="sxs-lookup"><span data-stu-id="f1b64-239">**Figure 4-29**.</span></span> <span data-ttu-id="f1b64-240">Локальное тестирование приложения Docker с помощью localhost</span><span class="sxs-lookup"><span data-stu-id="f1b64-240">Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="f1b64-241">Обратите внимание на то, что используется порт 80, однако внутренние запросы перенаправляются на порт 5000, поскольку именно так было выполнено развертывание с помощью команды `docker run`, как описывалось ранее.</span><span class="sxs-lookup"><span data-stu-id="f1b64-241">Note that it's using port 80, but internally it's being redirected to port 5000, because that's how it was deployed with `docker run`, as explained earlier.</span></span>

<span data-ttu-id="f1b64-242">Вы можете выполнить тестирование с помощью команды CURL из терминала.</span><span class="sxs-lookup"><span data-stu-id="f1b64-242">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="f1b64-243">Для Docker в Windows IP-адресом по умолчанию является 10.0.75.1, как показано на рисунке 4-30.</span><span class="sxs-lookup"><span data-stu-id="f1b64-243">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-30.</span></span>

![Выходные данные команды curl, выполненной применительно к http://10.0.75.1/API/values, в консоли](./media/docker-apps-inner-loop-workflow/test-docker-app-locally-curl.png)

<span data-ttu-id="f1b64-245">**Рис. 4-30**.</span><span class="sxs-lookup"><span data-stu-id="f1b64-245">**Figure 4-30**.</span></span> <span data-ttu-id="f1b64-246">Локальное тестирование приложения Docker с помощью CURL</span><span class="sxs-lookup"><span data-stu-id="f1b64-246">Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="f1b64-247">**Отладка контейнера, запущенного в Docker**</span><span class="sxs-lookup"><span data-stu-id="f1b64-247">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="f1b64-248">Visual Studio Code поддерживает отладку Docker при использовании Node.js и других платформ, таких как контейнеры .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f1b64-248">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="f1b64-249">Вы также можете отлаживать контейнеры .NET Core или .NET Framework в Docker с помощью Visual Studio для Windows или Mac, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="f1b64-249">You also can debug .NET Core or .NET Framework containers in Docker when using Visual Studio for Windows or Mac, as described in the next section.</span></span>

> [!TIP]
> <span data-ttu-id="f1b64-250">См. сведения об <https://blog.docker.com/2016/07/live-debugging-docker/>отладке контейнеров Docker Node.js<https://docs.microsoft.com/archive/blogs/user_ed/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more>.</span><span class="sxs-lookup"><span data-stu-id="f1b64-250">To learn more about debugging Node.js Docker containers, see <https://blog.docker.com/2016/07/live-debugging-docker/> and <https://docs.microsoft.com/archive/blogs/user_ed/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more>.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f1b64-251">[Назад](docker-apps-development-environment.md)
>[Вперед](visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="f1b64-251">[Previous](docker-apps-development-environment.md)
[Next](visual-studio-tools-for-docker.md)</span></span>
