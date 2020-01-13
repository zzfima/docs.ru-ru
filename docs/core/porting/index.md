---
title: Перенос кода из .NET Framework в .NET Core
description: Общие сведения о процессе переноса и инструментах, которые могут оказаться полезными при переносе проектов .NET Framework в .NET Core.
author: cartermp
ms.date: 10/22/2019
ms.openlocfilehash: b5b010acbccf134afe800aa5bb98a0ae6e9ffa25
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777361"
---
# <a name="overview-of-porting-from-net-framework-to-net-core"></a><span data-ttu-id="89330-103">Общие сведения о переносе кода в .NET Core из .NET Framework</span><span class="sxs-lookup"><span data-stu-id="89330-103">Overview of porting from .NET Framework to .NET Core</span></span>

<span data-ttu-id="89330-104">Возможно, у вас есть код, который сейчас выполняется в .NET Framework, и вы хотите перенести его в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="89330-104">You might have code that currently runs on the .NET Framework that you're interested in porting to .NET Core.</span></span> <span data-ttu-id="89330-105">В этой статье приводится следующее:</span><span class="sxs-lookup"><span data-stu-id="89330-105">This article provides:</span></span>

* <span data-ttu-id="89330-106">Общие сведения о переносе.</span><span class="sxs-lookup"><span data-stu-id="89330-106">An overview of the porting process.</span></span>
* <span data-ttu-id="89330-107">Список средств, которые могут оказаться полезными при переносе кода в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="89330-107">A list of tools that you may find helpful when you're porting your code to .NET Core.</span></span>

## <a name="overview-of-the-porting-process"></a><span data-ttu-id="89330-108">Общие сведения о переносе</span><span class="sxs-lookup"><span data-stu-id="89330-108">Overview of the porting process</span></span>

<span data-ttu-id="89330-109">Мы рекомендуем следовать следующему процессу при переносе проекта в .NET Core:</span><span class="sxs-lookup"><span data-stu-id="89330-109">We recommend you use the following process when porting your project to .NET Core:</span></span>

1. <span data-ttu-id="89330-110">Перенацельте все переносимые проекты на .NET Framework 4.7.2 и более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="89330-110">Retarget all projects you wish to port to target .NET Framework 4.7.2 or higher.</span></span>

   <span data-ttu-id="89330-111">Так вы сможете использовать альтернативные API для целевых платформ .NET Framework в случае, если платформа .NET Core не поддерживает определенный API.</span><span class="sxs-lookup"><span data-stu-id="89330-111">This step ensures that you can use API alternatives for .NET Framework-specific targets when .NET Core doesn't support a particular API.</span></span>

