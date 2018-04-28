---
title: Перенос кода в .NET Core из .NET Framework
description: Общие сведения о процессе переноса и инструментах, которые могут оказаться полезными при переносе проектов .NET Framework в .NET Core.
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: conceptual
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 2f943caff23ddbfcd5c845c9f517d24aea089850
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="porting-to-net-core-from-net-framework"></a><span data-ttu-id="836ad-103">Перенос кода в .NET Core из .NET Framework</span><span class="sxs-lookup"><span data-stu-id="836ad-103">Porting to .NET Core from .NET Framework</span></span>

<span data-ttu-id="836ad-104">Если у вас есть код, выполняющийся в .NET Framework, вам может потребоваться обеспечить его выполнение в .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="836ad-104">If you've got code running on the .NET Framework, you may be interested in running your code on .NET Core 1.0.</span></span>  <span data-ttu-id="836ad-105">В этой статье приводятся общие сведения о процессе переноса и перечислены средства, которые могут оказаться полезными при переносе кода в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="836ad-105">This article covers an overview of the porting process and a list of the tools you may find helpful when porting to .NET Core.</span></span>

## <a name="overview-of-the-porting-process"></a><span data-ttu-id="836ad-106">Обзор процесса переноса</span><span class="sxs-lookup"><span data-stu-id="836ad-106">Overview of the Porting Process</span></span>

<span data-ttu-id="836ad-107">Рекомендуемый процесс переноса состоит из описанной ниже последовательности действий.</span><span class="sxs-lookup"><span data-stu-id="836ad-107">The recommended process for porting follows the following series of steps.</span></span>  <span data-ttu-id="836ad-108">Каждый из этапов процесса более подробно рассматривается в последующих статьях.</span><span class="sxs-lookup"><span data-stu-id="836ad-108">Each of these parts of the process are covered in more detail in further articles.</span></span>

1. <span data-ttu-id="836ad-109">Определите и проанализируйте зависимости сторонних разработчиков.</span><span class="sxs-lookup"><span data-stu-id="836ad-109">Identify and account for your third-party dependencies.</span></span>

   <span data-ttu-id="836ad-110">Вам необходимо понять, какие зависимости сторонних разработчиков имеются, как они используются, как узнать, могут ли они выполняться в .NET Core, и что нужно сделать, если не могут.</span><span class="sxs-lookup"><span data-stu-id="836ad-110">This will involve understanding what your third-party dependencies are, how you depend on them, how to see if they also run on .NET Core, and steps you can take if they don't.</span></span>
   
2. <span data-ttu-id="836ad-111">Перенацельте все переносимые проекты на .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="836ad-111">Retarget all projects you wish to port to target .NET Framework 4.6.2.</span></span>

   <span data-ttu-id="836ad-112">Это позволит использовать альтернативные интерфейсы API для целевых платформ .NET Framework в случае, если платформа .NET Core не поддерживает определенный интерфейс API.</span><span class="sxs-lookup"><span data-stu-id="836ad-112">This ensures that you can use API alternatives for .NET Framework-specific targets in the cases where .NET Core can't support a particular API.</span></span>
   
