---
title: "С помощью средств Visual Studio для Docker (Visual Studio в Windows)"
description: "Жизненный цикл приложений контейнерного Docker с помощью платформы Майкрософт и средств"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: d7a24633f5857bc5b72ebab42020627c645f4302
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2017
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a><span data-ttu-id="0bfb1-104">С помощью средств Visual Studio для Docker (Visual Studio в Windows)</span><span class="sxs-lookup"><span data-stu-id="0bfb1-104">Using Visual Studio Tools for Docker (Visual Studio on Windows)</span></span>

<span data-ttu-id="0bfb1-105">Разработчик рабочего процесса при использовании средств Visual Studio для Docker аналогична рабочего процесса при использовании кода Visual Studio и Docker CLI (на самом деле он основан на одном Docker CLI), но проще приступить к работе, упрощает процесс и предоставляет больше производительность для построения, запуска и создать задач.</span><span class="sxs-lookup"><span data-stu-id="0bfb1-105">The developer workflow when using Visual Studio Tools for Docker is similar to the workflow when using Visual Studio Code and Docker CLI (in fact, it is based on the same Docker CLI), but it is easier to get started, simplifies the process, and provides greater productivity for the build, run, and compose tasks.</span></span> <span data-ttu-id="0bfb1-106">Это также может выполнять и отлаживать вашей контейнеры через простые действия, такие как F5 или Ctrl + F5 в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0bfb1-106">It's also able to execute and debug your containers via simple actions like F5 and Ctrl+F5 from Visual Studio.</span></span> <span data-ttu-id="0bfb1-107">Еще более с Visual Studio 2017 г Помимо возможности позволяют выполнять и отлаживать в одном контейнере, можно также запустить и отладить группы контейнеров (всего решения) в то же время, если они определены в одном файле docker compose.yml на уровне решения.</span><span class="sxs-lookup"><span data-stu-id="0bfb1-107">Even more, with Visual Studio 2017, in addition to being able to run and debug a single container, you also can run and debug a group of containers (a whole solution) at the same time if they are defined in the same docker-compose.yml file at the solution level.</span></span>

## <a name="configuring-your-local-environment"></a><span data-ttu-id="0bfb1-108">Настройка локальной среде</span><span class="sxs-lookup"><span data-stu-id="0bfb1-108">Configuring your local environment</span></span>

<span data-ttu-id="0bfb1-109">С последними версиями Docker для Windows проще, чем когда-либо для разработки Docker приложений так, как настройка является простым, как описано в следующих документах.</span><span class="sxs-lookup"><span data-stu-id="0bfb1-109">With the latest versions of Docker for Windows, it is easier than ever to develop Docker applications because the setup is straightforward, as explained in the following references.</span></span>

<span data-ttu-id="0bfb1-110">**Дополнительные сведения:** Дополнительные сведения об установке Docker для Windows, перейдите к <https://docs.docker.com/docker-for-windows/>.</span><span class="sxs-lookup"><span data-stu-id="0bfb1-110">**More info:** To learn more about installing Docker for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>

<span data-ttu-id="0bfb1-111">Если вы используете Visual Studio 2015, необходимо иметь обновления 3 или более поздней версии, а также средств Visual Studio для Docker.</span><span class="sxs-lookup"><span data-stu-id="0bfb1-111">If you're using Visual Studio 2015, you must have Update 3 or a later version plus the Visual Studio Tools for Docker.</span></span>

