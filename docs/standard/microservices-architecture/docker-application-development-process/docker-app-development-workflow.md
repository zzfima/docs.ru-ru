---
title: Рабочий процесс разработки для приложений Docker
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Рабочий процесс разработки для приложений Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: 2eb205e85300f22108b866e8446d6730d89ae6cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="development-workflow-for-docker-apps"></a><span data-ttu-id="63b41-103">Рабочий процесс разработки для приложений Docker</span><span class="sxs-lookup"><span data-stu-id="63b41-103">Development workflow for Docker apps</span></span>

<span data-ttu-id="63b41-104">Жизненный цикл разработки приложений начинается на компьютере каждого разработчика, где разработчик локально программирует приложение на предпочитаемом языке и тестирует его.</span><span class="sxs-lookup"><span data-stu-id="63b41-104">The application development lifecycle starts at each developer’s machine, where the developer codes the application using their preferred language and tests it locally.</span></span> <span data-ttu-id="63b41-105">Независимо от выбранного языка, инфраструктуры и платформы, в рамках этого рабочего процесса разработчик всегда разрабатывает и тестирует контейнеры Docker, но делает это локально.</span><span class="sxs-lookup"><span data-stu-id="63b41-105">No matter which language, framework, and platform the developer chooses, with this workflow, the developer is always developing and testing Docker containers, but doing so locally.</span></span>

<span data-ttu-id="63b41-106">В каждый контейнер (экземпляр образа Docker) входят следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="63b41-106">Each container (an instance of a Docker image) includes the following components:</span></span>

-   <span data-ttu-id="63b41-107">Выбранная операционная система (например, дистрибутив Linux, Windows Nano Server или Windows Server Core).</span><span class="sxs-lookup"><span data-stu-id="63b41-107">An operating system selection (for example, a Linux distribution, Windows Nano Server, or Windows Server Core).</span></span>

-   <span data-ttu-id="63b41-108">Файлы, добавленные разработчиком (двоичные файлы приложения и т. п.).</span><span class="sxs-lookup"><span data-stu-id="63b41-108">Files added by the developer (application binaries, etc.).</span></span>

-   <span data-ttu-id="63b41-109">Сведения о конфигурации (параметры среды и зависимости).</span><span class="sxs-lookup"><span data-stu-id="63b41-109">Configuration information (environment settings and dependencies).</span></span>

## <a name="workflow-for-developing-docker-container-based-applications"></a><span data-ttu-id="63b41-110">Рабочий процесс разработки приложений Docker на основе контейнера</span><span class="sxs-lookup"><span data-stu-id="63b41-110">Workflow for developing Docker container-based applications</span></span>

<span data-ttu-id="63b41-111">В этом разделе описывается рабочий процесс *внутреннего цикла* разработки приложений на основе контейнера Docker.</span><span class="sxs-lookup"><span data-stu-id="63b41-111">This section describes the *inner-loop* development workflow for Docker container-based applications.</span></span> <span data-ttu-id="63b41-112">Рабочий процесс внутреннего цикла означает, что речь идет только о разработке, которая выполняется на компьютере разработчика, не касаясь более широкого рабочего процесса DevOps.</span><span class="sxs-lookup"><span data-stu-id="63b41-112">The inner-loop workflow means it is not taking into account the broader DevOps workflow and just focuses on the development work done on the developer’s computer.</span></span> <span data-ttu-id="63b41-113">Начальные этапы настройки среды здесь не рассматриваются, так как они выполняются только один раз.</span><span class="sxs-lookup"><span data-stu-id="63b41-113">The initial steps to set up the environment are not included, since those are done only once.</span></span>

<span data-ttu-id="63b41-114">Приложение состоит из ваших собственных служб и дополнительных библиотек (зависимостей).</span><span class="sxs-lookup"><span data-stu-id="63b41-114">An application is composed of your own services plus additional libraries (dependencies).</span></span> <span data-ttu-id="63b41-115">Ниже приведены основные шаги, которые обычно выполняются при сборке приложения Docker, как показано на рисунке 5-1.</span><span class="sxs-lookup"><span data-stu-id="63b41-115">The following are the basic steps you usually take when building a Docker application, as illustrated in Figure 5-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="63b41-116">**Рис. 5-1**.</span><span class="sxs-lookup"><span data-stu-id="63b41-116">**Figure 5-1.**</span></span> <span data-ttu-id="63b41-117">Пошаговый рабочий процесс разработки приложения на основе контейнера Docker</span><span class="sxs-lookup"><span data-stu-id="63b41-117">Step-by-step workflow for developing Docker containerized apps</span></span>

<span data-ttu-id="63b41-118">В этом руководстве подробно описывается весь процесс, и каждый важный шаг объясняется с акцентом на среду Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="63b41-118">In this guide, this whole process is detailed and every major step is explained by focusing on a Visual Studio environment.</span></span>

