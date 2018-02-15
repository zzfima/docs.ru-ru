---
title: "Внутренний цикл разработки рабочего процесса для Docker приложений"
description: "Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3605a6cd53db695de3af015a777e3c1a0e92af58
ms.sourcegitcommit: 672c9cd122c13c9813f57f022c86ebdf6dd69b4f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2018
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="ee907-104">Внутренний цикл разработки рабочего процесса для Docker приложений</span><span class="sxs-lookup"><span data-stu-id="ee907-104">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="ee907-105">Перед тем как запускать внешнего цикла рабочего процесса, охвата всего DevOps цикл, начинаются все процессы на компьютере каждый разработчик, кодирование само приложение, с помощью предпочитаемых языков или платформ и локального тестирования (рис. 4-14).</span><span class="sxs-lookup"><span data-stu-id="ee907-105">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-14).</span></span> <span data-ttu-id="ee907-106">Но в любом случае имеется очень важно в том случае, независимо от того, какой язык, framework или платформ выберите.</span><span class="sxs-lookup"><span data-stu-id="ee907-106">But in every case, you will have a very important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="ee907-107">В этом конкретного рабочего процесса вы всегда разработки и тестирования контейнеры Docker, а на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ee907-107">In this specific workflow, you are always developing and testing Docker containers, but locally.</span></span>

![](./media/image18.png)

<span data-ttu-id="ee907-108">Рис. 4-14: внутренний цикл разработки контекста</span><span class="sxs-lookup"><span data-stu-id="ee907-108">Figure 4-14: Inner-loop development context</span></span>

<span data-ttu-id="ee907-109">Контейнер или экземпляр образа Docker будет содержать следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="ee907-109">The container or instance of a Docker image will contain these components:</span></span>

-   <span data-ttu-id="ee907-110">Выбор операционной системы (например, ОС Linux или Windows)</span><span class="sxs-lookup"><span data-stu-id="ee907-110">An operating system selection (for example, a Linux distribution or Windows)</span></span>

-   <span data-ttu-id="ee907-111">Файлы, добавленные разработчиком (например, двоичные файлы приложения)</span><span class="sxs-lookup"><span data-stu-id="ee907-111">Files added by the developer (for example, app binaries)</span></span>

-   <span data-ttu-id="ee907-112">Конфигурации (например, параметры среды и зависимостей)</span><span class="sxs-lookup"><span data-stu-id="ee907-112">Configuration (for example, environment settings and dependencies)</span></span>

-   <span data-ttu-id="ee907-113">Инструкции по какие процессы с Docker</span><span class="sxs-lookup"><span data-stu-id="ee907-113">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="ee907-114">Можно настроить внутренний цикл разработки рабочего процесса, который использует Docker в качестве процесса (как описано в следующем разделе).</span><span class="sxs-lookup"><span data-stu-id="ee907-114">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="ee907-115">Учитывать начальные этапы настройки среды не включается, поскольку его нужно сделать только один раз.</span><span class="sxs-lookup"><span data-stu-id="ee907-115">Take into account that the initial steps to set up the environment is not included, because you need to do that just once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="ee907-116">Создание одного приложения в контейнере Docker, с помощью кода Visual Studio и Docker CLI</span><span class="sxs-lookup"><span data-stu-id="ee907-116">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="ee907-117">Приложения состоят из собственных служб, а также дополнительные библиотеки (зависимостей).</span><span class="sxs-lookup"><span data-stu-id="ee907-117">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="ee907-118">Рис. 4-15 показывает основные шаги, которые обычно требуются для выполнения при создании приложения Docker, следуют подробное описание каждого шага.</span><span class="sxs-lookup"><span data-stu-id="ee907-118">Figure 4-15 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![](./media/image19.png)

<span data-ttu-id="ee907-119">Рис. 4-15: высокоуровневый рабочий процесс для жизненного цикла для Docker контейнерных приложений с помощью Docker CLI</span><span class="sxs-lookup"><span data-stu-id="ee907-119">Figure 4-15: High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="ee907-120">Шаг 1: Начать кодирование в Visual Studio Code и создание базового уровня начального приложения или службы</span><span class="sxs-lookup"><span data-stu-id="ee907-120">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="ee907-121">Способ разработки приложения очень похоже на способ сделать это без Docker.</span><span class="sxs-lookup"><span data-stu-id="ee907-121">The way you develop your application is pretty similar to the way you do it without Docker.</span></span> <span data-ttu-id="ee907-122">Разница заключается в том, что при разработке, развертывании и тестировании приложения или службы, работающие в контейнеры Docker, помещаются в локальной среде (например, виртуальных Машин с Linux или Windows).</span><span class="sxs-lookup"><span data-stu-id="ee907-122">The difference is that while developing, you are deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="ee907-123">**Настройка локальной среде**</span><span class="sxs-lookup"><span data-stu-id="ee907-123">**Setting up your local environment**</span></span>

