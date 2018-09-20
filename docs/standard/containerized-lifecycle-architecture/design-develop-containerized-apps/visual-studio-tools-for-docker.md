---
title: С помощью средств Visual Studio для Docker (Visual Studio в Windows)
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/12/2018
ms.custom: vs-dotnet
ms.openlocfilehash: af14c92ab27885deec878dc33e7b94035f43e65b
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2018
ms.locfileid: "46488955"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a><span data-ttu-id="b875c-103">С помощью средств Visual Studio для Docker (Visual Studio в Windows)</span><span class="sxs-lookup"><span data-stu-id="b875c-103">Using Visual Studio Tools for Docker (Visual Studio on Windows)</span></span>

<span data-ttu-id="b875c-104">Рабочий процесс разработки при использовании инструментов Visual Studio для Docker похоже на рабочий процесс, при использовании Visual Studio Code и Docker CLI.</span><span class="sxs-lookup"><span data-stu-id="b875c-104">The development workflow when using Visual Studio Tools for Docker is similar to the workflow when using Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="b875c-105">По сути, он основан на том же Docker CLI, но проще приступить к работе, упрощает процесс и обеспечивает повышение производительности для сборки, запуска, а также объединять задач.</span><span class="sxs-lookup"><span data-stu-id="b875c-105">In fact, it's based on the same Docker CLI, but it's easier to get started, simplifies the process, and provides greater productivity for the build, run, and compose tasks.</span></span> <span data-ttu-id="b875c-106">Он также имеет возможность выполнять и отлаживать контейнеры с помощью простых действий, таких как F5 или Ctrl + F5, из Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b875c-106">It's also able to execute and debug your containers via simple actions like F5 and Ctrl+F5 from Visual Studio.</span></span> <span data-ttu-id="b875c-107">Благодаря поддержке оркестрации дополнительный контейнер, помимо возможности для запуска и отладки одного контейнера можно выполнять и отлаживать группу контейнеров (всего решения), в то же время.</span><span class="sxs-lookup"><span data-stu-id="b875c-107">With the optional container orchestration support, in addition to being able to run and debug a single container, you can run and debug a group of containers (a whole solution) at the same time.</span></span> <span data-ttu-id="b875c-108">Просто определите контейнеры в том же *docker-compose.yml* файл на уровне решения.</span><span class="sxs-lookup"><span data-stu-id="b875c-108">Just define the containers in the same *docker-compose.yml* file at the solution level.</span></span>

## <a name="configuring-your-local-environment"></a><span data-ttu-id="b875c-109">Настройка локальной среды</span><span class="sxs-lookup"><span data-stu-id="b875c-109">Configuring your local environment</span></span>

<span data-ttu-id="b875c-110">Поддержка docker включена в Visual Studio 2017 с любым из рабочей нагрузки .NET и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b875c-110">Docker support is included in Visual Studio 2017 with any of the .NET and .NET Core workloads installed.</span></span> <span data-ttu-id="b875c-111">Установите Docker для Windows отдельно.</span><span class="sxs-lookup"><span data-stu-id="b875c-111">Install Docker for Windows separately.</span></span>

<span data-ttu-id="b875c-112">В последних версиях Docker для Windows это проще, чем когда-либо для разработки приложений Docker так, как настройка довольно прост, как описано в следующих документах.</span><span class="sxs-lookup"><span data-stu-id="b875c-112">With the latest versions of Docker for Windows, it is easier than ever to develop Docker applications because the setup is straightforward, as explained in the following references.</span></span>

<span data-ttu-id="b875c-113">**Дополнительные сведения:** Дополнительные сведения об установке Docker для Windows, перейдите к <https://docs.docker.com/docker-for-windows/>.</span><span class="sxs-lookup"><span data-stu-id="b875c-113">**More info:** To learn more about installing Docker for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>

