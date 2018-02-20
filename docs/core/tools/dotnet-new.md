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
ms.workload:
- dotnetcore
ms.openlocfilehash: ea94c875ae6fe82d0e5d35ba8ca3fd47971fbbe6
ms.sourcegitcommit: e2bf8e6bc365bd9a0e86fe81eeae7d14f85f48c1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2018
---
# <a name="dotnet-new"></a><span data-ttu-id="4ca57-104">dotnet new</span><span class="sxs-lookup"><span data-stu-id="4ca57-104">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="4ca57-105">name</span><span class="sxs-lookup"><span data-stu-id="4ca57-105">Name</span></span>

<span data-ttu-id="4ca57-106">`dotnet new` — создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="4ca57-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4ca57-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4ca57-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="4ca57-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="4ca57-108">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4ca57-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4ca57-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="4ca57-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="4ca57-110">Description</span></span>

<span data-ttu-id="4ca57-111">Команда `dotnet new` предоставляет удобный способ инициализации проекта .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4ca57-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span> 

<span data-ttu-id="4ca57-112">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="4ca57-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="4ca57-113">Аргументы</span><span class="sxs-lookup"><span data-stu-id="4ca57-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="4ca57-114">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="4ca57-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="4ca57-115">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="4ca57-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="4ca57-116">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="4ca57-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="4ca57-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="4ca57-117">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="4ca57-118">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4ca57-118">The command contains a default list of templates.</span></span> <span data-ttu-id="4ca57-119">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="4ca57-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="4ca57-120">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="4ca57-120">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="4ca57-121">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="4ca57-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="4ca57-122">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="4ca57-122">Template description</span></span>                          | <span data-ttu-id="4ca57-123">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="4ca57-123">Template name</span></span> | <span data-ttu-id="4ca57-124">Языки</span><span class="sxs-lookup"><span data-stu-id="4ca57-124">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="4ca57-125">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="4ca57-125">Console application</span></span>                          | `console`     | <span data-ttu-id="4ca57-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4ca57-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4ca57-127">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="4ca57-127">Class library</span></span>                                | `classlib`    | <span data-ttu-id="4ca57-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4ca57-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4ca57-129">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="4ca57-129">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="4ca57-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4ca57-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4ca57-131">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="4ca57-131">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="4ca57-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4ca57-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4ca57-133">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4ca57-133">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="4ca57-134">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4ca57-134">[C#], F#</span></span>      |
| <span data-ttu-id="4ca57-135">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="4ca57-135">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="4ca57-136">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4ca57-136">[C#], F#</span></span>      |
| <span data-ttu-id="4ca57-137">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4ca57-137">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="4ca57-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="4ca57-138">[C#]</span></span>          |
| <span data-ttu-id="4ca57-139">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="4ca57-139">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="4ca57-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="4ca57-140">[C#]</span></span>          |
| <span data-ttu-id="4ca57-141">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="4ca57-141">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="4ca57-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="4ca57-142">[C#]</span></span>          |
| <span data-ttu-id="4ca57-143">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="4ca57-143">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="4ca57-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="4ca57-144">[C#]</span></span>          |
| <span data-ttu-id="4ca57-145">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4ca57-145">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="4ca57-146">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4ca57-146">[C#], F#</span></span>      |
| <span data-ttu-id="4ca57-147">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="4ca57-147">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="4ca57-148">Конфигурация Nuget</span><span class="sxs-lookup"><span data-stu-id="4ca57-148">Nuget config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="4ca57-149">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="4ca57-149">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="4ca57-150">Файл решения</span><span class="sxs-lookup"><span data-stu-id="4ca57-150">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="4ca57-151">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="4ca57-151">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="4ca57-152">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="4ca57-152">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="4ca57-153">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="4ca57-153">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4ca57-154">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4ca57-154">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="4ca57-155">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4ca57-155">The command contains a default list of templates.</span></span> <span data-ttu-id="4ca57-156">Используйте `dotnet new -all`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="4ca57-156">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="4ca57-157">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="4ca57-157">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="4ca57-158">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="4ca57-158">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="4ca57-159">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="4ca57-159">Template description</span></span>  | <span data-ttu-id="4ca57-160">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="4ca57-160">Template name</span></span> | <span data-ttu-id="4ca57-161">Языки</span><span class="sxs-lookup"><span data-stu-id="4ca57-161">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="4ca57-162">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="4ca57-162">Console application</span></span>  | `console`     | <span data-ttu-id="4ca57-163">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4ca57-163">[C#], F#</span></span>  |
| <span data-ttu-id="4ca57-164">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="4ca57-164">Class library</span></span>        | `classlib`    | <span data-ttu-id="4ca57-165">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4ca57-165">[C#], F#</span></span>  |
| <span data-ttu-id="4ca57-166">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="4ca57-166">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="4ca57-167">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4ca57-167">[C#], F#</span></span>  |
| <span data-ttu-id="4ca57-168">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="4ca57-168">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="4ca57-169">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4ca57-169">[C#], F#</span></span>  |
| <span data-ttu-id="4ca57-170">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4ca57-170">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="4ca57-171">[C#]</span><span class="sxs-lookup"><span data-stu-id="4ca57-171">[C#]</span></span>      |
| <span data-ttu-id="4ca57-172">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4ca57-172">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="4ca57-173">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4ca57-173">[C#], F#</span></span>  |
| <span data-ttu-id="4ca57-174">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4ca57-174">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="4ca57-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="4ca57-175">[C#]</span></span>      |
| <span data-ttu-id="4ca57-176">Конфигурация Nuget</span><span class="sxs-lookup"><span data-stu-id="4ca57-176">Nuget config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="4ca57-177">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="4ca57-177">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="4ca57-178">Файл решения</span><span class="sxs-lookup"><span data-stu-id="4ca57-178">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="4ca57-179">Параметры</span><span class="sxs-lookup"><span data-stu-id="4ca57-179">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="4ca57-180">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="4ca57-180">.NET Core 2.x</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="4ca57-181">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="4ca57-181">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="4ca57-182">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="4ca57-182">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="4ca57-183">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="4ca57-183">Prints out help for the command.</span></span> <span data-ttu-id="4ca57-184">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-184">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="4ca57-185">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-185">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="4ca57-186">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="4ca57-186">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="4ca57-187">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="4ca57-187">Lists templates containing the specified name.</span></span> <span data-ttu-id="4ca57-188">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="4ca57-188">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="4ca57-189">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="4ca57-189">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="4ca57-190">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="4ca57-190">The language of the template to create.</span></span> <span data-ttu-id="4ca57-191">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="4ca57-191">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="4ca57-192">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="4ca57-192">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="4ca57-193">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="4ca57-193">The name for the created output.</span></span> <span data-ttu-id="4ca57-194">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="4ca57-194">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="4ca57-195">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="4ca57-195">Location to place the generated output.</span></span> <span data-ttu-id="4ca57-196">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="4ca57-196">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="4ca57-197">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="4ca57-197">Filters templates based on available types.</span></span> <span data-ttu-id="4ca57-198">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="4ca57-198">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="4ca57-199">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-199">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="4ca57-200">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="4ca57-200">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="4ca57-201">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="4ca57-201">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="4ca57-202">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="4ca57-202">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4ca57-203">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4ca57-203">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="4ca57-204">Показывает все шаблоны определенного типа проекта при запуске в контексте одной только команды `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-204">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="4ca57-205">При запуске в контексте конкретного шаблона, например `dotnet new web -all`, `-all` интерпретируется как флаг принудительного создания.</span><span class="sxs-lookup"><span data-stu-id="4ca57-205">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="4ca57-206">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="4ca57-206">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="4ca57-207">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="4ca57-207">Prints out help for the command.</span></span> <span data-ttu-id="4ca57-208">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-208">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="4ca57-209">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="4ca57-209">Lists templates containing the specified name.</span></span> <span data-ttu-id="4ca57-210">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="4ca57-210">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="4ca57-211">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="4ca57-211">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="4ca57-212">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="4ca57-212">The language of the template to create.</span></span> <span data-ttu-id="4ca57-213">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="4ca57-213">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="4ca57-214">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="4ca57-214">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="4ca57-215">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="4ca57-215">The name for the created output.</span></span> <span data-ttu-id="4ca57-216">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="4ca57-216">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="4ca57-217">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="4ca57-217">Location to place the generated output.</span></span> <span data-ttu-id="4ca57-218">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="4ca57-218">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="4ca57-219">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="4ca57-219">Template options</span></span>

<span data-ttu-id="4ca57-220">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="4ca57-220">Each project template may have additional options available.</span></span> <span data-ttu-id="4ca57-221">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="4ca57-221">The core templates have the following additional options:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="4ca57-222">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="4ca57-222">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="4ca57-223">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="4ca57-223">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="4ca57-224">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="4ca57-224">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="4ca57-225">**classlib**</span><span class="sxs-lookup"><span data-stu-id="4ca57-225">**classlib**</span></span>

<span data-ttu-id="4ca57-226">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="4ca57-226">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4ca57-227">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="4ca57-227">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="4ca57-228">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-228">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="4ca57-229">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="4ca57-229">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="4ca57-230">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="4ca57-230">**mstest, xunit**</span></span>

<span data-ttu-id="4ca57-231">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="4ca57-231">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="4ca57-232">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="4ca57-232">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="4ca57-233">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="4ca57-233">**globaljson**</span></span>

<span data-ttu-id="4ca57-234">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="4ca57-234">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="4ca57-235">**web**</span><span class="sxs-lookup"><span data-stu-id="4ca57-235">**web**</span></span>

<span data-ttu-id="4ca57-236">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="4ca57-236">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="4ca57-237">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="4ca57-237">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="4ca57-238">**webapi**</span><span class="sxs-lookup"><span data-stu-id="4ca57-238">**webapi**</span></span>

<span data-ttu-id="4ca57-239">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="4ca57-239">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="4ca57-240">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="4ca57-240">The possible values are:</span></span>

- <span data-ttu-id="4ca57-241">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="4ca57-241">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="4ca57-242">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="4ca57-242">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="4ca57-243">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="4ca57-243">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="4ca57-244">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="4ca57-244">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="4ca57-245">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="4ca57-245">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="4ca57-246">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-246">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="4ca57-247">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-247">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="4ca57-248">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="4ca57-248">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="4ca57-249">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-249">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4ca57-250">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="4ca57-250">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="4ca57-251">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-251">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4ca57-252">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-252">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="4ca57-253">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="4ca57-253">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="4ca57-254">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-254">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="4ca57-255">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-255">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="4ca57-256">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="4ca57-256">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="4ca57-257">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-257">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4ca57-258">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-258">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="4ca57-259">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="4ca57-259">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="4ca57-260">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-260">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4ca57-261">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-261">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="4ca57-262">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="4ca57-262">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="4ca57-263">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-263">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="4ca57-264">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="4ca57-264">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="4ca57-265">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="4ca57-265">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="4ca57-266">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-266">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4ca57-267">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="4ca57-267">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="4ca57-268">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="4ca57-268">**mvc, razor**</span></span>

<span data-ttu-id="4ca57-269">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="4ca57-269">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="4ca57-270">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="4ca57-270">The possible values are:</span></span>

- <span data-ttu-id="4ca57-271">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="4ca57-271">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="4ca57-272">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="4ca57-272">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="4ca57-273">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="4ca57-273">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="4ca57-274">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="4ca57-274">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="4ca57-275">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="4ca57-275">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="4ca57-276">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="4ca57-276">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="4ca57-277">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="4ca57-277">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="4ca57-278">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-278">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="4ca57-279">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-279">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="4ca57-280">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="4ca57-280">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="4ca57-281">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-281">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4ca57-282">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="4ca57-282">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="4ca57-283">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-283">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4ca57-284">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="4ca57-284">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="4ca57-285">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-285">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4ca57-286">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="4ca57-286">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="4ca57-287">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-287">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="4ca57-288">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-288">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="4ca57-289">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="4ca57-289">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="4ca57-290">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-290">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="4ca57-291">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-291">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="4ca57-292">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="4ca57-292">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="4ca57-293">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-293">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="4ca57-294">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-294">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="4ca57-295">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="4ca57-295">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="4ca57-296">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-296">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="4ca57-297">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-297">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="4ca57-298">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="4ca57-298">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="4ca57-299">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-299">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="4ca57-300">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-300">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="4ca57-301">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="4ca57-301">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="4ca57-302">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-302">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="4ca57-303">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="4ca57-303">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="4ca57-304">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="4ca57-304">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="4ca57-305">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="4ca57-305">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="4ca57-306">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-306">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4ca57-307">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="4ca57-307">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="4ca57-308">**page**</span><span class="sxs-lookup"><span data-stu-id="4ca57-308">**page**</span></span>

<span data-ttu-id="4ca57-309">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="4ca57-309">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="4ca57-310">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-310">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="4ca57-311">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="4ca57-311">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="4ca57-312">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="4ca57-312">**viewimports**</span></span>

<span data-ttu-id="4ca57-313">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="4ca57-313">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="4ca57-314">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-314">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4ca57-315">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4ca57-315">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="4ca57-316">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="4ca57-316">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="4ca57-317">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="4ca57-317">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4ca57-318">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-318">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="4ca57-319">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-319">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="4ca57-320">**classlib**</span><span class="sxs-lookup"><span data-stu-id="4ca57-320">**classlib**</span></span>

<span data-ttu-id="4ca57-321">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="4ca57-321">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4ca57-322">Значения: `netcoreapp1.0`, `netcoreapp1.1` или с `netstandard1.0` по `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-322">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="4ca57-323">Значение по умолчанию — `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-323">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="4ca57-324">**mvc**</span><span class="sxs-lookup"><span data-stu-id="4ca57-324">**mvc**</span></span>

<span data-ttu-id="4ca57-325">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="4ca57-325">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4ca57-326">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-326">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="4ca57-327">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-327">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="4ca57-328">`-au|--auth` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="4ca57-328">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="4ca57-329">Значения: `None` или `Individual`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-329">Values: `None` or `Individual`.</span></span> <span data-ttu-id="4ca57-330">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-330">The default value is `None`.</span></span>

<span data-ttu-id="4ca57-331">`-uld|--use-local-db` — указывает, следует ли использовать LocalDB вместо SQLite.</span><span class="sxs-lookup"><span data-stu-id="4ca57-331">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="4ca57-332">Значения: `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-332">Values: `true` or `false`.</span></span> <span data-ttu-id="4ca57-333">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="4ca57-333">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="4ca57-334">Примеры</span><span class="sxs-lookup"><span data-stu-id="4ca57-334">Examples</span></span>

<span data-ttu-id="4ca57-335">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="4ca57-335">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang f#`

<span data-ttu-id="4ca57-336">Создание проекта стандартной библиотеки классов .NET в указанном каталоге (доступно только при использовании пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="4ca57-336">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="4ca57-337">Создание проекта приложения ASP.NET Core C# MVC в текущем каталоге без проверки подлинности для .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="4ca57-337">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="4ca57-338">Создание приложения XUnit, предназначенного для .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="4ca57-338">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="4ca57-339">Перечислите все шаблоны, доступные для MVC:</span><span class="sxs-lookup"><span data-stu-id="4ca57-339">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

## <a name="see-also"></a><span data-ttu-id="4ca57-340">См. также</span><span class="sxs-lookup"><span data-stu-id="4ca57-340">See also</span></span>

[<span data-ttu-id="4ca57-341">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="4ca57-341">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="4ca57-342">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="4ca57-342">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="4ca57-343">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="4ca57-343">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="4ca57-344">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="4ca57-344">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
