---
title: Рабочий процесс внутреннего цикла разработки для приложений Docker
description: Дополнительные сведения «внутреннем цикле» рабочего процесса для разработки приложений Docker.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 1ed0feeec682f5a79bc38db6a101b751ea4dbc3a
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57676672"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="72c89-103">Рабочий процесс внутреннего цикла разработки для приложений Docker</span><span class="sxs-lookup"><span data-stu-id="72c89-103">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="72c89-104">Перед запуском рабочего процесса внешний цикл, охватывающие весь DevOps цикл, все начинает на компьютере каждого разработчика, кодирования самого приложения, с помощью предпочитаемых языков или платформ и его локальному тестированию (рис. 4-21).</span><span class="sxs-lookup"><span data-stu-id="72c89-104">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-21).</span></span> <span data-ttu-id="72c89-105">Однако в любом случае, вам придется важный момент общее, независимо от того, какой язык, framework или платформ.</span><span class="sxs-lookup"><span data-stu-id="72c89-105">But in every case, you'll have an important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="72c89-106">В этом конкретного рабочего процесса вы всегда разработке и тестировании контейнеров Docker, а на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="72c89-106">In this specific workflow, you're always developing and testing Docker containers, but locally.</span></span>

![Шаг 1 - код/запуска/отладки](./media/image18.png)

<span data-ttu-id="72c89-108">**Рис. 4-21**.</span><span class="sxs-lookup"><span data-stu-id="72c89-108">**Figure 4-21**.</span></span> <span data-ttu-id="72c89-109">Внутренний цикл разработки контекста</span><span class="sxs-lookup"><span data-stu-id="72c89-109">Inner-loop development context</span></span>

<span data-ttu-id="72c89-110">Контейнер или экземпляр образа Docker будет содержать следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="72c89-110">The container or instance of a Docker image will contain these components:</span></span>

-   <span data-ttu-id="72c89-111">Выбранная операционная система (например, дистрибутив Linux или Windows)</span><span class="sxs-lookup"><span data-stu-id="72c89-111">An operating system selection (for example, a Linux distribution or Windows)</span></span>

- <span data-ttu-id="72c89-112">Файлы, добавленные разработчиком (например, двоичные файлы приложения)</span><span class="sxs-lookup"><span data-stu-id="72c89-112">Files added by the developer (for example, app binaries)</span></span>

-   <span data-ttu-id="72c89-113">Конфигурации (например, параметры среды и зависимости)</span><span class="sxs-lookup"><span data-stu-id="72c89-113">Configuration (for example, environment settings and dependencies)</span></span>

- <span data-ttu-id="72c89-114">Инструкции для того, какие процессы с Docker</span><span class="sxs-lookup"><span data-stu-id="72c89-114">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="72c89-115">Можно настроить рабочий процесс внутреннего цикла разработки, который использует Docker, процесс (см. в следующем разделе).</span><span class="sxs-lookup"><span data-stu-id="72c89-115">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="72c89-116">Рассмотрим начальные действия по настройке среды не включены, так как вам нужно сделать всего один раз.</span><span class="sxs-lookup"><span data-stu-id="72c89-116">Consider that the initial steps to set up the environment are not included, because you only need to do it once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="72c89-117">Создание одного приложения в контейнере Docker, с помощью Visual Studio Code и Docker CLI</span><span class="sxs-lookup"><span data-stu-id="72c89-117">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="72c89-118">Приложения, состоящего из ваших собственных служб и дополнительных библиотек (зависимостей).</span><span class="sxs-lookup"><span data-stu-id="72c89-118">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="72c89-119">Рис. 4-22 показывает основные шаги, которые обычно требуется выполнить при создании приложения Docker, следуют подробное описание каждого шага.</span><span class="sxs-lookup"><span data-stu-id="72c89-119">Figure 4-22 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![Обзор рабочего процесса: Шаг 1 - кода, шаг 2 - писать файлы Dockerfile, шаг 3 - Создание образов, определенные с помощью файлов Dockerfile, шаг 4 - определение служб с помощью файла docker-Compose, шаг 5 - запуск контейнеров или составными приложениями, шаг 6 - тестирование приложений, шаг 7 - Push начать внешний цикл (конвейеров CI/CD) или продолжить de созданию.](./media/image19.png)

