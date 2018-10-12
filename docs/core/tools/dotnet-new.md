---
title: Команда dotnet new — интерфейс командной строки .NET Core
description: Команда dotnet new создает проекты .NET Core на основе указанного шаблона.
author: mairaw
ms.author: mairaw
ms.date: 07/31/2018
ms.openlocfilehash: 396c4ddf09854fa4582226bdb1422f8c929e459b
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2018
ms.locfileid: "47208637"
---
# <a name="dotnet-new"></a><span data-ttu-id="c306a-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c306a-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c306a-104">name</span><span class="sxs-lookup"><span data-stu-id="c306a-104">Name</span></span>

<span data-ttu-id="c306a-105">`dotnet new` — создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="c306a-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c306a-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c306a-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c306a-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c306a-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c306a-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c306a-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c306a-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c306a-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="c306a-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="c306a-110">Description</span></span>

<span data-ttu-id="c306a-111">Команда `dotnet new` предоставляет удобный способ инициализации проекта .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c306a-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="c306a-112">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="c306a-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="c306a-113">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c306a-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="c306a-114">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="c306a-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="c306a-115">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="c306a-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="c306a-116">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="c306a-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c306a-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c306a-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="c306a-118">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c306a-118">The command contains a default list of templates.</span></span> <span data-ttu-id="c306a-119">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="c306a-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="c306a-120">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="c306a-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="c306a-121">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="c306a-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="c306a-122">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="c306a-122">Template description</span></span>                          | <span data-ttu-id="c306a-123">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="c306a-123">Template name</span></span>   | <span data-ttu-id="c306a-124">Языки</span><span class="sxs-lookup"><span data-stu-id="c306a-124">Languages</span></span>     |
|----------------------------------------------|-----------------|---------------|
| <span data-ttu-id="c306a-125">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="c306a-125">Console application</span></span>                          | `console`       | <span data-ttu-id="c306a-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c306a-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c306a-127">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="c306a-127">Class library</span></span>                                | `classlib`      | <span data-ttu-id="c306a-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c306a-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c306a-129">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="c306a-129">Unit test project</span></span>                            | `mstest`        | <span data-ttu-id="c306a-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c306a-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c306a-131">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="c306a-131">xUnit test project</span></span>                           | `xunit`         | <span data-ttu-id="c306a-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c306a-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c306a-133">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="c306a-133">Razor page</span></span>                                   | `page`          | <span data-ttu-id="c306a-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="c306a-134">[C#]</span></span>          |
| <span data-ttu-id="c306a-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="c306a-135">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="c306a-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="c306a-136">[C#]</span></span>          |
| <span data-ttu-id="c306a-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="c306a-137">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="c306a-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="c306a-138">[C#]</span></span>          |
| <span data-ttu-id="c306a-139">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c306a-139">ASP.NET Core empty</span></span>                           | `web`           | <span data-ttu-id="c306a-140">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c306a-140">[C#], F#</span></span>      |
| <span data-ttu-id="c306a-141">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="c306a-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="c306a-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c306a-142">[C#], F#</span></span>      |
| <span data-ttu-id="c306a-143">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c306a-143">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="c306a-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="c306a-144">[C#]</span></span>          |
| <span data-ttu-id="c306a-145">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="c306a-145">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="c306a-146">[C#]</span><span class="sxs-lookup"><span data-stu-id="c306a-146">[C#]</span></span>          |
| <span data-ttu-id="c306a-147">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="c306a-147">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="c306a-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="c306a-148">[C#]</span></span>          |
| <span data-ttu-id="c306a-149">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="c306a-149">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="c306a-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="c306a-150">[C#]</span></span>          |
| <span data-ttu-id="c306a-151">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c306a-151">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="c306a-152">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c306a-152">[C#], F#</span></span>      |
| <span data-ttu-id="c306a-153">Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="c306a-153">Razor class library</span></span>                          | `razorclasslib` | <span data-ttu-id="c306a-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="c306a-154">[C#]</span></span>          |
| <span data-ttu-id="c306a-155">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="c306a-155">global.json file</span></span>                             | `globaljson`    |               |
| <span data-ttu-id="c306a-156">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="c306a-156">NuGet config</span></span>                                 | `nugetconfig`   |               |
| <span data-ttu-id="c306a-157">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="c306a-157">Web config</span></span>                                   | `webconfig`     |               |
| <span data-ttu-id="c306a-158">Файл решения</span><span class="sxs-lookup"><span data-stu-id="c306a-158">Solution file</span></span>                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c306a-159">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c306a-159">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="c306a-160">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c306a-160">The command contains a default list of templates.</span></span> <span data-ttu-id="c306a-161">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="c306a-161">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="c306a-162">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="c306a-162">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="c306a-163">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="c306a-163">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="c306a-164">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="c306a-164">Template description</span></span>                          | <span data-ttu-id="c306a-165">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="c306a-165">Template name</span></span> | <span data-ttu-id="c306a-166">Языки</span><span class="sxs-lookup"><span data-stu-id="c306a-166">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="c306a-167">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="c306a-167">Console application</span></span>                          | `console`     | <span data-ttu-id="c306a-168">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c306a-168">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c306a-169">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="c306a-169">Class library</span></span>                                | `classlib`    | <span data-ttu-id="c306a-170">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c306a-170">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c306a-171">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="c306a-171">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="c306a-172">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c306a-172">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c306a-173">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="c306a-173">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="c306a-174">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c306a-174">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c306a-175">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c306a-175">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="c306a-176">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c306a-176">[C#], F#</span></span>      |
| <span data-ttu-id="c306a-177">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="c306a-177">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="c306a-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c306a-178">[C#], F#</span></span>      |
| <span data-ttu-id="c306a-179">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c306a-179">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="c306a-180">[C#]</span><span class="sxs-lookup"><span data-stu-id="c306a-180">[C#]</span></span>          |
| <span data-ttu-id="c306a-181">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="c306a-181">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="c306a-182">[C#]</span><span class="sxs-lookup"><span data-stu-id="c306a-182">[C#]</span></span>          |
| <span data-ttu-id="c306a-183">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="c306a-183">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="c306a-184">[C#]</span><span class="sxs-lookup"><span data-stu-id="c306a-184">[C#]</span></span>          |
| <span data-ttu-id="c306a-185">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="c306a-185">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="c306a-186">[C#]</span><span class="sxs-lookup"><span data-stu-id="c306a-186">[C#]</span></span>          |
| <span data-ttu-id="c306a-187">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c306a-187">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="c306a-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c306a-188">[C#], F#</span></span>      |
| <span data-ttu-id="c306a-189">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="c306a-189">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="c306a-190">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="c306a-190">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="c306a-191">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="c306a-191">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="c306a-192">Файл решения</span><span class="sxs-lookup"><span data-stu-id="c306a-192">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="c306a-193">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="c306a-193">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="c306a-194">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="c306a-194">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="c306a-195">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="c306a-195">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c306a-196">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c306a-196">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="c306a-197">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c306a-197">The command contains a default list of templates.</span></span> <span data-ttu-id="c306a-198">Используйте `dotnet new -all`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="c306a-198">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="c306a-199">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="c306a-199">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="c306a-200">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="c306a-200">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="c306a-201">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="c306a-201">Template description</span></span>  | <span data-ttu-id="c306a-202">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="c306a-202">Template name</span></span> | <span data-ttu-id="c306a-203">Языки</span><span class="sxs-lookup"><span data-stu-id="c306a-203">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="c306a-204">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="c306a-204">Console application</span></span>  | `console`     | <span data-ttu-id="c306a-205">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c306a-205">[C#], F#</span></span>  |
| <span data-ttu-id="c306a-206">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="c306a-206">Class library</span></span>        | `classlib`    | <span data-ttu-id="c306a-207">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c306a-207">[C#], F#</span></span>  |
| <span data-ttu-id="c306a-208">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="c306a-208">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="c306a-209">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c306a-209">[C#], F#</span></span>  |
| <span data-ttu-id="c306a-210">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="c306a-210">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="c306a-211">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c306a-211">[C#], F#</span></span>  |
| <span data-ttu-id="c306a-212">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c306a-212">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="c306a-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="c306a-213">[C#]</span></span>      |
| <span data-ttu-id="c306a-214">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c306a-214">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="c306a-215">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c306a-215">[C#], F#</span></span>  |
| <span data-ttu-id="c306a-216">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c306a-216">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="c306a-217">[C#]</span><span class="sxs-lookup"><span data-stu-id="c306a-217">[C#]</span></span>      |
| <span data-ttu-id="c306a-218">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="c306a-218">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="c306a-219">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="c306a-219">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="c306a-220">Файл решения</span><span class="sxs-lookup"><span data-stu-id="c306a-220">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="c306a-221">Параметры</span><span class="sxs-lookup"><span data-stu-id="c306a-221">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c306a-222">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c306a-222">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="c306a-223">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="c306a-223">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="c306a-224">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="c306a-224">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="c306a-225">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="c306a-225">Prints out help for the command.</span></span> <span data-ttu-id="c306a-226">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="c306a-226">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="c306a-227">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="c306a-227">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="c306a-228">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="c306a-228">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="c306a-229">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="c306a-229">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="c306a-230">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="c306a-230">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="c306a-231">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="c306a-231">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="c306a-232">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="c306a-232">Lists templates containing the specified name.</span></span> <span data-ttu-id="c306a-233">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="c306a-233">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="c306a-234">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="c306a-234">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="c306a-235">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="c306a-235">The language of the template to create.</span></span> <span data-ttu-id="c306a-236">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="c306a-236">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="c306a-237">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="c306a-237">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="c306a-238">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="c306a-238">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="c306a-239">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="c306a-239">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="c306a-240">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="c306a-240">The name for the created output.</span></span> <span data-ttu-id="c306a-241">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="c306a-241">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="c306a-242">Задает источник пакетов NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="c306a-242">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c306a-243">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="c306a-243">Location to place the generated output.</span></span> <span data-ttu-id="c306a-244">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="c306a-244">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="c306a-245">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="c306a-245">Filters templates based on available types.</span></span> <span data-ttu-id="c306a-246">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="c306a-246">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="c306a-247">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="c306a-247">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="c306a-248">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="c306a-248">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="c306a-249">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="c306a-249">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="c306a-250">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="c306a-250">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c306a-251">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c306a-251">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="c306a-252">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="c306a-252">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="c306a-253">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="c306a-253">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="c306a-254">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="c306a-254">Prints out help for the command.</span></span> <span data-ttu-id="c306a-255">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="c306a-255">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="c306a-256">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="c306a-256">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="c306a-257">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="c306a-257">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="c306a-258">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="c306a-258">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="c306a-259">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="c306a-259">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="c306a-260">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="c306a-260">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="c306a-261">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="c306a-261">Lists templates containing the specified name.</span></span> <span data-ttu-id="c306a-262">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="c306a-262">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="c306a-263">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="c306a-263">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="c306a-264">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="c306a-264">The language of the template to create.</span></span> <span data-ttu-id="c306a-265">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="c306a-265">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="c306a-266">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="c306a-266">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="c306a-267">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="c306a-267">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="c306a-268">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="c306a-268">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="c306a-269">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="c306a-269">The name for the created output.</span></span> <span data-ttu-id="c306a-270">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="c306a-270">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c306a-271">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="c306a-271">Location to place the generated output.</span></span> <span data-ttu-id="c306a-272">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="c306a-272">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="c306a-273">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="c306a-273">Filters templates based on available types.</span></span> <span data-ttu-id="c306a-274">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="c306a-274">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="c306a-275">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="c306a-275">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="c306a-276">Чтобы удалить шаблон, используя путь к исходному пакету `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="c306a-276">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="c306a-277">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="c306a-277">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="c306a-278">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="c306a-278">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="c306a-279">Если вам не удается определить аргумент `PATH` или `NUGET_ID`, необходимый для удаления шаблона, выполните команду `dotnet new --uninstall` без аргумента. В результате будут перечислены все установленные шаблоны и аргумент, необходимый для их удаления.</span><span class="sxs-lookup"><span data-stu-id="c306a-279">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c306a-280">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c306a-280">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="c306a-281">Показывает все шаблоны определенного типа проекта при запуске в контексте одной только команды `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="c306a-281">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="c306a-282">При запуске в контексте конкретного шаблона, например `dotnet new web -all`, `-all` интерпретируется как флаг принудительного создания.</span><span class="sxs-lookup"><span data-stu-id="c306a-282">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="c306a-283">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="c306a-283">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="c306a-284">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="c306a-284">Prints out help for the command.</span></span> <span data-ttu-id="c306a-285">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="c306a-285">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="c306a-286">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="c306a-286">Lists templates containing the specified name.</span></span> <span data-ttu-id="c306a-287">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="c306a-287">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="c306a-288">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="c306a-288">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="c306a-289">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="c306a-289">The language of the template to create.</span></span> <span data-ttu-id="c306a-290">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="c306a-290">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="c306a-291">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="c306a-291">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="c306a-292">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="c306a-292">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="c306a-293">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="c306a-293">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="c306a-294">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="c306a-294">The name for the created output.</span></span> <span data-ttu-id="c306a-295">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="c306a-295">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c306a-296">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="c306a-296">Location to place the generated output.</span></span> <span data-ttu-id="c306a-297">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="c306a-297">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="c306a-298">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="c306a-298">Template options</span></span>

<span data-ttu-id="c306a-299">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="c306a-299">Each project template may have additional options available.</span></span> <span data-ttu-id="c306a-300">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="c306a-300">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c306a-301">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c306a-301">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="c306a-302">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="c306a-302">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="c306a-303">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="c306a-303">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c306a-304">**classlib**</span><span class="sxs-lookup"><span data-stu-id="c306a-304">**classlib**</span></span>

<span data-ttu-id="c306a-305">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="c306a-305">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c306a-306">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="c306a-306">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="c306a-307">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="c306a-307">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="c306a-308">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="c306a-308">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c306a-309">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="c306a-309">**mstest, xunit**</span></span>

<span data-ttu-id="c306a-310">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="c306a-310">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="c306a-311">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="c306a-311">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c306a-312">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="c306a-312">**globaljson**</span></span>

<span data-ttu-id="c306a-313">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="c306a-313">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="c306a-314">**web**</span><span class="sxs-lookup"><span data-stu-id="c306a-314">**web**</span></span>

<span data-ttu-id="c306a-315">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="c306a-315">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="c306a-316">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="c306a-316">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c306a-317">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c306a-317">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="c306a-318">Этот параметр применяется, только если `IndividualAuth` или `OrganizationalAuth` не используются.</span><span class="sxs-lookup"><span data-stu-id="c306a-318">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="c306a-319">**webapi**</span><span class="sxs-lookup"><span data-stu-id="c306a-319">**webapi**</span></span>

<span data-ttu-id="c306a-320">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="c306a-320">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="c306a-321">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="c306a-321">The possible values are:</span></span>

- <span data-ttu-id="c306a-322">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="c306a-322">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="c306a-323">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="c306a-323">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="c306a-324">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="c306a-324">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="c306a-325">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="c306a-325">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="c306a-326">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="c306a-326">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c306a-327">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c306a-327">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c306a-328">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="c306a-328">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="c306a-329">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="c306a-329">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c306a-330">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c306a-330">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c306a-331">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="c306a-331">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c306a-332">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c306a-332">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c306a-333">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="c306a-333">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="c306a-334">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="c306a-334">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="c306a-335">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c306a-335">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="c306a-336">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="c306a-336">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="c306a-337">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="c306a-337">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="c306a-338">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c306a-338">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c306a-339">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="c306a-339">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="c306a-340">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="c306a-340">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c306a-341">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c306a-341">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c306a-342">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="c306a-342">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="c306a-343">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="c306a-343">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="c306a-344">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c306a-344">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="c306a-345">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="c306a-345">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="c306a-346">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="c306a-346">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c306a-347">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c306a-347">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c306a-348">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="c306a-348">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c306a-349">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c306a-349">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="c306a-350">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="c306a-350">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="c306a-351">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="c306a-351">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="c306a-352">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="c306a-352">**mvc, razor**</span></span>

<span data-ttu-id="c306a-353">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="c306a-353">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="c306a-354">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="c306a-354">The possible values are:</span></span>

- <span data-ttu-id="c306a-355">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="c306a-355">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="c306a-356">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="c306a-356">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="c306a-357">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="c306a-357">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="c306a-358">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="c306a-358">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="c306a-359">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="c306a-359">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="c306a-360">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="c306a-360">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="c306a-361">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="c306a-361">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c306a-362">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c306a-362">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c306a-363">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="c306a-363">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="c306a-364">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="c306a-364">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c306a-365">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c306a-365">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c306a-366">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="c306a-366">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="c306a-367">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c306a-367">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c306a-368">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="c306a-368">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="c306a-369">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c306a-369">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c306a-370">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="c306a-370">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c306a-371">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c306a-371">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="c306a-372">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="c306a-372">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="c306a-373">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="c306a-373">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="c306a-374">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c306a-374">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="c306a-375">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="c306a-375">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="c306a-376">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="c306a-376">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="c306a-377">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c306a-377">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c306a-378">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="c306a-378">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="c306a-379">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="c306a-379">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c306a-380">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c306a-380">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c306a-381">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="c306a-381">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="c306a-382">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="c306a-382">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="c306a-383">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c306a-383">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c306a-384">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="c306a-384">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="c306a-385">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="c306a-385">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="c306a-386">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c306a-386">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="c306a-387">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="c306a-387">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="c306a-388">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="c306a-388">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="c306a-389">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="c306a-389">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c306a-390">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c306a-390">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c306a-391">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="c306a-391">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c306a-392">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c306a-392">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="c306a-393">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="c306a-393">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="c306a-394">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="c306a-394">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="c306a-395">**page**</span><span class="sxs-lookup"><span data-stu-id="c306a-395">**page**</span></span>

<span data-ttu-id="c306a-396">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="c306a-396">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="c306a-397">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="c306a-397">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="c306a-398">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="c306a-398">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="c306a-399">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="c306a-399">**viewimports**</span></span>

<span data-ttu-id="c306a-400">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="c306a-400">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="c306a-401">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="c306a-401">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c306a-402">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c306a-402">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="c306a-403">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="c306a-403">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="c306a-404">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="c306a-404">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c306a-405">**classlib**</span><span class="sxs-lookup"><span data-stu-id="c306a-405">**classlib**</span></span>

<span data-ttu-id="c306a-406">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="c306a-406">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c306a-407">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="c306a-407">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="c306a-408">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="c306a-408">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="c306a-409">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="c306a-409">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c306a-410">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="c306a-410">**mstest, xunit**</span></span>

<span data-ttu-id="c306a-411">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="c306a-411">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="c306a-412">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="c306a-412">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c306a-413">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="c306a-413">**globaljson**</span></span>

<span data-ttu-id="c306a-414">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="c306a-414">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="c306a-415">**web**</span><span class="sxs-lookup"><span data-stu-id="c306a-415">**web**</span></span>

<span data-ttu-id="c306a-416">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="c306a-416">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="c306a-417">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="c306a-417">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c306a-418">**webapi**</span><span class="sxs-lookup"><span data-stu-id="c306a-418">**webapi**</span></span>

<span data-ttu-id="c306a-419">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="c306a-419">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="c306a-420">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="c306a-420">The possible values are:</span></span>

- <span data-ttu-id="c306a-421">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="c306a-421">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="c306a-422">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="c306a-422">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="c306a-423">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="c306a-423">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="c306a-424">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="c306a-424">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="c306a-425">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="c306a-425">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c306a-426">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c306a-426">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c306a-427">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="c306a-427">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="c306a-428">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="c306a-428">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c306a-429">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c306a-429">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c306a-430">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="c306a-430">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c306a-431">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c306a-431">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c306a-432">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="c306a-432">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="c306a-433">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="c306a-433">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="c306a-434">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c306a-434">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="c306a-435">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="c306a-435">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="c306a-436">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="c306a-436">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="c306a-437">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c306a-437">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c306a-438">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="c306a-438">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="c306a-439">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="c306a-439">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c306a-440">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c306a-440">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c306a-441">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="c306a-441">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="c306a-442">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="c306a-442">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="c306a-443">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c306a-443">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="c306a-444">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="c306a-444">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="c306a-445">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="c306a-445">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c306a-446">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c306a-446">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c306a-447">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="c306a-447">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c306a-448">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="c306a-448">**mvc, razor**</span></span>

<span data-ttu-id="c306a-449">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="c306a-449">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="c306a-450">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="c306a-450">The possible values are:</span></span>

- <span data-ttu-id="c306a-451">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="c306a-451">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="c306a-452">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="c306a-452">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="c306a-453">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="c306a-453">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="c306a-454">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="c306a-454">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="c306a-455">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="c306a-455">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="c306a-456">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="c306a-456">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="c306a-457">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="c306a-457">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c306a-458">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c306a-458">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c306a-459">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="c306a-459">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="c306a-460">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="c306a-460">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c306a-461">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c306a-461">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c306a-462">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="c306a-462">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="c306a-463">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c306a-463">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c306a-464">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="c306a-464">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="c306a-465">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c306a-465">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c306a-466">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="c306a-466">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c306a-467">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c306a-467">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="c306a-468">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="c306a-468">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="c306a-469">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="c306a-469">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="c306a-470">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c306a-470">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="c306a-471">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="c306a-471">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="c306a-472">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="c306a-472">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="c306a-473">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c306a-473">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c306a-474">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="c306a-474">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="c306a-475">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="c306a-475">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c306a-476">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c306a-476">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c306a-477">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="c306a-477">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="c306a-478">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="c306a-478">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="c306a-479">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c306a-479">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c306a-480">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="c306a-480">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="c306a-481">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="c306a-481">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="c306a-482">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c306a-482">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="c306a-483">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="c306a-483">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="c306a-484">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="c306a-484">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="c306a-485">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="c306a-485">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c306a-486">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c306a-486">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c306a-487">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="c306a-487">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c306a-488">**page**</span><span class="sxs-lookup"><span data-stu-id="c306a-488">**page**</span></span>

<span data-ttu-id="c306a-489">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="c306a-489">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="c306a-490">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="c306a-490">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="c306a-491">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="c306a-491">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="c306a-492">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="c306a-492">**viewimports**</span></span>

<span data-ttu-id="c306a-493">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="c306a-493">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="c306a-494">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="c306a-494">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c306a-495">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c306a-495">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="c306a-496">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="c306a-496">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="c306a-497">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="c306a-497">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c306a-498">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="c306a-498">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="c306a-499">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="c306a-499">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="c306a-500">**classlib**</span><span class="sxs-lookup"><span data-stu-id="c306a-500">**classlib**</span></span>

<span data-ttu-id="c306a-501">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="c306a-501">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c306a-502">Значения: `netcoreapp1.0`, `netcoreapp1.1` или с `netstandard1.0` по `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="c306a-502">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="c306a-503">Значение по умолчанию — `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="c306a-503">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="c306a-504">**mvc**</span><span class="sxs-lookup"><span data-stu-id="c306a-504">**mvc**</span></span>

<span data-ttu-id="c306a-505">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="c306a-505">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c306a-506">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="c306a-506">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="c306a-507">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="c306a-507">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="c306a-508">`-au|--auth` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="c306a-508">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="c306a-509">Значения: `None` или `Individual`.</span><span class="sxs-lookup"><span data-stu-id="c306a-509">Values: `None` or `Individual`.</span></span> <span data-ttu-id="c306a-510">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="c306a-510">The default value is `None`.</span></span>

<span data-ttu-id="c306a-511">`-uld|--use-local-db` — указывает, следует ли использовать LocalDB вместо SQLite.</span><span class="sxs-lookup"><span data-stu-id="c306a-511">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="c306a-512">Значения: `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="c306a-512">Values: `true` or `false`.</span></span> <span data-ttu-id="c306a-513">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="c306a-513">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="c306a-514">Примеры</span><span class="sxs-lookup"><span data-stu-id="c306a-514">Examples</span></span>

<span data-ttu-id="c306a-515">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="c306a-515">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="c306a-516">Создание проекта библиотеки классов .NET Standard в указанном каталоге (доступно только при использовании пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="c306a-516">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="c306a-517">Создание проекта приложения ASP.NET Core C# MVC в текущем каталоге без проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="c306a-517">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="c306a-518">Создание нового приложения xUnit:</span><span class="sxs-lookup"><span data-stu-id="c306a-518">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="c306a-519">Перечислите все шаблоны, доступные для MVC:</span><span class="sxs-lookup"><span data-stu-id="c306a-519">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="c306a-520">Установите версию 2.0 шаблонов одностраничного приложения для ASP.NET Core (параметр команды доступен в .NET Core SDK 1.1 и более поздних версиях):</span><span class="sxs-lookup"><span data-stu-id="c306a-520">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="c306a-521">Создайте *global.json* в текущем каталоге, указав версию пакета SDK 2.0.0 (доступно только для пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="c306a-521">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="c306a-522">См. также</span><span class="sxs-lookup"><span data-stu-id="c306a-522">See also</span></span>

* [<span data-ttu-id="c306a-523">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="c306a-523">Custom templates for dotnet new</span></span>](custom-templates.md)  
* [<span data-ttu-id="c306a-524">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="c306a-524">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
* [<span data-ttu-id="c306a-525">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="c306a-525">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
* [<span data-ttu-id="c306a-526">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="c306a-526">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
