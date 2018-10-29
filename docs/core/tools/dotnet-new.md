---
title: Команда dotnet new — интерфейс командной строки .NET Core
description: Команда dotnet new создает проекты .NET Core на основе указанного шаблона.
author: mairaw
ms.author: mairaw
ms.date: 10/24/2018
ms.openlocfilehash: 56d76f1dd54097f9cf20129d74057235290c273c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188210"
---
# <a name="dotnet-new"></a><span data-ttu-id="4b8de-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="4b8de-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="4b8de-104">name</span><span class="sxs-lookup"><span data-stu-id="4b8de-104">Name</span></span>

<span data-ttu-id="4b8de-105">`dotnet new` — создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="4b8de-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4b8de-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4b8de-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="4b8de-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4b8de-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="4b8de-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4b8de-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4b8de-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4b8de-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="4b8de-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="4b8de-110">Description</span></span>

<span data-ttu-id="4b8de-111">Команда `dotnet new` предоставляет удобный способ инициализации проекта .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4b8de-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="4b8de-112">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="4b8de-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="4b8de-113">Аргументы</span><span class="sxs-lookup"><span data-stu-id="4b8de-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="4b8de-114">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="4b8de-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="4b8de-115">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="4b8de-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="4b8de-116">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="4b8de-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="4b8de-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4b8de-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="4b8de-118">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4b8de-118">The command contains a default list of templates.</span></span> <span data-ttu-id="4b8de-119">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="4b8de-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="4b8de-120">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="4b8de-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="4b8de-121">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="4b8de-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="4b8de-122">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="4b8de-122">Template description</span></span>                          | <span data-ttu-id="4b8de-123">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="4b8de-123">Template name</span></span>    | <span data-ttu-id="4b8de-124">Языки</span><span class="sxs-lookup"><span data-stu-id="4b8de-124">Languages</span></span>     |
|----------------------------------------------|------------------|---------------|
| <span data-ttu-id="4b8de-125">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="4b8de-125">Console application</span></span>                          | `console`        | <span data-ttu-id="4b8de-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4b8de-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4b8de-127">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="4b8de-127">Class library</span></span>                                | `classlib`       | <span data-ttu-id="4b8de-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4b8de-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4b8de-129">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="4b8de-129">Unit test project</span></span>                            | `mstest`         | <span data-ttu-id="4b8de-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4b8de-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4b8de-131">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="4b8de-131">xUnit test project</span></span>                           | `xunit`          | <span data-ttu-id="4b8de-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4b8de-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4b8de-133">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="4b8de-133">Razor page</span></span>                                   | `page`           | <span data-ttu-id="4b8de-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="4b8de-134">[C#]</span></span>          |
| <span data-ttu-id="4b8de-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="4b8de-135">MVC ViewImports</span></span>                              | `viewimports`    | <span data-ttu-id="4b8de-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="4b8de-136">[C#]</span></span>          |
| <span data-ttu-id="4b8de-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="4b8de-137">MVC ViewStart</span></span>                                | `viewstart`      | <span data-ttu-id="4b8de-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="4b8de-138">[C#]</span></span>          |
| <span data-ttu-id="4b8de-139">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4b8de-139">ASP.NET Core empty</span></span>                           | `web`            | <span data-ttu-id="4b8de-140">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4b8de-140">[C#], F#</span></span>      |
| <span data-ttu-id="4b8de-141">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="4b8de-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`            | <span data-ttu-id="4b8de-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4b8de-142">[C#], F#</span></span>      |
| <span data-ttu-id="4b8de-143">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4b8de-143">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="4b8de-144">`razor`, `webapp`</span><span class="sxs-lookup"><span data-stu-id="4b8de-144">`razor`, `webapp`</span></span>| <span data-ttu-id="4b8de-145">[C#]</span><span class="sxs-lookup"><span data-stu-id="4b8de-145">[C#]</span></span>          |
| <span data-ttu-id="4b8de-146">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="4b8de-146">ASP.NET Core with Angular</span></span>                    | `angular`        | <span data-ttu-id="4b8de-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="4b8de-147">[C#]</span></span>          |
| <span data-ttu-id="4b8de-148">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="4b8de-148">ASP.NET Core with React.js</span></span>                   | `react`          | <span data-ttu-id="4b8de-149">[C#]</span><span class="sxs-lookup"><span data-stu-id="4b8de-149">[C#]</span></span>          |
| <span data-ttu-id="4b8de-150">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="4b8de-150">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`     | <span data-ttu-id="4b8de-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="4b8de-151">[C#]</span></span>          |
| <span data-ttu-id="4b8de-152">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4b8de-152">ASP.NET Core Web API</span></span>                         | `webapi`         | <span data-ttu-id="4b8de-153">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4b8de-153">[C#], F#</span></span>      |
| <span data-ttu-id="4b8de-154">Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="4b8de-154">Razor class library</span></span>                          | `razorclasslib`  | <span data-ttu-id="4b8de-155">[C#]</span><span class="sxs-lookup"><span data-stu-id="4b8de-155">[C#]</span></span>          |
| <span data-ttu-id="4b8de-156">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="4b8de-156">global.json file</span></span>                             | `globaljson`     |               |
| <span data-ttu-id="4b8de-157">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="4b8de-157">NuGet config</span></span>                                 | `nugetconfig`    |               |
| <span data-ttu-id="4b8de-158">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="4b8de-158">Web config</span></span>                                   | `webconfig`      |               |
| <span data-ttu-id="4b8de-159">Файл решения</span><span class="sxs-lookup"><span data-stu-id="4b8de-159">Solution file</span></span>                                | `sln`            |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="4b8de-160">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4b8de-160">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="4b8de-161">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4b8de-161">The command contains a default list of templates.</span></span> <span data-ttu-id="4b8de-162">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="4b8de-162">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="4b8de-163">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="4b8de-163">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="4b8de-164">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="4b8de-164">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="4b8de-165">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="4b8de-165">Template description</span></span>                          | <span data-ttu-id="4b8de-166">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="4b8de-166">Template name</span></span> | <span data-ttu-id="4b8de-167">Языки</span><span class="sxs-lookup"><span data-stu-id="4b8de-167">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="4b8de-168">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="4b8de-168">Console application</span></span>                          | `console`     | <span data-ttu-id="4b8de-169">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4b8de-169">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4b8de-170">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="4b8de-170">Class library</span></span>                                | `classlib`    | <span data-ttu-id="4b8de-171">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4b8de-171">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4b8de-172">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="4b8de-172">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="4b8de-173">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4b8de-173">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4b8de-174">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="4b8de-174">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="4b8de-175">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4b8de-175">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4b8de-176">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4b8de-176">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="4b8de-177">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4b8de-177">[C#], F#</span></span>      |
| <span data-ttu-id="4b8de-178">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="4b8de-178">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="4b8de-179">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4b8de-179">[C#], F#</span></span>      |
| <span data-ttu-id="4b8de-180">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4b8de-180">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="4b8de-181">[C#]</span><span class="sxs-lookup"><span data-stu-id="4b8de-181">[C#]</span></span>          |
| <span data-ttu-id="4b8de-182">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="4b8de-182">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="4b8de-183">[C#]</span><span class="sxs-lookup"><span data-stu-id="4b8de-183">[C#]</span></span>          |
| <span data-ttu-id="4b8de-184">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="4b8de-184">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="4b8de-185">[C#]</span><span class="sxs-lookup"><span data-stu-id="4b8de-185">[C#]</span></span>          |
| <span data-ttu-id="4b8de-186">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="4b8de-186">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="4b8de-187">[C#]</span><span class="sxs-lookup"><span data-stu-id="4b8de-187">[C#]</span></span>          |
| <span data-ttu-id="4b8de-188">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4b8de-188">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="4b8de-189">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4b8de-189">[C#], F#</span></span>      |
| <span data-ttu-id="4b8de-190">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="4b8de-190">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="4b8de-191">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="4b8de-191">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="4b8de-192">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="4b8de-192">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="4b8de-193">Файл решения</span><span class="sxs-lookup"><span data-stu-id="4b8de-193">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="4b8de-194">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="4b8de-194">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="4b8de-195">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="4b8de-195">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="4b8de-196">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="4b8de-196">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4b8de-197">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4b8de-197">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="4b8de-198">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4b8de-198">The command contains a default list of templates.</span></span> <span data-ttu-id="4b8de-199">Используйте `dotnet new -all`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="4b8de-199">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="4b8de-200">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="4b8de-200">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="4b8de-201">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="4b8de-201">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="4b8de-202">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="4b8de-202">Template description</span></span>  | <span data-ttu-id="4b8de-203">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="4b8de-203">Template name</span></span> | <span data-ttu-id="4b8de-204">Языки</span><span class="sxs-lookup"><span data-stu-id="4b8de-204">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="4b8de-205">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="4b8de-205">Console application</span></span>  | `console`     | <span data-ttu-id="4b8de-206">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4b8de-206">[C#], F#</span></span>  |
| <span data-ttu-id="4b8de-207">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="4b8de-207">Class library</span></span>        | `classlib`    | <span data-ttu-id="4b8de-208">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4b8de-208">[C#], F#</span></span>  |
| <span data-ttu-id="4b8de-209">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="4b8de-209">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="4b8de-210">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4b8de-210">[C#], F#</span></span>  |
| <span data-ttu-id="4b8de-211">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="4b8de-211">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="4b8de-212">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4b8de-212">[C#], F#</span></span>  |
| <span data-ttu-id="4b8de-213">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4b8de-213">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="4b8de-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="4b8de-214">[C#]</span></span>      |
| <span data-ttu-id="4b8de-215">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4b8de-215">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="4b8de-216">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4b8de-216">[C#], F#</span></span>  |
| <span data-ttu-id="4b8de-217">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4b8de-217">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="4b8de-218">[C#]</span><span class="sxs-lookup"><span data-stu-id="4b8de-218">[C#]</span></span>      |
| <span data-ttu-id="4b8de-219">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="4b8de-219">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="4b8de-220">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="4b8de-220">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="4b8de-221">Файл решения</span><span class="sxs-lookup"><span data-stu-id="4b8de-221">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="4b8de-222">Параметры</span><span class="sxs-lookup"><span data-stu-id="4b8de-222">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="4b8de-223">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4b8de-223">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="4b8de-224">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="4b8de-224">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="4b8de-225">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="4b8de-225">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="4b8de-226">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="4b8de-226">Prints out help for the command.</span></span> <span data-ttu-id="4b8de-227">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-227">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="4b8de-228">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-228">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="4b8de-229">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-229">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="4b8de-230">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="4b8de-230">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="4b8de-231">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="4b8de-231">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="4b8de-232">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="4b8de-232">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="4b8de-233">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="4b8de-233">Lists templates containing the specified name.</span></span> <span data-ttu-id="4b8de-234">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="4b8de-234">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="4b8de-235">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="4b8de-235">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="4b8de-236">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="4b8de-236">The language of the template to create.</span></span> <span data-ttu-id="4b8de-237">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="4b8de-237">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="4b8de-238">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="4b8de-238">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="4b8de-239">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="4b8de-239">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="4b8de-240">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-240">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="4b8de-241">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="4b8de-241">The name for the created output.</span></span> <span data-ttu-id="4b8de-242">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="4b8de-242">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="4b8de-243">Задает источник пакетов NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="4b8de-243">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="4b8de-244">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="4b8de-244">Location to place the generated output.</span></span> <span data-ttu-id="4b8de-245">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="4b8de-245">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="4b8de-246">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="4b8de-246">Filters templates based on available types.</span></span> <span data-ttu-id="4b8de-247">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="4b8de-247">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="4b8de-248">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-248">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="4b8de-249">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="4b8de-249">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="4b8de-250">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="4b8de-250">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="4b8de-251">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="4b8de-251">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="4b8de-252">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4b8de-252">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="4b8de-253">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="4b8de-253">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="4b8de-254">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="4b8de-254">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="4b8de-255">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="4b8de-255">Prints out help for the command.</span></span> <span data-ttu-id="4b8de-256">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-256">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="4b8de-257">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-257">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="4b8de-258">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-258">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="4b8de-259">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="4b8de-259">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="4b8de-260">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="4b8de-260">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="4b8de-261">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="4b8de-261">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="4b8de-262">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="4b8de-262">Lists templates containing the specified name.</span></span> <span data-ttu-id="4b8de-263">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="4b8de-263">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="4b8de-264">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="4b8de-264">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="4b8de-265">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="4b8de-265">The language of the template to create.</span></span> <span data-ttu-id="4b8de-266">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="4b8de-266">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="4b8de-267">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="4b8de-267">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="4b8de-268">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="4b8de-268">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="4b8de-269">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-269">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="4b8de-270">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="4b8de-270">The name for the created output.</span></span> <span data-ttu-id="4b8de-271">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="4b8de-271">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="4b8de-272">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="4b8de-272">Location to place the generated output.</span></span> <span data-ttu-id="4b8de-273">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="4b8de-273">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="4b8de-274">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="4b8de-274">Filters templates based on available types.</span></span> <span data-ttu-id="4b8de-275">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="4b8de-275">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="4b8de-276">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-276">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="4b8de-277">Чтобы удалить шаблон, используя путь к исходному пакету `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="4b8de-277">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="4b8de-278">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="4b8de-278">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="4b8de-279">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="4b8de-279">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="4b8de-280">Если вам не удается определить аргумент `PATH` или `NUGET_ID`, необходимый для удаления шаблона, выполните команду `dotnet new --uninstall` без аргумента. В результате будут перечислены все установленные шаблоны и аргумент, необходимый для их удаления.</span><span class="sxs-lookup"><span data-stu-id="4b8de-280">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4b8de-281">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4b8de-281">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="4b8de-282">Показывает все шаблоны определенного типа проекта при запуске в контексте одной только команды `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-282">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="4b8de-283">При запуске в контексте конкретного шаблона, например `dotnet new web -all`, `-all` интерпретируется как флаг принудительного создания.</span><span class="sxs-lookup"><span data-stu-id="4b8de-283">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="4b8de-284">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="4b8de-284">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="4b8de-285">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="4b8de-285">Prints out help for the command.</span></span> <span data-ttu-id="4b8de-286">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-286">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="4b8de-287">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="4b8de-287">Lists templates containing the specified name.</span></span> <span data-ttu-id="4b8de-288">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="4b8de-288">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="4b8de-289">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="4b8de-289">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="4b8de-290">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="4b8de-290">The language of the template to create.</span></span> <span data-ttu-id="4b8de-291">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="4b8de-291">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="4b8de-292">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="4b8de-292">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="4b8de-293">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="4b8de-293">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="4b8de-294">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-294">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="4b8de-295">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="4b8de-295">The name for the created output.</span></span> <span data-ttu-id="4b8de-296">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="4b8de-296">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="4b8de-297">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="4b8de-297">Location to place the generated output.</span></span> <span data-ttu-id="4b8de-298">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="4b8de-298">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="4b8de-299">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="4b8de-299">Template options</span></span>

<span data-ttu-id="4b8de-300">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="4b8de-300">Each project template may have additional options available.</span></span> <span data-ttu-id="4b8de-301">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="4b8de-301">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="4b8de-302">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4b8de-302">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="4b8de-303">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="4b8de-303">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="4b8de-304">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="4b8de-304">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4b8de-305">**classlib**</span><span class="sxs-lookup"><span data-stu-id="4b8de-305">**classlib**</span></span>

<span data-ttu-id="4b8de-306">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="4b8de-306">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4b8de-307">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="4b8de-307">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="4b8de-308">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-308">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="4b8de-309">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="4b8de-309">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4b8de-310">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="4b8de-310">**mstest, xunit**</span></span>

<span data-ttu-id="4b8de-311">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="4b8de-311">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="4b8de-312">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="4b8de-312">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4b8de-313">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="4b8de-313">**globaljson**</span></span>

<span data-ttu-id="4b8de-314">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="4b8de-314">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="4b8de-315">**web**</span><span class="sxs-lookup"><span data-stu-id="4b8de-315">**web**</span></span>

<span data-ttu-id="4b8de-316">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="4b8de-316">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="4b8de-317">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="4b8de-317">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4b8de-318">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4b8de-318">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="4b8de-319">Этот параметр применяется, только если `IndividualAuth` или `OrganizationalAuth` не используются.</span><span class="sxs-lookup"><span data-stu-id="4b8de-319">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="4b8de-320">**webapi**</span><span class="sxs-lookup"><span data-stu-id="4b8de-320">**webapi**</span></span>

<span data-ttu-id="4b8de-321">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="4b8de-321">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="4b8de-322">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="4b8de-322">The possible values are:</span></span>

- <span data-ttu-id="4b8de-323">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="4b8de-323">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="4b8de-324">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="4b8de-324">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="4b8de-325">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="4b8de-325">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="4b8de-326">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="4b8de-326">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="4b8de-327">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="4b8de-327">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="4b8de-328">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-328">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="4b8de-329">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-329">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="4b8de-330">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="4b8de-330">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="4b8de-331">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-331">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4b8de-332">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="4b8de-332">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="4b8de-333">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-333">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4b8de-334">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-334">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="4b8de-335">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="4b8de-335">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="4b8de-336">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-336">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="4b8de-337">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-337">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="4b8de-338">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="4b8de-338">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="4b8de-339">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-339">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4b8de-340">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-340">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="4b8de-341">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="4b8de-341">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="4b8de-342">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-342">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4b8de-343">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-343">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="4b8de-344">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="4b8de-344">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="4b8de-345">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-345">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="4b8de-346">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="4b8de-346">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="4b8de-347">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="4b8de-347">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="4b8de-348">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-348">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4b8de-349">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="4b8de-349">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4b8de-350">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4b8de-350">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="4b8de-351">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-351">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="4b8de-352">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="4b8de-352">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="4b8de-353">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="4b8de-353">**mvc, razor**</span></span>

<span data-ttu-id="4b8de-354">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="4b8de-354">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="4b8de-355">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="4b8de-355">The possible values are:</span></span>

- <span data-ttu-id="4b8de-356">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="4b8de-356">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="4b8de-357">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="4b8de-357">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="4b8de-358">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="4b8de-358">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="4b8de-359">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="4b8de-359">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="4b8de-360">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="4b8de-360">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="4b8de-361">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="4b8de-361">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="4b8de-362">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="4b8de-362">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="4b8de-363">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-363">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="4b8de-364">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-364">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="4b8de-365">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="4b8de-365">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="4b8de-366">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-366">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4b8de-367">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="4b8de-367">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="4b8de-368">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-368">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4b8de-369">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="4b8de-369">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="4b8de-370">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-370">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4b8de-371">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="4b8de-371">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="4b8de-372">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-372">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="4b8de-373">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-373">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="4b8de-374">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="4b8de-374">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="4b8de-375">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-375">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="4b8de-376">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-376">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="4b8de-377">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="4b8de-377">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="4b8de-378">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-378">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4b8de-379">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-379">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="4b8de-380">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="4b8de-380">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="4b8de-381">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-381">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4b8de-382">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-382">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="4b8de-383">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="4b8de-383">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="4b8de-384">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-384">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4b8de-385">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-385">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="4b8de-386">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="4b8de-386">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="4b8de-387">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-387">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="4b8de-388">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="4b8de-388">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="4b8de-389">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="4b8de-389">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="4b8de-390">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="4b8de-390">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="4b8de-391">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-391">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4b8de-392">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="4b8de-392">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4b8de-393">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4b8de-393">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="4b8de-394">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-394">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="4b8de-395">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="4b8de-395">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="4b8de-396">**page**</span><span class="sxs-lookup"><span data-stu-id="4b8de-396">**page**</span></span>

<span data-ttu-id="4b8de-397">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="4b8de-397">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="4b8de-398">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-398">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="4b8de-399">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="4b8de-399">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="4b8de-400">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="4b8de-400">**viewimports**</span></span>

<span data-ttu-id="4b8de-401">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="4b8de-401">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="4b8de-402">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-402">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="4b8de-403">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4b8de-403">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="4b8de-404">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="4b8de-404">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="4b8de-405">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="4b8de-405">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4b8de-406">**classlib**</span><span class="sxs-lookup"><span data-stu-id="4b8de-406">**classlib**</span></span>

<span data-ttu-id="4b8de-407">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="4b8de-407">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4b8de-408">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="4b8de-408">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="4b8de-409">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-409">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="4b8de-410">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="4b8de-410">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4b8de-411">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="4b8de-411">**mstest, xunit**</span></span>

<span data-ttu-id="4b8de-412">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="4b8de-412">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="4b8de-413">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="4b8de-413">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4b8de-414">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="4b8de-414">**globaljson**</span></span>

<span data-ttu-id="4b8de-415">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="4b8de-415">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="4b8de-416">**web**</span><span class="sxs-lookup"><span data-stu-id="4b8de-416">**web**</span></span>

<span data-ttu-id="4b8de-417">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="4b8de-417">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="4b8de-418">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="4b8de-418">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4b8de-419">**webapi**</span><span class="sxs-lookup"><span data-stu-id="4b8de-419">**webapi**</span></span>

<span data-ttu-id="4b8de-420">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="4b8de-420">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="4b8de-421">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="4b8de-421">The possible values are:</span></span>

- <span data-ttu-id="4b8de-422">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="4b8de-422">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="4b8de-423">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="4b8de-423">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="4b8de-424">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="4b8de-424">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="4b8de-425">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="4b8de-425">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="4b8de-426">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="4b8de-426">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="4b8de-427">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-427">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="4b8de-428">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-428">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="4b8de-429">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="4b8de-429">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="4b8de-430">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-430">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4b8de-431">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="4b8de-431">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="4b8de-432">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-432">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4b8de-433">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-433">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="4b8de-434">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="4b8de-434">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="4b8de-435">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-435">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="4b8de-436">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-436">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="4b8de-437">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="4b8de-437">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="4b8de-438">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-438">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4b8de-439">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-439">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="4b8de-440">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="4b8de-440">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="4b8de-441">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-441">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4b8de-442">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-442">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="4b8de-443">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="4b8de-443">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="4b8de-444">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-444">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="4b8de-445">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="4b8de-445">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="4b8de-446">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="4b8de-446">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="4b8de-447">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-447">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4b8de-448">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="4b8de-448">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4b8de-449">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="4b8de-449">**mvc, razor**</span></span>

<span data-ttu-id="4b8de-450">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="4b8de-450">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="4b8de-451">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="4b8de-451">The possible values are:</span></span>

- <span data-ttu-id="4b8de-452">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="4b8de-452">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="4b8de-453">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="4b8de-453">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="4b8de-454">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="4b8de-454">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="4b8de-455">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="4b8de-455">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="4b8de-456">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="4b8de-456">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="4b8de-457">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="4b8de-457">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="4b8de-458">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="4b8de-458">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="4b8de-459">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-459">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="4b8de-460">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-460">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="4b8de-461">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="4b8de-461">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="4b8de-462">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-462">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4b8de-463">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="4b8de-463">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="4b8de-464">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-464">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4b8de-465">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="4b8de-465">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="4b8de-466">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-466">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4b8de-467">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="4b8de-467">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="4b8de-468">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-468">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="4b8de-469">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-469">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="4b8de-470">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="4b8de-470">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="4b8de-471">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-471">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="4b8de-472">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-472">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="4b8de-473">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="4b8de-473">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="4b8de-474">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-474">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4b8de-475">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-475">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="4b8de-476">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="4b8de-476">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="4b8de-477">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-477">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4b8de-478">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-478">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="4b8de-479">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="4b8de-479">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="4b8de-480">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-480">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4b8de-481">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-481">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="4b8de-482">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="4b8de-482">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="4b8de-483">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-483">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="4b8de-484">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="4b8de-484">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="4b8de-485">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="4b8de-485">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="4b8de-486">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="4b8de-486">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="4b8de-487">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-487">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4b8de-488">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="4b8de-488">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4b8de-489">**page**</span><span class="sxs-lookup"><span data-stu-id="4b8de-489">**page**</span></span>

<span data-ttu-id="4b8de-490">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="4b8de-490">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="4b8de-491">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-491">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="4b8de-492">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="4b8de-492">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="4b8de-493">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="4b8de-493">**viewimports**</span></span>

<span data-ttu-id="4b8de-494">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="4b8de-494">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="4b8de-495">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-495">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4b8de-496">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4b8de-496">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="4b8de-497">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="4b8de-497">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="4b8de-498">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="4b8de-498">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4b8de-499">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-499">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="4b8de-500">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-500">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="4b8de-501">**classlib**</span><span class="sxs-lookup"><span data-stu-id="4b8de-501">**classlib**</span></span>

<span data-ttu-id="4b8de-502">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="4b8de-502">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4b8de-503">Значения: `netcoreapp1.0`, `netcoreapp1.1` или с `netstandard1.0` по `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-503">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="4b8de-504">Значение по умолчанию — `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-504">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="4b8de-505">**mvc**</span><span class="sxs-lookup"><span data-stu-id="4b8de-505">**mvc**</span></span>

<span data-ttu-id="4b8de-506">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="4b8de-506">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4b8de-507">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-507">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="4b8de-508">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-508">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="4b8de-509">`-au|--auth` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="4b8de-509">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="4b8de-510">Значения: `None` или `Individual`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-510">Values: `None` or `Individual`.</span></span> <span data-ttu-id="4b8de-511">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-511">The default value is `None`.</span></span>

<span data-ttu-id="4b8de-512">`-uld|--use-local-db` — указывает, следует ли использовать LocalDB вместо SQLite.</span><span class="sxs-lookup"><span data-stu-id="4b8de-512">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="4b8de-513">Значения: `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-513">Values: `true` or `false`.</span></span> <span data-ttu-id="4b8de-514">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="4b8de-514">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="4b8de-515">Примеры</span><span class="sxs-lookup"><span data-stu-id="4b8de-515">Examples</span></span>

<span data-ttu-id="4b8de-516">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="4b8de-516">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="4b8de-517">Создание проекта библиотеки классов .NET Standard в указанном каталоге (доступно только при использовании пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="4b8de-517">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="4b8de-518">Создание проекта приложения ASP.NET Core C# MVC в текущем каталоге без проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="4b8de-518">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="4b8de-519">Создание нового приложения xUnit:</span><span class="sxs-lookup"><span data-stu-id="4b8de-519">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="4b8de-520">Перечислите все шаблоны, доступные для MVC:</span><span class="sxs-lookup"><span data-stu-id="4b8de-520">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="4b8de-521">Установите версию 2.0 шаблонов одностраничного приложения для ASP.NET Core (параметр команды доступен в .NET Core SDK 1.1 и более поздних версиях):</span><span class="sxs-lookup"><span data-stu-id="4b8de-521">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="4b8de-522">Создайте *global.json* в текущем каталоге, указав версию пакета SDK 2.0.0 (доступно только для пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="4b8de-522">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="4b8de-523">См. также</span><span class="sxs-lookup"><span data-stu-id="4b8de-523">See also</span></span>

* [<span data-ttu-id="4b8de-524">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="4b8de-524">Custom templates for dotnet new</span></span>](custom-templates.md)  
* [<span data-ttu-id="4b8de-525">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="4b8de-525">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
* [<span data-ttu-id="4b8de-526">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="4b8de-526">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
* [<span data-ttu-id="4b8de-527">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="4b8de-527">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
