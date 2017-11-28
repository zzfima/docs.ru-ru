---
title: "Перенос кода в .NET Core из .NET Framework"
description: "Общие сведения о процессе переноса и инструментах, которые могут оказаться полезными при переносе проектов .NET Framework в .NET Core."
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 00d00d38-99af-44f4-a75f-defcd9729dc5
ms.openlocfilehash: 4fc68a3dbdec634d8e92a066a46939ba19c65db7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="porting-to-net-core-from-net-framework"></a><span data-ttu-id="7fd15-104">Перенос кода в .NET Core из .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7fd15-104">Porting to .NET Core from .NET Framework</span></span>

<span data-ttu-id="7fd15-105">Если у вас есть код, выполняющийся в .NET Framework, вам может потребоваться обеспечить его выполнение в .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="7fd15-105">If you've got code running on the .NET Framework, you may be interested in running your code on .NET Core 1.0.</span></span>  <span data-ttu-id="7fd15-106">В этой статье приводятся общие сведения о процессе переноса и перечислены средства, которые могут оказаться полезными при переносе кода в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7fd15-106">This article covers an overview of the porting process and a list of the tools you may find helpful when porting to .NET Core.</span></span>

## <a name="overview-of-the-porting-process"></a><span data-ttu-id="7fd15-107">Обзор процесса переноса</span><span class="sxs-lookup"><span data-stu-id="7fd15-107">Overview of the Porting Process</span></span>

<span data-ttu-id="7fd15-108">Рекомендуемый процесс переноса состоит из описанной ниже последовательности действий.</span><span class="sxs-lookup"><span data-stu-id="7fd15-108">The recommended process for porting follows the following series of steps.</span></span>  <span data-ttu-id="7fd15-109">Каждый из этапов процесса более подробно рассматривается в последующих статьях.</span><span class="sxs-lookup"><span data-stu-id="7fd15-109">Each of these parts of the process are covered in more detail in further articles.</span></span>

1. <span data-ttu-id="7fd15-110">Определите и проанализируйте зависимости сторонних разработчиков.</span><span class="sxs-lookup"><span data-stu-id="7fd15-110">Identify and account for your third-party dependencies.</span></span>

   <span data-ttu-id="7fd15-111">Вам необходимо понять, какие зависимости сторонних разработчиков имеются, как они используются, как узнать, могут ли они выполняться в .NET Core, и что нужно сделать, если не могут.</span><span class="sxs-lookup"><span data-stu-id="7fd15-111">This will involve understanding what your third-party dependencies are, how you depend on them, how to see if they also run on .NET Core, and steps you can take if they don't.</span></span>
   
2. <span data-ttu-id="7fd15-112">Перенацельте все переносимые проекты на .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="7fd15-112">Retarget all projects you wish to port to target .NET Framework 4.6.2.</span></span>

   <span data-ttu-id="7fd15-113">Это позволит использовать альтернативные интерфейсы API для целевых платформ .NET Framework в случае, если платформа .NET Core не поддерживает определенный интерфейс API.</span><span class="sxs-lookup"><span data-stu-id="7fd15-113">This ensures that you can use API alternatives for .NET Framework-specific targets in the cases where .NET Core can't support a particular API.</span></span>
   
