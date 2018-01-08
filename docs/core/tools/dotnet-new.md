---
title: "Команда dotnet new — интерфейс командной строки .NET Core"
description: "Команда dotnet new создает проекты .NET Core на основе указанного шаблона."
keywords: "dotnet-new, CLI, команда CLI, .NET Core"
author: mairaw
ms.author: mairaw
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fcc3ed2e-9265-4d50-b59e-dc2e5c190b34
ms.workload: dotnetcore
ms.openlocfilehash: f5815e1ad2a36a8ef3279f6ff83465dba9ec5d50
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-new"></a><span data-ttu-id="68ff1-104">dotnet new</span><span class="sxs-lookup"><span data-stu-id="68ff1-104">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="68ff1-105">name</span><span class="sxs-lookup"><span data-stu-id="68ff1-105">Name</span></span>

<span data-ttu-id="68ff1-106">`dotnet new` — создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="68ff1-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="68ff1-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="68ff1-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="68ff1-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="68ff1-108">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="68ff1-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="68ff1-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="68ff1-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="68ff1-110">Description</span></span>

<span data-ttu-id="68ff1-111">Команда `dotnet new` предоставляет удобный способ инициализации проекта .NET Core.</span><span class="sxs-lookup"><span data-stu-id="68ff1-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span> 

