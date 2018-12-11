---
title: Среда разработки приложений Docker
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 471b52fd577e5560bd93e6da50f2032d63eb2e6f
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152420"
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="4a496-103">Среда разработки приложений Docker</span><span class="sxs-lookup"><span data-stu-id="4a496-103">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="4a496-104">Выбор средства разработки: Интегрированная среда разработки или редактор</span><span class="sxs-lookup"><span data-stu-id="4a496-104">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="4a496-105">Независимо от того, если вы предпочитаете полнофункциональную среду IDE или упрощенный редактор, корпорация Майкрософт предлагает вам рассматриваются, когда дело доходит до разработки приложений Docker.</span><span class="sxs-lookup"><span data-stu-id="4a496-105">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="4a496-106">Visual Studio Code и CLI Docker (кросс платформенные средства для Mac, Linux и Windows)</span><span class="sxs-lookup"><span data-stu-id="4a496-106">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="4a496-107">Если вам нужен упрощенный, кросс платформенных редактор, поддерживающий любой язык программирования, можно использовать Visual Studio Code и Docker CLI.</span><span class="sxs-lookup"><span data-stu-id="4a496-107">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="4a496-108">Эти решения обеспечивают простой и надежной, что очень важно для оптимизации рабочий процесс разработки.</span><span class="sxs-lookup"><span data-stu-id="4a496-108">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="4a496-109">Установив «Docker для Mac» или «Docker для Windows» (среда разработки), разработчики Docker можно использовать единый интерфейс CLI Docker для создания приложений для Windows или Linux (среду выполнения).</span><span class="sxs-lookup"><span data-stu-id="4a496-109">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="4a496-110">Кроме того, Visual Studio Code поддерживает расширения для Docker с поддержкой технологии IntelliSense для файлов Dockerfile и ярлыками задач для выполнения команд Docker из редактора.</span><span class="sxs-lookup"><span data-stu-id="4a496-110">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
> <span data-ttu-id="4a496-111">Чтобы скачать Visual Studio Code, перейдите к <https://code.visualstudio.com/download>.</span><span class="sxs-lookup"><span data-stu-id="4a496-111">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>

<span data-ttu-id="4a496-112">Чтобы скачать Docker для Mac и Windows, перейдите к <https://www.docker.com/products/docker>.</span><span class="sxs-lookup"><span data-stu-id="4a496-112">To download Docker for Mac and Windows, go to <https://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools"></a><span data-ttu-id="4a496-113">Visual Studio с помощью средств Docker</span><span class="sxs-lookup"><span data-stu-id="4a496-113">Visual Studio with Docker Tools</span></span>

<span data-ttu-id="4a496-114">При использовании Visual Studio 2015 можно установить дополнительные средства «Docker Tools for Visual Studio».</span><span class="sxs-lookup"><span data-stu-id="4a496-114">When you're using Visual Studio 2015 you can install the add-on tools "Docker Tools for Visual Studio."</span></span> <span data-ttu-id="4a496-115">Для Visual Studio 2017 средства Docker предоставляются вместе с используемыми в уже.</span><span class="sxs-lookup"><span data-stu-id="4a496-115">For Visual Studio 2017, Docker Tools come built in already.</span></span> <span data-ttu-id="4a496-116">В обоих случаях, которые можно разрабатывать запускать и проверять приложения непосредственно в выбранной среде Docker.</span><span class="sxs-lookup"><span data-stu-id="4a496-116">In both cases you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="4a496-117">F5 приложения (контейнера одного или нескольких) непосредственно в Docker разместить с отладкой, или нажмите клавиши Ctrl + F5, чтобы изменить и обновить приложение без повторной сборки контейнера.</span><span class="sxs-lookup"><span data-stu-id="4a496-117">F5 your application (single container or multiple containers) directly into a Docker host with debugging, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="4a496-118">Это самый простой и эффективный Выбор для разработчиков Windows, создание контейнеров Docker для Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="4a496-118">This is the simplest and more powerful choice for Windows developers creating Docker containers for Linux or Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="4a496-119">Чтобы скачать средства Docker для Visual Studio, перейдите к <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span><span class="sxs-lookup"><span data-stu-id="4a496-119">To download Docker Tools for Visual Studio, go to <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="4a496-120">Выбор языка и платформы</span><span class="sxs-lookup"><span data-stu-id="4a496-120">Language and framework choices</span></span>

<span data-ttu-id="4a496-121">Вы можете разрабатывать приложения Docker и средства Microsoft с наиболее современные языки.</span><span class="sxs-lookup"><span data-stu-id="4a496-121">You can develop Docker applications and Microsoft tools with most modern languages.</span></span> <span data-ttu-id="4a496-122">Ниже приведен исходный список, но вы не ограничены его:</span><span class="sxs-lookup"><span data-stu-id="4a496-122">The following is an initial list, but you are not limited to it:</span></span>

-   <span data-ttu-id="4a496-123">.NET Core и ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4a496-123">.NET Core and ASP.NET Core</span></span>
-   <span data-ttu-id="4a496-124">Node.js</span><span class="sxs-lookup"><span data-stu-id="4a496-124">Node.js</span></span>
-   <span data-ttu-id="4a496-125">Golang</span><span class="sxs-lookup"><span data-stu-id="4a496-125">Golang</span></span>
-   <span data-ttu-id="4a496-126">Java</span><span class="sxs-lookup"><span data-stu-id="4a496-126">Java</span></span>
-   <span data-ttu-id="4a496-127">Ruby</span><span class="sxs-lookup"><span data-stu-id="4a496-127">Ruby</span></span>
-   <span data-ttu-id="4a496-128">Python</span><span class="sxs-lookup"><span data-stu-id="4a496-128">Python</span></span>

<span data-ttu-id="4a496-129">По сути можно использовать любой современный язык, поддерживаемых в Docker в Linux или Windows.</span><span class="sxs-lookup"><span data-stu-id="4a496-129">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4a496-130">[Назад](orchestrate-high-scalability-availability.md)
>[Вперед](docker-apps-inner-loop-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="4a496-130">[Previous](orchestrate-high-scalability-availability.md)
[Next](docker-apps-inner-loop-workflow.md)</span></span>