<span data-ttu-id="b875c-114">**Дополнительные сведения:** инструкции по установке Visual Studio, см. в статье [ https://visualstudio.microsoft.com/downloads/ ](https://visualstudio.microsoft.com/downloads/).</span><span class="sxs-lookup"><span data-stu-id="b875c-114">**More info:** For instructions on installing Visual Studio, go to [https://visualstudio.microsoft.com/downloads/](https://visualstudio.microsoft.com/downloads/).</span></span>

<span data-ttu-id="b875c-115">Чтобы просмотреть сведения об установке средств Visual Studio для Docker, перейдите к <http://aka.ms/vstoolsfordocker> и <https://docs.microsoft.com/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker>.</span><span class="sxs-lookup"><span data-stu-id="b875c-115">To see more about installing Visual Studio Tools for Docker, go to <http://aka.ms/vstoolsfordocker> and <https://docs.microsoft.com/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker>.</span></span>

## <a name="using-docker-tools-in-visual-studio-2017"></a><span data-ttu-id="b875c-116">С помощью средств Docker в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="b875c-116">Using Docker Tools in Visual Studio 2017</span></span>

<span data-ttu-id="b875c-117">При добавлении поддержки Docker в проект (см. рис. 4-26), Visual Studio добавляет *Dockerfile* в корневую папку проекта.</span><span class="sxs-lookup"><span data-stu-id="b875c-117">When adding Docker support to a project (see Figure 4-26), Visual Studio adds a *Dockerfile* to the project root.</span></span>

![Включение поддержки решения Docker в проекте Visual Studio 2017](./media/image32.png)

<span data-ttu-id="b875c-119">Рис. 4-26: Включение поддержки решения Docker в проекте Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="b875c-119">Figure 4-26: Turning on Docker Solution support in a Visual Studio 2017 project</span></span>

 <span data-ttu-id="b875c-120">Поддержка оркестрации контейнера, с помощью Docker Compose, добавляется по умолчанию в Visual Studio 2017 версии 15.7 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="b875c-120">Container orchestration support, via Docker Compose, is added by default in Visual Studio 2017 versions 15.7 or earlier.</span></span> <span data-ttu-id="b875c-121">Поддержка оркестрации контейнеров — это компонент согласием в Visual Studio 2017 версии 15.8 или более поздней версии, в этом случае Docker Compose и Service Fabric поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="b875c-121">Container orchestration support is an opt-in feature in Visual Studio 2017 versions 15.8 or later, in which case Docker Compose and Service Fabric are supported.</span></span>

<span data-ttu-id="b875c-122">С помощью Visual Studio требуется выделить 15,8 и более поздних версий можно добавить поддержку для нескольких проектов в решении, каждый из которых содержит связанный контейнер.</span><span class="sxs-lookup"><span data-stu-id="b875c-122">With Visual Studio version 15.8 and later, you can add support for multiple projects in a solution that each have an associated container.</span></span> <span data-ttu-id="b875c-123">Щелкните правой кнопкой мыши узел решения или проекта в **обозревателе решений**и выберите **добавить** > **поддержки Оркестрации контейнеров**.</span><span class="sxs-lookup"><span data-stu-id="b875c-123">Right-click on the solution or project node in **Solution Explorer**, and choose **Add** > **Container Orchestration Support**.</span></span>  <span data-ttu-id="b875c-124">Затем выберите **Docker Compose** или **Service Fabric** для управления контейнерами.</span><span class="sxs-lookup"><span data-stu-id="b875c-124">Then choose **Docker Compose** or **Service Fabric** to manage the containers.</span></span>

<span data-ttu-id="b875c-125">При выборе **Docker Compose**, Visual Studio добавляет раздел служб в своем решении *docker-compose.yml* файлы (или создает файлы, если они не существуют).</span><span class="sxs-lookup"><span data-stu-id="b875c-125">When you choose **Docker Compose**, Visual Studio adds a service section in your solution's *docker-compose.yml* files (or creates the files if they didn't exist).</span></span> <span data-ttu-id="b875c-126">Это простой способ начать создание многоконтейнерного решения; Затем можно открыть *docker-compose.yml* файлы и обновлять их с помощью дополнительных функций.</span><span class="sxs-lookup"><span data-stu-id="b875c-126">It's an easy way to begin composing your multi-container solution; you then can open the *docker-compose.yml* files and update them with additional features.</span></span>