3. <span data-ttu-id="7fd15-114">Используйте средство [Анализатор переносимости API](https://github.com/Microsoft/dotnet-apiport/) для анализа сборок и разработки плана переноса на основе результатов.</span><span class="sxs-lookup"><span data-stu-id="7fd15-114">Use the [API Portability Analyzer tool](https://github.com/Microsoft/dotnet-apiport/) to analyze your assemblies and develop a plan to port based on its results.</span></span>

   <span data-ttu-id="7fd15-115">Анализатор переносимости API анализирует скомпилированные сборки и создает отчет, в котором приводятся обобщенные сведения о переносимости, а также информация с разбивкой по каждому используемому интерфейсу API, который недоступен в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7fd15-115">The API Portability Analyzer tool will analyze your compiled assemblies and generate a report which shows a high-level portability summary and a breakdown of each API you're using that isn't available on .NET Core.</span></span>  <span data-ttu-id="7fd15-116">Этот отчет можно использовать вместе с результатами анализа базы кода для составления плана переноса кода.</span><span class="sxs-lookup"><span data-stu-id="7fd15-116">You can use this report alongside an analysis of your codebase to develop a plan for how you'll port your code over.</span></span>
   
4. <span data-ttu-id="7fd15-117">Перенести код тестов.</span><span class="sxs-lookup"><span data-stu-id="7fd15-117">Port your tests code.</span></span>

   <span data-ttu-id="7fd15-118">Так как перенос в .NET Core является важным изменением для базы кода, настоятельно рекомендуется перенести тесты, чтобы можно было выполнять их в процессе переноса кода.</span><span class="sxs-lookup"><span data-stu-id="7fd15-118">Because porting to .NET Core is such a big change to your codebase, it's highly recommended to get your tests ported so that you can run tests as you port code over.</span></span>  <span data-ttu-id="7fd15-119">В настоящее время платформа .NET Core 1.0 поддерживается всеми основными средствами: MSTest, xUnit и NUnit.</span><span class="sxs-lookup"><span data-stu-id="7fd15-119">MSTest, xUnit, and NUnit all support .NET Core 1.0 today.</span></span>
   
6. <span data-ttu-id="7fd15-120">Выполните план переноса.</span><span class="sxs-lookup"><span data-stu-id="7fd15-120">Execute your plan for porting!</span></span>

## <a name="tools-to-help"></a><span data-ttu-id="7fd15-121">Полезные средства</span><span class="sxs-lookup"><span data-stu-id="7fd15-121">Tools to help</span></span>

<span data-ttu-id="7fd15-122">Ниже приведен краткий список средств, которые могут вам помочь.</span><span class="sxs-lookup"><span data-stu-id="7fd15-122">Here's a short list of the tools you'll find helpful:</span></span>

* <span data-ttu-id="7fd15-123">NuGet — [клиент Nuget](https://dist.nuget.org/index.html) или [обозреватель пакетов NuGet](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) — диспетчер пакетов Майкрософт для реализаций .NET.</span><span class="sxs-lookup"><span data-stu-id="7fd15-123">NuGet - [Nuget Client](https://dist.nuget.org/index.html) or [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer), Microsoft's package manager for .NET implementations.</span></span>
* <span data-ttu-id="7fd15-124">Анализатор переносимости API — [программа командной строки](https://github.com/Microsoft/dotnet-apiport/releases) или [расширение для Visual Studio Extension](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b) — цепочка инструментов, позволяющая создавать отчеты о переносимости кода между .NET Framework и .NET Core с разбивкой проблем по сборкам.</span><span class="sxs-lookup"><span data-stu-id="7fd15-124">Api Portability Analyzer - [command line tool](https://github.com/Microsoft/dotnet-apiport/releases) or [Visual Studio Extension](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b), a toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core, with an assembly-by-assembly breakdown of issues.</span></span>  <span data-ttu-id="7fd15-125">Дополнительные сведения см. в разделе [Полезные инструменты](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/).</span><span class="sxs-lookup"><span data-stu-id="7fd15-125">See [Tooling to help you on the process](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/) for more information.</span></span>
* <span data-ttu-id="7fd15-126">Reverse Package Search — [полезная веб-служба](https://packagesearch.azurewebsites.net), которая позволяет выполнять поиск типа и находить пакеты, содержащие его.</span><span class="sxs-lookup"><span data-stu-id="7fd15-126">Reverse Package Search - A [useful web service](https://packagesearch.azurewebsites.net) that allows you to search for a type and find packages containing that type.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7fd15-127">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="7fd15-127">Next steps</span></span>

[<span data-ttu-id="7fd15-128">Анализ сторонних зависимостей.</span><span class="sxs-lookup"><span data-stu-id="7fd15-128">Analyzing your third-party dependencies.</span></span>](third-party-deps.md)
   
