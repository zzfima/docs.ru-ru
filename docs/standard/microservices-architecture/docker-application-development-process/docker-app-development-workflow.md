---
title: "Рабочий процесс разработки для приложений Docker"
description: "Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Рабочий процесс разработки для приложений Docker"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8537b1db27f512ec0bfc2f23589efe8199ca3287
ms.sourcegitcommit: c3957fdb990060559d73cca44ab3e2c7b4d049c0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2018
---
# <a name="development-workflow-for-docker-apps"></a><span data-ttu-id="307da-104">Рабочий процесс разработки для приложений Docker</span><span class="sxs-lookup"><span data-stu-id="307da-104">Development workflow for Docker apps</span></span>

<span data-ttu-id="307da-105">Жизненный цикл разработки приложений начинается на компьютере каждого разработчика, где разработчик локально программирует приложение на предпочитаемом языке и тестирует его.</span><span class="sxs-lookup"><span data-stu-id="307da-105">The application development lifecycle starts at each developer’s machine, where the developer codes the application using their preferred language and tests it locally.</span></span> <span data-ttu-id="307da-106">Независимо от выбранного языка, инфраструктуры и платформы, в рамках этого рабочего процесса разработчик всегда разрабатывает и тестирует контейнеры Docker, но делает это локально.</span><span class="sxs-lookup"><span data-stu-id="307da-106">No matter which language, framework, and platform the developer chooses, with this workflow, the developer is always developing and testing Docker containers, but doing so locally.</span></span>

<span data-ttu-id="307da-107">В каждый контейнер (экземпляр образа Docker) входят следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="307da-107">Each container (an instance of a Docker image) includes the following components:</span></span>

-   <span data-ttu-id="307da-108">Выбранная операционная система (например, дистрибутив Linux, Windows Nano Server или Windows Server Core).</span><span class="sxs-lookup"><span data-stu-id="307da-108">An operating system selection (for example, a Linux distribution, Windows Nano Server, or Windows Server Core).</span></span>

-   <span data-ttu-id="307da-109">Файлы, добавленные разработчиком (двоичные файлы приложения и т. п.).</span><span class="sxs-lookup"><span data-stu-id="307da-109">Files added by the developer (application binaries, etc.).</span></span>

-   <span data-ttu-id="307da-110">Сведения о конфигурации (параметры среды и зависимости).</span><span class="sxs-lookup"><span data-stu-id="307da-110">Configuration information (environment settings and dependencies).</span></span>

## <a name="workflow-for-developing-docker-container-based-applications"></a><span data-ttu-id="307da-111">Рабочий процесс разработки приложений Docker на основе контейнера</span><span class="sxs-lookup"><span data-stu-id="307da-111">Workflow for developing Docker container-based applications</span></span>

<span data-ttu-id="307da-112">В этом разделе описывается рабочий процесс *внутреннего цикла* разработки приложений на основе контейнера Docker.</span><span class="sxs-lookup"><span data-stu-id="307da-112">This section describes the *inner-loop* development workflow for Docker container-based applications.</span></span> <span data-ttu-id="307da-113">Рабочий процесс внутреннего цикла означает, что речь идет только о разработке, которая выполняется на компьютере разработчика, не касаясь более широкого рабочего процесса DevOps.</span><span class="sxs-lookup"><span data-stu-id="307da-113">The inner-loop workflow means it is not taking into account the broader DevOps workflow and just focuses on the development work done on the developer’s computer.</span></span> <span data-ttu-id="307da-114">Начальные этапы настройки среды здесь не рассматриваются, так как они выполняются только один раз.</span><span class="sxs-lookup"><span data-stu-id="307da-114">The initial steps to set up the environment are not included, since those are done only once.</span></span>

<span data-ttu-id="307da-115">Приложение состоит из ваших собственных служб и дополнительных библиотек (зависимостей).</span><span class="sxs-lookup"><span data-stu-id="307da-115">An application is composed of your own services plus additional libraries (dependencies).</span></span> <span data-ttu-id="307da-116">Ниже приведены основные шаги, которые обычно выполняются при сборке приложения Docker, как показано на рисунке 5-1.</span><span class="sxs-lookup"><span data-stu-id="307da-116">The following are the basic steps you usually take when building a Docker application, as illustrated in Figure 5-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="307da-117">**Рис. 5-1**.</span><span class="sxs-lookup"><span data-stu-id="307da-117">**Figure 5-1.**</span></span> <span data-ttu-id="307da-118">Пошаговый рабочий процесс разработки приложения на основе контейнера Docker</span><span class="sxs-lookup"><span data-stu-id="307da-118">Step-by-step workflow for developing Docker containerized apps</span></span>

<span data-ttu-id="307da-119">В этом руководстве подробно описывается весь процесс, и каждый важный шаг объясняется с акцентом на среду Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="307da-119">In this guide, this whole process is detailed and every major step is explained by focusing on a Visual Studio environment.</span></span>

