---
title: Команда dotnet new
description: Команда dotnet new создает проекты .NET Core на основе указанного шаблона.
ms.date: 10/24/2018
ms.openlocfilehash: 5177c920fee6fa946d2bf5d96644f26309ed0a99
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54516152"
---
# <a name="dotnet-new"></a><span data-ttu-id="b2aec-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="b2aec-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="b2aec-104">name</span><span class="sxs-lookup"><span data-stu-id="b2aec-104">Name</span></span>

<span data-ttu-id="b2aec-105">`dotnet new` — создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="b2aec-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b2aec-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b2aec-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="b2aec-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b2aec-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="b2aec-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b2aec-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b2aec-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b2aec-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="b2aec-110">Описание</span><span class="sxs-lookup"><span data-stu-id="b2aec-110">Description</span></span>

<span data-ttu-id="b2aec-111">Команда `dotnet new` предоставляет удобный способ инициализации проекта .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b2aec-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="b2aec-112">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="b2aec-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="b2aec-113">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b2aec-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="b2aec-114">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="b2aec-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="b2aec-115">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="b2aec-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="b2aec-116">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="b2aec-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="b2aec-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b2aec-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="b2aec-118">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b2aec-118">The command contains a default list of templates.</span></span> <span data-ttu-id="b2aec-119">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b2aec-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="b2aec-120">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="b2aec-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="b2aec-121">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="b2aec-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="b2aec-122">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="b2aec-122">Template description</span></span>                          | <span data-ttu-id="b2aec-123">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="b2aec-123">Template name</span></span>    | <span data-ttu-id="b2aec-124">Языки</span><span class="sxs-lookup"><span data-stu-id="b2aec-124">Languages</span></span>     |
|----------------------------------------------|------------------|---------------|
| <span data-ttu-id="b2aec-125">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="b2aec-125">Console application</span></span>                          | `console`        | <span data-ttu-id="b2aec-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b2aec-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b2aec-127">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="b2aec-127">Class library</span></span>                                | `classlib`       | <span data-ttu-id="b2aec-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b2aec-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b2aec-129">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="b2aec-129">Unit test project</span></span>                            | `mstest`         | <span data-ttu-id="b2aec-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b2aec-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b2aec-131">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="b2aec-131">xUnit test project</span></span>                           | `xunit`          | <span data-ttu-id="b2aec-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b2aec-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b2aec-133">Проект теста NUnit</span><span class="sxs-lookup"><span data-stu-id="b2aec-133">NUnit test project</span></span>                           | `nunit`          | <span data-ttu-id="b2aec-134">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b2aec-134">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b2aec-135">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="b2aec-135">Razor page</span></span>                                   | `page`           | <span data-ttu-id="b2aec-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="b2aec-136">[C#]</span></span>          |
| <span data-ttu-id="b2aec-137">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="b2aec-137">MVC ViewImports</span></span>                              | `viewimports`    | <span data-ttu-id="b2aec-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="b2aec-138">[C#]</span></span>          |
| <span data-ttu-id="b2aec-139">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="b2aec-139">MVC ViewStart</span></span>                                | `viewstart`      | <span data-ttu-id="b2aec-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="b2aec-140">[C#]</span></span>          |
| <span data-ttu-id="b2aec-141">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b2aec-141">ASP.NET Core empty</span></span>                           | `web`            | <span data-ttu-id="b2aec-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b2aec-142">[C#], F#</span></span>      |
| <span data-ttu-id="b2aec-143">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="b2aec-143">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`            | <span data-ttu-id="b2aec-144">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b2aec-144">[C#], F#</span></span>      |
| <span data-ttu-id="b2aec-145">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b2aec-145">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="b2aec-146">`razor`, `webapp`</span><span class="sxs-lookup"><span data-stu-id="b2aec-146">`razor`, `webapp`</span></span>| <span data-ttu-id="b2aec-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="b2aec-147">[C#]</span></span>          |
| <span data-ttu-id="b2aec-148">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="b2aec-148">ASP.NET Core with Angular</span></span>                    | `angular`        | <span data-ttu-id="b2aec-149">[C#]</span><span class="sxs-lookup"><span data-stu-id="b2aec-149">[C#]</span></span>          |
| <span data-ttu-id="b2aec-150">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="b2aec-150">ASP.NET Core with React.js</span></span>                   | `react`          | <span data-ttu-id="b2aec-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="b2aec-151">[C#]</span></span>          |
| <span data-ttu-id="b2aec-152">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="b2aec-152">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`     | <span data-ttu-id="b2aec-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="b2aec-153">[C#]</span></span>          |
| <span data-ttu-id="b2aec-154">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b2aec-154">ASP.NET Core Web API</span></span>                         | `webapi`         | <span data-ttu-id="b2aec-155">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b2aec-155">[C#], F#</span></span>      |
| <span data-ttu-id="b2aec-156">Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="b2aec-156">Razor class library</span></span>                          | `razorclasslib`  | <span data-ttu-id="b2aec-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="b2aec-157">[C#]</span></span>          |
| <span data-ttu-id="b2aec-158">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="b2aec-158">global.json file</span></span>                             | `globaljson`     |               |
| <span data-ttu-id="b2aec-159">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="b2aec-159">NuGet config</span></span>                                 | `nugetconfig`    |               |
| <span data-ttu-id="b2aec-160">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="b2aec-160">Web config</span></span>                                   | `webconfig`      |               |
| <span data-ttu-id="b2aec-161">Файл решения</span><span class="sxs-lookup"><span data-stu-id="b2aec-161">Solution file</span></span>                                | `sln`            |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="b2aec-162">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b2aec-162">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="b2aec-163">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b2aec-163">The command contains a default list of templates.</span></span> <span data-ttu-id="b2aec-164">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b2aec-164">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="b2aec-165">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="b2aec-165">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="b2aec-166">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="b2aec-166">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="b2aec-167">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="b2aec-167">Template description</span></span>                          | <span data-ttu-id="b2aec-168">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="b2aec-168">Template name</span></span> | <span data-ttu-id="b2aec-169">Языки</span><span class="sxs-lookup"><span data-stu-id="b2aec-169">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="b2aec-170">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="b2aec-170">Console application</span></span>                          | `console`     | <span data-ttu-id="b2aec-171">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b2aec-171">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b2aec-172">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="b2aec-172">Class library</span></span>                                | `classlib`    | <span data-ttu-id="b2aec-173">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b2aec-173">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b2aec-174">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="b2aec-174">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="b2aec-175">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b2aec-175">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b2aec-176">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="b2aec-176">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="b2aec-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b2aec-177">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b2aec-178">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b2aec-178">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="b2aec-179">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b2aec-179">[C#], F#</span></span>      |
| <span data-ttu-id="b2aec-180">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="b2aec-180">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="b2aec-181">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b2aec-181">[C#], F#</span></span>      |
| <span data-ttu-id="b2aec-182">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b2aec-182">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="b2aec-183">[C#]</span><span class="sxs-lookup"><span data-stu-id="b2aec-183">[C#]</span></span>          |
| <span data-ttu-id="b2aec-184">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="b2aec-184">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="b2aec-185">[C#]</span><span class="sxs-lookup"><span data-stu-id="b2aec-185">[C#]</span></span>          |
| <span data-ttu-id="b2aec-186">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="b2aec-186">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="b2aec-187">[C#]</span><span class="sxs-lookup"><span data-stu-id="b2aec-187">[C#]</span></span>          |
| <span data-ttu-id="b2aec-188">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="b2aec-188">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="b2aec-189">[C#]</span><span class="sxs-lookup"><span data-stu-id="b2aec-189">[C#]</span></span>          |
| <span data-ttu-id="b2aec-190">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b2aec-190">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="b2aec-191">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b2aec-191">[C#], F#</span></span>      |
| <span data-ttu-id="b2aec-192">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="b2aec-192">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="b2aec-193">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="b2aec-193">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="b2aec-194">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="b2aec-194">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="b2aec-195">Файл решения</span><span class="sxs-lookup"><span data-stu-id="b2aec-195">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="b2aec-196">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="b2aec-196">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="b2aec-197">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="b2aec-197">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="b2aec-198">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="b2aec-198">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b2aec-199">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b2aec-199">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="b2aec-200">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b2aec-200">The command contains a default list of templates.</span></span> <span data-ttu-id="b2aec-201">Используйте `dotnet new -all`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b2aec-201">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="b2aec-202">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="b2aec-202">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="b2aec-203">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="b2aec-203">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="b2aec-204">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="b2aec-204">Template description</span></span>  | <span data-ttu-id="b2aec-205">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="b2aec-205">Template name</span></span> | <span data-ttu-id="b2aec-206">Языки</span><span class="sxs-lookup"><span data-stu-id="b2aec-206">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="b2aec-207">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="b2aec-207">Console application</span></span>  | `console`     | <span data-ttu-id="b2aec-208">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b2aec-208">[C#], F#</span></span>  |
| <span data-ttu-id="b2aec-209">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="b2aec-209">Class library</span></span>        | `classlib`    | <span data-ttu-id="b2aec-210">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b2aec-210">[C#], F#</span></span>  |
| <span data-ttu-id="b2aec-211">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="b2aec-211">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="b2aec-212">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b2aec-212">[C#], F#</span></span>  |
| <span data-ttu-id="b2aec-213">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="b2aec-213">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="b2aec-214">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b2aec-214">[C#], F#</span></span>  |
| <span data-ttu-id="b2aec-215">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b2aec-215">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="b2aec-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="b2aec-216">[C#]</span></span>      |
| <span data-ttu-id="b2aec-217">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b2aec-217">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="b2aec-218">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b2aec-218">[C#], F#</span></span>  |
| <span data-ttu-id="b2aec-219">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b2aec-219">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="b2aec-220">[C#]</span><span class="sxs-lookup"><span data-stu-id="b2aec-220">[C#]</span></span>      |
| <span data-ttu-id="b2aec-221">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="b2aec-221">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="b2aec-222">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="b2aec-222">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="b2aec-223">Файл решения</span><span class="sxs-lookup"><span data-stu-id="b2aec-223">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="b2aec-224">Параметры</span><span class="sxs-lookup"><span data-stu-id="b2aec-224">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="b2aec-225">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b2aec-225">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="b2aec-226">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="b2aec-226">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="b2aec-227">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="b2aec-227">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="b2aec-228">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="b2aec-228">Prints out help for the command.</span></span> <span data-ttu-id="b2aec-229">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-229">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="b2aec-230">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-230">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="b2aec-231">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-231">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="b2aec-232">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="b2aec-232">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="b2aec-233">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="b2aec-233">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="b2aec-234">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="b2aec-234">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="b2aec-235">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="b2aec-235">Lists templates containing the specified name.</span></span> <span data-ttu-id="b2aec-236">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="b2aec-236">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="b2aec-237">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="b2aec-237">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="b2aec-238">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="b2aec-238">The language of the template to create.</span></span> <span data-ttu-id="b2aec-239">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="b2aec-239">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="b2aec-240">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b2aec-240">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="b2aec-241">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="b2aec-241">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="b2aec-242">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-242">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="b2aec-243">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b2aec-243">The name for the created output.</span></span> <span data-ttu-id="b2aec-244">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="b2aec-244">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="b2aec-245">Задает источник пакетов NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="b2aec-245">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b2aec-246">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="b2aec-246">Location to place the generated output.</span></span> <span data-ttu-id="b2aec-247">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="b2aec-247">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="b2aec-248">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="b2aec-248">Filters templates based on available types.</span></span> <span data-ttu-id="b2aec-249">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="b2aec-249">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="b2aec-250">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-250">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="b2aec-251">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="b2aec-251">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="b2aec-252">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="b2aec-252">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="b2aec-253">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="b2aec-253">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="b2aec-254">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b2aec-254">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="b2aec-255">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="b2aec-255">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="b2aec-256">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="b2aec-256">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="b2aec-257">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="b2aec-257">Prints out help for the command.</span></span> <span data-ttu-id="b2aec-258">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-258">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="b2aec-259">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-259">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="b2aec-260">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-260">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="b2aec-261">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="b2aec-261">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="b2aec-262">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="b2aec-262">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="b2aec-263">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="b2aec-263">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="b2aec-264">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="b2aec-264">Lists templates containing the specified name.</span></span> <span data-ttu-id="b2aec-265">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="b2aec-265">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="b2aec-266">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="b2aec-266">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="b2aec-267">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="b2aec-267">The language of the template to create.</span></span> <span data-ttu-id="b2aec-268">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="b2aec-268">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="b2aec-269">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b2aec-269">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="b2aec-270">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="b2aec-270">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="b2aec-271">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-271">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="b2aec-272">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b2aec-272">The name for the created output.</span></span> <span data-ttu-id="b2aec-273">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="b2aec-273">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b2aec-274">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="b2aec-274">Location to place the generated output.</span></span> <span data-ttu-id="b2aec-275">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="b2aec-275">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="b2aec-276">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="b2aec-276">Filters templates based on available types.</span></span> <span data-ttu-id="b2aec-277">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="b2aec-277">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="b2aec-278">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-278">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="b2aec-279">Чтобы удалить шаблон, используя путь к исходному пакету `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="b2aec-279">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="b2aec-280">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="b2aec-280">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="b2aec-281">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="b2aec-281">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="b2aec-282">Если вам не удается определить аргумент `PATH` или `NUGET_ID`, необходимый для удаления шаблона, выполните команду `dotnet new --uninstall` без аргумента. В результате будут перечислены все установленные шаблоны и аргумент, необходимый для их удаления.</span><span class="sxs-lookup"><span data-stu-id="b2aec-282">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b2aec-283">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b2aec-283">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="b2aec-284">Показывает все шаблоны определенного типа проекта при запуске в контексте одной только команды `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-284">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="b2aec-285">При запуске в контексте конкретного шаблона, например `dotnet new web -all`, `-all` интерпретируется как флаг принудительного создания.</span><span class="sxs-lookup"><span data-stu-id="b2aec-285">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="b2aec-286">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="b2aec-286">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="b2aec-287">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="b2aec-287">Prints out help for the command.</span></span> <span data-ttu-id="b2aec-288">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-288">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="b2aec-289">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="b2aec-289">Lists templates containing the specified name.</span></span> <span data-ttu-id="b2aec-290">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="b2aec-290">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="b2aec-291">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="b2aec-291">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="b2aec-292">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="b2aec-292">The language of the template to create.</span></span> <span data-ttu-id="b2aec-293">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="b2aec-293">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="b2aec-294">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b2aec-294">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="b2aec-295">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="b2aec-295">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="b2aec-296">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-296">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="b2aec-297">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b2aec-297">The name for the created output.</span></span> <span data-ttu-id="b2aec-298">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="b2aec-298">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b2aec-299">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="b2aec-299">Location to place the generated output.</span></span> <span data-ttu-id="b2aec-300">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="b2aec-300">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="b2aec-301">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="b2aec-301">Template options</span></span>

<span data-ttu-id="b2aec-302">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="b2aec-302">Each project template may have additional options available.</span></span> <span data-ttu-id="b2aec-303">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="b2aec-303">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="b2aec-304">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b2aec-304">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="b2aec-305">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="b2aec-305">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="b2aec-306">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b2aec-306">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b2aec-307">**classlib**</span><span class="sxs-lookup"><span data-stu-id="b2aec-307">**classlib**</span></span>

<span data-ttu-id="b2aec-308">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="b2aec-308">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b2aec-309">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="b2aec-309">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="b2aec-310">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-310">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="b2aec-311">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b2aec-311">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b2aec-312">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="b2aec-312">**mstest, xunit**</span></span>

<span data-ttu-id="b2aec-313">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="b2aec-313">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="b2aec-314">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b2aec-314">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b2aec-315">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="b2aec-315">**globaljson**</span></span>

<span data-ttu-id="b2aec-316">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="b2aec-316">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="b2aec-317">**web**</span><span class="sxs-lookup"><span data-stu-id="b2aec-317">**web**</span></span>

<span data-ttu-id="b2aec-318">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="b2aec-318">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="b2aec-319">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b2aec-319">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b2aec-320">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b2aec-320">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="b2aec-321">Этот параметр применяется, только если `IndividualAuth` или `OrganizationalAuth` не используются.</span><span class="sxs-lookup"><span data-stu-id="b2aec-321">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="b2aec-322">**webapi**</span><span class="sxs-lookup"><span data-stu-id="b2aec-322">**webapi**</span></span>

<span data-ttu-id="b2aec-323">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b2aec-323">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="b2aec-324">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="b2aec-324">The possible values are:</span></span>

- <span data-ttu-id="b2aec-325">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b2aec-325">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="b2aec-326">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="b2aec-326">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="b2aec-327">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="b2aec-327">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="b2aec-328">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="b2aec-328">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="b2aec-329">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="b2aec-329">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b2aec-330">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-330">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b2aec-331">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-331">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="b2aec-332">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b2aec-332">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b2aec-333">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-333">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b2aec-334">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="b2aec-334">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b2aec-335">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-335">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b2aec-336">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-336">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="b2aec-337">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b2aec-337">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="b2aec-338">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-338">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="b2aec-339">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-339">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="b2aec-340">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="b2aec-340">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="b2aec-341">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-341">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b2aec-342">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-342">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="b2aec-343">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="b2aec-343">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b2aec-344">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-344">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b2aec-345">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-345">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="b2aec-346">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="b2aec-346">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="b2aec-347">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-347">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="b2aec-348">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="b2aec-348">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="b2aec-349">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="b2aec-349">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b2aec-350">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-350">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b2aec-351">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b2aec-351">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b2aec-352">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b2aec-352">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="b2aec-353">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-353">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="b2aec-354">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="b2aec-354">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="b2aec-355">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="b2aec-355">**mvc, razor**</span></span>

<span data-ttu-id="b2aec-356">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b2aec-356">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="b2aec-357">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="b2aec-357">The possible values are:</span></span>

- <span data-ttu-id="b2aec-358">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b2aec-358">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="b2aec-359">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="b2aec-359">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="b2aec-360">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="b2aec-360">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="b2aec-361">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="b2aec-361">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="b2aec-362">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="b2aec-362">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="b2aec-363">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="b2aec-363">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="b2aec-364">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="b2aec-364">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b2aec-365">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-365">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b2aec-366">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-366">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="b2aec-367">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b2aec-367">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b2aec-368">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-368">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b2aec-369">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b2aec-369">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="b2aec-370">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-370">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b2aec-371">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b2aec-371">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="b2aec-372">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-372">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b2aec-373">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="b2aec-373">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b2aec-374">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-374">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="b2aec-375">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-375">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="b2aec-376">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b2aec-376">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="b2aec-377">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-377">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="b2aec-378">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-378">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="b2aec-379">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="b2aec-379">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="b2aec-380">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-380">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b2aec-381">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-381">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="b2aec-382">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="b2aec-382">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b2aec-383">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-383">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b2aec-384">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-384">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="b2aec-385">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="b2aec-385">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="b2aec-386">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-386">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b2aec-387">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-387">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="b2aec-388">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="b2aec-388">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="b2aec-389">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-389">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="b2aec-390">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="b2aec-390">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="b2aec-391">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="b2aec-391">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="b2aec-392">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="b2aec-392">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b2aec-393">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-393">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b2aec-394">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b2aec-394">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b2aec-395">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b2aec-395">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="b2aec-396">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-396">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="b2aec-397">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="b2aec-397">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="b2aec-398">**page**</span><span class="sxs-lookup"><span data-stu-id="b2aec-398">**page**</span></span>

<span data-ttu-id="b2aec-399">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="b2aec-399">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="b2aec-400">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-400">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="b2aec-401">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="b2aec-401">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="b2aec-402">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="b2aec-402">**viewimports**</span></span>

<span data-ttu-id="b2aec-403">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="b2aec-403">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="b2aec-404">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-404">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="b2aec-405">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b2aec-405">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="b2aec-406">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="b2aec-406">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="b2aec-407">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b2aec-407">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b2aec-408">**classlib**</span><span class="sxs-lookup"><span data-stu-id="b2aec-408">**classlib**</span></span>

<span data-ttu-id="b2aec-409">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="b2aec-409">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b2aec-410">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="b2aec-410">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="b2aec-411">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-411">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="b2aec-412">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b2aec-412">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b2aec-413">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="b2aec-413">**mstest, xunit**</span></span>

<span data-ttu-id="b2aec-414">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="b2aec-414">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="b2aec-415">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b2aec-415">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b2aec-416">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="b2aec-416">**globaljson**</span></span>

<span data-ttu-id="b2aec-417">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="b2aec-417">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="b2aec-418">**web**</span><span class="sxs-lookup"><span data-stu-id="b2aec-418">**web**</span></span>

<span data-ttu-id="b2aec-419">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="b2aec-419">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="b2aec-420">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b2aec-420">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b2aec-421">**webapi**</span><span class="sxs-lookup"><span data-stu-id="b2aec-421">**webapi**</span></span>

<span data-ttu-id="b2aec-422">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b2aec-422">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="b2aec-423">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="b2aec-423">The possible values are:</span></span>

- <span data-ttu-id="b2aec-424">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b2aec-424">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="b2aec-425">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="b2aec-425">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="b2aec-426">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="b2aec-426">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="b2aec-427">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="b2aec-427">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="b2aec-428">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="b2aec-428">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b2aec-429">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-429">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b2aec-430">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-430">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="b2aec-431">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b2aec-431">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b2aec-432">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-432">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b2aec-433">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="b2aec-433">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b2aec-434">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-434">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b2aec-435">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-435">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="b2aec-436">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b2aec-436">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="b2aec-437">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-437">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="b2aec-438">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-438">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="b2aec-439">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="b2aec-439">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="b2aec-440">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-440">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b2aec-441">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-441">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="b2aec-442">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="b2aec-442">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b2aec-443">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-443">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b2aec-444">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-444">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="b2aec-445">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="b2aec-445">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="b2aec-446">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-446">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="b2aec-447">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="b2aec-447">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="b2aec-448">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="b2aec-448">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b2aec-449">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-449">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b2aec-450">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b2aec-450">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b2aec-451">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="b2aec-451">**mvc, razor**</span></span>

<span data-ttu-id="b2aec-452">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b2aec-452">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="b2aec-453">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="b2aec-453">The possible values are:</span></span>

- <span data-ttu-id="b2aec-454">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b2aec-454">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="b2aec-455">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="b2aec-455">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="b2aec-456">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="b2aec-456">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="b2aec-457">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="b2aec-457">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="b2aec-458">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="b2aec-458">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="b2aec-459">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="b2aec-459">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="b2aec-460">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="b2aec-460">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b2aec-461">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-461">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b2aec-462">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-462">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="b2aec-463">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b2aec-463">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b2aec-464">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-464">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b2aec-465">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b2aec-465">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="b2aec-466">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-466">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b2aec-467">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b2aec-467">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="b2aec-468">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-468">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b2aec-469">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="b2aec-469">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b2aec-470">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-470">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="b2aec-471">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-471">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="b2aec-472">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b2aec-472">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="b2aec-473">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-473">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="b2aec-474">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-474">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="b2aec-475">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="b2aec-475">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="b2aec-476">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-476">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b2aec-477">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-477">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="b2aec-478">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="b2aec-478">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b2aec-479">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-479">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b2aec-480">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-480">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="b2aec-481">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="b2aec-481">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="b2aec-482">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-482">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b2aec-483">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-483">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="b2aec-484">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="b2aec-484">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="b2aec-485">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-485">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="b2aec-486">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="b2aec-486">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="b2aec-487">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="b2aec-487">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="b2aec-488">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="b2aec-488">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b2aec-489">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-489">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b2aec-490">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b2aec-490">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b2aec-491">**page**</span><span class="sxs-lookup"><span data-stu-id="b2aec-491">**page**</span></span>

<span data-ttu-id="b2aec-492">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="b2aec-492">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="b2aec-493">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-493">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="b2aec-494">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="b2aec-494">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="b2aec-495">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="b2aec-495">**viewimports**</span></span>

<span data-ttu-id="b2aec-496">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="b2aec-496">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="b2aec-497">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-497">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b2aec-498">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b2aec-498">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="b2aec-499">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="b2aec-499">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="b2aec-500">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="b2aec-500">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b2aec-501">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-501">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="b2aec-502">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-502">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="b2aec-503">**classlib**</span><span class="sxs-lookup"><span data-stu-id="b2aec-503">**classlib**</span></span>

<span data-ttu-id="b2aec-504">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="b2aec-504">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b2aec-505">Значения: `netcoreapp1.0`, `netcoreapp1.1` или с `netstandard1.0` по `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-505">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="b2aec-506">Значение по умолчанию — `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-506">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="b2aec-507">**mvc**</span><span class="sxs-lookup"><span data-stu-id="b2aec-507">**mvc**</span></span>

<span data-ttu-id="b2aec-508">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="b2aec-508">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b2aec-509">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-509">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="b2aec-510">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-510">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="b2aec-511">`-au|--auth` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b2aec-511">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="b2aec-512">Значения: `None` или `Individual`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-512">Values: `None` or `Individual`.</span></span> <span data-ttu-id="b2aec-513">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-513">The default value is `None`.</span></span>

<span data-ttu-id="b2aec-514">`-uld|--use-local-db` — указывает, следует ли использовать LocalDB вместо SQLite.</span><span class="sxs-lookup"><span data-stu-id="b2aec-514">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="b2aec-515">Значения: `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-515">Values: `true` or `false`.</span></span> <span data-ttu-id="b2aec-516">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="b2aec-516">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="b2aec-517">Примеры</span><span class="sxs-lookup"><span data-stu-id="b2aec-517">Examples</span></span>

<span data-ttu-id="b2aec-518">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="b2aec-518">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="b2aec-519">Создание проекта библиотеки классов .NET Standard в указанном каталоге (доступно только при использовании пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="b2aec-519">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="b2aec-520">Создание проекта приложения ASP.NET Core C# MVC в текущем каталоге без проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="b2aec-520">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="b2aec-521">Создание нового приложения xUnit:</span><span class="sxs-lookup"><span data-stu-id="b2aec-521">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="b2aec-522">Перечислите все шаблоны, доступные для MVC:</span><span class="sxs-lookup"><span data-stu-id="b2aec-522">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="b2aec-523">Установите версию 2.0 шаблонов одностраничного приложения для ASP.NET Core (параметр команды доступен в .NET Core SDK 1.1 и более поздних версиях):</span><span class="sxs-lookup"><span data-stu-id="b2aec-523">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="b2aec-524">Создайте *global.json* в текущем каталоге, указав версию пакета SDK 2.0.0 (доступно только для пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="b2aec-524">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="b2aec-525">См. также</span><span class="sxs-lookup"><span data-stu-id="b2aec-525">See also</span></span>

- [<span data-ttu-id="b2aec-526">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="b2aec-526">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="b2aec-527">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="b2aec-527">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)
- [<span data-ttu-id="b2aec-528">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="b2aec-528">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="b2aec-529">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="b2aec-529">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
