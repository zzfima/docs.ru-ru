---
title: "Процесс разработки для приложений на основе Docker"
description: "Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Процесс разработки для приложений на основе Docker"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 97dfa3261c8ddc7a869b0991673b7a8d298972dd
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="development-process-for-docker-based-applications"></a><span data-ttu-id="2d9de-104">Процесс разработки для приложений на основе Docker</span><span class="sxs-lookup"><span data-stu-id="2d9de-104">Development Process for Docker-Based Applications</span></span>

<span data-ttu-id="2d9de-105">*Вы можете разрабатывать контейнерные приложения .NET так, как вам нравится: либо с помощью интегрированной среды разработки (IDE) Visual Studio и Средств Visual Studio для Docker, либо с помощью интерфейса командной строки (CLI) и редактора — CLI Docker и Visual Studio Code.*</span><span class="sxs-lookup"><span data-stu-id="2d9de-105">*Develop containerized .NET applications the way you like, either IDE focused with Visual Studio and Visual Studio tools for Docker or CLI/Editor focused with Docker CLI and Visual Studio Code.*</span></span>

## <a name="development-environment-for-docker-apps"></a><span data-ttu-id="2d9de-106">Среда разработки приложений Docker</span><span class="sxs-lookup"><span data-stu-id="2d9de-106">Development environment for Docker apps</span></span>

### <a name="development-tool-choices-ide-or-editor"></a><span data-ttu-id="2d9de-107">Выбор средства разработки: IDE или редактор</span><span class="sxs-lookup"><span data-stu-id="2d9de-107">Development tool choices: IDE or editor</span></span>

<span data-ttu-id="2d9de-108">Предпочитаете ли вы использовать полнофункциональную среду IDE или упрощенный редактор, корпорация Майкрософт предлагает средства, с помощью которых можно разрабатывать приложения Docker.</span><span class="sxs-lookup"><span data-stu-id="2d9de-108">Whether you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has tools that you can use for developing Docker applications.</span></span>

<span data-ttu-id="2d9de-109">**Visual Studio (для Windows)**.</span><span class="sxs-lookup"><span data-stu-id="2d9de-109">**Visual Studio (for Windows)**.</span></span> <span data-ttu-id="2d9de-110">Для разработки приложений на основе Docker используйте Visual Studio 2017 или более поздние версии, в которые уже встроены средства для Docker.</span><span class="sxs-lookup"><span data-stu-id="2d9de-110">To develop Docker-based applications, use Visual Studio 2017 or later versions that comes with tools for Docker already built-in.</span></span> <span data-ttu-id="2d9de-111">Средства для Docker позволяют разрабатывать, запускать и проверять приложения непосредственно в целевой среде Docker.</span><span class="sxs-lookup"><span data-stu-id="2d9de-111">The tools for Docker let you develop, run, and validate your applications directly in the target Docker environment.</span></span> <span data-ttu-id="2d9de-112">Нажмите клавишу F5 для запуска и отладки приложения (на основе одного контейнера или нескольких) непосредственно в узле Docker или нажмите клавиши CTRL+F5 для редактирования и обновления приложения без повторной сборки контейнера.</span><span class="sxs-lookup"><span data-stu-id="2d9de-112">You can press F5 to run and debug your application (single container or multiple containers) directly into a Docker host, or press CTRL+F5 to edit and refresh your application without having to rebuild the container.</span></span> <span data-ttu-id="2d9de-113">Это самый эффективный вариант разработки приложений на основе Docker.</span><span class="sxs-lookup"><span data-stu-id="2d9de-113">This is the most powerful development choice for Docker-based apps.</span></span>

<span data-ttu-id="2d9de-114">**Visual Studio для Mac**.</span><span class="sxs-lookup"><span data-stu-id="2d9de-114">**Visual Studio for Mac**.</span></span> <span data-ttu-id="2d9de-115">Это интегрированная среда разработки, которая является эволюцией Xamarin Studio, выполняется в macOS и поддерживает разработку приложений на основе Docker.</span><span class="sxs-lookup"><span data-stu-id="2d9de-115">It is an IDE, evolution of Xamarin Studio, that runs on macOS and supports Docker-based application development.</span></span> <span data-ttu-id="2d9de-116">Она должна быть предпочтительным вариантом для разработчиков, работающих на компьютерах Mac и стремящихся использовать мощную интегрированную среду разработки.</span><span class="sxs-lookup"><span data-stu-id="2d9de-116">This should be the preferred choice for developers working in Mac machines who also want to use a powerful IDE.</span></span>