<span data-ttu-id="307da-120">Если разработка выполняется с помощью редактора и CLI (например, Visual Studio Code и Docker CLI на macOS или Windows), то необходимо знать каждый шаг и обычно более детально, чем при использовании Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="307da-120">When you are using an editor/CLI development approach (for example, Visual Studio Code plus Docker CLI on macOS or Windows), you need to know every step, generally in more detail than if you are using Visual Studio.</span></span> <span data-ttu-id="307da-121">Дополнительные сведения о работе в среде CLI см. в электронной книге [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](http://aka.ms/dockerlifecycleebook/).</span><span class="sxs-lookup"><span data-stu-id="307da-121">For more details about working in a CLI environment, refer to the e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](http://aka.ms/dockerlifecycleebook/).</span></span>

<span data-ttu-id="307da-122">При использовании Visual Studio 2015 или Visual Studio 2017 многие из этих шагов выполняются автоматически, что значительно повышает производительность.</span><span class="sxs-lookup"><span data-stu-id="307da-122">When you are using Visual Studio 2015 or Visual Studio 2017, many of those steps are handled for you, which dramatically improves your productivity.</span></span> <span data-ttu-id="307da-123">Это особенно справедливо в тех случаях, когда используется Visual Studio 2017 и планируется создание многоконтейнерных приложений.</span><span class="sxs-lookup"><span data-stu-id="307da-123">This is especially true when you are using Visual Studio 2017 and targeting multi-container applications.</span></span> <span data-ttu-id="307da-124">Например, всего лишь одним щелчком мыши Visual Studio добавляет в проект Dockerfile и файл docker-compose.yml с конфигурацией для вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="307da-124">For instance, with just one mouse click, Visual Studio adds the Dockerfile and docker-compose.yml file to your projects with the configuration for your application.</span></span> <span data-ttu-id="307da-125">При запуске приложения в Visual Studio он создает образ Docker и запускает многоконтейнерное приложение непосредственно в Docker; вы даже можете отлаживать несколько контейнеров одновременно.</span><span class="sxs-lookup"><span data-stu-id="307da-125">When you run the application in Visual Studio, it builds the Docker image and runs the multi-container application directly in Docker; it even allows you to debug several containers at once.</span></span> <span data-ttu-id="307da-126">Эти возможности значительно повышают скорость разработки.</span><span class="sxs-lookup"><span data-stu-id="307da-126">These features will boost your development speed.</span></span>

<span data-ttu-id="307da-127">Однако то, что Visual Studio автоматизирует эти действия, не означает, что вам не нужно знать, что происходит внутри Docker.</span><span class="sxs-lookup"><span data-stu-id="307da-127">However, just because Visual Studio makes those steps automatic does not mean that you do not need to know what is going on underneath with Docker.</span></span> <span data-ttu-id="307da-128">Поэтому далее в руководстве подробно описывается каждый шаг.</span><span class="sxs-lookup"><span data-stu-id="307da-128">Therefore, in the guidance that follows, we detail every step.</span></span>

![](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a><span data-ttu-id="307da-129">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="307da-129">Step 1.</span></span> <span data-ttu-id="307da-130">Начало программирования и создание первого приложения или базовой службы</span><span class="sxs-lookup"><span data-stu-id="307da-130">Start coding and create your initial application or service baseline</span></span>

<span data-ttu-id="307da-131">Разработка приложения Docker аналогична разработке приложения без Docker.</span><span class="sxs-lookup"><span data-stu-id="307da-131">Developing a Docker application is similar to the way you develop an application without Docker.</span></span> <span data-ttu-id="307da-132">Разница заключается в том, что при разработке для Docker развертывание и тестирование приложения или служб, работающих в контейнерах Docker, выполняется в локальной среде.</span><span class="sxs-lookup"><span data-stu-id="307da-132">The difference is that while developing for Docker, you are deploying and testing your application or services running within Docker containers in your local environment.</span></span> <span data-ttu-id="307da-133">Этот контейнер может быть контейнером Linux или контейнером Windows.</span><span class="sxs-lookup"><span data-stu-id="307da-133">The container can be either a Linux container or a Windows container.</span></span>

### <a name="set-up-your-local-environment-with-visual-studio"></a><span data-ttu-id="307da-134">Настройка локальной среды с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="307da-134">Set up your local environment with Visual Studio</span></span>

<span data-ttu-id="307da-135">Перед началом работы убедитесь, что [Docker Community Edition (CE)](https://www.docker.com/community-edition) для Windows установлен, как описано в следующих инструкциях:</span><span class="sxs-lookup"><span data-stu-id="307da-135">To begin, make sure you have [Docker Community Edition (CE)](https://www.docker.com/community-edition) for Windows installed, as explained in the following instructions:</span></span>

[<span data-ttu-id="307da-136">Начало работы с Docker CE для Windows</span><span class="sxs-lookup"><span data-stu-id="307da-136">Get started with Docker CE for Windows</span></span>](https://docs.docker.com/docker-for-windows/)

<span data-ttu-id="307da-137">Кроме того, потребуется установленный Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="307da-137">In addition, you will need Visual Studio 2017 installed.</span></span> <span data-ttu-id="307da-138">Вместо Visual Studio 2015 с надстройкой "Средства Visual Studio для Docker" рекомендуется использовать именно Visual Studio 2017, поскольку в нем реализована расширенная поддержка Docker, например, поддерживается отладка контейнеров.</span><span class="sxs-lookup"><span data-stu-id="307da-138">This is preferred over Visual Studio 2015 with the Visual Studio Tools for Docker add-in, because Visual Studio 2017 has more advanced support for Docker, like support for debugging containers.</span></span> <span data-ttu-id="307da-139">Visual Studio 2017 включает инструментарий для Docker, если при установке вы выбрали рабочую нагрузку **.NET Core и Docker**, как показано на рисунке 5-2.</span><span class="sxs-lookup"><span data-stu-id="307da-139">Visual Studio 2017 includes the tooling for Docker if you selected the **.NET Core and Docker** workload during installation, as shown in Figure 5-2.</span></span>

![](./media/image3.png)

<span data-ttu-id="307da-140">**Рис. 5-2**.</span><span class="sxs-lookup"><span data-stu-id="307da-140">**Figure 5-2**.</span></span> <span data-ttu-id="307da-141">Выбор рабочей нагрузки **.NET Core и Docker** при установке Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="307da-141">Selecting the **.NET Core and Docker** workload during Visual Studio 2017 setup</span></span>

<span data-ttu-id="307da-142">Можно приступать к программированию приложения в обычной среде .NET (как правило, в .NET Core, если вы планируете использовать контейнеры) даже до включения Docker в вашем приложении и развертывания и тестирования в Docker.</span><span class="sxs-lookup"><span data-stu-id="307da-142">You can start coding your application in plain .NET (usually in .NET Core if you are planning to use containers) even before enabling Docker in your application and deploying and testing in Docker.</span></span> <span data-ttu-id="307da-143">Тем не менее рекомендуется начать работу в Docker как можно быстрее, поскольку это будет реальная среда, и любые проблемы можно будет обнаружить гораздо раньше.</span><span class="sxs-lookup"><span data-stu-id="307da-143">However, it is recommended that you start working on Docker as soon as possible, because that will be the real environment and any issues can be discovered as soon as possible.</span></span> <span data-ttu-id="307da-144">Это также рекомендуется потому, что Visual Studio настолько упрощает работу с Docker, что практически все действия очевидны; лучший пример — отладка многоконтейнерного приложения в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="307da-144">This is encouraged because Visual Studio makes it so easy to work with Docker that it almost feels transparent—the best example when debugging multi-container applications from Visual Studio.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="307da-145">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="307da-145">Additional resources</span></span>

-   <span data-ttu-id="307da-146">**Начало работы с Docker CE для Windows**
    [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)</span><span class="sxs-lookup"><span data-stu-id="307da-146">**Get started with Docker CE for Windows**
[*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)</span></span>

-   <span data-ttu-id="307da-147">**Visual Studio 2017**
    [*https://www.visualstudio.com/downloads/*](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)</span><span class="sxs-lookup"><span data-stu-id="307da-147">**Visual Studio 2017**
[*https://www.visualstudio.com/downloads/*](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)</span></span>

![](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a><span data-ttu-id="307da-148">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="307da-148">Step 2.</span></span> <span data-ttu-id="307da-149">Создание файла Dockerfile, связанного с существующим базовым образом .NET</span><span class="sxs-lookup"><span data-stu-id="307da-149">Create a Dockerfile related to an existing .NET base image</span></span>

<span data-ttu-id="307da-150">Dockerfile необходим для каждого пользовательского образа, который вы хотите создать; кроме того, Dockerfile потребуется для каждого контейнера, который будет развертываться автоматически из Visual Studio или вручную с помощью Docker CLI (с помощью команд docker run и docker-compose).</span><span class="sxs-lookup"><span data-stu-id="307da-150">You need a Dockerfile for each custom image you want to build; you also need a Dockerfile for each container to be deployed, whether you deploy automatically from Visual Studio or manually using the Docker CLI (docker run and docker-compose commands).</span></span> <span data-ttu-id="307da-151">Если в приложении имеется единственный экземпляр пользовательской службы, необходим один Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="307da-151">If your application contains a single custom service, you need a single Dockerfile.</span></span> <span data-ttu-id="307da-152">Если в приложении имеется несколько служб (как в архитектуре на основе микрослужб), потребуется по одному Dockerfile для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="307da-152">If your application contains multiple services (as in a microservices architecture), you need one Dockerfile for each service.</span></span>

<span data-ttu-id="307da-153">Dockerfile размещается в корневой папке приложения или службы.</span><span class="sxs-lookup"><span data-stu-id="307da-153">The Dockerfile is placed in the root folder of your application or service.</span></span> <span data-ttu-id="307da-154">Он содержит команды, которые указывают Docker, как настраивать и запускать приложение или службу в контейнере.</span><span class="sxs-lookup"><span data-stu-id="307da-154">It contains the commands that tell Docker how to set up and run your application or service in a container.</span></span> <span data-ttu-id="307da-155">Можно вручную создать Dockerfile в коде и добавить его в проект вместе с зависимостями .NET.</span><span class="sxs-lookup"><span data-stu-id="307da-155">You can manually create a Dockerfile in code and add it to your project along with your .NET dependencies.</span></span>

<span data-ttu-id="307da-156">В Visual Studio со средствами для Docker эта задача выполняется лишь несколькими щелчками мыши.</span><span class="sxs-lookup"><span data-stu-id="307da-156">With Visual Studio and its tools for Docker, this task requires only a few mouse clicks.</span></span> <span data-ttu-id="307da-157">При создании нового проекта в Visual Studio 2017 можно выбрать параметр с именем **Enable Container (Docker) Support** (Включить поддержку контейнеров (Docker)), как показано на рисунке 5-3.</span><span class="sxs-lookup"><span data-stu-id="307da-157">When you create a new project in Visual Studio 2017, there is an option named **Enable Container (Docker) Support**, as shown in Figure 5-3.</span></span>

![](./media/image5.png)

<span data-ttu-id="307da-158">**Рис. 5-3**.</span><span class="sxs-lookup"><span data-stu-id="307da-158">**Figure 5-3**.</span></span> <span data-ttu-id="307da-159">Включение поддержки Docker при создании нового проекта в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="307da-159">Enabling Docker Support when creating a new project in Visual Studio 2017</span></span>

<span data-ttu-id="307da-160">Можно также включить поддержку Docker в новом или существующем проекте, щелкнув правой кнопкой мыши файл проекта в Visual Studio и выбрав в меню пункты **Add-Docker Project Support** (Добавить-Поддержка проекта Docker), как показано на рисунке 5-4.</span><span class="sxs-lookup"><span data-stu-id="307da-160">You can also enable Docker support on a new or existing project by right-clicking your project file in Visual Studio and selecting the option **Add-Docker Project Support**, as shown in Figure 5-4.</span></span>

![](./media/image6.png)

<span data-ttu-id="307da-161">**Рис. 5-4**.</span><span class="sxs-lookup"><span data-stu-id="307da-161">**Figure 5-4**.</span></span> <span data-ttu-id="307da-162">Включение поддержки Docker в существующем проекте Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="307da-162">Enabling Docker support in an existing Visual Studio 2017 project</span></span>

<span data-ttu-id="307da-163">Если выполнить это действие в проекте (например, в веб-приложении ASP.NET или в службе веб-API), то в проект будет добавлен Dockerfile с необходимой конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="307da-163">This action on a project (like an ASP.NET Web application or Web API service) adds a Dockerfile to the project with the required configuration.</span></span> <span data-ttu-id="307da-164">Кроме того, будет добавлен файл docker-compose.yml для всего решения.</span><span class="sxs-lookup"><span data-stu-id="307da-164">It also adds a docker-compose.yml file for the whole solution.</span></span> <span data-ttu-id="307da-165">В следующих разделах описывается информация, которая находится в каждом из этих файлов.</span><span class="sxs-lookup"><span data-stu-id="307da-165">In the following sections, we describe the information that goes into each of those files.</span></span> <span data-ttu-id="307da-166">Visual Studio может сделать это вместо вас, однако полезно разобраться, что входит в Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="307da-166">Visual Studio can do this work for you, but it is useful to understand what goes into a Dockerfile.</span></span>

### <a name="option-a-creating-a-project-using-an-existing-official-net-docker-image"></a><span data-ttu-id="307da-167">Вариант А. Создание проекта с помощью существующего официального образа .NET Docker</span><span class="sxs-lookup"><span data-stu-id="307da-167">Option A: Creating a project using an existing official .NET Docker image</span></span>

<span data-ttu-id="307da-168">Обычно вы создаете пользовательский образ для своего контейнера на основе базового образа, который можно получить из официального репозитория в реестре [Центра Docker](https://hub.docker.com/).</span><span class="sxs-lookup"><span data-stu-id="307da-168">You usually build a custom image for your container on top of a base image you can get from an official repository at the [Docker Hub](https://hub.docker.com/) registry.</span></span> <span data-ttu-id="307da-169">Именно это происходит на внутреннем уровне при включении поддержки Docker в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="307da-169">That is precisely what happens under the covers when you enable Docker support in Visual Studio.</span></span> <span data-ttu-id="307da-170">Ваш Dockerfile будет использовать существующий образ aspnetcore.</span><span class="sxs-lookup"><span data-stu-id="307da-170">Your Dockerfile will use an existing aspnetcore image.</span></span>

<span data-ttu-id="307da-171">Ранее было показано, какие образы и репозитории Docker можно использовать в зависимости от выбранной платформы и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="307da-171">Earlier we explained which Docker images and repos you can use, depending on the framework and OS you have chosen.</span></span> <span data-ttu-id="307da-172">Например, если вы выбрали ASP.NET Core (Windows или Linux), следует использовать образ microsoft/aspnetcore:2.0.</span><span class="sxs-lookup"><span data-stu-id="307da-172">For instance, if you want to use ASP.NET Core (Linux or Windows), the image to use is microsoft/aspnetcore:2.0.</span></span> <span data-ttu-id="307da-173">Таким образом, достаточно просто указать, какой базовый образ Docker будет использоваться для контейнера.</span><span class="sxs-lookup"><span data-stu-id="307da-173">Therefore, you just need to specify what base Docker image you will use for your container.</span></span> <span data-ttu-id="307da-174">Для этого добавьте в Dockerfile строку FROM microsoft/aspnetcore:2.0.</span><span class="sxs-lookup"><span data-stu-id="307da-174">You do that by adding FROM microsoft/aspnetcore:2.0 to your Dockerfile.</span></span> <span data-ttu-id="307da-175">Visual Studio выполнит это автоматически, но в случае обновления версии вы обновляете это значение.</span><span class="sxs-lookup"><span data-stu-id="307da-175">This will be automatically performed by Visual Studio, but if you were to update the version, you update this value.</span></span>

<span data-ttu-id="307da-176">Использование официального репозитория образов .NET из Центра Docker с номером версии гарантирует, что на всех компьютерах (включая компьютеры для разработки, тестирования и работы) будут доступны одни и те же функции языка.</span><span class="sxs-lookup"><span data-stu-id="307da-176">Using an official .NET image repository from Docker Hub with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="307da-177">Ниже приведен пример Dockerfile для контейнера ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="307da-177">The following example shows a sample Dockerfile for an ASP.NET Core container.</span></span>

```
FROM microsoft/aspnetcore:2.0
  
ARG source
  
WORKDIR /app
  
EXPOSE 80
  
COPY ${source:-obj/Docker/publish} .
  
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

<span data-ttu-id="307da-178">В этом случае контейнер основан на версии 2.0 официального образа Docker ASP.NET Core (мультиархитектурного для Linux и Windows).</span><span class="sxs-lookup"><span data-stu-id="307da-178">In this case, the container is based on version 2.0 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows).</span></span> <span data-ttu-id="307da-179">Это параметр `FROM microsoft/aspnetcore:2.0`.</span><span class="sxs-lookup"><span data-stu-id="307da-179">This is the setting `FROM microsoft/aspnetcore:2.0`.</span></span> <span data-ttu-id="307da-180">(Дополнительные сведения об этом базовом образе см. на страницах [Образ Docker ASP.NET Core](https://hub.docker.com/r/microsoft/aspnetcore/) и [Образ Docker .NET Core](https://hub.docker.com/r/microsoft/dotnet/).) Кроме того, в Dockerfile необходимо указать Docker прослушивать порт TCP, который будет использоваться во время выполнения (в данном случае это порт 80, как задано в параметре EXPOSE).</span><span class="sxs-lookup"><span data-stu-id="307da-180">(For further details about this base image, see the [ASP.NET Core Docker Image](https://hub.docker.com/r/microsoft/aspnetcore/) page and the [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) page.) In the Dockerfile, you also need to instruct Docker to listen on the TCP port you will use at runtime (in this case, port 80, as configured with the EXPOSE setting).</span></span>

<span data-ttu-id="307da-181">В Dockerfile можно задать дополнительные параметры конфигурации, в зависимости от используемого языка и платформы.</span><span class="sxs-lookup"><span data-stu-id="307da-181">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you are using.</span></span> <span data-ttu-id="307da-182">Например, параметр ENTRYPOINT со значением \["dotnet", "MySingleContainerWebApp.dll"\] указывает Docker запускать приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="307da-182">For instance, the ENTRYPOINT line with \["dotnet", "MySingleContainerWebApp.dll"\] tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="307da-183">Если для создания и запуска приложения .NET используется пакет SDK и .NET Core CLI (dotnet CLI), этот параметр будет другим.</span><span class="sxs-lookup"><span data-stu-id="307da-183">If you are using the SDK and the .NET Core CLI (dotnet CLI) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="307da-184">Параметр ENTRYPOINT, который находится в нижней строке, и другие параметры будут отличаться в зависимости от языка и платформы, выбранных для приложения.</span><span class="sxs-lookup"><span data-stu-id="307da-184">The bottom line is that the ENTRYPOINT line and other settings will be different depending on the language and platform you choose for your application.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="307da-185">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="307da-185">Additional resources</span></span>

-   <span data-ttu-id="307da-186">**Создание образов Docker для приложений .NET Core**
    [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](../../../core/docker/building-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="307da-186">**Building Docker Images for .NET Core Applications**
[*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](../../../core/docker/building-net-docker-images.md)</span></span>

-   <span data-ttu-id="307da-187">**Создание собственного образа**.</span><span class="sxs-lookup"><span data-stu-id="307da-187">**Build your own image**.</span></span> <span data-ttu-id="307da-188">В официальной документации Docker.</span><span class="sxs-lookup"><span data-stu-id="307da-188">In the official Docker documentation.</span></span>
    [<span data-ttu-id="307da-189">*https://docs.docker.com/engine/tutorials/dockerimages/*</span><span class="sxs-lookup"><span data-stu-id="307da-189">*https://docs.docker.com/engine/tutorials/dockerimages/*</span></span>](https://docs.docker.com/engine/tutorials/dockerimages/)

### <a name="using-multi-arch-image-repositories"></a><span data-ttu-id="307da-190">Использование мультиархитектурных репозиториев</span><span class="sxs-lookup"><span data-stu-id="307da-190">Using multi-arch image repositories</span></span>

<span data-ttu-id="307da-191">Один репозиторий может содержать варианты платформ, например образ Linux и образ Windows.</span><span class="sxs-lookup"><span data-stu-id="307da-191">A single repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="307da-192">Эта функция позволяет поставщикам, таким как Майкрософт, которые создают базовые образы, создать один репозиторий для охвата нескольких платформ (т. е. Windows и Linux).</span><span class="sxs-lookup"><span data-stu-id="307da-192">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is Linux and Windows).</span></span> <span data-ttu-id="307da-193">Например, репозиторий [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) в реестре Центра Docker обеспечивает поддержку Linux и Windows Nano Server при использовании одного и того же имени репозитория.</span><span class="sxs-lookup"><span data-stu-id="307da-193">For example, the [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same repo name.</span></span>

<span data-ttu-id="307da-194">Можно указать тег, явно задающий платформу, как в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="307da-194">If you specify a tag, targeting a platform that is explicit like in the following cases:</span></span>

-   <span data-ttu-id="307da-195">**microsoft/aspnetcore:2.0.0-jessie**</span><span class="sxs-lookup"><span data-stu-id="307da-195">**microsoft/aspnetcore:2.0.0-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux 

-   <span data-ttu-id="307da-196">**microsoft/aspnetcore:2.0.0-nanoserver**</span><span class="sxs-lookup"><span data-stu-id="307da-196">**microsoft/aspnetcore:2.0.0-nanoserver**</span></span>

        .NET Core 2.0 runtime-only on Windows Nano Server

<span data-ttu-id="307da-197">Однако в середине 2017 г. появилась возможность указывать одно и то же имя образа, даже с одинаковым тегом, и новые мультиархитектурные образы (например, образ aspnetcore, поддерживающий мультиархитектурность) будут использовать версию Windows или Linux в зависимости от развернутой базовой ОС Docker, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="307da-197">But, and this is new since mid-2017, if you specify the same image name, even with the same tag, the new multi-arch images (like the aspnetcore image which supports multi-arch) will use the Linux or Windows version depending on the Docker host OS you are deploying, as shown in the following example:</span></span>

-   <span data-ttu-id="307da-198">**microsoft/aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="307da-198">**microsoft/aspnetcore:2.0**</span></span>

        Multi-arch: .NET Core 2.0 runtime-only on Linux or Windows Nano Server depending on the Docker host OS

<span data-ttu-id="307da-199">Таким образом, при запросе образа с узла Windows будет получен вариант для Windows, а при запросе образа с тем же именем с узла Linux будет получен вариант для Linux.</span><span class="sxs-lookup"><span data-stu-id="307da-199">This way, when you pull an image from a Windows host, it will pull the Windows variant, and pulling the same image name from a Linux host will pull the Linux variant.</span></span>

### <a name="option-b-creating-your-base-image-from-scratch"></a><span data-ttu-id="307da-200">Вариант Б. Создание базового образа с нуля</span><span class="sxs-lookup"><span data-stu-id="307da-200">Option B: Creating your base image from scratch</span></span>

<span data-ttu-id="307da-201">Вы можете создать собственный базовый образ Docker с нуля.</span><span class="sxs-lookup"><span data-stu-id="307da-201">You can create your own Docker base image from scratch.</span></span> <span data-ttu-id="307da-202">Этот сценарий не рекомендуется для тех, кто только начинает работать с Docker, но если вы хотите задать определенные биты базового образа, это можно сделать.</span><span class="sxs-lookup"><span data-stu-id="307da-202">This scenario is not recommended for someone who is starting with Docker, but if you want to set the specific bits of your own base image, you can do so.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="307da-203">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="307da-203">Additional resources</span></span>

-   <span data-ttu-id="307da-204">**Мультиархитектурные образы .NET Core**.</span><span class="sxs-lookup"><span data-stu-id="307da-204">**Multi-arch .NET Core images**.</span></span>
<span data-ttu-id="307da-205">https://github.com/dotnet/announcements/issues/14</span><span class="sxs-lookup"><span data-stu-id="307da-205">https://github.com/dotnet/announcements/issues/14</span></span> 
-   <span data-ttu-id="307da-206">**Создание базового образа**.</span><span class="sxs-lookup"><span data-stu-id="307da-206">**Create a base image**.</span></span> <span data-ttu-id="307da-207">Официальная документация Docker.</span><span class="sxs-lookup"><span data-stu-id="307da-207">Official Docker documentation.</span></span>
    [<span data-ttu-id="307da-208">*https://docs.docker.com/engine/userguide/eng-image/baseimages/*</span><span class="sxs-lookup"><span data-stu-id="307da-208">*https://docs.docker.com/engine/userguide/eng-image/baseimages/*</span></span>](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a><span data-ttu-id="307da-209">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="307da-209">Step 3.</span></span> <span data-ttu-id="307da-210">Создание пользовательских образов Docker и внедрение в них собственных приложений или служб</span><span class="sxs-lookup"><span data-stu-id="307da-210">Create your custom Docker images and embed your application or service in them</span></span>

<span data-ttu-id="307da-211">Для каждой службы в приложении необходимо создать связанный образ.</span><span class="sxs-lookup"><span data-stu-id="307da-211">For each service in your application, you need to create a related image.</span></span> <span data-ttu-id="307da-212">Если приложение состоит из одной службы или веб-приложения, достаточно одного образа.</span><span class="sxs-lookup"><span data-stu-id="307da-212">If your application is made up of a single service or web application, you just need a single image.</span></span>

<span data-ttu-id="307da-213">Обратите внимание, что образы Docker в Visual Studio создаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="307da-213">Note that the Docker images are built automatically for you in Visual Studio.</span></span> <span data-ttu-id="307da-214">Следующие действия потребуются только в рабочем процессе с использованием редактора/CLI и подробно описываются, чтобы показать, что происходит внутри.</span><span class="sxs-lookup"><span data-stu-id="307da-214">The following steps are only needed for the editor/CLI workflow and explained for clarity about what happens underneath.</span></span>

<span data-ttu-id="307da-215">Разработчик должен выполнять разработку и тестирование локально до тех пор, пока не завершит и отправит компонент или пока не перейдет в систему управления версиями (например, в GitHub).</span><span class="sxs-lookup"><span data-stu-id="307da-215">You, as developer, need to develop and test locally until you push a completed feature or change to your source control system (for example, to GitHub).</span></span> <span data-ttu-id="307da-216">Это означает, что необходимо создавать образы Docker и разворачивать контейнеры на локальном узле Docker (на виртуальной машине Windows или Linux), а затем выполнять запуск, тестирование и отладку этих локальных контейнеров.</span><span class="sxs-lookup"><span data-stu-id="307da-216">This means that you need to create the Docker images and deploy containers to a local Docker host (Windows or Linux VM) and run, test, and debug against those local containers.</span></span>

<span data-ttu-id="307da-217">Чтобы создать пользовательский образ в локальной среде с помощью Docker CLI и Dockerfile, можно использовать команду docker build, как показано на рисунке 5-5.</span><span class="sxs-lookup"><span data-stu-id="307da-217">To create a custom image in your local environment by using Docker CLI and your Dockerfile, you can use the docker build command, as in Figure 5-5.</span></span>

![](./media/image8.png)

<span data-ttu-id="307da-218">**Рис. 5-5**.</span><span class="sxs-lookup"><span data-stu-id="307da-218">**Figure 5-5**.</span></span> <span data-ttu-id="307da-219">Создание пользовательского образа Docker</span><span class="sxs-lookup"><span data-stu-id="307da-219">Creating a custom Docker image</span></span>

<span data-ttu-id="307da-220">При необходимости вместо непосредственного выполнения команды docker build из папки проекта можно сначала создать развертываемую папку с нужными библиотеками .NET и двоичными файлами, выполнив команду dotnet publish, а затем использовать команду docker build.</span><span class="sxs-lookup"><span data-stu-id="307da-220">Optionally, instead of directly running docker build from the project folder, you can first generate a deployable folder with the required .NET libraries and binaries by running dotnet publish, and then use the docker build command.</span></span>

<span data-ttu-id="307da-221">Так будет создан образ Docker с именем cesardl/netcore-webapi-microservice-docker:first.</span><span class="sxs-lookup"><span data-stu-id="307da-221">This will create a Docker image with the name cesardl/netcore-webapi-microservice-docker:first.</span></span> <span data-ttu-id="307da-222">В данном случае :first — это тег, представляющий конкретную версию.</span><span class="sxs-lookup"><span data-stu-id="307da-222">In this case, :first is a tag representing a specific version.</span></span> <span data-ttu-id="307da-223">Этот шаг можно повторить для каждого пользовательского образа, который вам требуется создать для своего составного приложения Docker.</span><span class="sxs-lookup"><span data-stu-id="307da-223">You can repeat this step for each custom image you need to create for your composed Docker application.</span></span>

<span data-ttu-id="307da-224">Если приложение состоит из нескольких контейнеров (т. е. это многоконтейнерное приложение), можно также использовать команду docker-compose up --build, чтобы собрать все связанные образы одной командой с помощью метаданных, представленных в связанном файле docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="307da-224">When an application is made of multiple containers (that is, it is a multi-container application), you can also use the docker-compose up --build command to build all the related images with a single command by using the metadata exposed in the related docker-compose.yml files.</span></span>

<span data-ttu-id="307da-225">Вы можете найти существующие в локальном репозитории образы с помощью команды docker images, как показано на рисунке 5-6.</span><span class="sxs-lookup"><span data-stu-id="307da-225">You can find the existing images in your local repository by using the docker images command, as shown in Figure 5-6.</span></span>

![](./media/image9.png)

<span data-ttu-id="307da-226">**Рис. 5-6**.</span><span class="sxs-lookup"><span data-stu-id="307da-226">**Figure 5-6.**</span></span> <span data-ttu-id="307da-227">Просмотр существующих образов с помощью команды docker images</span><span class="sxs-lookup"><span data-stu-id="307da-227">Viewing existing images using the docker images command</span></span>

### <a name="creating-docker-images-with-visual-studio"></a><span data-ttu-id="307da-228">Создание образов Docker с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="307da-228">Creating Docker images with Visual Studio</span></span>

<span data-ttu-id="307da-229">При использовании Visual Studio для создания проекта с поддержкой Docker не требуется создавать образ явно.</span><span class="sxs-lookup"><span data-stu-id="307da-229">When you are using Visual Studio to create a project with Docker support, you do not explicitly create an image.</span></span> <span data-ttu-id="307da-230">Этот образ создается автоматически, когда вы нажимаете клавишу F5 и запускаете приложение или службу, добавленную в Docker.</span><span class="sxs-lookup"><span data-stu-id="307da-230">Instead, the image is created for you when you press F5 and run the dockerized application or service.</span></span> <span data-ttu-id="307da-231">Этот шаг выполняется в Visual Studio автоматически, и вы не увидите, как это происходит, но важно знать, что происходит внутри.</span><span class="sxs-lookup"><span data-stu-id="307da-231">This step is automatic in Visual Studio, and you will not see it happen, but it is important that you know what is going on underneath.</span></span>

![](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a><span data-ttu-id="307da-232">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="307da-232">Step 4.</span></span> <span data-ttu-id="307da-233">Определение служб в файле docker-compose.yml при сборке многоконтейнерного приложения Docker</span><span class="sxs-lookup"><span data-stu-id="307da-233">Define your services in docker-compose.yml when building a multi-container Docker application</span></span>

<span data-ttu-id="307da-234">В файле [docker-compose.yml](https://docs.docker.com/compose/compose-file/) можно задать ряд связанных служб для развертывания в качестве составного приложения с помощью команд развертывания.</span><span class="sxs-lookup"><span data-stu-id="307da-234">The [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file lets you define a set of related services to be deployed as a composed application with deployment commands.</span></span>

<span data-ttu-id="307da-235">Чтобы использовать файл docker-compose.yml, его необходимо создать в основной или корневой папке решения, и его содержимое должно быть аналогично приведенному в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="307da-235">To use a docker-compose.yml file, you need to create the file in your main or root solution folder, with content similar to that in the following example:</span></span>

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

<span data-ttu-id="307da-236">Обратите внимание, что данный файл docker-compose.yml представляет собой упрощенную и объединенную версию.</span><span class="sxs-lookup"><span data-stu-id="307da-236">Note that this docker-compose.yml file is a simplified and merged version.</span></span> <span data-ttu-id="307da-237">Он содержит статические данные конфигурации для каждого контейнера (такие как имя пользовательского образа), которые применяются всегда, а также сведения о конфигурации, которые могут зависеть от среды развертывания, такие как строка подключения.</span><span class="sxs-lookup"><span data-stu-id="307da-237">It contains static configuration data for each container (like the name of the custom image), which always applies, plus configuration information that might depend on the deployment environment, like the connection string.</span></span> <span data-ttu-id="307da-238">В следующих разделах вы узнаете, как можно разбить конфигурацию в файле docker-compose.yml на несколько файлов docker-compose и переопределить значения в зависимости от среды и типа выполнения (отладка или выпуск).</span><span class="sxs-lookup"><span data-stu-id="307da-238">In later sections, you will learn how you can split the docker-compose.yml configuration into multiple docker-compose files and override values depending on the environment and execution type (debug or release).</span></span>

<span data-ttu-id="307da-239">В примере файла docker-compose.yml определяются четыре службы: служба webmvc (веб-приложение), две микрослужбы (catalog.api и ordering.api) и один контейнер источника данных, sql.data, на основе SQL Server для Linux, работающий как контейнер.</span><span class="sxs-lookup"><span data-stu-id="307da-239">The docker-compose.yml file example defines five services: the webmvc service (a web application), two microservices (catalog.api and ordering.api), and one data source container, sql.data, based on SQL Server for Linux running as a container.</span></span> <span data-ttu-id="307da-240">Каждая служба развертывается как контейнер, поэтому образ Docker требуется для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="307da-240">Each service is deployed as a container, so a Docker image is required for each.</span></span>

<span data-ttu-id="307da-241">Файл docker-compose.yml задает не только используемые контейнеры, но и их индивидуальные конфигурации.</span><span class="sxs-lookup"><span data-stu-id="307da-241">The docker-compose.yml file specifies not only what containers are being used, but how they are individually configured.</span></span> <span data-ttu-id="307da-242">Например, в определении контейнера webmvc в файле .yml задается следующее.</span><span class="sxs-lookup"><span data-stu-id="307da-242">For instance, the webmvc container definition in the .yml file:</span></span>

-   <span data-ttu-id="307da-243">Используется предварительно созданный образ eshop/web:latest.</span><span class="sxs-lookup"><span data-stu-id="307da-243">Uses a pre-built eshop/web:latest image.</span></span> <span data-ttu-id="307da-244">Однако вы также можете настроить сборку этого образа при выполнении команды docker-compose с дополнительной конфигурацией на основе раздела build: в файле docker-compose.</span><span class="sxs-lookup"><span data-stu-id="307da-244">However, you could also configure the image to be built as part of the docker-compose execution with an additional configuration based on a build: section in the docker-compose file.</span></span>

-   <span data-ttu-id="307da-245">Инициализируются две переменные среды (CatalogUrl и OrderingUrl).</span><span class="sxs-lookup"><span data-stu-id="307da-245">Initializes two environment variables (CatalogUrl and OrderingUrl).</span></span>

-   <span data-ttu-id="307da-246">Предоставленный порт 80 в контейнере переадресуется на внешний порт 80 на хост-компьютере.</span><span class="sxs-lookup"><span data-stu-id="307da-246">Forwards the exposed port 80 on the container to the external port 80 on the host machine.</span></span>

-   <span data-ttu-id="307da-247">Веб-приложение связывается со службами catalog и ordering с помощью параметра depends\_on.</span><span class="sxs-lookup"><span data-stu-id="307da-247">Links the web app to the catalog and ordering service with the depends\_on setting.</span></span> <span data-ttu-id="307da-248">В результате данная служба будет ожидать запуска этих служб.</span><span class="sxs-lookup"><span data-stu-id="307da-248">This causes the service to wait until those services are started.</span></span>

<span data-ttu-id="307da-249">Мы вернемся к файлу docker-compose.yml в следующем разделе, когда будем рассматривать реализацию микрослужб и многоконтейнерных приложений.</span><span class="sxs-lookup"><span data-stu-id="307da-249">We will revisit the docker-compose.yml file in a later section when we cover how to implement microservices and multi-container apps.</span></span>

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a><span data-ttu-id="307da-250">Работа с файлом docker-compose.yml в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="307da-250">Working with docker-compose.yml in Visual Studio 2017</span></span>

<span data-ttu-id="307da-251">Когда вы добавляете поддержку решения Docker в проект службы в решении Visual Studio, как показано на рисунке 5-7, Visual Studio добавляет в ваш проект Dockerfile, а также добавляет в ваше решение раздел служб (проект) с помощью файла docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="307da-251">When you add Docker solution support to a service project in a Visual Studio solution, as shown in Figure 5-7, Visual Studio adds a Dockerfile to your project, and it adds a service section (project) in your solution with the docker-compose.yml files.</span></span> <span data-ttu-id="307da-252">Это простой способ начать создание многоконтейнерного решения.</span><span class="sxs-lookup"><span data-stu-id="307da-252">It is an easy way to start composing your multiple-container solution.</span></span> <span data-ttu-id="307da-253">Затем можно открыть файлы docker-compose.yml и добавить в них дополнительные возможности.</span><span class="sxs-lookup"><span data-stu-id="307da-253">You can then open the docker-compose.yml files and update them with additional features.</span></span>

![](./media/image6.png)

<span data-ttu-id="307da-254">**Рис. 5-7**.</span><span class="sxs-lookup"><span data-stu-id="307da-254">**Figure 5-7**.</span></span> <span data-ttu-id="307da-255">Добавление поддержки Docker в Visual Studio 2017 щелчком правой кнопкой мыши на проекте ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="307da-255">Adding Docker support in Visual Studio 2017 by right-clicking an ASP.NET Core project</span></span>

<span data-ttu-id="307da-256">При добавлении поддержки Docker в Visual Studio помимо добавления в проект Dockerfile также добавляются сведения о конфигурации в несколько глобальных файлов docker-compose.yml, заданных на уровне решения.</span><span class="sxs-lookup"><span data-stu-id="307da-256">Adding Docker support in Visual Studio not only adds the Dockerfile to your project, but adds the configuration information to several global docker-compose.yml files that are set at the solution level.</span></span>

<span data-ttu-id="307da-257">После добавления поддержки Docker в решение в Visual Studio вы также увидите новый узел в обозревателе решений (в файле проекта docker-compose.dcproj), содержащий добавленные файлы docker-compose.yml, как показано на рисунке 5-8.</span><span class="sxs-lookup"><span data-stu-id="307da-257">After you add Docker support to your solution in Visual Studio, you will also see a new node (in the docker-compose.dcproj project file) in Solution Explorer that contains the added docker-compose.yml files, as shown in Figure 5-8.</span></span>

![](./media/image11.PNG)

<span data-ttu-id="307da-258">**Рис. 5-8**.</span><span class="sxs-lookup"><span data-stu-id="307da-258">**Figure 5-8**.</span></span> <span data-ttu-id="307da-259">Узел дерева **docker-compose**, добавленный в обозреватель решений Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="307da-259">The **docker-compose** tree node added in Visual Studio 2017 Solution Explorer</span></span>

<span data-ttu-id="307da-260">Можно было бы развернуть многоконтейнерное приложение с единственным файлом docker-compose.yml с помощью команды docker-compose up.</span><span class="sxs-lookup"><span data-stu-id="307da-260">You could deploy a multi-container application with a single docker-compose.yml file by using the docker-compose up command.</span></span> <span data-ttu-id="307da-261">Однако Visual Studio добавляет группу этих файлов, чтобы вы могли переопределять значения в зависимости от среды (разработки или рабочей) и типа выполнения (выпуска или отладки).</span><span class="sxs-lookup"><span data-stu-id="307da-261">However, Visual Studio adds a group of them so you can override values depending on the environment (development versus production) and execution type (release versus debug).</span></span> <span data-ttu-id="307da-262">Эта возможность разъясняется в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="307da-262">This capability will be explained in later sections.</span></span>

![](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a><span data-ttu-id="307da-263">Шаг 5.</span><span class="sxs-lookup"><span data-stu-id="307da-263">Step 5.</span></span> <span data-ttu-id="307da-264">Сборка и запуск приложения Docker</span><span class="sxs-lookup"><span data-stu-id="307da-264">Build and run your Docker application</span></span>

<span data-ttu-id="307da-265">Если в приложении имеется только один контейнер, его можно запустить путем развертывания на узле Docker (на виртуальной машине или физическом сервере).</span><span class="sxs-lookup"><span data-stu-id="307da-265">If your application only has a single container, you can run it by deploying it to your Docker host (VM or physical server).</span></span> <span data-ttu-id="307da-266">Но если приложение содержит несколько служб, его можно развернуть как составное приложение с помощью одной команды CLI (docker-compose up) или в Visual Studio, в котором внутри будет выполняться эта же команда.</span><span class="sxs-lookup"><span data-stu-id="307da-266">However, if your application contains multiple services, you can deploy it as a composed application, either using a single CLI command (docker-compose up), or with Visual Studio, which will use that command under the covers.</span></span> <span data-ttu-id="307da-267">Давайте рассмотрим разные варианты.</span><span class="sxs-lookup"><span data-stu-id="307da-267">Let’s look at the different options.</span></span>

### <a name="option-a-running-a-single-container-with-docker-cli"></a><span data-ttu-id="307da-268">Вариант А. Запуск единственного контейнера с помощью Docker CLI</span><span class="sxs-lookup"><span data-stu-id="307da-268">Option A: Running a single-container with Docker CLI</span></span>

<span data-ttu-id="307da-269">Контейнер Docker можно запустить с помощью команды docker run, как показано на рисунке 5-9.</span><span class="sxs-lookup"><span data-stu-id="307da-269">You can run a Docker container using the docker run command, as in Figure 5-9:</span></span>

```
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

![](./media/image13.png)

<span data-ttu-id="307da-270">**Рис. 5-9**.</span><span class="sxs-lookup"><span data-stu-id="307da-270">**Figure 5-9**.</span></span> <span data-ttu-id="307da-271">Запуск контейнера Docker с помощью команды docker run</span><span class="sxs-lookup"><span data-stu-id="307da-271">Running a Docker container using the docker run command</span></span>

<span data-ttu-id="307da-272">В этом случае команда привязывает внутренний порт 5000 контейнера к порту 80 хост-компьютера.</span><span class="sxs-lookup"><span data-stu-id="307da-272">In this case, the command binds the internal port 5000 of the container to port 80 of the host machine.</span></span> <span data-ttu-id="307da-273">Это означает, что узел выполняет прослушивание порта 80 и переадресацию в порт 5000 в контейнере.</span><span class="sxs-lookup"><span data-stu-id="307da-273">This means that the host is listening on port 80 and forwarding to port 5000 on the container.</span></span>

### <a name="option-b-running-a-multi-container-application"></a><span data-ttu-id="307da-274">Вариант Б. Запуск многоконтейнерного приложения</span><span class="sxs-lookup"><span data-stu-id="307da-274">Option B: Running a multi-container application</span></span>

<span data-ttu-id="307da-275">В большинстве корпоративных сценариев приложение Docker будет состоять из нескольких служб; это означает, что необходимо запускать многоконтейнерное приложение, как показано на рисунке 5-10.</span><span class="sxs-lookup"><span data-stu-id="307da-275">In most enterprise scenarios, a Docker application will be composed of multiple services, which means you need to run a multi-container application, as shown in Figure 5-10.</span></span>

![](./media/image14.png)

<span data-ttu-id="307da-276">**Рис. 5-10**.</span><span class="sxs-lookup"><span data-stu-id="307da-276">**Figure 5-10**.</span></span> <span data-ttu-id="307da-277">Виртуальная машина с развернутыми контейнерами Docker</span><span class="sxs-lookup"><span data-stu-id="307da-277">VM with Docker containers deployed</span></span>

#### <a name="running-a-multi-container-application-with-the-docker-cli"></a><span data-ttu-id="307da-278">Запуск многоконтейнерного приложения с помощью Docker CLI</span><span class="sxs-lookup"><span data-stu-id="307da-278">Running a multi-container application with the Docker CLI</span></span>

<span data-ttu-id="307da-279">Чтобы запустить многоконтейнерное приложение с помощью Docker CLI, можно выполнить команду docker-compose up.</span><span class="sxs-lookup"><span data-stu-id="307da-279">To run a multi-container application with the Docker CLI, you can run the docker-compose up command.</span></span> <span data-ttu-id="307da-280">Эта команда разворачивает многоконтейнерное приложение с помощью файла docker-compose.yml, существующего на уровне решения.</span><span class="sxs-lookup"><span data-stu-id="307da-280">This command uses the docker-compose.yml file that you have at the solution level to deploy a multi-container application.</span></span> <span data-ttu-id="307da-281">На рисунке 5-11 показаны результаты выполнения этой команды из главного каталога проекта, в котором находится файл docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="307da-281">Figure 5-11 shows the results when running the command from your main project directory, which contains the docker-compose.yml file.</span></span>

![](./media/image15.png)

<span data-ttu-id="307da-282">**Рис. 5-11**.</span><span class="sxs-lookup"><span data-stu-id="307da-282">**Figure 5-11**.</span></span> <span data-ttu-id="307da-283">Пример результата выполнения команды docker-compose up</span><span class="sxs-lookup"><span data-stu-id="307da-283">Example results when running the docker-compose up command</span></span>

<span data-ttu-id="307da-284">После выполнения команды docker-compose up приложение и связанные с ним контейнеры развертываются в узле Docker, как показано в представлении виртуальной машины на рисунке 5-10.</span><span class="sxs-lookup"><span data-stu-id="307da-284">After the docker-compose up command runs, the application and its related containers are deployed into your Docker host, as illustrated in the VM representation in Figure 5-10.</span></span>

#### <a name="running-and-debugging-a-multi-container-application-with-visual-studio"></a><span data-ttu-id="307da-285">Запуск и отладка многоконтейнерного приложения с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="307da-285">Running and debugging a multi-container application with Visual Studio</span></span> 

<span data-ttu-id="307da-286">Запуск многоконтейнерного приложения с помощью Visual Studio 2017 не может быть проще.</span><span class="sxs-lookup"><span data-stu-id="307da-286">Running a multi-container application using Visual Studio 2017 cannot get simpler.</span></span> <span data-ttu-id="307da-287">Вы можете не только запускать многоконтейнерное приложение, но также и отлаживать все его контейнеры непосредственно в Visual Studio, установив обычные точки останова.</span><span class="sxs-lookup"><span data-stu-id="307da-287">You can not only run the multi-container application, but you are able to debug all its containers directly from Visual Studio by setting regular breakpoints.</span></span>

<span data-ttu-id="307da-288">Как упоминалось ранее, каждый раз при добавлении поддержки решения Docker в проект в решении этот проект настраивается в глобальном (на уровне решения) файле docker-compose.yml, что позволяет запускать или отлаживать все решение сразу.</span><span class="sxs-lookup"><span data-stu-id="307da-288">As mentioned before, each time you add Docker solution support to a project within a solution, that project is configured in the global (solution-level) docker-compose.yml file, which lets you run or debug the whole solution at once.</span></span> <span data-ttu-id="307da-289">Visual Studio будет запускать по одному контейнеру для каждого проекта с включенной поддержкой решения Docker и выполнять все внутренние шаги автоматически (dotnet publish, docker build и т. д.).</span><span class="sxs-lookup"><span data-stu-id="307da-289">Visual Studio will start one container for each project that has Docker solution support enabled, and perform all the internal steps for you (dotnet publish, docker build, etc.).</span></span>

<span data-ttu-id="307da-290">Здесь важно то, что, как показано на рисунке 5-12, в Visual Studio 2017 имеется дополнительная команда **Docker** для действия клавиши F5.</span><span class="sxs-lookup"><span data-stu-id="307da-290">The important point here is that, as shown in Figure 5-12, in Visual Studio 2017 there is an additional **Docker** command for the F5 key action.</span></span> <span data-ttu-id="307da-291">Эта возможность позволяет запускать или отлаживать многоконтейнерное приложение путем запуска всех контейнеров, определенных в файлах docker-compose.yml на уровне решения.</span><span class="sxs-lookup"><span data-stu-id="307da-291">This option lets you run or debug a multi-container application by running all the containers that are defined in the docker-compose.yml files at the solution level.</span></span> <span data-ttu-id="307da-292">Возможность отладки многоконтейнерных решений означает, что можно установить несколько точек останова, чтобы все они были в разных проектах (контейнерах), и во время отладки из Visual Studio вы будете останавливаться в точках останова, заданных в разных проектах, и работать в разных контейнерах.</span><span class="sxs-lookup"><span data-stu-id="307da-292">The ability to debug multiple-container solutions means that you can set several breakpoints, each breakpoint in a different project (container), and while debugging from Visual Studio you will stop at breakpoints defined in different projects and running on different containers.</span></span>

![](./media/image16.png)

<span data-ttu-id="307da-293">**Рис. 5-12**.</span><span class="sxs-lookup"><span data-stu-id="307da-293">**Figure 5-12**.</span></span> <span data-ttu-id="307da-294">Запуск многоконтейнерных приложений в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="307da-294">Running multi-container apps in Visual Studio 2017</span></span>

### <a name="additional-resources"></a><span data-ttu-id="307da-295">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="307da-295">Additional resources</span></span>

-   <span data-ttu-id="307da-296">**Развертывание контейнера ASP.NET на удаленном узле Docker**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="307da-296">**Deploy an ASP.NET container to a remote Docker host**
[*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a><span data-ttu-id="307da-297">Примечание о тестировании и развертывании с использованием оркестраторов</span><span class="sxs-lookup"><span data-stu-id="307da-297">A note about testing and deploying with orchestrators</span></span>

<span data-ttu-id="307da-298">Команды docker-compose up и docker run (или запуск и отладка контейнеров в Visual Studio) подходят для тестирования контейнеров в вашей среде разработки.</span><span class="sxs-lookup"><span data-stu-id="307da-298">The docker-compose up and docker run commands (or running and debugging the containers in Visual Studio) are adequate for testing containers in your development environment.</span></span> <span data-ttu-id="307da-299">Однако этот способ не подходит, если вы планируете использовать оркестраторы и кластеры Docker, такие как Docker Swarm, Mesosphere DC/OS и Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="307da-299">But you should not use this approach if you are targeting Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes.</span></span> <span data-ttu-id="307da-300">Если вы используете кластер, например [режим Docker Swarm](https://docs.docker.com/engine/swarm/) (доступный в Docker CE для Windows и Mac, начиная с версии 1.12), необходимо выполнять развертывание и тестирование единственных служб с помощью дополнительных команд, таких как [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/).</span><span class="sxs-lookup"><span data-stu-id="307da-300">If you are using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker CE for Windows and Mac since version 1.12), you need to deploy and test with additional commands like [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/) for single services.</span></span> <span data-ttu-id="307da-301">При развертывании приложения, состоящего из нескольких контейнеров, следует использовать команды [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) и [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/), чтобы развернуть составное приложение как *стек*.</span><span class="sxs-lookup"><span data-stu-id="307da-301">If you are deploying an application composed of several containers, you use [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) and [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) to deploy the composed application as a *stack*.</span></span> <span data-ttu-id="307da-302">Дополнительные сведения см. в записи блога [Introducing Experimental Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) (Общие сведения об экспериментальных пакетах распределенных приложений) в документации Docker</span><span class="sxs-lookup"><span data-stu-id="307da-302">For more information, see the blog post [Introducing Experimental Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) in the Docker documentation.</span></span> <span data-ttu-id="307da-303">на сайте Docker.</span><span class="sxs-lookup"><span data-stu-id="307da-303">on the Docker site.</span></span>

<span data-ttu-id="307da-304">Для [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) и [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/) вы также должны использовать другие скрипты и команды развертывания.</span><span class="sxs-lookup"><span data-stu-id="307da-304">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/) you would use different deployment commands and scripts as well.</span></span>

![](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a><span data-ttu-id="307da-305">Шаг 6.</span><span class="sxs-lookup"><span data-stu-id="307da-305">Step 6.</span></span> <span data-ttu-id="307da-306">Тестирование приложения Docker с помощью локального узла Docker</span><span class="sxs-lookup"><span data-stu-id="307da-306">Test your Docker application using your local Docker host</span></span>

<span data-ttu-id="307da-307">Этот шаг будет зависеть от того, что делает ваше приложение.</span><span class="sxs-lookup"><span data-stu-id="307da-307">This step will vary depending on what your application is doing.</span></span> <span data-ttu-id="307da-308">В случае простого веб-приложения .NET Core, развернутого в виде единственного контейнера или службы, можно получить доступ к этой службе, открыв на узле Docker браузер и перейдя в нем на этот сайт, как показано на рисунке 5-13.</span><span class="sxs-lookup"><span data-stu-id="307da-308">In a simple .NET Core Web application that is deployed as a single container or service, you can access the service by opening a browser on the Docker host and navigating to that site as shown in Figure 5-13.</span></span> <span data-ttu-id="307da-309">(Если конфигурация в Dockerfile сопоставляет контейнер с портом узла, отличным от 80, укажите этот порт узла в URL-адресе.)</span><span class="sxs-lookup"><span data-stu-id="307da-309">(If the configuration in the Dockerfile maps the container to a port on the host that is anything other than 80, include the host post in the URL.)</span></span>

![](./media/image18.png)

<span data-ttu-id="307da-310">**Рис. 5-13**.</span><span class="sxs-lookup"><span data-stu-id="307da-310">**Figure 5-13**.</span></span> <span data-ttu-id="307da-311">Пример локального тестирования приложения Docker с помощью localhost</span><span class="sxs-lookup"><span data-stu-id="307da-311">Example of testing your Docker application locally using localhost</span></span>

<span data-ttu-id="307da-312">Если localhost не указывает на IP-адрес узла Docker (при использовании Docker CE это должно происходить по умолчанию), то для перехода к службе используйте IP-адрес сетевой карты вашего компьютера.</span><span class="sxs-lookup"><span data-stu-id="307da-312">If localhost is not pointing to the Docker host IP (by default, when using Docker CE, it should), to navigate to your service, use the IP address of your machine’s network card.</span></span>

<span data-ttu-id="307da-313">Обратите внимание, что этот URL-адрес в браузере использует порт 80 для рассматриваемого примера конкретного контейнера.</span><span class="sxs-lookup"><span data-stu-id="307da-313">Note that this URL in the browser uses port 80 for the particular container example being discussed.</span></span> <span data-ttu-id="307da-314">Однако внутренние запросы перенаправляются на порт 5000, поскольку именно так было выполнено развертывание с помощью команды docker run, как описано в предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="307da-314">However, internally the requests are being redirected to port 5000, because that was how it was deployed with the docker run command, as explained in a previous step.</span></span>

<span data-ttu-id="307da-315">Вы также можете тестировать приложение с помощью команды curl с терминала, как показано на рисунке 5-14.</span><span class="sxs-lookup"><span data-stu-id="307da-315">You can also test the application using curl from the terminal, as shown in Figure 5-14.</span></span> <span data-ttu-id="307da-316">В случае установки Docker в Windows по умолчанию всегда будет использоваться IP-адрес узла Docker 10.0.75.1 помимо фактического IP-адреса вашего компьютера.</span><span class="sxs-lookup"><span data-stu-id="307da-316">In a Docker installation on Windows, the default Docker Host IP is always 10.0.75.1 in addition to your machine’s actual IP address.</span></span>

![](./media/image19.png)

<span data-ttu-id="307da-317">**Рис. 5-14**.</span><span class="sxs-lookup"><span data-stu-id="307da-317">**Figure 5-14**.</span></span> <span data-ttu-id="307da-318">Пример локального тестирования приложения Docker с помощью curl</span><span class="sxs-lookup"><span data-stu-id="307da-318">Example of testing your Docker application locally using curl</span></span>

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a><span data-ttu-id="307da-319">Тестирование и отладка контейнеров в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="307da-319">Testing and debugging containers with Visual Studio 2017</span></span>

<span data-ttu-id="307da-320">При запуске и отладке контейнеров в Visual Studio 2017 вы можете отлаживать приложения .NET в основном так же, как при запуске без контейнеров.</span><span class="sxs-lookup"><span data-stu-id="307da-320">When running and debugging the containers with Visual Studio 2017, you can debug the .NET application in much the same way as you would when running without containers.</span></span>

### <a name="testing-and-debugging-without-visual-studio"></a><span data-ttu-id="307da-321">Тестирование и отладка без Visual Studio</span><span class="sxs-lookup"><span data-stu-id="307da-321">Testing and debugging without Visual Studio</span></span>

<span data-ttu-id="307da-322">Если при разработке используется редактор или CLI, отлаживать контейнеры будет значительно труднее, и вы захотите выполнять отладку путем создания трассировок.</span><span class="sxs-lookup"><span data-stu-id="307da-322">If you are developing using the editor/CLI approach, debugging containers is more difficult and you will want to debug by generating traces.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="307da-323">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="307da-323">Additional resources</span></span>

-   <span data-ttu-id="307da-324">**Отладка приложений в локальном контейнере Docker**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="307da-324">**Debugging apps in a local Docker container**
[*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

-   <span data-ttu-id="307da-325">**Стив Ласкер (Steve Lasker). Сборка, отладка, развертывание приложений ASP.NET Core с помощью Docker.**</span><span class="sxs-lookup"><span data-stu-id="307da-325">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker.**</span></span> <span data-ttu-id="307da-326">Видео.</span><span class="sxs-lookup"><span data-stu-id="307da-326">Video.</span></span>
    [<span data-ttu-id="307da-327">*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*</span><span class="sxs-lookup"><span data-stu-id="307da-327">*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*</span></span>](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a><span data-ttu-id="307da-328">Упрощенный рабочий процесс при разработке контейнеров в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="307da-328">Simplified workflow when developing containers with Visual Studio</span></span>

<span data-ttu-id="307da-329">В сущности, при использовании Visual Studio рабочий процесс гораздо проще, чем при использовании редактора или CLI.</span><span class="sxs-lookup"><span data-stu-id="307da-329">Effectively, the workflow when using Visual Studio is a lot simpler than if you use the editor/CLI approach.</span></span> <span data-ttu-id="307da-330">Большинство шагов, необходимых для Docker и связанных с Dockerfile и docker-compose.yml, выполняются скрыто от пользователя или значительно упрощаются благодаря Visual Studio, как показано на рисунке 5-15.</span><span class="sxs-lookup"><span data-stu-id="307da-330">Most of the steps required by Docker related to the Dockerfile and docker-compose.yml files are hidden or simplified by Visual Studio, as shown in Figure 5-15.</span></span>

![](./media/image20.png)

<span data-ttu-id="307da-331">**Рис. 5-15**.</span><span class="sxs-lookup"><span data-stu-id="307da-331">**Figure 5-15**.</span></span> <span data-ttu-id="307da-332">Упрощенный рабочий процесс при разработке в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="307da-332">Simplified workflow when developing with Visual Studio</span></span>

<span data-ttu-id="307da-333">Кроме того, вам достаточно будет выполнить шаг 2 (добавление поддержки Docker в проекты) только один раз.</span><span class="sxs-lookup"><span data-stu-id="307da-333">In addition, you need to perform step 2 (adding Docker support to your projects) just once.</span></span> <span data-ttu-id="307da-334">Таким образом, рабочий процесс аналогичен другим обычным задачам разработки, когда для разработки используется .NET.</span><span class="sxs-lookup"><span data-stu-id="307da-334">Therefore, the workflow is similar to your usual development tasks when using .NET for any other development.</span></span> <span data-ttu-id="307da-335">Вам нужно знать, что происходит на самом деле (процесс создания образа, какие базовые образы используются, развертывание контейнеров и т. п.), и в некоторых случаях также может потребоваться изменить файл Dockerfile или docker-compose.yml, чтобы настроить функциональность.</span><span class="sxs-lookup"><span data-stu-id="307da-335">You need to know what is going on under the covers (the image build process, what base images you are using, deployment of containers, etc.) and sometimes you will also need to edit the Dockerfile or docker-compose.yml file to customize behaviors.</span></span> <span data-ttu-id="307da-336">Но благодаря Visual Studio большую часть работы можно выполнить гораздо проще, что существенно повышает эффективность работы.</span><span class="sxs-lookup"><span data-stu-id="307da-336">But most of the work is greatly simplified by using Visual Studio, making you a lot more productive.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="307da-337">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="307da-337">Additional resources</span></span>

-   <span data-ttu-id="307da-338">**Стив Ласкер (Steve Lasker). Разработка .NET Docker в Visual Studio 2017**
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)</span><span class="sxs-lookup"><span data-stu-id="307da-338">**Steve Lasker. .NET Docker Development with Visual Studio 2017**
[*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)</span></span>

-   <span data-ttu-id="307da-339">**Джеффри Т. Фриц (Jeffrey T. Fritz). Помещение приложения .NET Core в контейнер с помощью новых средств Docker для Visual Studio**
    [*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)</span><span class="sxs-lookup"><span data-stu-id="307da-339">**Jeffrey T. Fritz. Put a .NET Core App in a Container with the new Docker Tools for Visual Studio**
[*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)</span></span>

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a><span data-ttu-id="307da-340">Использование команд PowerShell в DockerFile для настройки контейнеров Windows</span><span class="sxs-lookup"><span data-stu-id="307da-340">Using PowerShell commands in a Dockerfile to set up Windows Containers</span></span> 

<span data-ttu-id="307da-341">[Контейнеры Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) позволяют преобразовывать существующие приложения Windows в образы Docker и развертывать их с помощью тех же средств, что и остальную часть экосистемы Docker.</span><span class="sxs-lookup"><span data-stu-id="307da-341">[Windows Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) allow you to convert your existing Windows applications into Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span> <span data-ttu-id="307da-342">Чтобы использовать контейнеры Windows, выполните команды PowerShell в Dockerfile, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="307da-342">To use Windows Containers, you run PowerShell commands in the Dockerfile, as shown in the following example:</span></span>

```
FROM microsoft/windowsservercore
  
LABEL Description="IIS" Vendor="Microsoft" Version="10"
  
RUN powershell -Command Add-WindowsFeature Web-Server
  
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="307da-343">В этом случае мы используем базовый образ Windows Server Core (параметр FROM) и устанавливаем службы IIS с помощью команды PowerShell (параметр RUN).</span><span class="sxs-lookup"><span data-stu-id="307da-343">In this case, we are using a Windows Server Core base image (the FROM setting) and installing IIS with a PowerShell command (the RUN setting).</span></span> <span data-ttu-id="307da-344">Аналогичным образом можно также использовать команды PowerShell для настройки дополнительных компонентов, таких как ASP.NET 4.x, .NET 4.6 и другого программного обеспечения Windows.</span><span class="sxs-lookup"><span data-stu-id="307da-344">In a similar way, you could also use PowerShell commands to set up additional components like ASP.NET 4.x, .NET 4.6, or any other Windows software.</span></span> <span data-ttu-id="307da-345">Например, следующая команда в Dockerfile настраивает ASP.NET 4.5:</span><span class="sxs-lookup"><span data-stu-id="307da-345">For example, the following command in a Dockerfile sets up ASP.NET 4.5:</span></span>

```
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a><span data-ttu-id="307da-346">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="307da-346">Additional resources</span></span>

-   <span data-ttu-id="307da-347">**aspnet-docker/Dockerfile.**</span><span class="sxs-lookup"><span data-stu-id="307da-347">**aspnet-docker/Dockerfile.**</span></span> <span data-ttu-id="307da-348">Примеры команд Powershell, которые можно выполнять в файлах Dockerfile для включения компонентов Windows.</span><span class="sxs-lookup"><span data-stu-id="307da-348">Example Powershell commands to run from dockerfiles to include Windows features.</span></span>
    [<span data-ttu-id="307da-349">*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*</span><span class="sxs-lookup"><span data-stu-id="307da-349">*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*</span></span>](https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile)

>[!div class="step-by-step"]
<span data-ttu-id="307da-350">[Назад] (index.md) [Далее] (../net-core-single-containers-linux-windows-server-hosts/index.md)</span><span class="sxs-lookup"><span data-stu-id="307da-350">[Previous] (index.md) [Next] (../net-core-single-containers-linux-windows-server-hosts/index.md)</span></span>
