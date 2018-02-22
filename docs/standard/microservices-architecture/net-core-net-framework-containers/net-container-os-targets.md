---
title: "Для какой ОС использовать контейнеры .NET"
description: "Архитектура микрослужб .NET для контейнерных приложений .NET | Для какой ОС использовать контейнеры .NET"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ef7a21efa23be3a5181f08066a093abbb915c20f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="9f3c2-104">Для какой ОС использовать контейнеры .NET</span><span class="sxs-lookup"><span data-stu-id="9f3c2-104">What OS to target with .NET containers</span></span>

<span data-ttu-id="9f3c2-105">Учитывая разнообразие операционных систем, поддерживаемых Docker, и различия между .NET Framework и .NET Core, следует выбирать определенные ОС и определенные версии в зависимости от платформы, которую вы используете.</span><span class="sxs-lookup"><span data-stu-id="9f3c2-105">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span> 

<span data-ttu-id="9f3c2-106">Для Windows можно использовать Windows Server Core или Windows Nano Server.</span><span class="sxs-lookup"><span data-stu-id="9f3c2-106">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="9f3c2-107">Эти версии Windows предоставляют разные особенности (IIS в Windows Server Core или резидентный веб-сервер, такой как Kestrel, в Nano Server), которые могут быть необходимы в .NET Framework или .NET Core соответственно.</span><span class="sxs-lookup"><span data-stu-id="9f3c2-107">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span> 

<span data-ttu-id="9f3c2-108">Для Linux доступно и поддерживается множество дистрибутивов в официальных образах Docker .NET (например, Debian).</span><span class="sxs-lookup"><span data-stu-id="9f3c2-108">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="9f3c2-109">На рисунке 3-1 представлены возможные версии операционной системы в зависимости от используемой платформы .NET.</span><span class="sxs-lookup"><span data-stu-id="9f3c2-109">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![](./media/image1.png)

<span data-ttu-id="9f3c2-110">**Рис. 3-1**.</span><span class="sxs-lookup"><span data-stu-id="9f3c2-110">**Figure 3-1.**</span></span> <span data-ttu-id="9f3c2-111">Выбираемые операционные системы в зависимости от версии платформы .NET</span><span class="sxs-lookup"><span data-stu-id="9f3c2-111">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="9f3c2-112">В том случае, если требуется использовать другой дистрибутив Linux или если нужен образ с версиями, не предоставляемыми Майкрософт, можно также создать собственный образ Docker.</span><span class="sxs-lookup"><span data-stu-id="9f3c2-112">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="9f3c2-113">Например, можно создать образ с ASP.NET Core для работы на классической платформе .NET Framework и в Windows Server Core, что для Docker является довольно редко используемым сценарием.</span><span class="sxs-lookup"><span data-stu-id="9f3c2-113">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

<span data-ttu-id="9f3c2-114">При добавлении имени образа в файл Dockerfile можно выбрать операционную систему и версию в зависимости от используемого тега, как показано в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="9f3c2-114">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

-   <span data-ttu-id="9f3c2-115">microsoft/**dotnet:2.0.0-runtime-jessie**</span><span class="sxs-lookup"><span data-stu-id="9f3c2-115">microsoft/**dotnet:2.0.0-runtime-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux

-   <span data-ttu-id="9f3c2-116">microsoft/**dotnet:2.0.0-runtime-nanoserver-1709**</span><span class="sxs-lookup"><span data-stu-id="9f3c2-116">microsoft/**dotnet:2.0.0-runtime-nanoserver-1709**</span></span> 

        .NET Core 2.0 runtime-only on Windows Nano Server (Windows Server 2016 Fall Creators Update version 1709)

-   <span data-ttu-id="9f3c2-117">microsoft/**aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="9f3c2-117">microsoft/**aspnetcore:2.0**</span></span>
    
        .NET Core 2.0 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.
        The aspnetcore image has a few optimizations for ASP.NET Core. 





>[!div class="step-by-step"]
<span data-ttu-id="9f3c2-118">[Назад] (container-framework-choice-factors.md) [Далее] (official-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="9f3c2-118">[Previous] (container-framework-choice-factors.md) [Next] (official-net-docker-images.md)</span></span>