<span data-ttu-id="2d9de-117">**Visual Studio Code и CLI Docker**.</span><span class="sxs-lookup"><span data-stu-id="2d9de-117">**Visual Studio Code and Docker CLI**.</span></span> <span data-ttu-id="2d9de-118">Если вам нужен упрощенный кроссплатформенный редактор, поддерживающий любой язык программирования, то вы можете использовать Microsoft Visual Studio Code (VS Code) и CLI Docker.</span><span class="sxs-lookup"><span data-stu-id="2d9de-118">If you prefer a lightweight and cross-platform editor that supports any development language, you can use Microsoft Visual Studio Code (VS Code) and the Docker CLI.</span></span> <span data-ttu-id="2d9de-119">Таким образом реализуется кроссплатформенный подход к разработке приложений для Mac OS, Linux и Windows.</span><span class="sxs-lookup"><span data-stu-id="2d9de-119">This is a cross-platform development approach for Mac, Linux, and Windows.</span></span>

<span data-ttu-id="2d9de-120">Установив средства [Docker Community Edition (CE)](https://www.docker.com/community-edition), вы можете использовать единый интерфейс CLI Docker, чтобы создавать приложения как для Windows, так и для Linux.</span><span class="sxs-lookup"><span data-stu-id="2d9de-120">By installing [Docker Community Edition (CE)](https://www.docker.com/community-edition) tools, you can use a single Docker CLI to build apps for both Windows and Linux.</span></span> <span data-ttu-id="2d9de-121">Кроме того, Visual Studio Code поддерживает расширения для Docker, такие как IntelliSense для Dockerfile, и ярлыки для выполнения команд Docker из редактора.</span><span class="sxs-lookup"><span data-stu-id="2d9de-121">Additionally, Visual Studio Code supports extensions for Docker such as IntelliSense for Dockerfiles and shortcut tasks to run Docker commands from the editor.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="2d9de-122">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="2d9de-122">Additional resources</span></span>

-   <span data-ttu-id="2d9de-123">**Средства Visual Studio для Docker**
    [*https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker*](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)</span><span class="sxs-lookup"><span data-stu-id="2d9de-123">**Visual Studio Tools for Docker**
[*https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker*](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)</span></span>

-   <span data-ttu-id="2d9de-124">**Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="2d9de-124">**Visual Studio Code**.</span></span> <span data-ttu-id="2d9de-125">Официальный сайт</span><span class="sxs-lookup"><span data-stu-id="2d9de-125">Official site.</span></span>
    [<span data-ttu-id="2d9de-126">*https://code.visualstudio.com/download*</span><span class="sxs-lookup"><span data-stu-id="2d9de-126">*https://code.visualstudio.com/download*</span></span>](https://code.visualstudio.com/download)

-   <span data-ttu-id="2d9de-127">**Docker Community Edition (CE) для Mac и Windows**
    [*https://www.docker.com/community-editions*](https://www.docker.com/community-edition)</span><span class="sxs-lookup"><span data-stu-id="2d9de-127">**Docker Community Edition (CE) for Mac and Windows**
[*https://www.docker.com/community-editions*](https://www.docker.com/community-edition)</span></span>

## <a name="net-languages-and-frameworks-for-docker-containers"></a><span data-ttu-id="2d9de-128">Языки и платформы .NET для контейнеров Docker</span><span class="sxs-lookup"><span data-stu-id="2d9de-128">.NET languages and frameworks for Docker containers</span></span>

<span data-ttu-id="2d9de-129">Как уже упоминалось в предыдущих разделах этого руководства, при разработке приложений .NET, помещенных в контейнеры Docker, можно использовать .NET Framework, .NET Core или проект Mono с открытым кодом.</span><span class="sxs-lookup"><span data-stu-id="2d9de-129">As mentioned in earlier sections of this guide, you can use .NET Framework, .NET Core, or the open-source Mono project when developing Docker containerized .NET applications.</span></span> <span data-ttu-id="2d9de-130">При разработке приложений на основе контейнеров Linux или Windows можно использовать язык C\#, F\# или Visual Basic в зависимости от применяемой платформы .NET.</span><span class="sxs-lookup"><span data-stu-id="2d9de-130">You can develop in C\#, F\#, or Visual Basic when targeting Linux or Windows Containers, depending on which .NET framework is in use.</span></span> <span data-ttu-id="2d9de-131">Дополнительные сведения о языках .NET см. в записи блога [Стратегия .NET в отношении языков](https://blogs.msdn.microsoft.com/dotnet/2017/02/01/the-net-language-strategy/).</span><span class="sxs-lookup"><span data-stu-id="2d9de-131">For more details about.NET languages, see the blog post [The .NET Language Strategy](https://blogs.msdn.microsoft.com/dotnet/2017/02/01/the-net-language-strategy/).</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="2d9de-132">[Назад] (../architect-microservice-container-applications/using-azure-service-fabric.md) [Далее] (docker-app-development-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="2d9de-132">[Previous] (../architect-microservice-container-applications/using-azure-service-fabric.md) [Next] (docker-app-development-workflow.md)</span></span>