<span data-ttu-id="b875c-127">Это действие добавляет требуемую конфигурацию строки кода для *docker-compose.yml* задать на уровне решения.</span><span class="sxs-lookup"><span data-stu-id="b875c-127">This action adds the required configuration lines of code to a *docker-compose.yml* set at the solution level.</span></span>

<span data-ttu-id="b875c-128">Также можно включить поддержку Docker при создании проекта ASP.NET Core в Visual Studio 2017, как показано на рисунке 4-27.</span><span class="sxs-lookup"><span data-stu-id="b875c-128">You also can turn on Docker support when creating an ASP.NET Core project in Visual Studio 2017, as shown in Figure 4-27.</span></span>

![Включение поддержки Docker при создании проекта](./media/image33.png)

<span data-ttu-id="b875c-130">Рис. 4-27: Включение поддержки Docker при создании проекта</span><span class="sxs-lookup"><span data-stu-id="b875c-130">Figure 4-27: Turning on Docker support when creating a project</span></span>

<span data-ttu-id="b875c-131">После добавления поддержки Docker в решение в Visual Studio, вы также увидите новый узел дерева на **обозревателе решений** путем добавления *docker-compose.yml* файлы, как показано на рис. 4-28.</span><span class="sxs-lookup"><span data-stu-id="b875c-131">After you add Docker support to your solution in Visual Studio, you also will see a new node tree in **Solution Explorer** with the added *docker-compose.yml* files, as depicted in Figure 4-28.</span></span>

![файлы docker-compose.yml, теперь отображаются в обозревателе решений](./media/image34.PNG)

<span data-ttu-id="b875c-133">Рис. 4-28: файлы docker-compose.yml отображаться **обозревателе решений**</span><span class="sxs-lookup"><span data-stu-id="b875c-133">Figure 4-28: docker-compose.yml files now display in **Solution Explorer**</span></span>

<span data-ttu-id="b875c-134">Можно развернуть многоконтейнерного приложения с помощью одной *docker-compose.yml* файл при запуске `docker-compose up`, однако Visual Studio добавляет группу серверов, чтобы вы могли переопределять значения в зависимости от среды (разработки или для рабочей среды) и введите (выпуска или отладки) выполнения.</span><span class="sxs-lookup"><span data-stu-id="b875c-134">You could deploy a multi-container app by using a single *docker-compose.yml* file when you run `docker-compose up`; however, Visual Studio adds a group of them, so you can override values depending on the environment (development versus production) and the execution type (release versus debug).</span></span> <span data-ttu-id="b875c-135">Эта возможность лучше описан в последующих главах.</span><span class="sxs-lookup"><span data-stu-id="b875c-135">This capability is better explained in later chapters.</span></span>

<span data-ttu-id="b875c-136">Можно также использовать Service Fabric вместо Docker Compose для управления несколькими контейнерами.</span><span class="sxs-lookup"><span data-stu-id="b875c-136">You can also use Service Fabric instead of Docker Compose to manage multiple containers.</span></span> <span data-ttu-id="b875c-137">См. в разделе [руководство: развертывание приложения .NET в контейнере Windows в Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-host-app-in-a-container).</span><span class="sxs-lookup"><span data-stu-id="b875c-137">See [Tutorial: Deploy a .NET application in a Windows container to Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-host-app-in-a-container).</span></span>

<span data-ttu-id="b875c-138">**Дополнительные сведения:** Дополнительные сведения о реализации служб и использование набора средств Visual Studio для Docker в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="b875c-138">**More info:** For further details on the services implementation and use of Visual Studio Tools for Docker, read the following articles:</span></span>

<span data-ttu-id="b875c-139">Сборки, отладки, обновления и обновления приложений в локальном контейнере Docker: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="b875c-139">Build, debug, update, and refresh apps in a local Docker container: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

<span data-ttu-id="b875c-140">Развертывание контейнера ASP.NET Core Docker в реестр контейнеров: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="b875c-140">Deploy an ASP.NET Core Docker container to a container registry: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="b875c-141">[Назад](docker-apps-inner-loop-workflow.md)
[Вперед](set-up-windows-containers-with-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="b875c-141">[Previous](docker-apps-inner-loop-workflow.md)
[Next](set-up-windows-containers-with-powershell.md)</span></span>