<span data-ttu-id="68ff1-112">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="68ff1-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="68ff1-113">Аргументы</span><span class="sxs-lookup"><span data-stu-id="68ff1-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="68ff1-114">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="68ff1-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="68ff1-115">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="68ff1-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="68ff1-116">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="68ff1-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="68ff1-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="68ff1-117">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="68ff1-118">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="68ff1-118">The command contains a default list of templates.</span></span> <span data-ttu-id="68ff1-119">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="68ff1-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="68ff1-120">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="68ff1-120">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="68ff1-121">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="68ff1-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="68ff1-122">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="68ff1-122">Template description</span></span>                          | <span data-ttu-id="68ff1-123">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="68ff1-123">Template name</span></span>  | <span data-ttu-id="68ff1-124">Языки</span><span class="sxs-lookup"><span data-stu-id="68ff1-124">Languages</span></span>     |
|----------------------------------------------|----------------|---------------|
| <span data-ttu-id="68ff1-125">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="68ff1-125">Console application</span></span>                          | <span data-ttu-id="68ff1-126">консоль</span><span class="sxs-lookup"><span data-stu-id="68ff1-126">console</span></span>        | <span data-ttu-id="68ff1-127">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="68ff1-127">[C#], F#, VB</span></span>  |
| <span data-ttu-id="68ff1-128">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="68ff1-128">Class library</span></span>                                | <span data-ttu-id="68ff1-129">classlib</span><span class="sxs-lookup"><span data-stu-id="68ff1-129">classlib</span></span>       | <span data-ttu-id="68ff1-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="68ff1-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="68ff1-131">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="68ff1-131">Unit test project</span></span>                            | <span data-ttu-id="68ff1-132">mstest</span><span class="sxs-lookup"><span data-stu-id="68ff1-132">mstest</span></span>         | <span data-ttu-id="68ff1-133">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="68ff1-133">[C#], F#, VB</span></span>  |
| <span data-ttu-id="68ff1-134">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="68ff1-134">xUnit test project</span></span>                           | <span data-ttu-id="68ff1-135">xunit</span><span class="sxs-lookup"><span data-stu-id="68ff1-135">xunit</span></span>          | <span data-ttu-id="68ff1-136">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="68ff1-136">[C#], F#, VB</span></span>  |
| <span data-ttu-id="68ff1-137">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="68ff1-137">ASP.NET Core empty</span></span>                           | <span data-ttu-id="68ff1-138">web</span><span class="sxs-lookup"><span data-stu-id="68ff1-138">web</span></span>            | <span data-ttu-id="68ff1-139">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="68ff1-139">[C#], F#</span></span>      |
| <span data-ttu-id="68ff1-140">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="68ff1-140">ASP.NET Core Web App (Model-View-Controller)</span></span> | <span data-ttu-id="68ff1-141">mvc</span><span class="sxs-lookup"><span data-stu-id="68ff1-141">mvc</span></span>            | <span data-ttu-id="68ff1-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="68ff1-142">[C#], F#</span></span>      |
| <span data-ttu-id="68ff1-143">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="68ff1-143">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="68ff1-144">razor</span><span class="sxs-lookup"><span data-stu-id="68ff1-144">razor</span></span>          | <span data-ttu-id="68ff1-145">[C#]</span><span class="sxs-lookup"><span data-stu-id="68ff1-145">[C#]</span></span>          |
| <span data-ttu-id="68ff1-146">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="68ff1-146">ASP.NET Core with Angular</span></span>                    | <span data-ttu-id="68ff1-147">angular</span><span class="sxs-lookup"><span data-stu-id="68ff1-147">angular</span></span>        | <span data-ttu-id="68ff1-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="68ff1-148">[C#]</span></span>          |
| <span data-ttu-id="68ff1-149">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="68ff1-149">ASP.NET Core with React.js</span></span>                   | <span data-ttu-id="68ff1-150">react</span><span class="sxs-lookup"><span data-stu-id="68ff1-150">react</span></span>          | <span data-ttu-id="68ff1-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="68ff1-151">[C#]</span></span>          |
| <span data-ttu-id="68ff1-152">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="68ff1-152">ASP.NET Core with React.js and Redux</span></span>         | <span data-ttu-id="68ff1-153">reactredux</span><span class="sxs-lookup"><span data-stu-id="68ff1-153">reactredux</span></span>     | <span data-ttu-id="68ff1-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="68ff1-154">[C#]</span></span>          |
| <span data-ttu-id="68ff1-155">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="68ff1-155">ASP.NET Core Web API</span></span>                         | <span data-ttu-id="68ff1-156">webapi</span><span class="sxs-lookup"><span data-stu-id="68ff1-156">webapi</span></span>         | <span data-ttu-id="68ff1-157">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="68ff1-157">[C#], F#</span></span>      |
| <span data-ttu-id="68ff1-158">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="68ff1-158">global.json file</span></span>                             | <span data-ttu-id="68ff1-159">globaljson</span><span class="sxs-lookup"><span data-stu-id="68ff1-159">globaljson</span></span>     |               |
| <span data-ttu-id="68ff1-160">Конфигурация Nuget</span><span class="sxs-lookup"><span data-stu-id="68ff1-160">Nuget config</span></span>                                 | <span data-ttu-id="68ff1-161">nugetconfig</span><span class="sxs-lookup"><span data-stu-id="68ff1-161">nugetconfig</span></span>    |               |
| <span data-ttu-id="68ff1-162">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="68ff1-162">Web config</span></span>                                   | <span data-ttu-id="68ff1-163">webconfig</span><span class="sxs-lookup"><span data-stu-id="68ff1-163">webconfig</span></span>      |               |
| <span data-ttu-id="68ff1-164">Файл решения</span><span class="sxs-lookup"><span data-stu-id="68ff1-164">Solution file</span></span>                                | <span data-ttu-id="68ff1-165">sln</span><span class="sxs-lookup"><span data-stu-id="68ff1-165">sln</span></span>            |               |
| <span data-ttu-id="68ff1-166">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="68ff1-166">Razor page</span></span>                                   | <span data-ttu-id="68ff1-167">страница</span><span class="sxs-lookup"><span data-stu-id="68ff1-167">page</span></span>           |               |
| <span data-ttu-id="68ff1-168">MVC/ViewImports</span><span class="sxs-lookup"><span data-stu-id="68ff1-168">MVC/ViewImports</span></span>                              | <span data-ttu-id="68ff1-169">viewimports</span><span class="sxs-lookup"><span data-stu-id="68ff1-169">viewimports</span></span>    |               |
| <span data-ttu-id="68ff1-170">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="68ff1-170">MVC ViewStart</span></span>                                | <span data-ttu-id="68ff1-171">viewstart</span><span class="sxs-lookup"><span data-stu-id="68ff1-171">viewstart</span></span>      |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="68ff1-172">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="68ff1-172">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="68ff1-173">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="68ff1-173">The command contains a default list of templates.</span></span> <span data-ttu-id="68ff1-174">Используйте `dotnet new -all`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="68ff1-174">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="68ff1-175">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="68ff1-175">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="68ff1-176">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="68ff1-176">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="68ff1-177">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="68ff1-177">Template description</span></span>  | <span data-ttu-id="68ff1-178">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="68ff1-178">Template name</span></span>  | <span data-ttu-id="68ff1-179">Языки</span><span class="sxs-lookup"><span data-stu-id="68ff1-179">Languages</span></span> |
|----------------------|----------------|-----------|
| <span data-ttu-id="68ff1-180">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="68ff1-180">Console application</span></span>  | <span data-ttu-id="68ff1-181">console</span><span class="sxs-lookup"><span data-stu-id="68ff1-181">console</span></span>        | <span data-ttu-id="68ff1-182">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="68ff1-182">[C#], F#</span></span>  |
| <span data-ttu-id="68ff1-183">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="68ff1-183">Class library</span></span>        | <span data-ttu-id="68ff1-184">classlib</span><span class="sxs-lookup"><span data-stu-id="68ff1-184">classlib</span></span>       | <span data-ttu-id="68ff1-185">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="68ff1-185">[C#], F#</span></span>  |
| <span data-ttu-id="68ff1-186">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="68ff1-186">Unit test project</span></span>    | <span data-ttu-id="68ff1-187">mstest</span><span class="sxs-lookup"><span data-stu-id="68ff1-187">mstest</span></span>         | <span data-ttu-id="68ff1-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="68ff1-188">[C#], F#</span></span>  |
| <span data-ttu-id="68ff1-189">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="68ff1-189">xUnit test project</span></span>   | <span data-ttu-id="68ff1-190">xunit</span><span class="sxs-lookup"><span data-stu-id="68ff1-190">xunit</span></span>          | <span data-ttu-id="68ff1-191">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="68ff1-191">[C#], F#</span></span>  |
| <span data-ttu-id="68ff1-192">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="68ff1-192">ASP.NET Core empty</span></span>   | <span data-ttu-id="68ff1-193">web</span><span class="sxs-lookup"><span data-stu-id="68ff1-193">web</span></span>            | <span data-ttu-id="68ff1-194">[C#]</span><span class="sxs-lookup"><span data-stu-id="68ff1-194">[C#]</span></span>      |
| <span data-ttu-id="68ff1-195">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="68ff1-195">ASP.NET Core Web App</span></span> | <span data-ttu-id="68ff1-196">mvc</span><span class="sxs-lookup"><span data-stu-id="68ff1-196">mvc</span></span>            | <span data-ttu-id="68ff1-197">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="68ff1-197">[C#], F#</span></span>  |
| <span data-ttu-id="68ff1-198">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="68ff1-198">ASP.NET Core Web API</span></span> | <span data-ttu-id="68ff1-199">webapi</span><span class="sxs-lookup"><span data-stu-id="68ff1-199">webapi</span></span>         | <span data-ttu-id="68ff1-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="68ff1-200">[C#]</span></span>      |
| <span data-ttu-id="68ff1-201">Конфигурация Nuget</span><span class="sxs-lookup"><span data-stu-id="68ff1-201">Nuget config</span></span>         | <span data-ttu-id="68ff1-202">nugetconfig</span><span class="sxs-lookup"><span data-stu-id="68ff1-202">nugetconfig</span></span>    |           |
| <span data-ttu-id="68ff1-203">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="68ff1-203">Web config</span></span>           | <span data-ttu-id="68ff1-204">webconfig</span><span class="sxs-lookup"><span data-stu-id="68ff1-204">webconfig</span></span>      |           |
| <span data-ttu-id="68ff1-205">Файл решения</span><span class="sxs-lookup"><span data-stu-id="68ff1-205">Solution file</span></span>        | <span data-ttu-id="68ff1-206">sln</span><span class="sxs-lookup"><span data-stu-id="68ff1-206">sln</span></span>            |           |

---

## <a name="options"></a><span data-ttu-id="68ff1-207">Параметры</span><span class="sxs-lookup"><span data-stu-id="68ff1-207">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="68ff1-208">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="68ff1-208">.NET Core 2.x</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="68ff1-209">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="68ff1-209">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="68ff1-210">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="68ff1-210">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="68ff1-211">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="68ff1-211">Prints out help for the command.</span></span> <span data-ttu-id="68ff1-212">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-212">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="68ff1-213">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-213">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="68ff1-214">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="68ff1-214">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="68ff1-215">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="68ff1-215">Lists templates containing the specified name.</span></span> <span data-ttu-id="68ff1-216">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="68ff1-216">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="68ff1-217">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="68ff1-217">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="68ff1-218">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="68ff1-218">The language of the template to create.</span></span> <span data-ttu-id="68ff1-219">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="68ff1-219">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="68ff1-220">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="68ff1-220">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="68ff1-221">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="68ff1-221">The name for the created output.</span></span> <span data-ttu-id="68ff1-222">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="68ff1-222">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="68ff1-223">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="68ff1-223">Location to place the generated output.</span></span> <span data-ttu-id="68ff1-224">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="68ff1-224">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="68ff1-225">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="68ff1-225">Filters templates based on available types.</span></span> <span data-ttu-id="68ff1-226">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="68ff1-226">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="68ff1-227">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-227">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="68ff1-228">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="68ff1-228">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="68ff1-229">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="68ff1-229">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="68ff1-230">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="68ff1-230">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="68ff1-231">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="68ff1-231">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="68ff1-232">Показывает все шаблоны определенного типа проекта при запуске в контексте одной только команды `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-232">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="68ff1-233">При запуске в контексте конкретного шаблона, например `dotnet new web -all`, `-all` интерпретируется как флаг принудительного создания.</span><span class="sxs-lookup"><span data-stu-id="68ff1-233">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="68ff1-234">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="68ff1-234">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="68ff1-235">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="68ff1-235">Prints out help for the command.</span></span> <span data-ttu-id="68ff1-236">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-236">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="68ff1-237">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="68ff1-237">Lists templates containing the specified name.</span></span> <span data-ttu-id="68ff1-238">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="68ff1-238">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="68ff1-239">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="68ff1-239">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="68ff1-240">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="68ff1-240">The language of the template to create.</span></span> <span data-ttu-id="68ff1-241">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="68ff1-241">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="68ff1-242">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="68ff1-242">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="68ff1-243">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="68ff1-243">The name for the created output.</span></span> <span data-ttu-id="68ff1-244">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="68ff1-244">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="68ff1-245">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="68ff1-245">Location to place the generated output.</span></span> <span data-ttu-id="68ff1-246">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="68ff1-246">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="68ff1-247">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="68ff1-247">Template options</span></span>

<span data-ttu-id="68ff1-248">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="68ff1-248">Each project template may have additional options available.</span></span> <span data-ttu-id="68ff1-249">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="68ff1-249">The core templates have the following additional options:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="68ff1-250">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="68ff1-250">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="68ff1-251">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="68ff1-251">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="68ff1-252">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="68ff1-252">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="68ff1-253">**classlib**</span><span class="sxs-lookup"><span data-stu-id="68ff1-253">**classlib**</span></span>

<span data-ttu-id="68ff1-254">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="68ff1-254">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="68ff1-255">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="68ff1-255">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="68ff1-256">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-256">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="68ff1-257">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="68ff1-257">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="68ff1-258">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="68ff1-258">**mstest, xunit**</span></span>

<span data-ttu-id="68ff1-259">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="68ff1-259">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="68ff1-260">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="68ff1-260">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="68ff1-261">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="68ff1-261">**globaljson**</span></span>

<span data-ttu-id="68ff1-262">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="68ff1-262">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="68ff1-263">**web**</span><span class="sxs-lookup"><span data-stu-id="68ff1-263">**web**</span></span>

<span data-ttu-id="68ff1-264">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="68ff1-264">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="68ff1-265">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="68ff1-265">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="68ff1-266">**webapi**</span><span class="sxs-lookup"><span data-stu-id="68ff1-266">**webapi**</span></span>

<span data-ttu-id="68ff1-267">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="68ff1-267">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="68ff1-268">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="68ff1-268">The possible values are:</span></span>

- <span data-ttu-id="68ff1-269">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="68ff1-269">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="68ff1-270">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="68ff1-270">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="68ff1-271">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="68ff1-271">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="68ff1-272">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="68ff1-272">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="68ff1-273">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="68ff1-273">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="68ff1-274">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-274">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="68ff1-275">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-275">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="68ff1-276">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="68ff1-276">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="68ff1-277">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-277">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="68ff1-278">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="68ff1-278">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="68ff1-279">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-279">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="68ff1-280">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-280">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="68ff1-281">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="68ff1-281">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="68ff1-282">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-282">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="68ff1-283">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-283">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="68ff1-284">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="68ff1-284">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="68ff1-285">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-285">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="68ff1-286">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-286">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="68ff1-287">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="68ff1-287">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="68ff1-288">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-288">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="68ff1-289">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-289">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="68ff1-290">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="68ff1-290">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="68ff1-291">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-291">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="68ff1-292">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="68ff1-292">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="68ff1-293">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="68ff1-293">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="68ff1-294">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-294">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="68ff1-295">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="68ff1-295">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="68ff1-296">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="68ff1-296">**mvc, razor**</span></span>

<span data-ttu-id="68ff1-297">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="68ff1-297">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="68ff1-298">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="68ff1-298">The possible values are:</span></span>

- <span data-ttu-id="68ff1-299">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="68ff1-299">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="68ff1-300">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="68ff1-300">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="68ff1-301">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="68ff1-301">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="68ff1-302">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="68ff1-302">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="68ff1-303">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="68ff1-303">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="68ff1-304">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="68ff1-304">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="68ff1-305">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="68ff1-305">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="68ff1-306">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-306">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="68ff1-307">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-307">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="68ff1-308">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="68ff1-308">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="68ff1-309">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-309">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="68ff1-310">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="68ff1-310">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="68ff1-311">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-311">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="68ff1-312">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="68ff1-312">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="68ff1-313">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-313">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="68ff1-314">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="68ff1-314">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="68ff1-315">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-315">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="68ff1-316">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-316">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="68ff1-317">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="68ff1-317">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="68ff1-318">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-318">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="68ff1-319">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-319">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="68ff1-320">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="68ff1-320">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="68ff1-321">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-321">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="68ff1-322">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-322">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="68ff1-323">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="68ff1-323">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="68ff1-324">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-324">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="68ff1-325">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-325">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="68ff1-326">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="68ff1-326">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="68ff1-327">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-327">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="68ff1-328">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-328">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="68ff1-329">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="68ff1-329">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="68ff1-330">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-330">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="68ff1-331">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="68ff1-331">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="68ff1-332">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="68ff1-332">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="68ff1-333">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="68ff1-333">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="68ff1-334">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-334">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="68ff1-335">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="68ff1-335">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="68ff1-336">**page**</span><span class="sxs-lookup"><span data-stu-id="68ff1-336">**page**</span></span>

<span data-ttu-id="68ff1-337">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="68ff1-337">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="68ff1-338">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-338">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="68ff1-339">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="68ff1-339">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="68ff1-340">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="68ff1-340">**viewimports**</span></span>

<span data-ttu-id="68ff1-341">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="68ff1-341">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="68ff1-342">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-342">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="68ff1-343">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="68ff1-343">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="68ff1-344">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="68ff1-344">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="68ff1-345">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="68ff1-345">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="68ff1-346">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-346">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="68ff1-347">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-347">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="68ff1-348">**classlib**</span><span class="sxs-lookup"><span data-stu-id="68ff1-348">**classlib**</span></span>

<span data-ttu-id="68ff1-349">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="68ff1-349">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="68ff1-350">Значения: `netcoreapp1.0`, `netcoreapp1.1` или с `netstandard1.0` по `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-350">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="68ff1-351">Значение по умолчанию — `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-351">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="68ff1-352">**mvc**</span><span class="sxs-lookup"><span data-stu-id="68ff1-352">**mvc**</span></span>

<span data-ttu-id="68ff1-353">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="68ff1-353">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="68ff1-354">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-354">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="68ff1-355">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-355">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="68ff1-356">`-au|--auth` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="68ff1-356">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="68ff1-357">Значения: `None` или `Individual`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-357">Values: `None` or `Individual`.</span></span> <span data-ttu-id="68ff1-358">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-358">The default value is `None`.</span></span>

<span data-ttu-id="68ff1-359">`-uld|--use-local-db` — указывает, следует ли использовать LocalDB вместо SQLite.</span><span class="sxs-lookup"><span data-stu-id="68ff1-359">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="68ff1-360">Значения: `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-360">Values: `true` or `false`.</span></span> <span data-ttu-id="68ff1-361">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="68ff1-361">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="68ff1-362">Примеры</span><span class="sxs-lookup"><span data-stu-id="68ff1-362">Examples</span></span>

<span data-ttu-id="68ff1-363">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="68ff1-363">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang f#`

<span data-ttu-id="68ff1-364">Создание проекта стандартной библиотеки классов .NET в указанном каталоге (доступно только при использовании пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="68ff1-364">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="68ff1-365">Создание проекта приложения ASP.NET Core C# MVC в текущем каталоге без проверки подлинности для .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="68ff1-365">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="68ff1-366">Создание приложения XUnit, предназначенного для .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="68ff1-366">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="68ff1-367">Перечислите все шаблоны, доступные для MVC:</span><span class="sxs-lookup"><span data-stu-id="68ff1-367">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

## <a name="see-also"></a><span data-ttu-id="68ff1-368">См. также</span><span class="sxs-lookup"><span data-stu-id="68ff1-368">See also</span></span>

[<span data-ttu-id="68ff1-369">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="68ff1-369">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="68ff1-370">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="68ff1-370">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="68ff1-371">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="68ff1-371">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="68ff1-372">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="68ff1-372">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
