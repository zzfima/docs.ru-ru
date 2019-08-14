---
title: Общие рекомендации
description: Архитектура микрослужб .NET для контейнерных приложений .NET | Общие рекомендации
ms.date: 09/11/2018
ms.openlocfilehash: 0981cb16d5aa2036391caba0cf6ad3ac5c44ed6f
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68675801"
---
# <a name="general-guidance"></a><span data-ttu-id="9c936-103">Общие рекомендации</span><span class="sxs-lookup"><span data-stu-id="9c936-103">General guidance</span></span>

<span data-ttu-id="9c936-104">В этом разделе представлена сводка относительно выбора .NET Core или .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9c936-104">This section provides a summary of when to choose .NET Core or .NET Framework.</span></span> <span data-ttu-id="9c936-105">Дополнительные сведения об этих вариантах представлены в последующих разделах.</span><span class="sxs-lookup"><span data-stu-id="9c936-105">We provide more details about these choices in the sections that follow.</span></span>

<span data-ttu-id="9c936-106">Следует использовать .NET Core с контейнерами Windows или Linux для контейнерного серверного приложения Docker в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="9c936-106">You should use .NET Core, with Linux or Windows Containers, for your containerized Docker server application when:</span></span>

- <span data-ttu-id="9c936-107">для создания кроссплатформенных решений;</span><span class="sxs-lookup"><span data-stu-id="9c936-107">You have cross-platform needs.</span></span> <span data-ttu-id="9c936-108">Например, вы хотите использовать контейнеры и Windows, и Linux.</span><span class="sxs-lookup"><span data-stu-id="9c936-108">For example, you want to use both Linux and Windows Containers.</span></span>

- <span data-ttu-id="9c936-109">Архитектура приложения основана на микрослужбах.</span><span class="sxs-lookup"><span data-stu-id="9c936-109">Your application architecture is based on microservices.</span></span>

- <span data-ttu-id="9c936-110">Вам нужно быстро запустить контейнеры, и вы хотите использовать небольшой объем памяти на каждый контейнер, чтобы получить более высокую плотность или больше контейнеров на единицу оборудования для снижения затрат.</span><span class="sxs-lookup"><span data-stu-id="9c936-110">You need to start containers fast and want a small footprint per container to achieve better density or more containers per hardware unit in order to lower your costs.</span></span>

<span data-ttu-id="9c936-111">Вкратце, при создании новых контейнерных приложений .NET следует рассматривать .NET Core как вариант по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9c936-111">In short, when you create new containerized .NET applications, you should consider .NET Core as the default choice.</span></span> <span data-ttu-id="9c936-112">Он имеет множество преимуществ и лучше соответствует концепции и стилю работы с контейнерами.</span><span class="sxs-lookup"><span data-stu-id="9c936-112">It has many benefits and fits best with the containers philosophy and style of working.</span></span>

<span data-ttu-id="9c936-113">Дополнительное преимущество использования .NET Core заключается в том, что можно параллельно запускать версии .NET для приложений на одной и той же машине.</span><span class="sxs-lookup"><span data-stu-id="9c936-113">An additional benefit of using .NET Core is that you can run side by side .NET versions for applications within the same machine.</span></span> <span data-ttu-id="9c936-114">Данное преимущество более важно для серверов или виртуальных машин, которые не используют контейнеры, так как контейнеры изолируют версии .NET, нужные приложению.</span><span class="sxs-lookup"><span data-stu-id="9c936-114">This benefit is more important for servers or VMs that do not use containers, because containers isolate the versions of .NET that the app needs.</span></span> <span data-ttu-id="9c936-115">(При условии, что они совместимы с базовой ОС.)</span><span class="sxs-lookup"><span data-stu-id="9c936-115">(As long as they are compatible with the underlying OS.)</span></span>

<span data-ttu-id="9c936-116">.NET Framework для серверных приложений в контейнерах Docker следует использовать в перечисленных ниже случаях.</span><span class="sxs-lookup"><span data-stu-id="9c936-116">You should use .NET Framework for your containerized Docker server application when:</span></span>

- <span data-ttu-id="9c936-117">В настоящее время приложение использует .NET Framework и имеет строгие зависимости от Windows.</span><span class="sxs-lookup"><span data-stu-id="9c936-117">Your application currently uses .NET Framework and has strong dependencies on Windows.</span></span>

- <span data-ttu-id="9c936-118">Необходимо использовать API Windows, которые не поддерживаются .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9c936-118">You need to use Windows APIs that are not supported by .NET Core.</span></span>

- <span data-ttu-id="9c936-119">Требуются сторонние библиотеки .NET или пакеты NuGet, недоступные для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9c936-119">You need to use third-party .NET libraries or NuGet packages that are not available for .NET Core.</span></span>

<span data-ttu-id="9c936-120">Использование .NET Framework в Docker может улучшить качество развертывания, сводя к минимуму проблемы развертывания.</span><span class="sxs-lookup"><span data-stu-id="9c936-120">Using .NET Framework on Docker can improve your deployment experiences by minimizing deployment issues.</span></span> <span data-ttu-id="9c936-121">Данный [сценарий "подъема и смены"](https://aka.ms/liftandshiftwithcontainersebook) важен для контейнеризации приложений прежних версий, которые изначально были разработаны с использованием классической платформы .NET Framework, например ASP.NET WebForms, веб-приложений MVC или служб WCF (Windows Communication Foundation).</span><span class="sxs-lookup"><span data-stu-id="9c936-121">This ["lift and shift" scenario](https://aka.ms/liftandshiftwithcontainersebook) is important for containerizing legacy applications that were originally developed with the traditional .NET Framework, like ASP.NET WebForms, MVC web apps or WCF (Windows Communication Foundation) services.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="9c936-122">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="9c936-122">Additional resources</span></span>

- <span data-ttu-id="9c936-123">**Электронная книга: модернизация существующих приложений .NET Framework с помощью Azure и контейнеров Windows**</span><span class="sxs-lookup"><span data-stu-id="9c936-123">**eBook: Modernize existing .NET Framework applications with Azure and Windows Containers**</span></span>  
    https://aka.ms/liftandshiftwithcontainersebook

- <span data-ttu-id="9c936-124">**Примеры приложений: модернизация устаревших веб-приложений ASP.NET с помощью контейнеров Windows**</span><span class="sxs-lookup"><span data-stu-id="9c936-124">**Sample apps: Modernization of legacy ASP.NET web apps by using Windows Containers**</span></span>  
    https://aka.ms/eshopmodernizing

>[!div class="step-by-step"]
><span data-ttu-id="9c936-125">[Назад](index.md)
>[Вперед](net-core-container-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="9c936-125">[Previous](index.md)
[Next](net-core-container-scenarios.md)</span></span>