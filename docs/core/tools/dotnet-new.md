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
ms.openlocfilehash: cf65dc80f135badcb1580726a12a9ae9d94ae3d7
ms.sourcegitcommit: 8bde7a3432f30fc771079744955c75c58c4eb393
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/20/2018
---
# <a name="dotnet-new"></a><span data-ttu-id="938f5-104">dotnet new</span><span class="sxs-lookup"><span data-stu-id="938f5-104">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="938f5-105">name</span><span class="sxs-lookup"><span data-stu-id="938f5-105">Name</span></span>

<span data-ttu-id="938f5-106">`dotnet new` — создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="938f5-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="938f5-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="938f5-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="938f5-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="938f5-108">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="938f5-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="938f5-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="938f5-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="938f5-110">Description</span></span>

<span data-ttu-id="938f5-111">Команда `dotnet new` предоставляет удобный способ инициализации проекта .NET Core.</span><span class="sxs-lookup"><span data-stu-id="938f5-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span> 

<span data-ttu-id="938f5-112">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="938f5-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="938f5-113">Аргументы</span><span class="sxs-lookup"><span data-stu-id="938f5-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="938f5-114">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="938f5-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="938f5-115">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="938f5-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="938f5-116">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="938f5-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="938f5-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="938f5-117">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="938f5-118">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="938f5-118">The command contains a default list of templates.</span></span> <span data-ttu-id="938f5-119">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="938f5-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="938f5-120">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="938f5-120">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="938f5-121">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="938f5-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="938f5-122">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="938f5-122">Template description</span></span>                          | <span data-ttu-id="938f5-123">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="938f5-123">Template name</span></span> | <span data-ttu-id="938f5-124">Языки</span><span class="sxs-lookup"><span data-stu-id="938f5-124">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="938f5-125">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="938f5-125">Console application</span></span>                          | `console`     | <span data-ttu-id="938f5-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="938f5-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="938f5-127">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="938f5-127">Class library</span></span>                                | `classlib`    | <span data-ttu-id="938f5-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="938f5-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="938f5-129">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="938f5-129">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="938f5-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="938f5-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="938f5-131">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="938f5-131">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="938f5-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="938f5-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="938f5-133">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="938f5-133">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="938f5-134">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="938f5-134">[C#], F#</span></span>      |
| <span data-ttu-id="938f5-135">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="938f5-135">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="938f5-136">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="938f5-136">[C#], F#</span></span>      |
| <span data-ttu-id="938f5-137">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="938f5-137">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="938f5-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="938f5-138">[C#]</span></span>          |
| <span data-ttu-id="938f5-139">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="938f5-139">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="938f5-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="938f5-140">[C#]</span></span>          |
| <span data-ttu-id="938f5-141">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="938f5-141">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="938f5-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="938f5-142">[C#]</span></span>          |
| <span data-ttu-id="938f5-143">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="938f5-143">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="938f5-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="938f5-144">[C#]</span></span>          |
| <span data-ttu-id="938f5-145">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="938f5-145">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="938f5-146">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="938f5-146">[C#], F#</span></span>      |
| <span data-ttu-id="938f5-147">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="938f5-147">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="938f5-148">Конфигурация Nuget</span><span class="sxs-lookup"><span data-stu-id="938f5-148">Nuget config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="938f5-149">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="938f5-149">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="938f5-150">Файл решения</span><span class="sxs-lookup"><span data-stu-id="938f5-150">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="938f5-151">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="938f5-151">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="938f5-152">MVC/ViewImports</span><span class="sxs-lookup"><span data-stu-id="938f5-152">MVC/ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="938f5-153">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="938f5-153">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="938f5-154">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="938f5-154">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="938f5-155">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="938f5-155">The command contains a default list of templates.</span></span> <span data-ttu-id="938f5-156">Используйте `dotnet new -all`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="938f5-156">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="938f5-157">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="938f5-157">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="938f5-158">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="938f5-158">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="938f5-159">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="938f5-159">Template description</span></span>  | <span data-ttu-id="938f5-160">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="938f5-160">Template name</span></span> | <span data-ttu-id="938f5-161">Языки</span><span class="sxs-lookup"><span data-stu-id="938f5-161">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="938f5-162">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="938f5-162">Console application</span></span>  | `console`     | <span data-ttu-id="938f5-163">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="938f5-163">[C#], F#</span></span>  |
| <span data-ttu-id="938f5-164">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="938f5-164">Class library</span></span>        | `classlib`    | <span data-ttu-id="938f5-165">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="938f5-165">[C#], F#</span></span>  |
| <span data-ttu-id="938f5-166">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="938f5-166">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="938f5-167">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="938f5-167">[C#], F#</span></span>  |
| <span data-ttu-id="938f5-168">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="938f5-168">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="938f5-169">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="938f5-169">[C#], F#</span></span>  |
| <span data-ttu-id="938f5-170">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="938f5-170">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="938f5-171">[C#]</span><span class="sxs-lookup"><span data-stu-id="938f5-171">[C#]</span></span>      |
| <span data-ttu-id="938f5-172">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="938f5-172">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="938f5-173">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="938f5-173">[C#], F#</span></span>  |
| <span data-ttu-id="938f5-174">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="938f5-174">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="938f5-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="938f5-175">[C#]</span></span>      |
| <span data-ttu-id="938f5-176">Конфигурация Nuget</span><span class="sxs-lookup"><span data-stu-id="938f5-176">Nuget config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="938f5-177">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="938f5-177">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="938f5-178">Файл решения</span><span class="sxs-lookup"><span data-stu-id="938f5-178">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="938f5-179">Параметры</span><span class="sxs-lookup"><span data-stu-id="938f5-179">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="938f5-180">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="938f5-180">.NET Core 2.x</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="938f5-181">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="938f5-181">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="938f5-182">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="938f5-182">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="938f5-183">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="938f5-183">Prints out help for the command.</span></span> <span data-ttu-id="938f5-184">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="938f5-184">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="938f5-185">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="938f5-185">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="938f5-186">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="938f5-186">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="938f5-187">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="938f5-187">Lists templates containing the specified name.</span></span> <span data-ttu-id="938f5-188">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="938f5-188">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="938f5-189">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="938f5-189">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="938f5-190">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="938f5-190">The language of the template to create.</span></span> <span data-ttu-id="938f5-191">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="938f5-191">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="938f5-192">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="938f5-192">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="938f5-193">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="938f5-193">The name for the created output.</span></span> <span data-ttu-id="938f5-194">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="938f5-194">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="938f5-195">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="938f5-195">Location to place the generated output.</span></span> <span data-ttu-id="938f5-196">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="938f5-196">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="938f5-197">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="938f5-197">Filters templates based on available types.</span></span> <span data-ttu-id="938f5-198">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="938f5-198">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="938f5-199">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="938f5-199">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="938f5-200">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="938f5-200">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="938f5-201">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="938f5-201">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="938f5-202">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="938f5-202">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="938f5-203">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="938f5-203">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="938f5-204">Показывает все шаблоны определенного типа проекта при запуске в контексте одной только команды `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="938f5-204">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="938f5-205">При запуске в контексте конкретного шаблона, например `dotnet new web -all`, `-all` интерпретируется как флаг принудительного создания.</span><span class="sxs-lookup"><span data-stu-id="938f5-205">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="938f5-206">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="938f5-206">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="938f5-207">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="938f5-207">Prints out help for the command.</span></span> <span data-ttu-id="938f5-208">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="938f5-208">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="938f5-209">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="938f5-209">Lists templates containing the specified name.</span></span> <span data-ttu-id="938f5-210">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="938f5-210">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="938f5-211">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="938f5-211">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="938f5-212">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="938f5-212">The language of the template to create.</span></span> <span data-ttu-id="938f5-213">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="938f5-213">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="938f5-214">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="938f5-214">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="938f5-215">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="938f5-215">The name for the created output.</span></span> <span data-ttu-id="938f5-216">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="938f5-216">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="938f5-217">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="938f5-217">Location to place the generated output.</span></span> <span data-ttu-id="938f5-218">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="938f5-218">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="938f5-219">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="938f5-219">Template options</span></span>

<span data-ttu-id="938f5-220">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="938f5-220">Each project template may have additional options available.</span></span> <span data-ttu-id="938f5-221">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="938f5-221">The core templates have the following additional options:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="938f5-222">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="938f5-222">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="938f5-223">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="938f5-223">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="938f5-224">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="938f5-224">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="938f5-225">**classlib**</span><span class="sxs-lookup"><span data-stu-id="938f5-225">**classlib**</span></span>

<span data-ttu-id="938f5-226">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="938f5-226">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="938f5-227">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="938f5-227">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="938f5-228">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="938f5-228">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="938f5-229">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="938f5-229">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="938f5-230">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="938f5-230">**mstest, xunit**</span></span>

<span data-ttu-id="938f5-231">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="938f5-231">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="938f5-232">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="938f5-232">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="938f5-233">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="938f5-233">**globaljson**</span></span>

<span data-ttu-id="938f5-234">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="938f5-234">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="938f5-235">**web**</span><span class="sxs-lookup"><span data-stu-id="938f5-235">**web**</span></span>

<span data-ttu-id="938f5-236">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="938f5-236">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="938f5-237">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="938f5-237">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="938f5-238">**webapi**</span><span class="sxs-lookup"><span data-stu-id="938f5-238">**webapi**</span></span>

<span data-ttu-id="938f5-239">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="938f5-239">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="938f5-240">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="938f5-240">The possible values are:</span></span>

- <span data-ttu-id="938f5-241">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="938f5-241">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="938f5-242">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="938f5-242">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="938f5-243">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="938f5-243">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="938f5-244">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="938f5-244">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="938f5-245">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="938f5-245">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="938f5-246">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="938f5-246">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="938f5-247">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="938f5-247">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="938f5-248">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="938f5-248">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="938f5-249">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="938f5-249">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="938f5-250">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="938f5-250">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="938f5-251">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="938f5-251">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="938f5-252">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="938f5-252">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="938f5-253">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="938f5-253">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="938f5-254">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="938f5-254">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="938f5-255">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="938f5-255">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="938f5-256">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="938f5-256">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="938f5-257">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="938f5-257">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="938f5-258">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="938f5-258">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="938f5-259">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="938f5-259">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="938f5-260">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="938f5-260">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="938f5-261">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="938f5-261">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="938f5-262">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="938f5-262">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="938f5-263">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="938f5-263">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="938f5-264">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="938f5-264">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="938f5-265">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="938f5-265">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="938f5-266">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="938f5-266">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="938f5-267">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="938f5-267">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="938f5-268">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="938f5-268">**mvc, razor**</span></span>

<span data-ttu-id="938f5-269">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="938f5-269">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="938f5-270">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="938f5-270">The possible values are:</span></span>

- <span data-ttu-id="938f5-271">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="938f5-271">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="938f5-272">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="938f5-272">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="938f5-273">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="938f5-273">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="938f5-274">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="938f5-274">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="938f5-275">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="938f5-275">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="938f5-276">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="938f5-276">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="938f5-277">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="938f5-277">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="938f5-278">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="938f5-278">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="938f5-279">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="938f5-279">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="938f5-280">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="938f5-280">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="938f5-281">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="938f5-281">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="938f5-282">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="938f5-282">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="938f5-283">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="938f5-283">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="938f5-284">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="938f5-284">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="938f5-285">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="938f5-285">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="938f5-286">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="938f5-286">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="938f5-287">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="938f5-287">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="938f5-288">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="938f5-288">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="938f5-289">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="938f5-289">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="938f5-290">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="938f5-290">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="938f5-291">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="938f5-291">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="938f5-292">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="938f5-292">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="938f5-293">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="938f5-293">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="938f5-294">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="938f5-294">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="938f5-295">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="938f5-295">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="938f5-296">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="938f5-296">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="938f5-297">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="938f5-297">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="938f5-298">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="938f5-298">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="938f5-299">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="938f5-299">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="938f5-300">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="938f5-300">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="938f5-301">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="938f5-301">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="938f5-302">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="938f5-302">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="938f5-303">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="938f5-303">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="938f5-304">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="938f5-304">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="938f5-305">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="938f5-305">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="938f5-306">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="938f5-306">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="938f5-307">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="938f5-307">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="938f5-308">**page**</span><span class="sxs-lookup"><span data-stu-id="938f5-308">**page**</span></span>

<span data-ttu-id="938f5-309">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="938f5-309">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="938f5-310">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="938f5-310">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="938f5-311">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="938f5-311">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="938f5-312">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="938f5-312">**viewimports**</span></span>

<span data-ttu-id="938f5-313">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="938f5-313">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="938f5-314">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="938f5-314">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="938f5-315">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="938f5-315">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="938f5-316">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="938f5-316">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="938f5-317">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="938f5-317">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="938f5-318">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="938f5-318">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="938f5-319">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="938f5-319">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="938f5-320">**classlib**</span><span class="sxs-lookup"><span data-stu-id="938f5-320">**classlib**</span></span>

<span data-ttu-id="938f5-321">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="938f5-321">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="938f5-322">Значения: `netcoreapp1.0`, `netcoreapp1.1` или с `netstandard1.0` по `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="938f5-322">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="938f5-323">Значение по умолчанию — `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="938f5-323">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="938f5-324">**mvc**</span><span class="sxs-lookup"><span data-stu-id="938f5-324">**mvc**</span></span>

<span data-ttu-id="938f5-325">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="938f5-325">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="938f5-326">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="938f5-326">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="938f5-327">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="938f5-327">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="938f5-328">`-au|--auth` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="938f5-328">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="938f5-329">Значения: `None` или `Individual`.</span><span class="sxs-lookup"><span data-stu-id="938f5-329">Values: `None` or `Individual`.</span></span> <span data-ttu-id="938f5-330">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="938f5-330">The default value is `None`.</span></span>

<span data-ttu-id="938f5-331">`-uld|--use-local-db` — указывает, следует ли использовать LocalDB вместо SQLite.</span><span class="sxs-lookup"><span data-stu-id="938f5-331">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="938f5-332">Значения: `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="938f5-332">Values: `true` or `false`.</span></span> <span data-ttu-id="938f5-333">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="938f5-333">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="938f5-334">Примеры</span><span class="sxs-lookup"><span data-stu-id="938f5-334">Examples</span></span>

<span data-ttu-id="938f5-335">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="938f5-335">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang f#`

<span data-ttu-id="938f5-336">Создание проекта стандартной библиотеки классов .NET в указанном каталоге (доступно только при использовании пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="938f5-336">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="938f5-337">Создание проекта приложения ASP.NET Core C# MVC в текущем каталоге без проверки подлинности для .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="938f5-337">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="938f5-338">Создание приложения XUnit, предназначенного для .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="938f5-338">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="938f5-339">Перечислите все шаблоны, доступные для MVC:</span><span class="sxs-lookup"><span data-stu-id="938f5-339">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

## <a name="see-also"></a><span data-ttu-id="938f5-340">См. также</span><span class="sxs-lookup"><span data-stu-id="938f5-340">See also</span></span>

[<span data-ttu-id="938f5-341">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="938f5-341">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="938f5-342">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="938f5-342">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="938f5-343">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="938f5-343">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="938f5-344">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="938f5-344">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
