---
title: Среда разработки приложений Docker
description: Узнайте о наиболее важные параметры средства разработки, которые поддерживают жизненного цикла разработки Docker.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 3a2fcbe3b9380083622b6ce72cea4bab17d7c2ea
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318826"
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="6e542-103">Среда разработки приложений Docker</span><span class="sxs-lookup"><span data-stu-id="6e542-103">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="6e542-104">Выбор средств разработки: интегрированная среда разработки или редактор</span><span class="sxs-lookup"><span data-stu-id="6e542-104">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="6e542-105">Независимо от того, если вы предпочитаете полнофункциональную среду IDE или упрощенный редактор, корпорация Майкрософт предлагает вам рассматриваются, когда дело доходит до разработки приложений Docker.</span><span class="sxs-lookup"><span data-stu-id="6e542-105">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="6e542-106">Visual Studio Code и CLI Docker (кросс платформенные средства для Mac, Linux и Windows)</span><span class="sxs-lookup"><span data-stu-id="6e542-106">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="6e542-107">Если вам нужен упрощенный, кросс платформенных редактор, поддерживающий любой язык программирования, можно использовать Visual Studio Code и Docker CLI.</span><span class="sxs-lookup"><span data-stu-id="6e542-107">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="6e542-108">Эти решения обеспечивают простой и надежной, что очень важно для оптимизации рабочий процесс разработки.</span><span class="sxs-lookup"><span data-stu-id="6e542-108">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="6e542-109">Установив «Docker для Mac» или «Docker для Windows» (среда разработки), разработчики Docker можно использовать единый интерфейс CLI Docker для создания приложений для Windows или Linux (среду выполнения).</span><span class="sxs-lookup"><span data-stu-id="6e542-109">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="6e542-110">Кроме того, Visual Studio Code поддерживает расширения для Docker с поддержкой технологии IntelliSense для файлов Dockerfile и ярлыками задач для выполнения команд Docker из редактора.</span><span class="sxs-lookup"><span data-stu-id="6e542-110">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
>
> <span data-ttu-id="6e542-111">Чтобы скачать Visual Studio Code, перейдите к <https://code.visualstudio.com/download>.</span><span class="sxs-lookup"><span data-stu-id="6e542-111">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>
>
> <span data-ttu-id="6e542-112">Чтобы скачать Docker для Mac и Windows, перейдите к <https://www.docker.com/products/docker>.</span><span class="sxs-lookup"><span data-stu-id="6e542-112">To download Docker for Mac and Windows, go to <https://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools-windows-development-machine"></a><span data-ttu-id="6e542-113">Visual Studio с помощью инструментов Docker (на компьютере разработки Windows)</span><span class="sxs-lookup"><span data-stu-id="6e542-113">Visual Studio with Docker Tools (Windows development machine)</span></span>

<span data-ttu-id="6e542-114">Мы рекомендуем использовать Visual Studio 2017 (или более поздней версии) с помощью встроенных инструментов Docker включена.</span><span class="sxs-lookup"><span data-stu-id="6e542-114">We recommend you use Visual Studio 2017 (or later) with the built-in Docker Tools enabled.</span></span> <span data-ttu-id="6e542-115">С помощью Visual Studio можно разрабатывать, запускать и проверять приложения непосредственно в выбранной среде Docker.</span><span class="sxs-lookup"><span data-stu-id="6e542-115">With Visual Studio, you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="6e542-116">Нажмите клавишу F5 для отладки приложения (контейнера одного или нескольких) непосредственно в узле Docker или нажмите сочетание клавиш Ctrl + F5, чтобы изменить и обновить приложение без повторной сборки контейнера.</span><span class="sxs-lookup"><span data-stu-id="6e542-116">Press F5 to debug your application (single container or multiple containers) directly in a Docker host, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="6e542-117">Это самый простой и эффективный способ для разработчиков Windows для создания контейнеров Docker для Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="6e542-117">It's the simplest and most powerful choice for Windows developers to create Docker containers for Linux or Windows.</span></span>

### <a name="visual-studio-for-mac-mac-development-machine"></a><span data-ttu-id="6e542-118">Visual Studio для Mac (компьютер разработки Mac)</span><span class="sxs-lookup"><span data-stu-id="6e542-118">Visual Studio for Mac (Mac development machine)</span></span>

<span data-ttu-id="6e542-119">Можно использовать [Visual Studio для Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) при разработке приложений на основе Docker.</span><span class="sxs-lookup"><span data-stu-id="6e542-119">You can use [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) when developing Docker-based applications.</span></span> <span data-ttu-id="6e542-120">Visual Studio для Mac предлагает более широкие интегрированной среды разработки, по сравнению с Visual Studio Code для Mac.</span><span class="sxs-lookup"><span data-stu-id="6e542-120">Visual Studio for Mac offers a richer IDE when compared to Visual Studio Code for Mac.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="6e542-121">Выбор языка и платформы</span><span class="sxs-lookup"><span data-stu-id="6e542-121">Language and framework choices</span></span>

<span data-ttu-id="6e542-122">Можно разрабатывать приложения Docker с помощью средств Microsoft с наиболее современные языки.</span><span class="sxs-lookup"><span data-stu-id="6e542-122">You can develop Docker applications using Microsoft tools with most modern languages.</span></span> <span data-ttu-id="6e542-123">Ниже приведен исходный список, но вы не ограничены в него:</span><span class="sxs-lookup"><span data-stu-id="6e542-123">The following is an initial list, but you're not limited to it:</span></span>

- <span data-ttu-id="6e542-124">.NET Core и ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6e542-124">.NET Core and ASP.NET Core</span></span>
- <span data-ttu-id="6e542-125">Node.js</span><span class="sxs-lookup"><span data-stu-id="6e542-125">Node.js</span></span>
- <span data-ttu-id="6e542-126">Go</span><span class="sxs-lookup"><span data-stu-id="6e542-126">Go</span></span>
- <span data-ttu-id="6e542-127">Java</span><span class="sxs-lookup"><span data-stu-id="6e542-127">Java</span></span>
- <span data-ttu-id="6e542-128">Ruby</span><span class="sxs-lookup"><span data-stu-id="6e542-128">Ruby</span></span>
- <span data-ttu-id="6e542-129">Python</span><span class="sxs-lookup"><span data-stu-id="6e542-129">Python</span></span>

<span data-ttu-id="6e542-130">По сути можно использовать любой современный язык, поддерживаемых в Docker в Linux или Windows.</span><span class="sxs-lookup"><span data-stu-id="6e542-130">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6e542-131">[Назад](deploy-azure-kubernetes-service.md)
>[Вперед](docker-apps-inner-loop-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="6e542-131">[Previous](deploy-azure-kubernetes-service.md)
[Next](docker-apps-inner-loop-workflow.md)</span></span>