2. <span data-ttu-id="89330-112">Чтобы выполнить анализ сборок и узнать, можно ли их перенести в .NET Core, используйте [анализатор переносимости .NET](../../standard/analyzers/portability-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="89330-112">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to analyze your assemblies and see if they're portable to .NET Core.</span></span>

   <span data-ttu-id="89330-113">Средство анализатора переносимости API позволяет проанализировать скомпилированные сборки и создать отчет.</span><span class="sxs-lookup"><span data-stu-id="89330-113">The API Portability Analyzer tool analyzes your compiled assemblies and generates a report.</span></span> <span data-ttu-id="89330-114">В этом отчете представлена сводная информация о переносимости и разбивка по каждому используемому API, недоступному в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="89330-114">This report shows a high-level portability summary and a breakdown of each API you're using that isn't available on NET Core.</span></span>

3. <span data-ttu-id="89330-115">Установите [анализатор API .NET](../../standard/analyzers/api-analyzer.md) в проектах, чтобы узнать, какие интерфейсы API выдают исключение <xref:System.PlatformNotSupportedException> на отдельных платформах и другие потенциальные проблемы совместимости.</span><span class="sxs-lookup"><span data-stu-id="89330-115">Install the [.NET API analyzer](../../standard/analyzers/api-analyzer.md) into your projects to identify APIs throwing <xref:System.PlatformNotSupportedException> on some platforms and some other potential compatibility issues.</span></span>

   <span data-ttu-id="89330-116">Это средство подобно анализатору переносимости. Но вместо анализа того, можно ли создать элементы на платформе .NET Core, оно анализирует использование API на предмет действий, которые могут вызвать <xref:System.PlatformNotSupportedException> во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="89330-116">This tool is similar to the portability analyzer, but instead of analyzing if things can build on .NET Core, it analyzes if you're using an API in a way that will throw the <xref:System.PlatformNotSupportedException> at run time.</span></span> <span data-ttu-id="89330-117">Хотя такая проверка обычно не выполняется при переходе с .NET Framework 4.7.2 и более поздних версий, ее стоит выполнить.</span><span class="sxs-lookup"><span data-stu-id="89330-117">Although this isn't common if you're moving from .NET Framework 4.7.2 or higher, it's good to check.</span></span>

4. <span data-ttu-id="89330-118">Преобразуйте все зависимости `packages.config` в формат [PackageReference](/nuget/consume-packages/package-references-in-project-files) с помощью [средства преобразования в Visual Studio](/nuget/consume-packages/migrate-packages-config-to-package-reference).</span><span class="sxs-lookup"><span data-stu-id="89330-118">Convert all of your `packages.config` dependencies to the [PackageReference](/nuget/consume-packages/package-references-in-project-files) format with the [conversion tool in Visual Studio](/nuget/consume-packages/migrate-packages-config-to-package-reference).</span></span>

   <span data-ttu-id="89330-119">На этом шаге выполняется преобразование зависимостей из устаревшего формата `packages.config`.</span><span class="sxs-lookup"><span data-stu-id="89330-119">This step involves converting your dependencies from the legacy `packages.config` format.</span></span> <span data-ttu-id="89330-120">Формат `packages.config` не поддерживается в .NET Core, поэтому такое преобразование является обязательным при наличии зависимостей пакетов.</span><span class="sxs-lookup"><span data-stu-id="89330-120">`packages.config` doesn't work on .NET Core, so this conversion is required if you have package dependencies.</span></span>

5. <span data-ttu-id="89330-121">Создайте проекты для .NET Core, скопируйте исходные файлы или попытайтесь преобразовать существующий файл проекта с помощью средства.</span><span class="sxs-lookup"><span data-stu-id="89330-121">Create new projects for .NET Core and copy over source files, or attempt to convert your existing project file with a tool.</span></span>

   <span data-ttu-id="89330-122">В .NET Core используется более простой (и другой) [формат файла проекта](../tools/csproj.md), чем в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="89330-122">.NET Core uses a simplified (and different) [project file format](../tools/csproj.md) than .NET Framework.</span></span> <span data-ttu-id="89330-123">Чтобы продолжить, потребуется преобразовать файлы проекта в этот формат.</span><span class="sxs-lookup"><span data-stu-id="89330-123">You'll need to convert your project files into this format to continue.</span></span>

6. <span data-ttu-id="89330-124">Перенесите код тестов.</span><span class="sxs-lookup"><span data-stu-id="89330-124">Port your test code.</span></span>

   <span data-ttu-id="89330-125">Так как перенос в .NET Core является важным изменением базы кода, мы настоятельно рекомендуем перенести тестовые проекты, чтобы можно было выполнять тесты при переносе кода.</span><span class="sxs-lookup"><span data-stu-id="89330-125">Because porting to .NET Core is such a significant change to your codebase, it's highly recommended to port your test projects so that you can run tests as you port your code over.</span></span> <span data-ttu-id="89330-126">.NET Core поддерживает все основные платформы: MSTest, xUnit и NUnit.</span><span class="sxs-lookup"><span data-stu-id="89330-126">MSTest, xUnit, and NUnit all work on .NET Core.</span></span>

<span data-ttu-id="89330-127">Кроме того, можно попытаться перенести за одну операцию более мелкие решения или отдельные проекты в формат файла проекта .NET Core с помощью средства [dotnet try-convert](https://github.com/dotnet/try-convert).</span><span class="sxs-lookup"><span data-stu-id="89330-127">Additionally, you can attempt to port smaller solutions or individual projects in one operation to the .NET Core project file format with the [dotnet try-convert](https://github.com/dotnet/try-convert) tool.</span></span> <span data-ttu-id="89330-128">Нет гарантии, что `dotnet try-convert` будет поддерживать все проекты. Кроме того, оно может вызвать незначительные изменения в ожидаемом поведении.</span><span class="sxs-lookup"><span data-stu-id="89330-128">`dotnet try-convert` is not guaranteed to work for all your projects, and it may cause subtle changes in behavior that you depended on.</span></span> <span data-ttu-id="89330-129">Используйте это средство в качестве _начальной точки_, которая автоматизирует соответствующие основные процессы.</span><span class="sxs-lookup"><span data-stu-id="89330-129">Use it as a _starting point_ that automates the basic things that can be automated.</span></span> <span data-ttu-id="89330-130">Это решение не может гарантировать перенос проекта.</span><span class="sxs-lookup"><span data-stu-id="89330-130">It isn't a guaranteed solution to migrating a project.</span></span>

## <a name="next-steps"></a><span data-ttu-id="89330-131">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="89330-131">Next steps</span></span>

>[!div class="nextstepaction"]
>[<span data-ttu-id="89330-132">Недоступные в .NET Core технологии</span><span class="sxs-lookup"><span data-stu-id="89330-132">Unavailable technologies on .NET Core</span></span>](net-framework-tech-unavailable.md)
