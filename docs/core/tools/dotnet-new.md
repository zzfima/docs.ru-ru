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
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: 335902f26148d8201b7311b57370fd37280c68dd
ms.contentlocale: ru-ru
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-new"></a><span data-ttu-id="0bba7-104">dotnet new</span><span class="sxs-lookup"><span data-stu-id="0bba7-104">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="0bba7-105">Имя</span><span class="sxs-lookup"><span data-stu-id="0bba7-105">Name</span></span>

<span data-ttu-id="0bba7-106">`dotnet new` — создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="0bba7-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0bba7-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0bba7-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="0bba7-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="0bba7-108">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0bba7-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0bba7-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="0bba7-110">Описание</span><span class="sxs-lookup"><span data-stu-id="0bba7-110">Description</span></span>

<span data-ttu-id="0bba7-111">Команда `dotnet new` предоставляет удобный способ инициализации проекта .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0bba7-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span> 

<span data-ttu-id="0bba7-112">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="0bba7-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="0bba7-113">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0bba7-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="0bba7-114">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="0bba7-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="0bba7-115">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="0bba7-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="0bba7-116">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="0bba7-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="0bba7-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="0bba7-117">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="0bba7-118">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0bba7-118">The command contains a default list of templates.</span></span> <span data-ttu-id="0bba7-119">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="0bba7-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="0bba7-120">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="0bba7-120">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="0bba7-121">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="0bba7-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="0bba7-122">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="0bba7-122">Template description</span></span>                          | <span data-ttu-id="0bba7-123">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="0bba7-123">Template name</span></span>  | <span data-ttu-id="0bba7-124">Языки</span><span class="sxs-lookup"><span data-stu-id="0bba7-124">Languages</span></span>     |
|----------------------------------------------|----------------|---------------|
| <span data-ttu-id="0bba7-125">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="0bba7-125">Console application</span></span>                          | <span data-ttu-id="0bba7-126">консоль</span><span class="sxs-lookup"><span data-stu-id="0bba7-126">console</span></span>        | <span data-ttu-id="0bba7-127">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="0bba7-127">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0bba7-128">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="0bba7-128">Class library</span></span>                                | <span data-ttu-id="0bba7-129">classlib</span><span class="sxs-lookup"><span data-stu-id="0bba7-129">classlib</span></span>       | <span data-ttu-id="0bba7-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="0bba7-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0bba7-131">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="0bba7-131">Unit test project</span></span>                            | <span data-ttu-id="0bba7-132">mstest</span><span class="sxs-lookup"><span data-stu-id="0bba7-132">mstest</span></span>         | <span data-ttu-id="0bba7-133">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="0bba7-133">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0bba7-134">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="0bba7-134">xUnit test project</span></span>                           | <span data-ttu-id="0bba7-135">xunit</span><span class="sxs-lookup"><span data-stu-id="0bba7-135">xunit</span></span>          | <span data-ttu-id="0bba7-136">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="0bba7-136">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0bba7-137">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0bba7-137">ASP.NET Core empty</span></span>                           | <span data-ttu-id="0bba7-138">web</span><span class="sxs-lookup"><span data-stu-id="0bba7-138">web</span></span>            | <span data-ttu-id="0bba7-139">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0bba7-139">[C#], F#</span></span>      |
| <span data-ttu-id="0bba7-140">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="0bba7-140">ASP.NET Core Web App (Model-View-Controller)</span></span> | <span data-ttu-id="0bba7-141">mvc</span><span class="sxs-lookup"><span data-stu-id="0bba7-141">mvc</span></span>            | <span data-ttu-id="0bba7-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0bba7-142">[C#], F#</span></span>      |
| <span data-ttu-id="0bba7-143">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0bba7-143">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="0bba7-144">razor</span><span class="sxs-lookup"><span data-stu-id="0bba7-144">razor</span></span>          | <span data-ttu-id="0bba7-145">[C#]</span><span class="sxs-lookup"><span data-stu-id="0bba7-145">[C#]</span></span>          |
| <span data-ttu-id="0bba7-146">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="0bba7-146">ASP.NET Core with Angular</span></span>                    | <span data-ttu-id="0bba7-147">angular</span><span class="sxs-lookup"><span data-stu-id="0bba7-147">angular</span></span>        | <span data-ttu-id="0bba7-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="0bba7-148">[C#]</span></span>          |
| <span data-ttu-id="0bba7-149">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="0bba7-149">ASP.NET Core with React.js</span></span>                   | <span data-ttu-id="0bba7-150">react</span><span class="sxs-lookup"><span data-stu-id="0bba7-150">react</span></span>          | <span data-ttu-id="0bba7-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="0bba7-151">[C#]</span></span>          |
| <span data-ttu-id="0bba7-152">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="0bba7-152">ASP.NET Core with React.js and Redux</span></span>         | <span data-ttu-id="0bba7-153">reactredux</span><span class="sxs-lookup"><span data-stu-id="0bba7-153">reactredux</span></span>     | <span data-ttu-id="0bba7-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="0bba7-154">[C#]</span></span>          |
| <span data-ttu-id="0bba7-155">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0bba7-155">ASP.NET Core Web API</span></span>                         | <span data-ttu-id="0bba7-156">webapi</span><span class="sxs-lookup"><span data-stu-id="0bba7-156">webapi</span></span>         | <span data-ttu-id="0bba7-157">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0bba7-157">[C#], F#</span></span>      |
| <span data-ttu-id="0bba7-158">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="0bba7-158">global.json file</span></span>                             | <span data-ttu-id="0bba7-159">globaljson</span><span class="sxs-lookup"><span data-stu-id="0bba7-159">globaljson</span></span>     |               |
| <span data-ttu-id="0bba7-160">Конфигурация Nuget</span><span class="sxs-lookup"><span data-stu-id="0bba7-160">Nuget config</span></span>                                 | <span data-ttu-id="0bba7-161">nugetconfig</span><span class="sxs-lookup"><span data-stu-id="0bba7-161">nugetconfig</span></span>    |               |
| <span data-ttu-id="0bba7-162">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="0bba7-162">Web config</span></span>                                   | <span data-ttu-id="0bba7-163">webconfig</span><span class="sxs-lookup"><span data-stu-id="0bba7-163">webconfig</span></span>      |               |
| <span data-ttu-id="0bba7-164">Файл решения</span><span class="sxs-lookup"><span data-stu-id="0bba7-164">Solution file</span></span>                                | <span data-ttu-id="0bba7-165">sln</span><span class="sxs-lookup"><span data-stu-id="0bba7-165">sln</span></span>            |               |
| <span data-ttu-id="0bba7-166">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="0bba7-166">Razor page</span></span>                                   | <span data-ttu-id="0bba7-167">страница</span><span class="sxs-lookup"><span data-stu-id="0bba7-167">page</span></span>           |               |
| <span data-ttu-id="0bba7-168">MVC/ViewImports</span><span class="sxs-lookup"><span data-stu-id="0bba7-168">MVC/ViewImports</span></span>                              | <span data-ttu-id="0bba7-169">viewimports</span><span class="sxs-lookup"><span data-stu-id="0bba7-169">viewimports</span></span>    |               |
| <span data-ttu-id="0bba7-170">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="0bba7-170">MVC ViewStart</span></span>                                | <span data-ttu-id="0bba7-171">viewstart</span><span class="sxs-lookup"><span data-stu-id="0bba7-171">viewstart</span></span>      |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0bba7-172">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0bba7-172">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="0bba7-173">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0bba7-173">The command contains a default list of templates.</span></span> <span data-ttu-id="0bba7-174">Используйте `dotnet new -all`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="0bba7-174">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="0bba7-175">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="0bba7-175">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="0bba7-176">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="0bba7-176">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="0bba7-177">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="0bba7-177">Template description</span></span>  | <span data-ttu-id="0bba7-178">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="0bba7-178">Template name</span></span>  | <span data-ttu-id="0bba7-179">Языки</span><span class="sxs-lookup"><span data-stu-id="0bba7-179">Languages</span></span> |
|----------------------|----------------|-----------|
| <span data-ttu-id="0bba7-180">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="0bba7-180">Console application</span></span>  | <span data-ttu-id="0bba7-181">консоль</span><span class="sxs-lookup"><span data-stu-id="0bba7-181">console</span></span>        | <span data-ttu-id="0bba7-182">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0bba7-182">[C#], F#</span></span>  |
| <span data-ttu-id="0bba7-183">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="0bba7-183">Class library</span></span>        | <span data-ttu-id="0bba7-184">classlib</span><span class="sxs-lookup"><span data-stu-id="0bba7-184">classlib</span></span>       | <span data-ttu-id="0bba7-185">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0bba7-185">[C#], F#</span></span>  |
| <span data-ttu-id="0bba7-186">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="0bba7-186">Unit test project</span></span>    | <span data-ttu-id="0bba7-187">mstest</span><span class="sxs-lookup"><span data-stu-id="0bba7-187">mstest</span></span>         | <span data-ttu-id="0bba7-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0bba7-188">[C#], F#</span></span>  |
| <span data-ttu-id="0bba7-189">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="0bba7-189">xUnit test project</span></span>   | <span data-ttu-id="0bba7-190">xunit</span><span class="sxs-lookup"><span data-stu-id="0bba7-190">xunit</span></span>          | <span data-ttu-id="0bba7-191">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0bba7-191">[C#], F#</span></span>  |
| <span data-ttu-id="0bba7-192">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0bba7-192">ASP.NET Core empty</span></span>   | <span data-ttu-id="0bba7-193">web</span><span class="sxs-lookup"><span data-stu-id="0bba7-193">web</span></span>            | <span data-ttu-id="0bba7-194">[C#]</span><span class="sxs-lookup"><span data-stu-id="0bba7-194">[C#]</span></span>      |
| <span data-ttu-id="0bba7-195">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0bba7-195">ASP.NET Core Web App</span></span> | <span data-ttu-id="0bba7-196">mvc</span><span class="sxs-lookup"><span data-stu-id="0bba7-196">mvc</span></span>            | <span data-ttu-id="0bba7-197">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0bba7-197">[C#], F#</span></span>  |
| <span data-ttu-id="0bba7-198">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0bba7-198">ASP.NET Core Web API</span></span> | <span data-ttu-id="0bba7-199">webapi</span><span class="sxs-lookup"><span data-stu-id="0bba7-199">webapi</span></span>         | <span data-ttu-id="0bba7-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="0bba7-200">[C#]</span></span>      |
| <span data-ttu-id="0bba7-201">Конфигурация Nuget</span><span class="sxs-lookup"><span data-stu-id="0bba7-201">Nuget config</span></span>         | <span data-ttu-id="0bba7-202">nugetconfig</span><span class="sxs-lookup"><span data-stu-id="0bba7-202">nugetconfig</span></span>    |           |
| <span data-ttu-id="0bba7-203">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="0bba7-203">Web config</span></span>           | <span data-ttu-id="0bba7-204">webconfig</span><span class="sxs-lookup"><span data-stu-id="0bba7-204">webconfig</span></span>      |           |
| <span data-ttu-id="0bba7-205">Файл решения</span><span class="sxs-lookup"><span data-stu-id="0bba7-205">Solution file</span></span>        | <span data-ttu-id="0bba7-206">sln</span><span class="sxs-lookup"><span data-stu-id="0bba7-206">sln</span></span>            |           |

---

## <a name="options"></a><span data-ttu-id="0bba7-207">Параметры</span><span class="sxs-lookup"><span data-stu-id="0bba7-207">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="0bba7-208">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="0bba7-208">.NET Core 2.x</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="0bba7-209">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="0bba7-209">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="0bba7-210">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="0bba7-210">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="0bba7-211">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="0bba7-211">Prints out help for the command.</span></span> <span data-ttu-id="0bba7-212">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-212">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="0bba7-213">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-213">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="0bba7-214">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="0bba7-214">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="0bba7-215">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="0bba7-215">Lists templates containing the specified name.</span></span> <span data-ttu-id="0bba7-216">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="0bba7-216">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="0bba7-217">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="0bba7-217">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="0bba7-218">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="0bba7-218">The language of the template to create.</span></span> <span data-ttu-id="0bba7-219">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="0bba7-219">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="0bba7-220">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="0bba7-220">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="0bba7-221">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="0bba7-221">The name for the created output.</span></span> <span data-ttu-id="0bba7-222">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="0bba7-222">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="0bba7-223">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="0bba7-223">Location to place the generated output.</span></span> <span data-ttu-id="0bba7-224">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="0bba7-224">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="0bba7-225">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="0bba7-225">Filters templates based on available types.</span></span> <span data-ttu-id="0bba7-226">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="0bba7-226">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="0bba7-227">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-227">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0bba7-228">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0bba7-228">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="0bba7-229">Показывает все шаблоны определенного типа проекта при запуске в контексте одной только команды `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-229">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="0bba7-230">При запуске в контексте конкретного шаблона, например `dotnet new web -all`, `-all` интерпретируется как флаг принудительного создания.</span><span class="sxs-lookup"><span data-stu-id="0bba7-230">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="0bba7-231">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="0bba7-231">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="0bba7-232">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="0bba7-232">Prints out help for the command.</span></span> <span data-ttu-id="0bba7-233">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-233">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="0bba7-234">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="0bba7-234">Lists templates containing the specified name.</span></span> <span data-ttu-id="0bba7-235">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="0bba7-235">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="0bba7-236">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="0bba7-236">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="0bba7-237">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="0bba7-237">The language of the template to create.</span></span> <span data-ttu-id="0bba7-238">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="0bba7-238">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="0bba7-239">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="0bba7-239">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="0bba7-240">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="0bba7-240">The name for the created output.</span></span> <span data-ttu-id="0bba7-241">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="0bba7-241">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="0bba7-242">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="0bba7-242">Location to place the generated output.</span></span> <span data-ttu-id="0bba7-243">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="0bba7-243">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="0bba7-244">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="0bba7-244">Template options</span></span>

<span data-ttu-id="0bba7-245">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="0bba7-245">Each project template may have additional options available.</span></span> <span data-ttu-id="0bba7-246">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="0bba7-246">The core templates have the following additional options:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="0bba7-247">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="0bba7-247">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="0bba7-248">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="0bba7-248">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="0bba7-249">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="0bba7-249">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="0bba7-250">**classlib**</span><span class="sxs-lookup"><span data-stu-id="0bba7-250">**classlib**</span></span>

<span data-ttu-id="0bba7-251">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="0bba7-251">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0bba7-252">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="0bba7-252">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="0bba7-253">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-253">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="0bba7-254">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="0bba7-254">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="0bba7-255">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="0bba7-255">**mstest, xunit**</span></span>

<span data-ttu-id="0bba7-256">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="0bba7-256">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="0bba7-257">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="0bba7-257">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="0bba7-258">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="0bba7-258">**globaljson**</span></span>

<span data-ttu-id="0bba7-259">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="0bba7-259">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="0bba7-260">**web**</span><span class="sxs-lookup"><span data-stu-id="0bba7-260">**web**</span></span>

<span data-ttu-id="0bba7-261">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="0bba7-261">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="0bba7-262">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="0bba7-262">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="0bba7-263">**webapi**</span><span class="sxs-lookup"><span data-stu-id="0bba7-263">**webapi**</span></span>

<span data-ttu-id="0bba7-264">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="0bba7-264">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="0bba7-265">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="0bba7-265">The possible values are:</span></span>

- <span data-ttu-id="0bba7-266">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="0bba7-266">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="0bba7-267">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="0bba7-267">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="0bba7-268">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="0bba7-268">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="0bba7-269">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="0bba7-269">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="0bba7-270">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="0bba7-270">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="0bba7-271">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-271">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="0bba7-272">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-272">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="0bba7-273">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="0bba7-273">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="0bba7-274">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-274">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0bba7-275">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="0bba7-275">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="0bba7-276">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-276">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="0bba7-277">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-277">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="0bba7-278">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="0bba7-278">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="0bba7-279">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-279">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="0bba7-280">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-280">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="0bba7-281">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="0bba7-281">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="0bba7-282">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-282">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="0bba7-283">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-283">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="0bba7-284">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="0bba7-284">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="0bba7-285">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-285">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="0bba7-286">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-286">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="0bba7-287">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="0bba7-287">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="0bba7-288">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-288">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="0bba7-289">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="0bba7-289">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="0bba7-290">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="0bba7-290">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="0bba7-291">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-291">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0bba7-292">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="0bba7-292">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="0bba7-293">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="0bba7-293">**mvc, razor**</span></span>

<span data-ttu-id="0bba7-294">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="0bba7-294">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="0bba7-295">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="0bba7-295">The possible values are:</span></span>

- <span data-ttu-id="0bba7-296">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="0bba7-296">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="0bba7-297">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="0bba7-297">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="0bba7-298">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="0bba7-298">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="0bba7-299">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="0bba7-299">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="0bba7-300">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="0bba7-300">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="0bba7-301">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="0bba7-301">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="0bba7-302">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="0bba7-302">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="0bba7-303">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-303">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="0bba7-304">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-304">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="0bba7-305">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="0bba7-305">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="0bba7-306">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-306">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0bba7-307">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="0bba7-307">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="0bba7-308">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-308">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0bba7-309">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="0bba7-309">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="0bba7-310">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-310">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0bba7-311">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="0bba7-311">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="0bba7-312">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-312">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="0bba7-313">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-313">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="0bba7-314">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="0bba7-314">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="0bba7-315">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-315">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="0bba7-316">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-316">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="0bba7-317">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="0bba7-317">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="0bba7-318">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-318">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="0bba7-319">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-319">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="0bba7-320">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="0bba7-320">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="0bba7-321">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-321">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="0bba7-322">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-322">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="0bba7-323">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="0bba7-323">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="0bba7-324">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-324">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="0bba7-325">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-325">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="0bba7-326">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="0bba7-326">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="0bba7-327">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-327">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="0bba7-328">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="0bba7-328">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="0bba7-329">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="0bba7-329">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="0bba7-330">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="0bba7-330">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="0bba7-331">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-331">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0bba7-332">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="0bba7-332">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="0bba7-333">**page**</span><span class="sxs-lookup"><span data-stu-id="0bba7-333">**page**</span></span>

<span data-ttu-id="0bba7-334">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="0bba7-334">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="0bba7-335">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-335">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="0bba7-336">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="0bba7-336">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="0bba7-337">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="0bba7-337">**viewimports**</span></span>

<span data-ttu-id="0bba7-338">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="0bba7-338">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="0bba7-339">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-339">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0bba7-340">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0bba7-340">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="0bba7-341">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="0bba7-341">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="0bba7-342">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="0bba7-342">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0bba7-343">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-343">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="0bba7-344">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-344">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="0bba7-345">**classlib**</span><span class="sxs-lookup"><span data-stu-id="0bba7-345">**classlib**</span></span>

<span data-ttu-id="0bba7-346">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="0bba7-346">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0bba7-347">Значения: `netcoreapp1.0`, `netcoreapp1.1` или с `netstandard1.0` по `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-347">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="0bba7-348">Значение по умолчанию — `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-348">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="0bba7-349">**mvc**</span><span class="sxs-lookup"><span data-stu-id="0bba7-349">**mvc**</span></span>

<span data-ttu-id="0bba7-350">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="0bba7-350">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0bba7-351">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-351">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="0bba7-352">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-352">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="0bba7-353">`-au|--auth` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="0bba7-353">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="0bba7-354">Значения: `None` или `Individual`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-354">Values: `None` or `Individual`.</span></span> <span data-ttu-id="0bba7-355">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-355">The default value is `None`.</span></span>

<span data-ttu-id="0bba7-356">`-uld|--use-local-db` — указывает, следует ли использовать LocalDB вместо SQLite.</span><span class="sxs-lookup"><span data-stu-id="0bba7-356">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="0bba7-357">Значения: `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-357">Values: `true` or `false`.</span></span> <span data-ttu-id="0bba7-358">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="0bba7-358">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="0bba7-359">Примеры</span><span class="sxs-lookup"><span data-stu-id="0bba7-359">Examples</span></span>

<span data-ttu-id="0bba7-360">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="0bba7-360">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang f#`

<span data-ttu-id="0bba7-361">Создание проекта стандартной библиотеки классов .NET в указанном каталоге (доступно только при использовании пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="0bba7-361">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="0bba7-362">Создание проекта приложения ASP.NET Core C# MVC в текущем каталоге без проверки подлинности для .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="0bba7-362">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="0bba7-363">Создание приложения XUnit, предназначенного для .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="0bba7-363">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="0bba7-364">Перечислите все шаблоны, доступные для MVC:</span><span class="sxs-lookup"><span data-stu-id="0bba7-364">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

## <a name="see-also"></a><span data-ttu-id="0bba7-365">См. также</span><span class="sxs-lookup"><span data-stu-id="0bba7-365">See also</span></span>

[<span data-ttu-id="0bba7-366">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="0bba7-366">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="0bba7-367">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="0bba7-367">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="0bba7-368">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="0bba7-368">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="0bba7-369">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="0bba7-369">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)

