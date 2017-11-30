---
title: "Какие ОС для нацеливания .NET контейнеров"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Какие ОС для нацеливания .NET контейнеров"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 828ccb5e7a76f9419e80793b6cb3a6ba24f358cf
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="fb968-104">Какие ОС для нацеливания .NET контейнеров</span><span class="sxs-lookup"><span data-stu-id="fb968-104">What OS to target with .NET containers</span></span>

<span data-ttu-id="fb968-105">Учитывая разнообразие операционных систем, поддерживаемых Docker и различия между .NET Framework и .NET Core, должно использовать определенные ОС и определенные версии в зависимости от платформы, которую вы используете.</span><span class="sxs-lookup"><span data-stu-id="fb968-105">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span> 

<span data-ttu-id="fb968-106">Для Windows можно использовать Windows Server Core или Nano Windows Server.</span><span class="sxs-lookup"><span data-stu-id="fb968-106">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="fb968-107">Эти версии Windows предоставляют разные характеристики (IIS в Windows Server Core и резидентной веб-сервера как Kestrel в Nano Server), которые могут быть необходимы, .NET Framework или .NET Core, соответственно.</span><span class="sxs-lookup"><span data-stu-id="fb968-107">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span> 

<span data-ttu-id="fb968-108">Для Linux несколько дистрибутивы доступно и поддерживается в официальный образов .NET Docker (например, Debian).</span><span class="sxs-lookup"><span data-stu-id="fb968-108">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="fb968-109">На рисунке 3-1, вы увидите возможные версии операционной системы в зависимости от .NET framework, используемой.</span><span class="sxs-lookup"><span data-stu-id="fb968-109">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![](./media/image1.png)

<span data-ttu-id="fb968-110">**Рисунок 3-1.**</span><span class="sxs-lookup"><span data-stu-id="fb968-110">**Figure 3-1.**</span></span> <span data-ttu-id="fb968-111">Операционные системы для среды, в зависимости от версии платформы .NET framework</span><span class="sxs-lookup"><span data-stu-id="fb968-111">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="fb968-112">Также можно создать собственный образ Docker в случаях, где вы хотите использовать другой дистрибутив Linux или нужное изображение с версиями, не предоставляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fb968-112">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="fb968-113">Например можно создать образ с ASP.NET Core под управлением традиционных .NET Framework и Windows Server Core сценарии not, общие для Docker.</span><span class="sxs-lookup"><span data-stu-id="fb968-113">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

<span data-ttu-id="fb968-114">При добавлении имени образа в файл Dockerfile, можно выбрать операционной системы и версии в зависимости от тег, который используется, как показано в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="fb968-114">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

-   <span data-ttu-id="fb968-115">Microsoft и**dotnet:2.0.0-среда выполнения-детском**</span><span class="sxs-lookup"><span data-stu-id="fb968-115">microsoft/**dotnet:2.0.0-runtime-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux

-   <span data-ttu-id="fb968-116">Microsoft и**dotnet:2.0.0-среда выполнения-nanoserver-1709**</span><span class="sxs-lookup"><span data-stu-id="fb968-116">microsoft/**dotnet:2.0.0-runtime-nanoserver-1709**</span></span> 

        .NET Core 2.0 runtime-only on Windows Nano Server (Windows Server 2016 Fall Creators Update version 1709)

-   <span data-ttu-id="fb968-117">Microsoft и**aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="fb968-117">microsoft/**aspnetcore:2.0**</span></span>
    
        .NET Core 2.0 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.
        The aspnetcore image has a few optimizations for ASP.NET Core. 





>[!div class="step-by-step"]
<span data-ttu-id="fb968-118">[Предыдущие] (контейнер framework Выбор factors.md) [Далее] (официальное net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="fb968-118">[Previous] (container-framework-choice-factors.md) [Next] (official-net-docker-images.md)</span></span>
