---
title: Visual Studio Tools for Docker в Windows
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/12/2018
ms.custom: vs-dotnet
ms.openlocfilehash: cd140c12ef4a0187cce096e013937d5c98cd4b39
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47235719"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a><span data-ttu-id="76375-103">С помощью средств Visual Studio для Docker (Visual Studio в Windows)</span><span class="sxs-lookup"><span data-stu-id="76375-103">Using Visual Studio Tools for Docker (Visual Studio on Windows)</span></span>

<span data-ttu-id="76375-104">Visual Studio Tools для рабочий процесс разработки Docker похоже на использование Visual Studio Code и Docker CLI (он основан на том же Docker CLI).</span><span class="sxs-lookup"><span data-stu-id="76375-104">The Visual Studio Tools for Docker developer workflow is similar to using Visual Studio Code and Docker CLI (it is based on the same Docker CLI).</span></span> <span data-ttu-id="76375-105">Средства Visual Studio для Docker даже упрощает начало работы, упрощает процесс и обеспечивает повышение производительности для сборки, запуска и объединять задач.</span><span class="sxs-lookup"><span data-stu-id="76375-105">Visual Studio Tools for Docker makes it even easier to get started, simplifies the process, and provides greater productivity for the build, run, and compose tasks.</span></span> <span data-ttu-id="76375-106">Выполнение и отладка контейнеров с помощью простых действий, таких как **F5** и **Ctrl**+**F5**.</span><span class="sxs-lookup"><span data-stu-id="76375-106">Execute and debug your containers via simple actions like **F5** and **Ctrl**+**F5**.</span></span>

> [!NOTE]
> <span data-ttu-id="76375-107">Эта статья относится к Visual Studio в Windows, а не в Visual Studio для Mac.</span><span class="sxs-lookup"><span data-stu-id="76375-107">This article applies to Visual Studio on Windows, and not Visual Studio for Mac.</span></span>

## <a name="configure-your-local-environment"></a><span data-ttu-id="76375-108">Настройка локальной среды</span><span class="sxs-lookup"><span data-stu-id="76375-108">Configure your local environment</span></span>

<span data-ttu-id="76375-109">В последних версиях Docker для Windows ([https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/)), простой настройки упрощает процесс разработки приложений Docker.</span><span class="sxs-lookup"><span data-stu-id="76375-109">With the latest versions of Docker for Windows ([https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/)), the straightforward setup makes it easy to develop Docker applications.</span></span>

<span data-ttu-id="76375-110">Поддержка docker включена в Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="76375-110">Docker support is included in Visual Studio 2017.</span></span> <span data-ttu-id="76375-111">Ссылка для загрузки Visual Studio 2017: [https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)</span><span class="sxs-lookup"><span data-stu-id="76375-111">Download Visual Studio 2017 here: [https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)</span></span>

## <a name="use-docker-tools-in-visual-studio-2017"></a><span data-ttu-id="76375-112">С помощью средств Docker в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="76375-112">Use Docker Tools in Visual Studio 2017</span></span>

