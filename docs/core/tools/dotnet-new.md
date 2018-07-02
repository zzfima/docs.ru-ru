---
title: Команда dotnet new — интерфейс командной строки .NET Core
description: Команда dotnet new создает проекты .NET Core на основе указанного шаблона.
author: mairaw
ms.author: mairaw
ms.date: 06/12/2018
ms.openlocfilehash: f0ef91361dfbc2c2ba5532fbd607786289e98c69
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207813"
---
# <a name="dotnet-new"></a><span data-ttu-id="e0add-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="e0add-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="e0add-104">name</span><span class="sxs-lookup"><span data-stu-id="e0add-104">Name</span></span>

<span data-ttu-id="e0add-105">`dotnet new` — создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="e0add-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e0add-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e0add-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e0add-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e0add-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e0add-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e0add-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e0add-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e0add-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="e0add-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="e0add-110">Description</span></span>

<span data-ttu-id="e0add-111">Команда `dotnet new` предоставляет удобный способ инициализации проекта .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e0add-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="e0add-112">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="e0add-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="e0add-113">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e0add-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="e0add-114">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="e0add-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="e0add-115">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="e0add-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="e0add-116">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="e0add-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e0add-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e0add-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="e0add-118">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e0add-118">The command contains a default list of templates.</span></span> <span data-ttu-id="e0add-119">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="e0add-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="e0add-120">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="e0add-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="e0add-121">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="e0add-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="e0add-122">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="e0add-122">Template description</span></span>                          | <span data-ttu-id="e0add-123">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="e0add-123">Template name</span></span>   | <span data-ttu-id="e0add-124">Языки</span><span class="sxs-lookup"><span data-stu-id="e0add-124">Languages</span></span>     |
|----------------------------------------------|-----------------|---------------|
| <span data-ttu-id="e0add-125">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="e0add-125">Console application</span></span>                          | `console`       | <span data-ttu-id="e0add-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e0add-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e0add-127">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="e0add-127">Class library</span></span>                                | `classlib`      | <span data-ttu-id="e0add-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e0add-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e0add-129">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="e0add-129">Unit test project</span></span>                            | `mstest`        | <span data-ttu-id="e0add-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e0add-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e0add-131">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="e0add-131">xUnit test project</span></span>                           | `xunit`         | <span data-ttu-id="e0add-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e0add-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e0add-133">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="e0add-133">Razor page</span></span>                                   | `page`          | <span data-ttu-id="e0add-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0add-134">[C#]</span></span>          |
| <span data-ttu-id="e0add-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="e0add-135">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="e0add-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0add-136">[C#]</span></span>          |
| <span data-ttu-id="e0add-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="e0add-137">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="e0add-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0add-138">[C#]</span></span>          |
| <span data-ttu-id="e0add-139">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e0add-139">ASP.NET Core empty</span></span>                           | `web`           | <span data-ttu-id="e0add-140">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e0add-140">[C#], F#</span></span>      |
| <span data-ttu-id="e0add-141">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="e0add-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="e0add-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e0add-142">[C#], F#</span></span>      |
| <span data-ttu-id="e0add-143">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e0add-143">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="e0add-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0add-144">[C#]</span></span>          |
| <span data-ttu-id="e0add-145">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="e0add-145">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="e0add-146">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0add-146">[C#]</span></span>          |
| <span data-ttu-id="e0add-147">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="e0add-147">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="e0add-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0add-148">[C#]</span></span>          |
| <span data-ttu-id="e0add-149">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="e0add-149">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="e0add-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0add-150">[C#]</span></span>          |
| <span data-ttu-id="e0add-151">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e0add-151">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="e0add-152">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e0add-152">[C#], F#</span></span>      |
| <span data-ttu-id="e0add-153">Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="e0add-153">Razor class library</span></span>                          | `razorclasslib` | <span data-ttu-id="e0add-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0add-154">[C#]</span></span>          |
| <span data-ttu-id="e0add-155">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="e0add-155">global.json file</span></span>                             | `globaljson`    |               |
| <span data-ttu-id="e0add-156">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="e0add-156">NuGet config</span></span>                                 | `nugetconfig`   |               |
| <span data-ttu-id="e0add-157">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="e0add-157">Web config</span></span>                                   | `webconfig`     |               |
| <span data-ttu-id="e0add-158">Файл решения</span><span class="sxs-lookup"><span data-stu-id="e0add-158">Solution file</span></span>                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e0add-159">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e0add-159">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="e0add-160">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e0add-160">The command contains a default list of templates.</span></span> <span data-ttu-id="e0add-161">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="e0add-161">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="e0add-162">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="e0add-162">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="e0add-163">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="e0add-163">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="e0add-164">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="e0add-164">Template description</span></span>                          | <span data-ttu-id="e0add-165">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="e0add-165">Template name</span></span> | <span data-ttu-id="e0add-166">Языки</span><span class="sxs-lookup"><span data-stu-id="e0add-166">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="e0add-167">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="e0add-167">Console application</span></span>                          | `console`     | <span data-ttu-id="e0add-168">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e0add-168">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e0add-169">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="e0add-169">Class library</span></span>                                | `classlib`    | <span data-ttu-id="e0add-170">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e0add-170">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e0add-171">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="e0add-171">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="e0add-172">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e0add-172">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e0add-173">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="e0add-173">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="e0add-174">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e0add-174">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e0add-175">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e0add-175">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="e0add-176">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e0add-176">[C#], F#</span></span>      |
| <span data-ttu-id="e0add-177">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="e0add-177">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="e0add-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e0add-178">[C#], F#</span></span>      |
| <span data-ttu-id="e0add-179">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e0add-179">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="e0add-180">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0add-180">[C#]</span></span>          |
| <span data-ttu-id="e0add-181">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="e0add-181">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="e0add-182">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0add-182">[C#]</span></span>          |
| <span data-ttu-id="e0add-183">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="e0add-183">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="e0add-184">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0add-184">[C#]</span></span>          |
| <span data-ttu-id="e0add-185">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="e0add-185">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="e0add-186">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0add-186">[C#]</span></span>          |
| <span data-ttu-id="e0add-187">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e0add-187">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="e0add-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e0add-188">[C#], F#</span></span>      |
| <span data-ttu-id="e0add-189">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="e0add-189">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="e0add-190">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="e0add-190">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="e0add-191">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="e0add-191">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="e0add-192">Файл решения</span><span class="sxs-lookup"><span data-stu-id="e0add-192">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="e0add-193">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="e0add-193">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="e0add-194">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="e0add-194">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="e0add-195">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="e0add-195">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e0add-196">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e0add-196">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="e0add-197">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e0add-197">The command contains a default list of templates.</span></span> <span data-ttu-id="e0add-198">Используйте `dotnet new -all`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="e0add-198">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="e0add-199">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="e0add-199">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="e0add-200">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="e0add-200">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="e0add-201">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="e0add-201">Template description</span></span>  | <span data-ttu-id="e0add-202">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="e0add-202">Template name</span></span> | <span data-ttu-id="e0add-203">Языки</span><span class="sxs-lookup"><span data-stu-id="e0add-203">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="e0add-204">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="e0add-204">Console application</span></span>  | `console`     | <span data-ttu-id="e0add-205">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e0add-205">[C#], F#</span></span>  |
| <span data-ttu-id="e0add-206">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="e0add-206">Class library</span></span>        | `classlib`    | <span data-ttu-id="e0add-207">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e0add-207">[C#], F#</span></span>  |
| <span data-ttu-id="e0add-208">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="e0add-208">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="e0add-209">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e0add-209">[C#], F#</span></span>  |
| <span data-ttu-id="e0add-210">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="e0add-210">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="e0add-211">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e0add-211">[C#], F#</span></span>  |
| <span data-ttu-id="e0add-212">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e0add-212">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="e0add-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0add-213">[C#]</span></span>      |
| <span data-ttu-id="e0add-214">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e0add-214">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="e0add-215">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e0add-215">[C#], F#</span></span>  |
| <span data-ttu-id="e0add-216">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e0add-216">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="e0add-217">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0add-217">[C#]</span></span>      |
| <span data-ttu-id="e0add-218">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="e0add-218">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="e0add-219">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="e0add-219">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="e0add-220">Файл решения</span><span class="sxs-lookup"><span data-stu-id="e0add-220">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="e0add-221">Параметры</span><span class="sxs-lookup"><span data-stu-id="e0add-221">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e0add-222">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e0add-222">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="e0add-223">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="e0add-223">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="e0add-224">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="e0add-224">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="e0add-225">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="e0add-225">Prints out help for the command.</span></span> <span data-ttu-id="e0add-226">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="e0add-226">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="e0add-227">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="e0add-227">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="e0add-228">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="e0add-228">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="e0add-229">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="e0add-229">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="e0add-230">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="e0add-230">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="e0add-231">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="e0add-231">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="e0add-232">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="e0add-232">Lists templates containing the specified name.</span></span> <span data-ttu-id="e0add-233">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="e0add-233">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="e0add-234">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="e0add-234">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="e0add-235">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e0add-235">The language of the template to create.</span></span> <span data-ttu-id="e0add-236">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="e0add-236">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="e0add-237">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="e0add-237">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="e0add-238">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="e0add-238">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="e0add-239">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="e0add-239">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="e0add-240">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e0add-240">The name for the created output.</span></span> <span data-ttu-id="e0add-241">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="e0add-241">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="e0add-242">Задает источник пакетов NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="e0add-242">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="e0add-243">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="e0add-243">Location to place the generated output.</span></span> <span data-ttu-id="e0add-244">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="e0add-244">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="e0add-245">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="e0add-245">Filters templates based on available types.</span></span> <span data-ttu-id="e0add-246">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="e0add-246">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="e0add-247">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="e0add-247">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="e0add-248">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="e0add-248">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="e0add-249">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="e0add-249">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="e0add-250">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="e0add-250">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e0add-251">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e0add-251">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="e0add-252">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="e0add-252">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="e0add-253">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="e0add-253">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="e0add-254">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="e0add-254">Prints out help for the command.</span></span> <span data-ttu-id="e0add-255">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="e0add-255">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="e0add-256">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="e0add-256">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="e0add-257">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="e0add-257">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="e0add-258">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="e0add-258">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="e0add-259">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="e0add-259">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="e0add-260">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="e0add-260">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="e0add-261">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="e0add-261">Lists templates containing the specified name.</span></span> <span data-ttu-id="e0add-262">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="e0add-262">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="e0add-263">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="e0add-263">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="e0add-264">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e0add-264">The language of the template to create.</span></span> <span data-ttu-id="e0add-265">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="e0add-265">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="e0add-266">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="e0add-266">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="e0add-267">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="e0add-267">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="e0add-268">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="e0add-268">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="e0add-269">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e0add-269">The name for the created output.</span></span> <span data-ttu-id="e0add-270">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="e0add-270">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="e0add-271">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="e0add-271">Location to place the generated output.</span></span> <span data-ttu-id="e0add-272">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="e0add-272">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="e0add-273">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="e0add-273">Filters templates based on available types.</span></span> <span data-ttu-id="e0add-274">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="e0add-274">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="e0add-275">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="e0add-275">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="e0add-276">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="e0add-276">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="e0add-277">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="e0add-277">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="e0add-278">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="e0add-278">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e0add-279">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e0add-279">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="e0add-280">Показывает все шаблоны определенного типа проекта при запуске в контексте одной только команды `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="e0add-280">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="e0add-281">При запуске в контексте конкретного шаблона, например `dotnet new web -all`, `-all` интерпретируется как флаг принудительного создания.</span><span class="sxs-lookup"><span data-stu-id="e0add-281">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="e0add-282">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="e0add-282">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="e0add-283">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="e0add-283">Prints out help for the command.</span></span> <span data-ttu-id="e0add-284">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="e0add-284">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="e0add-285">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="e0add-285">Lists templates containing the specified name.</span></span> <span data-ttu-id="e0add-286">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="e0add-286">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="e0add-287">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="e0add-287">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="e0add-288">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e0add-288">The language of the template to create.</span></span> <span data-ttu-id="e0add-289">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="e0add-289">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="e0add-290">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="e0add-290">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="e0add-291">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="e0add-291">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="e0add-292">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="e0add-292">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="e0add-293">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e0add-293">The name for the created output.</span></span> <span data-ttu-id="e0add-294">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="e0add-294">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="e0add-295">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="e0add-295">Location to place the generated output.</span></span> <span data-ttu-id="e0add-296">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="e0add-296">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="e0add-297">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="e0add-297">Template options</span></span>

<span data-ttu-id="e0add-298">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="e0add-298">Each project template may have additional options available.</span></span> <span data-ttu-id="e0add-299">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="e0add-299">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e0add-300">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e0add-300">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="e0add-301">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="e0add-301">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="e0add-302">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e0add-302">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0add-303">**classlib**</span><span class="sxs-lookup"><span data-stu-id="e0add-303">**classlib**</span></span>

<span data-ttu-id="e0add-304">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e0add-304">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e0add-305">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="e0add-305">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="e0add-306">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="e0add-306">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="e0add-307">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e0add-307">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0add-308">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="e0add-308">**mstest, xunit**</span></span>

<span data-ttu-id="e0add-309">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="e0add-309">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="e0add-310">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e0add-310">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0add-311">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="e0add-311">**globaljson**</span></span>

<span data-ttu-id="e0add-312">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="e0add-312">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="e0add-313">**web**</span><span class="sxs-lookup"><span data-stu-id="e0add-313">**web**</span></span>

<span data-ttu-id="e0add-314">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="e0add-314">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="e0add-315">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e0add-315">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0add-316">**webapi**</span><span class="sxs-lookup"><span data-stu-id="e0add-316">**webapi**</span></span>

<span data-ttu-id="e0add-317">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e0add-317">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="e0add-318">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="e0add-318">The possible values are:</span></span>

- <span data-ttu-id="e0add-319">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e0add-319">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="e0add-320">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e0add-320">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="e0add-321">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="e0add-321">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="e0add-322">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="e0add-322">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="e0add-323">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e0add-323">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e0add-324">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0add-324">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e0add-325">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e0add-325">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="e0add-326">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e0add-326">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e0add-327">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0add-327">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0add-328">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e0add-328">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e0add-329">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0add-329">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e0add-330">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e0add-330">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="e0add-331">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e0add-331">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="e0add-332">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0add-332">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="e0add-333">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e0add-333">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="e0add-334">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="e0add-334">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="e0add-335">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0add-335">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e0add-336">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e0add-336">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="e0add-337">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="e0add-337">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e0add-338">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0add-338">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e0add-339">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e0add-339">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="e0add-340">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="e0add-340">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="e0add-341">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0add-341">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="e0add-342">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="e0add-342">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="e0add-343">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e0add-343">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e0add-344">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0add-344">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0add-345">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e0add-345">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0add-346">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="e0add-346">**mvc, razor**</span></span>

<span data-ttu-id="e0add-347">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e0add-347">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="e0add-348">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="e0add-348">The possible values are:</span></span>

- <span data-ttu-id="e0add-349">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e0add-349">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="e0add-350">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e0add-350">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="e0add-351">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e0add-351">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="e0add-352">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="e0add-352">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="e0add-353">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="e0add-353">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="e0add-354">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="e0add-354">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="e0add-355">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e0add-355">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e0add-356">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0add-356">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e0add-357">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e0add-357">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="e0add-358">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e0add-358">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e0add-359">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0add-359">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0add-360">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e0add-360">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="e0add-361">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0add-361">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0add-362">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e0add-362">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="e0add-363">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0add-363">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0add-364">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e0add-364">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e0add-365">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0add-365">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="e0add-366">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e0add-366">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="e0add-367">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e0add-367">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="e0add-368">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0add-368">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="e0add-369">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e0add-369">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="e0add-370">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="e0add-370">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="e0add-371">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0add-371">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e0add-372">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e0add-372">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="e0add-373">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="e0add-373">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e0add-374">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0add-374">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e0add-375">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e0add-375">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="e0add-376">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="e0add-376">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="e0add-377">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0add-377">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e0add-378">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="e0add-378">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="e0add-379">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="e0add-379">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="e0add-380">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0add-380">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="e0add-381">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="e0add-381">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="e0add-382">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="e0add-382">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="e0add-383">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e0add-383">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e0add-384">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0add-384">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0add-385">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e0add-385">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0add-386">**page**</span><span class="sxs-lookup"><span data-stu-id="e0add-386">**page**</span></span>

<span data-ttu-id="e0add-387">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="e0add-387">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="e0add-388">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e0add-388">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="e0add-389">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="e0add-389">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="e0add-390">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="e0add-390">**viewimports**</span></span>

<span data-ttu-id="e0add-391">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="e0add-391">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="e0add-392">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e0add-392">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e0add-393">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e0add-393">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="e0add-394">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="e0add-394">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="e0add-395">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e0add-395">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0add-396">**classlib**</span><span class="sxs-lookup"><span data-stu-id="e0add-396">**classlib**</span></span>

<span data-ttu-id="e0add-397">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e0add-397">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e0add-398">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="e0add-398">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="e0add-399">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="e0add-399">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="e0add-400">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e0add-400">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0add-401">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="e0add-401">**mstest, xunit**</span></span>

<span data-ttu-id="e0add-402">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="e0add-402">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="e0add-403">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e0add-403">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0add-404">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="e0add-404">**globaljson**</span></span>

<span data-ttu-id="e0add-405">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="e0add-405">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="e0add-406">**web**</span><span class="sxs-lookup"><span data-stu-id="e0add-406">**web**</span></span>

<span data-ttu-id="e0add-407">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="e0add-407">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="e0add-408">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e0add-408">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0add-409">**webapi**</span><span class="sxs-lookup"><span data-stu-id="e0add-409">**webapi**</span></span>

<span data-ttu-id="e0add-410">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e0add-410">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="e0add-411">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="e0add-411">The possible values are:</span></span>

- <span data-ttu-id="e0add-412">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e0add-412">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="e0add-413">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e0add-413">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="e0add-414">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="e0add-414">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="e0add-415">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="e0add-415">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="e0add-416">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e0add-416">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e0add-417">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0add-417">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e0add-418">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e0add-418">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="e0add-419">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e0add-419">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e0add-420">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0add-420">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0add-421">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e0add-421">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e0add-422">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0add-422">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e0add-423">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e0add-423">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="e0add-424">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e0add-424">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="e0add-425">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0add-425">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="e0add-426">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e0add-426">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="e0add-427">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="e0add-427">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="e0add-428">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0add-428">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e0add-429">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e0add-429">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="e0add-430">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="e0add-430">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e0add-431">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0add-431">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e0add-432">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e0add-432">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="e0add-433">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="e0add-433">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="e0add-434">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0add-434">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="e0add-435">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="e0add-435">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="e0add-436">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e0add-436">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e0add-437">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0add-437">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0add-438">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e0add-438">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0add-439">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="e0add-439">**mvc, razor**</span></span>

<span data-ttu-id="e0add-440">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e0add-440">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="e0add-441">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="e0add-441">The possible values are:</span></span>

- <span data-ttu-id="e0add-442">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e0add-442">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="e0add-443">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e0add-443">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="e0add-444">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e0add-444">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="e0add-445">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="e0add-445">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="e0add-446">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="e0add-446">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="e0add-447">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="e0add-447">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="e0add-448">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e0add-448">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e0add-449">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0add-449">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e0add-450">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e0add-450">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="e0add-451">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e0add-451">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e0add-452">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0add-452">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0add-453">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e0add-453">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="e0add-454">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0add-454">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0add-455">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e0add-455">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="e0add-456">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0add-456">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0add-457">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="e0add-457">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e0add-458">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0add-458">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="e0add-459">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e0add-459">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="e0add-460">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="e0add-460">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="e0add-461">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0add-461">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="e0add-462">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e0add-462">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="e0add-463">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="e0add-463">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="e0add-464">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0add-464">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e0add-465">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e0add-465">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="e0add-466">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="e0add-466">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e0add-467">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0add-467">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e0add-468">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e0add-468">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="e0add-469">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="e0add-469">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="e0add-470">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0add-470">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e0add-471">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="e0add-471">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="e0add-472">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="e0add-472">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="e0add-473">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0add-473">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="e0add-474">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="e0add-474">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="e0add-475">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="e0add-475">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="e0add-476">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e0add-476">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e0add-477">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0add-477">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0add-478">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="e0add-478">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0add-479">**page**</span><span class="sxs-lookup"><span data-stu-id="e0add-479">**page**</span></span>

<span data-ttu-id="e0add-480">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="e0add-480">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="e0add-481">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e0add-481">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="e0add-482">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="e0add-482">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="e0add-483">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="e0add-483">**viewimports**</span></span>

<span data-ttu-id="e0add-484">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="e0add-484">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="e0add-485">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e0add-485">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e0add-486">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e0add-486">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="e0add-487">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="e0add-487">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="e0add-488">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e0add-488">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e0add-489">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="e0add-489">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="e0add-490">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="e0add-490">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="e0add-491">**classlib**</span><span class="sxs-lookup"><span data-stu-id="e0add-491">**classlib**</span></span>

<span data-ttu-id="e0add-492">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e0add-492">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e0add-493">Значения: `netcoreapp1.0`, `netcoreapp1.1` или с `netstandard1.0` по `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="e0add-493">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="e0add-494">Значение по умолчанию — `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="e0add-494">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="e0add-495">**mvc**</span><span class="sxs-lookup"><span data-stu-id="e0add-495">**mvc**</span></span>

<span data-ttu-id="e0add-496">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="e0add-496">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e0add-497">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="e0add-497">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="e0add-498">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="e0add-498">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="e0add-499">`-au|--auth` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e0add-499">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="e0add-500">Значения: `None` или `Individual`.</span><span class="sxs-lookup"><span data-stu-id="e0add-500">Values: `None` or `Individual`.</span></span> <span data-ttu-id="e0add-501">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="e0add-501">The default value is `None`.</span></span>

<span data-ttu-id="e0add-502">`-uld|--use-local-db` — указывает, следует ли использовать LocalDB вместо SQLite.</span><span class="sxs-lookup"><span data-stu-id="e0add-502">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="e0add-503">Значения: `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="e0add-503">Values: `true` or `false`.</span></span> <span data-ttu-id="e0add-504">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="e0add-504">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="e0add-505">Примеры</span><span class="sxs-lookup"><span data-stu-id="e0add-505">Examples</span></span>

<span data-ttu-id="e0add-506">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="e0add-506">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="e0add-507">Создание проекта библиотеки классов .NET Standard в указанном каталоге (доступно только при использовании пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="e0add-507">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="e0add-508">Создание проекта приложения ASP.NET Core C# MVC в текущем каталоге без проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="e0add-508">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="e0add-509">Создание нового приложения xUnit:</span><span class="sxs-lookup"><span data-stu-id="e0add-509">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="e0add-510">Перечислите все шаблоны, доступные для MVC:</span><span class="sxs-lookup"><span data-stu-id="e0add-510">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="e0add-511">Установите версию 2.0 шаблонов одностраничного приложения для ASP.NET Core (параметр команды доступен в .NET Core SDK 1.1 и более поздних версиях):</span><span class="sxs-lookup"><span data-stu-id="e0add-511">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="e0add-512">Создайте *global.json* в текущем каталоге, указав версию пакета SDK 2.0.0 (доступно только для пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="e0add-512">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="e0add-513">См. также</span><span class="sxs-lookup"><span data-stu-id="e0add-513">See also</span></span>

[<span data-ttu-id="e0add-514">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="e0add-514">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="e0add-515">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="e0add-515">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="e0add-516">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="e0add-516">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="e0add-517">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="e0add-517">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
