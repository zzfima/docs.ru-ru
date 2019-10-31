---
title: Для какой ОС использовать контейнеры .NET
description: Архитектура микрослужб .NET для контейнерных приложений .NET | Для какой ОС использовать контейнеры .NET
ms.date: 01/07/2019
ms.openlocfilehash: 8bcfa0212f84c575a63f76e05edec1e511cadc36
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72772004"
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="cc4d3-103">Для какой ОС использовать контейнеры .NET</span><span class="sxs-lookup"><span data-stu-id="cc4d3-103">What OS to target with .NET containers</span></span>

<span data-ttu-id="cc4d3-104">Учитывая разнообразие операционных систем, поддерживаемых Docker, и различия между .NET Framework и .NET Core, следует выбирать определенные ОС и определенные версии в зависимости от платформы, которую вы используете.</span><span class="sxs-lookup"><span data-stu-id="cc4d3-104">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span>

<span data-ttu-id="cc4d3-105">Для Windows можно использовать Windows Server Core или Windows Nano Server.</span><span class="sxs-lookup"><span data-stu-id="cc4d3-105">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="cc4d3-106">Эти версии Windows предоставляют разные особенности (IIS в Windows Server Core или резидентный веб-сервер, такой как Kestrel, в Nano Server), которые могут быть необходимы в .NET Framework или .NET Core соответственно.</span><span class="sxs-lookup"><span data-stu-id="cc4d3-106">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span>

<span data-ttu-id="cc4d3-107">Для Linux доступно и поддерживается множество дистрибутивов в официальных образах Docker .NET (например, Debian).</span><span class="sxs-lookup"><span data-stu-id="cc4d3-107">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="cc4d3-108">На рисунке 3-1 представлены возможные версии операционной системы в зависимости от используемой платформы .NET.</span><span class="sxs-lookup"><span data-stu-id="cc4d3-108">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![При развертывании устаревших приложений .NET Framework выберите в качестве целевой ОС Windows Server Core, которая совместима с устаревшими приложениями и службами IIS и образ которой имеет больший размер.](./media/image1.png)

<span data-ttu-id="cc4d3-113">**Рис. 3-1**.</span><span class="sxs-lookup"><span data-stu-id="cc4d3-113">**Figure 3-1.**</span></span> <span data-ttu-id="cc4d3-114">Выбираемые операционные системы в зависимости от версии платформы .NET</span><span class="sxs-lookup"><span data-stu-id="cc4d3-114">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="cc4d3-115">В том случае, если требуется использовать другой дистрибутив Linux или если нужен образ с версиями, не предоставляемыми Майкрософт, можно также создать собственный образ Docker.</span><span class="sxs-lookup"><span data-stu-id="cc4d3-115">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="cc4d3-116">Например, можно создать образ с ASP.NET Core для работы на классической платформе .NET Framework и в Windows Server Core, что для Docker является довольно редко используемым сценарием.</span><span class="sxs-lookup"><span data-stu-id="cc4d3-116">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc4d3-117">При использовании образов Windows Server Core может оказаться, что отсутствуют некоторые библиотеки DLL по сравнению с полными образами Windows.</span><span class="sxs-lookup"><span data-stu-id="cc4d3-117">When using Windows Server Core images, you might find that some DLLs are missing, when compared to full Windows images.</span></span> <span data-ttu-id="cc4d3-118">Возможно, вы можете решить эту проблему, создав пользовательский образ Server Core и добавив отсутствующие файлы во время сборки, как описано в этом [комментарии на сайте GitHub](https://github.com/microsoft/dotnet-framework-docker/issues/299#issuecomment-511537448).</span><span class="sxs-lookup"><span data-stu-id="cc4d3-118">You might be able to solve this problem by creating a custom Server Core image, adding the missing files at image build time, as mentioned in this [GitHub comment](https://github.com/microsoft/dotnet-framework-docker/issues/299#issuecomment-511537448).</span></span>

<span data-ttu-id="cc4d3-119">При добавлении имени образа в файл Dockerfile можно выбрать операционную систему и версию в зависимости от используемого тега, как показано в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="cc4d3-119">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

| <span data-ttu-id="cc4d3-120">Изображение</span><span class="sxs-lookup"><span data-stu-id="cc4d3-120">Image</span></span> | <span data-ttu-id="cc4d3-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="cc4d3-121">Comments</span></span> |
|-------|----------|
| <span data-ttu-id="cc4d3-122">mcr.microsoft.com/dotnet/core/runtime:2.2</span><span class="sxs-lookup"><span data-stu-id="cc4d3-122">mcr.microsoft.com/dotnet/core/runtime:2.2</span></span> | <span data-ttu-id="cc4d3-123">.NET Core 2.2 (мультиархитектурный): поддерживает Linux и Windows Nano Server в зависимости от узла Docker.</span><span class="sxs-lookup"><span data-stu-id="cc4d3-123">.NET Core 2.2 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span> |
| <span data-ttu-id="cc4d3-124">mcr.microsoft.com/dotnet/core/aspnet:2.2</span><span class="sxs-lookup"><span data-stu-id="cc4d3-124">mcr.microsoft.com/dotnet/core/aspnet:2.2</span></span> | <span data-ttu-id="cc4d3-125">ASP.NET Core 2.2 (мультиархитектурный): поддерживает Linux и Windows Nano Server в зависимости от узла Docker.</span><span class="sxs-lookup"><span data-stu-id="cc4d3-125">ASP.NET Core 2.2 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span> <br/> <span data-ttu-id="cc4d3-126">Образ aspnetcore имеет несколько оптимизаций для ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="cc4d3-126">The aspnetcore image has a few optimizations for ASP.NET Core.</span></span> |
| <span data-ttu-id="cc4d3-127">mcr.microsoft.com/dotnet/core/aspnet:2.2-alpine</span><span class="sxs-lookup"><span data-stu-id="cc4d3-127">mcr.microsoft.com/dotnet/core/aspnet:2.2-alpine</span></span> | <span data-ttu-id="cc4d3-128">.NET Core 2.2 (только для среды выполнения), основанный на дистрибутиве Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="cc4d3-128">.NET Core 2.2 runtime-only on Linux Alpine distro</span></span> |
| <span data-ttu-id="cc4d3-129">mcr.microsoft.com/dotnet/core/aspnet:2.2-nanoserver-1803</span><span class="sxs-lookup"><span data-stu-id="cc4d3-129">mcr.microsoft.com/dotnet/core/aspnet:2.2-nanoserver-1803</span></span> | <span data-ttu-id="cc4d3-130">.NET Core 2.2 (только для среды выполнения), основанный на Windows Nano Server (Windows Server версии 1803)</span><span class="sxs-lookup"><span data-stu-id="cc4d3-130">.NET Core 2.2 runtime-only on Windows Nano Server (Windows Server version 1803)</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="cc4d3-131">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="cc4d3-131">Additional resources</span></span>

- <span data-ttu-id="cc4d3-132">**BitmapDecoder завершается со сбоем из-за отсутствующей библиотеки WindowsCodecsExt.dll (проблема GitHub)**</span><span class="sxs-lookup"><span data-stu-id="cc4d3-132">**BitmapDecoder fails due to missing WindowsCodecsExt.dll (GitHub issue)**</span></span>  
  <https://github.com/microsoft/dotnet-framework-docker/issues/299>

> [!div class="step-by-step"]
> <span data-ttu-id="cc4d3-133">[Назад](container-framework-choice-factors.md)
> [Вперед](official-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="cc4d3-133">[Previous](container-framework-choice-factors.md)
[Next](official-net-docker-images.md)</span></span>
