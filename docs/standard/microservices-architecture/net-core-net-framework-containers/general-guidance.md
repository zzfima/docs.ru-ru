---
title: "Общие рекомендации"
description: "Архитектура микрослужб .NET для контейнерных приложений .NET | Общие рекомендации"
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
ms.openlocfilehash: fa58d1d81b2d1523baf123d4963db2ca00fee15d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="general-guidance"></a><span data-ttu-id="ce380-104">Общие рекомендации</span><span class="sxs-lookup"><span data-stu-id="ce380-104">General guidance</span></span>

<span data-ttu-id="ce380-105">В этом разделе представлена сводка относительно выбора .NET Core или .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ce380-105">This section provides a summary of when to choose .NET Core or .NET Framework.</span></span> <span data-ttu-id="ce380-106">Дополнительные сведения об этих вариантах представлены в последующих разделах.</span><span class="sxs-lookup"><span data-stu-id="ce380-106">We provide more details about these choices in the sections that follow.</span></span>

<span data-ttu-id="ce380-107">Следует использовать .NET Core с контейнерами Windows или Linux для контейнерного серверного приложения Docker в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="ce380-107">You should use .NET Core, with Linux or Windows Containers, for your containerized Docker server application when:</span></span>

-   <span data-ttu-id="ce380-108">для создания кроссплатформенных решений;</span><span class="sxs-lookup"><span data-stu-id="ce380-108">You have cross-platform needs.</span></span> <span data-ttu-id="ce380-109">Например, вы хотите использовать контейнеры и Windows, и Linux.</span><span class="sxs-lookup"><span data-stu-id="ce380-109">For example, you want to use both Linux and Windows Containers.</span></span>

-   <span data-ttu-id="ce380-110">Архитектура приложения основана на микрослужбах.</span><span class="sxs-lookup"><span data-stu-id="ce380-110">Your application architecture is based on microservices.</span></span>

-   <span data-ttu-id="ce380-111">Вам нужно быстро запустить контейнеры, и вы хотите использовать небольшой объем памяти на каждый контейнер, чтобы получить более высокую плотность или больше контейнеров на единицу оборудования для снижения затрат.</span><span class="sxs-lookup"><span data-stu-id="ce380-111">You need to start containers fast and want a small footprint per container to achieve better density or more containers per hardware unit in order to lower your costs.</span></span>

<span data-ttu-id="ce380-112">Вкратце, при создании новых контейнерных приложений .NET следует рассматривать .NET Core как вариант по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ce380-112">In short, when you create new containerized .NET applications, you should consider .NET Core as the default choice.</span></span> <span data-ttu-id="ce380-113">Он имеет множество преимуществ и лучше соответствует концепции и стилю работы с контейнерами.</span><span class="sxs-lookup"><span data-stu-id="ce380-113">It has many benefits and fits best with the containers philosophy and style of working.</span></span>

<span data-ttu-id="ce380-114">Дополнительное преимущество использования .NET Core заключается в том, что можно параллельно запускать версии .NET для приложений на одной и той же машине.</span><span class="sxs-lookup"><span data-stu-id="ce380-114">An additional benefit of using .NET Core is that you can run side by side .NET versions for applications within the same machine.</span></span> <span data-ttu-id="ce380-115">Данное преимущество более важно для серверов или виртуальных машин, которые не используют контейнеры, так как контейнеры изолируют версии .NET, нужные приложению.</span><span class="sxs-lookup"><span data-stu-id="ce380-115">This benefit is more important for servers or VMs that do not use containers, because containers isolate the versions of .NET that the app needs.</span></span> <span data-ttu-id="ce380-116">(При условии, что они совместимы с базовой ОС.)</span><span class="sxs-lookup"><span data-stu-id="ce380-116">(As long as they are compatible with the underlying OS.)</span></span>

<span data-ttu-id="ce380-117">Следует использовать .NET Framework с контейнерами Windows или Linux для контейнерного серверного приложения Docker в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="ce380-117">You should use .NET Framework, with Windows Containers, for your containerized Docker server application when:</span></span>

-   <span data-ttu-id="ce380-118">В настоящее время приложение использует .NET Framework и имеет строгие зависимости от Windows.</span><span class="sxs-lookup"><span data-stu-id="ce380-118">Your application currently uses .NET Framework and has strong dependencies on Windows.</span></span>

-   <span data-ttu-id="ce380-119">Необходимо использовать API Windows, которые не поддерживаются .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ce380-119">You need to use Windows APIs that are not supported by .NET Core.</span></span>

-   <span data-ttu-id="ce380-120">Требуются сторонние библиотеки .NET или пакеты NuGet, недоступные для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ce380-120">You need to use third-party .NET libraries or NuGet packages that are not available for .NET Core.</span></span>

<span data-ttu-id="ce380-121">Использование .NET Framework в Docker может улучшить качество развертывания, сводя к минимуму проблемы развертывания.</span><span class="sxs-lookup"><span data-stu-id="ce380-121">Using .NET Framework on Docker can improve your deployment experiences by minimizing deployment issues.</span></span> <span data-ttu-id="ce380-122">Данный сценарий [*"подъема и смены"*](https://aka.ms/liftandshiftwithcontainersebook) важен для контейнеризации приложений прежних версий, которые изначально были разработаны с использованием классической платформы .NET Framework, например ASP.NET WebForms, веб-приложений MVC или служб WCF (Windows Communication Foundation).</span><span class="sxs-lookup"><span data-stu-id="ce380-122">This [*"lift and shift" scenario*](https://aka.ms/liftandshiftwithcontainersebook) is important for containerizing legacy applications that were originally developed with the traditional .NET Framework, like ASP.NET WebForms, MVC web apps or WCF (Windows Communication Foundation) services.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ce380-123">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ce380-123">Additional resources</span></span>

-   <span data-ttu-id="ce380-124">**Электронная книга: Modernize existing .NET Framework applications with Azure and Windows Containers**
    [*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)</span><span class="sxs-lookup"><span data-stu-id="ce380-124">**e-book: Modernize existing .NET Framework applications with Azure and Windows Containers**
[*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)</span></span>

-   <span data-ttu-id="ce380-125">**Примеры приложений: Modernization of legacy ASP.NET web apps by using Windows Containers**
    [*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)</span><span class="sxs-lookup"><span data-stu-id="ce380-125">**Sample apps: Modernization of legacy ASP.NET web apps by using Windows Containers**
[*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="ce380-126">[Назад] (index.md) [Далее] (net-core-container-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="ce380-126">[Previous] (index.md) [Next] (net-core-container-scenarios.md)</span></span>