<span data-ttu-id="ee907-124">Последние версии Docker для Mac и Windows проще, чем когда-либо для разработки приложений Docker и настройка является простым.</span><span class="sxs-lookup"><span data-stu-id="ee907-124">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

<span data-ttu-id="ee907-125">**Дополнительные сведения о** инструкции по настройке Docker для Windows, см. в [https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/).</span><span class="sxs-lookup"><span data-stu-id="ee907-125">**More info** For instructions on setting up Docker for Windows, go to [https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/).</span></span>

<span data-ttu-id="ee907-126">Инструкции по настройке Docker для Mac, см. в <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="ee907-126">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="ee907-127">Кроме того вам потребуется редактор кода, чтобы фактически можно разрабатывать приложения во время с помощью Docker CLI.</span><span class="sxs-lookup"><span data-stu-id="ee907-127">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="ee907-128">Корпорация Майкрософт предоставляет Visual Studio код, который является простой редактор кода, поддерживается в Windows, Mac и Linux и предоставляет IntelliSense с [для многих языков](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python и большинство современные языки) [отладки](https://code.visualstudio.com/Docs/editor/debugging), [интеграция с Git](https://code.visualstudio.com/Docs/editor/versioncontrol) и [расширения поддержки](https://code.visualstudio.com/docs/extensions/overview).</span><span class="sxs-lookup"><span data-stu-id="ee907-128">Microsoft provides Visual Studio Code, which is a lightweight code editor that is supported on Mac, Windows, and Linux, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="ee907-129">Этот редактор — отлично подходит для разработчиков Mac и Linux.</span><span class="sxs-lookup"><span data-stu-id="ee907-129">This editor is a great fit for Mac and Linux developers.</span></span> <span data-ttu-id="ee907-130">В Windows можно использовать полный приложения Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ee907-130">In Windows, you also can use the full Visual Studio application.</span></span>

<span data-ttu-id="ee907-131">**Дополнительные сведения о** инструкции по установке Visual Studio для Windows, Mac или Linux, перейдите к [http://code.visualstudio.com/docs/setup/setup-overview/https://docs.docker.com/docker-for-mac/](http://code.visualstudio.com/docs/setup/setup-overview/https:/docs.docker.com/docker-for-mac/).</span><span class="sxs-lookup"><span data-stu-id="ee907-131">**More info** For instructions on installing Visual Studio for Windows, Mac, or Linux, go to [http://code.visualstudio.com/docs/setup/setup-overview/https://docs.docker.com/docker-for-mac/](http://code.visualstudio.com/docs/setup/setup-overview/https:/docs.docker.com/docker-for-mac/).</span></span>

<span data-ttu-id="ee907-132">Можно работать с Docker CLI и напишите код, используя любой редактор кода, но при использовании кода Visual Studio упрощает их автора Dockerfile и docker compose.yml файлов в рабочей области.</span><span class="sxs-lookup"><span data-stu-id="ee907-132">You can work with Docker CLI and write your code using any code editor, but if you use Visual Studio Code, it makes it easy to author Dockerfile and docker-compose.yml files in your workspace.</span></span> <span data-ttu-id="ee907-133">Кроме того можно выполнять задачи кода Visual Studio в интегрированной среде разработки, который будет предлагать сценарии, которые могут работать продуманные операций, с помощью Docker CLI под.</span><span class="sxs-lookup"><span data-stu-id="ee907-133">Plus, you can run Visual Studio Code tasks from the IDE that will prompt scripts that can be running elaborated operations using Docker CLI underneath.</span></span>

<span data-ttu-id="ee907-134">Код Visual Studio предоставляется расширение, которое необходимо установить.</span><span class="sxs-lookup"><span data-stu-id="ee907-134">Visual Studio Code is provided by an extension, which you'll need to install.</span></span> <span data-ttu-id="ee907-135">Чтобы сделать это, нажмите клавиши Ctrl + Shift + P, введите **установить ext**, и запустите расширения: установить расширение команду, чтобы открыть список расширений Marketplace.</span><span class="sxs-lookup"><span data-stu-id="ee907-135">To do so, Press Ctrl+Shift+P, type **ext install**, and then run the Extensions: Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="ee907-136">Затем введите **docker** для фильтрации результатов и выберите Dockerfile и создать файл Docker (yml) расширения поддержки, как показано на рисунке 4-16.</span><span class="sxs-lookup"><span data-stu-id="ee907-136">Next, type **docker** to filter the results, and then select the Dockerfile And Docker Compose File (yml) Support extension, as depicted in Figure 4-16.</span></span>

![](./media/image20.png)

<span data-ttu-id="ee907-137">На рисунке 4 — 16: Установка расширения Docker в коде Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ee907-137">Figure 4-16: Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="ee907-138">Шаг 2: Создайте файл DockerFile, связанные с существующим образом (plain операционной системы или среды разработки, как .NET Core, Node.js и Ruby)</span><span class="sxs-lookup"><span data-stu-id="ee907-138">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="ee907-139">Вам потребуется файл DockerFile каждого пользовательского образа для сборки и каждой контейнера должны быть развернуты, таким образом, если приложение состоит из одной пользовательской службы, потребуется один DockerFile.</span><span class="sxs-lookup"><span data-stu-id="ee907-139">You will need a DockerFile per custom image to be built and per container to be deployed, therefore, if your app is made up of a single custom service, you will need a single DockerFile.</span></span> <span data-ttu-id="ee907-140">Но если приложение состоит из нескольких служб (как для архитектуры микрослужбами), вам потребуется один Dockerfile каждой службы.</span><span class="sxs-lookup"><span data-stu-id="ee907-140">But, if your app is composed of multiple services (as in a microservices architecture), you'll need one Dockerfile per service.</span></span>

<span data-ttu-id="ee907-141">DockerFile обычно размещается в корневой папке приложения или службы и содержит требуемые команды, так что Docker знает, как для установки и запуска данного приложения или службы.</span><span class="sxs-lookup"><span data-stu-id="ee907-141">The DockerFile is usually placed within the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="ee907-142">Можно создать DockerFile и добавить его в проект вместе с коде (node.js .NET Core, т. д.), или, если вы новичок в среду, взгляните на следующие подсказки.</span><span class="sxs-lookup"><span data-stu-id="ee907-142">You can create your DockerFile and add it to your project along with your code (node.js, .NET Core, etc.), or, if you are new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
> <span data-ttu-id="ee907-143">Можно использовать программу командной строки [ё docker](https://github.com/Microsoft/generator-docker), что закрепление файлов из проекта на языке, выберите и добавляет необходимые файлы конфигурации Docker.</span><span class="sxs-lookup"><span data-stu-id="ee907-143">You can use a command-line tool called [yo docker](https://github.com/Microsoft/generator-docker), which scaffolds files from your project in the language you choose and adds the required Docker configuration files.</span></span> <span data-ttu-id="ee907-144">По сути, помогающее разработчикам Приступая к работе, он создает соответствующий файл DockerFile, docker compose.yml и другие связанные сценарии, чтобы построить и запустить в контейнеры Docker.</span><span class="sxs-lookup"><span data-stu-id="ee907-144">Basically, to assist developers getting started, it creates the appropriate DockerFile, docker-compose.yml, and other associated scripts to build and run your Docker containers.</span></span> <span data-ttu-id="ee907-145">Этот генератор yeoman отобразится запрос на несколько вопросов, попросить выбранных разработки языка и конечный узел контейнера.</span><span class="sxs-lookup"><span data-stu-id="ee907-145">This yeoman generator will prompt you with a few questions, asking your selected development language and destination container host.</span></span>

![ё docker](./media/image21.png)

<span data-ttu-id="ee907-147">Для экземпляра на рисунке 4-17 показано два снимка экрана из терминалов в Windows и на компьютере Mac, в обоих случаях работе ё docker, который создаст образцов кода проектов (в настоящее время .NET Core, Golang и Node.js от поддерживаемых языков) уже настроен для работы с Начало Docker.</span><span class="sxs-lookup"><span data-stu-id="ee907-147">For instance, Figure 4-17 shows two screenshots from the terminals in Windows and on a Mac, in both cases, running yo docker, which will generate the sample code projects (currently .NET Core, Golang, and Node.js as supported languages) already configured to work on top of Docker.</span></span>

![](./media/image22.PNG)  ![](./media/image23.png)

<span data-ttu-id="ee907-148">На рисунке 4 — 17: ё docker программу командной в Windows (слева) и на компьютере Mac</span><span class="sxs-lookup"><span data-stu-id="ee907-148">Figure 4-17: yo docker command tool in Windows (left) and on a Mac</span></span>

<span data-ttu-id="ee907-149">На рисунке 4-18 представлен пример, с помощью ё docker после того как вы существующий проект .NET Core на месте, быть формирования шаблонов.</span><span class="sxs-lookup"><span data-stu-id="ee907-149">Figure 4-18 presents an example using yo docker after you have an existing .NET Core project in place to be scaffolded.</span></span>

![](./media/image24.PNG)

<span data-ttu-id="ee907-150">На рисунке 4 — 18: ё docker с существующие .NET Core проекта на месте</span><span class="sxs-lookup"><span data-stu-id="ee907-150">Figure 4-18: yo docker with an existing .NET Core project in place</span></span>

<span data-ttu-id="ee907-151">Из файла DockerFile укажите какие базового образа Docker, вы будете использовать (например, с помощью «от microsoft/dotnet:1.0.0-core»).</span><span class="sxs-lookup"><span data-stu-id="ee907-151">From the DockerFile, you specify what base Docker image you'll be using (like using "FROM microsoft/dotnet:1.0.0-core").</span></span> <span data-ttu-id="ee907-152">Обычно мы соберем настраиваемого образа на основе базового образа, можно получить из любой официальный репозиторий в [реестр Docker Hub](https://hub.docker.com/) (как [изображения для .NET Core](https://hub.docker.com/r/microsoft/dotnet/) или один [для Node.js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="ee907-152">You usually will build your custom image on top of a base image that you can get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/r/microsoft/dotnet/) or one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="ee907-153">***Вариант а используйте официальный существующего образа Docker***</span><span class="sxs-lookup"><span data-stu-id="ee907-153">***Option A: Use an existing official Docker image***</span></span>

<span data-ttu-id="ee907-154">Использование официальный репозиторий стека языка с номером версии гарантирует, что на всех компьютерах (включая разработку, тестирование и производственной) доступны те же возможности языка.</span><span class="sxs-lookup"><span data-stu-id="ee907-154">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="ee907-155">Ниже приведен образец файла DockerFile для контейнера .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ee907-155">Following is a sample DockerFile for a .NET Core container:</span></span>

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

<span data-ttu-id="ee907-156">В этом случае он использует версии 1.0.1 официальный образа ASP.NET Core Docker для Linux с именем microsoft/aspnetcore:1.0.1.</span><span class="sxs-lookup"><span data-stu-id="ee907-156">In this case, it is using the version 1.0.1 of the official ASP.NET Core Docker image for Linux named microsoft/aspnetcore:1.0.1.</span></span> <span data-ttu-id="ee907-157">Для получения дополнительных сведений обратитесь к [страницы образа Docker ASP.NET Core](https://hub.docker.com/r/microsoft/aspnetcore/) и [образа Docker .NET Core страницы](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="ee907-157">For further details, consult the [ASP.NET Core Docker Image page](https://hub.docker.com/r/microsoft/aspnetcore/) and the [.NET Core Docker Image page](https://hub.docker.com/r/microsoft/dotnet/).</span></span> <span data-ttu-id="ee907-158">Вы также может использовать другое изображение сопоставимых как узел: 4-onbuild для Node.js или много других предварительно настроенных образов для языков разработки, которые можно найти по адресу [Docker Hub](https://hub.docker.com/explore/).</span><span class="sxs-lookup"><span data-stu-id="ee907-158">You also could be using another comparable image like node:4-onbuild for Node.js, or many other preconfigured images for development languages, which are available at [Docker Hub](https://hub.docker.com/explore/).</span></span>

<span data-ttu-id="ee907-159">В файле DockerFile необходимо также указать Docker для прослушивания TCP-порт, который будет использоваться во время выполнения (например, порт 80).</span><span class="sxs-lookup"><span data-stu-id="ee907-159">In the DockerFile, you also need to instruct Docker to listen to the TCP port that you will use at runtime (such as port 80).</span></span>

<span data-ttu-id="ee907-160">Существуют другие строки конфигурации, которые можно добавить в файл DockerFile в зависимости от языка и framework, которую вы используете, поэтому Docker знает, как запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="ee907-160">There are other lines of configuration that you can add in the DockerFile depending on the language/framework you are using, so Docker knows how to run the app.</span></span> <span data-ttu-id="ee907-161">Для экземпляра, необходимо в строку ENTRYPOINT \[«dotnet», «MyCustomMicroservice.dll»\] для запуска приложения .NET Core, несмотря на то, что у вас есть несколько вариантов в зависимости от подхода для построения и запуска службы.</span><span class="sxs-lookup"><span data-stu-id="ee907-161">For instance, you need the ENTRYPOINT line with \["dotnet", "MyCustomMicroservice.dll"\] to run a .NET Core app, although you can have multiple variants depending on the approach to build and run your service.</span></span> <span data-ttu-id="ee907-162">При использовании пакета SDK и dotnet CLI построение и запуск приложения .NET было бы немного отличается.</span><span class="sxs-lookup"><span data-stu-id="ee907-162">If you're using the SDK and dotnet CLI to build and run the .NET app, it would be slightly different.</span></span> <span data-ttu-id="ee907-163">В конечном счете является что ENTRYPOINT строки, а также дополнительные строки будут отличаться в зависимости от языка или платформу, которая выбирается для приложения.</span><span class="sxs-lookup"><span data-stu-id="ee907-163">The bottom line is that the ENTRYPOINT line plus additional lines will be different depending on the language/platform you choose for your application.</span></span>

<span data-ttu-id="ee907-164">**Дополнительные сведения о** сведения о создании образов Docker для приложений .NET Core, перейдите к <https://docs.microsoft.com/dotnet/articles/core/docker/building-net-docker-images>.</span><span class="sxs-lookup"><span data-stu-id="ee907-164">**More info** For information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/articles/core/docker/building-net-docker-images>.</span></span>

<span data-ttu-id="ee907-165">Дополнительные сведения о создании собственных образов, перейдите к [https://docs.docker.com/engine/ \учебники/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).</span><span class="sxs-lookup"><span data-stu-id="ee907-165">To learn more about building your own images, go to [https://docs.docker.com/engine/\ tutorials/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).</span></span>

<span data-ttu-id="ee907-166">**Репозитории многоплатформенного изображения**</span><span class="sxs-lookup"><span data-stu-id="ee907-166">**Multiplatform image repositories**</span></span>

<span data-ttu-id="ee907-167">Как контейнеры Windows становятся более широкое распространение, одном репозитории может содержать вариантов платформы, например образ Windows и Linux.</span><span class="sxs-lookup"><span data-stu-id="ee907-167">As Windows containers become more prevalent, a single repository can contain platform variants, such as a Linux and Windows image.</span></span> <span data-ttu-id="ee907-168">Это новая функция, поступающих в Docker, позволяющий поставщикам использование одного репозитория для охвата нескольких платформ, таких как [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) репозитория, которая находится на DockerHub реестра.</span><span class="sxs-lookup"><span data-stu-id="ee907-168">This is a new feature coming in Docker that makes it possible for vendors to use a single repository to cover multiple platforms, such as [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repository, which is available at DockerHub registry.</span></span> <span data-ttu-id="ee907-169">Как компонент перейдет в активном состоянии, извлечение этого образа из узла Windows будет получать Windows variant, в то время как извлечение тем же именем образа из узла Linux будет получать Linux variant.</span><span class="sxs-lookup"><span data-stu-id="ee907-169">As the feature comes alive, pulling this image from a Windows host will pull the Windows variant, whereas pulling the same image name from a Linux host will pull the Linux variant.</span></span>

<span data-ttu-id="ee907-170">***Вариант б. Создание основной образ с нуля***</span><span class="sxs-lookup"><span data-stu-id="ee907-170">***Option B: Create your base image from scratch***</span></span>

<span data-ttu-id="ee907-171">Собственный базовый образ Docker можно создать с нуля, как описано в этом [статьи](https://docs.docker.com/engine/userguide/eng-image/baseimages/) из Docker.</span><span class="sxs-lookup"><span data-stu-id="ee907-171">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="ee907-172">Это сценарий, возможно, не лучше всего подходит для вас при запуске только с помощью Docker, но если вы хотите задать определенные биты базового образа, это можно сделать.</span><span class="sxs-lookup"><span data-stu-id="ee907-172">This is a scenario that is probably not best for you if you are just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="ee907-173">Шаг 3: Создание пользовательских образов Docker внедрения службы в ней</span><span class="sxs-lookup"><span data-stu-id="ee907-173">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="ee907-174">Для каждой пользовательской службы состоит из приложения необходимо будет создать связанные изображения.</span><span class="sxs-lookup"><span data-stu-id="ee907-174">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="ee907-175">Если приложение состоит из одной службы или веб-приложение, вам потребуется всего одним изображением.</span><span class="sxs-lookup"><span data-stu-id="ee907-175">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
> <span data-ttu-id="ee907-176">При учете «рабочий процесс DevOps внешний цикл», изображений будет создан автоматизированный процесс построения всякий раз, когда push исходный код репозитория (непрерывной интеграции), поэтому образы будут созданы в этой среде глобальных из вашей исходный код.</span><span class="sxs-lookup"><span data-stu-id="ee907-176">When taking into account the "outer-loop DevOps workflow," the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration) so the images will be created in that global environment from your source code.</span></span>

<span data-ttu-id="ee907-177">Но прежде чем мы рассмотрим переход в этом маршруте внешний цикл, необходимо убедиться, что приложение Docker фактически работает должным образом, чтобы они не push код, который может работать неправильно для системы управления версиями (Git, и т. д.).</span><span class="sxs-lookup"><span data-stu-id="ee907-177">But, before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>

<span data-ttu-id="ee907-178">Таким образом каждый разработчик сначала должен выполнить весь процесс внутреннего цикла для локального тестирования и продолжать разработку, пока они хотят принудительно функцию завершения, либо изменить систему управления версиями.</span><span class="sxs-lookup"><span data-stu-id="ee907-178">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="ee907-179">Для создания образа в локальной среде и с помощью файла DockerFile, можно использовать команду сборки docker, как показано на рисунке 4-19 (также можно запустить составления docker копирование--сборки для приложений, сформирован несколько контейнеров или служб).</span><span class="sxs-lookup"><span data-stu-id="ee907-179">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-19 (you also can run docker-compose up --build for applications composed by several containers/services).</span></span>

![](./media/image25.png)

<span data-ttu-id="ee907-180">На рисунке 4-19: под управлением сборки docker</span><span class="sxs-lookup"><span data-stu-id="ee907-180">Figure 4-19: Running docker build</span></span>

<span data-ttu-id="ee907-181">При необходимости вместо непосредственного использования docker сборки из папки проекта, вы сначала можно создать развертываемый папки с библиотеками .NET, необходимо с помощью выполнения dotnet команда публикации, а затем запустите сборки docker.</span><span class="sxs-lookup"><span data-stu-id="ee907-181">Optionally, instead of directly running docker build from the project's folder, you first can generate a deployable folder with the .NET libraries needed by using the run dotnet publish command, and then run docker build.</span></span>

<span data-ttu-id="ee907-182">В этом примере создается образ Docker с именем cesardl и netcore-webapi микрослужбу-docker: первый (: первого — тег, например определенную версию).</span><span class="sxs-lookup"><span data-stu-id="ee907-182">In this example, this creates a Docker image with the name cesardl/netcore-webapi-microservice-docker:first (:first is a tag, like a specific version).</span></span> <span data-ttu-id="ee907-183">Можно выполнить этот шаг для каждого настраиваемого образа, необходимые для создания составных приложений Docker с помощью несколько контейнеров.</span><span class="sxs-lookup"><span data-stu-id="ee907-183">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="ee907-184">Можно найти существующие образы в ваш локальный репозиторий (компьютере разработки) с помощью docker команда изображений, как показано на рисунке 4 до 20.</span><span class="sxs-lookup"><span data-stu-id="ee907-184">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-20.</span></span>

![](./media/image26.png)

<span data-ttu-id="ee907-185">На рисунке 4 до 20: Просмотр существующих образов на основе образов docker</span><span class="sxs-lookup"><span data-stu-id="ee907-185">Figure 4-20: Viewing existing images using docker images</span></span>

### <a name="step-4-optional-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="ee907-186">Шаг 4: Определение (необязательно) служб в docker compose.yml при создании составных Docker приложения с несколькими службами</span><span class="sxs-lookup"><span data-stu-id="ee907-186">Step 4: (Optional) Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="ee907-187">В файле docker compose.yml можно определить набор связанных служб для развертывания в виде составных приложений с помощью команд развертывания, см. Далее раздел шага.</span><span class="sxs-lookup"><span data-stu-id="ee907-187">With the docker-compose.yml file you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="ee907-188">Необходимо создать этот файл в ваш основной или корневую папку решения; он должен иметь аналогичное содержимое в следующий файл docker compose.yml:</span><span class="sxs-lookup"><span data-stu-id="ee907-188">You need to create that file in your main or root solution folder; it should have a similar content to the following docker-compose.yml file:</span></span>

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

<span data-ttu-id="ee907-189">В данном случае этот файл определяет две службы: веб-службы (пользовательские службы) и redis службы (популярные кэша).</span><span class="sxs-lookup"><span data-stu-id="ee907-189">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="ee907-190">Каждая служба будет развертываться как контейнер, поэтому необходимо использовать конкретный образ Docker для каждого.</span><span class="sxs-lookup"><span data-stu-id="ee907-190">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="ee907-191">Для определенного веб-службу изображения необходимо сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="ee907-191">For this particular web service, the image will need to do the following:</span></span>

-   <span data-ttu-id="ee907-192">Сборки из файла DockerFile в текущем каталоге</span><span class="sxs-lookup"><span data-stu-id="ee907-192">Build from the DockerFile in the current directory</span></span>

-   <span data-ttu-id="ee907-193">Пересылать предоставленный порт 80 для контейнера, чтобы порт 81 на хост-компьютере</span><span class="sxs-lookup"><span data-stu-id="ee907-193">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

-   <span data-ttu-id="ee907-194">Подключите каталог проекта на узле/Code в контейнере, благодаря чему можно изменять код без необходимости перестроения изображения</span><span class="sxs-lookup"><span data-stu-id="ee907-194">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

-   <span data-ttu-id="ee907-195">Связать веб-службы для службы redis</span><span class="sxs-lookup"><span data-stu-id="ee907-195">Link the web service to the redis service</span></span>

<span data-ttu-id="ee907-196">Служба использует redis [последний открытый redis образ](https://hub.docker.com/_/redis/) извлечено из реестра Docker Hub.</span><span class="sxs-lookup"><span data-stu-id="ee907-196">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="ee907-197">[redis](http://redis.io/) — это система популярным кэша для серверных приложений.</span><span class="sxs-lookup"><span data-stu-id="ee907-197">[redis](http://redis.io/) is a very popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="ee907-198">Шаг 5: Построение и запуск приложения Docker</span><span class="sxs-lookup"><span data-stu-id="ee907-198">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="ee907-199">Если ваше приложение имеет только один контейнер, необходимо просто запустите его, развернув узел Docker (физический сервер или ВМ).</span><span class="sxs-lookup"><span data-stu-id="ee907-199">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="ee907-200">Тем не менее, если приложение состоит из нескольких служб, необходимо *комбинирование ее*, также.</span><span class="sxs-lookup"><span data-stu-id="ee907-200">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="ee907-201">Давайте посмотрим, различные варианты.</span><span class="sxs-lookup"><span data-stu-id="ee907-201">Let's see the different options.</span></span>

<span data-ttu-id="ee907-202">***Параметр выполнения ответ одного контейнера или службы***</span><span class="sxs-lookup"><span data-stu-id="ee907-202">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="ee907-203">Образ Docker можно выполнить с помощью docker, выполните команду, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="ee907-203">You can run the Docker image by using the docker run command, as shown here:</span></span>

```
docker run -t -d -p 80:5000
cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="ee907-204">Обратите внимание, что для этого конкретного развертывания мы будем перенаправляться запросы, отправленные на порт 80, внутренний порт 5000.</span><span class="sxs-lookup"><span data-stu-id="ee907-204">Note that for this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="ee907-205">Теперь приложение прослушивает внешний порт 80 на уровне узла.</span><span class="sxs-lookup"><span data-stu-id="ee907-205">Now, the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="ee907-206">***Вариант б. Составление и запуск приложения-контейнера несколько***</span><span class="sxs-lookup"><span data-stu-id="ee907-206">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="ee907-207">В большинстве случаев корпоративного приложения Docker будет состоять из нескольких служб.</span><span class="sxs-lookup"><span data-stu-id="ee907-207">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="ee907-208">В этих случаях можно выполнить команду docker составления вверх (на рисунке 4-21), который будет использовать файл docker compose.yml, созданные ранее.</span><span class="sxs-lookup"><span data-stu-id="ee907-208">For these cases, you can run the command docker-compose up (Figure 4-21), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="ee907-209">Выполнение этой команды развертывает состоит приложение со всеми его связанных контейнеров.</span><span class="sxs-lookup"><span data-stu-id="ee907-209">Running this command deploys a composed application with all of its related containers.</span></span>

![](./media/image27.png)

<span data-ttu-id="ee907-210">На рисунке 4-21: результаты выполнения команды «docker-compose вверх»</span><span class="sxs-lookup"><span data-stu-id="ee907-210">Figure 4-21: Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="ee907-211">После запуска docker-составления вверх, развертывания приложения и его связанных контейнеров в узла Docker, как показано в на рисунке 4-22 в представлении виртуальных Машин.</span><span class="sxs-lookup"><span data-stu-id="ee907-211">After you run docker-compose up, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-22, in the VM representation.</span></span>

![](./media/image28.png)

<span data-ttu-id="ee907-212">На рисунке 4-22: виртуальной Машины с помощью развертывания контейнеров Docker</span><span class="sxs-lookup"><span data-stu-id="ee907-212">Figure 4-22: VM with Docker containers deployed</span></span>

<span data-ttu-id="ee907-213">Примечание docker создания копии и запуска docker может оказаться достаточно для тестирования вашей контейнеры в среде разработки, но можно не использовать их вообще, если вы предполагаете, для работы с кластерами Docker и orchestrators, например помощью Docker Swarm Mesosphere DC/OS и Kubernetes Чтобы иметь возможность увеличения масштаба.</span><span class="sxs-lookup"><span data-stu-id="ee907-213">Note docker-compose up and docker run might be enough for testing your containers in your development environment, but you might not use them at all if you are expecting to work with Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes in order to be able to scale up.</span></span> <span data-ttu-id="ee907-214">Если вы используете кластер как [режиме с помощью Docker Swarm](https://docs.docker.com/engine/swarm/) (доступно в Docker для Windows и Mac с версии 1.12), необходимо развернуть и протестировать дополнительные команды, такие, как создать службу docker для одной службы или во время развертывание приложения, состоящие из нескольких контейнеров, с помощью docker создания пакета и docker развертывание myBundleFile, по для развертывания приложения состоит в стек, как описано в статье [наборы распределенных приложений](https://blog.docker.com/2016/06/docker-app-bundle/) из Docker.</span><span class="sxs-lookup"><span data-stu-id="ee907-214">If you're using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker for Windows and Mac since version 1.12), you need to deploy and test with additional commands such as docker service create for single services, or when you're deploying an app composed of several containers, using docker compose bundle and docker deploy myBundleFile, by deploying the composed app as a stack, as explained in the article [Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) from Docker.</span></span>

<span data-ttu-id="ee907-215">Для [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) и [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) развертывания команды и сценарии, а также используются.</span><span class="sxs-lookup"><span data-stu-id="ee907-215">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) you would use different deployment commands and scripts, as well.</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="ee907-216">Шаг 6: Тестирование приложения Docker (локально, в локальной ВМ компакт-диска)</span><span class="sxs-lookup"><span data-stu-id="ee907-216">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="ee907-217">Этот шаг будет зависеть от действия приложения.</span><span class="sxs-lookup"><span data-stu-id="ee907-217">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="ee907-218">В очень простой .NET Core веб-API «Hello World» развернуто как в одном контейнере или службу необходимо только для доступа к службе, предоставляя TCP-порт, указанный в DockerFile.</span><span class="sxs-lookup"><span data-stu-id="ee907-218">In a very simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="ee907-219">Если localhost еще не включен, для перехода к службе, найти IP-адрес для компьютера с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="ee907-219">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

<span data-ttu-id="ee907-220">машины docker ip *ваше имя контейнера*</span><span class="sxs-lookup"><span data-stu-id="ee907-220">docker-machine ip *your-container-name*</span></span>

<span data-ttu-id="ee907-221">На узле Docker откройте браузер и перейдите к этому сайту; Вы увидите работающей, приложения или службы, как показано на рисунке 4 до 23.</span><span class="sxs-lookup"><span data-stu-id="ee907-221">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-23.</span></span>

![](./media/image29.png)

<span data-ttu-id="ee907-222">На рисунке 4 до 23: тестирования приложения Docker локально с помощью localhost</span><span class="sxs-lookup"><span data-stu-id="ee907-222">Figure 4-23: Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="ee907-223">Обратите внимание, что он использует порт 80, но внутренним образом был перенаправляемой порт 5000, так как это, как он был развернут с помощью docker при запуске, как было описано выше.</span><span class="sxs-lookup"><span data-stu-id="ee907-223">Note that it is using port 80, but internally it was being redirected to port 5000, because that's how it was deployed with docker run, as explained earlier.</span></span>

<span data-ttu-id="ee907-224">Это можно проверить с помощью ПЕРЕЛИСТЫВАНИЕ из терминала.</span><span class="sxs-lookup"><span data-stu-id="ee907-224">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="ee907-225">В Windows при установке Docker IP-адрес по умолчанию — 10.0.75.1, как показано на рисунке 4-24.</span><span class="sxs-lookup"><span data-stu-id="ee907-225">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-24.</span></span>

![](./media/image30.png)

<span data-ttu-id="ee907-226">На рисунке 4 – 24: тестирование Docker приложения локально с помощью CURL</span><span class="sxs-lookup"><span data-stu-id="ee907-226">Figure 4-24: Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="ee907-227">**Отладка контейнера, запущенного на Docker**</span><span class="sxs-lookup"><span data-stu-id="ee907-227">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="ee907-228">Кода Visual Studio поддерживает отладки Docker, если вы используете Node.js и другие платформы, такие как контейнеры .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ee907-228">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="ee907-229">Также можно отлаживать .NET Core контейнеры Docker при использовании Visual Studio, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="ee907-229">You also can debug .NET Core containers in Docker when using Visual Studio, as described in the next section.</span></span>

<span data-ttu-id="ee907-230">**Дополнительные сведения:** Дополнительные сведения об отладке контейнеры Node.js Docker, перейдите к <https://blog.docker.com/2016/07/live-debugging-docker/> и [https://blogs.msdn.microsoft.com/ \ пользователь\_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).</span><span class="sxs-lookup"><span data-stu-id="ee907-230">**More info:** To learn more about debugging Node.js Docker containers, go to <https://blog.docker.com/2016/07/live-debugging-docker/> and [https://blogs.msdn.microsoft.com/\ user\_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="ee907-231">[Предыдущие] (docker приложения development-environment.md) [Далее] (visual средств studio для docker.md)</span><span class="sxs-lookup"><span data-stu-id="ee907-231">[Previous] (docker-apps-development-environment.md) [Next] (visual-studio-tools-for-docker.md)</span></span>
