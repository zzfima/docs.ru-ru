---
title: Рабочий процесс разработки для приложений Docker
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Рабочий процесс разработки для приложений Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/05/2018
ms.openlocfilehash: bc6b1796ed7b12a04affc521ac2efee515c48ae2
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53150554"
---
# <a name="development-workflow-for-docker-apps"></a><span data-ttu-id="ce6ea-103">Рабочий процесс разработки для приложений Docker</span><span class="sxs-lookup"><span data-stu-id="ce6ea-103">Development workflow for Docker apps</span></span>

<span data-ttu-id="ce6ea-104">Жизненный цикл разработки приложений начинается на компьютере каждого разработчика, где разработчик локально программирует приложение на предпочитаемом языке и тестирует его.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-104">The application development life cycle starts at each developer’s machine, where the developer codes the application using their preferred language and tests it locally.</span></span> <span data-ttu-id="ce6ea-105">Независимо от выбранного языка, инфраструктуры и платформы, в рамках этого рабочего процесса разработчик всегда разрабатывает и тестирует контейнеры Docker, но делает это локально.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-105">No matter which language, framework, and platform the developer chooses, with this workflow, the developer is always developing and testing Docker containers, but doing so locally.</span></span>

<span data-ttu-id="ce6ea-106">В каждый контейнер (экземпляр образа Docker) входят следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="ce6ea-106">Each container (an instance of a Docker image) includes the following components:</span></span>

- <span data-ttu-id="ce6ea-107">Выбранная операционная система (например, дистрибутив Linux, Windows Nano Server или Windows Server Core).</span><span class="sxs-lookup"><span data-stu-id="ce6ea-107">An operating system selection (for example, a Linux distribution, Windows Nano Server, or Windows Server Core).</span></span>

- <span data-ttu-id="ce6ea-108">Файлы, добавленные разработчиком (двоичные файлы приложения и т. п.).</span><span class="sxs-lookup"><span data-stu-id="ce6ea-108">Files added by the developer (application binaries, etc.).</span></span>

- <span data-ttu-id="ce6ea-109">Сведения о конфигурации (параметры среды и зависимости).</span><span class="sxs-lookup"><span data-stu-id="ce6ea-109">Configuration information (environment settings and dependencies).</span></span>

## <a name="workflow-for-developing-docker-container-based-applications"></a><span data-ttu-id="ce6ea-110">Рабочий процесс разработки приложений Docker на основе контейнера</span><span class="sxs-lookup"><span data-stu-id="ce6ea-110">Workflow for developing Docker container-based applications</span></span>

<span data-ttu-id="ce6ea-111">В этом разделе описывается рабочий процесс *внутреннего цикла* разработки приложений на основе контейнера Docker.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-111">This section describes the *inner-loop* development workflow for Docker container-based applications.</span></span> <span data-ttu-id="ce6ea-112">Рабочий процесс внутреннего цикла означает, что речь идет только о разработке, которая выполняется на компьютере разработчика, не касаясь более широкого рабочего процесса DevOps.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-112">The inner-loop workflow means it is not taking into account the broader DevOps workflow and just focuses on the development work done on the developer’s computer.</span></span> <span data-ttu-id="ce6ea-113">Начальные этапы настройки среды здесь не рассматриваются, так как они выполняются только один раз.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-113">The initial steps to set up the environment are not included, since those are done only once.</span></span>

<span data-ttu-id="ce6ea-114">Приложение состоит из ваших собственных служб и дополнительных библиотек (зависимостей).</span><span class="sxs-lookup"><span data-stu-id="ce6ea-114">An application is composed of your own services plus additional libraries (dependencies).</span></span> <span data-ttu-id="ce6ea-115">Ниже приведены основные шаги, которые обычно выполняются при сборке приложения Docker, как показано на рисунке 5-1.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-115">The following are the basic steps you usually take when building a Docker application, as illustrated in Figure 5-1.</span></span>

![Рис. "Пошаговый рабочий процесс разработки графики приложения на основе контейнеров Docker"](./media/image1.png)

<span data-ttu-id="ce6ea-117">**Рис. 5-1**.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-117">**Figure 5-1.**</span></span> <span data-ttu-id="ce6ea-118">Пошаговый рабочий процесс разработки приложения на основе контейнера Docker</span><span class="sxs-lookup"><span data-stu-id="ce6ea-118">Step-by-step workflow for developing Docker containerized apps</span></span>

<span data-ttu-id="ce6ea-119">В этом руководстве подробно описывается весь процесс, и каждый важный шаг объясняется с акцентом на среду Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-119">In this guide, this whole process is detailed and every major step is explained by focusing on a Visual Studio environment.</span></span>

<span data-ttu-id="ce6ea-120">Если разработка выполняется с помощью редактора и CLI (например, Visual Studio Code и Docker CLI на macOS или Windows), то необходимо знать каждый шаг и обычно более детально, чем при использовании Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-120">When you are using an editor/CLI development approach (for example, Visual Studio Code plus Docker CLI on macOS or Windows), you need to know every step, generally in more detail than if you are using Visual Studio.</span></span> <span data-ttu-id="ce6ea-121">Дополнительные сведения о работе в среде CLI см. в электронной книге [Жизненный цикл приложений в контейнерах Docker с платформами и средствами Майкрософт](https://aka.ms/dockerlifecycleebook/).</span><span class="sxs-lookup"><span data-stu-id="ce6ea-121">For more information about working in a CLI environment, see the e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/).</span></span>

<span data-ttu-id="ce6ea-122">При использовании Visual Studio многие из этих шагов выполняются автоматически, что значительно повышает производительность.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-122">When you're using Visual Studio, many of those steps are handled for you, which dramatically improves your productivity.</span></span> <span data-ttu-id="ce6ea-123">Это особенно справедливо в тех случаях, когда используется Visual Studio 2017 и планируется создание многоконтейнерных приложений.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-123">This is especially true when you are using Visual Studio 2017 and targeting multi-container applications.</span></span> <span data-ttu-id="ce6ea-124">Например, всего лишь одним щелчком мыши Visual Studio добавляет в проект *Dockerfile* и файл *docker-compose.yml* с конфигурацией для вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-124">For instance, with just one mouse click, Visual Studio adds the *Dockerfile* and *docker-compose.yml* files to your projects with the configuration for your application.</span></span> <span data-ttu-id="ce6ea-125">При запуске приложения в Visual Studio он создает образ Docker и запускает многоконтейнерное приложение непосредственно в Docker.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-125">When you run the application in Visual Studio, it builds the Docker image and runs the multi-container application directly in Docker.</span></span> <span data-ttu-id="ce6ea-126">Вы даже можете отлаживать несколько контейнеров одновременно.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-126">It even allows you to debug several containers at once.</span></span> <span data-ttu-id="ce6ea-127">Эти возможности значительно повышают скорость разработки.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-127">These features boost your development speed.</span></span>

<span data-ttu-id="ce6ea-128">В этом руководстве мы расскажем, что происходит "за кулисами" в Docker.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-128">In the guidance that follows, we explain what's happening "under the covers" with Docker.</span></span>

