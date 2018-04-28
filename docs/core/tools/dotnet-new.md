---
title: Команда dotnet new — интерфейс командной строки .NET Core
description: Команда dotnet new создает проекты .NET Core на основе указанного шаблона.
author: mairaw
ms.author: mairaw
ms.date: 03/26/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: ab8d6f779a428aab7bd2739105dcf08b51d14ab9
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-new"></a><span data-ttu-id="c603a-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c603a-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c603a-104">name</span><span class="sxs-lookup"><span data-stu-id="c603a-104">Name</span></span>

<span data-ttu-id="c603a-105">`dotnet new` — создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="c603a-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c603a-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c603a-106">Synopsis</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="c603a-107">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c603a-107">.NET Core 2.0</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c603a-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c603a-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="c603a-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="c603a-109">Description</span></span>

<span data-ttu-id="c603a-110">Команда `dotnet new` предоставляет удобный способ инициализации проекта .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c603a-110">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="c603a-111">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="c603a-111">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="c603a-112">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c603a-112">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="c603a-113">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="c603a-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="c603a-114">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="c603a-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="c603a-115">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="c603a-115">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="c603a-116">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c603a-116">.NET Core 2.0</span></span>](#tab/netcore2x)

<span data-ttu-id="c603a-117">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c603a-117">The command contains a default list of templates.</span></span> <span data-ttu-id="c603a-118">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="c603a-118">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="c603a-119">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="c603a-119">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="c603a-120">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="c603a-120">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="c603a-121">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="c603a-121">Template description</span></span>                          | <span data-ttu-id="c603a-122">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="c603a-122">Template name</span></span> | <span data-ttu-id="c603a-123">Языки</span><span class="sxs-lookup"><span data-stu-id="c603a-123">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="c603a-124">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="c603a-124">Console application</span></span>                          | `console`     | <span data-ttu-id="c603a-125">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c603a-125">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c603a-126">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="c603a-126">Class library</span></span>                                | `classlib`    | <span data-ttu-id="c603a-127">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c603a-127">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c603a-128">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="c603a-128">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="c603a-129">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c603a-129">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c603a-130">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="c603a-130">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="c603a-131">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c603a-131">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c603a-132">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c603a-132">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="c603a-133">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c603a-133">[C#], F#</span></span>      |
| <span data-ttu-id="c603a-134">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="c603a-134">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="c603a-135">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c603a-135">[C#], F#</span></span>      |
| <span data-ttu-id="c603a-136">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c603a-136">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="c603a-137">[C#]</span><span class="sxs-lookup"><span data-stu-id="c603a-137">[C#]</span></span>          |
| <span data-ttu-id="c603a-138">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="c603a-138">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="c603a-139">[C#]</span><span class="sxs-lookup"><span data-stu-id="c603a-139">[C#]</span></span>          |
| <span data-ttu-id="c603a-140">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="c603a-140">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="c603a-141">[C#]</span><span class="sxs-lookup"><span data-stu-id="c603a-141">[C#]</span></span>          |
| <span data-ttu-id="c603a-142">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="c603a-142">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="c603a-143">[C#]</span><span class="sxs-lookup"><span data-stu-id="c603a-143">[C#]</span></span>          |
| <span data-ttu-id="c603a-144">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c603a-144">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="c603a-145">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c603a-145">[C#], F#</span></span>      |
| <span data-ttu-id="c603a-146">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="c603a-146">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="c603a-147">Конфигурация Nuget</span><span class="sxs-lookup"><span data-stu-id="c603a-147">Nuget config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="c603a-148">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="c603a-148">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="c603a-149">Файл решения</span><span class="sxs-lookup"><span data-stu-id="c603a-149">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="c603a-150">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="c603a-150">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="c603a-151">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="c603a-151">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="c603a-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="c603a-152">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c603a-153">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c603a-153">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="c603a-154">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c603a-154">The command contains a default list of templates.</span></span> <span data-ttu-id="c603a-155">Используйте `dotnet new -all`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="c603a-155">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="c603a-156">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="c603a-156">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="c603a-157">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="c603a-157">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="c603a-158">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="c603a-158">Template description</span></span>  | <span data-ttu-id="c603a-159">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="c603a-159">Template name</span></span> | <span data-ttu-id="c603a-160">Языки</span><span class="sxs-lookup"><span data-stu-id="c603a-160">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="c603a-161">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="c603a-161">Console application</span></span>  | `console`     | <span data-ttu-id="c603a-162">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c603a-162">[C#], F#</span></span>  |
| <span data-ttu-id="c603a-163">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="c603a-163">Class library</span></span>        | `classlib`    | <span data-ttu-id="c603a-164">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c603a-164">[C#], F#</span></span>  |
| <span data-ttu-id="c603a-165">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="c603a-165">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="c603a-166">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c603a-166">[C#], F#</span></span>  |
| <span data-ttu-id="c603a-167">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="c603a-167">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="c603a-168">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c603a-168">[C#], F#</span></span>  |
| <span data-ttu-id="c603a-169">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c603a-169">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="c603a-170">[C#]</span><span class="sxs-lookup"><span data-stu-id="c603a-170">[C#]</span></span>      |
| <span data-ttu-id="c603a-171">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c603a-171">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="c603a-172">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c603a-172">[C#], F#</span></span>  |
| <span data-ttu-id="c603a-173">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c603a-173">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="c603a-174">[C#]</span><span class="sxs-lookup"><span data-stu-id="c603a-174">[C#]</span></span>      |
| <span data-ttu-id="c603a-175">Конфигурация Nuget</span><span class="sxs-lookup"><span data-stu-id="c603a-175">Nuget config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="c603a-176">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="c603a-176">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="c603a-177">Файл решения</span><span class="sxs-lookup"><span data-stu-id="c603a-177">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="c603a-178">Параметры</span><span class="sxs-lookup"><span data-stu-id="c603a-178">Options</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="c603a-179">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c603a-179">.NET Core 2.0</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="c603a-180">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="c603a-180">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="c603a-181">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="c603a-181">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="c603a-182">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="c603a-182">Prints out help for the command.</span></span> <span data-ttu-id="c603a-183">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="c603a-183">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="c603a-184">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="c603a-184">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="c603a-185">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="c603a-185">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="c603a-186">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="c603a-186">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="c603a-187">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="c603a-187">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="c603a-188">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="c603a-188">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="c603a-189">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="c603a-189">Lists templates containing the specified name.</span></span> <span data-ttu-id="c603a-190">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="c603a-190">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="c603a-191">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="c603a-191">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="c603a-192">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="c603a-192">The language of the template to create.</span></span> <span data-ttu-id="c603a-193">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="c603a-193">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="c603a-194">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="c603a-194">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="c603a-195">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="c603a-195">The name for the created output.</span></span> <span data-ttu-id="c603a-196">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="c603a-196">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c603a-197">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="c603a-197">Location to place the generated output.</span></span> <span data-ttu-id="c603a-198">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="c603a-198">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="c603a-199">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="c603a-199">Filters templates based on available types.</span></span> <span data-ttu-id="c603a-200">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="c603a-200">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="c603a-201">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="c603a-201">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="c603a-202">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="c603a-202">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="c603a-203">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="c603a-203">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="c603a-204">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="c603a-204">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c603a-205">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c603a-205">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="c603a-206">Показывает все шаблоны определенного типа проекта при запуске в контексте одной только команды `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="c603a-206">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="c603a-207">При запуске в контексте конкретного шаблона, например `dotnet new web -all`, `-all` интерпретируется как флаг принудительного создания.</span><span class="sxs-lookup"><span data-stu-id="c603a-207">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="c603a-208">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="c603a-208">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="c603a-209">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="c603a-209">Prints out help for the command.</span></span> <span data-ttu-id="c603a-210">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="c603a-210">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="c603a-211">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="c603a-211">Lists templates containing the specified name.</span></span> <span data-ttu-id="c603a-212">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="c603a-212">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="c603a-213">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="c603a-213">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="c603a-214">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="c603a-214">The language of the template to create.</span></span> <span data-ttu-id="c603a-215">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="c603a-215">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="c603a-216">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="c603a-216">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="c603a-217">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="c603a-217">The name for the created output.</span></span> <span data-ttu-id="c603a-218">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="c603a-218">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c603a-219">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="c603a-219">Location to place the generated output.</span></span> <span data-ttu-id="c603a-220">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="c603a-220">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="c603a-221">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="c603a-221">Template options</span></span>

<span data-ttu-id="c603a-222">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="c603a-222">Each project template may have additional options available.</span></span> <span data-ttu-id="c603a-223">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="c603a-223">The core templates have the following additional options:</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="c603a-224">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c603a-224">.NET Core 2.0</span></span>](#tab/netcore2x)

<span data-ttu-id="c603a-225">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="c603a-225">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="c603a-226">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="c603a-226">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="c603a-227">**classlib**</span><span class="sxs-lookup"><span data-stu-id="c603a-227">**classlib**</span></span>

<span data-ttu-id="c603a-228">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="c603a-228">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c603a-229">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="c603a-229">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="c603a-230">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="c603a-230">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="c603a-231">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="c603a-231">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="c603a-232">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="c603a-232">**mstest, xunit**</span></span>

<span data-ttu-id="c603a-233">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="c603a-233">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="c603a-234">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="c603a-234">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="c603a-235">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="c603a-235">**globaljson**</span></span>

<span data-ttu-id="c603a-236">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="c603a-236">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="c603a-237">**web**</span><span class="sxs-lookup"><span data-stu-id="c603a-237">**web**</span></span>

<span data-ttu-id="c603a-238">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="c603a-238">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="c603a-239">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="c603a-239">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="c603a-240">**webapi**</span><span class="sxs-lookup"><span data-stu-id="c603a-240">**webapi**</span></span>

<span data-ttu-id="c603a-241">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="c603a-241">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="c603a-242">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="c603a-242">The possible values are:</span></span>

- <span data-ttu-id="c603a-243">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="c603a-243">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="c603a-244">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="c603a-244">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="c603a-245">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="c603a-245">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="c603a-246">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="c603a-246">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="c603a-247">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="c603a-247">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c603a-248">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c603a-248">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c603a-249">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="c603a-249">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="c603a-250">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="c603a-250">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c603a-251">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c603a-251">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c603a-252">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="c603a-252">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c603a-253">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c603a-253">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c603a-254">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="c603a-254">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="c603a-255">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="c603a-255">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="c603a-256">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c603a-256">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="c603a-257">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="c603a-257">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="c603a-258">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="c603a-258">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="c603a-259">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c603a-259">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c603a-260">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="c603a-260">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="c603a-261">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="c603a-261">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c603a-262">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c603a-262">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c603a-263">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="c603a-263">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="c603a-264">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="c603a-264">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="c603a-265">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c603a-265">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="c603a-266">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="c603a-266">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="c603a-267">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="c603a-267">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c603a-268">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c603a-268">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c603a-269">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="c603a-269">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="c603a-270">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="c603a-270">**mvc, razor**</span></span>

<span data-ttu-id="c603a-271">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="c603a-271">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="c603a-272">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="c603a-272">The possible values are:</span></span>

- <span data-ttu-id="c603a-273">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="c603a-273">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="c603a-274">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="c603a-274">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="c603a-275">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="c603a-275">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="c603a-276">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="c603a-276">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="c603a-277">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="c603a-277">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="c603a-278">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="c603a-278">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="c603a-279">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="c603a-279">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c603a-280">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c603a-280">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c603a-281">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="c603a-281">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="c603a-282">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="c603a-282">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c603a-283">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c603a-283">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c603a-284">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="c603a-284">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="c603a-285">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c603a-285">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c603a-286">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="c603a-286">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="c603a-287">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c603a-287">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c603a-288">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="c603a-288">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c603a-289">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c603a-289">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="c603a-290">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="c603a-290">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="c603a-291">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="c603a-291">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="c603a-292">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c603a-292">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="c603a-293">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="c603a-293">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="c603a-294">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="c603a-294">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="c603a-295">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c603a-295">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="c603a-296">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="c603a-296">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="c603a-297">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="c603a-297">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c603a-298">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c603a-298">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="c603a-299">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="c603a-299">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="c603a-300">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="c603a-300">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="c603a-301">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c603a-301">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="c603a-302">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="c603a-302">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="c603a-303">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="c603a-303">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="c603a-304">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c603a-304">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="c603a-305">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="c603a-305">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="c603a-306">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="c603a-306">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="c603a-307">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="c603a-307">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c603a-308">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c603a-308">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c603a-309">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="c603a-309">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="c603a-310">**page**</span><span class="sxs-lookup"><span data-stu-id="c603a-310">**page**</span></span>

<span data-ttu-id="c603a-311">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="c603a-311">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="c603a-312">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="c603a-312">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="c603a-313">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="c603a-313">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="c603a-314">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="c603a-314">**viewimports**</span></span>

<span data-ttu-id="c603a-315">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="c603a-315">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="c603a-316">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="c603a-316">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c603a-317">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c603a-317">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="c603a-318">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="c603a-318">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="c603a-319">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="c603a-319">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c603a-320">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="c603a-320">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="c603a-321">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="c603a-321">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="c603a-322">**classlib**</span><span class="sxs-lookup"><span data-stu-id="c603a-322">**classlib**</span></span>

<span data-ttu-id="c603a-323">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="c603a-323">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c603a-324">Значения: `netcoreapp1.0`, `netcoreapp1.1` или с `netstandard1.0` по `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="c603a-324">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="c603a-325">Значение по умолчанию — `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="c603a-325">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="c603a-326">**mvc**</span><span class="sxs-lookup"><span data-stu-id="c603a-326">**mvc**</span></span>

<span data-ttu-id="c603a-327">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="c603a-327">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c603a-328">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="c603a-328">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="c603a-329">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="c603a-329">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="c603a-330">`-au|--auth` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="c603a-330">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="c603a-331">Значения: `None` или `Individual`.</span><span class="sxs-lookup"><span data-stu-id="c603a-331">Values: `None` or `Individual`.</span></span> <span data-ttu-id="c603a-332">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="c603a-332">The default value is `None`.</span></span>

<span data-ttu-id="c603a-333">`-uld|--use-local-db` — указывает, следует ли использовать LocalDB вместо SQLite.</span><span class="sxs-lookup"><span data-stu-id="c603a-333">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="c603a-334">Значения: `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="c603a-334">Values: `true` or `false`.</span></span> <span data-ttu-id="c603a-335">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="c603a-335">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="c603a-336">Примеры</span><span class="sxs-lookup"><span data-stu-id="c603a-336">Examples</span></span>

<span data-ttu-id="c603a-337">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="c603a-337">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="c603a-338">Создание проекта стандартной библиотеки классов .NET в указанном каталоге (доступно только при использовании пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="c603a-338">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="c603a-339">Создание проекта приложения ASP.NET Core C# MVC в текущем каталоге без проверки подлинности для .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="c603a-339">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="c603a-340">Создание приложения XUnit, предназначенного для .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="c603a-340">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="c603a-341">Перечислите все шаблоны, доступные для MVC:</span><span class="sxs-lookup"><span data-stu-id="c603a-341">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="c603a-342">Установите версию 2.0 шаблонов одностраничного приложения для ASP.NET Core (параметр команды доступен в .NET Core SDK 1.1 и более поздних версиях):</span><span class="sxs-lookup"><span data-stu-id="c603a-342">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

## <a name="see-also"></a><span data-ttu-id="c603a-343">См. также</span><span class="sxs-lookup"><span data-stu-id="c603a-343">See also</span></span>

[<span data-ttu-id="c603a-344">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="c603a-344">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="c603a-345">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="c603a-345">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="c603a-346">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="c603a-346">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="c603a-347">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="c603a-347">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
