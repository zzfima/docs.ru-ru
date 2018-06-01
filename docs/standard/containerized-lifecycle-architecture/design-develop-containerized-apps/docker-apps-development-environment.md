---
title: Среда разработки приложений Docker
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 4adbdd7099dfc1c5ef13d5bbb4370ae2f14aba1e
ms.sourcegitcommit: 3540f614fc94f77ca4ab58df66db2d0f4d52dfee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2018
ms.locfileid: "34696784"
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="5e4b2-103">Среда разработки приложений Docker</span><span class="sxs-lookup"><span data-stu-id="5e4b2-103">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="5e4b2-104">Выбор средства разработки: IDE или редактор</span><span class="sxs-lookup"><span data-stu-id="5e4b2-104">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="5e4b2-105">Независимо от при желании полные и мощные IDE или редактора упрощенных и гибкой, корпорация Майкрософт вас когда речь заходит о разработке приложений Docker.</span><span class="sxs-lookup"><span data-stu-id="5e4b2-105">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="5e4b2-106">Visual Studio Code и Docker CLI (кросс платформенных инструменты для Mac, Linux и Windows)</span><span class="sxs-lookup"><span data-stu-id="5e4b2-106">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="5e4b2-107">Если вы предпочитаете упрощенный, кросс платформенных редактора, поддержка любой язык разработки, можно использовать кода Visual Studio и Docker CLI.</span><span class="sxs-lookup"><span data-stu-id="5e4b2-107">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="5e4b2-108">Эти продукты обеспечивают простой и надежной работы, которая необходима для оптимизации разработчика рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="5e4b2-108">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="5e4b2-109">Установив «Docker для Mac» или «Docker для Windows» (среда разработки), Docker позволяют разработчикам один Docker CLI для создания приложений для Windows или Linux (среда выполнения).</span><span class="sxs-lookup"><span data-stu-id="5e4b2-109">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="5e4b2-110">Кроме того, код Visual Studio поддерживает расширения для Docker с поддержкой технологии IntelliSense для файлов Dockerfile и ярлык задачи для выполнения команд Docker из редактора.</span><span class="sxs-lookup"><span data-stu-id="5e4b2-110">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
> <span data-ttu-id="5e4b2-111">Чтобы загрузить кода Visual Studio, перейдите на <https://code.visualstudio.com/download>.</span><span class="sxs-lookup"><span data-stu-id="5e4b2-111">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>

<span data-ttu-id="5e4b2-112">Чтобы загрузить Docker для Mac и Windows, перейдите к <https://www.docker.com/products/docker>.</span><span class="sxs-lookup"><span data-stu-id="5e4b2-112">To download Docker for Mac and Windows, go to <https://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools"></a><span data-ttu-id="5e4b2-113">Visual Studio с помощью средств Docker</span><span class="sxs-lookup"><span data-stu-id="5e4b2-113">Visual Studio with Docker Tools</span></span>

<span data-ttu-id="5e4b2-114">Если вы используете Visual Studio 2015 можно установить дополнительные средства «Docker средства для Visual Studio».</span><span class="sxs-lookup"><span data-stu-id="5e4b2-114">When you're using Visual Studio 2015 you can install the add-on tools "Docker Tools for Visual Studio."</span></span> <span data-ttu-id="5e4b2-115">Для Visual Studio 2017 г., Docker средства, предоставляемые встроенной уже.</span><span class="sxs-lookup"><span data-stu-id="5e4b2-115">For Visual Studio 2017, Docker Tools come built in already.</span></span> <span data-ttu-id="5e4b2-116">В обоих случаях можно разрабатывать, запуска и проверки приложения непосредственно в выбранной среде Docker.</span><span class="sxs-lookup"><span data-stu-id="5e4b2-116">In both cases you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="5e4b2-117">F5 приложения (один контейнер или несколько контейнеров) непосредственно в Docker разместить с отладкой, либо нажмите клавиши Ctrl + F5, чтобы изменить и обновить приложение без необходимости перестроения контейнера.</span><span class="sxs-lookup"><span data-stu-id="5e4b2-117">F5 your application (single container or multiple containers) directly into a Docker host with debugging, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="5e4b2-118">Это простой и расширенные возможности для разработчиков Windows, создание контейнеров Docker для Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="5e4b2-118">This is the simplest and more powerful choice for Windows developers creating Docker containers for Linux or Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="5e4b2-119">Чтобы загрузить набор средств Docker для Visual Studio, перейдите на <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span><span class="sxs-lookup"><span data-stu-id="5e4b2-119">To download Docker Tools for Visual Studio, go to <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="5e4b2-120">Выбор языка и платформы</span><span class="sxs-lookup"><span data-stu-id="5e4b2-120">Language and framework choices</span></span>

<span data-ttu-id="5e4b2-121">Можно разрабатывать приложения Docker и средства Microsoft с наиболее современные языки.</span><span class="sxs-lookup"><span data-stu-id="5e4b2-121">You can develop Docker applications and Microsoft tools with most modern languages.</span></span> <span data-ttu-id="5e4b2-122">Ниже приведен исходный список, но вы не ограничены его:</span><span class="sxs-lookup"><span data-stu-id="5e4b2-122">The following is an initial list, but you are not limited to it:</span></span>

-   <span data-ttu-id="5e4b2-123">.NET core и ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5e4b2-123">.NET Core and ASP.NET Core</span></span>
-   <span data-ttu-id="5e4b2-124">Node.js</span><span class="sxs-lookup"><span data-stu-id="5e4b2-124">Node.js</span></span>
-   <span data-ttu-id="5e4b2-125">Golang</span><span class="sxs-lookup"><span data-stu-id="5e4b2-125">Golang</span></span>
-   <span data-ttu-id="5e4b2-126">Java</span><span class="sxs-lookup"><span data-stu-id="5e4b2-126">Java</span></span>
-   <span data-ttu-id="5e4b2-127">Ruby</span><span class="sxs-lookup"><span data-stu-id="5e4b2-127">Ruby</span></span>
-   <span data-ttu-id="5e4b2-128">Python</span><span class="sxs-lookup"><span data-stu-id="5e4b2-128">Python</span></span>

<span data-ttu-id="5e4b2-129">По сути можно использовать любой современный язык, поддерживаемый Docker в Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="5e4b2-129">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="5e4b2-130">[Предыдущие] (координировать высокой масштабируемость availability.md) [Далее] (docker приложения внутреннее loop-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5e4b2-130">[Previous] (orchestrate-high-scalability-availability.md) [Next] (docker-apps-inner-loop-workflow.md)</span></span>
