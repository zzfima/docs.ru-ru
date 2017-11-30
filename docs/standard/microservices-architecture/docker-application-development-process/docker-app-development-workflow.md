---
title: "Рабочий процесс разработки для приложений Docker"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Рабочий процесс разработки для приложений Docker"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 5a53aee4261a5a0bfc25b3520c50cf505b84f287
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="development-workflow-for-docker-apps"></a><span data-ttu-id="f37a9-104">Рабочий процесс разработки для приложений Docker</span><span class="sxs-lookup"><span data-stu-id="f37a9-104">Development workflow for Docker apps</span></span>

<span data-ttu-id="f37a9-105">Жизненный цикл разработки приложений начинается каждому разработчику компьютера, где разработчик коды приложения, использующего язык и проверяет его локально.</span><span class="sxs-lookup"><span data-stu-id="f37a9-105">The application development lifecycle starts at each developer’s machine, where the developer codes the application using their preferred language and tests it locally.</span></span> <span data-ttu-id="f37a9-106">Независимо от того, какой язык, framework и платформы, разработчик выбирает в этом рабочем процессе разработчик всегда разработка и тестирование контейнеры Docker, но это локально.</span><span class="sxs-lookup"><span data-stu-id="f37a9-106">No matter which language, framework, and platform the developer chooses, with this workflow, the developer is always developing and testing Docker containers, but doing so locally.</span></span>

<span data-ttu-id="f37a9-107">Каждый контейнер (экземпляр образа Docker) включает следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="f37a9-107">Each container (an instance of a Docker image) includes the following components:</span></span>

-   <span data-ttu-id="f37a9-108">Выбор операционной системы (например, ОС Linux, Nano Windows Server или Windows Server Core).</span><span class="sxs-lookup"><span data-stu-id="f37a9-108">An operating system selection (for example, a Linux distribution, Windows Nano Server, or Windows Server Core).</span></span>

-   <span data-ttu-id="f37a9-109">Файлы, добавленные разработчиком (двоичные файлы приложения, и т. д.).</span><span class="sxs-lookup"><span data-stu-id="f37a9-109">Files added by the developer (application binaries, etc.).</span></span>

-   <span data-ttu-id="f37a9-110">Сведения о конфигурации (переменные окружения и зависимости).</span><span class="sxs-lookup"><span data-stu-id="f37a9-110">Configuration information (environment settings and dependencies).</span></span>

## <a name="workflow-for-developing-docker-container-based-applications"></a><span data-ttu-id="f37a9-111">Рабочий процесс для разработки приложений контейнера Docker</span><span class="sxs-lookup"><span data-stu-id="f37a9-111">Workflow for developing Docker container-based applications</span></span>

<span data-ttu-id="f37a9-112">В этом разделе описываются *внутренний цикл* рабочего процесса разработки для приложений на базе контейнер Docker.</span><span class="sxs-lookup"><span data-stu-id="f37a9-112">This section describes the *inner-loop* development workflow for Docker container-based applications.</span></span> <span data-ttu-id="f37a9-113">Внутренний цикл рабочего процесса означает его не принимая во внимание более широкой DevOps рабочего процесса и просто фокусируется на работу разработки на компьютере разработчика.</span><span class="sxs-lookup"><span data-stu-id="f37a9-113">The inner-loop workflow means it is not taking into account the broader DevOps workflow and just focuses on the development work done on the developer’s computer.</span></span> <span data-ttu-id="f37a9-114">Начальные этапы настройки среды, не включаются, так как те, выполняются только один раз.</span><span class="sxs-lookup"><span data-stu-id="f37a9-114">The initial steps to set up the environment are not included, since those are done only once.</span></span>

<span data-ttu-id="f37a9-115">Приложение состоит из службы и дополнительные библиотеки (зависимостей).</span><span class="sxs-lookup"><span data-stu-id="f37a9-115">An application is composed of your own services plus additional libraries (dependencies).</span></span> <span data-ttu-id="f37a9-116">Ниже приведены основные шаги, которые обычно предпринять при построении приложения Docker, как показано на рисунке 5-1.</span><span class="sxs-lookup"><span data-stu-id="f37a9-116">The following are the basic steps you usually take when building a Docker application, as illustrated in Figure 5-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="f37a9-117">**Рис. 5-1.**</span><span class="sxs-lookup"><span data-stu-id="f37a9-117">**Figure 5-1.**</span></span> <span data-ttu-id="f37a9-118">Пошаговые рабочего процесса для разработки приложений помещать в контейнеры Docker</span><span class="sxs-lookup"><span data-stu-id="f37a9-118">Step-by-step workflow for developing Docker containerized apps</span></span>

<span data-ttu-id="f37a9-119">В этом руководстве подробно описан процесс целиком и каждый важный шаг описан сосредоточиться на среде Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f37a9-119">In this guide, this whole process is detailed and every major step is explained by focusing on a Visual Studio environment.</span></span>

<span data-ttu-id="f37a9-120">При использовании подхода разработки редактора или CLI (например, Visual Studio Code плюс Docker CLI на macOS или Windows), необходимо знать все шаги, как правило, более подробно, чем при использовании Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f37a9-120">When you are using an editor/CLI development approach (for example, Visual Studio Code plus Docker CLI on macOS or Windows), you need to know every step, generally in more detail than if you are using Visual Studio.</span></span> <span data-ttu-id="f37a9-121">Дополнительные сведения о работе в среде CLI см. электронную [жизненного цикла помещать в контейнеры Docker приложения с платформы Майкрософт и средств](http://aka.ms/dockerlifecycleebook/).</span><span class="sxs-lookup"><span data-stu-id="f37a9-121">For more details about working in a CLI environment, refer to the e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](http://aka.ms/dockerlifecycleebook/).</span></span>

<span data-ttu-id="f37a9-122">При использовании Visual Studio 2015 или Visual Studio 2017 г., многие из этих действий обрабатываются для вас, что значительно повышает производительность.</span><span class="sxs-lookup"><span data-stu-id="f37a9-122">When you are using Visual Studio 2015 or Visual Studio 2017, many of those steps are handled for you, which dramatically improves your productivity.</span></span> <span data-ttu-id="f37a9-123">Это особенно важно в тех случаях, когда используется Visual Studio 2017 г. и предназначенных для нескольких контейнера приложений.</span><span class="sxs-lookup"><span data-stu-id="f37a9-123">This is especially true when you are using Visual Studio 2017 and targeting multi-container applications.</span></span> <span data-ttu-id="f37a9-124">Для экземпляра только одним щелчком мыши, Visual Studio добавляет файл Dockerfile и docker compose.yml в проекты с конфигурацией для вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="f37a9-124">For instance, with just one mouse click, Visual Studio adds the Dockerfile and docker-compose.yml file to your projects with the configuration for your application.</span></span> <span data-ttu-id="f37a9-125">При запуске приложения в Visual Studio сборке образа Docker и выполнении приложения-контейнера несколькими непосредственно в Docker; даже позволяет отлаживать сразу несколько контейнеров.</span><span class="sxs-lookup"><span data-stu-id="f37a9-125">When you run the application in Visual Studio, it builds the Docker image and runs the multi-container application directly in Docker; it even allows you to debug several containers at once.</span></span> <span data-ttu-id="f37a9-126">Эти функции будут значительно повысить скорость разработки.</span><span class="sxs-lookup"><span data-stu-id="f37a9-126">These features will boost your development speed.</span></span>

<span data-ttu-id="f37a9-127">Однако только потому, что Visual Studio автоматизирует эти действия не означает не нужно знать, что по ним с помощью Docker.</span><span class="sxs-lookup"><span data-stu-id="f37a9-127">However, just because Visual Studio makes those steps automatic does not mean that you do not need to know what is going on underneath with Docker.</span></span> <span data-ttu-id="f37a9-128">Таким образом в указанных рекомендаций мы подробно описывается каждый этап.</span><span class="sxs-lookup"><span data-stu-id="f37a9-128">Therefore, in the guidance that follows, we detail every step.</span></span>

