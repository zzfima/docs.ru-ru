---
title: "Общие рекомендации"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Общие рекомендации"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 22dea926e77079e4f543934613ced13a28b2dae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="general-guidance"></a><span data-ttu-id="ea712-104">Общие рекомендации</span><span class="sxs-lookup"><span data-stu-id="ea712-104">General guidance</span></span>

<span data-ttu-id="ea712-105">В этом разделе представлена сводка относительно выбора .NET Core или .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ea712-105">This section provides a summary of when to choose .NET Core or .NET Framework.</span></span> <span data-ttu-id="ea712-106">Мы содержат дополнительные сведения об этих вариантов в последующих разделах.</span><span class="sxs-lookup"><span data-stu-id="ea712-106">We provide more details about these choices in the sections that follow.</span></span>

<span data-ttu-id="ea712-107">Следует использовать .NET Core с контейнерами Windows или Linux для контейнерного серверное приложение Docker при:</span><span class="sxs-lookup"><span data-stu-id="ea712-107">You should use .NET Core, with Linux or Windows Containers, for your containerized Docker server application when:</span></span>

-   <span data-ttu-id="ea712-108">для создания кроссплатформенных решений;</span><span class="sxs-lookup"><span data-stu-id="ea712-108">You have cross-platform needs.</span></span> <span data-ttu-id="ea712-109">Например вы хотите использовать контейнеры Windows и Linux.</span><span class="sxs-lookup"><span data-stu-id="ea712-109">For example, you want to use both Linux and Windows Containers.</span></span>

-   <span data-ttu-id="ea712-110">Архитектура приложения основан на микрослужбами.</span><span class="sxs-lookup"><span data-stu-id="ea712-110">Your application architecture is based on microservices.</span></span>

-   <span data-ttu-id="ea712-111">Необходимо быстро запустить контейнеры и потребоваться небольшого размера каждого контейнера для достижения более высокую плотность или несколько контейнеров на единицу оборудования, чтобы снизить затраты.</span><span class="sxs-lookup"><span data-stu-id="ea712-111">You need to start containers fast and want a small footprint per container to achieve better density or more containers per hardware unit in order to lower your costs.</span></span>

<span data-ttu-id="ea712-112">Иными словами при создании новых приложений .NET в контейнерах .NET Core следует рассматривать как вариант по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ea712-112">In short, when you create new containerized .NET applications, you should consider .NET Core as the default choice.</span></span> <span data-ttu-id="ea712-113">Он имеет множество преимуществ и наиболее подходящее философии контейнеров и предпочтениями.</span><span class="sxs-lookup"><span data-stu-id="ea712-113">It has many benefits and fits best with the containers philosophy and style of working.</span></span>

<span data-ttu-id="ea712-114">Дополнительное преимущество использования .NET Core является то, что можно запускать параллельно версии платформы .NET для приложений, в том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="ea712-114">An additional benefit of using .NET Core is that you can run side by side .NET versions for applications within the same machine.</span></span> <span data-ttu-id="ea712-115">Данное преимущество более важна для серверов или виртуальных машин, которые не используют контейнеры, так как контейнеры изолировать версии .NET, приложению.</span><span class="sxs-lookup"><span data-stu-id="ea712-115">This benefit is more important for servers or VMs that do not use containers, because containers isolate the versions of .NET that the app needs.</span></span> <span data-ttu-id="ea712-116">(При условии, что они совместимы с базовой ОС.)</span><span class="sxs-lookup"><span data-stu-id="ea712-116">(As long as they are compatible with the underlying OS.)</span></span>

<span data-ttu-id="ea712-117">Платформа .NET Framework, следует использовать с контейнерами Windows для контейнерного серверное приложение Docker при:</span><span class="sxs-lookup"><span data-stu-id="ea712-117">You should use .NET Framework, with Windows Containers, for your containerized Docker server application when:</span></span>

-   <span data-ttu-id="ea712-118">В настоящее время приложение использует .NET Framework и ее строгое зависит от Windows.</span><span class="sxs-lookup"><span data-stu-id="ea712-118">Your application currently uses .NET Framework and has strong dependencies on Windows.</span></span>

-   <span data-ttu-id="ea712-119">Необходимо использовать API-интерфейсы Windows, который не поддерживается .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ea712-119">You need to use Windows APIs that are not supported by .NET Core.</span></span>

-   <span data-ttu-id="ea712-120">Необходимо использовать сторонние библиотеки .NET или пакеты NuGet, которые недоступны для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ea712-120">You need to use third-party .NET libraries or NuGet packages that are not available for .NET Core.</span></span>

<span data-ttu-id="ea712-121">Использование .NET Framework на Docker может повысить своими впечатлениями развертывания, сводя к минимуму проблемы развертывания.</span><span class="sxs-lookup"><span data-stu-id="ea712-121">Using .NET Framework on Docker can improve your deployment experiences by minimizing deployment issues.</span></span> <span data-ttu-id="ea712-122">Это [ *сценарий «точности прогнозов и сдвиг»* ](https://aka.ms/liftandshiftwithcontainersebook) важно для containerizing приложений прежних версий, которые изначально были разработаны с помощью традиционных .NET Framework, как веб-форм ASP.NET, MVC, веб-приложений или WCF () Службы Windows Communication Foundation).</span><span class="sxs-lookup"><span data-stu-id="ea712-122">This [*"lift and shift" scenario*](https://aka.ms/liftandshiftwithcontainersebook) is important for containerizing legacy applications that were originally developed with the traditional .NET Framework, like ASP.NET WebForms, MVC web apps or WCF (Windows Communication Foundation) services.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ea712-123">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ea712-123">Additional resources</span></span>

-   <span data-ttu-id="ea712-124">**электронная книга: модернизировать существующие приложения .NET Framework с Azure и контейнеров Windows**
    [*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)</span><span class="sxs-lookup"><span data-stu-id="ea712-124">**e-book: Modernize existing .NET Framework applications with Azure and Windows Containers**
[*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)</span></span>

-   <span data-ttu-id="ea712-125">**Образец приложения: модернизацию устаревших веб-приложения ASP.NET с помощью контейнеров Windows**
    [*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)</span><span class="sxs-lookup"><span data-stu-id="ea712-125">**Sample apps: Modernization of legacy ASP.NET web apps by using Windows Containers**
[*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="ea712-126">[Предыдущие] (index.md) [Далее] (net-core контейнера scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="ea712-126">[Previous] (index.md) [Next] (net-core-container-scenarios.md)</span></span>
