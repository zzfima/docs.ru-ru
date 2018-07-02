---
title: Для какой ОС использовать контейнеры .NET
description: Архитектура микрослужб .NET для контейнерных приложений .NET | Для какой ОС использовать контейнеры .NET
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: fca5cf280d5abb85da78413a6eed463a2ffe6a88
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37104883"
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="da790-103">Для какой ОС использовать контейнеры .NET</span><span class="sxs-lookup"><span data-stu-id="da790-103">What OS to target with .NET containers</span></span>

<span data-ttu-id="da790-104">Учитывая разнообразие операционных систем, поддерживаемых Docker, и различия между .NET Framework и .NET Core, следует выбирать определенные ОС и определенные версии в зависимости от платформы, которую вы используете.</span><span class="sxs-lookup"><span data-stu-id="da790-104">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span> 

<span data-ttu-id="da790-105">Для Windows можно использовать Windows Server Core или Windows Nano Server.</span><span class="sxs-lookup"><span data-stu-id="da790-105">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="da790-106">Эти версии Windows предоставляют разные особенности (IIS в Windows Server Core или резидентный веб-сервер, такой как Kestrel, в Nano Server), которые могут быть необходимы в .NET Framework или .NET Core соответственно.</span><span class="sxs-lookup"><span data-stu-id="da790-106">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span> 

<span data-ttu-id="da790-107">Для Linux доступно и поддерживается множество дистрибутивов в официальных образах Docker .NET (например, Debian).</span><span class="sxs-lookup"><span data-stu-id="da790-107">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="da790-108">На рисунке 3-1 представлены возможные версии операционной системы в зависимости от используемой платформы .NET.</span><span class="sxs-lookup"><span data-stu-id="da790-108">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![](./media/image1.png)

<span data-ttu-id="da790-109">**Рис. 3-1**.</span><span class="sxs-lookup"><span data-stu-id="da790-109">**Figure 3-1.**</span></span> <span data-ttu-id="da790-110">Выбираемые операционные системы в зависимости от версии платформы .NET</span><span class="sxs-lookup"><span data-stu-id="da790-110">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="da790-111">В том случае, если требуется использовать другой дистрибутив Linux или если нужен образ с версиями, не предоставляемыми Майкрософт, можно также создать собственный образ Docker.</span><span class="sxs-lookup"><span data-stu-id="da790-111">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="da790-112">Например, можно создать образ с ASP.NET Core для работы на классической платформе .NET Framework и в Windows Server Core, что для Docker является довольно редко используемым сценарием.</span><span class="sxs-lookup"><span data-stu-id="da790-112">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

<span data-ttu-id="da790-113">При добавлении имени образа в файл Dockerfile можно выбрать операционную систему и версию в зависимости от используемого тега, как показано в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="da790-113">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

-   <span data-ttu-id="da790-114">microsoft/**dotnet:2.1-runtime**</span><span class="sxs-lookup"><span data-stu-id="da790-114">microsoft/**dotnet:2.1-runtime**</span></span>

        .NET Core 2.1 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.

-   <span data-ttu-id="da790-115">microsoft/**dotnet:2.1-aspnetcore-runtime**</span><span class="sxs-lookup"><span data-stu-id="da790-115">microsoft/**dotnet:2.1-aspnetcore-runtime**</span></span>
    
        ASP.NET Core 2.1 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.
        The aspnetcore image has a few optimizations for ASP.NET Core. 

-   <span data-ttu-id="da790-116">microsoft/**dotnet:2.1-aspnetcore-runtime-alpine**</span><span class="sxs-lookup"><span data-stu-id="da790-116">microsoft/**dotnet:2.1-aspnetcore-runtime-alpine**</span></span> 

        .NET Core 2.1 runtime-only on Linux Alpine distro

-   <span data-ttu-id="da790-117">microsoft/**dotnet:2.1-aspnetcore-runtime-nanoserver-1803**</span><span class="sxs-lookup"><span data-stu-id="da790-117">microsoft/**dotnet:2.1-aspnetcore-runtime-nanoserver-1803**</span></span> 

        .NET Core 2.1 runtime-only on Windows Nano Server (Windows Server version 1803)




>[!div class="step-by-step"]
<span data-ttu-id="da790-118">[Назад](container-framework-choice-factors.md)
[Вперед](official-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="da790-118">[Previous](container-framework-choice-factors.md)
[Next](official-net-docker-images.md)</span></span>