<span data-ttu-id="72c89-121">**Рис. 4-22**.</span><span class="sxs-lookup"><span data-stu-id="72c89-121">**Figure 4-22**.</span></span> <span data-ttu-id="72c89-122">Высокоуровневый рабочий процесс для жизненного цикла для Docker контейнерных приложений с помощью интерфейса командной строки Docker</span><span class="sxs-lookup"><span data-stu-id="72c89-122">High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="72c89-123">Шаг 1. Приступаем к написанию кода в Visual Studio Code и создания начальной приложения или услуги базовых показателей</span><span class="sxs-lookup"><span data-stu-id="72c89-123">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="72c89-124">Способ, при разработке приложения похоже на способ сделать это без Docker.</span><span class="sxs-lookup"><span data-stu-id="72c89-124">The way you develop your application is similar to the way you do it without Docker.</span></span> <span data-ttu-id="72c89-125">Разница в том, что при разработке, развертывание и тестирование приложения или службы, работающие в контейнеры Docker, размещенные в локальной среде (например, виртуальной Машины Linux или Windows).</span><span class="sxs-lookup"><span data-stu-id="72c89-125">The difference is that while developing, you're deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="72c89-126">**Настройка локальной среды**</span><span class="sxs-lookup"><span data-stu-id="72c89-126">**Setting up your local environment**</span></span>

<span data-ttu-id="72c89-127">Последние версии Docker для Mac и Windows проще, чем когда-либо для разработки приложений Docker и установки прямолинейна.</span><span class="sxs-lookup"><span data-stu-id="72c89-127">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