![](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a><span data-ttu-id="f37a9-129">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="f37a9-129">Step 1.</span></span> <span data-ttu-id="f37a9-130">Начать создание кода и создания начального приложения или базовой службы</span><span class="sxs-lookup"><span data-stu-id="f37a9-130">Start coding and create your initial application or service baseline</span></span>

<span data-ttu-id="f37a9-131">Разработка приложения Docker аналогично тому, как разрабатывать приложение без Docker.</span><span class="sxs-lookup"><span data-stu-id="f37a9-131">Developing a Docker application is similar to the way you develop an application without Docker.</span></span> <span data-ttu-id="f37a9-132">Разница заключается в том, что при разработке для Docker, развертывании и тестировании приложения или службы, работающие в контейнеры Docker в локальной среде.</span><span class="sxs-lookup"><span data-stu-id="f37a9-132">The difference is that while developing for Docker, you are deploying and testing your application or services running within Docker containers in your local environment.</span></span> <span data-ttu-id="f37a9-133">Контейнер может быть контейнер Linux или контейнера Windows.</span><span class="sxs-lookup"><span data-stu-id="f37a9-133">The container can be either a Linux container or a Windows container.</span></span>

### <a name="set-up-your-local-environment-with-visual-studio"></a><span data-ttu-id="f37a9-134">Настройка локальной среды с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f37a9-134">Set up your local environment with Visual Studio</span></span>

<span data-ttu-id="f37a9-135">Чтобы начать, убедитесь, что у вас есть [Docker Community Edition (CE)](https://www.docker.com/community-edition) для Windows установлены, как описано в следующих инструкциях:</span><span class="sxs-lookup"><span data-stu-id="f37a9-135">To begin, make sure you have [Docker Community Edition (CE)](https://www.docker.com/community-edition) for Windows installed, as explained in the following instructions:</span></span>

[<span data-ttu-id="f37a9-136">Начало работы с Docker CE для Windows</span><span class="sxs-lookup"><span data-stu-id="f37a9-136">Get started with Docker CE for Windows</span></span>](https://docs.docker.com/docker-for-windows/)

<span data-ttu-id="f37a9-137">Кроме того вам потребуется Visual Studio установлена 2017 г.</span><span class="sxs-lookup"><span data-stu-id="f37a9-137">In addition, you will need Visual Studio 2017 installed.</span></span> <span data-ttu-id="f37a9-138">Этот метод является предпочтительным по Visual Studio 2015 с набором средств Visual Studio для Docker надстройки, поскольку 2017 г. Visual Studio реализованы дополнительные поддержка Docker, такие как поддержка отладки контейнеров.</span><span class="sxs-lookup"><span data-stu-id="f37a9-138">This is preferred over Visual Studio 2015 with the Visual Studio Tools for Docker add-in, because Visual Studio 2017 has more advanced support for Docker, like support for debugging containers.</span></span> <span data-ttu-id="f37a9-139">Visual Studio 2017 г. включает инструментарий для Docker, если вы выбрали **.NET Core и Docker** рабочей нагрузки во время установки, как показано на рисунке 5-2.</span><span class="sxs-lookup"><span data-stu-id="f37a9-139">Visual Studio 2017 includes the tooling for Docker if you selected the **.NET Core and Docker** workload during installation, as shown in Figure 5-2.</span></span>

![](./media/image3.png)

<span data-ttu-id="f37a9-140">**Рис. 5-2**.</span><span class="sxs-lookup"><span data-stu-id="f37a9-140">**Figure 5-2**.</span></span> <span data-ttu-id="f37a9-141">При выборе **.NET Core и Docker** рабочей нагрузки во время установки Visual Studio 2017 г.</span><span class="sxs-lookup"><span data-stu-id="f37a9-141">Selecting the **.NET Core and Docker** workload during Visual Studio 2017 setup</span></span>

<span data-ttu-id="f37a9-142">Прежде чем Docker приложения и развертывания и тестирования в Docker, можно начать кодирование приложения в обычный .NET (обычно в .NET Core, если вы планируете использовать контейнеры).</span><span class="sxs-lookup"><span data-stu-id="f37a9-142">You can start coding your application in plain .NET (usually in .NET Core if you are planning to use containers) even before enabling Docker in your application and deploying and testing in Docker.</span></span> <span data-ttu-id="f37a9-143">Тем не менее рекомендуется начать работу над Docker как можно быстрее, поскольку, которые будут реальной среды и любые проблемы, можно выполнить обнаружение как можно быстрее.</span><span class="sxs-lookup"><span data-stu-id="f37a9-143">However, it is recommended that you start working on Docker as soon as possible, because that will be the real environment and any issues can be discovered as soon as possible.</span></span> <span data-ttu-id="f37a9-144">Это действие рекомендуется, поскольку Visual Studio делает так же просто, для работы с Docker, что почти, что прозрачный — примера при отладке приложения с несколькими контейнера из Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f37a9-144">This is encouraged because Visual Studio makes it so easy to work with Docker that it almost feels transparent—the best example when debugging multi-container applications from Visual Studio.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="f37a9-145">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="f37a9-145">Additional resources</span></span>

-   <span data-ttu-id="f37a9-146">**Начало работы с Docker CE для Windows**
    [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)</span><span class="sxs-lookup"><span data-stu-id="f37a9-146">**Get started with Docker CE for Windows**
[*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)</span></span>

-   <span data-ttu-id="f37a9-147">**Visual Studio 2017 г**
    [*https://www.visualstudio.com/vs/visual-studio-2017/*](https://www.visualstudio.com/vs/visual-studio-2017/)</span><span class="sxs-lookup"><span data-stu-id="f37a9-147">**Visual Studio 2017**
[*https://www.visualstudio.com/vs/visual-studio-2017/*](https://www.visualstudio.com/vs/visual-studio-2017/)</span></span>

![](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a><span data-ttu-id="f37a9-148">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="f37a9-148">Step 2.</span></span> <span data-ttu-id="f37a9-149">Создайте файл Dockerfile, связанные с существующие базовый образ .NET</span><span class="sxs-lookup"><span data-stu-id="f37a9-149">Create a Dockerfile related to an existing .NET base image</span></span>

<span data-ttu-id="f37a9-150">Требуется файл Dockerfile для каждого настраиваемого образа, необходимо создать; необходимо также Dockerfile для каждого контейнера для развертывания, будет ли автоматически развертывать в Visual Studio или вручную с помощью Docker CLI (запуска docker и docker — составить команды).</span><span class="sxs-lookup"><span data-stu-id="f37a9-150">You need a Dockerfile for each custom image you want to build; you also need a Dockerfile for each container to be deployed, whether you deploy automatically from Visual Studio or manually using the Docker CLI (docker run and docker-compose commands).</span></span> <span data-ttu-id="f37a9-151">Если приложение содержит одну пользовательскую службу, необходимо один Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="f37a9-151">If your application contains a single custom service, you need a single Dockerfile.</span></span> <span data-ttu-id="f37a9-152">Если приложение содержит несколько служб (как для архитектуры микрослужбами), необходимо один Dockerfile для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="f37a9-152">If your application contains multiple services (as in a microservices architecture), you need one Dockerfile for each service.</span></span>

<span data-ttu-id="f37a9-153">Dockerfile помещается в корневой папке приложения или службы.</span><span class="sxs-lookup"><span data-stu-id="f37a9-153">The Dockerfile is placed in the root folder of your application or service.</span></span> <span data-ttu-id="f37a9-154">Он содержит команды, которые сообщить способ установки и запуска приложения или службы в контейнер Docker.</span><span class="sxs-lookup"><span data-stu-id="f37a9-154">It contains the commands that tell Docker how to set up and run your application or service in a container.</span></span> <span data-ttu-id="f37a9-155">Можно вручную создать файл Dockerfile в коде и добавить его в проект вместе с зависимостями .NET.</span><span class="sxs-lookup"><span data-stu-id="f37a9-155">You can manually create a Dockerfile in code and add it to your project along with your .NET dependencies.</span></span>

<span data-ttu-id="f37a9-156">В Visual Studio и средствами для Docker эта задача требует нескольких щелчков мыши.</span><span class="sxs-lookup"><span data-stu-id="f37a9-156">With Visual Studio and its tools for Docker, this task requires only a few mouse clicks.</span></span> <span data-ttu-id="f37a9-157">При создании нового проекта в Visual Studio 2017 г имеется параметр с именем **поддержки включить контейнеров (Docker)**, как показано на рисунке 5-3.</span><span class="sxs-lookup"><span data-stu-id="f37a9-157">When you create a new project in Visual Studio 2017, there is an option named **Enable Container (Docker) Support**, as shown in Figure 5-3.</span></span>

![](./media/image5.png)

<span data-ttu-id="f37a9-158">**Рис**.</span><span class="sxs-lookup"><span data-stu-id="f37a9-158">**Figure 5-3**.</span></span> <span data-ttu-id="f37a9-159">Включение поддержки Docker при создании нового проекта в Visual Studio 2017 г.</span><span class="sxs-lookup"><span data-stu-id="f37a9-159">Enabling Docker Support when creating a new project in Visual Studio 2017</span></span>

<span data-ttu-id="f37a9-160">Можно также включить поддержку Docker на новый или существующий проект, щелкнув правой кнопкой мыши файл проекта в Visual Studio и выбрав параметр **Docker добавить проект поддерживает**, как показано на рисунке 5-4.</span><span class="sxs-lookup"><span data-stu-id="f37a9-160">You can also enable Docker support on a new or existing project by right-clicking your project file in Visual Studio and selecting the option **Add-Docker Project Support**, as shown in Figure 5-4.</span></span>

![](./media/image6.png)

<span data-ttu-id="f37a9-161">**Рис. 5-4**.</span><span class="sxs-lookup"><span data-stu-id="f37a9-161">**Figure 5-4**.</span></span> <span data-ttu-id="f37a9-162">Включение поддержки Docker в существующем проекте Visual Studio 2017 г.</span><span class="sxs-lookup"><span data-stu-id="f37a9-162">Enabling Docker support in an existing Visual Studio 2017 project</span></span>

<span data-ttu-id="f37a9-163">Это действие для проекта (например, веб-приложения ASP.NET или службы веб-API) добавляет в проект с необходимой конфигурацией файла Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="f37a9-163">This action on a project (like an ASP.NET Web application or Web API service) adds a Dockerfile to the project with the required configuration.</span></span> <span data-ttu-id="f37a9-164">Он также добавляет в файл docker compose.yml для всего решения.</span><span class="sxs-lookup"><span data-stu-id="f37a9-164">It also adds a docker-compose.yml file for the whole solution.</span></span> <span data-ttu-id="f37a9-165">В следующих разделах описаны сведения, хранящиеся в каждом из этих файлов.</span><span class="sxs-lookup"><span data-stu-id="f37a9-165">In the following sections, we describe the information that goes into each of those files.</span></span> <span data-ttu-id="f37a9-166">Visual Studio создаст для вас эту работу, однако полезно понимать, что необходимо включить в файл Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="f37a9-166">Visual Studio can do this work for you, but it is useful to understand what goes into a Dockerfile.</span></span>

### <a name="option-a-creating-a-project-using-an-existing-official-net-docker-image"></a><span data-ttu-id="f37a9-167">Вариант а создание проекта с помощью существующего образа официальный .NET Docker</span><span class="sxs-lookup"><span data-stu-id="f37a9-167">Option A: Creating a project using an existing official .NET Docker image</span></span>

<span data-ttu-id="f37a9-168">Обычно построения пользовательского образа для контейнера на основе базового образа, можно получить из официальный репозиторий, в [Docker Hub](https://hub.docker.com/) реестра.</span><span class="sxs-lookup"><span data-stu-id="f37a9-168">You usually build a custom image for your container on top of a base image you can get from an official repository at the [Docker Hub](https://hub.docker.com/) registry.</span></span> <span data-ttu-id="f37a9-169">Это точно что происходит на самом деле, если включена поддержка Docker в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f37a9-169">That is precisely what happens under the covers when you enable Docker support in Visual Studio.</span></span> <span data-ttu-id="f37a9-170">Dockerfile будет использовать существующий образ aspnetcore.</span><span class="sxs-lookup"><span data-stu-id="f37a9-170">Your Dockerfile will use an existing aspnetcore image.</span></span>

<span data-ttu-id="f37a9-171">Ранее было показано, какие образы Docker и репозиториев, можно использовать, в зависимости от framework и операционной системы, которые вы выбрали.</span><span class="sxs-lookup"><span data-stu-id="f37a9-171">Earlier we explained which Docker images and repos you can use, depending on the framework and OS you have chosen.</span></span> <span data-ttu-id="f37a9-172">Например, если вы хотите использовать ASP.NET Core (Windows или Linux), изображение, используемое — microsoft / aspnetcore:2.0.</span><span class="sxs-lookup"><span data-stu-id="f37a9-172">For instance, if you want to use ASP.NET Core (Linux or Windows), the image to use is microsoft/aspnetcore:2.0.</span></span> <span data-ttu-id="f37a9-173">Таким образом необходимо просто указать, какой базовый образ Docker, который будет использоваться для контейнера.</span><span class="sxs-lookup"><span data-stu-id="f37a9-173">Therefore, you just need to specify what base Docker image you will use for your container.</span></span> <span data-ttu-id="f37a9-174">Для этого добавьте корпорации Майкрософт или aspnetcore:2.0 для Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="f37a9-174">You do that by adding FROM microsoft/aspnetcore:2.0 to your Dockerfile.</span></span> <span data-ttu-id="f37a9-175">Это будет автоматически выполнена с помощью Visual Studio, но в случае обновления версии обновления это значение.</span><span class="sxs-lookup"><span data-stu-id="f37a9-175">This will be automatically performed by Visual Studio, but if you were to update the version, you update this value.</span></span>

<span data-ttu-id="f37a9-176">Использование официальный репозиторий образов .NET из Docker Hub с номером версии гарантирует, что на всех компьютерах (включая разработку, тестирование и производственной) доступны те же возможности языка.</span><span class="sxs-lookup"><span data-stu-id="f37a9-176">Using an official .NET image repository from Docker Hub with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="f37a9-177">Приведенный ниже образец Dockerfile для контейнеров ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f37a9-177">The following example shows a sample Dockerfile for an ASP.NET Core container.</span></span>

```
FROM microsoft/aspnetcore:2.0
  
ARG source
  
WORKDIR /app
  
EXPOSE 80
  
COPY ${source:-obj/Docker/publish} .
  
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

<span data-ttu-id="f37a9-178">В этом случае контейнера основан на версии 2.0 официальный образа ASP.NET Core Docker (несколькими arch для Linux и Windows).</span><span class="sxs-lookup"><span data-stu-id="f37a9-178">In this case, the container is based on version 2.0 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows).</span></span> <span data-ttu-id="f37a9-179">Это параметр `FROM microsoft/aspnetcore:2.0`.</span><span class="sxs-lookup"><span data-stu-id="f37a9-179">This is the setting `FROM microsoft/aspnetcore:2.0`.</span></span> <span data-ttu-id="f37a9-180">(Дополнительные сведения об этом базового образа в разделе [образа Docker ASP.NET Core](https://hub.docker.com/r/microsoft/aspnetcore/) страницы и [образа Docker .NET Core](https://hub.docker.com/r/microsoft/dotnet/) страницы.) В файле Dockerfile необходимо также указать Docker для прослушивания TCP-порт, который будет использоваться во время выполнения (в данном случае порт 80, настроенной с помощью параметра ПРЕДОСТАВЛЯЮТ).</span><span class="sxs-lookup"><span data-stu-id="f37a9-180">(For further details about this base image, see the [ASP.NET Core Docker Image](https://hub.docker.com/r/microsoft/aspnetcore/) page and the [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) page.) In the Dockerfile, you also need to instruct Docker to listen on the TCP port you will use at runtime (in this case, port 80, as configured with the EXPOSE setting).</span></span>

<span data-ttu-id="f37a9-181">Можно указать дополнительные параметры конфигурации в файл Dockerfile, в зависимости от языка и framework, которую вы используете.</span><span class="sxs-lookup"><span data-stu-id="f37a9-181">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you are using.</span></span> <span data-ttu-id="f37a9-182">Для экземпляра строки ENTRYPOINT с \[«dotnet», «MySingleContainerWebApp.dll»\] сообщает Docker для запуска приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f37a9-182">For instance, the ENTRYPOINT line with \["dotnet", "MySingleContainerWebApp.dll"\] tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="f37a9-183">При использовании пакета SDK и .NET Core CLI (dotnet CLI) для построения и запуска приложения .NET, этот параметр будет отличаться.</span><span class="sxs-lookup"><span data-stu-id="f37a9-183">If you are using the SDK and the .NET Core CLI (dotnet CLI) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="f37a9-184">Заключается в том, ENTRYPOINT строки и другие параметры будут отличаться в зависимости от языка и платформы, которая выбирается для приложения.</span><span class="sxs-lookup"><span data-stu-id="f37a9-184">The bottom line is that the ENTRYPOINT line and other settings will be different depending on the language and platform you choose for your application.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="f37a9-185">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="f37a9-185">Additional resources</span></span>

-   <span data-ttu-id="f37a9-186">**Создание образов Docker для приложений .NET Core**
    [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images)</span><span class="sxs-lookup"><span data-stu-id="f37a9-186">**Building Docker Images for .NET Core Applications**
[*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images)</span></span>

-   <span data-ttu-id="f37a9-187">**Создать собственный образ**.</span><span class="sxs-lookup"><span data-stu-id="f37a9-187">**Build your own image**.</span></span> <span data-ttu-id="f37a9-188">В официальной документации Docker.</span><span class="sxs-lookup"><span data-stu-id="f37a9-188">In the official Docker documentation.</span></span>
    [<span data-ttu-id="f37a9-189">*https://docs.docker.com/Engine/tutorials/dockerimages/*</span><span class="sxs-lookup"><span data-stu-id="f37a9-189">*https://docs.docker.com/engine/tutorials/dockerimages/*</span></span>](https://docs.docker.com/engine/tutorials/dockerimages/)

### <a name="using-multi-arch-image-repositories"></a><span data-ttu-id="f37a9-190">Использование нескольких arch изображения репозитории</span><span class="sxs-lookup"><span data-stu-id="f37a9-190">Using multi-arch image repositories</span></span>

<span data-ttu-id="f37a9-191">Один репозиторий может содержать вариантов платформы, например в Linux образ и образ Windows.</span><span class="sxs-lookup"><span data-stu-id="f37a9-191">A single repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="f37a9-192">Эта функция позволяет поставщиков, таких как Microsoft (базовый образ создатели) для создания одного репозитория для охвата нескольких платформ (то есть, Windows и Linux).</span><span class="sxs-lookup"><span data-stu-id="f37a9-192">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is Linux and Windows).</span></span> <span data-ttu-id="f37a9-193">Например [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) репозитория в реестр Docker Hub обеспечивает поддержку для Linux и Windows Nano Server с тем же именем репозитория.</span><span class="sxs-lookup"><span data-stu-id="f37a9-193">For example, the [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same repo name.</span></span>

<span data-ttu-id="f37a9-194">Если задать метку, использующих платформу, которая является явным образом в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="f37a9-194">If you specify a tag, targeting a platform that is explicit like in the following cases:</span></span>

-   <span data-ttu-id="f37a9-195">**Microsoft/aspnetcore:2.0.0-jessie**</span><span class="sxs-lookup"><span data-stu-id="f37a9-195">**microsoft/aspnetcore:2.0.0-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux 

-   <span data-ttu-id="f37a9-196">**Microsoft/aspnetcore:2.0.0-nanoserver**</span><span class="sxs-lookup"><span data-stu-id="f37a9-196">**microsoft/aspnetcore:2.0.0-nanoserver**</span></span>

        .NET Core 2.0 runtime-only on Windows Nano Server

<span data-ttu-id="f37a9-197">Однако и это новые, так как функция mid 2017 г при указании изображения с одинаковым именем, даже такой же тег, новые несколькими arch изображения (например, изображение aspnetcore, поддерживающего несколькими arch) будут использовать версию Windows или Linux в зависимости от узла Docker ОС выполняется развертывание , как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f37a9-197">But, and this is new since mid-2017, if you specify the same image name, even with the same tag, the new multi-arch images (like the aspnetcore image which supports multi-arch) will use the Linux or Windows version depending on the Docker host OS you are deploying, as shown in the following example:</span></span>

-   <span data-ttu-id="f37a9-198">**Microsoft и aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="f37a9-198">**microsoft/aspnetcore:2.0**</span></span>

        Multi-arch: .NET Core 2.0 runtime-only on Linux or Windows Nano Server depending on the Docker host OS

<span data-ttu-id="f37a9-199">Таким образом, когда опрос изображения с сервера Windows, он будет получать Windows variant и извлечение тем же именем образа из узла Linux будет получать Linux variant.</span><span class="sxs-lookup"><span data-stu-id="f37a9-199">This way, when you pull an image from a Windows host, it will pull the Windows variant, and pulling the same image name from a Linux host will pull the Linux variant.</span></span>

### <a name="option-b-creating-your-base-image-from-scratch"></a><span data-ttu-id="f37a9-200">Вариант б. Создание основной образ с нуля</span><span class="sxs-lookup"><span data-stu-id="f37a9-200">Option B: Creating your base image from scratch</span></span>

<span data-ttu-id="f37a9-201">Собственный базовый образ Docker можно создать с нуля.</span><span class="sxs-lookup"><span data-stu-id="f37a9-201">You can create your own Docker base image from scratch.</span></span> <span data-ttu-id="f37a9-202">Этот сценарий не рекомендуется для тех, кто начиная с помощью Docker, но если вы хотите задать определенные биты базового образа, это можно сделать.</span><span class="sxs-lookup"><span data-stu-id="f37a9-202">This scenario is not recommended for someone who is starting with Docker, but if you want to set the specific bits of your own base image, you can do so.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="f37a9-203">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="f37a9-203">Additional resources</span></span>

-   <span data-ttu-id="f37a9-204">**Образы несколькими arch .NET Core**.</span><span class="sxs-lookup"><span data-stu-id="f37a9-204">**Multi-arch .NET Core images**.</span></span>
<span data-ttu-id="f37a9-205">https://github.com/DotNet/Announcements/issues/14</span><span class="sxs-lookup"><span data-stu-id="f37a9-205">https://github.com/dotnet/announcements/issues/14</span></span> 
-   <span data-ttu-id="f37a9-206">**Создание базового образа**.</span><span class="sxs-lookup"><span data-stu-id="f37a9-206">**Create a base image**.</span></span> <span data-ttu-id="f37a9-207">Официальной документации Docker.</span><span class="sxs-lookup"><span data-stu-id="f37a9-207">Official Docker documentation.</span></span>
    [<span data-ttu-id="f37a9-208">*https://docs.docker.com/Engine/userguide/eng-Image/baseimages/*</span><span class="sxs-lookup"><span data-stu-id="f37a9-208">*https://docs.docker.com/engine/userguide/eng-image/baseimages/*</span></span>](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a><span data-ttu-id="f37a9-209">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="f37a9-209">Step 3.</span></span> <span data-ttu-id="f37a9-210">Создание пользовательских образов Docker и внедрить их в приложение или службу</span><span class="sxs-lookup"><span data-stu-id="f37a9-210">Create your custom Docker images and embed your application or service in them</span></span>

<span data-ttu-id="f37a9-211">Для каждой службы в приложении необходимо создать связанные изображения.</span><span class="sxs-lookup"><span data-stu-id="f37a9-211">For each service in your application, you need to create a related image.</span></span> <span data-ttu-id="f37a9-212">Если приложение состоит из одной службы или веб-приложения, необходимо просто одного изображения.</span><span class="sxs-lookup"><span data-stu-id="f37a9-212">If your application is made up of a single service or web application, you just need a single image.</span></span>

<span data-ttu-id="f37a9-213">Обратите внимание, что образы Docker создаются автоматически для вас в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f37a9-213">Note that the Docker images are built automatically for you in Visual Studio.</span></span> <span data-ttu-id="f37a9-214">Следующие шаги только для редактора/CLI рабочего процесса и рассматривается для ясности сведения о том, что происходит под.</span><span class="sxs-lookup"><span data-stu-id="f37a9-214">The following steps are only needed for the editor/CLI workflow and explained for clarity about what happens underneath.</span></span>

<span data-ttu-id="f37a9-215">Разработчику необходимо разрабатывать и тестировать локально, пока не будет принудительно завершенного компонентов или изменения в системе управления версиями (например, для GitHub).</span><span class="sxs-lookup"><span data-stu-id="f37a9-215">You, as developer, need to develop and test locally until you push a completed feature or change to your source control system (for example, to GitHub).</span></span> <span data-ttu-id="f37a9-216">Это означает необходимость создания образов Docker и развернуть контейнеры на локальном узле Docker (Windows или виртуальной Машине Linux) и запуска, тестирования и отладки от этих локальных контейнеров.</span><span class="sxs-lookup"><span data-stu-id="f37a9-216">This means that you need to create the Docker images and deploy containers to a local Docker host (Windows or Linux VM) and run, test, and debug against those local containers.</span></span>

<span data-ttu-id="f37a9-217">Чтобы создать пользовательский образ в локальной среде с помощью Docker CLI и Dockerfile, можно использовать команду сборки docker, как показано на рисунке 5-5.</span><span class="sxs-lookup"><span data-stu-id="f37a9-217">To create a custom image in your local environment by using Docker CLI and your Dockerfile, you can use the docker build command, as in Figure 5-5.</span></span>

![](./media/image8.png)

<span data-ttu-id="f37a9-218">**Рис**.</span><span class="sxs-lookup"><span data-stu-id="f37a9-218">**Figure 5-5**.</span></span> <span data-ttu-id="f37a9-219">Создание пользовательского образа Docker</span><span class="sxs-lookup"><span data-stu-id="f37a9-219">Creating a custom Docker image</span></span>

<span data-ttu-id="f37a9-220">При необходимости вместо непосредственного использования сборки docker из папки проекта, можно сначала создать папки развертывания с необходимые библиотеки .NET и двоичные файлы, запустив dotnet публикации, а затем использовать команду сборки docker.</span><span class="sxs-lookup"><span data-stu-id="f37a9-220">Optionally, instead of directly running docker build from the project folder, you can first generate a deployable folder with the required .NET libraries and binaries by running dotnet publish, and then use the docker build command.</span></span>

<span data-ttu-id="f37a9-221">Образ Docker, будет создано с именем cesardl и netcore-webapi микрослужбу-docker: первый.</span><span class="sxs-lookup"><span data-stu-id="f37a9-221">This will create a Docker image with the name cesardl/netcore-webapi-microservice-docker:first.</span></span> <span data-ttu-id="f37a9-222">В этом случае: первого — тег, представляющий конкретную версию.</span><span class="sxs-lookup"><span data-stu-id="f37a9-222">In this case, :first is a tag representing a specific version.</span></span> <span data-ttu-id="f37a9-223">Этот шаг можно повторить для каждого настраиваемого образа, необходимо создать приложение Docker состоит.</span><span class="sxs-lookup"><span data-stu-id="f37a9-223">You can repeat this step for each custom image you need to create for your composed Docker application.</span></span>

<span data-ttu-id="f37a9-224">Когда приложение состоит из нескольких контейнеров (то есть, это приложение несколькими контейнера), можно также использовать docker создания копии — команда сборки для создания связанных изображений с помощью одной команды с помощью метаданных, представленным в связанном файлы docker compose.yml.</span><span class="sxs-lookup"><span data-stu-id="f37a9-224">When an application is made of multiple containers (that is, it is a multi-container application), you can also use the docker-compose up --build command to build all the related images with a single command by using the metadata exposed in the related docker-compose.yml files.</span></span>

<span data-ttu-id="f37a9-225">Можно найти существующие образы в ваш локальный репозиторий с помощью docker команда изображений, как показано на рисунке 5-6.</span><span class="sxs-lookup"><span data-stu-id="f37a9-225">You can find the existing images in your local repository by using the docker images command, as shown in Figure 5-6.</span></span>

![](./media/image9.png)

<span data-ttu-id="f37a9-226">**Рис. 5-6.**</span><span class="sxs-lookup"><span data-stu-id="f37a9-226">**Figure 5-6.**</span></span> <span data-ttu-id="f37a9-227">Просмотр существующих образов с помощью команды docker изображений</span><span class="sxs-lookup"><span data-stu-id="f37a9-227">Viewing existing images using the docker images command</span></span>

### <a name="creating-docker-images-with-visual-studio"></a><span data-ttu-id="f37a9-228">Создание образов Docker с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f37a9-228">Creating Docker images with Visual Studio</span></span>

<span data-ttu-id="f37a9-229">При использовании Visual Studio для создания проекта с поддержкой Docker вы не создан явно изображения.</span><span class="sxs-lookup"><span data-stu-id="f37a9-229">When you are using Visual Studio to create a project with Docker support, you do not explicitly create an image.</span></span> <span data-ttu-id="f37a9-230">Вместо этого образ создается автоматически при нажатии F5 и выполнения dockerized приложения или службы.</span><span class="sxs-lookup"><span data-stu-id="f37a9-230">Instead, the image is created for you when you press F5 and run the dockerized application or service.</span></span> <span data-ttu-id="f37a9-231">Этот шаг выполняется автоматически в Visual Studio и недоступен для этого действия, но важно знать, что происходит по ним.</span><span class="sxs-lookup"><span data-stu-id="f37a9-231">This step is automatic in Visual Studio, and you will not see it happen, but it is important that you know what is going on underneath.</span></span>

![](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a><span data-ttu-id="f37a9-232">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="f37a9-232">Step 4.</span></span> <span data-ttu-id="f37a9-233">Определение службы в docker compose.yml при построении приложения несколькими контейнера Docker</span><span class="sxs-lookup"><span data-stu-id="f37a9-233">Define your services in docker-compose.yml when building a multi-container Docker application</span></span>

<span data-ttu-id="f37a9-234">[Docker compose.yml](https://docs.docker.com/compose/compose-file/) файла позволяет определить набор связанных служб для развертывания в виде составных приложений с помощью команды развертывания.</span><span class="sxs-lookup"><span data-stu-id="f37a9-234">The [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file lets you define a set of related services to be deployed as a composed application with deployment commands.</span></span>

<span data-ttu-id="f37a9-235">Чтобы использовать файл docker compose.yml, необходимо создать файл в ваш основной или корневой папке решения, с содержимым, аналогичного тому, который, в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f37a9-235">To use a docker-compose.yml file, you need to create the file in your main or root solution folder, with content similar to that in the following example:</span></span>

```yml
version: '3'
  
services:

  webmvc:
    image: eshop/web
    environment:
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
    ports:
      - "80:80"
    depends_on:
      - catalog.api
      - ordering.api

  catalog.api:
    image: eshop/catalog.api
    environment: 
      - ConnectionString=Server=sql.data;Database=CatalogDB;…
    ports:
      - "81:80"
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    environment:
      - ConnectionString=Server=sql.data;Database=OrderingDb;…
    ports:
      - "82:80"
    extra_hosts:
      - "CESARDLBOOKVHD:10.0.75.1"
    depends_on:
      - sql.data

  sql.data:
    image: mssql-server-linux:latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"

```

<span data-ttu-id="f37a9-236">Обратите внимание, что этот файл docker compose.yml упрощенной и объединенной версии.</span><span class="sxs-lookup"><span data-stu-id="f37a9-236">Note that this docker-compose.yml file is a simplified and merged version.</span></span> <span data-ttu-id="f37a9-237">Он содержит данные статической конфигурации для каждого контейнера (например, имя пользовательского образа), который всегда применяется, а также сведения о конфигурации, могут зависеть от среды развертывания, такие как строка подключения.</span><span class="sxs-lookup"><span data-stu-id="f37a9-237">It contains static configuration data for each container (like the name of the custom image), which always applies, plus configuration information that might depend on the deployment environment, like the connection string.</span></span> <span data-ttu-id="f37a9-238">В следующих разделах вы узнаете, как можно разделить конфигурации docker compose.yml на несколько docker соединить файлы и переопределение значений в зависимости от типа среды и выполнение (Отладка или выпуск).</span><span class="sxs-lookup"><span data-stu-id="f37a9-238">In later sections, you will learn how you can split the docker-compose.yml configuration into multiple docker-compose files and override values depending on the environment and execution type (debug or release).</span></span>

<span data-ttu-id="f37a9-239">Пример файла docker compose.yml определяет пять служб: webmvc службы (веб-приложения), два микрослужбами (catalog.api и ordering.api) и один источник контейнера данных, sql.data, основанных на SQL Server для ОС Linux работает как контейнер.</span><span class="sxs-lookup"><span data-stu-id="f37a9-239">The docker-compose.yml file example defines five services: the webmvc service (a web application), two microservices (catalog.api and ordering.api), and one data source container, sql.data, based on SQL Server for Linux running as a container.</span></span> <span data-ttu-id="f37a9-240">Каждая служба развертывается как контейнер, поэтому образа Docker не требуется для каждого.</span><span class="sxs-lookup"><span data-stu-id="f37a9-240">Each service is deployed as a container, so a Docker image is required for each.</span></span>

<span data-ttu-id="f37a9-241">Файл docker compose.yml указывает не только используются какие контейнеры, но их по отдельности настройки.</span><span class="sxs-lookup"><span data-stu-id="f37a9-241">The docker-compose.yml file specifies not only what containers are being used, but how they are individually configured.</span></span> <span data-ttu-id="f37a9-242">Например webmvc контейнера определению в файле .yml:</span><span class="sxs-lookup"><span data-stu-id="f37a9-242">For instance, the webmvc container definition in the .yml file:</span></span>

-   <span data-ttu-id="f37a9-243">Использует предварительно построенного eshop-web: последнюю версию образа.</span><span class="sxs-lookup"><span data-stu-id="f37a9-243">Uses a pre-built eshop/web:latest image.</span></span> <span data-ttu-id="f37a9-244">Тем не менее, можно также настроить изображения, создаваемой как часть создания docker на основе выполнения с помощью дополнительной настройки со сборкой: раздела в файле docker-compose.</span><span class="sxs-lookup"><span data-stu-id="f37a9-244">However, you could also configure the image to be built as part of the docker-compose execution with an additional configuration based on a build: section in the docker-compose file.</span></span>

-   <span data-ttu-id="f37a9-245">Инициализирует две переменные среды (URL-адрес каталога и OrderingUrl).</span><span class="sxs-lookup"><span data-stu-id="f37a9-245">Initializes two environment variables (CatalogUrl and OrderingUrl).</span></span>

-   <span data-ttu-id="f37a9-246">Пересылает предоставленный порт 80 в контейнере для внешнего порта 80 на хост-компьютере.</span><span class="sxs-lookup"><span data-stu-id="f37a9-246">Forwards the exposed port 80 on the container to the external port 80 on the host machine.</span></span>

-   <span data-ttu-id="f37a9-247">Ссылки на каталог и порядок обновления с веб-приложения зависит от\_на параметр.</span><span class="sxs-lookup"><span data-stu-id="f37a9-247">Links the web app to the catalog and ordering service with the depends\_on setting.</span></span> <span data-ttu-id="f37a9-248">В результате служба ожидает запуска этих служб.</span><span class="sxs-lookup"><span data-stu-id="f37a9-248">This causes the service to wait until those services are started.</span></span>

<span data-ttu-id="f37a9-249">Мы вернемся файл docker compose.yml в одном из следующих разделов при будет рассматриваться как реализовать микрослужбами и несколькими контейнера приложений.</span><span class="sxs-lookup"><span data-stu-id="f37a9-249">We will revisit the docker-compose.yml file in a later section when we cover how to implement microservices and multi-container apps.</span></span>

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a><span data-ttu-id="f37a9-250">Работа с docker compose.yml в Visual Studio 2017 г.</span><span class="sxs-lookup"><span data-stu-id="f37a9-250">Working with docker-compose.yml in Visual Studio 2017</span></span>

<span data-ttu-id="f37a9-251">После добавления поддержки решения Docker в проект службы в решении Visual Studio, как показано на рисунке 5 – 7, Visual Studio добавляет в проект файл Dockerfile, а также добавляет раздел "службы" (проект) в решении с файлами docker compose.yml.</span><span class="sxs-lookup"><span data-stu-id="f37a9-251">When you add Docker solution support to a service project in a Visual Studio solution, as shown in Figure 5-7, Visual Studio adds a Dockerfile to your project, and it adds a service section (project) in your solution with the docker-compose.yml files.</span></span> <span data-ttu-id="f37a9-252">Это простой способ создания решения несколько контейнеров.</span><span class="sxs-lookup"><span data-stu-id="f37a9-252">It is an easy way to start composing your multiple-container solution.</span></span> <span data-ttu-id="f37a9-253">Затем можно открыть файлы docker compose.yml и обновлять их с дополнительными возможностями.</span><span class="sxs-lookup"><span data-stu-id="f37a9-253">You can then open the docker-compose.yml files and update them with additional features.</span></span>

![](./media/image6.png)

<span data-ttu-id="f37a9-254">**Рис**.</span><span class="sxs-lookup"><span data-stu-id="f37a9-254">**Figure 5-7**.</span></span> <span data-ttu-id="f37a9-255">Добавление поддержки Docker в Visual Studio 2017 г., щелкнув правой кнопкой мыши проект ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f37a9-255">Adding Docker support in Visual Studio 2017 by right-clicking an ASP.NET Core project</span></span>

<span data-ttu-id="f37a9-256">Добавление поддержки Docker в Visual Studio не только добавляет в проект файл Dockerfile, но добавляет сведения о конфигурации для нескольких файлов глобального docker-compose.yml, заданные на уровне решения.</span><span class="sxs-lookup"><span data-stu-id="f37a9-256">Adding Docker support in Visual Studio not only adds the Dockerfile to your project, but adds the configuration information to several global docker-compose.yml files that are set at the solution level.</span></span>

<span data-ttu-id="f37a9-257">После добавления поддержки Docker в решение в Visual Studio, также появится новый узел (в файле проекта docker compose.dcproj) в обозревателе решений с файлами добавлены docker-compose.yml, как показано на рисунке 5-8.</span><span class="sxs-lookup"><span data-stu-id="f37a9-257">After you add Docker support to your solution in Visual Studio, you will also see a new node (in the docker-compose.dcproj project file) in Solution Explorer that contains the added docker-compose.yml files, as shown in Figure 5-8.</span></span>

![](./media/image11.PNG)

<span data-ttu-id="f37a9-258">**Рис**.</span><span class="sxs-lookup"><span data-stu-id="f37a9-258">**Figure 5-8**.</span></span> <span data-ttu-id="f37a9-259">**Docker составления** узел дерева, добавленные в обозревателе решений Visual Studio 2017 г.</span><span class="sxs-lookup"><span data-stu-id="f37a9-259">The **docker-compose** tree node added in Visual Studio 2017 Solution Explorer</span></span>

<span data-ttu-id="f37a9-260">Можно развернуть приложение несколькими контейнера с помощью одного docker-compose.yml файла с помощью docker создания копии команды.</span><span class="sxs-lookup"><span data-stu-id="f37a9-260">You could deploy a multi-container application with a single docker-compose.yml file by using the docker-compose up command.</span></span> <span data-ttu-id="f37a9-261">Однако Visual Studio добавляет группу из них, можно изменить значения в зависимости от среды (разработки и производственной), при этом тип (выпуска и отладки).</span><span class="sxs-lookup"><span data-stu-id="f37a9-261">However, Visual Studio adds a group of them so you can override values depending on the environment (development versus production) and execution type (release versus debug).</span></span> <span data-ttu-id="f37a9-262">Эта возможность описывается в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="f37a9-262">This capability will be explained in later sections.</span></span>

![](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a><span data-ttu-id="f37a9-263">Шаг 5.</span><span class="sxs-lookup"><span data-stu-id="f37a9-263">Step 5.</span></span> <span data-ttu-id="f37a9-264">Постройте и запустите приложение Docker</span><span class="sxs-lookup"><span data-stu-id="f37a9-264">Build and run your Docker application</span></span>

<span data-ttu-id="f37a9-265">Если приложение имеет только один контейнер, его можно выполнить, развертывания на узле Docker (физический сервер или ВМ).</span><span class="sxs-lookup"><span data-stu-id="f37a9-265">If your application only has a single container, you can run it by deploying it to your Docker host (VM or physical server).</span></span> <span data-ttu-id="f37a9-266">Тем не менее, если приложение содержит несколько служб, можно развернуть его как состоит приложение, либо с помощью одной команды CLI (docker составить вверх), и с помощью Visual Studio с использованием этой команды на самом деле.</span><span class="sxs-lookup"><span data-stu-id="f37a9-266">However, if your application contains multiple services, you can deploy it as a composed application, either using a single CLI command (docker-compose up), or with Visual Studio, which will use that command under the covers.</span></span> <span data-ttu-id="f37a9-267">Давайте рассмотрим различные варианты.</span><span class="sxs-lookup"><span data-stu-id="f37a9-267">Let’s look at the different options.</span></span>

### <a name="option-a-running-a-single-container-with-docker-cli"></a><span data-ttu-id="f37a9-268">Вариант а, выполнив один контейнер Docker CLI</span><span class="sxs-lookup"><span data-stu-id="f37a9-268">Option A: Running a single-container with Docker CLI</span></span>

<span data-ttu-id="f37a9-269">Можно запустить контейнер Docker с помощью docker, выполните команду, как показано на рисунке 5 – 9.</span><span class="sxs-lookup"><span data-stu-id="f37a9-269">You can run a Docker container using the docker run command, as in Figure 5-9:</span></span>

```
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

![](./media/image13.png)

<span data-ttu-id="f37a9-270">**Рис. 5-9**.</span><span class="sxs-lookup"><span data-stu-id="f37a9-270">**Figure 5-9**.</span></span> <span data-ttu-id="f37a9-271">Запуск контейнера Docker, с помощью docker, выполните команду</span><span class="sxs-lookup"><span data-stu-id="f37a9-271">Running a Docker container using the docker run command</span></span>

<span data-ttu-id="f37a9-272">В этом случае команда привязывает внутренний порт 5000 контейнера с портом 80 хост-компьютера.</span><span class="sxs-lookup"><span data-stu-id="f37a9-272">In this case, the command binds the internal port 5000 of the container to port 80 of the host machine.</span></span> <span data-ttu-id="f37a9-273">Это означает, что узел прослушивает порт 80 и перенаправление в порт 5000 в контейнере.</span><span class="sxs-lookup"><span data-stu-id="f37a9-273">This means that the host is listening on port 80 and forwarding to port 5000 on the container.</span></span>

### <a name="option-b-running-a-multi-container-application"></a><span data-ttu-id="f37a9-274">Вариант б. запуск приложения несколькими контейнера</span><span class="sxs-lookup"><span data-stu-id="f37a9-274">Option B: Running a multi-container application</span></span>

<span data-ttu-id="f37a9-275">В большинстве случаев корпоративного приложения Docker будет состоять из нескольких служб, это означает, что необходимо запустить приложение несколькими контейнера, как показано на рисунке 5 – 10.</span><span class="sxs-lookup"><span data-stu-id="f37a9-275">In most enterprise scenarios, a Docker application will be composed of multiple services, which means you need to run a multi-container application, as shown in Figure 5-10.</span></span>

![](./media/image14.png)

<span data-ttu-id="f37a9-276">**На рисунке 5 – 10**.</span><span class="sxs-lookup"><span data-stu-id="f37a9-276">**Figure 5-10**.</span></span> <span data-ttu-id="f37a9-277">Виртуальная машина с развернуть контейнеры Docker</span><span class="sxs-lookup"><span data-stu-id="f37a9-277">VM with Docker containers deployed</span></span>

#### <a name="running-a-multi-container-application-with-the-docker-cli"></a><span data-ttu-id="f37a9-278">Запуск приложения несколькими контейнера с Docker CLI</span><span class="sxs-lookup"><span data-stu-id="f37a9-278">Running a multi-container application with the Docker CLI</span></span>

<span data-ttu-id="f37a9-279">Чтобы запустить приложение несколькими контейнера с Docker CLI, можно выполнить docker-составления копирование команды.</span><span class="sxs-lookup"><span data-stu-id="f37a9-279">To run a multi-container application with the Docker CLI, you can run the docker-compose up command.</span></span> <span data-ttu-id="f37a9-280">Командный файл использует docker-compose.yml наличие на уровне решения для развертывания приложения несколькими контейнера.</span><span class="sxs-lookup"><span data-stu-id="f37a9-280">This command uses the docker-compose.yml file that you have at the solution level to deploy a multi-container application.</span></span> <span data-ttu-id="f37a9-281">Рис. 5-11 показаны результаты при выполнении команды из каталога основного проекта, которая содержит файл docker compose.yml.</span><span class="sxs-lookup"><span data-stu-id="f37a9-281">Figure 5-11 shows the results when running the command from your main project directory, which contains the docker-compose.yml file.</span></span>

![](./media/image15.png)

<span data-ttu-id="f37a9-282">**Рис. 5-11**.</span><span class="sxs-lookup"><span data-stu-id="f37a9-282">**Figure 5-11**.</span></span> <span data-ttu-id="f37a9-283">Пример результатов при работе docker создания копии команды</span><span class="sxs-lookup"><span data-stu-id="f37a9-283">Example results when running the docker-compose up command</span></span>

<span data-ttu-id="f37a9-284">После docker-составления копирование выполняется команда, приложения и его связанные контейнеры развертываются в узла Docker, как показано в представлении виртуальных Машин на рисунке 5 — 10.</span><span class="sxs-lookup"><span data-stu-id="f37a9-284">After the docker-compose up command runs, the application and its related containers are deployed into your Docker host, as illustrated in the VM representation in Figure 5-10.</span></span>

#### <a name="running-and-debugging-a-multi-container-application-with-visual-studio"></a><span data-ttu-id="f37a9-285">Запуск и отладка приложения несколькими контейнера с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f37a9-285">Running and debugging a multi-container application with Visual Studio</span></span> 

<span data-ttu-id="f37a9-286">Запуск приложения с несколькими контейнера, с помощью Visual Studio 2017 г. не удается получить проще.</span><span class="sxs-lookup"><span data-stu-id="f37a9-286">Running a multi-container application using Visual Studio 2017 cannot get simpler.</span></span> <span data-ttu-id="f37a9-287">Не только приложение можно запустить несколькими контейнера, но существует возможность отладки все его контейнеры непосредственно из Visual Studio с помощью обычных точек останова.</span><span class="sxs-lookup"><span data-stu-id="f37a9-287">You can not only run the multi-container application, but you are able to debug all its containers directly from Visual Studio by setting regular breakpoints.</span></span>

<span data-ttu-id="f37a9-288">Как упоминалось ранее, каждый раз при добавлении поддержки решения Docker проекта в решении, этот проект настраивается в файле глобального docker compose.yml (на уровне решения), который позволяет запустить или отладить все решение за один раз.</span><span class="sxs-lookup"><span data-stu-id="f37a9-288">As mentioned before, each time you add Docker solution support to a project within a solution, that project is configured in the global (solution-level) docker-compose.yml file, which lets you run or debug the whole solution at once.</span></span> <span data-ttu-id="f37a9-289">Visual Studio запустите один контейнер для каждого проекта, с поддержкой Docker решения и выполнения всех шагов внутренняя вам (dotnet публикации, сборки docker и т. д.).</span><span class="sxs-lookup"><span data-stu-id="f37a9-289">Visual Studio will start one container for each project that has Docker solution support enabled, and perform all the internal steps for you (dotnet publish, docker build, etc.).</span></span>

<span data-ttu-id="f37a9-290">Здесь важно то, что, как показано на рисунке 5-12, в Visual Studio 2017 г имеется дополнительный **Docker** команду для действия ключа F5.</span><span class="sxs-lookup"><span data-stu-id="f37a9-290">The important point here is that, as shown in Figure 5-12, in Visual Studio 2017 there is an additional **Docker** command for the F5 key action.</span></span> <span data-ttu-id="f37a9-291">Этот параметр позволяет запустить или отладить приложение несколькими контейнера, запустив все контейнеры, которые определены в файлах docker compose.yml на уровне решения.</span><span class="sxs-lookup"><span data-stu-id="f37a9-291">This option lets you run or debug a multi-container application by running all the containers that are defined in the docker-compose.yml files at the solution level.</span></span> <span data-ttu-id="f37a9-292">Возможность отладки нескольких контейнерными решениями означает, что можно установить несколько точек останова, каждой точки останова в другом проекте (контейнер) и во время отладки из Visual Studio вы будет останавливаться в точках останова, определенными в разных проектах и работает на разные контейнеры.</span><span class="sxs-lookup"><span data-stu-id="f37a9-292">The ability to debug multiple-container solutions means that you can set several breakpoints, each breakpoint in a different project (container), and while debugging from Visual Studio you will stop at breakpoints defined in different projects and running on different containers.</span></span>

![](./media/image16.png)

<span data-ttu-id="f37a9-293">**Рис. 5-12**.</span><span class="sxs-lookup"><span data-stu-id="f37a9-293">**Figure 5-12**.</span></span> <span data-ttu-id="f37a9-294">Запуск нескольких контейнера приложений в Visual Studio 2017 г.</span><span class="sxs-lookup"><span data-stu-id="f37a9-294">Running multi-container apps in Visual Studio 2017</span></span>

### <a name="additional-resources"></a><span data-ttu-id="f37a9-295">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="f37a9-295">Additional resources</span></span>

-   <span data-ttu-id="f37a9-296">**Разверните контейнер ASP.NET к удаленному узлу Docker**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="f37a9-296">**Deploy an ASP.NET container to a remote Docker host**
[*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a><span data-ttu-id="f37a9-297">Примечание о тестировании и развертывании с orchestrators</span><span class="sxs-lookup"><span data-stu-id="f37a9-297">A note about testing and deploying with orchestrators</span></span>

<span data-ttu-id="f37a9-298">Docker составлять вверх и команды docker запуска (или запуске и отладке контейнеров в Visual Studio) не подходит для тестирования контейнеры в среде разработки.</span><span class="sxs-lookup"><span data-stu-id="f37a9-298">The docker-compose up and docker run commands (or running and debugging the containers in Visual Studio) are adequate for testing containers in your development environment.</span></span> <span data-ttu-id="f37a9-299">Однако не следует использовать этот подход, если вы используете Docker кластеры и orchestrators как помощью Docker Swarm Mesosphere DC/OS и Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="f37a9-299">But you should not use this approach if you are targeting Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes.</span></span> <span data-ttu-id="f37a9-300">При использовании кластера как [режиме с помощью Docker Swarm](https://docs.docker.com/engine/swarm/) (доступно в CE Docker для Windows и Mac с версии 1.12), необходимо развернуть и протестировать дополнительные команды, такие как [создать службу docker](https://docs.docker.com/engine/reference/commandline/service_create/) для одной службы.</span><span class="sxs-lookup"><span data-stu-id="f37a9-300">If you are using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker CE for Windows and Mac since version 1.12), you need to deploy and test with additional commands like [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/) for single services.</span></span> <span data-ttu-id="f37a9-301">При развертывании приложения, состоящие из нескольких контейнеров, используйте [docker создания пакета](https://docs.docker.com/compose/reference/bundle/) и [docker развертывание myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) развертывание приложения состоит как *стека*.</span><span class="sxs-lookup"><span data-stu-id="f37a9-301">If you are deploying an application composed of several containers, you use [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) and [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) to deploy the composed application as a *stack*.</span></span> <span data-ttu-id="f37a9-302">Дополнительные сведения см. в записи блога [введение в экспериментальном наборы распределенных приложений](https://blog.docker.com/2016/06/docker-app-bundle/) в документации Docker.</span><span class="sxs-lookup"><span data-stu-id="f37a9-302">For more information, see the blog post [Introducing Experimental Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) in the Docker documentation.</span></span> <span data-ttu-id="f37a9-303">на узле Docker.</span><span class="sxs-lookup"><span data-stu-id="f37a9-303">on the Docker site.</span></span>

<span data-ttu-id="f37a9-304">Для [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) и [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/) развертывания команды и сценарии также используются.</span><span class="sxs-lookup"><span data-stu-id="f37a9-304">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/) you would use different deployment commands and scripts as well.</span></span>

![](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a><span data-ttu-id="f37a9-305">Шаг 6.</span><span class="sxs-lookup"><span data-stu-id="f37a9-305">Step 6.</span></span> <span data-ttu-id="f37a9-306">Протестируйте приложение Docker с помощью локального узла Docker</span><span class="sxs-lookup"><span data-stu-id="f37a9-306">Test your Docker application using your local Docker host</span></span>

<span data-ttu-id="f37a9-307">Этот шаг будет зависеть от действия приложения.</span><span class="sxs-lookup"><span data-stu-id="f37a9-307">This step will vary depending on what your application is doing.</span></span> <span data-ttu-id="f37a9-308">В простой .NET Core веб-приложение, развернутое в виде одного контейнера или службы доступа к службе, открыв браузер на узле Docker и перехода к этому сайту, как показано на рисунке 5-13.</span><span class="sxs-lookup"><span data-stu-id="f37a9-308">In a simple .NET Core Web application that is deployed as a single container or service, you can access the service by opening a browser on the Docker host and navigating to that site as shown in Figure 5-13.</span></span> <span data-ttu-id="f37a9-309">(Если контейнера конфигурации в файл Dockerfile сопоставляется портов на узле, отличной от 80, указывать узел после в URL-адрес).</span><span class="sxs-lookup"><span data-stu-id="f37a9-309">(If the configuration in the Dockerfile maps the container to a port on the host that is anything other than 80, include the host post in the URL.)</span></span>

![](./media/image18.png)

<span data-ttu-id="f37a9-310">**На рисунке 5 — 13**.</span><span class="sxs-lookup"><span data-stu-id="f37a9-310">**Figure 5-13**.</span></span> <span data-ttu-id="f37a9-311">Пример тестирования приложения Docker локально с помощью localhost</span><span class="sxs-lookup"><span data-stu-id="f37a9-311">Example of testing your Docker application locally using localhost</span></span>

<span data-ttu-id="f37a9-312">Если localhost не указывает на Docker узлом IP (по умолчанию, при использовании Docker CE, оно должно быть), чтобы перейти к службе, используйте IP-адрес сетевой карты для вашего компьютера.</span><span class="sxs-lookup"><span data-stu-id="f37a9-312">If localhost is not pointing to the Docker host IP (by default, when using Docker CE, it should), to navigate to your service, use the IP address of your machine’s network card.</span></span>

<span data-ttu-id="f37a9-313">Обратите внимание, что этот URL-адрес в браузере использует порт 80 для конкретного контейнера примера обсуждаются.</span><span class="sxs-lookup"><span data-stu-id="f37a9-313">Note that this URL in the browser uses port 80 for the particular container example being discussed.</span></span> <span data-ttu-id="f37a9-314">Тем не менее внутри запросов осуществляется перенаправление к port 5000, поскольку, как он был развернут с помощью docker, выполните команду, как описано в предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="f37a9-314">However, internally the requests are being redirected to port 5000, because that was how it was deployed with the docker run command, as explained in a previous step.</span></span>

<span data-ttu-id="f37a9-315">Также можно протестировать приложение, используя перелистывание из терминала, как показано на рисунке 5-14.</span><span class="sxs-lookup"><span data-stu-id="f37a9-315">You can also test the application using curl from the terminal, as shown in Figure 5-14.</span></span> <span data-ttu-id="f37a9-316">В случае установки Docker в Windows по умолчанию IP-узле Docker всегда используется 10.0.75.1 помимо фактический IP-адрес вашего компьютера.</span><span class="sxs-lookup"><span data-stu-id="f37a9-316">In a Docker installation on Windows, the default Docker Host IP is always 10.0.75.1 in addition to your machine’s actual IP address.</span></span>

![](./media/image19.png)

<span data-ttu-id="f37a9-317">**Рис**.</span><span class="sxs-lookup"><span data-stu-id="f37a9-317">**Figure 5-14**.</span></span> <span data-ttu-id="f37a9-318">Пример тестирования приложения Docker локально с помощью curl</span><span class="sxs-lookup"><span data-stu-id="f37a9-318">Example of testing your Docker application locally using curl</span></span>

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a><span data-ttu-id="f37a9-319">Тестирование и отладка контейнерами с помощью Visual Studio 2017 г.</span><span class="sxs-lookup"><span data-stu-id="f37a9-319">Testing and debugging containers with Visual Studio 2017</span></span>

<span data-ttu-id="f37a9-320">При запуске и отладке контейнерами с помощью Visual Studio 2017 г., можно отлаживать приложения .NET в так же, как при выполнении без контейнеров.</span><span class="sxs-lookup"><span data-stu-id="f37a9-320">When running and debugging the containers with Visual Studio 2017, you can debug the .NET application in much the same way as you would when running without containers.</span></span>

### <a name="testing-and-debugging-without-visual-studio"></a><span data-ttu-id="f37a9-321">Тестирование и отладку без Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f37a9-321">Testing and debugging without Visual Studio</span></span>

<span data-ttu-id="f37a9-322">При разработке с помощью редактора или CLI подход, отладка контейнеров является более сложной и необходимо будет выполнить отладку путем создания трассировки.</span><span class="sxs-lookup"><span data-stu-id="f37a9-322">If you are developing using the editor/CLI approach, debugging containers is more difficult and you will want to debug by generating traces.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="f37a9-323">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="f37a9-323">Additional resources</span></span>

-   <span data-ttu-id="f37a9-324">**Отладка приложений в локальном контейнере Docker**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="f37a9-324">**Debugging apps in a local Docker container**
[*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

-   <span data-ttu-id="f37a9-325">**Стив Ласкера. Создавать, отлаживать, развертывать приложения ASP.NET Core с помощью Docker.**</span><span class="sxs-lookup"><span data-stu-id="f37a9-325">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker.**</span></span> <span data-ttu-id="f37a9-326">Видео.</span><span class="sxs-lookup"><span data-stu-id="f37a9-326">Video.</span></span>
    [<span data-ttu-id="f37a9-327">*https://Channel9.MSDN.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*</span><span class="sxs-lookup"><span data-stu-id="f37a9-327">*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*</span></span>](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a><span data-ttu-id="f37a9-328">Упрощенная рабочего процесса при разработке контейнерами с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f37a9-328">Simplified workflow when developing containers with Visual Studio</span></span>

<span data-ttu-id="f37a9-329">По сути рабочего процесса при использовании Visual Studio, гораздо проще, чем при использовании редактора/CLI подход.</span><span class="sxs-lookup"><span data-stu-id="f37a9-329">Effectively, the workflow when using Visual Studio is a lot simpler than if you use the editor/CLI approach.</span></span> <span data-ttu-id="f37a9-330">Основные шаги, необходимые для Docker, связанные с Dockerfile и docker compose.yml файлы скрытых или проще благодаря Visual Studio, как показано на рисунке 5-15.</span><span class="sxs-lookup"><span data-stu-id="f37a9-330">Most of the steps required by Docker related to the Dockerfile and docker-compose.yml files are hidden or simplified by Visual Studio, as shown in Figure 5-15.</span></span>

![](./media/image20.png)

<span data-ttu-id="f37a9-331">**Рис. 5-15**.</span><span class="sxs-lookup"><span data-stu-id="f37a9-331">**Figure 5-15**.</span></span> <span data-ttu-id="f37a9-332">Упрощенная рабочий процесс во время разработки в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f37a9-332">Simplified workflow when developing with Visual Studio</span></span>

<span data-ttu-id="f37a9-333">Кроме того необходимо выполнить шаг 2 (Добавление поддержки Docker в проекты) только один раз.</span><span class="sxs-lookup"><span data-stu-id="f37a9-333">In addition, you need to perform step 2 (adding Docker support to your projects) just once.</span></span> <span data-ttu-id="f37a9-334">Таким образом рабочий процесс аналогичен задачам разработки обычные при использовании для других разработки приложений .NET.</span><span class="sxs-lookup"><span data-stu-id="f37a9-334">Therefore, the workflow is similar to your usual development tasks when using .NET for any other development.</span></span> <span data-ttu-id="f37a9-335">Необходимо знать, что происходит на самом деле (процесс создания образа, какие базовые образы, которые вы используете, развертывание контейнеры, т. д.) и в некоторых случаях том, что также необходимо изменить файл Dockerfile или docker compose.yml, чтобы настроить поведение.</span><span class="sxs-lookup"><span data-stu-id="f37a9-335">You need to know what is going on under the covers (the image build process, what base images you are using, deployment of containers, etc.) and sometimes you will also need to edit the Dockerfile or docker-compose.yml file to customize behaviors.</span></span> <span data-ttu-id="f37a9-336">Однако с помощью Visual Studio, можно сделать гораздо эффективнее упрощено большую часть работы.</span><span class="sxs-lookup"><span data-stu-id="f37a9-336">But most of the work is greatly simplified by using Visual Studio, making you a lot more productive.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="f37a9-337">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="f37a9-337">Additional resources</span></span>

-   <span data-ttu-id="f37a9-338">**Стив Ласкера. Разработка .NET docker с помощью Visual Studio 2017 г**
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)</span><span class="sxs-lookup"><span data-stu-id="f37a9-338">**Steve Lasker. .NET Docker Development with Visual Studio 2017**
[*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)</span></span>

-   <span data-ttu-id="f37a9-339">**Фриц T. Джеффри. Поместите приложении .NET Core в контейнер Docker новые средства для Visual Studio**
    [*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)</span><span class="sxs-lookup"><span data-stu-id="f37a9-339">**Jeffrey T. Fritz. Put a .NET Core App in a Container with the new Docker Tools for Visual Studio**
[*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)</span></span>

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a><span data-ttu-id="f37a9-340">С помощью команды PowerShell в Dockerfile для настройки контейнеры Windows</span><span class="sxs-lookup"><span data-stu-id="f37a9-340">Using PowerShell commands in a Dockerfile to set up Windows Containers</span></span> 

<span data-ttu-id="f37a9-341">[Контейнеры Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) позволяют преобразовать существующие приложения Windows в Docker images и развертывать их с помощью тех же средств, что и остальная часть экосистеме Docker.</span><span class="sxs-lookup"><span data-stu-id="f37a9-341">[Windows Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) allow you to convert your existing Windows applications into Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span> <span data-ttu-id="f37a9-342">Чтобы использовать контейнеры Windows, выполните команды PowerShell в Dockerfile, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f37a9-342">To use Windows Containers, you run PowerShell commands in the Dockerfile, as shown in the following example:</span></span>

```
FROM microsoft/windowsservercore
  
LABEL Description="IIS" Vendor="Microsoft" Version="10"
  
RUN powershell -Command Add-WindowsFeature Web-Server
  
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="f37a9-343">В этом случае мы с помощью базового образа Windows Server Core (параметр FROM) и установка служб IIS с помощью команды PowerShell (параметр ВЫПОЛНЕНИЯ).</span><span class="sxs-lookup"><span data-stu-id="f37a9-343">In this case, we are using a Windows Server Core base image (the FROM setting) and installing IIS with a PowerShell command (the RUN setting).</span></span> <span data-ttu-id="f37a9-344">Аналогичным образом может также использовать команды PowerShell, чтобы настроить дополнительные компоненты, например ASP.NET 4.x .NET 4.6 и другого программного обеспечения Windows.</span><span class="sxs-lookup"><span data-stu-id="f37a9-344">In a similar way, you could also use PowerShell commands to set up additional components like ASP.NET 4.x, .NET 4.6, or any other Windows software.</span></span> <span data-ttu-id="f37a9-345">Например следующая команда в файл Dockerfile устанавливает ASP.NET 4.5:</span><span class="sxs-lookup"><span data-stu-id="f37a9-345">For example, the following command in a Dockerfile sets up ASP.NET 4.5:</span></span>

```
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a><span data-ttu-id="f37a9-346">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="f37a9-346">Additional resources</span></span>

-   <span data-ttu-id="f37a9-347">**ASPNET-docker или Dockerfile.**</span><span class="sxs-lookup"><span data-stu-id="f37a9-347">**aspnet-docker/Dockerfile.**</span></span> <span data-ttu-id="f37a9-348">Примеры команд Powershell для запуска из файлов dockerfile для включения компонентов Windows.</span><span class="sxs-lookup"><span data-stu-id="f37a9-348">Example Powershell commands to run from dockerfiles to include Windows features.</span></span>
    [<span data-ttu-id="f37a9-349">*https://github.com/Microsoft/ASPNET-docker/BLOB/master/4.6.2/Dockerfile*</span><span class="sxs-lookup"><span data-stu-id="f37a9-349">*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*</span></span>](https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile)

>[!div class="step-by-step"]
<span data-ttu-id="f37a9-350">[Предыдущие] (index.md) [Далее] (.. / net-core-single-containers-linux-windows-server-hosts/index.md)</span><span class="sxs-lookup"><span data-stu-id="f37a9-350">[Previous] (index.md) [Next] (../net-core-single-containers-linux-windows-server-hosts/index.md)</span></span>
