---
title: "Среда разработки приложений Docker"
description: "Жизненный цикл приложений контейнерного Docker с помощью платформы Майкрософт и средств"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: eedba16136ad394bda45cc871944f9b876c8ee38
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2017
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="f31af-104">Среда разработки приложений Docker</span><span class="sxs-lookup"><span data-stu-id="f31af-104">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="f31af-105">Выбор средства разработки: IDE или редактора</span><span class="sxs-lookup"><span data-stu-id="f31af-105">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="f31af-106">Независимо от при желании полные и мощные IDE или редактора упрощенных и гибкой, корпорация Майкрософт вас когда речь заходит о разработке приложений Docker.</span><span class="sxs-lookup"><span data-stu-id="f31af-106">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="f31af-107">Visual Studio Code и Docker CLI (кросс платформенных инструменты для Mac, Linux и Windows)</span><span class="sxs-lookup"><span data-stu-id="f31af-107">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="f31af-108">Если вы предпочитаете упрощенный, кросс платформенных редактора, поддержка любой язык разработки, можно использовать кода Visual Studio и Docker CLI.</span><span class="sxs-lookup"><span data-stu-id="f31af-108">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="f31af-109">Эти продукты обеспечивают простой и надежной работы, которая необходима для оптимизации разработчика рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f31af-109">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="f31af-110">Установив «Docker для Mac» или «Docker для Windows» (среда разработки), Docker позволяют разработчикам один Docker CLI для создания приложений для Windows или Linux (среда выполнения).</span><span class="sxs-lookup"><span data-stu-id="f31af-110">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="f31af-111">Кроме того, код Visual Studio поддерживает расширения для Docker с поддержкой технологии IntelliSense для файлов Dockerfile и ярлык задачи для выполнения команд Docker из редактора.</span><span class="sxs-lookup"><span data-stu-id="f31af-111">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
> <span data-ttu-id="f31af-112">Чтобы загрузить кода Visual Studio, перейдите на <https://code.visualstudio.com/download>.</span><span class="sxs-lookup"><span data-stu-id="f31af-112">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>

<span data-ttu-id="f31af-113">Чтобы загрузить Docker для Mac и Windows, перейдите к <http://www.docker.com/products/docker>.</span><span class="sxs-lookup"><span data-stu-id="f31af-113">To download Docker for Mac and Windows, go to <http://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools"></a><span data-ttu-id="f31af-114">Visual Studio с помощью средств Docker</span><span class="sxs-lookup"><span data-stu-id="f31af-114">Visual Studio with Docker Tools</span></span>

<span data-ttu-id="f31af-115">Если вы используете Visual Studio 2015 можно установить дополнительные средства «Docker средства для Visual Studio».</span><span class="sxs-lookup"><span data-stu-id="f31af-115">When you're using Visual Studio 2015 you can install the add-on tools "Docker Tools for Visual Studio."</span></span> <span data-ttu-id="f31af-116">Для Visual Studio 2017 г., Docker средства, предоставляемые встроенной уже.</span><span class="sxs-lookup"><span data-stu-id="f31af-116">For Visual Studio 2017, Docker Tools come built in already.</span></span> <span data-ttu-id="f31af-117">В обоих случаях можно разрабатывать, запуска и проверки приложения непосредственно в выбранной среде Docker.</span><span class="sxs-lookup"><span data-stu-id="f31af-117">In both cases you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="f31af-118">F5 приложения (один контейнер или несколько контейнеров) непосредственно в Docker разместить с отладкой, либо нажмите клавиши Ctrl + F5, чтобы изменить и обновить приложение без необходимости перестроения контейнера.</span><span class="sxs-lookup"><span data-stu-id="f31af-118">F5 your application (single container or multiple containers) directly into a Docker host with debugging, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="f31af-119">Это простой и расширенные возможности для разработчиков Windows, создание контейнеров Docker для Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="f31af-119">This is the simplest and more powerful choice for Windows developers creating Docker containers for Linux or Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="f31af-120">Чтобы загрузить набор средств Docker для Visual Studio, перейдите на <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span><span class="sxs-lookup"><span data-stu-id="f31af-120">To download Docker Tools for Visual Studio, go to <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="f31af-121">Выбор языка и платформы</span><span class="sxs-lookup"><span data-stu-id="f31af-121">Language and framework choices</span></span>

<span data-ttu-id="f31af-122">Можно разрабатывать приложения Docker и средства Microsoft с наиболее современные языки.</span><span class="sxs-lookup"><span data-stu-id="f31af-122">You can develop Docker applications and Microsoft tools with most modern languages.</span></span> <span data-ttu-id="f31af-123">Ниже приведен исходный список, но вы не ограничены его:</span><span class="sxs-lookup"><span data-stu-id="f31af-123">The following is an initial list, but you are not limited to it:</span></span>

-   <span data-ttu-id="f31af-124">.NET core и ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f31af-124">.NET Core and ASP.NET Core</span></span>

-   <span data-ttu-id="f31af-125">Node.js</span><span class="sxs-lookup"><span data-stu-id="f31af-125">Node.js</span></span>

-   <span data-ttu-id="f31af-126">Golang</span><span class="sxs-lookup"><span data-stu-id="f31af-126">Golang</span></span>

-   <span data-ttu-id="f31af-127">Java</span><span class="sxs-lookup"><span data-stu-id="f31af-127">Java</span></span>

-   <span data-ttu-id="f31af-128">Ruby</span><span class="sxs-lookup"><span data-stu-id="f31af-128">Ruby</span></span>

-   <span data-ttu-id="f31af-129">Python</span><span class="sxs-lookup"><span data-stu-id="f31af-129">Python</span></span>

<span data-ttu-id="f31af-130">По сути можно использовать любой современный язык, поддерживаемый Docker в Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="f31af-130">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="f31af-131">[Предыдущие] (координировать высокой масштабируемость availability.md) [Далее] (docker приложения внутреннее loop-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="f31af-131">[Previous] (orchestrate-high-scalability-availability.md) [Next] (docker-apps-inner-loop-workflow.md)</span></span>
