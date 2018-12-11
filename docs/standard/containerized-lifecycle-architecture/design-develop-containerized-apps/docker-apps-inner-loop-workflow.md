---
title: Рабочий процесс внутреннего цикла разработки для приложений Docker
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: f7acb60e6136c0250d18bdce23ac21fb6aa80b34
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148867"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="1af2a-103">Рабочий процесс внутреннего цикла разработки для приложений Docker</span><span class="sxs-lookup"><span data-stu-id="1af2a-103">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="1af2a-104">Перед запуском рабочего процесса внешний цикл, охватывающие весь DevOps цикл, все начинает на компьютере каждого разработчика, кодирования самого приложения, с помощью предпочитаемых языков или платформ и его локальному тестированию (рис. 4-14).</span><span class="sxs-lookup"><span data-stu-id="1af2a-104">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-14).</span></span> <span data-ttu-id="1af2a-105">Но в любом случае, вы получите очень важный момент общее, независимо от того, какой язык, framework или платформ выбрано.</span><span class="sxs-lookup"><span data-stu-id="1af2a-105">But in every case, you will have a very important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="1af2a-106">В этом конкретного рабочего процесса вы всегда разработки и тестирования контейнеров Docker, а на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1af2a-106">In this specific workflow, you are always developing and testing Docker containers, but locally.</span></span>

![](./media/image18.png)

<span data-ttu-id="1af2a-107">Рис. 4-14: Внутренний цикл разработки контекста</span><span class="sxs-lookup"><span data-stu-id="1af2a-107">Figure 4-14: Inner-loop development context</span></span>

<span data-ttu-id="1af2a-108">Контейнер или экземпляр образа Docker будет содержать следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="1af2a-108">The container or instance of a Docker image will contain these components:</span></span>

-   <span data-ttu-id="1af2a-109">Выбранная операционная система (например, дистрибутив Linux или Windows)</span><span class="sxs-lookup"><span data-stu-id="1af2a-109">An operating system selection (for example, a Linux distribution or Windows)</span></span>

-   <span data-ttu-id="1af2a-110">Файлы, добавленные разработчиком (например, двоичные файлы приложения)</span><span class="sxs-lookup"><span data-stu-id="1af2a-110">Files added by the developer (for example, app binaries)</span></span>

-   <span data-ttu-id="1af2a-111">Конфигурации (например, параметры среды и зависимости)</span><span class="sxs-lookup"><span data-stu-id="1af2a-111">Configuration (for example, environment settings and dependencies)</span></span>

-   <span data-ttu-id="1af2a-112">Инструкции для того, какие процессы с Docker</span><span class="sxs-lookup"><span data-stu-id="1af2a-112">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="1af2a-113">Можно настроить рабочий процесс внутреннего цикла разработки, который использует Docker, процесс (см. в следующем разделе).</span><span class="sxs-lookup"><span data-stu-id="1af2a-113">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="1af2a-114">Учитывайте для учетной записи, что начальные действия по настройке среды не будет включен, так как вам нужно сделать только один раз.</span><span class="sxs-lookup"><span data-stu-id="1af2a-114">Take into account that the initial steps to set up the environment is not included, because you need to do that just once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="1af2a-115">Создание одного приложения в контейнере Docker, с помощью Visual Studio Code и Docker CLI</span><span class="sxs-lookup"><span data-stu-id="1af2a-115">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="1af2a-116">Приложения, состоящего из ваших собственных служб и дополнительных библиотек (зависимостей).</span><span class="sxs-lookup"><span data-stu-id="1af2a-116">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="1af2a-117">Рис. 4-15 показывает основные шаги, которые обычно требуется выполнить при создании приложения Docker, следуют подробное описание каждого шага.</span><span class="sxs-lookup"><span data-stu-id="1af2a-117">Figure 4-15 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![](./media/image19.png)

<span data-ttu-id="1af2a-118">Рис. 4-15. Высокоуровневый рабочий процесс для жизненного цикла для Docker контейнерных приложений с помощью интерфейса командной строки Docker</span><span class="sxs-lookup"><span data-stu-id="1af2a-118">Figure 4-15: High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="1af2a-119">Шаг 1. Приступаем к написанию кода в Visual Studio Code и создания начальной приложения или услуги базовых показателей</span><span class="sxs-lookup"><span data-stu-id="1af2a-119">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="1af2a-120">Способ разработки приложения очень похоже на способ сделать это без Docker.</span><span class="sxs-lookup"><span data-stu-id="1af2a-120">The way you develop your application is pretty similar to the way you do it without Docker.</span></span> <span data-ttu-id="1af2a-121">Разница в том, что при разработке, развертывании и тестировании приложения или службы, работающие в контейнеры Docker, размещенные в локальной среде (например, виртуальной Машины Linux или Windows).</span><span class="sxs-lookup"><span data-stu-id="1af2a-121">The difference is that while developing, you are deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="1af2a-122">**Настройка локальной среды**</span><span class="sxs-lookup"><span data-stu-id="1af2a-122">**Setting up your local environment**</span></span>