3. <span data-ttu-id="836ad-113">Используйте средство [Анализатор переносимости API](https://github.com/Microsoft/dotnet-apiport/) для анализа сборок и разработки плана переноса на основе результатов.</span><span class="sxs-lookup"><span data-stu-id="836ad-113">Use the [API Portability Analyzer tool](https://github.com/Microsoft/dotnet-apiport/) to analyze your assemblies and develop a plan to port based on its results.</span></span>

   <span data-ttu-id="836ad-114">Анализатор переносимости API анализирует скомпилированные сборки и создает отчет, в котором приводятся обобщенные сведения о переносимости, а также информация с разбивкой по каждому используемому интерфейсу API, который недоступен в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="836ad-114">The API Portability Analyzer tool will analyze your compiled assemblies and generate a report which shows a high-level portability summary and a breakdown of each API you're using that isn't available on .NET Core.</span></span>  <span data-ttu-id="836ad-115">Этот отчет можно использовать вместе с результатами анализа базы кода для составления плана переноса кода.</span><span class="sxs-lookup"><span data-stu-id="836ad-115">You can use this report alongside an analysis of your codebase to develop a plan for how you'll port your code over.</span></span>
   
4. <span data-ttu-id="836ad-116">Перенести код тестов.</span><span class="sxs-lookup"><span data-stu-id="836ad-116">Port your tests code.</span></span>

   <span data-ttu-id="836ad-117">Так как перенос в .NET Core является важным изменением для базы кода, настоятельно рекомендуется перенести тесты, чтобы можно было выполнять их в процессе переноса кода.</span><span class="sxs-lookup"><span data-stu-id="836ad-117">Because porting to .NET Core is such a big change to your codebase, it's highly recommended to get your tests ported so that you can run tests as you port code over.</span></span>  <span data-ttu-id="836ad-118">В настоящее время платформа .NET Core 1.0 поддерживается всеми основными средствами: MSTest, xUnit и NUnit.</span><span class="sxs-lookup"><span data-stu-id="836ad-118">MSTest, xUnit, and NUnit all support .NET Core 1.0 today.</span></span>
   
6. <span data-ttu-id="836ad-119">Выполните план переноса.</span><span class="sxs-lookup"><span data-stu-id="836ad-119">Execute your plan for porting!</span></span>

## <a name="tools-to-help"></a><span data-ttu-id="836ad-120">Полезные средства</span><span class="sxs-lookup"><span data-stu-id="836ad-120">Tools to help</span></span>

<span data-ttu-id="836ad-121">Ниже приведен краткий список средств, которые могут вам помочь.</span><span class="sxs-lookup"><span data-stu-id="836ad-121">Here's a short list of the tools you'll find helpful:</span></span>

* <span data-ttu-id="836ad-122">NuGet — [клиент Nuget](https://dist.nuget.org/index.html) или [обозреватель пакетов NuGet](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) — диспетчер пакетов Майкрософт для реализаций .NET.</span><span class="sxs-lookup"><span data-stu-id="836ad-122">NuGet - [Nuget Client](https://dist.nuget.org/index.html) or [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer), Microsoft's package manager for .NET implementations.</span></span>
* <span data-ttu-id="836ad-123">Анализатор переносимости API — [программа командной строки](https://github.com/Microsoft/dotnet-apiport/releases) или [расширение для Visual Studio Extension](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b) — цепочка инструментов, позволяющая создавать отчеты о переносимости кода между .NET Framework и .NET Core с разбивкой проблем по сборкам.</span><span class="sxs-lookup"><span data-stu-id="836ad-123">Api Portability Analyzer - [command line tool](https://github.com/Microsoft/dotnet-apiport/releases) or [Visual Studio Extension](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b), a toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core, with an assembly-by-assembly breakdown of issues.</span></span>  <span data-ttu-id="836ad-124">Дополнительные сведения см. в разделе [Полезные инструменты](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/).</span><span class="sxs-lookup"><span data-stu-id="836ad-124">See [Tooling to help you on the process](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/) for more information.</span></span>
* <span data-ttu-id="836ad-125">Reverse Package Search — [полезная веб-служба](https://packagesearch.azurewebsites.net), которая позволяет выполнять поиск типа и находить пакеты, содержащие его.</span><span class="sxs-lookup"><span data-stu-id="836ad-125">Reverse Package Search - A [useful web service](https://packagesearch.azurewebsites.net) that allows you to search for a type and find packages containing that type.</span></span>

## <a name="next-steps"></a><span data-ttu-id="836ad-126">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="836ad-126">Next steps</span></span>

[<span data-ttu-id="836ad-127">Анализ сторонних зависимостей.</span><span class="sxs-lookup"><span data-stu-id="836ad-127">Analyzing your third-party dependencies.</span></span>](third-party-deps.md)
   
