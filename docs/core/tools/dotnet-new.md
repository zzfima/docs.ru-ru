---
title: Команда dotnet new — интерфейс командной строки .NET Core
description: Команда dotnet new создает проекты .NET Core на основе указанного шаблона.
author: mairaw
ms.author: mairaw
ms.date: 10/24/2018
ms.openlocfilehash: a8d486f569f31d68d5659ac6a80d615474ef2506
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131486"
---
# <a name="dotnet-new"></a><span data-ttu-id="97816-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="97816-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="97816-104">name</span><span class="sxs-lookup"><span data-stu-id="97816-104">Name</span></span>

<span data-ttu-id="97816-105">`dotnet new` — создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="97816-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="97816-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="97816-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="97816-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="97816-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="97816-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="97816-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="97816-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="97816-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="97816-110">Описание</span><span class="sxs-lookup"><span data-stu-id="97816-110">Description</span></span>

<span data-ttu-id="97816-111">Команда `dotnet new` предоставляет удобный способ инициализации проекта .NET Core.</span><span class="sxs-lookup"><span data-stu-id="97816-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="97816-112">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="97816-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="97816-113">Аргументы</span><span class="sxs-lookup"><span data-stu-id="97816-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="97816-114">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="97816-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="97816-115">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="97816-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="97816-116">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="97816-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="97816-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="97816-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="97816-118">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="97816-118">The command contains a default list of templates.</span></span> <span data-ttu-id="97816-119">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="97816-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="97816-120">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="97816-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="97816-121">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="97816-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="97816-122">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="97816-122">Template description</span></span>                          | <span data-ttu-id="97816-123">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="97816-123">Template name</span></span>    | <span data-ttu-id="97816-124">Языки</span><span class="sxs-lookup"><span data-stu-id="97816-124">Languages</span></span>     |
|----------------------------------------------|------------------|---------------|
| <span data-ttu-id="97816-125">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="97816-125">Console application</span></span>                          | `console`        | <span data-ttu-id="97816-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="97816-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="97816-127">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="97816-127">Class library</span></span>                                | `classlib`       | <span data-ttu-id="97816-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="97816-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="97816-129">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="97816-129">Unit test project</span></span>                            | `mstest`         | <span data-ttu-id="97816-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="97816-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="97816-131">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="97816-131">xUnit test project</span></span>                           | `xunit`          | <span data-ttu-id="97816-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="97816-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="97816-133">Проект теста NUnit</span><span class="sxs-lookup"><span data-stu-id="97816-133">NUnit test project</span></span>                           | `nunit`          | <span data-ttu-id="97816-134">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="97816-134">[C#], F#, VB</span></span>  |
| <span data-ttu-id="97816-135">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="97816-135">Razor page</span></span>                                   | `page`           | <span data-ttu-id="97816-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="97816-136">[C#]</span></span>          |
| <span data-ttu-id="97816-137">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="97816-137">MVC ViewImports</span></span>                              | `viewimports`    | <span data-ttu-id="97816-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="97816-138">[C#]</span></span>          |
| <span data-ttu-id="97816-139">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="97816-139">MVC ViewStart</span></span>                                | `viewstart`      | <span data-ttu-id="97816-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="97816-140">[C#]</span></span>          |
| <span data-ttu-id="97816-141">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="97816-141">ASP.NET Core empty</span></span>                           | `web`            | <span data-ttu-id="97816-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="97816-142">[C#], F#</span></span>      |
| <span data-ttu-id="97816-143">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="97816-143">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`            | <span data-ttu-id="97816-144">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="97816-144">[C#], F#</span></span>      |
| <span data-ttu-id="97816-145">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="97816-145">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="97816-146">`razor`, `webapp`</span><span class="sxs-lookup"><span data-stu-id="97816-146">`razor`, `webapp`</span></span>| <span data-ttu-id="97816-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="97816-147">[C#]</span></span>          |
| <span data-ttu-id="97816-148">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="97816-148">ASP.NET Core with Angular</span></span>                    | `angular`        | <span data-ttu-id="97816-149">[C#]</span><span class="sxs-lookup"><span data-stu-id="97816-149">[C#]</span></span>          |
| <span data-ttu-id="97816-150">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="97816-150">ASP.NET Core with React.js</span></span>                   | `react`          | <span data-ttu-id="97816-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="97816-151">[C#]</span></span>          |
| <span data-ttu-id="97816-152">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="97816-152">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`     | <span data-ttu-id="97816-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="97816-153">[C#]</span></span>          |
| <span data-ttu-id="97816-154">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="97816-154">ASP.NET Core Web API</span></span>                         | `webapi`         | <span data-ttu-id="97816-155">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="97816-155">[C#], F#</span></span>      |
| <span data-ttu-id="97816-156">Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="97816-156">Razor class library</span></span>                          | `razorclasslib`  | <span data-ttu-id="97816-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="97816-157">[C#]</span></span>          |
| <span data-ttu-id="97816-158">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="97816-158">global.json file</span></span>                             | `globaljson`     |               |
| <span data-ttu-id="97816-159">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="97816-159">NuGet config</span></span>                                 | `nugetconfig`    |               |
| <span data-ttu-id="97816-160">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="97816-160">Web config</span></span>                                   | `webconfig`      |               |
| <span data-ttu-id="97816-161">Файл решения</span><span class="sxs-lookup"><span data-stu-id="97816-161">Solution file</span></span>                                | `sln`            |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="97816-162">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="97816-162">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="97816-163">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="97816-163">The command contains a default list of templates.</span></span> <span data-ttu-id="97816-164">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="97816-164">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="97816-165">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="97816-165">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="97816-166">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="97816-166">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="97816-167">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="97816-167">Template description</span></span>                          | <span data-ttu-id="97816-168">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="97816-168">Template name</span></span> | <span data-ttu-id="97816-169">Языки</span><span class="sxs-lookup"><span data-stu-id="97816-169">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="97816-170">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="97816-170">Console application</span></span>                          | `console`     | <span data-ttu-id="97816-171">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="97816-171">[C#], F#, VB</span></span>  |
| <span data-ttu-id="97816-172">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="97816-172">Class library</span></span>                                | `classlib`    | <span data-ttu-id="97816-173">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="97816-173">[C#], F#, VB</span></span>  |
| <span data-ttu-id="97816-174">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="97816-174">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="97816-175">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="97816-175">[C#], F#, VB</span></span>  |
| <span data-ttu-id="97816-176">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="97816-176">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="97816-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="97816-177">[C#], F#, VB</span></span>  |
| <span data-ttu-id="97816-178">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="97816-178">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="97816-179">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="97816-179">[C#], F#</span></span>      |
| <span data-ttu-id="97816-180">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="97816-180">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="97816-181">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="97816-181">[C#], F#</span></span>      |
| <span data-ttu-id="97816-182">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="97816-182">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="97816-183">[C#]</span><span class="sxs-lookup"><span data-stu-id="97816-183">[C#]</span></span>          |
| <span data-ttu-id="97816-184">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="97816-184">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="97816-185">[C#]</span><span class="sxs-lookup"><span data-stu-id="97816-185">[C#]</span></span>          |
| <span data-ttu-id="97816-186">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="97816-186">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="97816-187">[C#]</span><span class="sxs-lookup"><span data-stu-id="97816-187">[C#]</span></span>          |
| <span data-ttu-id="97816-188">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="97816-188">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="97816-189">[C#]</span><span class="sxs-lookup"><span data-stu-id="97816-189">[C#]</span></span>          |
| <span data-ttu-id="97816-190">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="97816-190">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="97816-191">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="97816-191">[C#], F#</span></span>      |
| <span data-ttu-id="97816-192">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="97816-192">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="97816-193">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="97816-193">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="97816-194">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="97816-194">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="97816-195">Файл решения</span><span class="sxs-lookup"><span data-stu-id="97816-195">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="97816-196">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="97816-196">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="97816-197">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="97816-197">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="97816-198">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="97816-198">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="97816-199">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="97816-199">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="97816-200">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="97816-200">The command contains a default list of templates.</span></span> <span data-ttu-id="97816-201">Используйте `dotnet new -all`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="97816-201">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="97816-202">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="97816-202">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="97816-203">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="97816-203">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="97816-204">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="97816-204">Template description</span></span>  | <span data-ttu-id="97816-205">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="97816-205">Template name</span></span> | <span data-ttu-id="97816-206">Языки</span><span class="sxs-lookup"><span data-stu-id="97816-206">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="97816-207">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="97816-207">Console application</span></span>  | `console`     | <span data-ttu-id="97816-208">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="97816-208">[C#], F#</span></span>  |
| <span data-ttu-id="97816-209">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="97816-209">Class library</span></span>        | `classlib`    | <span data-ttu-id="97816-210">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="97816-210">[C#], F#</span></span>  |
| <span data-ttu-id="97816-211">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="97816-211">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="97816-212">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="97816-212">[C#], F#</span></span>  |
| <span data-ttu-id="97816-213">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="97816-213">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="97816-214">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="97816-214">[C#], F#</span></span>  |
| <span data-ttu-id="97816-215">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="97816-215">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="97816-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="97816-216">[C#]</span></span>      |
| <span data-ttu-id="97816-217">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="97816-217">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="97816-218">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="97816-218">[C#], F#</span></span>  |
| <span data-ttu-id="97816-219">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="97816-219">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="97816-220">[C#]</span><span class="sxs-lookup"><span data-stu-id="97816-220">[C#]</span></span>      |
| <span data-ttu-id="97816-221">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="97816-221">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="97816-222">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="97816-222">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="97816-223">Файл решения</span><span class="sxs-lookup"><span data-stu-id="97816-223">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="97816-224">Параметры</span><span class="sxs-lookup"><span data-stu-id="97816-224">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="97816-225">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="97816-225">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="97816-226">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="97816-226">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="97816-227">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="97816-227">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="97816-228">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="97816-228">Prints out help for the command.</span></span> <span data-ttu-id="97816-229">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="97816-229">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="97816-230">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="97816-230">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="97816-231">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="97816-231">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="97816-232">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="97816-232">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="97816-233">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="97816-233">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="97816-234">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="97816-234">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="97816-235">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="97816-235">Lists templates containing the specified name.</span></span> <span data-ttu-id="97816-236">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="97816-236">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="97816-237">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="97816-237">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="97816-238">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="97816-238">The language of the template to create.</span></span> <span data-ttu-id="97816-239">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="97816-239">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="97816-240">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="97816-240">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="97816-241">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="97816-241">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="97816-242">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="97816-242">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="97816-243">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="97816-243">The name for the created output.</span></span> <span data-ttu-id="97816-244">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="97816-244">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="97816-245">Задает источник пакетов NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="97816-245">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="97816-246">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="97816-246">Location to place the generated output.</span></span> <span data-ttu-id="97816-247">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="97816-247">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="97816-248">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="97816-248">Filters templates based on available types.</span></span> <span data-ttu-id="97816-249">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="97816-249">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="97816-250">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="97816-250">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="97816-251">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="97816-251">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="97816-252">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="97816-252">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="97816-253">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="97816-253">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="97816-254">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="97816-254">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="97816-255">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="97816-255">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="97816-256">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="97816-256">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="97816-257">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="97816-257">Prints out help for the command.</span></span> <span data-ttu-id="97816-258">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="97816-258">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="97816-259">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="97816-259">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="97816-260">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="97816-260">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="97816-261">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="97816-261">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="97816-262">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="97816-262">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="97816-263">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="97816-263">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="97816-264">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="97816-264">Lists templates containing the specified name.</span></span> <span data-ttu-id="97816-265">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="97816-265">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="97816-266">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="97816-266">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="97816-267">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="97816-267">The language of the template to create.</span></span> <span data-ttu-id="97816-268">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="97816-268">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="97816-269">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="97816-269">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="97816-270">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="97816-270">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="97816-271">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="97816-271">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="97816-272">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="97816-272">The name for the created output.</span></span> <span data-ttu-id="97816-273">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="97816-273">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="97816-274">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="97816-274">Location to place the generated output.</span></span> <span data-ttu-id="97816-275">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="97816-275">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="97816-276">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="97816-276">Filters templates based on available types.</span></span> <span data-ttu-id="97816-277">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="97816-277">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="97816-278">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="97816-278">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="97816-279">Чтобы удалить шаблон, используя путь к исходному пакету `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="97816-279">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="97816-280">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="97816-280">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="97816-281">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="97816-281">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="97816-282">Если вам не удается определить аргумент `PATH` или `NUGET_ID`, необходимый для удаления шаблона, выполните команду `dotnet new --uninstall` без аргумента. В результате будут перечислены все установленные шаблоны и аргумент, необходимый для их удаления.</span><span class="sxs-lookup"><span data-stu-id="97816-282">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="97816-283">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="97816-283">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="97816-284">Показывает все шаблоны определенного типа проекта при запуске в контексте одной только команды `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="97816-284">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="97816-285">При запуске в контексте конкретного шаблона, например `dotnet new web -all`, `-all` интерпретируется как флаг принудительного создания.</span><span class="sxs-lookup"><span data-stu-id="97816-285">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="97816-286">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="97816-286">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="97816-287">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="97816-287">Prints out help for the command.</span></span> <span data-ttu-id="97816-288">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="97816-288">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="97816-289">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="97816-289">Lists templates containing the specified name.</span></span> <span data-ttu-id="97816-290">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="97816-290">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="97816-291">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="97816-291">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="97816-292">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="97816-292">The language of the template to create.</span></span> <span data-ttu-id="97816-293">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="97816-293">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="97816-294">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="97816-294">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="97816-295">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="97816-295">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="97816-296">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="97816-296">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="97816-297">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="97816-297">The name for the created output.</span></span> <span data-ttu-id="97816-298">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="97816-298">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="97816-299">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="97816-299">Location to place the generated output.</span></span> <span data-ttu-id="97816-300">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="97816-300">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="97816-301">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="97816-301">Template options</span></span>

<span data-ttu-id="97816-302">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="97816-302">Each project template may have additional options available.</span></span> <span data-ttu-id="97816-303">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="97816-303">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="97816-304">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="97816-304">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="97816-305">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="97816-305">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="97816-306">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="97816-306">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="97816-307">**classlib**</span><span class="sxs-lookup"><span data-stu-id="97816-307">**classlib**</span></span>

<span data-ttu-id="97816-308">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="97816-308">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="97816-309">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="97816-309">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="97816-310">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="97816-310">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="97816-311">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="97816-311">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="97816-312">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="97816-312">**mstest, xunit**</span></span>

<span data-ttu-id="97816-313">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="97816-313">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="97816-314">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="97816-314">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="97816-315">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="97816-315">**globaljson**</span></span>

<span data-ttu-id="97816-316">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="97816-316">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="97816-317">**web**</span><span class="sxs-lookup"><span data-stu-id="97816-317">**web**</span></span>

<span data-ttu-id="97816-318">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="97816-318">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="97816-319">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="97816-319">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="97816-320">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="97816-320">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="97816-321">Этот параметр применяется, только если `IndividualAuth` или `OrganizationalAuth` не используются.</span><span class="sxs-lookup"><span data-stu-id="97816-321">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="97816-322">**webapi**</span><span class="sxs-lookup"><span data-stu-id="97816-322">**webapi**</span></span>

<span data-ttu-id="97816-323">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="97816-323">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="97816-324">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="97816-324">The possible values are:</span></span>

- <span data-ttu-id="97816-325">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="97816-325">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="97816-326">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="97816-326">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="97816-327">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="97816-327">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="97816-328">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="97816-328">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="97816-329">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="97816-329">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="97816-330">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="97816-330">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="97816-331">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="97816-331">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="97816-332">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="97816-332">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="97816-333">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="97816-333">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="97816-334">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="97816-334">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="97816-335">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="97816-335">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="97816-336">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="97816-336">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="97816-337">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="97816-337">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="97816-338">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="97816-338">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="97816-339">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="97816-339">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="97816-340">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="97816-340">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="97816-341">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="97816-341">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="97816-342">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="97816-342">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="97816-343">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="97816-343">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="97816-344">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="97816-344">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="97816-345">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="97816-345">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="97816-346">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="97816-346">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="97816-347">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="97816-347">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="97816-348">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="97816-348">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="97816-349">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="97816-349">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="97816-350">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="97816-350">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="97816-351">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="97816-351">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="97816-352">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="97816-352">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="97816-353">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="97816-353">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="97816-354">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="97816-354">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="97816-355">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="97816-355">**mvc, razor**</span></span>

<span data-ttu-id="97816-356">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="97816-356">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="97816-357">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="97816-357">The possible values are:</span></span>

- <span data-ttu-id="97816-358">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="97816-358">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="97816-359">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="97816-359">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="97816-360">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="97816-360">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="97816-361">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="97816-361">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="97816-362">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="97816-362">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="97816-363">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="97816-363">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="97816-364">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="97816-364">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="97816-365">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="97816-365">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="97816-366">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="97816-366">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="97816-367">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="97816-367">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="97816-368">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="97816-368">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="97816-369">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="97816-369">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="97816-370">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="97816-370">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="97816-371">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="97816-371">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="97816-372">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="97816-372">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="97816-373">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="97816-373">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="97816-374">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="97816-374">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="97816-375">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="97816-375">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="97816-376">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="97816-376">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="97816-377">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="97816-377">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="97816-378">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="97816-378">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="97816-379">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="97816-379">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="97816-380">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="97816-380">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="97816-381">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="97816-381">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="97816-382">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="97816-382">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="97816-383">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="97816-383">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="97816-384">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="97816-384">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="97816-385">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="97816-385">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="97816-386">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="97816-386">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="97816-387">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="97816-387">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="97816-388">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="97816-388">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="97816-389">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="97816-389">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="97816-390">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="97816-390">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="97816-391">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="97816-391">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="97816-392">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="97816-392">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="97816-393">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="97816-393">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="97816-394">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="97816-394">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="97816-395">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="97816-395">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="97816-396">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="97816-396">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="97816-397">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="97816-397">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="97816-398">**page**</span><span class="sxs-lookup"><span data-stu-id="97816-398">**page**</span></span>

<span data-ttu-id="97816-399">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="97816-399">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="97816-400">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="97816-400">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="97816-401">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="97816-401">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="97816-402">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="97816-402">**viewimports**</span></span>

<span data-ttu-id="97816-403">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="97816-403">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="97816-404">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="97816-404">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="97816-405">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="97816-405">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="97816-406">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="97816-406">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="97816-407">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="97816-407">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="97816-408">**classlib**</span><span class="sxs-lookup"><span data-stu-id="97816-408">**classlib**</span></span>

<span data-ttu-id="97816-409">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="97816-409">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="97816-410">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="97816-410">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="97816-411">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="97816-411">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="97816-412">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="97816-412">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="97816-413">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="97816-413">**mstest, xunit**</span></span>

<span data-ttu-id="97816-414">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="97816-414">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="97816-415">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="97816-415">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="97816-416">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="97816-416">**globaljson**</span></span>

<span data-ttu-id="97816-417">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="97816-417">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="97816-418">**web**</span><span class="sxs-lookup"><span data-stu-id="97816-418">**web**</span></span>

<span data-ttu-id="97816-419">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="97816-419">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="97816-420">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="97816-420">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="97816-421">**webapi**</span><span class="sxs-lookup"><span data-stu-id="97816-421">**webapi**</span></span>

<span data-ttu-id="97816-422">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="97816-422">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="97816-423">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="97816-423">The possible values are:</span></span>

- <span data-ttu-id="97816-424">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="97816-424">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="97816-425">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="97816-425">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="97816-426">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="97816-426">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="97816-427">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="97816-427">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="97816-428">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="97816-428">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="97816-429">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="97816-429">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="97816-430">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="97816-430">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="97816-431">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="97816-431">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="97816-432">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="97816-432">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="97816-433">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="97816-433">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="97816-434">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="97816-434">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="97816-435">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="97816-435">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="97816-436">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="97816-436">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="97816-437">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="97816-437">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="97816-438">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="97816-438">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="97816-439">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="97816-439">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="97816-440">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="97816-440">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="97816-441">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="97816-441">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="97816-442">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="97816-442">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="97816-443">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="97816-443">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="97816-444">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="97816-444">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="97816-445">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="97816-445">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="97816-446">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="97816-446">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="97816-447">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="97816-447">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="97816-448">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="97816-448">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="97816-449">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="97816-449">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="97816-450">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="97816-450">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="97816-451">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="97816-451">**mvc, razor**</span></span>

<span data-ttu-id="97816-452">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="97816-452">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="97816-453">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="97816-453">The possible values are:</span></span>

- <span data-ttu-id="97816-454">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="97816-454">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="97816-455">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="97816-455">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="97816-456">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="97816-456">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="97816-457">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="97816-457">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="97816-458">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="97816-458">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="97816-459">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="97816-459">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="97816-460">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="97816-460">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="97816-461">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="97816-461">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="97816-462">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="97816-462">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="97816-463">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="97816-463">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="97816-464">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="97816-464">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="97816-465">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="97816-465">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="97816-466">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="97816-466">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="97816-467">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="97816-467">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="97816-468">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="97816-468">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="97816-469">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="97816-469">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="97816-470">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="97816-470">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="97816-471">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="97816-471">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="97816-472">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="97816-472">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="97816-473">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="97816-473">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="97816-474">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="97816-474">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="97816-475">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="97816-475">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="97816-476">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="97816-476">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="97816-477">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="97816-477">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="97816-478">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="97816-478">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="97816-479">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="97816-479">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="97816-480">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="97816-480">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="97816-481">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="97816-481">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="97816-482">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="97816-482">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="97816-483">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="97816-483">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="97816-484">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="97816-484">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="97816-485">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="97816-485">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="97816-486">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="97816-486">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="97816-487">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="97816-487">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="97816-488">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="97816-488">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="97816-489">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="97816-489">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="97816-490">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="97816-490">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="97816-491">**page**</span><span class="sxs-lookup"><span data-stu-id="97816-491">**page**</span></span>

<span data-ttu-id="97816-492">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="97816-492">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="97816-493">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="97816-493">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="97816-494">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="97816-494">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="97816-495">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="97816-495">**viewimports**</span></span>

<span data-ttu-id="97816-496">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="97816-496">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="97816-497">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="97816-497">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="97816-498">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="97816-498">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="97816-499">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="97816-499">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="97816-500">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="97816-500">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="97816-501">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="97816-501">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="97816-502">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="97816-502">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="97816-503">**classlib**</span><span class="sxs-lookup"><span data-stu-id="97816-503">**classlib**</span></span>

<span data-ttu-id="97816-504">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="97816-504">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="97816-505">Значения: `netcoreapp1.0`, `netcoreapp1.1` или с `netstandard1.0` по `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="97816-505">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="97816-506">Значение по умолчанию — `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="97816-506">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="97816-507">**mvc**</span><span class="sxs-lookup"><span data-stu-id="97816-507">**mvc**</span></span>

<span data-ttu-id="97816-508">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="97816-508">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="97816-509">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="97816-509">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="97816-510">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="97816-510">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="97816-511">`-au|--auth` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="97816-511">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="97816-512">Значения: `None` или `Individual`.</span><span class="sxs-lookup"><span data-stu-id="97816-512">Values: `None` or `Individual`.</span></span> <span data-ttu-id="97816-513">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="97816-513">The default value is `None`.</span></span>

<span data-ttu-id="97816-514">`-uld|--use-local-db` — указывает, следует ли использовать LocalDB вместо SQLite.</span><span class="sxs-lookup"><span data-stu-id="97816-514">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="97816-515">Значения: `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="97816-515">Values: `true` or `false`.</span></span> <span data-ttu-id="97816-516">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="97816-516">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="97816-517">Примеры</span><span class="sxs-lookup"><span data-stu-id="97816-517">Examples</span></span>

<span data-ttu-id="97816-518">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="97816-518">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="97816-519">Создание проекта библиотеки классов .NET Standard в указанном каталоге (доступно только при использовании пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="97816-519">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="97816-520">Создание проекта приложения ASP.NET Core C# MVC в текущем каталоге без проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="97816-520">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="97816-521">Создание нового приложения xUnit:</span><span class="sxs-lookup"><span data-stu-id="97816-521">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="97816-522">Перечислите все шаблоны, доступные для MVC:</span><span class="sxs-lookup"><span data-stu-id="97816-522">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="97816-523">Установите версию 2.0 шаблонов одностраничного приложения для ASP.NET Core (параметр команды доступен в .NET Core SDK 1.1 и более поздних версиях):</span><span class="sxs-lookup"><span data-stu-id="97816-523">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="97816-524">Создайте *global.json* в текущем каталоге, указав версию пакета SDK 2.0.0 (доступно только для пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="97816-524">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="97816-525">См. также</span><span class="sxs-lookup"><span data-stu-id="97816-525">See also</span></span>

* [<span data-ttu-id="97816-526">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="97816-526">Custom templates for dotnet new</span></span>](custom-templates.md)  
* [<span data-ttu-id="97816-527">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="97816-527">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
* [<span data-ttu-id="97816-528">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="97816-528">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
* [<span data-ttu-id="97816-529">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="97816-529">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