> [! СВЕДЕНИЯ]
>
> <span data-ttu-id="72c89-129">Инструкции по настройке Docker для Windows, см. в статье <https://docs.docker.com/docker-for-windows/>.</span><span class="sxs-lookup"><span data-stu-id="72c89-129">For instructions on setting up Docker for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>
>
><span data-ttu-id="72c89-130">Инструкции по настройке Docker для Mac, см. в статье <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="72c89-130">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="72c89-131">Кроме того потребуется редактор кода, чтобы фактически можно разрабатывать приложения при использовании интерфейса командной строки Docker.</span><span class="sxs-lookup"><span data-stu-id="72c89-131">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="72c89-132">Корпорация Майкрософт предоставляет Visual Studio Code, который представляет собой редактор небольшой объем кода, который поддерживается на Mac, Windows и Linux, а также предоставляет поддержку технологии IntelliSense с [поддержка множества языков](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python и большинство современные языки), [отладки](https://code.visualstudio.com/Docs/editor/debugging), [интеграция с Git](https://code.visualstudio.com/Docs/editor/versioncontrol) и [поддержке расширений](https://code.visualstudio.com/docs/extensions/overview).</span><span class="sxs-lookup"><span data-stu-id="72c89-132">Microsoft provides Visual Studio Code, which is a lightweight code editor that's supported on Mac, Windows, and Linux, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="72c89-133">Этот редактор — отлично подходит для разработчиков Mac и Linux.</span><span class="sxs-lookup"><span data-stu-id="72c89-133">This editor is a great fit for Mac and Linux developers.</span></span> <span data-ttu-id="72c89-134">В Windows также можно использовать полный приложения Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="72c89-134">In Windows, you also can use the full Visual Studio application.</span></span>

> [! СВЕДЕНИЯ]
>
> <span data-ttu-id="72c89-136">Инструкции по установке Visual Studio Code для Windows, Mac или Linux, см. в статье <https://code.visualstudio.com/docs/setup/setup-overview/>.</span><span class="sxs-lookup"><span data-stu-id="72c89-136">For instructions on installing Visual Studio Code for Windows, Mac, or Linux, go to <https://code.visualstudio.com/docs/setup/setup-overview/>.</span></span>
>
> <span data-ttu-id="72c89-137">Инструкции по настройке Docker для Mac, см. в статье <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="72c89-137">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="72c89-138">Можно работать с помощью Docker CLI и написать код, используя любой редактор кода, но с помощью Visual Studio Code с расширением Docker упрощает создание и настройка `Dockerfile` и `docker-compose.yml` файлов в рабочей области.</span><span class="sxs-lookup"><span data-stu-id="72c89-138">You can work with Docker CLI and write your code using any code editor, but using Visual Studio Code with the Docker extension makes it easy to author `Dockerfile` and `docker-compose.yml` files in your workspace.</span></span> <span data-ttu-id="72c89-139">Задачи и скрипты также можно запустить из Visual Studio IDE код для выполнения команды Docker, с помощью интерфейса командной строки Docker под.</span><span class="sxs-lookup"><span data-stu-id="72c89-139">You can also run tasks and scripts from the Visual Studio Code IDE to execute Docker commands using the Docker CLI underneath.</span></span>

<span data-ttu-id="72c89-140">Расширение Docker для VS Code предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="72c89-140">The Docker extension for VS Code provides the following features:</span></span>

- <span data-ttu-id="72c89-141">Автоматическое `Dockerfile` и `docker-compose.yml` файл поколения</span><span class="sxs-lookup"><span data-stu-id="72c89-141">Automatic `Dockerfile` and `docker-compose.yml` file generation</span></span>

- <span data-ttu-id="72c89-142">Советы по выделению и при наведении указателя мыши синтаксису для `docker-compose.yml` и `Dockerfile` файлов</span><span class="sxs-lookup"><span data-stu-id="72c89-142">Syntax highlighting and hover tips for `docker-compose.yml` and `Dockerfile` files</span></span>

- <span data-ttu-id="72c89-143">IntelliSense (завершений) для `Dockerfile` и `docker-compose.yml` файлов</span><span class="sxs-lookup"><span data-stu-id="72c89-143">IntelliSense (completions) for `Dockerfile` and `docker-compose.yml` files</span></span>

- <span data-ttu-id="72c89-144">Анализ кода (ошибки и предупреждения) для `Dockerfile` файлов</span><span class="sxs-lookup"><span data-stu-id="72c89-144">Linting (errors and warnings) for `Dockerfile` files</span></span>

- <span data-ttu-id="72c89-145">Команда интеграцию палитры (F1) для наиболее часто используемых команд Docker</span><span class="sxs-lookup"><span data-stu-id="72c89-145">Command Palette (F1) integration for the most common Docker commands</span></span>

- <span data-ttu-id="72c89-146">Интеграция обозревателя для управления образами и контейнерами</span><span class="sxs-lookup"><span data-stu-id="72c89-146">Explorer integration for managing Images and Containers</span></span>

- <span data-ttu-id="72c89-147">Развернуть образы из DockerHub и реестры контейнеров Azure в службе приложений Azure</span><span class="sxs-lookup"><span data-stu-id="72c89-147">Deploy images from DockerHub and Azure Container Registries to Azure App Service</span></span>

<span data-ttu-id="72c89-148">Чтобы установить расширение Docker, нажмите клавиши Ctrl + Shift + P, введите `ext install`, и выполните команду установить расширение, чтобы открыть список расширений Marketplace.</span><span class="sxs-lookup"><span data-stu-id="72c89-148">To install the Docker extension, press Ctrl+Shift+P, type `ext install`, and then run the Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="72c89-149">Затем введите **docker** для фильтрации результатов, а затем выберите модуль поддержки Docker, как показано на рис. 4-23.</span><span class="sxs-lookup"><span data-stu-id="72c89-149">Next, type **docker** to filter the results, and then select the Docker Support extension, as depicted in Figure 4-23.</span></span>

![Представление расширения Docker для VS Code.](./media/image20.png)

<span data-ttu-id="72c89-151">**Рис. 4-23**.</span><span class="sxs-lookup"><span data-stu-id="72c89-151">**Figure 4-23**.</span></span> <span data-ttu-id="72c89-152">Установка расширения Docker в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="72c89-152">Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="72c89-153">Шаг 2. Создание файла DockerFile, связанного с существующим образом (plain ОС или сред разработки, например .NET Core, Node.js и Ruby)</span><span class="sxs-lookup"><span data-stu-id="72c89-153">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="72c89-154">Вам потребуется `DockerFile` каждого пользовательского образа для построения и каждого контейнера должны быть развернуты.</span><span class="sxs-lookup"><span data-stu-id="72c89-154">You'll need a `DockerFile` per custom image to be built and per container to be deployed.</span></span> <span data-ttu-id="72c89-155">Если приложение состоит из единственный экземпляр пользовательской службы, вам потребуется один `DockerFile`.</span><span class="sxs-lookup"><span data-stu-id="72c89-155">If your app is made up of a single custom service, you'll need a single `DockerFile`.</span></span> <span data-ttu-id="72c89-156">Но если приложение состоит из нескольких служб (как в архитектуре микрослужб), вам понадобится `Dockerfile` каждой службы.</span><span class="sxs-lookup"><span data-stu-id="72c89-156">But if your app is composed of multiple services (as in a microservices architecture), you'll need one `Dockerfile` per service.</span></span>

<span data-ttu-id="72c89-157">`DockerFile` Обычно помещается в корневой папке приложения или службы и содержит необходимые команды, поэтому Docker знает, как установить и запустить приложения или службы.</span><span class="sxs-lookup"><span data-stu-id="72c89-157">The `DockerFile` is commonly placed in the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="72c89-158">Можно создать вашей `DockerFile` и добавьте его в проект, а также код (node.js, .NET Core, и т.д.), или, если вы новичок в среду, взгляните на следующий совет.</span><span class="sxs-lookup"><span data-stu-id="72c89-158">You can create your `DockerFile` and add it to your project along with your code (node.js, .NET Core, etc.), or, if you're new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
>
> <span data-ttu-id="72c89-159">Можно использовать расширения Docker помогут вам при использовании `Dockerfile` и `docker-compose.yml` файлы, связанные с Docker контейнеров.</span><span class="sxs-lookup"><span data-stu-id="72c89-159">You can use the Docker extension to guide you when using the `Dockerfile` and `docker-compose.yml` files related to your Docker containers.</span></span> <span data-ttu-id="72c89-160">В конечном счете скорее всего, вы будете писать таких файлов без это средство, но с помощью расширения Docker является хорошей отправной точкой, которая ускоряет изучение оболочки.</span><span class="sxs-lookup"><span data-stu-id="72c89-160">Eventually, you'll probably write these kinds of files without this tool, but using the Docker extension is a good starting point that will accelerate your learning curve.</span></span>

<span data-ttu-id="72c89-161">На рисунке 4-24, посмотрим, насколько docker-compose с помощью расширения Docker для VS Code добавляется файл.</span><span class="sxs-lookup"><span data-stu-id="72c89-161">In Figure 4-24, you can see how a docker-compose file is added by using the Docker Extension for VS Code.</span></span>

![Представление консоли расширения Docker для VS Code.](./media/image24.png)

<span data-ttu-id="72c89-163">**Рис. 4-24**.</span><span class="sxs-lookup"><span data-stu-id="72c89-163">**Figure 4-24**.</span></span> <span data-ttu-id="72c89-164">Файлы docker, добавленные с помощью **файлы Docker, добавьте к команде рабочей области**</span><span class="sxs-lookup"><span data-stu-id="72c89-164">Docker files added using the **Add Docker files to Workspace command**</span></span>

<span data-ttu-id="72c89-165">При добавлении файла DockerFile, указать, какой базовый образ Docker, вы будете использовать (например, использование `FROM microsoft/aspnetcore`).</span><span class="sxs-lookup"><span data-stu-id="72c89-165">When you add a DockerFile, you specify what base Docker image you’ll be using (like using `FROM microsoft/aspnetcore`).</span></span> <span data-ttu-id="72c89-166">Обычно вы создадите пользовательский образ на основе базового образа, которую можно получить из любой официального репозитория в [реестра Docker Hub](https://hub.docker.com/) (таких как [изображение для .NET Core](https://hub.docker.com/r/microsoft/dotnet/) или [для Node.js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="72c89-166">You'll usually build your custom image on top of a base image that you get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/r/microsoft/dotnet/) or the one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="72c89-167">***Использовать существующий официальный образ Docker***</span><span class="sxs-lookup"><span data-stu-id="72c89-167">***Use an existing official Docker image***</span></span>

<span data-ttu-id="72c89-168">Использование официального репозитория стек для языка с номером версии гарантирует, что те же функции языка доступны на всех компьютерах (включая разработки, тестирования и эксплуатации).</span><span class="sxs-lookup"><span data-stu-id="72c89-168">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="72c89-169">Ниже приведен пример DockerFile для контейнера .NET Core.</span><span class="sxs-lookup"><span data-stu-id="72c89-169">The following is a sample DockerFile for a .NET Core container:</span></span>

```Dockerfile
# Base Docker image to use  
FROM microsoft/dotnet:2.1-aspnetcore-runtime
  
# Set the Working Directory and files to be copied to the image  
ARG source  
WORKDIR /app  
COPY ${source:-bin/Release/PublishOutput} .  
  
# Configure the listening port to 80 (Internal/Secured port within Docker host)  
EXPOSE 80  
  
# Application entry point  
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

<span data-ttu-id="72c89-170">В этом случае образ основан на версии 2.1 официального образа ASP.NET Core Docker (мультиархитектурного для Linux и Windows), согласно строке `FROM microsoft/dotnet:2.1-aspnetcore-runtime`.</span><span class="sxs-lookup"><span data-stu-id="72c89-170">In this case, the image is based on version 2.1 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows), as per the line `FROM microsoft/dotnet:2.1-aspnetcore-runtime`.</span></span> <span data-ttu-id="72c89-171">(Дополнительные сведения об этом см. в разделе [образ Docker ASP.NET Core](https://hub.docker.com/r/microsoft/aspnetcore/) страницы и [образ Docker .NET Core](https://hub.docker.com/r/microsoft/dotnet/) страницы).</span><span class="sxs-lookup"><span data-stu-id="72c89-171">(For more information about this topic, see the [ASP.NET Core Docker Image](https://hub.docker.com/r/microsoft/aspnetcore/) page and the [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) page).</span></span>

<span data-ttu-id="72c89-172">В DockerFile можно также указать Docker прослушивать TCP-порт, который будет использоваться во время выполнения (например, порт 80).</span><span class="sxs-lookup"><span data-stu-id="72c89-172">In the DockerFile, you can also instruct Docker to listen to the TCP port that you'll use at runtime (such as port 80).</span></span>

<span data-ttu-id="72c89-173">В Dockerfile можно задать дополнительные параметры конфигурации, в зависимости от используемого языка и платформы.</span><span class="sxs-lookup"><span data-stu-id="72c89-173">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="72c89-174">Например `ENTRYPOINT` линия с пустым `["dotnet", "MySingleContainerWebApp.dll"]` указывает Docker запускать приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="72c89-174">For instance, the `ENTRYPOINT` line with `["dotnet", "MySingleContainerWebApp.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="72c89-175">Если вы используете пакет SDK и .NET Core CLI (`dotnet CLI`) для построения и запуска приложения .NET, этот параметр будет другим.</span><span class="sxs-lookup"><span data-stu-id="72c89-175">If you're using the SDK and the .NET Core CLI (`dotnet CLI`) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="72c89-176">Ключевой момент здесь является то, что ENTRYPOINT строки и другие параметры зависят от языка и платформы, выбранных для приложения.</span><span class="sxs-lookup"><span data-stu-id="72c89-176">The key point here is that the ENTRYPOINT line and other settings depend on the language and platform you choose for your application.</span></span>

> [! СВЕДЕНИЯ]
>
> <span data-ttu-id="72c89-178">Дополнительные сведения о создании образов Docker для приложений .NET Core, см. в статье <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span><span class="sxs-lookup"><span data-stu-id="72c89-178">For more information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>
>
> <span data-ttu-id="72c89-179">Дополнительные сведения о создании собственных образов, перейдите к <https://docs.docker.com/engine/tutorials/dockerimages/>.</span><span class="sxs-lookup"><span data-stu-id="72c89-179">To learn more about building your own images, go to <https://docs.docker.com/engine/tutorials/dockerimages/>.</span></span>

<span data-ttu-id="72c89-180">**Использование мультиархитектурных репозиториев**</span><span class="sxs-lookup"><span data-stu-id="72c89-180">**Use multi-arch image repositories**</span></span>

<span data-ttu-id="72c89-181">Имя одного образа в репозиторий может содержать варианты платформ, например образ Linux и образ Windows.</span><span class="sxs-lookup"><span data-stu-id="72c89-181">A single image name in a repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="72c89-182">Эта функция позволяет поставщиков, таких как Microsoft (creators базового образа) создать один репозиторий для охвата нескольких платформ (то есть, Linux и Windows).</span><span class="sxs-lookup"><span data-stu-id="72c89-182">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is, Linux and Windows).</span></span> <span data-ttu-id="72c89-183">Например [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) репозитория в реестре центра Docker обеспечивает поддержку для Linux и Windows Nano Server, используя то же имя образа.</span><span class="sxs-lookup"><span data-stu-id="72c89-183">For example, the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same image name.</span></span>

<span data-ttu-id="72c89-184">Извлечение [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) образа с узла Windows извлекает вариант Windows, тогда как извлекать имя образа из узла Linux извлекает вариант для Linux.</span><span class="sxs-lookup"><span data-stu-id="72c89-184">Pulling the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image from a Windows host pulls the Windows variant, whereas pulling the same image name from a Linux host pulls the Linux variant.</span></span>

<span data-ttu-id="72c89-185">***Создание базового образа с нуля***</span><span class="sxs-lookup"><span data-stu-id="72c89-185">***Create your base image from scratch***</span></span>

<span data-ttu-id="72c89-186">Можно создать свой собственный базовый образ Docker с нуля, описанные в этой [статье](https://docs.docker.com/engine/userguide/eng-image/baseimages/) из Docker.</span><span class="sxs-lookup"><span data-stu-id="72c89-186">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="72c89-187">Этот сценарий является скорее всего, не лучше подходит, если только вы начинаете с помощью Docker, но если вы хотите задать определенные биты базового образа, это можно сделать.</span><span class="sxs-lookup"><span data-stu-id="72c89-187">This scenario is probably not the best for you if you're just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="72c89-188">Шаг 3. Создание пользовательских образов Docker внедрения службы в нем</span><span class="sxs-lookup"><span data-stu-id="72c89-188">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="72c89-189">Для каждого пользовательского службы, которая состоит из приложения необходимо создать связанный образ.</span><span class="sxs-lookup"><span data-stu-id="72c89-189">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="72c89-190">Если приложение состоит из одной службы или веб-приложения, вам потребуется всего одним изображением.</span><span class="sxs-lookup"><span data-stu-id="72c89-190">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
>
> <span data-ttu-id="72c89-191">Учитывая «рабочего процесса DevOps внешний цикл», образы будут создаваться по автоматизированный процесс сборки при каждой отправке исходного кода в репозиторий Git (непрерывная интеграция), поэтому изображения будет создан в глобальной среде из вашей исходный код.</span><span class="sxs-lookup"><span data-stu-id="72c89-191">When taking into account the "outer-loop DevOps workflow", the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration), so the images will be created in that global environment from your source code.</span></span>
>
> <span data-ttu-id="72c89-192">Но прежде чем мы рассмотрим переход по этому маршруту внешний цикл, но нужно убедиться, что приложения Docker фактически работает правильно, чтобы они не будет отправлено код, который может не работать должным образом для системы управления версиями (Git, и т.д.).</span><span class="sxs-lookup"><span data-stu-id="72c89-192">But before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>
>
> <span data-ttu-id="72c89-193">Таким образом каждый разработчик сначала необходимо выполнить процесс внутреннего цикла для локального тестирования и продолжить разработку, пока они хотят передать полный функцию или изменить систему управления версиями.</span><span class="sxs-lookup"><span data-stu-id="72c89-193">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="72c89-194">Чтобы создать образ в локальной среде и с помощью DockerFile, можно использовать команду docker build, как показано на рис. 4-25 (также можно запустить `docker-compose up --build` для приложений, состоящих из нескольких контейнеров и служб).</span><span class="sxs-lookup"><span data-stu-id="72c89-194">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-25 (you also can run `docker-compose up --build` for applications composed by several containers/services).</span></span>

![Выходные данные консоли сборки docker-Compose, показывающий ход выполнения загрузки изображений.](./media/image25.png)

<span data-ttu-id="72c89-196">**Рис. 4-25**.</span><span class="sxs-lookup"><span data-stu-id="72c89-196">**Figure 4-25**.</span></span> <span data-ttu-id="72c89-197">Выполнения команды docker build</span><span class="sxs-lookup"><span data-stu-id="72c89-197">Running docker build</span></span>

<span data-ttu-id="72c89-198">При необходимости вместо непосредственного выполнения команды `docker build` из папки проекта, сначала можно создать развертываемую папку с библиотеками .NET с помощью запуска `dotnet publish` команды, а затем запустите `docker build`.</span><span class="sxs-lookup"><span data-stu-id="72c89-198">Optionally, instead of directly running `docker build` from the project folder, you first can generate a deployable folder with the .NET libraries needed by using the run `dotnet publish` command, and then run `docker build`.</span></span>

<span data-ttu-id="72c89-199">В этом примере создается образ Docker с именем `cesardl/netcore-webapi-microservice-docker:first` (`:first` — это тег, например определенной версии).</span><span class="sxs-lookup"><span data-stu-id="72c89-199">This example creates a Docker image with the name `cesardl/netcore-webapi-microservice-docker:first` (`:first` is a tag, like a specific version).</span></span> <span data-ttu-id="72c89-200">Вы можете использовать этот шаг для каждого пользовательского образа, который необходимо создать для своего составного приложения Docker с несколькими контейнерами.</span><span class="sxs-lookup"><span data-stu-id="72c89-200">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="72c89-201">Можно найти существующие образы в локальном репозитории (компьютере разработки) с помощью docker команду образов, как показано на рисунке 4-26.</span><span class="sxs-lookup"><span data-stu-id="72c89-201">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-26.</span></span>

![Выходные данные консоли из команды docker иллюстрации, существующих образов.](./media/image26.png)

<span data-ttu-id="72c89-203">**Рис. 4-26**.</span><span class="sxs-lookup"><span data-stu-id="72c89-203">**Figure 4-26**.</span></span> <span data-ttu-id="72c89-204">Просмотр существующих образов с помощью образов docker</span><span class="sxs-lookup"><span data-stu-id="72c89-204">Viewing existing images using docker images</span></span>

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="72c89-205">Шаг 4. Определение служб в файле docker-compose.yml, при создании составного приложения Docker с несколькими службами</span><span class="sxs-lookup"><span data-stu-id="72c89-205">Step 4: Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="72c89-206">С помощью `docker-compose.yml` файл, можно определить набор связанных служб для развертывания как составное приложение с помощью команд развертывания, как описано в следующем разделе шаг.</span><span class="sxs-lookup"><span data-stu-id="72c89-206">With the `docker-compose.yml` file, you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="72c89-207">Создание этого файла в основной или корневой папке решения; оно должно быть содержимое, как показано в этом `docker-compose.yml` файла:</span><span class="sxs-lookup"><span data-stu-id="72c89-207">Create that file in your main or root solution folder; it should have content similar to that shown in this `docker-compose.yml` file:</span></span>

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

<span data-ttu-id="72c89-208">В данном случае этот файл определяет две службы: веб-службы (настраиваемая служба) и служба redis (служба популярных кэширования).</span><span class="sxs-lookup"><span data-stu-id="72c89-208">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="72c89-209">Каждая служба будет развертываться как контейнер, поэтому нам нужно использовать конкретный образ Docker для каждого.</span><span class="sxs-lookup"><span data-stu-id="72c89-209">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="72c89-210">Для этого конкретного веб-службы изображение необходимо выполнить следующие:</span><span class="sxs-lookup"><span data-stu-id="72c89-210">For this particular web service, the image will need to do the following:</span></span>

- <span data-ttu-id="72c89-211">Строится на основе файла DockerFile в текущем каталоге</span><span class="sxs-lookup"><span data-stu-id="72c89-211">Build from the DockerFile in the current directory</span></span>

- <span data-ttu-id="72c89-212">Пересылать предоставленный порт 80 в контейнере для порта 81 на хост-компьютере</span><span class="sxs-lookup"><span data-stu-id="72c89-212">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

- <span data-ttu-id="72c89-213">Подключения в каталог проекта на узле для/Code в контейнере, благодаря чему можно изменять код без повторной сборки образа</span><span class="sxs-lookup"><span data-stu-id="72c89-213">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

- <span data-ttu-id="72c89-214">Привязать веб-службы к службе redis</span><span class="sxs-lookup"><span data-stu-id="72c89-214">Link the web service to the redis service</span></span>

<span data-ttu-id="72c89-215">Служба использует redis [последней версии образа общей redis](https://hub.docker.com/_/redis/) извлечь из реестра Docker Hub.</span><span class="sxs-lookup"><span data-stu-id="72c89-215">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="72c89-216">[redis](https://redis.io/) — это система популярных кэширования для серверных приложений.</span><span class="sxs-lookup"><span data-stu-id="72c89-216">[redis](https://redis.io/) is a popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="72c89-217">Шаг 5. Сборка и запуск приложения Docker</span><span class="sxs-lookup"><span data-stu-id="72c89-217">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="72c89-218">Если приложение имеет только один контейнер, необходимо просто запустите его, развернув ее к узлу Docker (виртуальной Машине или физическом сервере).</span><span class="sxs-lookup"><span data-stu-id="72c89-218">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="72c89-219">Тем не менее, если приложение состоит из нескольких служб, необходимо *комбинирование ее*, слишком.</span><span class="sxs-lookup"><span data-stu-id="72c89-219">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="72c89-220">Давайте посмотрим, различные варианты.</span><span class="sxs-lookup"><span data-stu-id="72c89-220">Let's see the different options.</span></span>

<span data-ttu-id="72c89-221">***Вариант а Запустите единственного контейнера или службы***</span><span class="sxs-lookup"><span data-stu-id="72c89-221">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="72c89-222">Образ Docker можно запустить с помощью команды docker run, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="72c89-222">You can run the Docker image by using the docker run command, as shown here:</span></span>

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="72c89-223">Для данного конкретного развертывания мы будем перенаправление запросов, отправленный на порт 80 с внутренним портом 5000.</span><span class="sxs-lookup"><span data-stu-id="72c89-223">For this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="72c89-224">Теперь приложение прослушивает внешний порт 80 на уровне узла.</span><span class="sxs-lookup"><span data-stu-id="72c89-224">Now the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="72c89-225">***Вариант б Составление и выполнение приложения-контейнера с несколькими***</span><span class="sxs-lookup"><span data-stu-id="72c89-225">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="72c89-226">В большинстве корпоративных сценариев приложение Docker будет состоять из нескольких служб.</span><span class="sxs-lookup"><span data-stu-id="72c89-226">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="72c89-227">В этих случаях можно запустить `docker-compose up` команду (рис. 4-27), которая будет использовать файл docker-compose.yml, который вы создали ранее.</span><span class="sxs-lookup"><span data-stu-id="72c89-227">For these cases, you can run the `docker-compose up` command (Figure 4-27), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="72c89-228">Данная команда развертывает составное приложение со всеми связанные с ним контейнеры.</span><span class="sxs-lookup"><span data-stu-id="72c89-228">Running this command deploys a composed application with all of its related containers.</span></span>

![Выходные данные консоли-команду docker compose up.](./media/image27.png)

<span data-ttu-id="72c89-230">**Рис. 4-27**.</span><span class="sxs-lookup"><span data-stu-id="72c89-230">**Figure 4-27**.</span></span> <span data-ttu-id="72c89-231">Результаты выполнения команды «docker-compose up»</span><span class="sxs-lookup"><span data-stu-id="72c89-231">Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="72c89-232">После того, как `docker-compose up`, развертывании приложения и его связанные контейнеры в узле Docker, как показано на рис. 4-28, в представлении виртуальной Машины.</span><span class="sxs-lookup"><span data-stu-id="72c89-232">After you run `docker-compose up`, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-28, in the VM representation.</span></span>

![Виртуальная машина выполнения многоконтейнерных приложений.](./media/image28.png)

<span data-ttu-id="72c89-234">**Рис. 4-28**.</span><span class="sxs-lookup"><span data-stu-id="72c89-234">**Figure 4-28**.</span></span> <span data-ttu-id="72c89-235">Виртуальная машина с развернутыми контейнерами Docker</span><span class="sxs-lookup"><span data-stu-id="72c89-235">VM with Docker containers deployed</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="72c89-236">Шаг 6. Тестирование приложения Docker (локально, в вашей локальной виртуальной Машине компакт-диска)</span><span class="sxs-lookup"><span data-stu-id="72c89-236">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="72c89-237">Этот шаг будет зависеть от действия приложения.</span><span class="sxs-lookup"><span data-stu-id="72c89-237">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="72c89-238">В простой .NET Core веб-API «Hello World» развернуть в качестве единственного контейнера или службы необходимо просто доступ к службе, предоставляя TCP-порт, указанный в DockerFile.</span><span class="sxs-lookup"><span data-stu-id="72c89-238">In a simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="72c89-239">Если localhost не включена, чтобы перейти к службе, найти IP-адрес для компьютера с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="72c89-239">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

```console
docker-machine {IP} {YOUR-CONTAINER-NAME}
```

<span data-ttu-id="72c89-240">На узле Docker откройте браузер и перейдите к этому сайту; Вы увидите/службе приложений под управлением, как показано на рис. 4-29.</span><span class="sxs-lookup"><span data-stu-id="72c89-240">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-29.</span></span>

![Представление браузера ответа от localhost/API/values.](./media/image29.png)

<span data-ttu-id="72c89-242">**Рис. 4-29**.</span><span class="sxs-lookup"><span data-stu-id="72c89-242">**Figure 4-29**.</span></span> <span data-ttu-id="72c89-243">Тестирование приложения Docker локально с помощью localhost</span><span class="sxs-lookup"><span data-stu-id="72c89-243">Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="72c89-244">Обратите внимание на то что он использует порт 80, но внутренне он перенаправляется на порт 5000, потому что это, как она была развернута с `docker run`, как описано ранее.</span><span class="sxs-lookup"><span data-stu-id="72c89-244">Note that it's using port 80, but internally it's being redirected to port 5000, because that's how it was deployed with `docker run`, as explained earlier.</span></span>

<span data-ttu-id="72c89-245">Это можно проверить с помощью CURL с терминала.</span><span class="sxs-lookup"><span data-stu-id="72c89-245">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="72c89-246">В установки Docker в Windows IP-адрес по умолчанию является 10.0.75.1, как показано на рис. 4-30.</span><span class="sxs-lookup"><span data-stu-id="72c89-246">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-30.</span></span>

![Получение выходных данных консоли http://10.0.75.1/API/values с помощью curl](./media/image30.png)

<span data-ttu-id="72c89-248">**Рис. 4-30**.</span><span class="sxs-lookup"><span data-stu-id="72c89-248">**Figure 4-30**.</span></span> <span data-ttu-id="72c89-249">Тестирование приложения Docker локально с помощью CURL</span><span class="sxs-lookup"><span data-stu-id="72c89-249">Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="72c89-250">**Отладка контейнера, запущенного в Docker**</span><span class="sxs-lookup"><span data-stu-id="72c89-250">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="72c89-251">Visual Studio Code поддерживает отладки Docker, если вы используете Node.js и других платформ, таких как контейнеры .NET Core.</span><span class="sxs-lookup"><span data-stu-id="72c89-251">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="72c89-252">Также можно отлаживать контейнеры .NET Core или .NET Framework в Docker при использовании Visual Studio для Windows или Mac, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="72c89-252">You also can debug .NET Core or .NET Framework containers in Docker when using Visual Studio for Windows or Mac, as described in the next section.</span></span>

> [! СВЕДЕНИЯ]
>
> <span data-ttu-id="72c89-254">Дополнительные сведения об отладке контейнеров Node.js Docker, перейдите к <https://blog.docker.com/2016/07/live-debugging-docker/> и <https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/>.</span><span class="sxs-lookup"><span data-stu-id="72c89-254">To learn more about debugging Node.js Docker containers, go to <https://blog.docker.com/2016/07/live-debugging-docker/> and <https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/>.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="72c89-255">[Назад](docker-apps-development-environment.md)
>[Вперед](visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="72c89-255">[Previous](docker-apps-development-environment.md)
[Next](visual-studio-tools-for-docker.md)</span></span>
