---
title: Среда разработки приложений Docker
description: Узнайте о наиболее важные параметры средства разработки, которые поддерживают жизненного цикла разработки Docker.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 1d22b45a8eee9198d337df9f0b8b4b78371fa31a
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220001"
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="828f4-103">Среда разработки приложений Docker</span><span class="sxs-lookup"><span data-stu-id="828f4-103">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="828f4-104">Выбор средств разработки: интегрированная среда разработки или редактор</span><span class="sxs-lookup"><span data-stu-id="828f4-104">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="828f4-105">Независимо от того, если вы предпочитаете полнофункциональную среду IDE или упрощенный редактор, корпорация Майкрософт предлагает вам рассматриваются, когда дело доходит до разработки приложений Docker.</span><span class="sxs-lookup"><span data-stu-id="828f4-105">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="828f4-106">Visual Studio Code и CLI Docker (кросс платформенные средства для Mac, Linux и Windows)</span><span class="sxs-lookup"><span data-stu-id="828f4-106">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="828f4-107">Если вам нужен упрощенный, кросс платформенных редактор, поддерживающий любой язык программирования, можно использовать Visual Studio Code и Docker CLI.</span><span class="sxs-lookup"><span data-stu-id="828f4-107">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="828f4-108">Эти решения обеспечивают простой и надежной, что очень важно для оптимизации рабочий процесс разработки.</span><span class="sxs-lookup"><span data-stu-id="828f4-108">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="828f4-109">Установив «Docker для Mac» или «Docker для Windows» (среда разработки), разработчики Docker можно использовать единый интерфейс CLI Docker для создания приложений для Windows или Linux (среду выполнения).</span><span class="sxs-lookup"><span data-stu-id="828f4-109">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="828f4-110">Кроме того, Visual Studio Code поддерживает расширения для Docker с поддержкой технологии IntelliSense для файлов Dockerfile и ярлыками задач для выполнения команд Docker из редактора.</span><span class="sxs-lookup"><span data-stu-id="828f4-110">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
> <span data-ttu-id="828f4-111">Чтобы скачать Visual Studio Code, перейдите к <https://code.visualstudio.com/download>.</span><span class="sxs-lookup"><span data-stu-id="828f4-111">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>

<span data-ttu-id="828f4-112">Чтобы скачать Docker для Mac и Windows, перейдите к <https://www.docker.com/products/docker>.</span><span class="sxs-lookup"><span data-stu-id="828f4-112">To download Docker for Mac and Windows, go to <https://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools"></a><span data-ttu-id="828f4-113">Visual Studio с помощью средств Docker</span><span class="sxs-lookup"><span data-stu-id="828f4-113">Visual Studio with Docker Tools</span></span>

<span data-ttu-id="828f4-114">При использовании Visual Studio 2015 можно установить дополнительные средства «Docker Tools for Visual Studio».</span><span class="sxs-lookup"><span data-stu-id="828f4-114">When you're using Visual Studio 2015 you can install the add-on tools "Docker Tools for Visual Studio."</span></span> <span data-ttu-id="828f4-115">Для Visual Studio 2017 средства Docker предоставляются вместе с используемыми в уже.</span><span class="sxs-lookup"><span data-stu-id="828f4-115">For Visual Studio 2017, Docker Tools come built in already.</span></span> <span data-ttu-id="828f4-116">В обоих случаях, которые можно разрабатывать запускать и проверять приложения непосредственно в выбранной среде Docker.</span><span class="sxs-lookup"><span data-stu-id="828f4-116">In both cases you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="828f4-117">F5 приложения (контейнера одного или нескольких) непосредственно в Docker разместить с отладкой, или нажмите клавиши Ctrl + F5, чтобы изменить и обновить приложение без повторной сборки контейнера.</span><span class="sxs-lookup"><span data-stu-id="828f4-117">F5 your application (single container or multiple containers) directly into a Docker host with debugging, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="828f4-118">Это самый простой и эффективный Выбор для разработчиков Windows, создание контейнеров Docker для Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="828f4-118">This is the simplest and more powerful choice for Windows developers creating Docker containers for Linux or Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="828f4-119">Чтобы скачать средства Docker для Visual Studio, перейдите к <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span><span class="sxs-lookup"><span data-stu-id="828f4-119">To download Docker Tools for Visual Studio, go to <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="828f4-120">Выбор языка и платформы</span><span class="sxs-lookup"><span data-stu-id="828f4-120">Language and framework choices</span></span>

<span data-ttu-id="828f4-121">Вы можете разрабатывать приложения Docker и средства Microsoft с наиболее современные языки.</span><span class="sxs-lookup"><span data-stu-id="828f4-121">You can develop Docker applications and Microsoft tools with most modern languages.</span></span> <span data-ttu-id="828f4-122">Ниже приведен исходный список, но вы не ограничены его:</span><span class="sxs-lookup"><span data-stu-id="828f4-122">The following is an initial list, but you are not limited to it:</span></span>

-   <span data-ttu-id="828f4-123">.NET Core и ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="828f4-123">.NET Core and ASP.NET Core</span></span>
-   <span data-ttu-id="828f4-124">Node.js</span><span class="sxs-lookup"><span data-stu-id="828f4-124">Node.js</span></span>
-   <span data-ttu-id="828f4-125">Golang</span><span class="sxs-lookup"><span data-stu-id="828f4-125">Golang</span></span>
-   <span data-ttu-id="828f4-126">Java</span><span class="sxs-lookup"><span data-stu-id="828f4-126">Java</span></span>
-   <span data-ttu-id="828f4-127">Ruby</span><span class="sxs-lookup"><span data-stu-id="828f4-127">Ruby</span></span>
-   <span data-ttu-id="828f4-128">Python</span><span class="sxs-lookup"><span data-stu-id="828f4-128">Python</span></span>

<span data-ttu-id="828f4-129">По сути можно использовать любой современный язык, поддерживаемых в Docker в Linux или Windows.</span><span class="sxs-lookup"><span data-stu-id="828f4-129">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="828f4-130">[Назад](deploy-azure-kubernetes-service.md)
>[Вперед](docker-apps-inner-loop-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="828f4-130">[Previous](deploy-azure-kubernetes-service.md)
[Next](docker-apps-inner-loop-workflow.md)</span></span>