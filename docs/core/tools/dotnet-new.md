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
ms.openlocfilehash: d64881380febee08414f57a36ed92079e8d69ed6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-new"></a><span data-ttu-id="d548e-104">dotnet new</span><span class="sxs-lookup"><span data-stu-id="d548e-104">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d548e-105">Имя</span><span class="sxs-lookup"><span data-stu-id="d548e-105">Name</span></span>

<span data-ttu-id="d548e-106">`dotnet new` — создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="d548e-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d548e-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d548e-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d548e-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d548e-108">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d548e-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d548e-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="d548e-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d548e-110">Description</span></span>

<span data-ttu-id="d548e-111">Команда `dotnet new` предоставляет удобный способ инициализации проекта .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d548e-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span> 

<span data-ttu-id="d548e-112">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="d548e-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="d548e-113">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d548e-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="d548e-114">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="d548e-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="d548e-115">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="d548e-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="d548e-116">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="d548e-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d548e-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d548e-117">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="d548e-118">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d548e-118">The command contains a default list of templates.</span></span> <span data-ttu-id="d548e-119">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="d548e-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="d548e-120">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="d548e-120">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="d548e-121">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="d548e-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="d548e-122">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="d548e-122">Template description</span></span>                          | <span data-ttu-id="d548e-123">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="d548e-123">Template name</span></span>  | <span data-ttu-id="d548e-124">Языки</span><span class="sxs-lookup"><span data-stu-id="d548e-124">Languages</span></span>     |
|----------------------------------------------|----------------|---------------|
| <span data-ttu-id="d548e-125">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="d548e-125">Console application</span></span>                          | <span data-ttu-id="d548e-126">консоль</span><span class="sxs-lookup"><span data-stu-id="d548e-126">console</span></span>        | <span data-ttu-id="d548e-127">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d548e-127">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d548e-128">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="d548e-128">Class library</span></span>                                | <span data-ttu-id="d548e-129">classlib</span><span class="sxs-lookup"><span data-stu-id="d548e-129">classlib</span></span>       | <span data-ttu-id="d548e-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d548e-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d548e-131">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="d548e-131">Unit test project</span></span>                            | <span data-ttu-id="d548e-132">mstest</span><span class="sxs-lookup"><span data-stu-id="d548e-132">mstest</span></span>         | <span data-ttu-id="d548e-133">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d548e-133">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d548e-134">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="d548e-134">xUnit test project</span></span>                           | <span data-ttu-id="d548e-135">xunit</span><span class="sxs-lookup"><span data-stu-id="d548e-135">xunit</span></span>          | <span data-ttu-id="d548e-136">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d548e-136">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d548e-137">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d548e-137">ASP.NET Core empty</span></span>                           | <span data-ttu-id="d548e-138">web</span><span class="sxs-lookup"><span data-stu-id="d548e-138">web</span></span>            | <span data-ttu-id="d548e-139">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d548e-139">[C#], F#</span></span>      |
| <span data-ttu-id="d548e-140">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="d548e-140">ASP.NET Core Web App (Model-View-Controller)</span></span> | <span data-ttu-id="d548e-141">mvc</span><span class="sxs-lookup"><span data-stu-id="d548e-141">mvc</span></span>            | <span data-ttu-id="d548e-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d548e-142">[C#], F#</span></span>      |
| <span data-ttu-id="d548e-143">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d548e-143">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="d548e-144">razor</span><span class="sxs-lookup"><span data-stu-id="d548e-144">razor</span></span>          | <span data-ttu-id="d548e-145">[C#]</span><span class="sxs-lookup"><span data-stu-id="d548e-145">[C#]</span></span>          |
| <span data-ttu-id="d548e-146">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="d548e-146">ASP.NET Core with Angular</span></span>                    | <span data-ttu-id="d548e-147">angular</span><span class="sxs-lookup"><span data-stu-id="d548e-147">angular</span></span>        | <span data-ttu-id="d548e-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="d548e-148">[C#]</span></span>          |
| <span data-ttu-id="d548e-149">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="d548e-149">ASP.NET Core with React.js</span></span>                   | <span data-ttu-id="d548e-150">react</span><span class="sxs-lookup"><span data-stu-id="d548e-150">react</span></span>          | <span data-ttu-id="d548e-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="d548e-151">[C#]</span></span>          |
| <span data-ttu-id="d548e-152">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="d548e-152">ASP.NET Core with React.js and Redux</span></span>         | <span data-ttu-id="d548e-153">reactredux</span><span class="sxs-lookup"><span data-stu-id="d548e-153">reactredux</span></span>     | <span data-ttu-id="d548e-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="d548e-154">[C#]</span></span>          |
| <span data-ttu-id="d548e-155">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d548e-155">ASP.NET Core Web API</span></span>                         | <span data-ttu-id="d548e-156">webapi</span><span class="sxs-lookup"><span data-stu-id="d548e-156">webapi</span></span>         | <span data-ttu-id="d548e-157">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d548e-157">[C#], F#</span></span>      |
| <span data-ttu-id="d548e-158">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="d548e-158">global.json file</span></span>                             | <span data-ttu-id="d548e-159">globaljson</span><span class="sxs-lookup"><span data-stu-id="d548e-159">globaljson</span></span>     |               |
| <span data-ttu-id="d548e-160">Конфигурация Nuget</span><span class="sxs-lookup"><span data-stu-id="d548e-160">Nuget config</span></span>                                 | <span data-ttu-id="d548e-161">nugetconfig</span><span class="sxs-lookup"><span data-stu-id="d548e-161">nugetconfig</span></span>    |               |
| <span data-ttu-id="d548e-162">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="d548e-162">Web config</span></span>                                   | <span data-ttu-id="d548e-163">webconfig</span><span class="sxs-lookup"><span data-stu-id="d548e-163">webconfig</span></span>      |               |
| <span data-ttu-id="d548e-164">Файл решения</span><span class="sxs-lookup"><span data-stu-id="d548e-164">Solution file</span></span>                                | <span data-ttu-id="d548e-165">sln</span><span class="sxs-lookup"><span data-stu-id="d548e-165">sln</span></span>            |               |
| <span data-ttu-id="d548e-166">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="d548e-166">Razor page</span></span>                                   | <span data-ttu-id="d548e-167">страница</span><span class="sxs-lookup"><span data-stu-id="d548e-167">page</span></span>           |               |
| <span data-ttu-id="d548e-168">MVC/ViewImports</span><span class="sxs-lookup"><span data-stu-id="d548e-168">MVC/ViewImports</span></span>                              | <span data-ttu-id="d548e-169">viewimports</span><span class="sxs-lookup"><span data-stu-id="d548e-169">viewimports</span></span>    |               |
| <span data-ttu-id="d548e-170">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="d548e-170">MVC ViewStart</span></span>                                | <span data-ttu-id="d548e-171">viewstart</span><span class="sxs-lookup"><span data-stu-id="d548e-171">viewstart</span></span>      |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d548e-172">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d548e-172">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="d548e-173">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d548e-173">The command contains a default list of templates.</span></span> <span data-ttu-id="d548e-174">Используйте `dotnet new -all`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="d548e-174">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="d548e-175">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="d548e-175">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="d548e-176">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="d548e-176">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="d548e-177">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="d548e-177">Template description</span></span>  | <span data-ttu-id="d548e-178">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="d548e-178">Template name</span></span>  | <span data-ttu-id="d548e-179">Языки</span><span class="sxs-lookup"><span data-stu-id="d548e-179">Languages</span></span> |
|----------------------|----------------|-----------|
| <span data-ttu-id="d548e-180">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="d548e-180">Console application</span></span>  | <span data-ttu-id="d548e-181">консоль</span><span class="sxs-lookup"><span data-stu-id="d548e-181">console</span></span>        | <span data-ttu-id="d548e-182">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d548e-182">[C#], F#</span></span>  |
| <span data-ttu-id="d548e-183">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="d548e-183">Class library</span></span>        | <span data-ttu-id="d548e-184">classlib</span><span class="sxs-lookup"><span data-stu-id="d548e-184">classlib</span></span>       | <span data-ttu-id="d548e-185">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d548e-185">[C#], F#</span></span>  |
| <span data-ttu-id="d548e-186">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="d548e-186">Unit test project</span></span>    | <span data-ttu-id="d548e-187">mstest</span><span class="sxs-lookup"><span data-stu-id="d548e-187">mstest</span></span>         | <span data-ttu-id="d548e-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d548e-188">[C#], F#</span></span>  |
| <span data-ttu-id="d548e-189">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="d548e-189">xUnit test project</span></span>   | <span data-ttu-id="d548e-190">xunit</span><span class="sxs-lookup"><span data-stu-id="d548e-190">xunit</span></span>          | <span data-ttu-id="d548e-191">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d548e-191">[C#], F#</span></span>  |
| <span data-ttu-id="d548e-192">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d548e-192">ASP.NET Core empty</span></span>   | <span data-ttu-id="d548e-193">web</span><span class="sxs-lookup"><span data-stu-id="d548e-193">web</span></span>            | <span data-ttu-id="d548e-194">[C#]</span><span class="sxs-lookup"><span data-stu-id="d548e-194">[C#]</span></span>      |
| <span data-ttu-id="d548e-195">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d548e-195">ASP.NET Core Web App</span></span> | <span data-ttu-id="d548e-196">mvc</span><span class="sxs-lookup"><span data-stu-id="d548e-196">mvc</span></span>            | <span data-ttu-id="d548e-197">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d548e-197">[C#], F#</span></span>  |
| <span data-ttu-id="d548e-198">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d548e-198">ASP.NET Core Web API</span></span> | <span data-ttu-id="d548e-199">webapi</span><span class="sxs-lookup"><span data-stu-id="d548e-199">webapi</span></span>         | <span data-ttu-id="d548e-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="d548e-200">[C#]</span></span>      |
| <span data-ttu-id="d548e-201">Конфигурация Nuget</span><span class="sxs-lookup"><span data-stu-id="d548e-201">Nuget config</span></span>         | <span data-ttu-id="d548e-202">nugetconfig</span><span class="sxs-lookup"><span data-stu-id="d548e-202">nugetconfig</span></span>    |           |
| <span data-ttu-id="d548e-203">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="d548e-203">Web config</span></span>           | <span data-ttu-id="d548e-204">webconfig</span><span class="sxs-lookup"><span data-stu-id="d548e-204">webconfig</span></span>      |           |
| <span data-ttu-id="d548e-205">Файл решения</span><span class="sxs-lookup"><span data-stu-id="d548e-205">Solution file</span></span>        | <span data-ttu-id="d548e-206">sln</span><span class="sxs-lookup"><span data-stu-id="d548e-206">sln</span></span>            |           |

---

## <a name="options"></a><span data-ttu-id="d548e-207">Параметры</span><span class="sxs-lookup"><span data-stu-id="d548e-207">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d548e-208">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d548e-208">.NET Core 2.x</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="d548e-209">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="d548e-209">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="d548e-210">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="d548e-210">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="d548e-211">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="d548e-211">Prints out help for the command.</span></span> <span data-ttu-id="d548e-212">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="d548e-212">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="d548e-213">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="d548e-213">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="d548e-214">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="d548e-214">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="d548e-215">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="d548e-215">Lists templates containing the specified name.</span></span> <span data-ttu-id="d548e-216">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="d548e-216">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="d548e-217">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="d548e-217">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="d548e-218">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="d548e-218">The language of the template to create.</span></span> <span data-ttu-id="d548e-219">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="d548e-219">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="d548e-220">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="d548e-220">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="d548e-221">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="d548e-221">The name for the created output.</span></span> <span data-ttu-id="d548e-222">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="d548e-222">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d548e-223">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="d548e-223">Location to place the generated output.</span></span> <span data-ttu-id="d548e-224">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="d548e-224">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="d548e-225">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="d548e-225">Filters templates based on available types.</span></span> <span data-ttu-id="d548e-226">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="d548e-226">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="d548e-227">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="d548e-227">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="d548e-228">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="d548e-228">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="d548e-229">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="d548e-229">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="d548e-230">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="d548e-230">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d548e-231">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d548e-231">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="d548e-232">Показывает все шаблоны определенного типа проекта при запуске в контексте одной только команды `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="d548e-232">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="d548e-233">При запуске в контексте конкретного шаблона, например `dotnet new web -all`, `-all` интерпретируется как флаг принудительного создания.</span><span class="sxs-lookup"><span data-stu-id="d548e-233">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="d548e-234">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="d548e-234">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="d548e-235">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="d548e-235">Prints out help for the command.</span></span> <span data-ttu-id="d548e-236">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="d548e-236">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="d548e-237">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="d548e-237">Lists templates containing the specified name.</span></span> <span data-ttu-id="d548e-238">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="d548e-238">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="d548e-239">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="d548e-239">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="d548e-240">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="d548e-240">The language of the template to create.</span></span> <span data-ttu-id="d548e-241">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="d548e-241">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="d548e-242">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="d548e-242">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="d548e-243">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="d548e-243">The name for the created output.</span></span> <span data-ttu-id="d548e-244">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="d548e-244">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d548e-245">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="d548e-245">Location to place the generated output.</span></span> <span data-ttu-id="d548e-246">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="d548e-246">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="d548e-247">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="d548e-247">Template options</span></span>

<span data-ttu-id="d548e-248">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="d548e-248">Each project template may have additional options available.</span></span> <span data-ttu-id="d548e-249">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="d548e-249">The core templates have the following additional options:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d548e-250">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d548e-250">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="d548e-251">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="d548e-251">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="d548e-252">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="d548e-252">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d548e-253">**classlib**</span><span class="sxs-lookup"><span data-stu-id="d548e-253">**classlib**</span></span>

<span data-ttu-id="d548e-254">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="d548e-254">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d548e-255">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="d548e-255">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="d548e-256">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="d548e-256">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="d548e-257">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="d548e-257">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d548e-258">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="d548e-258">**mstest, xunit**</span></span>

<span data-ttu-id="d548e-259">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="d548e-259">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="d548e-260">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="d548e-260">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d548e-261">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="d548e-261">**globaljson**</span></span>

<span data-ttu-id="d548e-262">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="d548e-262">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="d548e-263">**web**</span><span class="sxs-lookup"><span data-stu-id="d548e-263">**web**</span></span>

<span data-ttu-id="d548e-264">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="d548e-264">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="d548e-265">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="d548e-265">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d548e-266">**webapi**</span><span class="sxs-lookup"><span data-stu-id="d548e-266">**webapi**</span></span>

<span data-ttu-id="d548e-267">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d548e-267">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="d548e-268">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="d548e-268">The possible values are:</span></span>

- <span data-ttu-id="d548e-269">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d548e-269">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="d548e-270">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="d548e-270">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="d548e-271">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="d548e-271">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="d548e-272">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="d548e-272">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="d548e-273">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="d548e-273">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="d548e-274">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d548e-274">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="d548e-275">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="d548e-275">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="d548e-276">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="d548e-276">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="d548e-277">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d548e-277">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d548e-278">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="d548e-278">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="d548e-279">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="d548e-279">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="d548e-280">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="d548e-280">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="d548e-281">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="d548e-281">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="d548e-282">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="d548e-282">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="d548e-283">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="d548e-283">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="d548e-284">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="d548e-284">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="d548e-285">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d548e-285">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="d548e-286">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="d548e-286">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="d548e-287">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="d548e-287">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="d548e-288">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="d548e-288">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="d548e-289">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="d548e-289">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="d548e-290">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="d548e-290">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="d548e-291">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="d548e-291">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="d548e-292">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="d548e-292">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="d548e-293">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="d548e-293">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="d548e-294">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d548e-294">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d548e-295">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="d548e-295">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d548e-296">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="d548e-296">**mvc, razor**</span></span>

<span data-ttu-id="d548e-297">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d548e-297">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="d548e-298">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="d548e-298">The possible values are:</span></span>

- <span data-ttu-id="d548e-299">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d548e-299">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="d548e-300">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="d548e-300">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="d548e-301">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="d548e-301">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="d548e-302">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="d548e-302">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="d548e-303">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="d548e-303">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="d548e-304">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="d548e-304">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="d548e-305">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="d548e-305">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="d548e-306">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d548e-306">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="d548e-307">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="d548e-307">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="d548e-308">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="d548e-308">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="d548e-309">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d548e-309">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d548e-310">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="d548e-310">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="d548e-311">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d548e-311">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d548e-312">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="d548e-312">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="d548e-313">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d548e-313">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d548e-314">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="d548e-314">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="d548e-315">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="d548e-315">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="d548e-316">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="d548e-316">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="d548e-317">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="d548e-317">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="d548e-318">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="d548e-318">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="d548e-319">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="d548e-319">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="d548e-320">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="d548e-320">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="d548e-321">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d548e-321">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="d548e-322">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="d548e-322">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="d548e-323">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="d548e-323">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="d548e-324">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="d548e-324">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="d548e-325">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="d548e-325">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="d548e-326">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="d548e-326">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="d548e-327">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d548e-327">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="d548e-328">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="d548e-328">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="d548e-329">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="d548e-329">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="d548e-330">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="d548e-330">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="d548e-331">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="d548e-331">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="d548e-332">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="d548e-332">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="d548e-333">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="d548e-333">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="d548e-334">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d548e-334">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d548e-335">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="d548e-335">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d548e-336">**page**</span><span class="sxs-lookup"><span data-stu-id="d548e-336">**page**</span></span>

<span data-ttu-id="d548e-337">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="d548e-337">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="d548e-338">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="d548e-338">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="d548e-339">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="d548e-339">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="d548e-340">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="d548e-340">**viewimports**</span></span>

<span data-ttu-id="d548e-341">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="d548e-341">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="d548e-342">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="d548e-342">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d548e-343">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d548e-343">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="d548e-344">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="d548e-344">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="d548e-345">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="d548e-345">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d548e-346">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="d548e-346">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="d548e-347">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="d548e-347">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="d548e-348">**classlib**</span><span class="sxs-lookup"><span data-stu-id="d548e-348">**classlib**</span></span>

<span data-ttu-id="d548e-349">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="d548e-349">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d548e-350">Значения: `netcoreapp1.0`, `netcoreapp1.1` или с `netstandard1.0` по `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="d548e-350">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="d548e-351">Значение по умолчанию — `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="d548e-351">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="d548e-352">**mvc**</span><span class="sxs-lookup"><span data-stu-id="d548e-352">**mvc**</span></span>

<span data-ttu-id="d548e-353">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="d548e-353">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d548e-354">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="d548e-354">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="d548e-355">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="d548e-355">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="d548e-356">`-au|--auth` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d548e-356">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="d548e-357">Значения: `None` или `Individual`.</span><span class="sxs-lookup"><span data-stu-id="d548e-357">Values: `None` or `Individual`.</span></span> <span data-ttu-id="d548e-358">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="d548e-358">The default value is `None`.</span></span>

<span data-ttu-id="d548e-359">`-uld|--use-local-db` — указывает, следует ли использовать LocalDB вместо SQLite.</span><span class="sxs-lookup"><span data-stu-id="d548e-359">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="d548e-360">Значения: `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="d548e-360">Values: `true` or `false`.</span></span> <span data-ttu-id="d548e-361">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="d548e-361">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="d548e-362">Примеры</span><span class="sxs-lookup"><span data-stu-id="d548e-362">Examples</span></span>

<span data-ttu-id="d548e-363">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="d548e-363">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang f#`

<span data-ttu-id="d548e-364">Создание проекта стандартной библиотеки классов .NET в указанном каталоге (доступно только при использовании пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="d548e-364">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="d548e-365">Создание проекта приложения ASP.NET Core C# MVC в текущем каталоге без проверки подлинности для .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="d548e-365">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="d548e-366">Создание приложения XUnit, предназначенного для .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="d548e-366">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="d548e-367">Перечислите все шаблоны, доступные для MVC:</span><span class="sxs-lookup"><span data-stu-id="d548e-367">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

## <a name="see-also"></a><span data-ttu-id="d548e-368">См. также</span><span class="sxs-lookup"><span data-stu-id="d548e-368">See also</span></span>

[<span data-ttu-id="d548e-369">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="d548e-369">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="d548e-370">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="d548e-370">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="d548e-371">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="d548e-371">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="d548e-372">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="d548e-372">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