<span data-ttu-id="76375-113">Существует два уровня поддержки Docker, который можно добавить в проект.</span><span class="sxs-lookup"><span data-stu-id="76375-113">There are two levels of Docker support you can add to a project.</span></span> <span data-ttu-id="76375-114">В веб-приложения .NET Core проектов, можно просто добавить *Dockerfile* файл в проект, включение поддержки Docker.</span><span class="sxs-lookup"><span data-stu-id="76375-114">In .NET Core web app projects, you can just add a *Dockerfile* file to the project by enabling Docker support.</span></span> <span data-ttu-id="76375-115">На следующем уровне находится поддержки оркестратора контейнеров, который добавляет *Dockerfile* в проект (если он еще не существует) и *docker-compose.yml* файл на уровне решения.</span><span class="sxs-lookup"><span data-stu-id="76375-115">The next level is container orchestrator support, which adds a *Dockerfile* to the project (if it doesn't already exist) and a *docker-compose.yml* file at the solution level.</span></span>

<span data-ttu-id="76375-116">**Добавить** > **поддержку Docker** и **добавить** > **поддержки оркестратора контейнеров** команды находятся в контекстном меню (или контекстное меню) из узла проекта для проекта веб-приложения в **обозревателе решений**, как показано на рисунке 4-26:</span><span class="sxs-lookup"><span data-stu-id="76375-116">The **Add** > **Docker Support** and **Add** > **Container Orchestrator Support** commands are located on the right-click menu (or context menu) of the project node for a web app project in **Solution Explorer**, as shown in Figure 4-26:</span></span>

![Добавить поддержку Docker команду меню в Visual Studio](media/add-docker-support-menu.png)

<span data-ttu-id="76375-118">Рис. 4-26: Добавление поддержки Docker в проект Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="76375-118">Figure 4-26: Adding Docker support to a Visual Studio 2017 project</span></span>

### <a name="add-docker-support"></a><span data-ttu-id="76375-119">Добавление поддержки Docker</span><span class="sxs-lookup"><span data-stu-id="76375-119">Add Docker support</span></span>

<span data-ttu-id="76375-120">Можно добавить поддержку Docker в существующий проект веб-приложения .NET Core, выбрав **добавить** > **Docker поддерживает** в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="76375-120">You can add Docker support to an existing .NET Core web app project by selecting **Add** > **Docker Support** in **Solution Explorer**.</span></span> <span data-ttu-id="76375-121">Можно также включить поддержку Docker во время создания проекта, выбрав **Включение поддержки Docker** в **новый веб-приложение ASP.NET Core** диалоговое окно, которое открывается при нажатии **ОК** в **новый проект** диалоговое окно, как показано на рисунке 4-27.</span><span class="sxs-lookup"><span data-stu-id="76375-121">You can also enable Docker support during project creation by selecting **Enable Docker Support** in the **New ASP.NET Core Web Application** dialog box that opens after you click **OK** in the **New Project** dialog box, as shown in Figure 4-27.</span></span>

![Включить поддержку Docker для нового веб-приложения ASP.NET Core в Visual Studio](./media/enable-docker-support-visual-studio.png)

<span data-ttu-id="76375-123">Рис. 4-27: Включение поддержки Docker во время создания проекта в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="76375-123">Figure 4-27: Enable Docker support during project creation in Visual Studio 2017</span></span>

<span data-ttu-id="76375-124">При добавлении или включить поддержку Docker, Visual Studio добавляет *Dockerfile* файл в проект.</span><span class="sxs-lookup"><span data-stu-id="76375-124">When you add or enable Docker support, Visual Studio adds a *Dockerfile* file to the project.</span></span>

> [!NOTE]
> <span data-ttu-id="76375-125">Когда вы включаете поддержку Docker Compose во время создания проекта для проект веб-приложения .NET Framework (не .NET Core проект веб-приложения), как показано на рис. 4-28, также добавляется поддержка оркестратора контейнеров.</span><span class="sxs-lookup"><span data-stu-id="76375-125">When you enable Docker Compose support during project creation for a .NET Framework web app project (not a .NET Core web app project) as shown in Figure 4-28, container orchestrator support is also added.</span></span>
>
> ![Включить Docker compose поддержка проект веб-приложения .NET Framework](media/enable-docker-compose-support.png)

> <span data-ttu-id="76375-127">Рис. 4-28: Включение поддержки Docker Compose на веб-приложения .NET Framework проекта в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="76375-127">Figure 4-28: Enabling Docker Compose support on a .NET Framework web app project in Visual Studio 2017</span></span>

### <a name="add-container-orchestrator-support"></a><span data-ttu-id="76375-128">Добавление поддержки оркестратора контейнеров</span><span class="sxs-lookup"><span data-stu-id="76375-128">Add container orchestrator support</span></span>

<span data-ttu-id="76375-129">При необходимости для составления многоконтейнерного решения, добавление поддержки оркестратора контейнеров к проектам.</span><span class="sxs-lookup"><span data-stu-id="76375-129">When you want to compose a multicontainer solution, add container orchestrator support to your projects.</span></span> <span data-ttu-id="76375-130">При добавлении поддержки оркестратора контейнеров, Visual Studio добавляет *Dockerfile* к проекту (если он еще не существует), глобальный *docker-compose.yml* файл на уровне решения.</span><span class="sxs-lookup"><span data-stu-id="76375-130">When you add container orchestrator support, Visual Studio adds a *Dockerfile* to the project (if it doesn't already exist) and a global *docker-compose.yml* file at the solution level.</span></span> <span data-ttu-id="76375-131">Это позволяет выполнять и отлаживать группу контейнеров (всего решения) в то же время, если они определяются в том же *docker-compose.yml* файл.</span><span class="sxs-lookup"><span data-stu-id="76375-131">This lets you run and debug a group of containers (a whole solution) at the same time if they're defined in the same *docker-compose.yml* file.</span></span> <span data-ttu-id="76375-132">Если *docker-compose.yml* уже существует, Visual Studio просто добавляет необходимые строки кода конфигурации к нему.</span><span class="sxs-lookup"><span data-stu-id="76375-132">If *docker-compose.yml* already exists, Visual Studio just adds the required lines of configuration code to it.</span></span>

<span data-ttu-id="76375-133">После добавления поддержки оркестрации контейнера в проект, вы видите добавлен в проект файл Dockerfile и **docker-compose** папка добавлена в решение в **обозревателе решений**, как показано на рис. 4-29:</span><span class="sxs-lookup"><span data-stu-id="76375-133">After you add container orchestration support to your project, you see a Dockerfile added to the project and a **docker-compose** folder added to the solution in **Solution Explorer**, as shown in Figure 4-29:</span></span>

![Файлы docker в обозревателе решений в Visual Studio](media/docker-support-solution-explorer.png)

<span data-ttu-id="76375-135">Рис. 4-29: файлы Docker в обозревателе решений в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="76375-135">Figure 4-29: Docker files in Solution Explorer in Visual Studio 2017</span></span>

<span data-ttu-id="76375-136">**Дополнительные сведения:** Дополнительные сведения о реализации служб и использование набора средств Visual Studio для Docker в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="76375-136">**More information:** For further details on the services implementation and use of Visual Studio Tools for Docker, read the following articles:</span></span>

<span data-ttu-id="76375-137">Сборки, отладки, обновления и обновления приложений в локальном контейнере Docker: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="76375-137">Build, debug, update, and refresh apps in a local Docker container: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

<span data-ttu-id="76375-138">Развертывание контейнера ASP.NET Core Docker в реестр контейнеров: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="76375-138">Deploy an ASP.NET Core Docker container to a container registry: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="76375-139">[Назад](docker-apps-inner-loop-workflow.md)
[Вперед](set-up-windows-containers-with-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="76375-139">[Previous](docker-apps-inner-loop-workflow.md)
[Next](set-up-windows-containers-with-powershell.md)</span></span>