<span data-ttu-id="1af2a-123">Последние версии Docker для Mac и Windows проще, чем когда-либо для разработки приложений Docker и установки прямолинейна.</span><span class="sxs-lookup"><span data-stu-id="1af2a-123">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

<span data-ttu-id="1af2a-124">**Дополнительные сведения о** инструкции по настройке Docker для Windows, см. в статье [ https://docs.docker.com/docker-for-windows/ ](https://docs.docker.com/docker-for-windows/).</span><span class="sxs-lookup"><span data-stu-id="1af2a-124">**More info** For instructions on setting up Docker for Windows, go to [https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/).</span></span>

<span data-ttu-id="1af2a-125">Инструкции по настройке Docker для Mac, см. в статье <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="1af2a-125">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="1af2a-126">Кроме того потребуется редактор кода, чтобы фактически можно разрабатывать приложения при использовании интерфейса командной строки Docker.</span><span class="sxs-lookup"><span data-stu-id="1af2a-126">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="1af2a-127">Корпорация Майкрософт предоставляет Visual Studio Code, который представляет собой редактор небольшой объем кода, который поддерживается на Mac, Windows и Linux, а также предоставляет поддержку технологии IntelliSense с [поддержка множества языков](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python и большинство современные языки), [отладки](https://code.visualstudio.com/Docs/editor/debugging), [интеграция с Git](https://code.visualstudio.com/Docs/editor/versioncontrol) и [поддержке расширений](https://code.visualstudio.com/docs/extensions/overview).</span><span class="sxs-lookup"><span data-stu-id="1af2a-127">Microsoft provides Visual Studio Code, which is a lightweight code editor that is supported on Mac, Windows, and Linux, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="1af2a-128">Этот редактор — отлично подходит для разработчиков Mac и Linux.</span><span class="sxs-lookup"><span data-stu-id="1af2a-128">This editor is a great fit for Mac and Linux developers.</span></span> <span data-ttu-id="1af2a-129">В Windows также можно использовать полный приложения Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1af2a-129">In Windows, you also can use the full Visual Studio application.</span></span>

<span data-ttu-id="1af2a-130">**Дополнительные сведения о** инструкции по установке Visual Studio для Windows, Mac или Linux, см. в статье <https://code.visualstudio.com/docs/setup/setup-overview/>.</span><span class="sxs-lookup"><span data-stu-id="1af2a-130">**More info** For instructions on installing Visual Studio for Windows, Mac, or Linux, go to <https://code.visualstudio.com/docs/setup/setup-overview/>.</span></span>

<span data-ttu-id="1af2a-131">Можно работать с помощью Docker CLI и написать код, используя любой редактор кода, но если вы используете Visual Studio Code, зато его автор Dockerfile и docker-compose.yml файлов в рабочей области.</span><span class="sxs-lookup"><span data-stu-id="1af2a-131">You can work with Docker CLI and write your code using any code editor, but if you use Visual Studio Code, it makes it easy to author Dockerfile and docker-compose.yml files in your workspace.</span></span> <span data-ttu-id="1af2a-132">Кроме того можно выполнять задачи Visual Studio Code в интегрированной среде разработки, позволяющего запросить скрипты, которые можно выполнять сложные операции, с помощью интерфейса командной строки Docker под.</span><span class="sxs-lookup"><span data-stu-id="1af2a-132">Plus, you can run Visual Studio Code tasks from the IDE that will prompt scripts that can be running elaborated operations using Docker CLI underneath.</span></span>

<span data-ttu-id="1af2a-133">Visual Studio Code предоставляется расширение, которое необходимо установить.</span><span class="sxs-lookup"><span data-stu-id="1af2a-133">Visual Studio Code is provided by an extension, which you'll need to install.</span></span> <span data-ttu-id="1af2a-134">Чтобы сделать это, нажмите клавиши Ctrl + Shift + P, введите **установить ext**, а затем запустите расширения: Установите расширение команду, чтобы открыть список расширений Marketplace.</span><span class="sxs-lookup"><span data-stu-id="1af2a-134">To do so, Press Ctrl+Shift+P, type **ext install**, and then run the Extensions: Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="1af2a-135">Затем введите **docker** для фильтрации результатов, затем выберите файл Dockerfile и файл Docker Compose (yml) расширения поддержки, как показано на рисунке 4-16.</span><span class="sxs-lookup"><span data-stu-id="1af2a-135">Next, type **docker** to filter the results, and then select the Dockerfile And Docker Compose File (yml) Support extension, as depicted in Figure 4-16.</span></span>

![](./media/image20.png)

<span data-ttu-id="1af2a-136">Рис. 4-16. Установка расширения Docker в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="1af2a-136">Figure 4-16: Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="1af2a-137">Шаг 2. Создание файла DockerFile, связанного с существующим образом (plain ОС или сред разработки, например .NET Core, Node.js и Ruby)</span><span class="sxs-lookup"><span data-stu-id="1af2a-137">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="1af2a-138">Вам потребуется файл DockerFile в пользовательский образ для построения и каждый контейнер развертывается, таким образом, если приложение состоит из единственный экземпляр пользовательской службы, вам потребуется один DockerFile.</span><span class="sxs-lookup"><span data-stu-id="1af2a-138">You will need a DockerFile per custom image to be built and per container to be deployed, therefore, if your app is made up of a single custom service, you will need a single DockerFile.</span></span> <span data-ttu-id="1af2a-139">Но если приложение состоит из нескольких служб (как в архитектуре микрослужб), вам потребуется один Dockerfile каждой службы.</span><span class="sxs-lookup"><span data-stu-id="1af2a-139">But, if your app is composed of multiple services (as in a microservices architecture), you'll need one Dockerfile per service.</span></span>

<span data-ttu-id="1af2a-140">DockerFile обычно размещается в корневой папке приложения или службы и содержит необходимые команды, поэтому Docker знает, как установить и запустить приложения или службы.</span><span class="sxs-lookup"><span data-stu-id="1af2a-140">The DockerFile is usually placed within the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="1af2a-141">Можно создать DockerFile и добавить его в проект вместе с кода (node.js, .NET Core, и т.д.), или, если вы новичок в среду, взгляните на следующий совет.</span><span class="sxs-lookup"><span data-stu-id="1af2a-141">You can create your DockerFile and add it to your project along with your code (node.js, .NET Core, etc.), or, if you are new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
> <span data-ttu-id="1af2a-142">Можно использовать программу командной строки [yo docker](https://github.com/Microsoft/generator-docker), который формирует шаблоны файлов из проекта в языках, а также добавляет необходимые файлы конфигурации Docker.</span><span class="sxs-lookup"><span data-stu-id="1af2a-142">You can use a command-line tool called [yo docker](https://github.com/Microsoft/generator-docker), which scaffolds files from your project in the language you choose and adds the required Docker configuration files.</span></span> <span data-ttu-id="1af2a-143">По сути, чтобы помочь разработчикам Приступая к работе, он создает соответствующий файл DockerFile, docker-compose.yml и другие связанные сценарии, для построения и выполнения контейнеров Docker.</span><span class="sxs-lookup"><span data-stu-id="1af2a-143">Basically, to assist developers getting started, it creates the appropriate DockerFile, docker-compose.yml, and other associated scripts to build and run your Docker containers.</span></span> <span data-ttu-id="1af2a-144">Этот генератор yeoman предложит ответить на несколько вопросов, запросом разработки выбранного языка и назначения узла контейнера.</span><span class="sxs-lookup"><span data-stu-id="1af2a-144">This yeoman generator will prompt you with a few questions, asking your selected development language and destination container host.</span></span>

![yo docker](./media/image21.png)

<span data-ttu-id="1af2a-146">Например рис. 4-17 показано два снимка экрана из терминалов в Windows и на компьютер Mac, в обоих случаях с yo docker, который создаст образцов кода проектов (в настоящее время .NET Core, Golang и Node.js в качестве поддерживаемых языков) уже настроен для работы с Верхняя часть Docker.</span><span class="sxs-lookup"><span data-stu-id="1af2a-146">For instance, Figure 4-17 shows two screenshots from the terminals in Windows and on a Mac, in both cases, running yo docker, which will generate the sample code projects (currently .NET Core, Golang, and Node.js as supported languages) already configured to work on top of Docker.</span></span>

![](./media/image22.PNG)  ![](./media/image23.png)

<span data-ttu-id="1af2a-147">Рис. 4-17: docker команды yo средство в Windows (слева) и на компьютере Mac</span><span class="sxs-lookup"><span data-stu-id="1af2a-147">Figure 4-17: yo docker command tool in Windows (left) and on a Mac</span></span>

<span data-ttu-id="1af2a-148">Рис. 4-18 представлен пример с использованием yo docker после существующего проекта .NET Core на месте, чтобы быть скаффолдинга.</span><span class="sxs-lookup"><span data-stu-id="1af2a-148">Figure 4-18 presents an example using yo docker after you have an existing .NET Core project in place to be scaffolded.</span></span>

![](./media/image24.PNG)

<span data-ttu-id="1af2a-149">Рис. 4-18: yo docker с .NET Core существующего проекта на месте</span><span class="sxs-lookup"><span data-stu-id="1af2a-149">Figure 4-18: yo docker with an existing .NET Core project in place</span></span>

<span data-ttu-id="1af2a-150">Из файла DockerFile укажите какой базовый образ Docker, вы будете использовать (например, использование «FROM microsoft/dotnet:1.0.0-core»).</span><span class="sxs-lookup"><span data-stu-id="1af2a-150">From the DockerFile, you specify what base Docker image you'll be using (like using "FROM microsoft/dotnet:1.0.0-core").</span></span> <span data-ttu-id="1af2a-151">Создайте пользовательский образ на основе базового образа, который можно получить из любой официального репозитория в обычно будет [реестра Docker Hub](https://hub.docker.com/) (как [изображение для .NET Core](https://hub.docker.com/r/microsoft/dotnet/) или один [для Node.js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="1af2a-151">You usually will build your custom image on top of a base image that you can get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/r/microsoft/dotnet/) or one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="1af2a-152">***Вариант а Использовать существующий официальный образ Docker***</span><span class="sxs-lookup"><span data-stu-id="1af2a-152">***Option A: Use an existing official Docker image***</span></span>

<span data-ttu-id="1af2a-153">Использование официального репозитория стек для языка с номером версии гарантирует, что те же функции языка доступны на всех компьютерах (включая разработки, тестирования и эксплуатации).</span><span class="sxs-lookup"><span data-stu-id="1af2a-153">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="1af2a-154">Ниже приведен пример DockerFile для контейнера .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1af2a-154">Following is a sample DockerFile for a .NET Core container:</span></span>

```
# Base Docker image to use
FROM microsoft/aspnetcore:1.0.1\

# Set the Working Directory and files to be copied to the image
ARG source
WORKDIR /app
COPY ${source:-bin/Release/PublishOutput} .

# Configure the listening port to 80 (Internal/Secured port within Docker host)
EXPOSE 80

# Application entry point
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

<span data-ttu-id="1af2a-155">В этом случае он использует версии 1.0.1 официального образа ASP.NET Core Docker для Linux, с именем microsoft/aspnetcore:1.0.1.</span><span class="sxs-lookup"><span data-stu-id="1af2a-155">In this case, it is using the version 1.0.1 of the official ASP.NET Core Docker image for Linux named microsoft/aspnetcore:1.0.1.</span></span> <span data-ttu-id="1af2a-156">Для получения дополнительных сведений обратитесь к [страницы образ Docker ASP.NET Core](https://hub.docker.com/r/microsoft/aspnetcore/) и [образ Docker .NET Core страницы](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="1af2a-156">For further details, consult the [ASP.NET Core Docker Image page](https://hub.docker.com/r/microsoft/aspnetcore/) and the [.NET Core Docker Image page](https://hub.docker.com/r/microsoft/dotnet/).</span></span> <span data-ttu-id="1af2a-157">Его также можно использовать другое изображение сопоставимых как узел: 4-onbuild Node.js и многих других предварительно настроенных образов для разработки языков, которые можно найти по адресу [Docker Hub](https://hub.docker.com/explore/).</span><span class="sxs-lookup"><span data-stu-id="1af2a-157">You also could be using another comparable image like node:4-onbuild for Node.js, or many other preconfigured images for development languages, which are available at [Docker Hub](https://hub.docker.com/explore/).</span></span>

<span data-ttu-id="1af2a-158">В файле DockerFile необходимо также указать Docker прослушивать TCP-порт, который будет использоваться во время выполнения (например, порт 80).</span><span class="sxs-lookup"><span data-stu-id="1af2a-158">In the DockerFile, you also need to instruct Docker to listen to the TCP port that you will use at runtime (such as port 80).</span></span>

<span data-ttu-id="1af2a-159">Существуют другие строки конфигурации, можно добавить в файл DockerFile в зависимости от языка и платформы, которую вы используете, чтобы Docker знает, как запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="1af2a-159">There are other lines of configuration that you can add in the DockerFile depending on the language/framework you are using, so Docker knows how to run the app.</span></span> <span data-ttu-id="1af2a-160">К примеру, требуется ENTRYPOINT строку с \[«dotnet», «MyCustomMicroservice.dll»\] запустить приложение .NET Core, несмотря на то, что вы можете выбрать несколько вариантов в зависимости от подхода для построения и запуска службы.</span><span class="sxs-lookup"><span data-stu-id="1af2a-160">For instance, you need the ENTRYPOINT line with \["dotnet", "MyCustomMicroservice.dll"\] to run a .NET Core app, although you can have multiple variants depending on the approach to build and run your service.</span></span> <span data-ttu-id="1af2a-161">При использовании пакета SDK и dotnet CLI для создания и запуска приложений .NET, было бы немного отличается.</span><span class="sxs-lookup"><span data-stu-id="1af2a-161">If you're using the SDK and dotnet CLI to build and run the .NET app, it would be slightly different.</span></span> <span data-ttu-id="1af2a-162">Суть что ENTRYPOINT строки, а также дополнительные строки будет отличаться в зависимости от языка и платформы, выбранных для приложения.</span><span class="sxs-lookup"><span data-stu-id="1af2a-162">The bottom line is that the ENTRYPOINT line plus additional lines will be different depending on the language/platform you choose for your application.</span></span>

<span data-ttu-id="1af2a-163">**Дополнительные сведения о** сведения о создании образов Docker для приложений .NET Core, см. в статье <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span><span class="sxs-lookup"><span data-stu-id="1af2a-163">**More info** For information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>

<span data-ttu-id="1af2a-164">Дополнительные сведения о создании собственных образов, перейдите к [ https://docs.docker.com/engine/\ учебники/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).</span><span class="sxs-lookup"><span data-stu-id="1af2a-164">To learn more about building your own images, go to [https://docs.docker.com/engine/\ tutorials/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).</span></span>

<span data-ttu-id="1af2a-165">**Репозитории многоплатформенного образа**</span><span class="sxs-lookup"><span data-stu-id="1af2a-165">**Multiplatform image repositories**</span></span>

<span data-ttu-id="1af2a-166">Как контейнеры Windows станут более распространенными, один репозиторий может содержать варианты платформ, например образ Linux и Windows.</span><span class="sxs-lookup"><span data-stu-id="1af2a-166">As Windows containers become more prevalent, a single repository can contain platform variants, such as a Linux and Windows image.</span></span> <span data-ttu-id="1af2a-167">Это новая функция, добавленная в Docker, который делает возможным для поставщиков использовать один репозиторий для охвата нескольких платформ, таких как [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) репозитория, которая находится на реестра DockerHub.</span><span class="sxs-lookup"><span data-stu-id="1af2a-167">This is a new feature coming in Docker that makes it possible for vendors to use a single repository to cover multiple platforms, such as [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repository, which is available at DockerHub registry.</span></span> <span data-ttu-id="1af2a-168">Как компонент оживает, получение этого образа с узла Windows будет получать вариант Windows, тогда как извлекать имя образа из узла Linux будет получен вариант для Linux.</span><span class="sxs-lookup"><span data-stu-id="1af2a-168">As the feature comes alive, pulling this image from a Windows host will pull the Windows variant, whereas pulling the same image name from a Linux host will pull the Linux variant.</span></span>

<span data-ttu-id="1af2a-169">***Вариант б Создание базового образа с нуля***</span><span class="sxs-lookup"><span data-stu-id="1af2a-169">***Option B: Create your base image from scratch***</span></span>

<span data-ttu-id="1af2a-170">Можно создать свой собственный базовый образ Docker с нуля, описанные в этой [статье](https://docs.docker.com/engine/userguide/eng-image/baseimages/) из Docker.</span><span class="sxs-lookup"><span data-stu-id="1af2a-170">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="1af2a-171">Это сценарий, скорее всего, не оптимальную для вас, если только вы начинаете с помощью Docker, но если вы хотите задать определенные биты базового образа, это можно сделать.</span><span class="sxs-lookup"><span data-stu-id="1af2a-171">This is a scenario that is probably not best for you if you are just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="1af2a-172">Шаг 3. Создание пользовательских образов Docker внедрения службы в нем</span><span class="sxs-lookup"><span data-stu-id="1af2a-172">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="1af2a-173">Для каждого пользовательского службы, которая состоит из приложения необходимо создать связанный образ.</span><span class="sxs-lookup"><span data-stu-id="1af2a-173">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="1af2a-174">Если приложение состоит из одной службы или веб-приложения, вам потребуется всего одним изображением.</span><span class="sxs-lookup"><span data-stu-id="1af2a-174">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
> <span data-ttu-id="1af2a-175">Учитывая «рабочего процесса DevOps внешний цикл», образы будут создаваться по автоматизированный процесс сборки при каждой отправке исходного кода в репозиторий Git (непрерывная интеграция), поэтому изображения будет создан в глобальной среде из вашей исходный код.</span><span class="sxs-lookup"><span data-stu-id="1af2a-175">When taking into account the "outer-loop DevOps workflow," the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration) so the images will be created in that global environment from your source code.</span></span>

<span data-ttu-id="1af2a-176">Но прежде чем мы рассмотрим переход по этому маршруту внешний цикл, но нужно убедиться, что приложения Docker фактически работает правильно, чтобы они не будет отправлено код, который может не работать должным образом для системы управления версиями (Git, и т.д.).</span><span class="sxs-lookup"><span data-stu-id="1af2a-176">But, before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>

<span data-ttu-id="1af2a-177">Таким образом каждый разработчик сначала необходимо выполнить процесс внутреннего цикла для локального тестирования и продолжить разработку, пока они хотят передать полный функцию или изменить систему управления версиями.</span><span class="sxs-lookup"><span data-stu-id="1af2a-177">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="1af2a-178">Чтобы создать образ в локальной среде и с помощью DockerFile, можно использовать команду docker build, как показано на рис. 4-19 (также можно запустить docker-compose up--сборки для приложений, состоящих из нескольких контейнеров и служб).</span><span class="sxs-lookup"><span data-stu-id="1af2a-178">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-19 (you also can run docker-compose up --build for applications composed by several containers/services).</span></span>

![](./media/image25.png)

<span data-ttu-id="1af2a-179">Рис. 4-19. Выполнения команды docker build</span><span class="sxs-lookup"><span data-stu-id="1af2a-179">Figure 4-19: Running docker build</span></span>

<span data-ttu-id="1af2a-180">При необходимости вместо непосредственного выполнения команды docker сборки из папки проекта, вы сначала можно создать развертываемую папку с библиотеками .NET, необходимо с помощью выполнения dotnet команды публикации, а затем запустите сборки docker.</span><span class="sxs-lookup"><span data-stu-id="1af2a-180">Optionally, instead of directly running docker build from the project's folder, you first can generate a deployable folder with the .NET libraries needed by using the run dotnet publish command, and then run docker build.</span></span>

<span data-ttu-id="1af2a-181">В этом примере создается образ Docker с именем cesardl/netcore-webapi микрослужба-docker: first (: first — это тег, например определенной версии).</span><span class="sxs-lookup"><span data-stu-id="1af2a-181">In this example, this creates a Docker image with the name cesardl/netcore-webapi-microservice-docker:first (:first is a tag, like a specific version).</span></span> <span data-ttu-id="1af2a-182">Вы можете использовать этот шаг для каждого пользовательского образа, который необходимо создать для своего составного приложения Docker с несколькими контейнерами.</span><span class="sxs-lookup"><span data-stu-id="1af2a-182">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="1af2a-183">Можно найти существующие образы в локальном репозитории (компьютере разработки) с помощью docker команду образов, как показано на рис. 4-20.</span><span class="sxs-lookup"><span data-stu-id="1af2a-183">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-20.</span></span>

![](./media/image26.png)

<span data-ttu-id="1af2a-184">Рис. 4-20: Просмотр существующих образов с помощью образов docker</span><span class="sxs-lookup"><span data-stu-id="1af2a-184">Figure 4-20: Viewing existing images using docker images</span></span>

### <a name="step-4-optional-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="1af2a-185">Шаг 4. (Необязательно) Определение служб в файле docker-compose.yml, при создании составного приложения Docker с несколькими службами</span><span class="sxs-lookup"><span data-stu-id="1af2a-185">Step 4: (Optional) Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="1af2a-186">В файле docker-compose.yml можно определить набор связанных служб для развертывания как составное приложение с помощью команд развертывания, как описано в следующем разделе шаг.</span><span class="sxs-lookup"><span data-stu-id="1af2a-186">With the docker-compose.yml file you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="1af2a-187">Чтобы создать этот файл в основной или корневой папке решения; он должен иметь аналогичное содержимое в следующий файл docker-compose.yml:</span><span class="sxs-lookup"><span data-stu-id="1af2a-187">You need to create that file in your main or root solution folder; it should have a similar content to the following docker-compose.yml file:</span></span>

```yml
version: '2'
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

<span data-ttu-id="1af2a-188">В данном случае этот файл определяет две службы: веб-службы (настраиваемая служба) и служба redis (служба популярных кэширования).</span><span class="sxs-lookup"><span data-stu-id="1af2a-188">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="1af2a-189">Каждая служба будет развертываться как контейнер, поэтому нам нужно использовать конкретный образ Docker для каждого.</span><span class="sxs-lookup"><span data-stu-id="1af2a-189">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="1af2a-190">Для этого конкретного веб-службы изображение необходимо выполнить следующие:</span><span class="sxs-lookup"><span data-stu-id="1af2a-190">For this particular web service, the image will need to do the following:</span></span>

-   <span data-ttu-id="1af2a-191">Строится на основе файла DockerFile в текущем каталоге</span><span class="sxs-lookup"><span data-stu-id="1af2a-191">Build from the DockerFile in the current directory</span></span>

-   <span data-ttu-id="1af2a-192">Пересылать предоставленный порт 80 в контейнере для порта 81 на хост-компьютере</span><span class="sxs-lookup"><span data-stu-id="1af2a-192">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

-   <span data-ttu-id="1af2a-193">Подключения в каталог проекта на узле для/Code в контейнере, благодаря чему можно изменять код без повторной сборки образа</span><span class="sxs-lookup"><span data-stu-id="1af2a-193">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

-   <span data-ttu-id="1af2a-194">Привязать веб-службы к службе redis</span><span class="sxs-lookup"><span data-stu-id="1af2a-194">Link the web service to the redis service</span></span>

<span data-ttu-id="1af2a-195">Служба использует redis [последней версии образа общей redis](https://hub.docker.com/_/redis/) извлечь из реестра Docker Hub.</span><span class="sxs-lookup"><span data-stu-id="1af2a-195">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="1af2a-196">[redis](https://redis.io/) — это система очень популярных кэширования для серверных приложений.</span><span class="sxs-lookup"><span data-stu-id="1af2a-196">[redis](https://redis.io/) is a very popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="1af2a-197">Шаг 5. Сборка и запуск приложения Docker</span><span class="sxs-lookup"><span data-stu-id="1af2a-197">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="1af2a-198">Если приложение имеет только один контейнер, необходимо просто запустите его, развернув ее к узлу Docker (виртуальной Машине или физическом сервере).</span><span class="sxs-lookup"><span data-stu-id="1af2a-198">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="1af2a-199">Тем не менее, если приложение состоит из нескольких служб, необходимо *комбинирование ее*, слишком.</span><span class="sxs-lookup"><span data-stu-id="1af2a-199">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="1af2a-200">Давайте посмотрим, различные варианты.</span><span class="sxs-lookup"><span data-stu-id="1af2a-200">Let's see the different options.</span></span>

<span data-ttu-id="1af2a-201">***Вариант а Запустите единственного контейнера или службы***</span><span class="sxs-lookup"><span data-stu-id="1af2a-201">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="1af2a-202">Образ Docker можно запустить с помощью команды docker run, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="1af2a-202">You can run the Docker image by using the docker run command, as shown here:</span></span>

```
docker run -t -d -p 80:5000
cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="1af2a-203">Обратите внимание на то, что для данного конкретного развертывания, мы будем перенаправление запросы, отправляемые на порт 80 с внутренним портом 5000.</span><span class="sxs-lookup"><span data-stu-id="1af2a-203">Note that for this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="1af2a-204">Теперь приложение прослушивает внешний порт 80 на уровне узла.</span><span class="sxs-lookup"><span data-stu-id="1af2a-204">Now, the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="1af2a-205">***Вариант б Составление и выполнение приложения-контейнера с несколькими***</span><span class="sxs-lookup"><span data-stu-id="1af2a-205">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="1af2a-206">В большинстве корпоративных сценариев приложение Docker будет состоять из нескольких служб.</span><span class="sxs-lookup"><span data-stu-id="1af2a-206">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="1af2a-207">В этих случаях можно выполнить команду docker-compose up (рис. 4-21), который будет использовать файл docker-compose.yml, который вы создали ранее.</span><span class="sxs-lookup"><span data-stu-id="1af2a-207">For these cases, you can run the command docker-compose up (Figure 4-21), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="1af2a-208">Данная команда развертывает составное приложение со всеми связанные с ним контейнеры.</span><span class="sxs-lookup"><span data-stu-id="1af2a-208">Running this command deploys a composed application with all of its related containers.</span></span>

![](./media/image27.png)

<span data-ttu-id="1af2a-209">Рис. 4-21. Результаты выполнения команды «docker-compose up»</span><span class="sxs-lookup"><span data-stu-id="1af2a-209">Figure 4-21: Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="1af2a-210">После запуска docker-compose up, развернуть приложение и его связанные контейнеры в узле Docker, как показано на рисунке 4-22, в представлении виртуальной Машины.</span><span class="sxs-lookup"><span data-stu-id="1af2a-210">After you run docker-compose up, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-22, in the VM representation.</span></span>

![](./media/image28.png)

<span data-ttu-id="1af2a-211">Рис. 4-22: Виртуальная машина с развернутыми контейнерами Docker</span><span class="sxs-lookup"><span data-stu-id="1af2a-211">Figure 4-22: VM with Docker containers deployed</span></span>

<span data-ttu-id="1af2a-212">Примечание docker-compose up "run" docker может оказаться достаточно для тестирования контейнеров в среде разработки, но не использовать их вообще, если вы предполагаете, для работы с кластерами Docker и оркестраторы, такие как Docker Swarm, Mesosphere DC/OS или Kubernetes Чтобы иметь возможность увеличить масштаб.</span><span class="sxs-lookup"><span data-stu-id="1af2a-212">Note docker-compose up and docker run might be enough for testing your containers in your development environment, but you might not use them at all if you are expecting to work with Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes in order to be able to scale up.</span></span> <span data-ttu-id="1af2a-213">Если вы используете кластер, например [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (доступно в Docker для Windows и Mac с версии 1.12), необходимо для развертывания и тестирования с помощью дополнительных команд, таких как создания службы docker для одной службы или когда вы будете развертывание приложения, состоящего из нескольких контейнеров, пакета с помощью docker compose и docker myBundleFile, развертывание, развернув составных приложений в качестве стека, как описано в статье [наборы распределенных приложений](https://blog.docker.com/2016/06/docker-app-bundle/) из Docker.</span><span class="sxs-lookup"><span data-stu-id="1af2a-213">If you're using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker for Windows and Mac since version 1.12), you need to deploy and test with additional commands such as docker service create for single services, or when you're deploying an app composed of several containers, using docker compose bundle and docker deploy myBundleFile, by deploying the composed app as a stack, as explained in the article [Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) from Docker.</span></span>

<span data-ttu-id="1af2a-214">Для [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) и [Kubernetes](https://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) команд разные развертывания и сценарии, а также используются.</span><span class="sxs-lookup"><span data-stu-id="1af2a-214">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](https://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) you would use different deployment commands and scripts, as well.</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="1af2a-215">Шаг 6. Тестирование приложения Docker (локально, в вашей локальной виртуальной Машине компакт-диска)</span><span class="sxs-lookup"><span data-stu-id="1af2a-215">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="1af2a-216">Этот шаг будет зависеть от действия приложения.</span><span class="sxs-lookup"><span data-stu-id="1af2a-216">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="1af2a-217">В очень простой .NET Core веб-API «Hello World» развернуть в качестве единственного контейнера или службы необходимо просто доступ к службе, предоставляя TCP-порт, указанный в DockerFile.</span><span class="sxs-lookup"><span data-stu-id="1af2a-217">In a very simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="1af2a-218">Если localhost не включена, чтобы перейти к службе, найти IP-адрес для компьютера с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="1af2a-218">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

<span data-ttu-id="1af2a-219">IP-адреса компьютера docker *your имя контейнера*</span><span class="sxs-lookup"><span data-stu-id="1af2a-219">docker-machine ip *your-container-name*</span></span>

<span data-ttu-id="1af2a-220">На узле Docker откройте браузер и перейдите к этому сайту; Вы увидите/службе приложений под управлением, как показано на рис. 4-23.</span><span class="sxs-lookup"><span data-stu-id="1af2a-220">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-23.</span></span>

![](./media/image29.png)

<span data-ttu-id="1af2a-221">Рис. 4-23. Тестирование приложения Docker локально с помощью localhost</span><span class="sxs-lookup"><span data-stu-id="1af2a-221">Figure 4-23: Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="1af2a-222">Обратите внимание, что он использует порт 80, но внутренне были перенаправлены на порт 5000, потому что это, как он был развернут с помощью запуска, docker, как объяснялось ранее.</span><span class="sxs-lookup"><span data-stu-id="1af2a-222">Note that it is using port 80, but internally it was being redirected to port 5000, because that's how it was deployed with docker run, as explained earlier.</span></span>

<span data-ttu-id="1af2a-223">Это можно проверить с помощью CURL с терминала.</span><span class="sxs-lookup"><span data-stu-id="1af2a-223">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="1af2a-224">В установки Docker в Windows IP-адрес по умолчанию является 10.0.75.1, как показано на рисунке 4-24.</span><span class="sxs-lookup"><span data-stu-id="1af2a-224">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-24.</span></span>

![](./media/image30.png)

<span data-ttu-id="1af2a-225">Рис. 4-24. Тестирование приложения Docker локально с помощью CURL</span><span class="sxs-lookup"><span data-stu-id="1af2a-225">Figure 4-24: Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="1af2a-226">**Отладка контейнера, запущенного в Docker**</span><span class="sxs-lookup"><span data-stu-id="1af2a-226">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="1af2a-227">Visual Studio Code поддерживает отладки Docker, если вы используете Node.js и других платформ, таких как контейнеры .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1af2a-227">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="1af2a-228">Также можно отлаживать контейнеры .NET Core в Docker при использовании Visual Studio, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="1af2a-228">You also can debug .NET Core containers in Docker when using Visual Studio, as described in the next section.</span></span>

<span data-ttu-id="1af2a-229">**Дополнительные сведения:** Дополнительные сведения об отладке контейнеров Node.js Docker, перейдите к <https://blog.docker.com/2016/07/live-debugging-docker/> и [ https://blogs.msdn.microsoft.com/\ пользователя\_ed/2016/02/27 / Visual-Studio-Code-New-Features-13-Big-Debugging-Updates-Rich-Object-hover-Conditional-Breakpoints-node-js-Mono-More/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).</span><span class="sxs-lookup"><span data-stu-id="1af2a-229">**More info:** To learn more about debugging Node.js Docker containers, go to <https://blog.docker.com/2016/07/live-debugging-docker/> and [https://blogs.msdn.microsoft.com/\ user\_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1af2a-230">[Назад](docker-apps-development-environment.md)
>[Вперед](visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="1af2a-230">[Previous](docker-apps-development-environment.md)
[Next](visual-studio-tools-for-docker.md)</span></span>