<span data-ttu-id="63b41-119">Если разработка выполняется с помощью редактора и CLI (например, Visual Studio Code и Docker CLI на macOS или Windows), то необходимо знать каждый шаг и обычно более детально, чем при использовании Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="63b41-119">When you are using an editor/CLI development approach (for example, Visual Studio Code plus Docker CLI on macOS or Windows), you need to know every step, generally in more detail than if you are using Visual Studio.</span></span> <span data-ttu-id="63b41-120">Дополнительные сведения о работе в среде CLI см. в электронной книге [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](http://aka.ms/dockerlifecycleebook/).</span><span class="sxs-lookup"><span data-stu-id="63b41-120">For more details about working in a CLI environment, refer to the e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](http://aka.ms/dockerlifecycleebook/).</span></span>

<span data-ttu-id="63b41-121">При использовании Visual Studio 2015 или Visual Studio 2017 многие из этих шагов выполняются автоматически, что значительно повышает производительность.</span><span class="sxs-lookup"><span data-stu-id="63b41-121">When you are using Visual Studio 2015 or Visual Studio 2017, many of those steps are handled for you, which dramatically improves your productivity.</span></span> <span data-ttu-id="63b41-122">Это особенно справедливо в тех случаях, когда используется Visual Studio 2017 и планируется создание многоконтейнерных приложений.</span><span class="sxs-lookup"><span data-stu-id="63b41-122">This is especially true when you are using Visual Studio 2017 and targeting multi-container applications.</span></span> <span data-ttu-id="63b41-123">Например, всего лишь одним щелчком мыши Visual Studio добавляет в проект Dockerfile и файл docker-compose.yml с конфигурацией для вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="63b41-123">For instance, with just one mouse click, Visual Studio adds the Dockerfile and docker-compose.yml file to your projects with the configuration for your application.</span></span> <span data-ttu-id="63b41-124">При запуске приложения в Visual Studio он создает образ Docker и запускает многоконтейнерное приложение непосредственно в Docker; вы даже можете отлаживать несколько контейнеров одновременно.</span><span class="sxs-lookup"><span data-stu-id="63b41-124">When you run the application in Visual Studio, it builds the Docker image and runs the multi-container application directly in Docker; it even allows you to debug several containers at once.</span></span> <span data-ttu-id="63b41-125">Эти возможности значительно повышают скорость разработки.</span><span class="sxs-lookup"><span data-stu-id="63b41-125">These features will boost your development speed.</span></span>

<span data-ttu-id="63b41-126">Однако то, что Visual Studio автоматизирует эти действия, не означает, что вам не нужно знать, что происходит внутри Docker.</span><span class="sxs-lookup"><span data-stu-id="63b41-126">However, just because Visual Studio makes those steps automatic does not mean that you do not need to know what is going on underneath with Docker.</span></span> <span data-ttu-id="63b41-127">Поэтому далее в руководстве подробно описывается каждый шаг.</span><span class="sxs-lookup"><span data-stu-id="63b41-127">Therefore, in the guidance that follows, we detail every step.</span></span>

![](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a><span data-ttu-id="63b41-128">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="63b41-128">Step 1.</span></span> <span data-ttu-id="63b41-129">Начало программирования и создание первого приложения или базовой службы</span><span class="sxs-lookup"><span data-stu-id="63b41-129">Start coding and create your initial application or service baseline</span></span>

<span data-ttu-id="63b41-130">Разработка приложения Docker аналогична разработке приложения без Docker.</span><span class="sxs-lookup"><span data-stu-id="63b41-130">Developing a Docker application is similar to the way you develop an application without Docker.</span></span> <span data-ttu-id="63b41-131">Разница заключается в том, что при разработке для Docker развертывание и тестирование приложения или служб, работающих в контейнерах Docker, выполняется в локальной среде.</span><span class="sxs-lookup"><span data-stu-id="63b41-131">The difference is that while developing for Docker, you are deploying and testing your application or services running within Docker containers in your local environment.</span></span> <span data-ttu-id="63b41-132">Этот контейнер может быть контейнером Linux или контейнером Windows.</span><span class="sxs-lookup"><span data-stu-id="63b41-132">The container can be either a Linux container or a Windows container.</span></span>

### <a name="set-up-your-local-environment-with-visual-studio"></a><span data-ttu-id="63b41-133">Настройка локальной среды с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="63b41-133">Set up your local environment with Visual Studio</span></span>

<span data-ttu-id="63b41-134">Перед началом работы убедитесь, что [Docker Community Edition (CE)](https://www.docker.com/community-edition) для Windows установлен, как описано в следующих инструкциях:</span><span class="sxs-lookup"><span data-stu-id="63b41-134">To begin, make sure you have [Docker Community Edition (CE)](https://www.docker.com/community-edition) for Windows installed, as explained in the following instructions:</span></span>

[<span data-ttu-id="63b41-135">Начало работы с Docker CE для Windows</span><span class="sxs-lookup"><span data-stu-id="63b41-135">Get started with Docker CE for Windows</span></span>](https://docs.docker.com/docker-for-windows/)

<span data-ttu-id="63b41-136">Кроме того, потребуется установленный Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="63b41-136">In addition, you will need Visual Studio 2017 installed.</span></span> <span data-ttu-id="63b41-137">Вместо Visual Studio 2015 с надстройкой "Средства Visual Studio для Docker" рекомендуется использовать именно Visual Studio 2017, поскольку в нем реализована расширенная поддержка Docker, например, поддерживается отладка контейнеров.</span><span class="sxs-lookup"><span data-stu-id="63b41-137">This is preferred over Visual Studio 2015 with the Visual Studio Tools for Docker add-in, because Visual Studio 2017 has more advanced support for Docker, like support for debugging containers.</span></span> <span data-ttu-id="63b41-138">Visual Studio 2017 включает инструментарий для Docker, если при установке вы выбрали рабочую нагрузку **.NET Core и Docker**, как показано на рисунке 5-2.</span><span class="sxs-lookup"><span data-stu-id="63b41-138">Visual Studio 2017 includes the tooling for Docker if you selected the **.NET Core and Docker** workload during installation, as shown in Figure 5-2.</span></span>

![](./media/image3.png)

<span data-ttu-id="63b41-139">**Рис. 5-2**.</span><span class="sxs-lookup"><span data-stu-id="63b41-139">**Figure 5-2**.</span></span> <span data-ttu-id="63b41-140">Выбор рабочей нагрузки **.NET Core и Docker** при установке Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="63b41-140">Selecting the **.NET Core and Docker** workload during Visual Studio 2017 setup</span></span>

<span data-ttu-id="63b41-141">Можно приступать к программированию приложения в обычной среде .NET (как правило, в .NET Core, если вы планируете использовать контейнеры) даже до включения Docker в вашем приложении и развертывания и тестирования в Docker.</span><span class="sxs-lookup"><span data-stu-id="63b41-141">You can start coding your application in plain .NET (usually in .NET Core if you are planning to use containers) even before enabling Docker in your application and deploying and testing in Docker.</span></span> <span data-ttu-id="63b41-142">Тем не менее рекомендуется начать работу в Docker как можно быстрее, поскольку это будет реальная среда, и любые проблемы можно будет обнаружить гораздо раньше.</span><span class="sxs-lookup"><span data-stu-id="63b41-142">However, it is recommended that you start working on Docker as soon as possible, because that will be the real environment and any issues can be discovered as soon as possible.</span></span> <span data-ttu-id="63b41-143">Это также рекомендуется потому, что Visual Studio настолько упрощает работу с Docker, что практически все действия очевидны; лучший пример — отладка многоконтейнерного приложения в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="63b41-143">This is encouraged because Visual Studio makes it so easy to work with Docker that it almost feels transparent—the best example when debugging multi-container applications from Visual Studio.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="63b41-144">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="63b41-144">Additional resources</span></span>

-   <span data-ttu-id="63b41-145">**Начало работы с Docker CE для Windows**
    [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)</span><span class="sxs-lookup"><span data-stu-id="63b41-145">**Get started with Docker CE for Windows**
[*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)</span></span>

-   <span data-ttu-id="63b41-146">**Visual Studio 2017**
    [*https://www.visualstudio.com/downloads/*](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)</span><span class="sxs-lookup"><span data-stu-id="63b41-146">**Visual Studio 2017**
[*https://www.visualstudio.com/downloads/*](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)</span></span>

![](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a><span data-ttu-id="63b41-147">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="63b41-147">Step 2.</span></span> <span data-ttu-id="63b41-148">Создание файла Dockerfile, связанного с существующим базовым образом .NET</span><span class="sxs-lookup"><span data-stu-id="63b41-148">Create a Dockerfile related to an existing .NET base image</span></span>

<span data-ttu-id="63b41-149">Dockerfile необходим для каждого пользовательского образа, который вы хотите создать; кроме того, Dockerfile потребуется для каждого контейнера, который будет развертываться автоматически из Visual Studio или вручную с помощью Docker CLI (с помощью команд docker run и docker-compose).</span><span class="sxs-lookup"><span data-stu-id="63b41-149">You need a Dockerfile for each custom image you want to build; you also need a Dockerfile for each container to be deployed, whether you deploy automatically from Visual Studio or manually using the Docker CLI (docker run and docker-compose commands).</span></span> <span data-ttu-id="63b41-150">Если в приложении имеется единственный экземпляр пользовательской службы, необходим один Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="63b41-150">If your application contains a single custom service, you need a single Dockerfile.</span></span> <span data-ttu-id="63b41-151">Если в приложении имеется несколько служб (как в архитектуре на основе микрослужб), потребуется по одному Dockerfile для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="63b41-151">If your application contains multiple services (as in a microservices architecture), you need one Dockerfile for each service.</span></span>

<span data-ttu-id="63b41-152">Dockerfile размещается в корневой папке приложения или службы.</span><span class="sxs-lookup"><span data-stu-id="63b41-152">The Dockerfile is placed in the root folder of your application or service.</span></span> <span data-ttu-id="63b41-153">Он содержит команды, которые указывают Docker, как настраивать и запускать приложение или службу в контейнере.</span><span class="sxs-lookup"><span data-stu-id="63b41-153">It contains the commands that tell Docker how to set up and run your application or service in a container.</span></span> <span data-ttu-id="63b41-154">Можно вручную создать Dockerfile в коде и добавить его в проект вместе с зависимостями .NET.</span><span class="sxs-lookup"><span data-stu-id="63b41-154">You can manually create a Dockerfile in code and add it to your project along with your .NET dependencies.</span></span>

<span data-ttu-id="63b41-155">В Visual Studio со средствами для Docker эта задача выполняется лишь несколькими щелчками мыши.</span><span class="sxs-lookup"><span data-stu-id="63b41-155">With Visual Studio and its tools for Docker, this task requires only a few mouse clicks.</span></span> <span data-ttu-id="63b41-156">При создании нового проекта в Visual Studio 2017 можно выбрать параметр с именем **Enable Container (Docker) Support** (Включить поддержку контейнеров (Docker)), как показано на рисунке 5-3.</span><span class="sxs-lookup"><span data-stu-id="63b41-156">When you create a new project in Visual Studio 2017, there is an option named **Enable Container (Docker) Support**, as shown in Figure 5-3.</span></span>

![](./media/image5.png)

<span data-ttu-id="63b41-157">**Рис. 5-3**.</span><span class="sxs-lookup"><span data-stu-id="63b41-157">**Figure 5-3**.</span></span> <span data-ttu-id="63b41-158">Включение поддержки Docker при создании нового проекта в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="63b41-158">Enabling Docker Support when creating a new project in Visual Studio 2017</span></span>

<span data-ttu-id="63b41-159">Можно также включить поддержку Docker в новом или существующем проекте, щелкнув правой кнопкой мыши файл проекта в Visual Studio и выбрав в меню пункты **Add-Docker Project Support** (Добавить-Поддержка проекта Docker), как показано на рисунке 5-4.</span><span class="sxs-lookup"><span data-stu-id="63b41-159">You can also enable Docker support on a new or existing project by right-clicking your project file in Visual Studio and selecting the option **Add-Docker Project Support**, as shown in Figure 5-4.</span></span>

![](./media/image6.png)

<span data-ttu-id="63b41-160">**Рис. 5-4**.</span><span class="sxs-lookup"><span data-stu-id="63b41-160">**Figure 5-4**.</span></span> <span data-ttu-id="63b41-161">Включение поддержки Docker в существующем проекте Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="63b41-161">Enabling Docker support in an existing Visual Studio 2017 project</span></span>

<span data-ttu-id="63b41-162">Если выполнить это действие в проекте (например, в веб-приложении ASP.NET или в службе веб-API), то в проект будет добавлен Dockerfile с необходимой конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="63b41-162">This action on a project (like an ASP.NET Web application or Web API service) adds a Dockerfile to the project with the required configuration.</span></span> <span data-ttu-id="63b41-163">Кроме того, будет добавлен файл docker-compose.yml для всего решения.</span><span class="sxs-lookup"><span data-stu-id="63b41-163">It also adds a docker-compose.yml file for the whole solution.</span></span> <span data-ttu-id="63b41-164">В следующих разделах описывается информация, которая находится в каждом из этих файлов.</span><span class="sxs-lookup"><span data-stu-id="63b41-164">In the following sections, we describe the information that goes into each of those files.</span></span> <span data-ttu-id="63b41-165">Visual Studio может сделать это вместо вас, однако полезно разобраться, что входит в Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="63b41-165">Visual Studio can do this work for you, but it is useful to understand what goes into a Dockerfile.</span></span>

### <a name="option-a-creating-a-project-using-an-existing-official-net-docker-image"></a><span data-ttu-id="63b41-166">Вариант А. Создание проекта с помощью существующего официального образа .NET Docker</span><span class="sxs-lookup"><span data-stu-id="63b41-166">Option A: Creating a project using an existing official .NET Docker image</span></span>

<span data-ttu-id="63b41-167">Обычно вы создаете пользовательский образ для своего контейнера на основе базового образа, который можно получить из официального репозитория в реестре [Центра Docker](https://hub.docker.com/).</span><span class="sxs-lookup"><span data-stu-id="63b41-167">You usually build a custom image for your container on top of a base image you can get from an official repository at the [Docker Hub](https://hub.docker.com/) registry.</span></span> <span data-ttu-id="63b41-168">Именно это происходит на внутреннем уровне при включении поддержки Docker в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="63b41-168">That is precisely what happens under the covers when you enable Docker support in Visual Studio.</span></span> <span data-ttu-id="63b41-169">Ваш Dockerfile будет использовать существующий образ aspnetcore.</span><span class="sxs-lookup"><span data-stu-id="63b41-169">Your Dockerfile will use an existing aspnetcore image.</span></span>

<span data-ttu-id="63b41-170">Ранее было показано, какие образы и репозитории Docker можно использовать в зависимости от выбранной платформы и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="63b41-170">Earlier we explained which Docker images and repos you can use, depending on the framework and OS you have chosen.</span></span> <span data-ttu-id="63b41-171">Например, если вы выбрали ASP.NET Core (Windows или Linux), следует использовать образ microsoft/aspnetcore:2.0.</span><span class="sxs-lookup"><span data-stu-id="63b41-171">For instance, if you want to use ASP.NET Core (Linux or Windows), the image to use is microsoft/aspnetcore:2.0.</span></span> <span data-ttu-id="63b41-172">Таким образом, достаточно просто указать, какой базовый образ Docker будет использоваться для контейнера.</span><span class="sxs-lookup"><span data-stu-id="63b41-172">Therefore, you just need to specify what base Docker image you will use for your container.</span></span> <span data-ttu-id="63b41-173">Для этого добавьте в Dockerfile строку FROM microsoft/aspnetcore:2.0.</span><span class="sxs-lookup"><span data-stu-id="63b41-173">You do that by adding FROM microsoft/aspnetcore:2.0 to your Dockerfile.</span></span> <span data-ttu-id="63b41-174">Visual Studio выполнит это автоматически, но в случае обновления версии вы обновляете это значение.</span><span class="sxs-lookup"><span data-stu-id="63b41-174">This will be automatically performed by Visual Studio, but if you were to update the version, you update this value.</span></span>

<span data-ttu-id="63b41-175">Использование официального репозитория образов .NET из Центра Docker с номером версии гарантирует, что на всех компьютерах (включая компьютеры для разработки, тестирования и работы) будут доступны одни и те же функции языка.</span><span class="sxs-lookup"><span data-stu-id="63b41-175">Using an official .NET image repository from Docker Hub with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="63b41-176">Ниже приведен пример Dockerfile для контейнера ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="63b41-176">The following example shows a sample Dockerfile for an ASP.NET Core container.</span></span>

```Dockerfile
FROM microsoft/aspnetcore:2.0
  
ARG source
  
WORKDIR /app
  
EXPOSE 80
  
COPY ${source:-obj/Docker/publish} .
  
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

<span data-ttu-id="63b41-177">В этом случае контейнер основан на версии 2.0 официального образа Docker ASP.NET Core (мультиархитектурного для Linux и Windows).</span><span class="sxs-lookup"><span data-stu-id="63b41-177">In this case, the container is based on version 2.0 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows).</span></span> <span data-ttu-id="63b41-178">Это параметр `FROM microsoft/aspnetcore:2.0`.</span><span class="sxs-lookup"><span data-stu-id="63b41-178">This is the setting `FROM microsoft/aspnetcore:2.0`.</span></span> <span data-ttu-id="63b41-179">(Дополнительные сведения об этом базовом образе см. на страницах [Образ Docker ASP.NET Core](https://hub.docker.com/r/microsoft/aspnetcore/) и [Образ Docker .NET Core](https://hub.docker.com/r/microsoft/dotnet/).) Кроме того, в Dockerfile необходимо указать Docker прослушивать порт TCP, который будет использоваться во время выполнения (в данном случае это порт 80, как задано в параметре EXPOSE).</span><span class="sxs-lookup"><span data-stu-id="63b41-179">(For further details about this base image, see the [ASP.NET Core Docker Image](https://hub.docker.com/r/microsoft/aspnetcore/) page and the [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) page.) In the Dockerfile, you also need to instruct Docker to listen on the TCP port you will use at runtime (in this case, port 80, as configured with the EXPOSE setting).</span></span>

<span data-ttu-id="63b41-180">В Dockerfile можно задать дополнительные параметры конфигурации, в зависимости от используемого языка и платформы.</span><span class="sxs-lookup"><span data-stu-id="63b41-180">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you are using.</span></span> <span data-ttu-id="63b41-181">Например, параметр ENTRYPOINT со значением \["dotnet", "MySingleContainerWebApp.dll"\] указывает Docker запускать приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="63b41-181">For instance, the ENTRYPOINT line with \["dotnet", "MySingleContainerWebApp.dll"\] tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="63b41-182">Если для создания и запуска приложения .NET используется пакет SDK и .NET Core CLI (dotnet CLI), этот параметр будет другим.</span><span class="sxs-lookup"><span data-stu-id="63b41-182">If you are using the SDK and the .NET Core CLI (dotnet CLI) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="63b41-183">Параметр ENTRYPOINT, который находится в нижней строке, и другие параметры будут отличаться в зависимости от языка и платформы, выбранных для приложения.</span><span class="sxs-lookup"><span data-stu-id="63b41-183">The bottom line is that the ENTRYPOINT line and other settings will be different depending on the language and platform you choose for your application.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="63b41-184">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="63b41-184">Additional resources</span></span>

-   <span data-ttu-id="63b41-185">**Создание образов Docker для приложений .NET Core**
    [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](../../../core/docker/building-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="63b41-185">**Building Docker Images for .NET Core Applications**
[*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](../../../core/docker/building-net-docker-images.md)</span></span>

-   <span data-ttu-id="63b41-186">**Создание собственного образа**.</span><span class="sxs-lookup"><span data-stu-id="63b41-186">**Build your own image**.</span></span> <span data-ttu-id="63b41-187">В официальной документации Docker.</span><span class="sxs-lookup"><span data-stu-id="63b41-187">In the official Docker documentation.</span></span>
    [*https://docs.docker.com/engine/tutorials/dockerimages/*](https://docs.docker.com/engine/tutorials/dockerimages/)

### <a name="using-multi-arch-image-repositories"></a><span data-ttu-id="63b41-188">Использование мультиархитектурных репозиториев</span><span class="sxs-lookup"><span data-stu-id="63b41-188">Using multi-arch image repositories</span></span>

<span data-ttu-id="63b41-189">Один репозиторий может содержать варианты платформ, например образ Linux и образ Windows.</span><span class="sxs-lookup"><span data-stu-id="63b41-189">A single repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="63b41-190">Эта функция позволяет поставщикам, таким как Майкрософт, которые создают базовые образы, создать один репозиторий для охвата нескольких платформ (т. е. Windows и Linux).</span><span class="sxs-lookup"><span data-stu-id="63b41-190">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is Linux and Windows).</span></span> <span data-ttu-id="63b41-191">Например, репозиторий [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) в реестре Центра Docker обеспечивает поддержку Linux и Windows Nano Server при использовании одного и того же имени репозитория.</span><span class="sxs-lookup"><span data-stu-id="63b41-191">For example, the [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same repo name.</span></span>

<span data-ttu-id="63b41-192">Можно указать тег, явно задающий платформу, как в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="63b41-192">If you specify a tag, targeting a platform that is explicit like in the following cases:</span></span>

-   <span data-ttu-id="63b41-193">**microsoft/aspnetcore:2.0.0-jessie**</span><span class="sxs-lookup"><span data-stu-id="63b41-193">**microsoft/aspnetcore:2.0.0-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux 

-   <span data-ttu-id="63b41-194">**microsoft/aspnetcore:2.0.0-nanoserver**</span><span class="sxs-lookup"><span data-stu-id="63b41-194">**microsoft/aspnetcore:2.0.0-nanoserver**</span></span>

        .NET Core 2.0 runtime-only on Windows Nano Server

<span data-ttu-id="63b41-195">Однако в середине 2017 г. появилась возможность указывать одно и то же имя образа, даже с одинаковым тегом, и новые мультиархитектурные образы (например, образ aspnetcore, поддерживающий мультиархитектурность) будут использовать версию Windows или Linux в зависимости от развернутой базовой ОС Docker, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="63b41-195">But, and this is new since mid-2017, if you specify the same image name, even with the same tag, the new multi-arch images (like the aspnetcore image which supports multi-arch) will use the Linux or Windows version depending on the Docker host OS you are deploying, as shown in the following example:</span></span>

-   <span data-ttu-id="63b41-196">**microsoft/aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="63b41-196">**microsoft/aspnetcore:2.0**</span></span>

        Multi-arch: .NET Core 2.0 runtime-only on Linux or Windows Nano Server depending on the Docker host OS

<span data-ttu-id="63b41-197">Таким образом, при запросе образа с узла Windows будет получен вариант для Windows, а при запросе образа с тем же именем с узла Linux будет получен вариант для Linux.</span><span class="sxs-lookup"><span data-stu-id="63b41-197">This way, when you pull an image from a Windows host, it will pull the Windows variant, and pulling the same image name from a Linux host will pull the Linux variant.</span></span>

### <a name="option-b-creating-your-base-image-from-scratch"></a><span data-ttu-id="63b41-198">Вариант Б. Создание базового образа с нуля</span><span class="sxs-lookup"><span data-stu-id="63b41-198">Option B: Creating your base image from scratch</span></span>

<span data-ttu-id="63b41-199">Вы можете создать собственный базовый образ Docker с нуля.</span><span class="sxs-lookup"><span data-stu-id="63b41-199">You can create your own Docker base image from scratch.</span></span> <span data-ttu-id="63b41-200">Этот сценарий не рекомендуется для тех, кто только начинает работать с Docker, но если вы хотите задать определенные биты базового образа, это можно сделать.</span><span class="sxs-lookup"><span data-stu-id="63b41-200">This scenario is not recommended for someone who is starting with Docker, but if you want to set the specific bits of your own base image, you can do so.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="63b41-201">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="63b41-201">Additional resources</span></span>

-   <span data-ttu-id="63b41-202">**Мультиархитектурные образы .NET Core**.</span><span class="sxs-lookup"><span data-stu-id="63b41-202">**Multi-arch .NET Core images**.</span></span>
<span data-ttu-id="63b41-203">https://github.com/dotnet/announcements/issues/14</span><span class="sxs-lookup"><span data-stu-id="63b41-203">https://github.com/dotnet/announcements/issues/14</span></span> 
-   <span data-ttu-id="63b41-204">**Создание базового образа**.</span><span class="sxs-lookup"><span data-stu-id="63b41-204">**Create a base image**.</span></span> <span data-ttu-id="63b41-205">Официальная документация Docker.</span><span class="sxs-lookup"><span data-stu-id="63b41-205">Official Docker documentation.</span></span>
    [*https://docs.docker.com/engine/userguide/eng-image/baseimages/*](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a><span data-ttu-id="63b41-206">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="63b41-206">Step 3.</span></span> <span data-ttu-id="63b41-207">Создание пользовательских образов Docker и внедрение в них собственных приложений или служб</span><span class="sxs-lookup"><span data-stu-id="63b41-207">Create your custom Docker images and embed your application or service in them</span></span>

<span data-ttu-id="63b41-208">Для каждой службы в приложении необходимо создать связанный образ.</span><span class="sxs-lookup"><span data-stu-id="63b41-208">For each service in your application, you need to create a related image.</span></span> <span data-ttu-id="63b41-209">Если приложение состоит из одной службы или веб-приложения, достаточно одного образа.</span><span class="sxs-lookup"><span data-stu-id="63b41-209">If your application is made up of a single service or web application, you just need a single image.</span></span>

<span data-ttu-id="63b41-210">Обратите внимание, что образы Docker в Visual Studio создаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="63b41-210">Note that the Docker images are built automatically for you in Visual Studio.</span></span> <span data-ttu-id="63b41-211">Следующие действия потребуются только в рабочем процессе с использованием редактора/CLI и подробно описываются, чтобы показать, что происходит внутри.</span><span class="sxs-lookup"><span data-stu-id="63b41-211">The following steps are only needed for the editor/CLI workflow and explained for clarity about what happens underneath.</span></span>

<span data-ttu-id="63b41-212">Разработчик должен выполнять разработку и тестирование локально до тех пор, пока не завершит и отправит компонент или пока не перейдет в систему управления версиями (например, в GitHub).</span><span class="sxs-lookup"><span data-stu-id="63b41-212">You, as developer, need to develop and test locally until you push a completed feature or change to your source control system (for example, to GitHub).</span></span> <span data-ttu-id="63b41-213">Это означает, что необходимо создавать образы Docker и разворачивать контейнеры на локальном узле Docker (на виртуальной машине Windows или Linux), а затем выполнять запуск, тестирование и отладку этих локальных контейнеров.</span><span class="sxs-lookup"><span data-stu-id="63b41-213">This means that you need to create the Docker images and deploy containers to a local Docker host (Windows or Linux VM) and run, test, and debug against those local containers.</span></span>

<span data-ttu-id="63b41-214">Чтобы создать пользовательский образ в локальной среде с помощью Docker CLI и Dockerfile, можно использовать команду docker build, как показано на рисунке 5-5.</span><span class="sxs-lookup"><span data-stu-id="63b41-214">To create a custom image in your local environment by using Docker CLI and your Dockerfile, you can use the docker build command, as in Figure 5-5.</span></span>

![](./media/image8.png)

<span data-ttu-id="63b41-215">**Рис. 5-5**.</span><span class="sxs-lookup"><span data-stu-id="63b41-215">**Figure 5-5**.</span></span> <span data-ttu-id="63b41-216">Создание пользовательского образа Docker</span><span class="sxs-lookup"><span data-stu-id="63b41-216">Creating a custom Docker image</span></span>

<span data-ttu-id="63b41-217">При необходимости вместо непосредственного выполнения команды docker build из папки проекта можно сначала создать развертываемую папку с нужными библиотеками .NET и двоичными файлами, выполнив команду dotnet publish, а затем использовать команду docker build.</span><span class="sxs-lookup"><span data-stu-id="63b41-217">Optionally, instead of directly running docker build from the project folder, you can first generate a deployable folder with the required .NET libraries and binaries by running dotnet publish, and then use the docker build command.</span></span>

<span data-ttu-id="63b41-218">Так будет создан образ Docker с именем cesardl/netcore-webapi-microservice-docker:first.</span><span class="sxs-lookup"><span data-stu-id="63b41-218">This will create a Docker image with the name cesardl/netcore-webapi-microservice-docker:first.</span></span> <span data-ttu-id="63b41-219">В данном случае :first — это тег, представляющий конкретную версию.</span><span class="sxs-lookup"><span data-stu-id="63b41-219">In this case, :first is a tag representing a specific version.</span></span> <span data-ttu-id="63b41-220">Этот шаг можно повторить для каждого пользовательского образа, который вам требуется создать для своего составного приложения Docker.</span><span class="sxs-lookup"><span data-stu-id="63b41-220">You can repeat this step for each custom image you need to create for your composed Docker application.</span></span>

<span data-ttu-id="63b41-221">Если приложение состоит из нескольких контейнеров (т. е. это многоконтейнерное приложение), можно также использовать команду docker-compose up --build, чтобы собрать все связанные образы одной командой с помощью метаданных, представленных в связанном файле docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="63b41-221">When an application is made of multiple containers (that is, it is a multi-container application), you can also use the docker-compose up --build command to build all the related images with a single command by using the metadata exposed in the related docker-compose.yml files.</span></span>

<span data-ttu-id="63b41-222">Вы можете найти существующие в локальном репозитории образы с помощью команды docker images, как показано на рисунке 5-6.</span><span class="sxs-lookup"><span data-stu-id="63b41-222">You can find the existing images in your local repository by using the docker images command, as shown in Figure 5-6.</span></span>

![](./media/image9.png)

<span data-ttu-id="63b41-223">**Рис. 5-6**.</span><span class="sxs-lookup"><span data-stu-id="63b41-223">**Figure 5-6.**</span></span> <span data-ttu-id="63b41-224">Просмотр существующих образов с помощью команды docker images</span><span class="sxs-lookup"><span data-stu-id="63b41-224">Viewing existing images using the docker images command</span></span>

### <a name="creating-docker-images-with-visual-studio"></a><span data-ttu-id="63b41-225">Создание образов Docker с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="63b41-225">Creating Docker images with Visual Studio</span></span>

<span data-ttu-id="63b41-226">При использовании Visual Studio для создания проекта с поддержкой Docker не требуется создавать образ явно.</span><span class="sxs-lookup"><span data-stu-id="63b41-226">When you are using Visual Studio to create a project with Docker support, you do not explicitly create an image.</span></span> <span data-ttu-id="63b41-227">Этот образ создается автоматически, когда вы нажимаете клавишу F5 и запускаете приложение или службу, добавленную в Docker.</span><span class="sxs-lookup"><span data-stu-id="63b41-227">Instead, the image is created for you when you press F5 and run the dockerized application or service.</span></span> <span data-ttu-id="63b41-228">Этот шаг выполняется в Visual Studio автоматически, и вы не увидите, как это происходит, но важно знать, что происходит внутри.</span><span class="sxs-lookup"><span data-stu-id="63b41-228">This step is automatic in Visual Studio, and you will not see it happen, but it is important that you know what is going on underneath.</span></span>

![](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a><span data-ttu-id="63b41-229">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="63b41-229">Step 4.</span></span> <span data-ttu-id="63b41-230">Определение служб в файле docker-compose.yml при сборке многоконтейнерного приложения Docker</span><span class="sxs-lookup"><span data-stu-id="63b41-230">Define your services in docker-compose.yml when building a multi-container Docker application</span></span>

<span data-ttu-id="63b41-231">В файле [docker-compose.yml](https://docs.docker.com/compose/compose-file/) можно задать ряд связанных служб для развертывания в качестве составного приложения с помощью команд развертывания.</span><span class="sxs-lookup"><span data-stu-id="63b41-231">The [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file lets you define a set of related services to be deployed as a composed application with deployment commands.</span></span>

<span data-ttu-id="63b41-232">Чтобы использовать файл docker-compose.yml, его необходимо создать в основной или корневой папке решения, и его содержимое должно быть аналогично приведенному в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="63b41-232">To use a docker-compose.yml file, you need to create the file in your main or root solution folder, with content similar to that in the following example:</span></span>

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

<span data-ttu-id="63b41-233">Обратите внимание, что данный файл docker-compose.yml представляет собой упрощенную и объединенную версию.</span><span class="sxs-lookup"><span data-stu-id="63b41-233">Note that this docker-compose.yml file is a simplified and merged version.</span></span> <span data-ttu-id="63b41-234">Он содержит статические данные конфигурации для каждого контейнера (такие как имя пользовательского образа), которые применяются всегда, а также сведения о конфигурации, которые могут зависеть от среды развертывания, такие как строка подключения.</span><span class="sxs-lookup"><span data-stu-id="63b41-234">It contains static configuration data for each container (like the name of the custom image), which always applies, plus configuration information that might depend on the deployment environment, like the connection string.</span></span> <span data-ttu-id="63b41-235">В следующих разделах вы узнаете, как можно разбить конфигурацию в файле docker-compose.yml на несколько файлов docker-compose и переопределить значения в зависимости от среды и типа выполнения (отладка или выпуск).</span><span class="sxs-lookup"><span data-stu-id="63b41-235">In later sections, you will learn how you can split the docker-compose.yml configuration into multiple docker-compose files and override values depending on the environment and execution type (debug or release).</span></span>

<span data-ttu-id="63b41-236">В примере файла docker-compose.yml определяются четыре службы: служба webmvc (веб-приложение), две микрослужбы (catalog.api и ordering.api) и один контейнер источника данных, sql.data, на основе SQL Server для Linux, работающий как контейнер.</span><span class="sxs-lookup"><span data-stu-id="63b41-236">The docker-compose.yml file example defines five services: the webmvc service (a web application), two microservices (catalog.api and ordering.api), and one data source container, sql.data, based on SQL Server for Linux running as a container.</span></span> <span data-ttu-id="63b41-237">Каждая служба развертывается как контейнер, поэтому образ Docker требуется для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="63b41-237">Each service is deployed as a container, so a Docker image is required for each.</span></span>

<span data-ttu-id="63b41-238">Файл docker-compose.yml задает не только используемые контейнеры, но и их индивидуальные конфигурации.</span><span class="sxs-lookup"><span data-stu-id="63b41-238">The docker-compose.yml file specifies not only what containers are being used, but how they are individually configured.</span></span> <span data-ttu-id="63b41-239">Например, в определении контейнера webmvc в файле .yml задается следующее.</span><span class="sxs-lookup"><span data-stu-id="63b41-239">For instance, the webmvc container definition in the .yml file:</span></span>

-   <span data-ttu-id="63b41-240">Используется предварительно созданный образ eshop/web:latest.</span><span class="sxs-lookup"><span data-stu-id="63b41-240">Uses a pre-built eshop/web:latest image.</span></span> <span data-ttu-id="63b41-241">Однако вы также можете настроить сборку этого образа при выполнении команды docker-compose с дополнительной конфигурацией на основе раздела build: в файле docker-compose.</span><span class="sxs-lookup"><span data-stu-id="63b41-241">However, you could also configure the image to be built as part of the docker-compose execution with an additional configuration based on a build: section in the docker-compose file.</span></span>

-   <span data-ttu-id="63b41-242">Инициализируются две переменные среды (CatalogUrl и OrderingUrl).</span><span class="sxs-lookup"><span data-stu-id="63b41-242">Initializes two environment variables (CatalogUrl and OrderingUrl).</span></span>

-   <span data-ttu-id="63b41-243">Предоставленный порт 80 в контейнере переадресуется на внешний порт 80 на хост-компьютере.</span><span class="sxs-lookup"><span data-stu-id="63b41-243">Forwards the exposed port 80 on the container to the external port 80 on the host machine.</span></span>

-   <span data-ttu-id="63b41-244">Веб-приложение связывается со службами catalog и ordering с помощью параметра depends\_on.</span><span class="sxs-lookup"><span data-stu-id="63b41-244">Links the web app to the catalog and ordering service with the depends\_on setting.</span></span> <span data-ttu-id="63b41-245">В результате данная служба будет ожидать запуска этих служб.</span><span class="sxs-lookup"><span data-stu-id="63b41-245">This causes the service to wait until those services are started.</span></span>

<span data-ttu-id="63b41-246">Мы вернемся к файлу docker-compose.yml в следующем разделе, когда будем рассматривать реализацию микрослужб и многоконтейнерных приложений.</span><span class="sxs-lookup"><span data-stu-id="63b41-246">We will revisit the docker-compose.yml file in a later section when we cover how to implement microservices and multi-container apps.</span></span>

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a><span data-ttu-id="63b41-247">Работа с файлом docker-compose.yml в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="63b41-247">Working with docker-compose.yml in Visual Studio 2017</span></span>

<span data-ttu-id="63b41-248">Когда вы добавляете поддержку решения Docker в проект службы в решении Visual Studio, как показано на рисунке 5-7, Visual Studio добавляет в ваш проект Dockerfile, а также добавляет в ваше решение раздел служб (проект) с помощью файла docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="63b41-248">When you add Docker solution support to a service project in a Visual Studio solution, as shown in Figure 5-7, Visual Studio adds a Dockerfile to your project, and it adds a service section (project) in your solution with the docker-compose.yml files.</span></span> <span data-ttu-id="63b41-249">Это простой способ начать создание многоконтейнерного решения.</span><span class="sxs-lookup"><span data-stu-id="63b41-249">It is an easy way to start composing your multiple-container solution.</span></span> <span data-ttu-id="63b41-250">Затем можно открыть файлы docker-compose.yml и добавить в них дополнительные возможности.</span><span class="sxs-lookup"><span data-stu-id="63b41-250">You can then open the docker-compose.yml files and update them with additional features.</span></span>

![](./media/image6.png)

<span data-ttu-id="63b41-251">**Рис. 5-7**.</span><span class="sxs-lookup"><span data-stu-id="63b41-251">**Figure 5-7**.</span></span> <span data-ttu-id="63b41-252">Добавление поддержки Docker в Visual Studio 2017 щелчком правой кнопкой мыши на проекте ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="63b41-252">Adding Docker support in Visual Studio 2017 by right-clicking an ASP.NET Core project</span></span>

<span data-ttu-id="63b41-253">При добавлении поддержки Docker в Visual Studio помимо добавления в проект Dockerfile также добавляются сведения о конфигурации в несколько глобальных файлов docker-compose.yml, заданных на уровне решения.</span><span class="sxs-lookup"><span data-stu-id="63b41-253">Adding Docker support in Visual Studio not only adds the Dockerfile to your project, but adds the configuration information to several global docker-compose.yml files that are set at the solution level.</span></span>

<span data-ttu-id="63b41-254">После добавления поддержки Docker в решение в Visual Studio вы также увидите новый узел в обозревателе решений (в файле проекта docker-compose.dcproj), содержащий добавленные файлы docker-compose.yml, как показано на рисунке 5-8.</span><span class="sxs-lookup"><span data-stu-id="63b41-254">After you add Docker support to your solution in Visual Studio, you will also see a new node (in the docker-compose.dcproj project file) in Solution Explorer that contains the added docker-compose.yml files, as shown in Figure 5-8.</span></span>

![](./media/image11.PNG)

<span data-ttu-id="63b41-255">**Рис. 5-8**.</span><span class="sxs-lookup"><span data-stu-id="63b41-255">**Figure 5-8**.</span></span> <span data-ttu-id="63b41-256">Узел дерева **docker-compose**, добавленный в обозреватель решений Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="63b41-256">The **docker-compose** tree node added in Visual Studio 2017 Solution Explorer</span></span>

<span data-ttu-id="63b41-257">Можно было бы развернуть многоконтейнерное приложение с единственным файлом docker-compose.yml с помощью команды docker-compose up.</span><span class="sxs-lookup"><span data-stu-id="63b41-257">You could deploy a multi-container application with a single docker-compose.yml file by using the docker-compose up command.</span></span> <span data-ttu-id="63b41-258">Однако Visual Studio добавляет группу этих файлов, чтобы вы могли переопределять значения в зависимости от среды (разработки или рабочей) и типа выполнения (выпуска или отладки).</span><span class="sxs-lookup"><span data-stu-id="63b41-258">However, Visual Studio adds a group of them so you can override values depending on the environment (development versus production) and execution type (release versus debug).</span></span> <span data-ttu-id="63b41-259">Эта возможность разъясняется в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="63b41-259">This capability will be explained in later sections.</span></span>

![](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a><span data-ttu-id="63b41-260">Шаг 5.</span><span class="sxs-lookup"><span data-stu-id="63b41-260">Step 5.</span></span> <span data-ttu-id="63b41-261">Сборка и запуск приложения Docker</span><span class="sxs-lookup"><span data-stu-id="63b41-261">Build and run your Docker application</span></span>

<span data-ttu-id="63b41-262">Если в приложении имеется только один контейнер, его можно запустить путем развертывания на узле Docker (на виртуальной машине или физическом сервере).</span><span class="sxs-lookup"><span data-stu-id="63b41-262">If your application only has a single container, you can run it by deploying it to your Docker host (VM or physical server).</span></span> <span data-ttu-id="63b41-263">Но если приложение содержит несколько служб, его можно развернуть как составное приложение с помощью одной команды CLI (docker-compose up) или в Visual Studio, в котором внутри будет выполняться эта же команда.</span><span class="sxs-lookup"><span data-stu-id="63b41-263">However, if your application contains multiple services, you can deploy it as a composed application, either using a single CLI command (docker-compose up), or with Visual Studio, which will use that command under the covers.</span></span> <span data-ttu-id="63b41-264">Давайте рассмотрим разные варианты.</span><span class="sxs-lookup"><span data-stu-id="63b41-264">Let’s look at the different options.</span></span>

### <a name="option-a-running-a-single-container-with-docker-cli"></a><span data-ttu-id="63b41-265">Вариант А. Запуск единственного контейнера с помощью Docker CLI</span><span class="sxs-lookup"><span data-stu-id="63b41-265">Option A: Running a single-container with Docker CLI</span></span>

<span data-ttu-id="63b41-266">Контейнер Docker можно запустить с помощью команды docker run, как показано на рисунке 5-9.</span><span class="sxs-lookup"><span data-stu-id="63b41-266">You can run a Docker container using the docker run command, as in Figure 5-9:</span></span>

```console
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

![](./media/image13.png)

<span data-ttu-id="63b41-267">**Рис. 5-9**.</span><span class="sxs-lookup"><span data-stu-id="63b41-267">**Figure 5-9**.</span></span> <span data-ttu-id="63b41-268">Запуск контейнера Docker с помощью команды docker run</span><span class="sxs-lookup"><span data-stu-id="63b41-268">Running a Docker container using the docker run command</span></span>

<span data-ttu-id="63b41-269">В этом случае команда привязывает внутренний порт 5000 контейнера к порту 80 хост-компьютера.</span><span class="sxs-lookup"><span data-stu-id="63b41-269">In this case, the command binds the internal port 5000 of the container to port 80 of the host machine.</span></span> <span data-ttu-id="63b41-270">Это означает, что узел выполняет прослушивание порта 80 и переадресацию в порт 5000 в контейнере.</span><span class="sxs-lookup"><span data-stu-id="63b41-270">This means that the host is listening on port 80 and forwarding to port 5000 on the container.</span></span>

### <a name="option-b-running-a-multi-container-application"></a><span data-ttu-id="63b41-271">Вариант Б. Запуск многоконтейнерного приложения</span><span class="sxs-lookup"><span data-stu-id="63b41-271">Option B: Running a multi-container application</span></span>

<span data-ttu-id="63b41-272">В большинстве корпоративных сценариев приложение Docker будет состоять из нескольких служб; это означает, что необходимо запускать многоконтейнерное приложение, как показано на рисунке 5-10.</span><span class="sxs-lookup"><span data-stu-id="63b41-272">In most enterprise scenarios, a Docker application will be composed of multiple services, which means you need to run a multi-container application, as shown in Figure 5-10.</span></span>

![](./media/image14.png)

<span data-ttu-id="63b41-273">**Рис. 5-10**.</span><span class="sxs-lookup"><span data-stu-id="63b41-273">**Figure 5-10**.</span></span> <span data-ttu-id="63b41-274">Виртуальная машина с развернутыми контейнерами Docker</span><span class="sxs-lookup"><span data-stu-id="63b41-274">VM with Docker containers deployed</span></span>

#### <a name="running-a-multi-container-application-with-the-docker-cli"></a><span data-ttu-id="63b41-275">Запуск многоконтейнерного приложения с помощью Docker CLI</span><span class="sxs-lookup"><span data-stu-id="63b41-275">Running a multi-container application with the Docker CLI</span></span>

<span data-ttu-id="63b41-276">Чтобы запустить многоконтейнерное приложение с помощью Docker CLI, можно выполнить команду docker-compose up.</span><span class="sxs-lookup"><span data-stu-id="63b41-276">To run a multi-container application with the Docker CLI, you can run the docker-compose up command.</span></span> <span data-ttu-id="63b41-277">Эта команда разворачивает многоконтейнерное приложение с помощью файла docker-compose.yml, существующего на уровне решения.</span><span class="sxs-lookup"><span data-stu-id="63b41-277">This command uses the docker-compose.yml file that you have at the solution level to deploy a multi-container application.</span></span> <span data-ttu-id="63b41-278">На рисунке 5-11 показаны результаты выполнения этой команды из главного каталога проекта, в котором находится файл docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="63b41-278">Figure 5-11 shows the results when running the command from your main project directory, which contains the docker-compose.yml file.</span></span>

![](./media/image15.png)

<span data-ttu-id="63b41-279">**Рис. 5-11**.</span><span class="sxs-lookup"><span data-stu-id="63b41-279">**Figure 5-11**.</span></span> <span data-ttu-id="63b41-280">Пример результата выполнения команды docker-compose up</span><span class="sxs-lookup"><span data-stu-id="63b41-280">Example results when running the docker-compose up command</span></span>

<span data-ttu-id="63b41-281">После выполнения команды docker-compose up приложение и связанные с ним контейнеры развертываются в узле Docker, как показано в представлении виртуальной машины на рисунке 5-10.</span><span class="sxs-lookup"><span data-stu-id="63b41-281">After the docker-compose up command runs, the application and its related containers are deployed into your Docker host, as illustrated in the VM representation in Figure 5-10.</span></span>

#### <a name="running-and-debugging-a-multi-container-application-with-visual-studio"></a><span data-ttu-id="63b41-282">Запуск и отладка многоконтейнерного приложения с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="63b41-282">Running and debugging a multi-container application with Visual Studio</span></span> 

<span data-ttu-id="63b41-283">Запуск многоконтейнерного приложения с помощью Visual Studio 2017 не может быть проще.</span><span class="sxs-lookup"><span data-stu-id="63b41-283">Running a multi-container application using Visual Studio 2017 cannot get simpler.</span></span> <span data-ttu-id="63b41-284">Вы можете не только запускать многоконтейнерное приложение, но также и отлаживать все его контейнеры непосредственно в Visual Studio, установив обычные точки останова.</span><span class="sxs-lookup"><span data-stu-id="63b41-284">You can not only run the multi-container application, but you are able to debug all its containers directly from Visual Studio by setting regular breakpoints.</span></span>

<span data-ttu-id="63b41-285">Как упоминалось ранее, каждый раз при добавлении поддержки решения Docker в проект в решении этот проект настраивается в глобальном (на уровне решения) файле docker-compose.yml, что позволяет запускать или отлаживать все решение сразу.</span><span class="sxs-lookup"><span data-stu-id="63b41-285">As mentioned before, each time you add Docker solution support to a project within a solution, that project is configured in the global (solution-level) docker-compose.yml file, which lets you run or debug the whole solution at once.</span></span> <span data-ttu-id="63b41-286">Visual Studio будет запускать по одному контейнеру для каждого проекта с включенной поддержкой решения Docker и выполнять все внутренние шаги автоматически (dotnet publish, docker build и т. д.).</span><span class="sxs-lookup"><span data-stu-id="63b41-286">Visual Studio will start one container for each project that has Docker solution support enabled, and perform all the internal steps for you (dotnet publish, docker build, etc.).</span></span>

<span data-ttu-id="63b41-287">Здесь важно то, что, как показано на рисунке 5-12, в Visual Studio 2017 имеется дополнительная команда **Docker** для действия клавиши F5.</span><span class="sxs-lookup"><span data-stu-id="63b41-287">The important point here is that, as shown in Figure 5-12, in Visual Studio 2017 there is an additional **Docker** command for the F5 key action.</span></span> <span data-ttu-id="63b41-288">Эта возможность позволяет запускать или отлаживать многоконтейнерное приложение путем запуска всех контейнеров, определенных в файлах docker-compose.yml на уровне решения.</span><span class="sxs-lookup"><span data-stu-id="63b41-288">This option lets you run or debug a multi-container application by running all the containers that are defined in the docker-compose.yml files at the solution level.</span></span> <span data-ttu-id="63b41-289">Возможность отладки многоконтейнерных решений означает, что можно установить несколько точек останова, чтобы все они были в разных проектах (контейнерах), и во время отладки из Visual Studio вы будете останавливаться в точках останова, заданных в разных проектах, и работать в разных контейнерах.</span><span class="sxs-lookup"><span data-stu-id="63b41-289">The ability to debug multiple-container solutions means that you can set several breakpoints, each breakpoint in a different project (container), and while debugging from Visual Studio you will stop at breakpoints defined in different projects and running on different containers.</span></span>

![](./media/image16.png)

<span data-ttu-id="63b41-290">**Рис. 5-12**.</span><span class="sxs-lookup"><span data-stu-id="63b41-290">**Figure 5-12**.</span></span> <span data-ttu-id="63b41-291">Запуск многоконтейнерных приложений в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="63b41-291">Running multi-container apps in Visual Studio 2017</span></span>

### <a name="additional-resources"></a><span data-ttu-id="63b41-292">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="63b41-292">Additional resources</span></span>

-   <span data-ttu-id="63b41-293">**Развертывание контейнера ASP.NET на удаленном узле Docker**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="63b41-293">**Deploy an ASP.NET container to a remote Docker host**
[*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a><span data-ttu-id="63b41-294">Примечание о тестировании и развертывании с использованием оркестраторов</span><span class="sxs-lookup"><span data-stu-id="63b41-294">A note about testing and deploying with orchestrators</span></span>

<span data-ttu-id="63b41-295">Команды docker-compose up и docker run (или запуск и отладка контейнеров в Visual Studio) подходят для тестирования контейнеров в вашей среде разработки.</span><span class="sxs-lookup"><span data-stu-id="63b41-295">The docker-compose up and docker run commands (or running and debugging the containers in Visual Studio) are adequate for testing containers in your development environment.</span></span> <span data-ttu-id="63b41-296">Однако этот способ не подходит, если вы планируете использовать оркестраторы и кластеры Docker, такие как Docker Swarm, Mesosphere DC/OS и Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="63b41-296">But you should not use this approach if you are targeting Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes.</span></span> <span data-ttu-id="63b41-297">Если вы используете кластер, например [режим Docker Swarm](https://docs.docker.com/engine/swarm/) (доступный в Docker CE для Windows и Mac, начиная с версии 1.12), необходимо выполнять развертывание и тестирование единственных служб с помощью дополнительных команд, таких как [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/).</span><span class="sxs-lookup"><span data-stu-id="63b41-297">If you are using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker CE for Windows and Mac since version 1.12), you need to deploy and test with additional commands like [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/) for single services.</span></span> <span data-ttu-id="63b41-298">При развертывании приложения, состоящего из нескольких контейнеров, следует использовать команды [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) и [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/), чтобы развернуть составное приложение как *стек*.</span><span class="sxs-lookup"><span data-stu-id="63b41-298">If you are deploying an application composed of several containers, you use [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) and [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) to deploy the composed application as a *stack*.</span></span> <span data-ttu-id="63b41-299">Дополнительные сведения см. в записи блога [Introducing Experimental Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) (Общие сведения об экспериментальных пакетах распределенных приложений) в документации Docker</span><span class="sxs-lookup"><span data-stu-id="63b41-299">For more information, see the blog post [Introducing Experimental Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) in the Docker documentation.</span></span> <span data-ttu-id="63b41-300">на сайте Docker.</span><span class="sxs-lookup"><span data-stu-id="63b41-300">on the Docker site.</span></span>

<span data-ttu-id="63b41-301">Для [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) и [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/) вы также должны использовать другие скрипты и команды развертывания.</span><span class="sxs-lookup"><span data-stu-id="63b41-301">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/) you would use different deployment commands and scripts as well.</span></span>

![](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a><span data-ttu-id="63b41-302">Шаг 6.</span><span class="sxs-lookup"><span data-stu-id="63b41-302">Step 6.</span></span> <span data-ttu-id="63b41-303">Тестирование приложения Docker с помощью локального узла Docker</span><span class="sxs-lookup"><span data-stu-id="63b41-303">Test your Docker application using your local Docker host</span></span>

<span data-ttu-id="63b41-304">Этот шаг будет зависеть от того, что делает ваше приложение.</span><span class="sxs-lookup"><span data-stu-id="63b41-304">This step will vary depending on what your application is doing.</span></span> <span data-ttu-id="63b41-305">В случае простого веб-приложения .NET Core, развернутого в виде единственного контейнера или службы, можно получить доступ к этой службе, открыв на узле Docker браузер и перейдя в нем на этот сайт, как показано на рисунке 5-13.</span><span class="sxs-lookup"><span data-stu-id="63b41-305">In a simple .NET Core Web application that is deployed as a single container or service, you can access the service by opening a browser on the Docker host and navigating to that site as shown in Figure 5-13.</span></span> <span data-ttu-id="63b41-306">(Если конфигурация в Dockerfile сопоставляет контейнер с портом узла, отличным от 80, укажите этот порт узла в URL-адресе.)</span><span class="sxs-lookup"><span data-stu-id="63b41-306">(If the configuration in the Dockerfile maps the container to a port on the host that is anything other than 80, include the host port in the URL.)</span></span>

![](./media/image18.png)

<span data-ttu-id="63b41-307">**Рис. 5-13**.</span><span class="sxs-lookup"><span data-stu-id="63b41-307">**Figure 5-13**.</span></span> <span data-ttu-id="63b41-308">Пример локального тестирования приложения Docker с помощью localhost</span><span class="sxs-lookup"><span data-stu-id="63b41-308">Example of testing your Docker application locally using localhost</span></span>

<span data-ttu-id="63b41-309">Если localhost не указывает на IP-адрес узла Docker (при использовании Docker CE это должно происходить по умолчанию), то для перехода к службе используйте IP-адрес сетевой карты вашего компьютера.</span><span class="sxs-lookup"><span data-stu-id="63b41-309">If localhost is not pointing to the Docker host IP (by default, when using Docker CE, it should), to navigate to your service, use the IP address of your machine’s network card.</span></span>

<span data-ttu-id="63b41-310">Обратите внимание, что этот URL-адрес в браузере использует порт 80 для рассматриваемого примера конкретного контейнера.</span><span class="sxs-lookup"><span data-stu-id="63b41-310">Note that this URL in the browser uses port 80 for the particular container example being discussed.</span></span> <span data-ttu-id="63b41-311">Однако внутренние запросы перенаправляются на порт 5000, поскольку именно так было выполнено развертывание с помощью команды docker run, как описано в предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="63b41-311">However, internally the requests are being redirected to port 5000, because that was how it was deployed with the docker run command, as explained in a previous step.</span></span>

<span data-ttu-id="63b41-312">Вы также можете тестировать приложение с помощью команды curl с терминала, как показано на рисунке 5-14.</span><span class="sxs-lookup"><span data-stu-id="63b41-312">You can also test the application using curl from the terminal, as shown in Figure 5-14.</span></span> <span data-ttu-id="63b41-313">В случае установки Docker в Windows по умолчанию всегда будет использоваться IP-адрес узла Docker 10.0.75.1 помимо фактического IP-адреса вашего компьютера.</span><span class="sxs-lookup"><span data-stu-id="63b41-313">In a Docker installation on Windows, the default Docker Host IP is always 10.0.75.1 in addition to your machine’s actual IP address.</span></span>

![](./media/image19.png)

<span data-ttu-id="63b41-314">**Рис. 5-14**.</span><span class="sxs-lookup"><span data-stu-id="63b41-314">**Figure 5-14**.</span></span> <span data-ttu-id="63b41-315">Пример локального тестирования приложения Docker с помощью curl</span><span class="sxs-lookup"><span data-stu-id="63b41-315">Example of testing your Docker application locally using curl</span></span>

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a><span data-ttu-id="63b41-316">Тестирование и отладка контейнеров в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="63b41-316">Testing and debugging containers with Visual Studio 2017</span></span>

<span data-ttu-id="63b41-317">При запуске и отладке контейнеров в Visual Studio 2017 вы можете отлаживать приложения .NET в основном так же, как при запуске без контейнеров.</span><span class="sxs-lookup"><span data-stu-id="63b41-317">When running and debugging the containers with Visual Studio 2017, you can debug the .NET application in much the same way as you would when running without containers.</span></span>

### <a name="testing-and-debugging-without-visual-studio"></a><span data-ttu-id="63b41-318">Тестирование и отладка без Visual Studio</span><span class="sxs-lookup"><span data-stu-id="63b41-318">Testing and debugging without Visual Studio</span></span>

<span data-ttu-id="63b41-319">Если при разработке используется редактор или CLI, отлаживать контейнеры будет значительно труднее, и вы захотите выполнять отладку путем создания трассировок.</span><span class="sxs-lookup"><span data-stu-id="63b41-319">If you are developing using the editor/CLI approach, debugging containers is more difficult and you will want to debug by generating traces.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="63b41-320">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="63b41-320">Additional resources</span></span>

-   <span data-ttu-id="63b41-321">**Отладка приложений в локальном контейнере Docker**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="63b41-321">**Debugging apps in a local Docker container**
[*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

-   <span data-ttu-id="63b41-322">**Стив Ласкер (Steve Lasker). Сборка, отладка, развертывание приложений ASP.NET Core с помощью Docker.**</span><span class="sxs-lookup"><span data-stu-id="63b41-322">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker.**</span></span> <span data-ttu-id="63b41-323">Видео.</span><span class="sxs-lookup"><span data-stu-id="63b41-323">Video.</span></span>
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a><span data-ttu-id="63b41-324">Упрощенный рабочий процесс при разработке контейнеров в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="63b41-324">Simplified workflow when developing containers with Visual Studio</span></span>

<span data-ttu-id="63b41-325">В сущности, при использовании Visual Studio рабочий процесс гораздо проще, чем при использовании редактора или CLI.</span><span class="sxs-lookup"><span data-stu-id="63b41-325">Effectively, the workflow when using Visual Studio is a lot simpler than if you use the editor/CLI approach.</span></span> <span data-ttu-id="63b41-326">Большинство шагов, необходимых для Docker и связанных с Dockerfile и docker-compose.yml, выполняются скрыто от пользователя или значительно упрощаются благодаря Visual Studio, как показано на рисунке 5-15.</span><span class="sxs-lookup"><span data-stu-id="63b41-326">Most of the steps required by Docker related to the Dockerfile and docker-compose.yml files are hidden or simplified by Visual Studio, as shown in Figure 5-15.</span></span>

![](./media/image20.png)

<span data-ttu-id="63b41-327">**Рис. 5-15**.</span><span class="sxs-lookup"><span data-stu-id="63b41-327">**Figure 5-15**.</span></span> <span data-ttu-id="63b41-328">Упрощенный рабочий процесс при разработке в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="63b41-328">Simplified workflow when developing with Visual Studio</span></span>

<span data-ttu-id="63b41-329">Кроме того, вам достаточно будет выполнить шаг 2 (добавление поддержки Docker в проекты) только один раз.</span><span class="sxs-lookup"><span data-stu-id="63b41-329">In addition, you need to perform step 2 (adding Docker support to your projects) just once.</span></span> <span data-ttu-id="63b41-330">Таким образом, рабочий процесс аналогичен другим обычным задачам разработки, когда для разработки используется .NET.</span><span class="sxs-lookup"><span data-stu-id="63b41-330">Therefore, the workflow is similar to your usual development tasks when using .NET for any other development.</span></span> <span data-ttu-id="63b41-331">Вам нужно знать, что происходит на самом деле (процесс создания образа, какие базовые образы используются, развертывание контейнеров и т. п.), и в некоторых случаях также может потребоваться изменить файл Dockerfile или docker-compose.yml, чтобы настроить функциональность.</span><span class="sxs-lookup"><span data-stu-id="63b41-331">You need to know what is going on under the covers (the image build process, what base images you are using, deployment of containers, etc.) and sometimes you will also need to edit the Dockerfile or docker-compose.yml file to customize behaviors.</span></span> <span data-ttu-id="63b41-332">Но благодаря Visual Studio большую часть работы можно выполнить гораздо проще, что существенно повышает эффективность работы.</span><span class="sxs-lookup"><span data-stu-id="63b41-332">But most of the work is greatly simplified by using Visual Studio, making you a lot more productive.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="63b41-333">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="63b41-333">Additional resources</span></span>

-   <span data-ttu-id="63b41-334">**Стив Ласкер (Steve Lasker). Разработка .NET Docker в Visual Studio 2017**
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)</span><span class="sxs-lookup"><span data-stu-id="63b41-334">**Steve Lasker. .NET Docker Development with Visual Studio 2017**
[*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)</span></span>

-   <span data-ttu-id="63b41-335">**Джеффри Т. Фриц (Jeffrey T. Fritz). Помещение приложения .NET Core в контейнер с помощью новых инструментов Docker для Visual Studio**
    [*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)</span><span class="sxs-lookup"><span data-stu-id="63b41-335">**Jeffrey T. Fritz. Put a .NET Core App in a Container with the new Docker Tools for Visual Studio**
[*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)</span></span>

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a><span data-ttu-id="63b41-336">Использование команд PowerShell в DockerFile для настройки контейнеров Windows</span><span class="sxs-lookup"><span data-stu-id="63b41-336">Using PowerShell commands in a Dockerfile to set up Windows Containers</span></span> 

<span data-ttu-id="63b41-337">[Контейнеры Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) позволяют преобразовывать существующие приложения Windows в образы Docker и развертывать их с помощью тех же средств, что и остальную часть экосистемы Docker.</span><span class="sxs-lookup"><span data-stu-id="63b41-337">[Windows Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) allow you to convert your existing Windows applications into Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span> <span data-ttu-id="63b41-338">Чтобы использовать контейнеры Windows, выполните команды PowerShell в Dockerfile, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="63b41-338">To use Windows Containers, you run PowerShell commands in the Dockerfile, as shown in the following example:</span></span>

```Dockerfile
FROM microsoft/windowsservercore
  
LABEL Description="IIS" Vendor="Microsoft" Version="10"
  
RUN powershell -Command Add-WindowsFeature Web-Server
  
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="63b41-339">В этом случае мы используем базовый образ Windows Server Core (параметр FROM) и устанавливаем службы IIS с помощью команды PowerShell (параметр RUN).</span><span class="sxs-lookup"><span data-stu-id="63b41-339">In this case, we are using a Windows Server Core base image (the FROM setting) and installing IIS with a PowerShell command (the RUN setting).</span></span> <span data-ttu-id="63b41-340">Аналогичным образом можно также использовать команды PowerShell для настройки дополнительных компонентов, таких как ASP.NET 4.x, .NET 4.6 и другого программного обеспечения Windows.</span><span class="sxs-lookup"><span data-stu-id="63b41-340">In a similar way, you could also use PowerShell commands to set up additional components like ASP.NET 4.x, .NET 4.6, or any other Windows software.</span></span> <span data-ttu-id="63b41-341">Например, следующая команда в Dockerfile настраивает ASP.NET 4.5:</span><span class="sxs-lookup"><span data-stu-id="63b41-341">For example, the following command in a Dockerfile sets up ASP.NET 4.5:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a><span data-ttu-id="63b41-342">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="63b41-342">Additional resources</span></span>

-   <span data-ttu-id="63b41-343">**aspnet-docker/Dockerfile.**</span><span class="sxs-lookup"><span data-stu-id="63b41-343">**aspnet-docker/Dockerfile.**</span></span> <span data-ttu-id="63b41-344">Примеры команд Powershell, которые можно выполнять в файлах Dockerfile для включения компонентов Windows.</span><span class="sxs-lookup"><span data-stu-id="63b41-344">Example Powershell commands to run from dockerfiles to include Windows features.</span></span>
    [*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*](https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile)

>[!div class="step-by-step"]
<span data-ttu-id="63b41-345">[Назад] (index.md) [Далее] (../net-core-single-containers-linux-windows-server-hosts/index.md)</span><span class="sxs-lookup"><span data-stu-id="63b41-345">[Previous] (index.md) [Next] (../net-core-single-containers-linux-windows-server-hosts/index.md)</span></span>
