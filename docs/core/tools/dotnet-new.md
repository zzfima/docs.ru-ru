---
title: Команда dotnet new — интерфейс командной строки .NET Core
description: Команда dotnet new создает проекты .NET Core на основе указанного шаблона.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: ae24c4145cc67ca863c07e4d22af8a1c2c2dd732
ms.sourcegitcommit: 3540f614fc94f77ca4ab58df66db2d0f4d52dfee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2018
ms.locfileid: "34570467"
---
# <a name="dotnet-new"></a><span data-ttu-id="bdd5c-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="bdd5c-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="bdd5c-104">name</span><span class="sxs-lookup"><span data-stu-id="bdd5c-104">Name</span></span>

<span data-ttu-id="bdd5c-105">`dotnet new` — создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="bdd5c-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="bdd5c-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="bdd5c-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="bdd5c-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="bdd5c-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="bdd5c-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bdd5c-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bdd5c-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="bdd5c-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="bdd5c-110">Description</span></span>

<span data-ttu-id="bdd5c-111">Команда `dotnet new` предоставляет удобный способ инициализации проекта .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="bdd5c-112">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="bdd5c-113">Аргументы</span><span class="sxs-lookup"><span data-stu-id="bdd5c-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="bdd5c-114">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="bdd5c-115">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="bdd5c-116">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="bdd5c-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="bdd5c-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="bdd5c-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="bdd5c-118">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-118">The command contains a default list of templates.</span></span> <span data-ttu-id="bdd5c-119">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="bdd5c-120">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="bdd5c-121">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="bdd5c-122">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="bdd5c-122">Template description</span></span>                          | <span data-ttu-id="bdd5c-123">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="bdd5c-123">Template name</span></span>   | <span data-ttu-id="bdd5c-124">Языки</span><span class="sxs-lookup"><span data-stu-id="bdd5c-124">Languages</span></span>     |
|----------------------------------------------|-----------------|---------------|
| <span data-ttu-id="bdd5c-125">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="bdd5c-125">Console application</span></span>                          | `console`       | <span data-ttu-id="bdd5c-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="bdd5c-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="bdd5c-127">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="bdd5c-127">Class library</span></span>                                | `classlib`      | <span data-ttu-id="bdd5c-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="bdd5c-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="bdd5c-129">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="bdd5c-129">Unit test project</span></span>                            | `mstest`        | <span data-ttu-id="bdd5c-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="bdd5c-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="bdd5c-131">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="bdd5c-131">xUnit test project</span></span>                           | `xunit`         | <span data-ttu-id="bdd5c-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="bdd5c-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="bdd5c-133">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="bdd5c-133">Razor page</span></span>                                   | `page`          | <span data-ttu-id="bdd5c-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="bdd5c-134">[C#]</span></span>          |
| <span data-ttu-id="bdd5c-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="bdd5c-135">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="bdd5c-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="bdd5c-136">[C#]</span></span>          |
| <span data-ttu-id="bdd5c-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="bdd5c-137">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="bdd5c-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="bdd5c-138">[C#]</span></span>          |
| <span data-ttu-id="bdd5c-139">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bdd5c-139">ASP.NET Core empty</span></span>                           | `web`           | <span data-ttu-id="bdd5c-140">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="bdd5c-140">[C#], F#</span></span>      |
| <span data-ttu-id="bdd5c-141">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="bdd5c-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="bdd5c-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="bdd5c-142">[C#], F#</span></span>      |
| <span data-ttu-id="bdd5c-143">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bdd5c-143">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="bdd5c-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="bdd5c-144">[C#]</span></span>          |
| <span data-ttu-id="bdd5c-145">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="bdd5c-145">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="bdd5c-146">[C#]</span><span class="sxs-lookup"><span data-stu-id="bdd5c-146">[C#]</span></span>          |
| <span data-ttu-id="bdd5c-147">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="bdd5c-147">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="bdd5c-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="bdd5c-148">[C#]</span></span>          |
| <span data-ttu-id="bdd5c-149">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="bdd5c-149">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="bdd5c-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="bdd5c-150">[C#]</span></span>          |
| <span data-ttu-id="bdd5c-151">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bdd5c-151">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="bdd5c-152">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="bdd5c-152">[C#], F#</span></span>      |
| <span data-ttu-id="bdd5c-153">Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="bdd5c-153">Razor class library</span></span>                          | `razorclasslib` | <span data-ttu-id="bdd5c-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="bdd5c-154">[C#]</span></span>          |
| <span data-ttu-id="bdd5c-155">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="bdd5c-155">global.json file</span></span>                             | `globaljson`    |               |
| <span data-ttu-id="bdd5c-156">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="bdd5c-156">NuGet config</span></span>                                 | `nugetconfig`   |               |
| <span data-ttu-id="bdd5c-157">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="bdd5c-157">Web config</span></span>                                   | `webconfig`     |               |
| <span data-ttu-id="bdd5c-158">Файл решения</span><span class="sxs-lookup"><span data-stu-id="bdd5c-158">Solution file</span></span>                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="bdd5c-159">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="bdd5c-159">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="bdd5c-160">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-160">The command contains a default list of templates.</span></span> <span data-ttu-id="bdd5c-161">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-161">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="bdd5c-162">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-162">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="bdd5c-163">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-163">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="bdd5c-164">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="bdd5c-164">Template description</span></span>                          | <span data-ttu-id="bdd5c-165">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="bdd5c-165">Template name</span></span> | <span data-ttu-id="bdd5c-166">Языки</span><span class="sxs-lookup"><span data-stu-id="bdd5c-166">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="bdd5c-167">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="bdd5c-167">Console application</span></span>                          | `console`     | <span data-ttu-id="bdd5c-168">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="bdd5c-168">[C#], F#, VB</span></span>  |
| <span data-ttu-id="bdd5c-169">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="bdd5c-169">Class library</span></span>                                | `classlib`    | <span data-ttu-id="bdd5c-170">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="bdd5c-170">[C#], F#, VB</span></span>  |
| <span data-ttu-id="bdd5c-171">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="bdd5c-171">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="bdd5c-172">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="bdd5c-172">[C#], F#, VB</span></span>  |
| <span data-ttu-id="bdd5c-173">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="bdd5c-173">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="bdd5c-174">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="bdd5c-174">[C#], F#, VB</span></span>  |
| <span data-ttu-id="bdd5c-175">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bdd5c-175">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="bdd5c-176">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="bdd5c-176">[C#], F#</span></span>      |
| <span data-ttu-id="bdd5c-177">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="bdd5c-177">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="bdd5c-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="bdd5c-178">[C#], F#</span></span>      |
| <span data-ttu-id="bdd5c-179">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bdd5c-179">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="bdd5c-180">[C#]</span><span class="sxs-lookup"><span data-stu-id="bdd5c-180">[C#]</span></span>          |
| <span data-ttu-id="bdd5c-181">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="bdd5c-181">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="bdd5c-182">[C#]</span><span class="sxs-lookup"><span data-stu-id="bdd5c-182">[C#]</span></span>          |
| <span data-ttu-id="bdd5c-183">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="bdd5c-183">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="bdd5c-184">[C#]</span><span class="sxs-lookup"><span data-stu-id="bdd5c-184">[C#]</span></span>          |
| <span data-ttu-id="bdd5c-185">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="bdd5c-185">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="bdd5c-186">[C#]</span><span class="sxs-lookup"><span data-stu-id="bdd5c-186">[C#]</span></span>          |
| <span data-ttu-id="bdd5c-187">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bdd5c-187">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="bdd5c-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="bdd5c-188">[C#], F#</span></span>      |
| <span data-ttu-id="bdd5c-189">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="bdd5c-189">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="bdd5c-190">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="bdd5c-190">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="bdd5c-191">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="bdd5c-191">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="bdd5c-192">Файл решения</span><span class="sxs-lookup"><span data-stu-id="bdd5c-192">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="bdd5c-193">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="bdd5c-193">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="bdd5c-194">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="bdd5c-194">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="bdd5c-195">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="bdd5c-195">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bdd5c-196">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bdd5c-196">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="bdd5c-197">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-197">The command contains a default list of templates.</span></span> <span data-ttu-id="bdd5c-198">Используйте `dotnet new -all`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-198">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="bdd5c-199">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-199">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="bdd5c-200">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-200">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="bdd5c-201">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="bdd5c-201">Template description</span></span>  | <span data-ttu-id="bdd5c-202">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="bdd5c-202">Template name</span></span> | <span data-ttu-id="bdd5c-203">Языки</span><span class="sxs-lookup"><span data-stu-id="bdd5c-203">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="bdd5c-204">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="bdd5c-204">Console application</span></span>  | `console`     | <span data-ttu-id="bdd5c-205">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="bdd5c-205">[C#], F#</span></span>  |
| <span data-ttu-id="bdd5c-206">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="bdd5c-206">Class library</span></span>        | `classlib`    | <span data-ttu-id="bdd5c-207">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="bdd5c-207">[C#], F#</span></span>  |
| <span data-ttu-id="bdd5c-208">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="bdd5c-208">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="bdd5c-209">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="bdd5c-209">[C#], F#</span></span>  |
| <span data-ttu-id="bdd5c-210">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="bdd5c-210">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="bdd5c-211">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="bdd5c-211">[C#], F#</span></span>  |
| <span data-ttu-id="bdd5c-212">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bdd5c-212">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="bdd5c-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="bdd5c-213">[C#]</span></span>      |
| <span data-ttu-id="bdd5c-214">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bdd5c-214">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="bdd5c-215">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="bdd5c-215">[C#], F#</span></span>  |
| <span data-ttu-id="bdd5c-216">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bdd5c-216">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="bdd5c-217">[C#]</span><span class="sxs-lookup"><span data-stu-id="bdd5c-217">[C#]</span></span>      |
| <span data-ttu-id="bdd5c-218">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="bdd5c-218">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="bdd5c-219">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="bdd5c-219">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="bdd5c-220">Файл решения</span><span class="sxs-lookup"><span data-stu-id="bdd5c-220">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="bdd5c-221">Параметры</span><span class="sxs-lookup"><span data-stu-id="bdd5c-221">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="bdd5c-222">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="bdd5c-222">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="bdd5c-223">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-223">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="bdd5c-224">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-224">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="bdd5c-225">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-225">Prints out help for the command.</span></span> <span data-ttu-id="bdd5c-226">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-226">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="bdd5c-227">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-227">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="bdd5c-228">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-228">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="bdd5c-229">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-229">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="bdd5c-230">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="bdd5c-230">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="bdd5c-231">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="bdd5c-231">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="bdd5c-232">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-232">Lists templates containing the specified name.</span></span> <span data-ttu-id="bdd5c-233">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-233">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="bdd5c-234">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-234">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="bdd5c-235">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-235">The language of the template to create.</span></span> <span data-ttu-id="bdd5c-236">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="bdd5c-236">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="bdd5c-237">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-237">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="bdd5c-238">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-238">The name for the created output.</span></span> <span data-ttu-id="bdd5c-239">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-239">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="bdd5c-240">Задает источник пакетов NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-240">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="bdd5c-241">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-241">Location to place the generated output.</span></span> <span data-ttu-id="bdd5c-242">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-242">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="bdd5c-243">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-243">Filters templates based on available types.</span></span> <span data-ttu-id="bdd5c-244">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-244">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="bdd5c-245">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-245">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="bdd5c-246">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-246">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="bdd5c-247">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-247">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="bdd5c-248">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-248">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="bdd5c-249">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="bdd5c-249">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="bdd5c-250">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-250">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="bdd5c-251">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-251">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="bdd5c-252">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-252">Prints out help for the command.</span></span> <span data-ttu-id="bdd5c-253">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-253">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="bdd5c-254">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-254">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="bdd5c-255">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-255">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="bdd5c-256">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-256">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="bdd5c-257">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="bdd5c-257">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="bdd5c-258">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="bdd5c-258">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="bdd5c-259">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-259">Lists templates containing the specified name.</span></span> <span data-ttu-id="bdd5c-260">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-260">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="bdd5c-261">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-261">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="bdd5c-262">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-262">The language of the template to create.</span></span> <span data-ttu-id="bdd5c-263">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="bdd5c-263">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="bdd5c-264">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-264">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="bdd5c-265">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-265">The name for the created output.</span></span> <span data-ttu-id="bdd5c-266">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-266">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="bdd5c-267">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-267">Location to place the generated output.</span></span> <span data-ttu-id="bdd5c-268">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-268">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="bdd5c-269">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-269">Filters templates based on available types.</span></span> <span data-ttu-id="bdd5c-270">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-270">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="bdd5c-271">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-271">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="bdd5c-272">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-272">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="bdd5c-273">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-273">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="bdd5c-274">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-274">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bdd5c-275">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bdd5c-275">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="bdd5c-276">Показывает все шаблоны определенного типа проекта при запуске в контексте одной только команды `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-276">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="bdd5c-277">При запуске в контексте конкретного шаблона, например `dotnet new web -all`, `-all` интерпретируется как флаг принудительного создания.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-277">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="bdd5c-278">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-278">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="bdd5c-279">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-279">Prints out help for the command.</span></span> <span data-ttu-id="bdd5c-280">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-280">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="bdd5c-281">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-281">Lists templates containing the specified name.</span></span> <span data-ttu-id="bdd5c-282">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-282">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="bdd5c-283">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-283">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="bdd5c-284">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-284">The language of the template to create.</span></span> <span data-ttu-id="bdd5c-285">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="bdd5c-285">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="bdd5c-286">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-286">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="bdd5c-287">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-287">The name for the created output.</span></span> <span data-ttu-id="bdd5c-288">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-288">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="bdd5c-289">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-289">Location to place the generated output.</span></span> <span data-ttu-id="bdd5c-290">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-290">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="bdd5c-291">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="bdd5c-291">Template options</span></span>

<span data-ttu-id="bdd5c-292">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-292">Each project template may have additional options available.</span></span> <span data-ttu-id="bdd5c-293">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="bdd5c-293">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="bdd5c-294">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="bdd5c-294">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="bdd5c-295">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="bdd5c-295">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="bdd5c-296">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-296">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="bdd5c-297">**classlib**</span><span class="sxs-lookup"><span data-stu-id="bdd5c-297">**classlib**</span></span>

<span data-ttu-id="bdd5c-298">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="bdd5c-298">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="bdd5c-299">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-299">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="bdd5c-300">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-300">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="bdd5c-301">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-301">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="bdd5c-302">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="bdd5c-302">**mstest, xunit**</span></span>

<span data-ttu-id="bdd5c-303">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="bdd5c-303">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="bdd5c-304">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-304">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="bdd5c-305">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="bdd5c-305">**globaljson**</span></span>

<span data-ttu-id="bdd5c-306">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-306">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="bdd5c-307">**web**</span><span class="sxs-lookup"><span data-stu-id="bdd5c-307">**web**</span></span>

<span data-ttu-id="bdd5c-308">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-308">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="bdd5c-309">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-309">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="bdd5c-310">**webapi**</span><span class="sxs-lookup"><span data-stu-id="bdd5c-310">**webapi**</span></span>

<span data-ttu-id="bdd5c-311">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-311">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="bdd5c-312">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="bdd5c-312">The possible values are:</span></span>

- <span data-ttu-id="bdd5c-313">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="bdd5c-313">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="bdd5c-314">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-314">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="bdd5c-315">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-315">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="bdd5c-316">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-316">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="bdd5c-317">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-317">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="bdd5c-318">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-318">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="bdd5c-319">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-319">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="bdd5c-320">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-320">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="bdd5c-321">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-321">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="bdd5c-322">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-322">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="bdd5c-323">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-323">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="bdd5c-324">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-324">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="bdd5c-325">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-325">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="bdd5c-326">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-326">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="bdd5c-327">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-327">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="bdd5c-328">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-328">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="bdd5c-329">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-329">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="bdd5c-330">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-330">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="bdd5c-331">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-331">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="bdd5c-332">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-332">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="bdd5c-333">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-333">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="bdd5c-334">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-334">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="bdd5c-335">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-335">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="bdd5c-336">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-336">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="bdd5c-337">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-337">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="bdd5c-338">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-338">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="bdd5c-339">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-339">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="bdd5c-340">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="bdd5c-340">**mvc, razor**</span></span>

<span data-ttu-id="bdd5c-341">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-341">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="bdd5c-342">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="bdd5c-342">The possible values are:</span></span>

- <span data-ttu-id="bdd5c-343">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="bdd5c-343">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="bdd5c-344">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-344">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="bdd5c-345">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-345">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="bdd5c-346">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-346">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="bdd5c-347">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-347">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="bdd5c-348">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-348">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="bdd5c-349">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-349">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="bdd5c-350">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-350">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="bdd5c-351">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-351">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="bdd5c-352">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-352">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="bdd5c-353">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-353">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="bdd5c-354">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-354">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="bdd5c-355">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-355">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="bdd5c-356">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-356">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="bdd5c-357">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-357">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="bdd5c-358">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-358">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="bdd5c-359">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-359">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="bdd5c-360">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-360">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="bdd5c-361">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-361">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="bdd5c-362">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-362">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="bdd5c-363">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-363">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="bdd5c-364">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-364">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="bdd5c-365">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-365">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="bdd5c-366">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-366">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="bdd5c-367">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-367">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="bdd5c-368">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-368">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="bdd5c-369">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-369">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="bdd5c-370">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-370">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="bdd5c-371">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-371">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="bdd5c-372">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-372">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="bdd5c-373">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-373">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="bdd5c-374">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-374">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="bdd5c-375">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-375">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="bdd5c-376">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-376">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="bdd5c-377">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-377">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="bdd5c-378">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-378">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="bdd5c-379">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-379">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="bdd5c-380">**page**</span><span class="sxs-lookup"><span data-stu-id="bdd5c-380">**page**</span></span>

<span data-ttu-id="bdd5c-381">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-381">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="bdd5c-382">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-382">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="bdd5c-383">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-383">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="bdd5c-384">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="bdd5c-384">**viewimports**</span></span>

<span data-ttu-id="bdd5c-385">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-385">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="bdd5c-386">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-386">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="bdd5c-387">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="bdd5c-387">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="bdd5c-388">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="bdd5c-388">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="bdd5c-389">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-389">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="bdd5c-390">**classlib**</span><span class="sxs-lookup"><span data-stu-id="bdd5c-390">**classlib**</span></span>

<span data-ttu-id="bdd5c-391">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="bdd5c-391">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="bdd5c-392">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-392">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="bdd5c-393">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-393">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="bdd5c-394">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-394">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="bdd5c-395">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="bdd5c-395">**mstest, xunit**</span></span>

<span data-ttu-id="bdd5c-396">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="bdd5c-396">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="bdd5c-397">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-397">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="bdd5c-398">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="bdd5c-398">**globaljson**</span></span>

<span data-ttu-id="bdd5c-399">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-399">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="bdd5c-400">**web**</span><span class="sxs-lookup"><span data-stu-id="bdd5c-400">**web**</span></span>

<span data-ttu-id="bdd5c-401">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-401">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="bdd5c-402">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-402">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="bdd5c-403">**webapi**</span><span class="sxs-lookup"><span data-stu-id="bdd5c-403">**webapi**</span></span>

<span data-ttu-id="bdd5c-404">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-404">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="bdd5c-405">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="bdd5c-405">The possible values are:</span></span>

- <span data-ttu-id="bdd5c-406">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="bdd5c-406">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="bdd5c-407">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-407">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="bdd5c-408">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-408">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="bdd5c-409">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-409">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="bdd5c-410">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-410">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="bdd5c-411">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-411">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="bdd5c-412">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-412">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="bdd5c-413">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-413">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="bdd5c-414">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-414">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="bdd5c-415">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-415">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="bdd5c-416">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-416">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="bdd5c-417">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-417">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="bdd5c-418">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-418">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="bdd5c-419">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-419">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="bdd5c-420">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-420">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="bdd5c-421">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-421">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="bdd5c-422">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-422">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="bdd5c-423">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-423">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="bdd5c-424">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-424">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="bdd5c-425">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-425">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="bdd5c-426">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-426">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="bdd5c-427">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-427">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="bdd5c-428">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-428">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="bdd5c-429">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-429">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="bdd5c-430">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-430">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="bdd5c-431">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-431">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="bdd5c-432">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-432">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="bdd5c-433">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="bdd5c-433">**mvc, razor**</span></span>

<span data-ttu-id="bdd5c-434">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-434">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="bdd5c-435">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="bdd5c-435">The possible values are:</span></span>

- <span data-ttu-id="bdd5c-436">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="bdd5c-436">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="bdd5c-437">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-437">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="bdd5c-438">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-438">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="bdd5c-439">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-439">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="bdd5c-440">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-440">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="bdd5c-441">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-441">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="bdd5c-442">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-442">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="bdd5c-443">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-443">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="bdd5c-444">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-444">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="bdd5c-445">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-445">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="bdd5c-446">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-446">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="bdd5c-447">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-447">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="bdd5c-448">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-448">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="bdd5c-449">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-449">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="bdd5c-450">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-450">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="bdd5c-451">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-451">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="bdd5c-452">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-452">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="bdd5c-453">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-453">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="bdd5c-454">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-454">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="bdd5c-455">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-455">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="bdd5c-456">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-456">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="bdd5c-457">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-457">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="bdd5c-458">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-458">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="bdd5c-459">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-459">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="bdd5c-460">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-460">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="bdd5c-461">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-461">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="bdd5c-462">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-462">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="bdd5c-463">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-463">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="bdd5c-464">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-464">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="bdd5c-465">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-465">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="bdd5c-466">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-466">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="bdd5c-467">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-467">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="bdd5c-468">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-468">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="bdd5c-469">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-469">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="bdd5c-470">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-470">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="bdd5c-471">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-471">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="bdd5c-472">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-472">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="bdd5c-473">**page**</span><span class="sxs-lookup"><span data-stu-id="bdd5c-473">**page**</span></span>

<span data-ttu-id="bdd5c-474">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-474">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="bdd5c-475">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-475">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="bdd5c-476">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-476">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="bdd5c-477">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="bdd5c-477">**viewimports**</span></span>

<span data-ttu-id="bdd5c-478">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-478">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="bdd5c-479">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-479">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bdd5c-480">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bdd5c-480">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="bdd5c-481">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="bdd5c-481">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="bdd5c-482">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="bdd5c-482">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="bdd5c-483">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-483">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="bdd5c-484">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-484">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="bdd5c-485">**classlib**</span><span class="sxs-lookup"><span data-stu-id="bdd5c-485">**classlib**</span></span>

<span data-ttu-id="bdd5c-486">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="bdd5c-486">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="bdd5c-487">Значения: `netcoreapp1.0`, `netcoreapp1.1` или с `netstandard1.0` по `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-487">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="bdd5c-488">Значение по умолчанию — `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-488">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="bdd5c-489">**mvc**</span><span class="sxs-lookup"><span data-stu-id="bdd5c-489">**mvc**</span></span>

<span data-ttu-id="bdd5c-490">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="bdd5c-490">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="bdd5c-491">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-491">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="bdd5c-492">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-492">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="bdd5c-493">`-au|--auth` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-493">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="bdd5c-494">Значения: `None` или `Individual`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-494">Values: `None` or `Individual`.</span></span> <span data-ttu-id="bdd5c-495">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-495">The default value is `None`.</span></span>

<span data-ttu-id="bdd5c-496">`-uld|--use-local-db` — указывает, следует ли использовать LocalDB вместо SQLite.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-496">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="bdd5c-497">Значения: `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-497">Values: `true` or `false`.</span></span> <span data-ttu-id="bdd5c-498">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="bdd5c-498">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="bdd5c-499">Примеры</span><span class="sxs-lookup"><span data-stu-id="bdd5c-499">Examples</span></span>

<span data-ttu-id="bdd5c-500">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="bdd5c-500">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="bdd5c-501">Создание проекта библиотеки классов .NET Standard в указанном каталоге (доступно только при использовании пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="bdd5c-501">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="bdd5c-502">Создание проекта приложения ASP.NET Core C# MVC в текущем каталоге без проверки подлинности для .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="bdd5c-502">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="bdd5c-503">Создание приложения XUnit, предназначенного для .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="bdd5c-503">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="bdd5c-504">Перечислите все шаблоны, доступные для MVC:</span><span class="sxs-lookup"><span data-stu-id="bdd5c-504">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="bdd5c-505">Установите версию 2.0 шаблонов одностраничного приложения для ASP.NET Core (параметр команды доступен в .NET Core SDK 1.1 и более поздних версиях):</span><span class="sxs-lookup"><span data-stu-id="bdd5c-505">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="bdd5c-506">Создайте *global.json* в текущем каталоге, указав версию пакета SDK 2.0.0 (доступно только для пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="bdd5c-506">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="bdd5c-507">См. также</span><span class="sxs-lookup"><span data-stu-id="bdd5c-507">See also</span></span>

[<span data-ttu-id="bdd5c-508">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="bdd5c-508">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="bdd5c-509">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="bdd5c-509">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="bdd5c-510">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="bdd5c-510">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="bdd5c-511">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="bdd5c-511">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)