![Рис. "Шаг 1. Создание кода приложения"](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a><span data-ttu-id="ce6ea-130">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-130">Step 1.</span></span> <span data-ttu-id="ce6ea-131">Начало программирования и создание первого приложения или базовой службы</span><span class="sxs-lookup"><span data-stu-id="ce6ea-131">Start coding and create your initial application or service baseline</span></span>

<span data-ttu-id="ce6ea-132">Разработка приложения Docker аналогична разработке приложения без Docker.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-132">Developing a Docker application is similar to the way you develop an application without Docker.</span></span> <span data-ttu-id="ce6ea-133">Разница заключается в том, что при разработке для Docker развертывание и тестирование приложения или служб, работающих в контейнерах Docker, выполняется в локальной среде.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-133">The difference is that while developing for Docker, you are deploying and testing your application or services running within Docker containers in your local environment.</span></span> <span data-ttu-id="ce6ea-134">Этот контейнер может быть контейнером Linux или контейнером Windows.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-134">The container can be either a Linux container or a Windows container.</span></span>

### <a name="set-up-your-local-environment-with-visual-studio"></a><span data-ttu-id="ce6ea-135">Настройка локальной среды с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ce6ea-135">Set up your local environment with Visual Studio</span></span>

<span data-ttu-id="ce6ea-136">Перед началом работы убедитесь, что [Docker Community Edition (CE)](https://www.docker.com/community-edition) для Windows установлен, как описано в следующих инструкциях:</span><span class="sxs-lookup"><span data-stu-id="ce6ea-136">To begin, make sure you have [Docker Community Edition (CE)](https://www.docker.com/community-edition) for Windows installed, as explained in the following instructions:</span></span>

[<span data-ttu-id="ce6ea-137">Начало работы с Docker CE для Windows</span><span class="sxs-lookup"><span data-stu-id="ce6ea-137">Get started with Docker CE for Windows</span></span>](https://docs.docker.com/docker-for-windows/)

<span data-ttu-id="ce6ea-138">Кроме того, вам нужна Visual Studio 2017 с установленной рабочей нагрузкой **Кроссплатформенная разработка .NET Core**, как показано на рис. 5-2.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-138">In addition, you need Visual Studio 2017 with the **.NET Core cross-platform development** workload installed, as shown in Figure 5-2.</span></span>

![](./media/image3.png)

<span data-ttu-id="ce6ea-139">**Рис. 5-2**.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-139">**Figure 5-2**.</span></span> <span data-ttu-id="ce6ea-140">Выбор рабочей нагрузки **.NET Core и Docker** при установке Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="ce6ea-140">Selecting the **.NET Core and Docker** workload during Visual Studio 2017 setup</span></span>

<span data-ttu-id="ce6ea-141">Можно приступать к программированию приложения в обычной среде .NET (как правило, в .NET Core, если вы планируете использовать контейнеры) даже до включения Docker в вашем приложении и развертывания и тестирования в Docker.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-141">You can start coding your application in plain .NET (usually in .NET Core if you are planning to use containers) even before enabling Docker in your application and deploying and testing in Docker.</span></span> <span data-ttu-id="ce6ea-142">Тем не менее рекомендуется начать работу в Docker как можно быстрее, поскольку это будет реальная среда, и любые проблемы можно будет обнаружить гораздо раньше.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-142">However, it is recommended that you start working on Docker as soon as possible, because that will be the real environment and any issues can be discovered as soon as possible.</span></span> <span data-ttu-id="ce6ea-143">Это также рекомендуется потому, что Visual Studio настолько упрощает работу с Docker, что практически все действия очевидны; лучший пример — отладка многоконтейнерного приложения в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-143">This is encouraged because Visual Studio makes it so easy to work with Docker that it almost feels transparent — the best example when debugging multi-container applications from Visual Studio.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ce6ea-144">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ce6ea-144">Additional resources</span></span>

- <span data-ttu-id="ce6ea-145">**Начало работы с Docker CE для Windows**</span><span class="sxs-lookup"><span data-stu-id="ce6ea-145">**Get started with Docker CE for Windows**</span></span>

   [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)

- <span data-ttu-id="ce6ea-146">**Visual Studio 2017**</span><span class="sxs-lookup"><span data-stu-id="ce6ea-146">**Visual Studio 2017**</span></span>

   [*https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs*](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

![Рис. "Шаг 2. Запись файлов Dockerfile"](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a><span data-ttu-id="ce6ea-148">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-148">Step 2.</span></span> <span data-ttu-id="ce6ea-149">Создание файла Dockerfile, связанного с существующим базовым образом .NET</span><span class="sxs-lookup"><span data-stu-id="ce6ea-149">Create a Dockerfile related to an existing .NET base image</span></span>

<span data-ttu-id="ce6ea-150">Dockerfile необходим для каждого пользовательского образа, который вы хотите создать; кроме того, Dockerfile потребуется для каждого контейнера, который будет развертываться автоматически из Visual Studio или вручную с помощью Docker CLI (с помощью команд docker run и docker-compose).</span><span class="sxs-lookup"><span data-stu-id="ce6ea-150">You need a Dockerfile for each custom image you want to build; you also need a Dockerfile for each container to be deployed, whether you deploy automatically from Visual Studio or manually using the Docker CLI (docker run and docker-compose commands).</span></span> <span data-ttu-id="ce6ea-151">Если в приложении имеется единственный экземпляр пользовательской службы, необходим один Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-151">If your application contains a single custom service, you need a single Dockerfile.</span></span> <span data-ttu-id="ce6ea-152">Если в приложении имеется несколько служб (как в архитектуре на основе микрослужб), потребуется по одному Dockerfile для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-152">If your application contains multiple services (as in a microservices architecture), you need one Dockerfile for each service.</span></span>

<span data-ttu-id="ce6ea-153">Dockerfile размещается в корневой папке приложения или службы.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-153">The Dockerfile is placed in the root folder of your application or service.</span></span> <span data-ttu-id="ce6ea-154">Он содержит команды, которые указывают Docker, как настраивать и запускать приложение или службу в контейнере.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-154">It contains the commands that tell Docker how to set up and run your application or service in a container.</span></span> <span data-ttu-id="ce6ea-155">Можно вручную создать Dockerfile в коде и добавить его в проект вместе с зависимостями .NET.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-155">You can manually create a Dockerfile in code and add it to your project along with your .NET dependencies.</span></span>

<span data-ttu-id="ce6ea-156">Со средствами Visual Studio для Docker эта задача выполняется лишь несколькими щелчками мыши.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-156">With Visual Studio Tools for Docker, this task requires only a few mouse clicks.</span></span> <span data-ttu-id="ce6ea-157">При создании нового проекта в Visual Studio 2017 можно выбрать параметр **Включить поддержку Docker**, как показано на рисунке 5-3.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-157">When you create a new project in Visual Studio 2017, there's an option named **Enable Docker Support**, as shown in Figure 5-3.</span></span>

![Включение поддержки Docker при создании нового проекта в Visual Studio 2017](./media/image5.png)

<span data-ttu-id="ce6ea-159">**Рис. 5-3**.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-159">**Figure 5-3**.</span></span> <span data-ttu-id="ce6ea-160">Включение поддержки Docker при создании нового проекта в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="ce6ea-160">Enabling Docker Support when creating a new project in Visual Studio 2017</span></span>

<span data-ttu-id="ce6ea-161">Можно также включить поддержку Docker в существующий проект веб-приложения .NET Core, щелкнув правой кнопкой мыши проект в **обозревателе решений** и выбрав **Добавить** > **Поддержка Docker**, как показано на рисунке 5-4.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-161">You can also enable Docker support on an existing .NET Core web app project by right-clicking the project in **Solution Explorer** and selecting **Add** > **Docker Support**, as shown in Figure 5-4.</span></span>

![Пункт меню "Добавить поддержку Docker" в Visual Studio](./media/add-docker-support.png)

<span data-ttu-id="ce6ea-163">**Рис. 5-4**.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-163">**Figure 5-4**.</span></span> <span data-ttu-id="ce6ea-164">Включение поддержки Docker в существующем проекте Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="ce6ea-164">Enabling Docker support in an existing Visual Studio 2017 project</span></span>

<span data-ttu-id="ce6ea-165">Это действие добавляет *Dockerfile* в проект с необходимой конфигурацией и доступно только для проектов веб-приложений.NET Core.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-165">This action adds a *Dockerfile* to the project with the required configuration, and is only available on .NET Core web app projects.</span></span>

<span data-ttu-id="ce6ea-166">Чтобы добавить файл *docker-compose.yml* для всего решения, щелкните правой кнопкой мыши проект в **обозревателе решений** и выберите **Добавить** >  **Поддержка оркестратора контейнеров**, как показано на рисунке 5-5.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-166">To add a *docker-compose.yml* file for the whole solution, right-click on the project in **Solution Explorer** and select **Add** > **Container Orchestrator Support**, as shown in Figure 5-5.</span></span>

![Пункт меню "Добавить оркестратор контейнеров" в Visual Studio](./media/add-container-orchestrator-support.png)

<span data-ttu-id="ce6ea-168">**Рис. 5-5**.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-168">**Figure 5-5**.</span></span> <span data-ttu-id="ce6ea-169">Добавление поддержки оркестратора контейнеров в существующий проект в Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-169">Adding container orchestrator support to an existing project in Visual Studio 2017.</span></span>

<span data-ttu-id="ce6ea-170">В следующих разделах описывается информация, которая находится в каждом из этих файлов.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-170">In the following sections, we describe the information that goes into each of those files.</span></span> <span data-ttu-id="ce6ea-171">Visual Studio может сделать это вместо вас, однако полезно разобраться, что входит в Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-171">Visual Studio can do this work for you, but it is useful to understand what goes into a Dockerfile.</span></span>

### <a name="option-a-creating-a-project-using-an-existing-official-net-docker-image"></a><span data-ttu-id="ce6ea-172">Вариант А. Создание проекта с помощью существующего официального образа .NET Docker</span><span class="sxs-lookup"><span data-stu-id="ce6ea-172">Option A: Creating a project using an existing official .NET Docker image</span></span>

<span data-ttu-id="ce6ea-173">Обычно вы создаете пользовательский образ для своего контейнера на основе базового образа, который можно получить из официального репозитория в реестре [Центра Docker](https://hub.docker.com/).</span><span class="sxs-lookup"><span data-stu-id="ce6ea-173">You usually build a custom image for your container on top of a base image you can get from an official repository at the [Docker Hub](https://hub.docker.com/) registry.</span></span> <span data-ttu-id="ce6ea-174">Именно это происходит на внутреннем уровне при включении поддержки Docker в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-174">That is precisely what happens under the covers when you enable Docker support in Visual Studio.</span></span> <span data-ttu-id="ce6ea-175">Dockerfile использует существующий образ aspnetcore.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-175">The Dockerfile uses an existing aspnetcore image.</span></span>

<span data-ttu-id="ce6ea-176">Ранее было показано, какие образы и репозитории Docker можно использовать в зависимости от выбранной платформы и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-176">Earlier we explained which Docker images and repos you can use, depending on the framework and OS you have chosen.</span></span> <span data-ttu-id="ce6ea-177">Например, если вы выбрали ASP.NET Core (Windows или Linux), следует использовать образ microsoft/aspnetcore:2.0.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-177">For instance, if you want to use ASP.NET Core (Linux or Windows), the image to use is microsoft/aspnetcore:2.0.</span></span> <span data-ttu-id="ce6ea-178">Таким образом, достаточно просто указать, какой базовый образ Docker будет использоваться для контейнера.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-178">Therefore, you just need to specify what base Docker image you will use for your container.</span></span> <span data-ttu-id="ce6ea-179">Для этого добавьте в Dockerfile строку FROM microsoft/aspnetcore:2.0.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-179">You do that by adding FROM microsoft/aspnetcore:2.0 to your Dockerfile.</span></span> <span data-ttu-id="ce6ea-180">Visual Studio выполняет это автоматически, но в случае обновления версии вы обновляете это значение.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-180">This is automatically performed by Visual Studio, but if you were to update the version, you update this value.</span></span>

<span data-ttu-id="ce6ea-181">Использование официального репозитория образов .NET из Центра Docker с номером версии гарантирует, что на всех компьютерах (включая компьютеры для разработки, тестирования и работы) будут доступны одни и те же функции языка.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-181">Using an official .NET image repository from Docker Hub with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="ce6ea-182">Ниже приведен пример Dockerfile для контейнера ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-182">The following example shows a sample Dockerfile for an ASP.NET Core container.</span></span>

```Dockerfile
FROM microsoft/aspnetcore:2.0

ARG source

WORKDIR /app

EXPOSE 80

COPY ${source:-obj/Docker/publish} .

ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

<span data-ttu-id="ce6ea-183">В этом случае контейнер основан на версии 2.0 официального образа Docker ASP.NET Core (мультиархитектурного для Linux и Windows).</span><span class="sxs-lookup"><span data-stu-id="ce6ea-183">In this case, the container is based on version 2.0 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows).</span></span> <span data-ttu-id="ce6ea-184">Это параметр `FROM microsoft/aspnetcore:2.0`.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-184">This is the setting `FROM microsoft/aspnetcore:2.0`.</span></span> <span data-ttu-id="ce6ea-185">(Дополнительные сведения об этом базовом образе см. на страницах [Образ Docker ASP.NET Core](https://hub.docker.com/r/microsoft/aspnetcore/) и [Образ Docker .NET Core](https://hub.docker.com/r/microsoft/dotnet/).) Кроме того, в Dockerfile необходимо указать Docker прослушивать порт TCP, который будет использоваться во время выполнения (в данном случае это порт 80, как задано в параметре EXPOSE).</span><span class="sxs-lookup"><span data-stu-id="ce6ea-185">(For more information about this base image, see the [ASP.NET Core Docker Image](https://hub.docker.com/r/microsoft/aspnetcore/) page and the [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) page.) In the Dockerfile, you also need to instruct Docker to listen on the TCP port you will use at runtime (in this case, port 80, as configured with the EXPOSE setting).</span></span>

<span data-ttu-id="ce6ea-186">В Dockerfile можно задать дополнительные параметры конфигурации, в зависимости от используемого языка и платформы.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-186">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you are using.</span></span> <span data-ttu-id="ce6ea-187">Например, параметр ENTRYPOINT со значением \["dotnet", "MySingleContainerWebApp.dll"\] указывает Docker запускать приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-187">For instance, the ENTRYPOINT line with \["dotnet", "MySingleContainerWebApp.dll"\] tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="ce6ea-188">Если для создания и запуска приложения .NET используется пакет SDK и .NET Core CLI (dotnet CLI), этот параметр будет другим.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-188">If you are using the SDK and the .NET Core CLI (dotnet CLI) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="ce6ea-189">Параметр ENTRYPOINT, который находится в нижней строке, и другие параметры будут отличаться в зависимости от языка и платформы, выбранных для приложения.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-189">The bottom line is that the ENTRYPOINT line and other settings will be different depending on the language and platform you choose for your application.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ce6ea-190">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ce6ea-190">Additional resources</span></span>

- <span data-ttu-id="ce6ea-191">**Создание образов Docker для приложений .NET Core**</span><span class="sxs-lookup"><span data-stu-id="ce6ea-191">**Building Docker Images for .NET Core Applications**</span></span>

   [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](../../../core/docker/building-net-docker-images.md)

- <span data-ttu-id="ce6ea-192">**Создание собственного образа**.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-192">**Build your own image**.</span></span> <span data-ttu-id="ce6ea-193">В официальной документации Docker.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-193">In the official Docker documentation.</span></span>

   [*https://docs.docker.com/engine/tutorials/dockerimages/*](https://docs.docker.com/engine/tutorials/dockerimages/)

### <a name="using-multi-arch-image-repositories"></a><span data-ttu-id="ce6ea-194">Использование мультиархитектурных репозиториев</span><span class="sxs-lookup"><span data-stu-id="ce6ea-194">Using multi-arch image repositories</span></span>

<span data-ttu-id="ce6ea-195">Один репозиторий может содержать варианты платформ, например образ Linux и образ Windows.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-195">A single repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="ce6ea-196">Эта функция позволяет поставщикам, таким как Майкрософт, которые создают базовые образы, создать один репозиторий для охвата нескольких платформ (т. е. Windows и Linux).</span><span class="sxs-lookup"><span data-stu-id="ce6ea-196">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is Linux and Windows).</span></span> <span data-ttu-id="ce6ea-197">Например, репозиторий [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) в реестре Центра Docker обеспечивает поддержку Linux и Windows Nano Server при использовании одного и того же имени репозитория.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-197">For example, the [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same repo name.</span></span>

<span data-ttu-id="ce6ea-198">Можно указать тег, явно задающий платформу, как в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="ce6ea-198">If you specify a tag, targeting a platform that is explicit like in the following cases:</span></span>

- <span data-ttu-id="ce6ea-199">**microsoft/aspnetcore:2.0.0-jessie**</span><span class="sxs-lookup"><span data-stu-id="ce6ea-199">**microsoft/aspnetcore:2.0.0-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux

- <span data-ttu-id="ce6ea-200">**microsoft/aspnetcore:2.0.0-nanoserver**</span><span class="sxs-lookup"><span data-stu-id="ce6ea-200">**microsoft/aspnetcore:2.0.0-nanoserver**</span></span>

        .NET Core 2.0 runtime-only on Windows Nano Server

<span data-ttu-id="ce6ea-201">Однако в середине 2017 г. появилась возможность указывать одно и то же имя образа, даже с одинаковым тегом, и новые мультиархитектурные образы (например, образ aspnetcore, поддерживающий мультиархитектурность) будут использовать версию Windows или Linux в зависимости от развернутой базовой ОС Docker, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="ce6ea-201">But, and this is new since mid-2017, if you specify the same image name, even with the same tag, the new multi-arch images (like the aspnetcore image, which supports multi-arch) will use the Linux or Windows version depending on the Docker host OS you are deploying, as shown in the following example:</span></span>

- <span data-ttu-id="ce6ea-202">**microsoft/aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="ce6ea-202">**microsoft/aspnetcore:2.0**</span></span>

        Multi-arch: .NET Core 2.0 runtime-only on Linux or Windows Nano Server depending on the Docker host OS

<span data-ttu-id="ce6ea-203">Таким образом, при запросе образа с узла Windows будет получен вариант для Windows, а при запросе образа с тем же именем с узла Linux будет получен вариант для Linux.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-203">This way, when you pull an image from a Windows host, it will pull the Windows variant, and pulling the same image name from a Linux host will pull the Linux variant.</span></span>

### <a name="option-b-creating-your-base-image-from-scratch"></a><span data-ttu-id="ce6ea-204">Вариант Б. Создание базового образа с нуля</span><span class="sxs-lookup"><span data-stu-id="ce6ea-204">Option B: Creating your base image from scratch</span></span>

<span data-ttu-id="ce6ea-205">Вы можете создать собственный базовый образ Docker с нуля.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-205">You can create your own Docker base image from scratch.</span></span> <span data-ttu-id="ce6ea-206">Этот сценарий не рекомендуется для тех, кто только начинает работать с Docker, но если вы хотите задать определенные биты базового образа, это можно сделать.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-206">This scenario is not recommended for someone who is starting with Docker, but if you want to set the specific bits of your own base image, you can do so.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ce6ea-207">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ce6ea-207">Additional resources</span></span>

- <span data-ttu-id="ce6ea-208">**Мультиархитектурные образы .NET Core**.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-208">**Multi-arch .NET Core images**.</span></span>

   https://github.com/dotnet/announcements/issues/14

- <span data-ttu-id="ce6ea-209">**Создание базового образа**.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-209">**Create a base image**.</span></span> <span data-ttu-id="ce6ea-210">Официальная документация Docker.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-210">Official Docker documentation.</span></span>

   [*https://docs.docker.com/engine/userguide/eng-image/baseimages/*](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![Рис. "Шаг 3. Создание образов"](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a><span data-ttu-id="ce6ea-212">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-212">Step 3.</span></span> <span data-ttu-id="ce6ea-213">Создание пользовательских образов Docker и внедрение в них собственных приложений или служб</span><span class="sxs-lookup"><span data-stu-id="ce6ea-213">Create your custom Docker images and embed your application or service in them</span></span>

<span data-ttu-id="ce6ea-214">Для каждой службы в приложении необходимо создать связанный образ.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-214">For each service in your application, you need to create a related image.</span></span> <span data-ttu-id="ce6ea-215">Если приложение состоит из одной службы или веб-приложения, достаточно одного образа.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-215">If your application is made up of a single service or web application, you just need a single image.</span></span>

<span data-ttu-id="ce6ea-216">Образы Docker в Visual Studio создаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-216">The Docker images are built automatically for you in Visual Studio.</span></span> <span data-ttu-id="ce6ea-217">Следующие действия потребуются только в рабочем процессе с использованием редактора/CLI и подробно описываются, чтобы показать, что происходит внутри.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-217">The following steps are only needed for the editor/CLI workflow and explained for clarity about what happens underneath.</span></span>

<span data-ttu-id="ce6ea-218">Разработчик должен выполнять разработку и тестирование локально до тех пор, пока не завершит и отправит компонент или пока не перейдет в систему управления версиями (например, в GitHub).</span><span class="sxs-lookup"><span data-stu-id="ce6ea-218">You, as developer, need to develop and test locally until you push a completed feature or change to your source control system (for example, to GitHub).</span></span> <span data-ttu-id="ce6ea-219">Это означает, что необходимо создавать образы Docker и разворачивать контейнеры на локальном узле Docker (на виртуальной машине Windows или Linux), а затем выполнять запуск, тестирование и отладку этих локальных контейнеров.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-219">This means that you need to create the Docker images and deploy containers to a local Docker host (Windows or Linux VM) and run, test, and debug against those local containers.</span></span>

<span data-ttu-id="ce6ea-220">Чтобы создать пользовательский образ в локальной среде с помощью Docker CLI и Dockerfile, можно использовать команду docker build, как показано на рисунке 5-5.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-220">To create a custom image in your local environment by using Docker CLI and your Dockerfile, you can use the docker build command, as in Figure 5-5.</span></span>

![Создание пользовательского образа Docker](./media/image8.png)

<span data-ttu-id="ce6ea-222">**Рис. 5-5**.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-222">**Figure 5-5**.</span></span> <span data-ttu-id="ce6ea-223">Создание пользовательского образа Docker</span><span class="sxs-lookup"><span data-stu-id="ce6ea-223">Creating a custom Docker image</span></span>

<span data-ttu-id="ce6ea-224">При необходимости вместо непосредственного выполнения команды docker build из папки проекта можно сначала создать развертываемую папку с нужными библиотеками .NET и двоичными файлами, выполнив команду dotnet publish, а затем использовать команду docker build.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-224">Optionally, instead of directly running docker build from the project folder, you can first generate a deployable folder with the required .NET libraries and binaries by running dotnet publish, and then use the docker build command.</span></span>

<span data-ttu-id="ce6ea-225">Так будет создан образ Docker с именем **cesardl/netcore-webapi-microservice-docker:first**.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-225">This will create a Docker image with the name **cesardl/netcore-webapi-microservice-docker:first**.</span></span> <span data-ttu-id="ce6ea-226">В данном случае :first — это тег, представляющий конкретную версию.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-226">In this case, :first is a tag representing a specific version.</span></span> <span data-ttu-id="ce6ea-227">Этот шаг можно повторить для каждого пользовательского образа, который вам требуется создать для своего составного приложения Docker.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-227">You can repeat this step for each custom image you need to create for your composed Docker application.</span></span>

<span data-ttu-id="ce6ea-228">Если приложение состоит из нескольких контейнеров (т. е. это многоконтейнерное приложение), можно также использовать команду docker-compose up --build, чтобы собрать все связанные образы одной командой с помощью метаданных, представленных в связанном файле docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-228">When an application is made of multiple containers (that is, it is a multi-container application), you can also use the docker-compose up --build command to build all the related images with a single command by using the metadata exposed in the related docker-compose.yml files.</span></span>

<span data-ttu-id="ce6ea-229">Вы можете найти существующие в локальном репозитории образы с помощью команды docker images, как показано на рисунке 5-6.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-229">You can find the existing images in your local repository by using the docker images command, as shown in Figure 5-6.</span></span>

![Просмотр существующих образов с помощью команды docker images](./media/image9.png)

<span data-ttu-id="ce6ea-231">**Рис. 5-6**.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-231">**Figure 5-6.**</span></span> <span data-ttu-id="ce6ea-232">Просмотр существующих образов с помощью команды docker images</span><span class="sxs-lookup"><span data-stu-id="ce6ea-232">Viewing existing images using the docker images command</span></span>

### <a name="creating-docker-images-with-visual-studio"></a><span data-ttu-id="ce6ea-233">Создание образов Docker с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ce6ea-233">Creating Docker images with Visual Studio</span></span>

<span data-ttu-id="ce6ea-234">При использовании Visual Studio для создания проекта с поддержкой Docker не требуется создавать образ явно.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-234">When you use Visual Studio to create a project with Docker support, you don't explicitly create an image.</span></span> <span data-ttu-id="ce6ea-235">Этот образ создается автоматически, когда вы нажимаете клавишу **F5** и запускаете приложение или службу, добавленную в Docker.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-235">Instead, the image is created for you when you press **F5** to run the dockerized application or service.</span></span> <span data-ttu-id="ce6ea-236">Этот шаг выполняется в Visual Studio автоматически, и вы не увидите, как это происходит, но важно знать, что происходит внутри.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-236">This step is automatic in Visual Studio and you won't see it happen, but it's important that you know what's going on underneath.</span></span>

![Рис. "Шаг 4. Определение служб"](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a><span data-ttu-id="ce6ea-238">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-238">Step 4.</span></span> <span data-ttu-id="ce6ea-239">Определение служб в файле docker-compose.yml при сборке многоконтейнерного приложения Docker</span><span class="sxs-lookup"><span data-stu-id="ce6ea-239">Define your services in docker-compose.yml when building a multi-container Docker application</span></span>

<span data-ttu-id="ce6ea-240">В файле [docker-compose.yml](https://docs.docker.com/compose/compose-file/) можно задать ряд связанных служб для развертывания в качестве составного приложения с помощью команд развертывания.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-240">The [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file lets you define a set of related services to be deployed as a composed application with deployment commands.</span></span>

<span data-ttu-id="ce6ea-241">Чтобы использовать файл docker-compose.yml, его необходимо создать в основной или корневой папке решения, и его содержимое должно быть аналогично приведенному в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-241">To use a docker-compose.yml file, you need to create the file in your main or root solution folder, with content similar to that in the following example:</span></span>

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

<span data-ttu-id="ce6ea-242">Данный файл docker-compose.yml представляет собой упрощенную и объединенную версию.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-242">This docker-compose.yml file is a simplified and merged version.</span></span> <span data-ttu-id="ce6ea-243">Он содержит статические данные конфигурации для каждого контейнера (такие как имя пользовательского образа), которые применяются всегда, а также сведения о конфигурации, которые могут зависеть от среды развертывания, такие как строка подключения.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-243">It contains static configuration data for each container (like the name of the custom image), which always applies, plus configuration information that might depend on the deployment environment, like the connection string.</span></span> <span data-ttu-id="ce6ea-244">В следующих разделах вы узнаете, как можно разбить конфигурацию в файле docker-compose.yml на несколько файлов docker-compose и переопределить значения в зависимости от среды и типа выполнения (отладка или выпуск).</span><span class="sxs-lookup"><span data-stu-id="ce6ea-244">In later sections, you will learn how you can split the docker-compose.yml configuration into multiple docker-compose files and override values depending on the environment and execution type (debug or release).</span></span>

<span data-ttu-id="ce6ea-245">В примере файла docker-compose.yml определяются четыре службы: служба webmvc (веб-приложение), две микрослужбы (catalog.api и ordering.api) и один контейнер источника данных, sql.data, на основе SQL Server для Linux, работающего как контейнер.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-245">The docker-compose.yml file example defines four services: the webmvc service (a web application), two microservices (catalog.api and ordering.api), and one data source container, sql.data, based on SQL Server for Linux running as a container.</span></span> <span data-ttu-id="ce6ea-246">Каждая служба развертывается как контейнер, поэтому образ Docker требуется для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-246">Each service is deployed as a container, so a Docker image is required for each.</span></span>

<span data-ttu-id="ce6ea-247">Файл docker-compose.yml задает не только используемые контейнеры, но и их индивидуальные конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-247">The docker-compose.yml file specifies not only what containers are being used, but how they are individually configured.</span></span> <span data-ttu-id="ce6ea-248">Например, в определении контейнера webmvc в файле .yml задается следующее.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-248">For instance, the webmvc container definition in the .yml file:</span></span>

- <span data-ttu-id="ce6ea-249">Используется предварительно созданный образ eshop/web:latest.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-249">Uses a pre-built eshop/web:latest image.</span></span> <span data-ttu-id="ce6ea-250">Однако вы также можете настроить сборку этого образа при выполнении команды docker-compose с дополнительной конфигурацией на основе раздела build: в файле docker-compose.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-250">However, you could also configure the image to be built as part of the docker-compose execution with an additional configuration based on a build: section in the docker-compose file.</span></span>

- <span data-ttu-id="ce6ea-251">Инициализируются две переменные среды (CatalogUrl и OrderingUrl).</span><span class="sxs-lookup"><span data-stu-id="ce6ea-251">Initializes two environment variables (CatalogUrl and OrderingUrl).</span></span>

- <span data-ttu-id="ce6ea-252">Предоставленный порт 80 в контейнере переадресуется на внешний порт 80 на хост-компьютере.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-252">Forwards the exposed port 80 on the container to the external port 80 on the host machine.</span></span>

- <span data-ttu-id="ce6ea-253">Веб-приложение связывается со службами catalog и ordering с помощью параметра depends\_on.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-253">Links the web app to the catalog and ordering service with the depends\_on setting.</span></span> <span data-ttu-id="ce6ea-254">В результате данная служба будет ожидать запуска этих служб.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-254">This causes the service to wait until those services are started.</span></span>

<span data-ttu-id="ce6ea-255">Мы вернемся к файлу docker-compose.yml в следующем разделе, когда будем рассматривать реализацию микрослужб и многоконтейнерных приложений.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-255">We will revisit the docker-compose.yml file in a later section when we cover how to implement microservices and multi-container apps.</span></span>

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a><span data-ttu-id="ce6ea-256">Работа с файлом docker-compose.yml в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="ce6ea-256">Working with docker-compose.yml in Visual Studio 2017</span></span>

<span data-ttu-id="ce6ea-257">При добавлении поддержки оркестратора контейнеров в проект веб-приложения, как показано на рисунке 5-7, Visual Studio добавляет раздел служб (проект) в решение, содержащее файл docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-257">When you add container orchestrator support to a web app project, as shown in Figure 5-7, Visual Studio adds a service section (project) to the solution that contains a docker-compose.yml file.</span></span> <span data-ttu-id="ce6ea-258">Это простой способ начать создание многоконтейнерного решения.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-258">This is an easy way to start composing a multiple-container solution.</span></span>

![Пункт меню "Добавить оркестратор контейнеров" в Visual Studio](./media/add-container-orchestrator-support.png)

<span data-ttu-id="ce6ea-260">**Рис. 5-7**.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-260">**Figure 5-7**.</span></span> <span data-ttu-id="ce6ea-261">Добавление поддержки Docker в Visual Studio 2017 щелчком правой кнопкой мыши на проекте ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ce6ea-261">Adding Docker support in Visual Studio 2017 by right-clicking an ASP.NET Core project</span></span>

<span data-ttu-id="ce6ea-262">Добавление поддержки оркестратора контейнеров добавляет Dockerfile в проект (если он еще не существует).</span><span class="sxs-lookup"><span data-stu-id="ce6ea-262">Adding container orchestrator support adds the Dockerfile to your project (if it doesn't already exist).</span></span> <span data-ttu-id="ce6ea-263">Это действие также добавляет сведения о конфигурации в глобальный файл docker-compose.yml на уровне решения.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-263">It also adds configuration information to a global docker-compose.yml file at the solution level.</span></span> <span data-ttu-id="ce6ea-264">Вы увидите новый узел проекта (файл проекта *docker-compose.dcproj*) в **обозревателе решений**, содержащий файл docker-compose.yml, как показано на рис. 5-8.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-264">You'll see a new project node (the *docker-compose.dcproj* project file) in **Solution Explorer** that contains the docker-compose.yml file, as shown in Figure 5-8.</span></span>

![Узел docker-compose в обозревателе решений](./media/docker-compose-files.png)

<span data-ttu-id="ce6ea-266">**Рис. 5-8**.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-266">**Figure 5-8**.</span></span> <span data-ttu-id="ce6ea-267">Узел дерева **docker-compose**, добавленный в обозреватель решений Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="ce6ea-267">The **docker-compose** tree node added in Visual Studio 2017 Solution Explorer</span></span>

<span data-ttu-id="ce6ea-268">Затем можно открыть файлы docker-compose.yml и добавить в них дополнительные возможности.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-268">You can then open the docker-compose.yml file and update it with additional features.</span></span>

<span data-ttu-id="ce6ea-269">Можно развернуть многоконтейнерное приложение с единственным файлом docker-compose.yml с помощью команды `docker-compose up`.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-269">You can deploy a multi-container application with a single docker-compose.yml file by using the `docker-compose up` command.</span></span>

![Рис. "Шаг 5. Запуск приложения"](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a><span data-ttu-id="ce6ea-271">Шаг 5.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-271">Step 5.</span></span> <span data-ttu-id="ce6ea-272">Сборка и запуск приложения Docker</span><span class="sxs-lookup"><span data-stu-id="ce6ea-272">Build and run your Docker application</span></span>

<span data-ttu-id="ce6ea-273">Если в приложении имеется только один контейнер, его можно запустить путем развертывания на узле Docker (на виртуальной машине или физическом сервере).</span><span class="sxs-lookup"><span data-stu-id="ce6ea-273">If your application only has a single container, you can run it by deploying it to your Docker host (VM or physical server).</span></span> <span data-ttu-id="ce6ea-274">Но если приложение содержит несколько служб, его можно развернуть как составное приложение с помощью одной команды CLI (docker-compose up) или в Visual Studio, в котором внутри будет выполняться эта же команда.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-274">However, if your application contains multiple services, you can deploy it as a composed application, either using a single CLI command (docker-compose up), or with Visual Studio, which will use that command under the covers.</span></span> <span data-ttu-id="ce6ea-275">Давайте рассмотрим разные варианты.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-275">Let’s look at the different options.</span></span>

### <a name="option-a-run-a-single-container-app"></a><span data-ttu-id="ce6ea-276">Вариант А. Запуск одноконтейнерного приложения</span><span class="sxs-lookup"><span data-stu-id="ce6ea-276">Option A: Run a single-container app</span></span>

#### <a name="docker-cli"></a><span data-ttu-id="ce6ea-277">Docker CLI</span><span class="sxs-lookup"><span data-stu-id="ce6ea-277">Docker CLI</span></span>

<span data-ttu-id="ce6ea-278">Контейнер Docker можно запустить с помощью команды docker run, как показано на рисунке 5-9.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-278">You can run a Docker container using the docker run command, as in Figure 5-9:</span></span>

```console
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

![Запуск контейнера Docker с помощью команды docker run](./media/image13.png)

<span data-ttu-id="ce6ea-280">**Рис. 5-9**.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-280">**Figure 5-9**.</span></span> <span data-ttu-id="ce6ea-281">Запуск контейнера Docker с помощью команды docker run</span><span class="sxs-lookup"><span data-stu-id="ce6ea-281">Running a Docker container using the docker run command</span></span>

<span data-ttu-id="ce6ea-282">В этом случае команда привязывает внутренний порт 5000 контейнера к порту 80 хост-компьютера.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-282">In this case, the command binds the internal port 5000 of the container to port 80 of the host machine.</span></span> <span data-ttu-id="ce6ea-283">Это означает, что узел выполняет прослушивание порта 80 и переадресацию в порт 5000 в контейнере.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-283">This means that the host is listening on port 80 and forwarding to port 5000 on the container.</span></span>

#### <a name="visual-studio"></a><span data-ttu-id="ce6ea-284">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ce6ea-284">Visual Studio</span></span>

<span data-ttu-id="ce6ea-285">Если вы еще не добавили поддержку оркестратора контейнеров, запустите одноконтейнерное приложение в Visual Studio, нажав клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-285">If you haven't added container orchestrator support, you can also run a single container app in Visual Studio by pressing **F5**.</span></span> <span data-ttu-id="ce6ea-286">Контейнер запускается локально с помощью команды docker run.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-286">The container runs locally using docker run.</span></span>

### <a name="option-b-run-a-multi-container-app"></a><span data-ttu-id="ce6ea-287">Вариант Б. Запуск многоконтейнерного приложения</span><span class="sxs-lookup"><span data-stu-id="ce6ea-287">Option B: Run a multi-container app</span></span>

<span data-ttu-id="ce6ea-288">В большинстве корпоративных сценариев приложение Docker будет состоять из нескольких служб; это означает, что необходимо запускать многоконтейнерное приложение, как показано на рисунке 5-10.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-288">In most enterprise scenarios, a Docker application will be composed of multiple services, which means you need to run a multi-container application, as shown in Figure 5-10.</span></span>

![Рисунок, изображающий виртуальную машину с развернутыми контейнерами Docker](./media/image14.png)

<span data-ttu-id="ce6ea-290">**Рис. 5-10**.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-290">**Figure 5-10**.</span></span> <span data-ttu-id="ce6ea-291">Виртуальная машина с развернутыми контейнерами Docker</span><span class="sxs-lookup"><span data-stu-id="ce6ea-291">VM with Docker containers deployed</span></span>

#### <a name="docker-cli"></a><span data-ttu-id="ce6ea-292">Docker CLI</span><span class="sxs-lookup"><span data-stu-id="ce6ea-292">Docker CLI</span></span>

<span data-ttu-id="ce6ea-293">Чтобы запустить многоконтейнерное приложение с помощью Docker CLI, можно выполнить команду docker-compose up.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-293">To run a multi-container application with the Docker CLI, you can run the docker-compose up command.</span></span> <span data-ttu-id="ce6ea-294">Эта команда разворачивает многоконтейнерное приложение с помощью файла docker-compose.yml, существующего на уровне решения.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-294">This command uses the docker-compose.yml file that you have at the solution level to deploy a multi-container application.</span></span> <span data-ttu-id="ce6ea-295">На рисунке 5-11 показаны результаты выполнения этой команды из главного каталога проекта, в котором находится файл docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-295">Figure 5-11 shows the results when running the command from your main project directory, which contains the docker-compose.yml file.</span></span>

![Пример результата выполнения команды docker-compose up](./media/image15.png)

<span data-ttu-id="ce6ea-297">**Рис. 5-11**.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-297">**Figure 5-11**.</span></span> <span data-ttu-id="ce6ea-298">Пример результата выполнения команды docker-compose up</span><span class="sxs-lookup"><span data-stu-id="ce6ea-298">Example results when running the docker-compose up command</span></span>

<span data-ttu-id="ce6ea-299">После выполнения команды docker-compose up приложение и связанные с ним контейнеры развертываются в узле Docker.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-299">After the docker-compose up command runs, the application and its related containers are deployed into your Docker host.</span></span>

#### <a name="visual-studio"></a><span data-ttu-id="ce6ea-300">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ce6ea-300">Visual Studio</span></span>

<span data-ttu-id="ce6ea-301">Запустить многоконтейнерное приложение с помощью Visual Studio 2017 очень просто.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-301">Running a multi-container application using Visual Studio 2017 is simple.</span></span> <span data-ttu-id="ce6ea-302">Вы можете не только запускать многоконтейнерное приложение, но также и отлаживать все его контейнеры непосредственно в Visual Studio, установив обычные точки останова.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-302">Not only can you run the multi-container application, but you're able to debug all its containers directly from Visual Studio by setting regular breakpoints.</span></span>

<span data-ttu-id="ce6ea-303">Как упоминалось ранее, каждый раз при добавлении поддержки оркестратора контейнеров в проект в решении этот проект настраивается в глобальном (на уровне решения) файле docker-compose.yml, что позволяет запускать или отлаживать все решение сразу.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-303">As mentioned before, each time you add container orchestrator support to a project within a solution, that project is configured in the global (solution-level) docker-compose.yml file, which lets you run or debug the whole solution at once.</span></span> <span data-ttu-id="ce6ea-304">Visual Studio будет запускать по одному контейнеру для каждого проекта с включенной поддержкой решения Docker и выполнять все внутренние шаги автоматически (dotnet publish, docker build и т. д.).</span><span class="sxs-lookup"><span data-stu-id="ce6ea-304">Visual Studio will start one container for each project that has Docker solution support enabled and perform all the internal steps for you (dotnet publish, docker build, etc.).</span></span>

<span data-ttu-id="ce6ea-305">Здесь важно то, что, как показано на рисунке 5-12, в Visual Studio 2017 имеется дополнительная команда **Docker** для действия клавиши **F5**.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-305">The important point here is that, as shown in Figure 5-12, in Visual Studio 2017 there's an additional **Docker** command for the **F5** key action.</span></span> <span data-ttu-id="ce6ea-306">Эта возможность позволяет запускать или отлаживать многоконтейнерное приложение путем запуска всех контейнеров, определенных в файлах docker-compose.yml на уровне решения.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-306">This option lets you run or debug a multi-container application by running all the containers that are defined in the docker-compose.yml files at the solution level.</span></span> <span data-ttu-id="ce6ea-307">Возможность отладки многоконтейнерных решений означает, что можно установить несколько точек останова, чтобы все они были в разных проектах (контейнерах), и во время отладки из Visual Studio вы будете останавливаться в точках останова, заданных в разных проектах, и работать в разных контейнерах.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-307">The ability to debug multiple-container solutions means that you can set several breakpoints, each breakpoint in a different project (container), and while debugging from Visual Studio you will stop at breakpoints defined in different projects and running on different containers.</span></span>

![Запуск многоконтейнерных приложений в Visual Studio 2017](./media/image16.png)

<span data-ttu-id="ce6ea-309">**Рис. 5-12**.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-309">**Figure 5-12**.</span></span> <span data-ttu-id="ce6ea-310">Запуск многоконтейнерных приложений в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="ce6ea-310">Running multi-container apps in Visual Studio 2017</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ce6ea-311">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ce6ea-311">Additional resources</span></span>

-  <span data-ttu-id="ce6ea-312">**Развертывание контейнера ASP.NET на удаленном узле Docker**</span><span class="sxs-lookup"><span data-stu-id="ce6ea-312">**Deploy an ASP.NET container to a remote Docker host**</span></span>

   [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a><span data-ttu-id="ce6ea-313">Примечание о тестировании и развертывании с использованием оркестраторов</span><span class="sxs-lookup"><span data-stu-id="ce6ea-313">A note about testing and deploying with orchestrators</span></span>

<span data-ttu-id="ce6ea-314">Команды docker-compose up и docker run (или запуск и отладка контейнеров в Visual Studio) подходят для тестирования контейнеров в вашей среде разработки.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-314">The docker-compose up and docker run commands (or running and debugging the containers in Visual Studio) are adequate for testing containers in your development environment.</span></span> <span data-ttu-id="ce6ea-315">Однако этот способ не подходит, если вы планируете использовать оркестраторы и кластеры Docker, такие как Docker Swarm, Mesosphere DC/OS и Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-315">But you should not use this approach if you are targeting Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes.</span></span> <span data-ttu-id="ce6ea-316">Если вы используете кластер, например [режим Docker Swarm](https://docs.docker.com/engine/swarm/) (доступный в Docker CE для Windows и Mac, начиная с версии 1.12), необходимо выполнять развертывание и тестирование единственных служб с помощью дополнительных команд, таких как [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/).</span><span class="sxs-lookup"><span data-stu-id="ce6ea-316">If you are using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker CE for Windows and Mac since version 1.12), you need to deploy and test with additional commands like [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/) for single services.</span></span> <span data-ttu-id="ce6ea-317">При развертывании приложения, состоящего из нескольких контейнеров, следует использовать команды [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) и [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/), чтобы развернуть составное приложение как *стек*.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-317">If you are deploying an application composed of several containers, you use [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) and [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) to deploy the composed application as a *stack*.</span></span> <span data-ttu-id="ce6ea-318">Дополнительные сведения см. в записи блога [Introducing Experimental Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) (Общие сведения об экспериментальных пакетах распределенных приложений) в документации Docker</span><span class="sxs-lookup"><span data-stu-id="ce6ea-318">For more information, see the blog post [Introducing Experimental Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) in the Docker documentation.</span></span> <span data-ttu-id="ce6ea-319">на сайте Docker.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-319">on the Docker site.</span></span>

<span data-ttu-id="ce6ea-320">Для [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) и [Kubernetes](https://kubernetes.io/docs/user-guide/deployments/) вы также должны использовать другие скрипты и команды развертывания.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-320">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](https://kubernetes.io/docs/user-guide/deployments/) you would use different deployment commands and scripts as well.</span></span>

![Рис. "Шаг 6"](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a><span data-ttu-id="ce6ea-322">Шаг 6.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-322">Step 6.</span></span> <span data-ttu-id="ce6ea-323">Тестирование приложения Docker с помощью локального узла Docker</span><span class="sxs-lookup"><span data-stu-id="ce6ea-323">Test your Docker application using your local Docker host</span></span>

<span data-ttu-id="ce6ea-324">Этот шаг будет зависеть от того, что делает ваше приложение.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-324">This step will vary depending on what your application is doing.</span></span> <span data-ttu-id="ce6ea-325">В случае простого веб-приложения .NET Core, развернутого в виде единственного контейнера или службы, можно получить доступ к этой службе, открыв на узле Docker браузер и перейдя в нем на этот сайт, как показано на рисунке 5-13.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-325">In a simple .NET Core Web application that is deployed as a single container or service, you can access the service by opening a browser on the Docker host and navigating to that site, as shown in Figure 5-13.</span></span> <span data-ttu-id="ce6ea-326">(Если конфигурация в Dockerfile сопоставляет контейнер с портом узла, отличным от 80, укажите этот порт узла в URL-адресе.)</span><span class="sxs-lookup"><span data-stu-id="ce6ea-326">(If the configuration in the Dockerfile maps the container to a port on the host that is anything other than 80, include the host port in the URL.)</span></span>

![Пример локального тестирования приложения Docker с помощью localhost](./media/image18.png)

<span data-ttu-id="ce6ea-328">**Рис. 5-13**.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-328">**Figure 5-13**.</span></span> <span data-ttu-id="ce6ea-329">Пример локального тестирования приложения Docker с помощью localhost</span><span class="sxs-lookup"><span data-stu-id="ce6ea-329">Example of testing your Docker application locally using localhost</span></span>

<span data-ttu-id="ce6ea-330">Если localhost не указывает на IP-адрес узла Docker (при использовании Docker CE это должно происходить по умолчанию), то для перехода к службе используйте IP-адрес сетевой карты вашего компьютера.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-330">If localhost is not pointing to the Docker host IP (by default, when using Docker CE, it should), to navigate to your service, use the IP address of your machine’s network card.</span></span>

<span data-ttu-id="ce6ea-331">Этот URL-адрес в браузере использует порт 80 для рассматриваемого примера конкретного контейнера.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-331">This URL in the browser uses port 80 for the particular container example being discussed.</span></span> <span data-ttu-id="ce6ea-332">Однако внутренние запросы перенаправляются на порт 5000, поскольку именно так было выполнено развертывание с помощью команды docker run, как описано в предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-332">However, internally the requests are being redirected to port 5000, because that was how it was deployed with the docker run command, as explained in a previous step.</span></span>

<span data-ttu-id="ce6ea-333">Вы также можете тестировать приложение с помощью команды curl с терминала, как показано на рисунке 5-14.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-333">You can also test the application using curl from the terminal, as shown in Figure 5-14.</span></span> <span data-ttu-id="ce6ea-334">В случае установки Docker в Windows по умолчанию всегда будет использоваться IP-адрес узла Docker 10.0.75.1 помимо фактического IP-адреса вашего компьютера.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-334">In a Docker installation on Windows, the default Docker Host IP is always 10.0.75.1 in addition to your machine’s actual IP address.</span></span>

![Пример локального тестирования приложения Docker с помощью curl](./media/image19.png)

<span data-ttu-id="ce6ea-336">**Рис. 5-14**.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-336">**Figure 5-14**.</span></span> <span data-ttu-id="ce6ea-337">Пример локального тестирования приложения Docker с помощью curl</span><span class="sxs-lookup"><span data-stu-id="ce6ea-337">Example of testing your Docker application locally using curl</span></span>

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a><span data-ttu-id="ce6ea-338">Тестирование и отладка контейнеров в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="ce6ea-338">Testing and debugging containers with Visual Studio 2017</span></span>

<span data-ttu-id="ce6ea-339">При запуске и отладке контейнеров в Visual Studio 2017 вы можете отлаживать приложения .NET в основном так же, как при запуске без контейнеров.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-339">When running and debugging the containers with Visual Studio 2017, you can debug the .NET application in much the same way as you would when running without containers.</span></span>

### <a name="testing-and-debugging-without-visual-studio"></a><span data-ttu-id="ce6ea-340">Тестирование и отладка без Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ce6ea-340">Testing and debugging without Visual Studio</span></span>

<span data-ttu-id="ce6ea-341">Если при разработке используется редактор или CLI, отлаживать контейнеры будет значительно труднее, и вы захотите выполнять отладку путем создания трассировок.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-341">If you are developing using the editor/CLI approach, debugging containers is more difficult and you will want to debug by generating traces.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ce6ea-342">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ce6ea-342">Additional resources</span></span>

- <span data-ttu-id="ce6ea-343">**Отладка приложений в локальном контейнере Docker**</span><span class="sxs-lookup"><span data-stu-id="ce6ea-343">**Debugging apps in a local Docker container**</span></span>

   [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

- <span data-ttu-id="ce6ea-344">**Стив Ласкер (Steve Lasker). Сборка, отладка, развертывание приложений ASP.NET Core с помощью Docker.**</span><span class="sxs-lookup"><span data-stu-id="ce6ea-344">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker.**</span></span> <span data-ttu-id="ce6ea-345">Видео.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-345">Video.</span></span>

   [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a><span data-ttu-id="ce6ea-346">Упрощенный рабочий процесс при разработке контейнеров в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ce6ea-346">Simplified workflow when developing containers with Visual Studio</span></span>

<span data-ttu-id="ce6ea-347">В сущности, при использовании Visual Studio рабочий процесс гораздо проще, чем при использовании редактора или CLI.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-347">Effectively, the workflow when using Visual Studio is a lot simpler than if you use the editor/CLI approach.</span></span> <span data-ttu-id="ce6ea-348">Большинство шагов, необходимых для Docker и связанных с Dockerfile и docker-compose.yml, выполняются скрыто от пользователя или значительно упрощаются благодаря Visual Studio, как показано на рисунке 5-15.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-348">Most of the steps required by Docker related to the Dockerfile and docker-compose.yml files are hidden or simplified by Visual Studio, as shown in Figure 5-15.</span></span>

![Упрощенный рабочий процесс при разработке в Visual Studio](./media/image20.png)

<span data-ttu-id="ce6ea-350">**Рис. 5-15**.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-350">**Figure 5-15**.</span></span> <span data-ttu-id="ce6ea-351">Упрощенный рабочий процесс при разработке в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ce6ea-351">Simplified workflow when developing with Visual Studio</span></span>

<span data-ttu-id="ce6ea-352">Кроме того, вам достаточно будет выполнить шаг 2 (добавление поддержки Docker в проекты) только один раз.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-352">In addition, you need to perform step 2 (adding Docker support to your projects) just once.</span></span> <span data-ttu-id="ce6ea-353">Таким образом, рабочий процесс аналогичен другим обычным задачам разработки, когда для разработки используется .NET.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-353">Therefore, the workflow is similar to your usual development tasks when using .NET for any other development.</span></span> <span data-ttu-id="ce6ea-354">Вам нужно знать, что происходит на самом деле (процесс создания образа, какие базовые образы используются, развертывание контейнеров и т. п.), и в некоторых случаях также может потребоваться изменить файл Dockerfile или docker-compose.yml, чтобы настроить функциональность.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-354">You need to know what is going on under the covers (the image build process, what base images you are using, deployment of containers, etc.) and sometimes you will also need to edit the Dockerfile or docker-compose.yml file to customize behaviors.</span></span> <span data-ttu-id="ce6ea-355">Но благодаря Visual Studio большую часть работы можно выполнить гораздо проще, что существенно повышает эффективность работы.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-355">But most of the work is greatly simplified by using Visual Studio, making you a lot more productive.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ce6ea-356">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ce6ea-356">Additional resources</span></span>

- <span data-ttu-id="ce6ea-357">**Стив Ласкер (Steve Lasker). Разработка .NET Docker в Visual Studio 2017**</span><span class="sxs-lookup"><span data-stu-id="ce6ea-357">**Steve Lasker. .NET Docker Development with Visual Studio 2017**</span></span>

   [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)

- <span data-ttu-id="ce6ea-358">**Джеффри Т. Фриц (Jeffrey T. Fritz). Помещение приложения .NET Core в контейнер с помощью новых средств Docker для Visual Studio**</span><span class="sxs-lookup"><span data-stu-id="ce6ea-358">**Jeffrey T. Fritz. Put a .NET Core App in a Container with the new Docker Tools for Visual Studio**</span></span>

   [*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a><span data-ttu-id="ce6ea-359">Использование команд PowerShell в DockerFile для настройки контейнеров Windows</span><span class="sxs-lookup"><span data-stu-id="ce6ea-359">Using PowerShell commands in a Dockerfile to set up Windows Containers</span></span>

<span data-ttu-id="ce6ea-360">[Контейнеры Windows](/virtualization/windowscontainers/about/) позволяют преобразовывать существующие приложения Windows в образы Docker и развертывать их с помощью тех же средств, что и остальную часть экосистемы Docker.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-360">[Windows Containers](/virtualization/windowscontainers/about/) allow you to convert your existing Windows applications into Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span> <span data-ttu-id="ce6ea-361">Чтобы использовать контейнеры Windows, выполните команды PowerShell в Dockerfile, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="ce6ea-361">To use Windows Containers, you run PowerShell commands in the Dockerfile, as shown in the following example:</span></span>

```Dockerfile
FROM microsoft/windowsservercore

LABEL Description="IIS" Vendor="Microsoft" Version="10"

RUN powershell -Command Add-WindowsFeature Web-Server

CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="ce6ea-362">В этом случае мы используем базовый образ Windows Server Core (параметр FROM) и устанавливаем службы IIS с помощью команды PowerShell (параметр RUN).</span><span class="sxs-lookup"><span data-stu-id="ce6ea-362">In this case, we are using a Windows Server Core base image (the FROM setting) and installing IIS with a PowerShell command (the RUN setting).</span></span> <span data-ttu-id="ce6ea-363">Аналогичным образом можно также использовать команды PowerShell для настройки дополнительных компонентов, таких как ASP.NET 4.x, .NET 4.6 и другого программного обеспечения Windows.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-363">In a similar way, you could also use PowerShell commands to set up additional components like ASP.NET 4.x, .NET 4.6, or any other Windows software.</span></span> <span data-ttu-id="ce6ea-364">Например, следующая команда в Dockerfile настраивает ASP.NET 4.5:</span><span class="sxs-lookup"><span data-stu-id="ce6ea-364">For example, the following command in a Dockerfile sets up ASP.NET 4.5:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a><span data-ttu-id="ce6ea-365">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ce6ea-365">Additional resources</span></span>

- <span data-ttu-id="ce6ea-366">**aspnet-docker/Dockerfile.**</span><span class="sxs-lookup"><span data-stu-id="ce6ea-366">**aspnet-docker/Dockerfile.**</span></span> <span data-ttu-id="ce6ea-367">Примеры команд Powershell, которые можно выполнять в файлах Dockerfile для включения компонентов Windows.</span><span class="sxs-lookup"><span data-stu-id="ce6ea-367">Example Powershell commands to run from dockerfiles to include Windows features.</span></span>

   [*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*](https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile)

>[!div class="step-by-step"]
><span data-ttu-id="ce6ea-368">[Назад](index.md)
>[Вперед](../multi-container-microservice-net-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="ce6ea-368">[Previous](index.md)
[Next](../multi-container-microservice-net-applications/index.md)</span></span>