<span data-ttu-id="0bfb1-112">**Дополнительные сведения:** инструкции по установке Visual Studio перейдите к [https://www.visualstudio.com/ \ продуктов или vs-2015--выпуски продукта](https://www.visualstudio.com/products/vs-2015-product-editions).</span><span class="sxs-lookup"><span data-stu-id="0bfb1-112">**More info:** For instructions on installing Visual Studio, go to [https://www.visualstudio.com/\ products/vs-2015-product-editions](https://www.visualstudio.com/products/vs-2015-product-editions).</span></span>

<span data-ttu-id="0bfb1-113">Для просмотра дополнительных сведений об установке набора средств Visual Studio для Docker, воспользуйтесь <http://aka.ms/vstoolsfordocker> и <https://docs.microsoft.com/dotnet/articles/core/docker/visual-studio-tools-for-docker>.</span><span class="sxs-lookup"><span data-stu-id="0bfb1-113">To see more about installing Visual Studio Tools for Docker, go to <http://aka.ms/vstoolsfordocker> and <https://docs.microsoft.com/dotnet/articles/core/docker/visual-studio-tools-for-docker>.</span></span>

<span data-ttu-id="0bfb1-114">Вы используете Visual Studio 2017 г., уже включена поддержка Docker.</span><span class="sxs-lookup"><span data-stu-id="0bfb1-114">If you're using Visual Studio 2017, Docker support is already included.</span></span>

## <a name="using-docker-tools-in-visual-studio-2015"></a><span data-ttu-id="0bfb1-115">С помощью средств Docker в Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="0bfb1-115">Using Docker Tools in Visual Studio 2015</span></span>

<span data-ttu-id="0bfb1-116">Средства Visual Studio для Docker предоставляет согласованный способ разработки и проверки локально в контейнеры Docker для Linux в узле Linux Docker или виртуальной Машины или в контейнеры Windows непосредственно в Windows.</span><span class="sxs-lookup"><span data-stu-id="0bfb1-116">The Visual Studio Tools for Docker provides a consistent way to develop and validate locally your Docker containers for Linux in a Linux Docker host or VM, or your Windows Containers directly on Windows.</span></span>

<span data-ttu-id="0bfb1-117">Если вы используете один контейнер, первое, что необходимо начать — включить поддержку Docker в проект .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0bfb1-117">If you're using a single container, the first thing you need to begin is to turn on Docker support into your .NET Core project.</span></span> <span data-ttu-id="0bfb1-118">Для этого щелкните правой кнопкой мыши файл проекта, как показано на рисунке 4 — 25.</span><span class="sxs-lookup"><span data-stu-id="0bfb1-118">To do this, right-click your project file, as shown in Figure 4-25.</span></span>

![https://I1.visualstudiogallery.MSDN.s-MSFT.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4/Image/File/205468/1/Add-docker-support.PNG](./media/image31.png)

<span data-ttu-id="0bfb1-120">На рисунке 4-25: Включение поддержки Docker для проекта Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0bfb1-120">Figure 4-25: Turning on Docker support for your Visual Studio project</span></span>

## <a name="using-docker-tools-in-visual-studio-2017"></a><span data-ttu-id="0bfb1-121">С помощью средств Docker в Visual Studio 2017 г.</span><span class="sxs-lookup"><span data-stu-id="0bfb1-121">Using Docker Tools in Visual Studio 2017</span></span>

<span data-ttu-id="0bfb1-122">При добавлении поддержки Docker в проект службы в решении (см. рис. 4-26), Visual Studio является не просто прибавляет файл DockerFile в проект, он также является добавление раздела службы в решения docker compose.yml файлы (или создании файлов, если они не существует).</span><span class="sxs-lookup"><span data-stu-id="0bfb1-122">When you add Docker support to a service project in your solution (see Figure 4-26), Visual Studio is not just adding a DockerFile file to your project, it also is adding a service section in your solution's docker-compose.yml files (or creating the files if they didn't exist).</span></span> <span data-ttu-id="0bfb1-123">Это простой способ начать составление multicontainer решения; Затем можно открыть файлы docker compose.yml и обновлять их с дополнительными возможностями.</span><span class="sxs-lookup"><span data-stu-id="0bfb1-123">It's an easy way to begin composing your multicontainer solution; you then can open the docker-compose.yml files and update them with additional features.</span></span>

![](./media/image32.png)

<span data-ttu-id="0bfb1-124">Рис. 4-26: Включение поддержки Docker решений в проекте Visual Studio 2017 г.</span><span class="sxs-lookup"><span data-stu-id="0bfb1-124">Figure 4-26: Turning on Docker Solution support in a Visual Studio 2017 project</span></span>

<span data-ttu-id="0bfb1-125">Это действие не только добавляет файл DockerFile в проект, он также добавляет необходимую настройку строки кода для глобальных docker-compose.yml задавать на уровне решения.</span><span class="sxs-lookup"><span data-stu-id="0bfb1-125">This action not only adds the DockerFile to your project, it also adds the required configuration lines of code to a global docker-compose.yml set at the solution level.</span></span>

<span data-ttu-id="0bfb1-126">Также можно включить поддержку Docker при создании проекта ASP.NET Core в Visual Studio 2017 г., как показано на рисунке 4-27.</span><span class="sxs-lookup"><span data-stu-id="0bfb1-126">You also can turn on Docker support when creating an ASP.NET Core project in Visual Studio 2017, as shown in Figure 4-27.</span></span>

![](./media/image33.png)

<span data-ttu-id="0bfb1-127">Рис. 4-27: Включение поддержки Docker при создании проекта</span><span class="sxs-lookup"><span data-stu-id="0bfb1-127">Figure 4-27: Turning on Docker support when creating a project</span></span>

<span data-ttu-id="0bfb1-128">После добавления поддержки Docker в решение в Visual Studio, вы также увидите нового узла дерева в обозревателе решений с файлами добавлены docker-compose.yml, как показано на рисунке 4-28.</span><span class="sxs-lookup"><span data-stu-id="0bfb1-128">After you add Docker support to your solution in Visual Studio, you also will see a new node tree in Solution Explorer with the added docker-compose.yml files, as depicted in Figure 4-28.</span></span>

![](./media/image34.PNG)

<span data-ttu-id="0bfb1-129">Рис. 4-28: файлы docker compose.yml теперь отображаются в обозревателе решений</span><span class="sxs-lookup"><span data-stu-id="0bfb1-129">Figure 4-28: docker-compose.yml files now display in Solution Explorer</span></span>

<span data-ttu-id="0bfb1-130">Можно развернуть multicontainer приложения с помощью файла одного docker-compose.yml при запуске docker составления вверх; Тем не менее, Visual Studio добавляет группу из них, можно изменить значения в зависимости от среды (разработки и производственной) и выполнения типа (выпуска и отладки).</span><span class="sxs-lookup"><span data-stu-id="0bfb1-130">You could deploy a multicontainer application by using a single docker-compose.yml file when you run docker-compose up; however, Visual Studio adds a group of them, so you can override values depending on the environment (development versus production) and the execution type (release versus debug).</span></span> <span data-ttu-id="0bfb1-131">Эта возможность лучше описывается в последующих главах.</span><span class="sxs-lookup"><span data-stu-id="0bfb1-131">This capability will be better explained in later chapters.</span></span>

<span data-ttu-id="0bfb1-132">**Дополнительные сведения:** для получения сведений о реализации службы и использовании средств Visual Studio для Docker в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="0bfb1-132">**More info:** For further details on the services implementation and use of Visual Studio Tools for Docker, read the following articles:</span></span>

<span data-ttu-id="0bfb1-133">Сборки, отладки, обновления и обновления приложений в локальном контейнере Docker: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="0bfb1-133">Build, debug, update, and refresh apps in a local Docker container: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

<span data-ttu-id="0bfb1-134">Разверните контейнер ASP.NET к удаленному узлу Docker: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="0bfb1-134">Deploy an ASP.NET container to a remote Docker host: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="0bfb1-135">[Предыдущие] (docker приложения внутреннее loop-workflow.md) [Далее] (set-up-windows-containers-with-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="0bfb1-135">[Previous] (docker-apps-inner-loop-workflow.md) [Next] (set-up-windows-containers-with-powershell.md)</span></span>
