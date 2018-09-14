---
title: Команда dotnet new — интерфейс командной строки .NET Core
description: Команда dotnet new создает проекты .NET Core на основе указанного шаблона.
author: mairaw
ms.author: mairaw
ms.date: 07/31/2018
ms.openlocfilehash: 2c82dda2d93225edb360316637e22964135cd5e4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512559"
---
# <a name="dotnet-new"></a><span data-ttu-id="9cb31-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="9cb31-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="9cb31-104">name</span><span class="sxs-lookup"><span data-stu-id="9cb31-104">Name</span></span>

<span data-ttu-id="9cb31-105">`dotnet new` — создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="9cb31-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9cb31-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9cb31-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="9cb31-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9cb31-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="9cb31-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="9cb31-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9cb31-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9cb31-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="9cb31-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="9cb31-110">Description</span></span>

<span data-ttu-id="9cb31-111">Команда `dotnet new` предоставляет удобный способ инициализации проекта .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9cb31-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="9cb31-112">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="9cb31-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="9cb31-113">Аргументы</span><span class="sxs-lookup"><span data-stu-id="9cb31-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="9cb31-114">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="9cb31-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="9cb31-115">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="9cb31-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="9cb31-116">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="9cb31-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="9cb31-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9cb31-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="9cb31-118">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9cb31-118">The command contains a default list of templates.</span></span> <span data-ttu-id="9cb31-119">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="9cb31-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="9cb31-120">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="9cb31-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="9cb31-121">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="9cb31-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="9cb31-122">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="9cb31-122">Template description</span></span>                          | <span data-ttu-id="9cb31-123">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="9cb31-123">Template name</span></span>   | <span data-ttu-id="9cb31-124">Языки</span><span class="sxs-lookup"><span data-stu-id="9cb31-124">Languages</span></span>     |
|----------------------------------------------|-----------------|---------------|
| <span data-ttu-id="9cb31-125">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="9cb31-125">Console application</span></span>                          | `console`       | <span data-ttu-id="9cb31-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9cb31-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="9cb31-127">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="9cb31-127">Class library</span></span>                                | `classlib`      | <span data-ttu-id="9cb31-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9cb31-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="9cb31-129">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="9cb31-129">Unit test project</span></span>                            | `mstest`        | <span data-ttu-id="9cb31-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9cb31-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="9cb31-131">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="9cb31-131">xUnit test project</span></span>                           | `xunit`         | <span data-ttu-id="9cb31-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9cb31-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="9cb31-133">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="9cb31-133">Razor page</span></span>                                   | `page`          | <span data-ttu-id="9cb31-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cb31-134">[C#]</span></span>          |
| <span data-ttu-id="9cb31-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="9cb31-135">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="9cb31-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cb31-136">[C#]</span></span>          |
| <span data-ttu-id="9cb31-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="9cb31-137">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="9cb31-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cb31-138">[C#]</span></span>          |
| <span data-ttu-id="9cb31-139">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9cb31-139">ASP.NET Core empty</span></span>                           | `web`           | <span data-ttu-id="9cb31-140">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9cb31-140">[C#], F#</span></span>      |
| <span data-ttu-id="9cb31-141">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="9cb31-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="9cb31-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9cb31-142">[C#], F#</span></span>      |
| <span data-ttu-id="9cb31-143">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9cb31-143">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="9cb31-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cb31-144">[C#]</span></span>          |
| <span data-ttu-id="9cb31-145">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="9cb31-145">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="9cb31-146">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cb31-146">[C#]</span></span>          |
| <span data-ttu-id="9cb31-147">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="9cb31-147">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="9cb31-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cb31-148">[C#]</span></span>          |
| <span data-ttu-id="9cb31-149">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="9cb31-149">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="9cb31-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cb31-150">[C#]</span></span>          |
| <span data-ttu-id="9cb31-151">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9cb31-151">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="9cb31-152">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9cb31-152">[C#], F#</span></span>      |
| <span data-ttu-id="9cb31-153">Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="9cb31-153">Razor class library</span></span>                          | `razorclasslib` | <span data-ttu-id="9cb31-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cb31-154">[C#]</span></span>          |
| <span data-ttu-id="9cb31-155">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="9cb31-155">global.json file</span></span>                             | `globaljson`    |               |
| <span data-ttu-id="9cb31-156">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="9cb31-156">NuGet config</span></span>                                 | `nugetconfig`   |               |
| <span data-ttu-id="9cb31-157">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="9cb31-157">Web config</span></span>                                   | `webconfig`     |               |
| <span data-ttu-id="9cb31-158">Файл решения</span><span class="sxs-lookup"><span data-stu-id="9cb31-158">Solution file</span></span>                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="9cb31-159">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="9cb31-159">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="9cb31-160">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9cb31-160">The command contains a default list of templates.</span></span> <span data-ttu-id="9cb31-161">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="9cb31-161">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="9cb31-162">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="9cb31-162">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="9cb31-163">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="9cb31-163">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="9cb31-164">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="9cb31-164">Template description</span></span>                          | <span data-ttu-id="9cb31-165">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="9cb31-165">Template name</span></span> | <span data-ttu-id="9cb31-166">Языки</span><span class="sxs-lookup"><span data-stu-id="9cb31-166">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="9cb31-167">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="9cb31-167">Console application</span></span>                          | `console`     | <span data-ttu-id="9cb31-168">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9cb31-168">[C#], F#, VB</span></span>  |
| <span data-ttu-id="9cb31-169">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="9cb31-169">Class library</span></span>                                | `classlib`    | <span data-ttu-id="9cb31-170">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9cb31-170">[C#], F#, VB</span></span>  |
| <span data-ttu-id="9cb31-171">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="9cb31-171">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="9cb31-172">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9cb31-172">[C#], F#, VB</span></span>  |
| <span data-ttu-id="9cb31-173">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="9cb31-173">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="9cb31-174">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9cb31-174">[C#], F#, VB</span></span>  |
| <span data-ttu-id="9cb31-175">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9cb31-175">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="9cb31-176">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9cb31-176">[C#], F#</span></span>      |
| <span data-ttu-id="9cb31-177">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="9cb31-177">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="9cb31-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9cb31-178">[C#], F#</span></span>      |
| <span data-ttu-id="9cb31-179">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9cb31-179">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="9cb31-180">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cb31-180">[C#]</span></span>          |
| <span data-ttu-id="9cb31-181">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="9cb31-181">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="9cb31-182">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cb31-182">[C#]</span></span>          |
| <span data-ttu-id="9cb31-183">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="9cb31-183">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="9cb31-184">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cb31-184">[C#]</span></span>          |
| <span data-ttu-id="9cb31-185">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="9cb31-185">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="9cb31-186">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cb31-186">[C#]</span></span>          |
| <span data-ttu-id="9cb31-187">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9cb31-187">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="9cb31-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9cb31-188">[C#], F#</span></span>      |
| <span data-ttu-id="9cb31-189">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="9cb31-189">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="9cb31-190">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="9cb31-190">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="9cb31-191">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="9cb31-191">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="9cb31-192">Файл решения</span><span class="sxs-lookup"><span data-stu-id="9cb31-192">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="9cb31-193">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="9cb31-193">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="9cb31-194">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="9cb31-194">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="9cb31-195">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="9cb31-195">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9cb31-196">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9cb31-196">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="9cb31-197">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9cb31-197">The command contains a default list of templates.</span></span> <span data-ttu-id="9cb31-198">Используйте `dotnet new -all`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="9cb31-198">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="9cb31-199">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="9cb31-199">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="9cb31-200">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="9cb31-200">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="9cb31-201">Описание шаблона</span><span class="sxs-lookup"><span data-stu-id="9cb31-201">Template description</span></span>  | <span data-ttu-id="9cb31-202">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="9cb31-202">Template name</span></span> | <span data-ttu-id="9cb31-203">Языки</span><span class="sxs-lookup"><span data-stu-id="9cb31-203">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="9cb31-204">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="9cb31-204">Console application</span></span>  | `console`     | <span data-ttu-id="9cb31-205">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9cb31-205">[C#], F#</span></span>  |
| <span data-ttu-id="9cb31-206">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="9cb31-206">Class library</span></span>        | `classlib`    | <span data-ttu-id="9cb31-207">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9cb31-207">[C#], F#</span></span>  |
| <span data-ttu-id="9cb31-208">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="9cb31-208">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="9cb31-209">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9cb31-209">[C#], F#</span></span>  |
| <span data-ttu-id="9cb31-210">Проект теста xUnit</span><span class="sxs-lookup"><span data-stu-id="9cb31-210">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="9cb31-211">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9cb31-211">[C#], F#</span></span>  |
| <span data-ttu-id="9cb31-212">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9cb31-212">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="9cb31-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cb31-213">[C#]</span></span>      |
| <span data-ttu-id="9cb31-214">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9cb31-214">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="9cb31-215">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9cb31-215">[C#], F#</span></span>  |
| <span data-ttu-id="9cb31-216">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9cb31-216">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="9cb31-217">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cb31-217">[C#]</span></span>      |
| <span data-ttu-id="9cb31-218">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="9cb31-218">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="9cb31-219">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="9cb31-219">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="9cb31-220">Файл решения</span><span class="sxs-lookup"><span data-stu-id="9cb31-220">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="9cb31-221">Параметры</span><span class="sxs-lookup"><span data-stu-id="9cb31-221">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="9cb31-222">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9cb31-222">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="9cb31-223">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="9cb31-223">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="9cb31-224">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="9cb31-224">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="9cb31-225">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="9cb31-225">Prints out help for the command.</span></span> <span data-ttu-id="9cb31-226">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-226">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="9cb31-227">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-227">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="9cb31-228">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-228">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="9cb31-229">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="9cb31-229">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="9cb31-230">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="9cb31-230">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="9cb31-231">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="9cb31-231">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="9cb31-232">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="9cb31-232">Lists templates containing the specified name.</span></span> <span data-ttu-id="9cb31-233">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="9cb31-233">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="9cb31-234">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="9cb31-234">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="9cb31-235">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="9cb31-235">The language of the template to create.</span></span> <span data-ttu-id="9cb31-236">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="9cb31-236">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="9cb31-237">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="9cb31-237">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="9cb31-238">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="9cb31-238">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="9cb31-239">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-239">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="9cb31-240">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="9cb31-240">The name for the created output.</span></span> <span data-ttu-id="9cb31-241">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="9cb31-241">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="9cb31-242">Задает источник пакетов NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="9cb31-242">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="9cb31-243">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="9cb31-243">Location to place the generated output.</span></span> <span data-ttu-id="9cb31-244">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="9cb31-244">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="9cb31-245">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="9cb31-245">Filters templates based on available types.</span></span> <span data-ttu-id="9cb31-246">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="9cb31-246">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="9cb31-247">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-247">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="9cb31-248">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="9cb31-248">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="9cb31-249">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="9cb31-249">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="9cb31-250">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="9cb31-250">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="9cb31-251">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="9cb31-251">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="9cb31-252">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="9cb31-252">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="9cb31-253">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="9cb31-253">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="9cb31-254">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="9cb31-254">Prints out help for the command.</span></span> <span data-ttu-id="9cb31-255">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-255">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="9cb31-256">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-256">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="9cb31-257">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-257">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="9cb31-258">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="9cb31-258">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="9cb31-259">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="9cb31-259">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="9cb31-260">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="9cb31-260">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="9cb31-261">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="9cb31-261">Lists templates containing the specified name.</span></span> <span data-ttu-id="9cb31-262">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="9cb31-262">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="9cb31-263">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="9cb31-263">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="9cb31-264">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="9cb31-264">The language of the template to create.</span></span> <span data-ttu-id="9cb31-265">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="9cb31-265">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="9cb31-266">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="9cb31-266">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="9cb31-267">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="9cb31-267">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="9cb31-268">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-268">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="9cb31-269">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="9cb31-269">The name for the created output.</span></span> <span data-ttu-id="9cb31-270">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="9cb31-270">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="9cb31-271">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="9cb31-271">Location to place the generated output.</span></span> <span data-ttu-id="9cb31-272">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="9cb31-272">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="9cb31-273">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="9cb31-273">Filters templates based on available types.</span></span> <span data-ttu-id="9cb31-274">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="9cb31-274">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="9cb31-275">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-275">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="9cb31-276">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="9cb31-276">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="9cb31-277">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="9cb31-277">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="9cb31-278">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="9cb31-278">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9cb31-279">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9cb31-279">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="9cb31-280">Показывает все шаблоны определенного типа проекта при запуске в контексте одной только команды `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-280">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="9cb31-281">При запуске в контексте конкретного шаблона, например `dotnet new web -all`, `-all` интерпретируется как флаг принудительного создания.</span><span class="sxs-lookup"><span data-stu-id="9cb31-281">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="9cb31-282">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="9cb31-282">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="9cb31-283">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="9cb31-283">Prints out help for the command.</span></span> <span data-ttu-id="9cb31-284">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-284">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="9cb31-285">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="9cb31-285">Lists templates containing the specified name.</span></span> <span data-ttu-id="9cb31-286">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="9cb31-286">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="9cb31-287">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="9cb31-287">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="9cb31-288">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="9cb31-288">The language of the template to create.</span></span> <span data-ttu-id="9cb31-289">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="9cb31-289">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="9cb31-290">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="9cb31-290">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="9cb31-291">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="9cb31-291">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="9cb31-292">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-292">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="9cb31-293">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="9cb31-293">The name for the created output.</span></span> <span data-ttu-id="9cb31-294">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="9cb31-294">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="9cb31-295">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="9cb31-295">Location to place the generated output.</span></span> <span data-ttu-id="9cb31-296">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="9cb31-296">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="9cb31-297">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="9cb31-297">Template options</span></span>

<span data-ttu-id="9cb31-298">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="9cb31-298">Each project template may have additional options available.</span></span> <span data-ttu-id="9cb31-299">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="9cb31-299">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="9cb31-300">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9cb31-300">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="9cb31-301">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="9cb31-301">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="9cb31-302">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="9cb31-302">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9cb31-303">**classlib**</span><span class="sxs-lookup"><span data-stu-id="9cb31-303">**classlib**</span></span>

<span data-ttu-id="9cb31-304">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="9cb31-304">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9cb31-305">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="9cb31-305">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="9cb31-306">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-306">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="9cb31-307">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="9cb31-307">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9cb31-308">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="9cb31-308">**mstest, xunit**</span></span>

<span data-ttu-id="9cb31-309">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="9cb31-309">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="9cb31-310">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="9cb31-310">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9cb31-311">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="9cb31-311">**globaljson**</span></span>

<span data-ttu-id="9cb31-312">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="9cb31-312">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="9cb31-313">**web**</span><span class="sxs-lookup"><span data-stu-id="9cb31-313">**web**</span></span>

<span data-ttu-id="9cb31-314">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="9cb31-314">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="9cb31-315">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="9cb31-315">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9cb31-316">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9cb31-316">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="9cb31-317">Этот параметр применяется, только если `IndividualAuth` или `OrganizationalAuth` не используются.</span><span class="sxs-lookup"><span data-stu-id="9cb31-317">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="9cb31-318">**webapi**</span><span class="sxs-lookup"><span data-stu-id="9cb31-318">**webapi**</span></span>

<span data-ttu-id="9cb31-319">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="9cb31-319">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="9cb31-320">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="9cb31-320">The possible values are:</span></span>

- <span data-ttu-id="9cb31-321">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="9cb31-321">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="9cb31-322">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="9cb31-322">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="9cb31-323">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="9cb31-323">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="9cb31-324">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="9cb31-324">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="9cb31-325">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="9cb31-325">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="9cb31-326">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-326">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cb31-327">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-327">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="9cb31-328">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="9cb31-328">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="9cb31-329">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-329">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9cb31-330">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="9cb31-330">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="9cb31-331">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-331">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9cb31-332">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-332">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="9cb31-333">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="9cb31-333">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="9cb31-334">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-334">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="9cb31-335">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-335">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="9cb31-336">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="9cb31-336">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="9cb31-337">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-337">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cb31-338">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-338">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="9cb31-339">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="9cb31-339">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="9cb31-340">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-340">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9cb31-341">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-341">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="9cb31-342">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="9cb31-342">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="9cb31-343">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-343">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="9cb31-344">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="9cb31-344">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="9cb31-345">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="9cb31-345">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="9cb31-346">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-346">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9cb31-347">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="9cb31-347">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9cb31-348">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9cb31-348">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="9cb31-349">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-349">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="9cb31-350">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="9cb31-350">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="9cb31-351">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="9cb31-351">**mvc, razor**</span></span>

<span data-ttu-id="9cb31-352">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="9cb31-352">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="9cb31-353">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="9cb31-353">The possible values are:</span></span>

- <span data-ttu-id="9cb31-354">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="9cb31-354">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="9cb31-355">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="9cb31-355">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="9cb31-356">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="9cb31-356">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="9cb31-357">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="9cb31-357">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="9cb31-358">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="9cb31-358">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="9cb31-359">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="9cb31-359">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="9cb31-360">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="9cb31-360">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="9cb31-361">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-361">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cb31-362">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-362">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="9cb31-363">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="9cb31-363">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="9cb31-364">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-364">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9cb31-365">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="9cb31-365">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="9cb31-366">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-366">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9cb31-367">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="9cb31-367">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="9cb31-368">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-368">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9cb31-369">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="9cb31-369">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="9cb31-370">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-370">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="9cb31-371">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-371">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="9cb31-372">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="9cb31-372">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="9cb31-373">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-373">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="9cb31-374">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-374">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="9cb31-375">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="9cb31-375">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="9cb31-376">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-376">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cb31-377">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-377">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="9cb31-378">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="9cb31-378">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="9cb31-379">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-379">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9cb31-380">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-380">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="9cb31-381">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="9cb31-381">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="9cb31-382">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-382">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cb31-383">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-383">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="9cb31-384">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="9cb31-384">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="9cb31-385">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-385">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="9cb31-386">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="9cb31-386">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="9cb31-387">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="9cb31-387">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="9cb31-388">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="9cb31-388">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="9cb31-389">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-389">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9cb31-390">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="9cb31-390">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9cb31-391">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9cb31-391">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="9cb31-392">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-392">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="9cb31-393">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="9cb31-393">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="9cb31-394">**page**</span><span class="sxs-lookup"><span data-stu-id="9cb31-394">**page**</span></span>

<span data-ttu-id="9cb31-395">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="9cb31-395">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="9cb31-396">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-396">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="9cb31-397">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="9cb31-397">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="9cb31-398">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="9cb31-398">**viewimports**</span></span>

<span data-ttu-id="9cb31-399">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="9cb31-399">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="9cb31-400">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-400">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="9cb31-401">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="9cb31-401">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="9cb31-402">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="9cb31-402">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="9cb31-403">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="9cb31-403">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9cb31-404">**classlib**</span><span class="sxs-lookup"><span data-stu-id="9cb31-404">**classlib**</span></span>

<span data-ttu-id="9cb31-405">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="9cb31-405">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9cb31-406">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="9cb31-406">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="9cb31-407">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-407">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="9cb31-408">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="9cb31-408">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9cb31-409">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="9cb31-409">**mstest, xunit**</span></span>

<span data-ttu-id="9cb31-410">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="9cb31-410">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="9cb31-411">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="9cb31-411">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9cb31-412">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="9cb31-412">**globaljson**</span></span>

<span data-ttu-id="9cb31-413">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="9cb31-413">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="9cb31-414">**web**</span><span class="sxs-lookup"><span data-stu-id="9cb31-414">**web**</span></span>

<span data-ttu-id="9cb31-415">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="9cb31-415">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="9cb31-416">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="9cb31-416">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9cb31-417">**webapi**</span><span class="sxs-lookup"><span data-stu-id="9cb31-417">**webapi**</span></span>

<span data-ttu-id="9cb31-418">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="9cb31-418">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="9cb31-419">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="9cb31-419">The possible values are:</span></span>

- <span data-ttu-id="9cb31-420">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="9cb31-420">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="9cb31-421">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="9cb31-421">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="9cb31-422">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="9cb31-422">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="9cb31-423">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="9cb31-423">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="9cb31-424">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="9cb31-424">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="9cb31-425">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-425">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cb31-426">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-426">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="9cb31-427">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="9cb31-427">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="9cb31-428">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-428">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9cb31-429">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="9cb31-429">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="9cb31-430">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-430">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9cb31-431">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-431">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="9cb31-432">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="9cb31-432">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="9cb31-433">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-433">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="9cb31-434">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-434">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="9cb31-435">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="9cb31-435">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="9cb31-436">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-436">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cb31-437">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-437">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="9cb31-438">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="9cb31-438">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="9cb31-439">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-439">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9cb31-440">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-440">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="9cb31-441">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="9cb31-441">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="9cb31-442">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-442">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="9cb31-443">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="9cb31-443">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="9cb31-444">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="9cb31-444">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="9cb31-445">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-445">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9cb31-446">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="9cb31-446">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9cb31-447">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="9cb31-447">**mvc, razor**</span></span>

<span data-ttu-id="9cb31-448">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="9cb31-448">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="9cb31-449">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="9cb31-449">The possible values are:</span></span>

- <span data-ttu-id="9cb31-450">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="9cb31-450">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="9cb31-451">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="9cb31-451">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="9cb31-452">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="9cb31-452">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="9cb31-453">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="9cb31-453">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="9cb31-454">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="9cb31-454">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="9cb31-455">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="9cb31-455">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="9cb31-456">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="9cb31-456">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="9cb31-457">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-457">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cb31-458">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-458">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="9cb31-459">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="9cb31-459">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="9cb31-460">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-460">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9cb31-461">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="9cb31-461">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="9cb31-462">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-462">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9cb31-463">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="9cb31-463">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="9cb31-464">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-464">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9cb31-465">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="9cb31-465">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="9cb31-466">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-466">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="9cb31-467">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-467">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="9cb31-468">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="9cb31-468">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="9cb31-469">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-469">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="9cb31-470">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-470">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="9cb31-471">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="9cb31-471">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="9cb31-472">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-472">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cb31-473">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-473">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="9cb31-474">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="9cb31-474">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="9cb31-475">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-475">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9cb31-476">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-476">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="9cb31-477">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="9cb31-477">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="9cb31-478">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-478">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cb31-479">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-479">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="9cb31-480">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="9cb31-480">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="9cb31-481">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-481">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="9cb31-482">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="9cb31-482">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="9cb31-483">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="9cb31-483">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="9cb31-484">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="9cb31-484">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="9cb31-485">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-485">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9cb31-486">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="9cb31-486">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9cb31-487">**page**</span><span class="sxs-lookup"><span data-stu-id="9cb31-487">**page**</span></span>

<span data-ttu-id="9cb31-488">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="9cb31-488">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="9cb31-489">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-489">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="9cb31-490">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="9cb31-490">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="9cb31-491">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="9cb31-491">**viewimports**</span></span>

<span data-ttu-id="9cb31-492">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="9cb31-492">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="9cb31-493">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-493">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9cb31-494">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9cb31-494">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="9cb31-495">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="9cb31-495">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="9cb31-496">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="9cb31-496">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9cb31-497">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-497">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="9cb31-498">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-498">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="9cb31-499">**classlib**</span><span class="sxs-lookup"><span data-stu-id="9cb31-499">**classlib**</span></span>

<span data-ttu-id="9cb31-500">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="9cb31-500">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9cb31-501">Значения: `netcoreapp1.0`, `netcoreapp1.1` или с `netstandard1.0` по `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-501">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="9cb31-502">Значение по умолчанию — `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-502">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="9cb31-503">**mvc**</span><span class="sxs-lookup"><span data-stu-id="9cb31-503">**mvc**</span></span>

<span data-ttu-id="9cb31-504">`-f|--framework` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="9cb31-504">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9cb31-505">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-505">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="9cb31-506">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-506">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="9cb31-507">`-au|--auth` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="9cb31-507">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="9cb31-508">Значения: `None` или `Individual`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-508">Values: `None` or `Individual`.</span></span> <span data-ttu-id="9cb31-509">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-509">The default value is `None`.</span></span>

<span data-ttu-id="9cb31-510">`-uld|--use-local-db` — указывает, следует ли использовать LocalDB вместо SQLite.</span><span class="sxs-lookup"><span data-stu-id="9cb31-510">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="9cb31-511">Значения: `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-511">Values: `true` or `false`.</span></span> <span data-ttu-id="9cb31-512">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="9cb31-512">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="9cb31-513">Примеры</span><span class="sxs-lookup"><span data-stu-id="9cb31-513">Examples</span></span>

<span data-ttu-id="9cb31-514">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="9cb31-514">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="9cb31-515">Создание проекта библиотеки классов .NET Standard в указанном каталоге (доступно только при использовании пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="9cb31-515">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="9cb31-516">Создание проекта приложения ASP.NET Core C# MVC в текущем каталоге без проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="9cb31-516">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="9cb31-517">Создание нового приложения xUnit:</span><span class="sxs-lookup"><span data-stu-id="9cb31-517">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="9cb31-518">Перечислите все шаблоны, доступные для MVC:</span><span class="sxs-lookup"><span data-stu-id="9cb31-518">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="9cb31-519">Установите версию 2.0 шаблонов одностраничного приложения для ASP.NET Core (параметр команды доступен в .NET Core SDK 1.1 и более поздних версиях):</span><span class="sxs-lookup"><span data-stu-id="9cb31-519">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="9cb31-520">Создайте *global.json* в текущем каталоге, указав версию пакета SDK 2.0.0 (доступно только для пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="9cb31-520">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="9cb31-521">См. также</span><span class="sxs-lookup"><span data-stu-id="9cb31-521">See also</span></span>

* [<span data-ttu-id="9cb31-522">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="9cb31-522">Custom templates for dotnet new</span></span>](custom-templates.md)  
* [<span data-ttu-id="9cb31-523">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="9cb31-523">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
* [<span data-ttu-id="9cb31-524">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="9cb31-524">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
* [<span data-ttu-id="9cb31-525">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="9cb31-525">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
