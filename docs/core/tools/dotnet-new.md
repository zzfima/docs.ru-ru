---
title: Команда dotnet new
description: Команда dotnet new создает проекты .NET Core на основе указанного шаблона.
ms.date: 05/06/2019
ms.openlocfilehash: c9529e135f48c80f445c91038294a3e7266486f1
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73420477"
---
# <a name="dotnet-new"></a><span data-ttu-id="b7817-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="b7817-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="b7817-104">name</span><span class="sxs-lookup"><span data-stu-id="b7817-104">Name</span></span>

<span data-ttu-id="b7817-105">`dotnet new` - создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="b7817-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b7817-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b7817-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="b7817-107">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="b7817-107">.NET Core 2.2</span></span>](#tab/netcore22)

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="b7817-108">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b7817-108">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="b7817-109">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b7817-109">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b7817-110">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b7817-110">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="b7817-111">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="b7817-111">Description</span></span>

<span data-ttu-id="b7817-112">Команда `dotnet new` предоставляет удобный способ инициализации проекта .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b7817-112">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="b7817-113">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="b7817-113">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="b7817-114">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b7817-114">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="b7817-115">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="b7817-115">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="b7817-116">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="b7817-116">Each template might have specific options you can pass.</span></span> <span data-ttu-id="b7817-117">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="b7817-117">For more information, see [Template options](#template-options).</span></span>

<span data-ttu-id="b7817-118">Если значение `TEMPLATE` не в точности совпадает с текстом в столбце **Шаблоны** или **Короткое имя**, для этих двух столбцов выполняется поиск совпадений в подстроках.</span><span class="sxs-lookup"><span data-stu-id="b7817-118">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column, a substring match is performed on those two columns.</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="b7817-119">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="b7817-119">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="b7817-120">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b7817-120">The command contains a default list of templates.</span></span> <span data-ttu-id="b7817-121">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b7817-121">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="b7817-122">В следующей таблице показаны шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.2.100.</span><span class="sxs-lookup"><span data-stu-id="b7817-122">The following table shows the templates that come pre-installed with the .NET Core SDK 2.2.100.</span></span> <span data-ttu-id="b7817-123">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="b7817-123">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="b7817-124">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="b7817-124">Templates</span></span>                                    | <span data-ttu-id="b7817-125">Краткое имя</span><span class="sxs-lookup"><span data-stu-id="b7817-125">Short Name</span></span>        | <span data-ttu-id="b7817-126">Язык</span><span class="sxs-lookup"><span data-stu-id="b7817-126">Language</span></span>     | <span data-ttu-id="b7817-127">Tags</span><span class="sxs-lookup"><span data-stu-id="b7817-127">Tags</span></span>                                  |
|----------------------------------------------|-------------------|--------------|---------------------------------------|
| <span data-ttu-id="b7817-128">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="b7817-128">Console Application</span></span>                          | `console`         | <span data-ttu-id="b7817-129">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b7817-129">[C#], F#, VB</span></span> | <span data-ttu-id="b7817-130">Общее/консоль</span><span class="sxs-lookup"><span data-stu-id="b7817-130">Common/Console</span></span>                        |
| <span data-ttu-id="b7817-131">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="b7817-131">Class library</span></span>                                | `classlib`        | <span data-ttu-id="b7817-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b7817-132">[C#], F#, VB</span></span> | <span data-ttu-id="b7817-133">Общее/библиотека</span><span class="sxs-lookup"><span data-stu-id="b7817-133">Common/Library</span></span>                        |
| <span data-ttu-id="b7817-134">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="b7817-134">Unit Test Project</span></span>                            | `mstest`          | <span data-ttu-id="b7817-135">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b7817-135">[C#], F#, VB</span></span> | <span data-ttu-id="b7817-136">Тест/MSTest</span><span class="sxs-lookup"><span data-stu-id="b7817-136">Test/MSTest</span></span>                           |
| <span data-ttu-id="b7817-137">Тестовый проект NUnit 3</span><span class="sxs-lookup"><span data-stu-id="b7817-137">NUnit 3 Test Project</span></span>                         | `nunit`           | <span data-ttu-id="b7817-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b7817-138">[C#], F#, VB</span></span> | <span data-ttu-id="b7817-139">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="b7817-139">Test/NUnit</span></span>                            |
| <span data-ttu-id="b7817-140">Элемент теста NUnit 3</span><span class="sxs-lookup"><span data-stu-id="b7817-140">NUnit 3 Test Item</span></span>                            | `nunit-test`      | <span data-ttu-id="b7817-141">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b7817-141">[C#], F#, VB</span></span> | <span data-ttu-id="b7817-142">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="b7817-142">Test/NUnit</span></span>                            |
| <span data-ttu-id="b7817-143">Тестовый проект xUnit</span><span class="sxs-lookup"><span data-stu-id="b7817-143">xUnit Test Project</span></span>                           | `xunit`           | <span data-ttu-id="b7817-144">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b7817-144">[C#], F#, VB</span></span> | <span data-ttu-id="b7817-145">Тест/xUnit</span><span class="sxs-lookup"><span data-stu-id="b7817-145">Test/xUnit</span></span>                            |
| <span data-ttu-id="b7817-146">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="b7817-146">Razor Page</span></span>                                   | `page`            | <span data-ttu-id="b7817-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7817-147">[C#]</span></span>         | <span data-ttu-id="b7817-148">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b7817-148">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="b7817-149">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="b7817-149">MVC ViewImports</span></span>                              | `viewimports`     | <span data-ttu-id="b7817-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7817-150">[C#]</span></span>         | <span data-ttu-id="b7817-151">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b7817-151">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="b7817-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="b7817-152">MVC ViewStart</span></span>                                | `viewstart`       | <span data-ttu-id="b7817-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7817-153">[C#]</span></span>         | <span data-ttu-id="b7817-154">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b7817-154">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="b7817-155">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7817-155">ASP.NET Core Empty</span></span>                           | `web`             | <span data-ttu-id="b7817-156">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b7817-156">[C#], F#</span></span>     | <span data-ttu-id="b7817-157">Веб/пусто</span><span class="sxs-lookup"><span data-stu-id="b7817-157">Web/Empty</span></span>                             |
| <span data-ttu-id="b7817-158">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="b7817-158">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`             | <span data-ttu-id="b7817-159">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b7817-159">[C#], F#</span></span>     | <span data-ttu-id="b7817-160">Веб/MVC</span><span class="sxs-lookup"><span data-stu-id="b7817-160">Web/MVC</span></span>                               |
| <span data-ttu-id="b7817-161">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7817-161">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="b7817-162">`webapp`, `razor`</span><span class="sxs-lookup"><span data-stu-id="b7817-162">`webapp`, `razor`</span></span> | <span data-ttu-id="b7817-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7817-163">[C#]</span></span>         | <span data-ttu-id="b7817-164">Веб/MVC и Razor Pages</span><span class="sxs-lookup"><span data-stu-id="b7817-164">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="b7817-165">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="b7817-165">ASP.NET Core with Angular</span></span>                    | `angular`         | <span data-ttu-id="b7817-166">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7817-166">[C#]</span></span>         | <span data-ttu-id="b7817-167">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="b7817-167">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="b7817-168">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="b7817-168">ASP.NET Core with React.js</span></span>                   | `react`           | <span data-ttu-id="b7817-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7817-169">[C#]</span></span>         | <span data-ttu-id="b7817-170">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="b7817-170">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="b7817-171">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="b7817-171">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`      | <span data-ttu-id="b7817-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7817-172">[C#]</span></span>         | <span data-ttu-id="b7817-173">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="b7817-173">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="b7817-174">Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="b7817-174">Razor Class Library</span></span>                          | `razorclasslib`   | <span data-ttu-id="b7817-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7817-175">[C#]</span></span>         | <span data-ttu-id="b7817-176">Веб/Razor/Библиотека/Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="b7817-176">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="b7817-177">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7817-177">ASP.NET Core Web API</span></span>                         | `webapi`          | <span data-ttu-id="b7817-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b7817-178">[C#], F#</span></span>     | <span data-ttu-id="b7817-179">Веб/веб-API</span><span class="sxs-lookup"><span data-stu-id="b7817-179">Web/WebAPI</span></span>                            |
| <span data-ttu-id="b7817-180">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="b7817-180">global.json file</span></span>                             | `globaljson`      |              | <span data-ttu-id="b7817-181">Config</span><span class="sxs-lookup"><span data-stu-id="b7817-181">Config</span></span>                                |
| <span data-ttu-id="b7817-182">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="b7817-182">NuGet Config</span></span>                                 | `nugetconfig`     |              | <span data-ttu-id="b7817-183">Config</span><span class="sxs-lookup"><span data-stu-id="b7817-183">Config</span></span>                                |
| <span data-ttu-id="b7817-184">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="b7817-184">Web Config</span></span>                                   | `webconfig`       |              | <span data-ttu-id="b7817-185">Config</span><span class="sxs-lookup"><span data-stu-id="b7817-185">Config</span></span>                                |
| <span data-ttu-id="b7817-186">Файл решения</span><span class="sxs-lookup"><span data-stu-id="b7817-186">Solution File</span></span>                                | `sln`             |              | <span data-ttu-id="b7817-187">Решение</span><span class="sxs-lookup"><span data-stu-id="b7817-187">Solution</span></span>                              |

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="b7817-188">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b7817-188">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="b7817-189">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b7817-189">The command contains a default list of templates.</span></span> <span data-ttu-id="b7817-190">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b7817-190">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="b7817-191">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="b7817-191">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="b7817-192">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="b7817-192">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="b7817-193">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="b7817-193">Templates</span></span>                                    | <span data-ttu-id="b7817-194">Краткое имя</span><span class="sxs-lookup"><span data-stu-id="b7817-194">Short Name</span></span>      | <span data-ttu-id="b7817-195">Язык</span><span class="sxs-lookup"><span data-stu-id="b7817-195">Language</span></span>     | <span data-ttu-id="b7817-196">Tags</span><span class="sxs-lookup"><span data-stu-id="b7817-196">Tags</span></span>                                  |
|----------------------------------------------|-----------------|--------------|---------------------------------------|
| <span data-ttu-id="b7817-197">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="b7817-197">Console Application</span></span>                          | `console`       | <span data-ttu-id="b7817-198">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b7817-198">[C#], F#, VB</span></span> | <span data-ttu-id="b7817-199">Общее/консоль</span><span class="sxs-lookup"><span data-stu-id="b7817-199">Common/Console</span></span>                        |
| <span data-ttu-id="b7817-200">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="b7817-200">Class library</span></span>                                | `classlib`      | <span data-ttu-id="b7817-201">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b7817-201">[C#], F#, VB</span></span> | <span data-ttu-id="b7817-202">Общее/библиотека</span><span class="sxs-lookup"><span data-stu-id="b7817-202">Common/Library</span></span>                        |
| <span data-ttu-id="b7817-203">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="b7817-203">Unit Test Project</span></span>                            | `mstest`        | <span data-ttu-id="b7817-204">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b7817-204">[C#], F#, VB</span></span> | <span data-ttu-id="b7817-205">Тест/MSTest</span><span class="sxs-lookup"><span data-stu-id="b7817-205">Test/MSTest</span></span>                           |
| <span data-ttu-id="b7817-206">Тестовый проект xUnit</span><span class="sxs-lookup"><span data-stu-id="b7817-206">xUnit Test Project</span></span>                           | `xunit`         | <span data-ttu-id="b7817-207">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b7817-207">[C#], F#, VB</span></span> | <span data-ttu-id="b7817-208">Тест/xUnit</span><span class="sxs-lookup"><span data-stu-id="b7817-208">Test/xUnit</span></span>                            |
| <span data-ttu-id="b7817-209">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="b7817-209">Razor Page</span></span>                                   | `page`          | <span data-ttu-id="b7817-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7817-210">[C#]</span></span>         | <span data-ttu-id="b7817-211">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b7817-211">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="b7817-212">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="b7817-212">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="b7817-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7817-213">[C#]</span></span>         | <span data-ttu-id="b7817-214">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b7817-214">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="b7817-215">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="b7817-215">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="b7817-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7817-216">[C#]</span></span>         | <span data-ttu-id="b7817-217">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b7817-217">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="b7817-218">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7817-218">ASP.NET Core Empty</span></span>                           | `web`           | <span data-ttu-id="b7817-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b7817-219">[C#], F#</span></span>     | <span data-ttu-id="b7817-220">Веб/пусто</span><span class="sxs-lookup"><span data-stu-id="b7817-220">Web/Empty</span></span>                             |
| <span data-ttu-id="b7817-221">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="b7817-221">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="b7817-222">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b7817-222">[C#], F#</span></span>     | <span data-ttu-id="b7817-223">Веб/MVC</span><span class="sxs-lookup"><span data-stu-id="b7817-223">Web/MVC</span></span>                               |
| <span data-ttu-id="b7817-224">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7817-224">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="b7817-225">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7817-225">[C#]</span></span>         | <span data-ttu-id="b7817-226">Веб/MVC и Razor Pages</span><span class="sxs-lookup"><span data-stu-id="b7817-226">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="b7817-227">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="b7817-227">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="b7817-228">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7817-228">[C#]</span></span>         | <span data-ttu-id="b7817-229">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="b7817-229">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="b7817-230">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="b7817-230">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="b7817-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7817-231">[C#]</span></span>         | <span data-ttu-id="b7817-232">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="b7817-232">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="b7817-233">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="b7817-233">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="b7817-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7817-234">[C#]</span></span>         | <span data-ttu-id="b7817-235">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="b7817-235">Web/MVC/SPA</span></span>                           | 
| <span data-ttu-id="b7817-236">Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="b7817-236">Razor Class Library</span></span>                          | `razorclasslib` | <span data-ttu-id="b7817-237">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7817-237">[C#]</span></span>         | <span data-ttu-id="b7817-238">Веб/Razor/Библиотека/Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="b7817-238">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="b7817-239">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7817-239">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="b7817-240">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b7817-240">[C#], F#</span></span>     | <span data-ttu-id="b7817-241">Веб/веб-API</span><span class="sxs-lookup"><span data-stu-id="b7817-241">Web/WebAPI</span></span>                            |
| <span data-ttu-id="b7817-242">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="b7817-242">global.json file</span></span>                             | `globaljson`    |              | <span data-ttu-id="b7817-243">Config</span><span class="sxs-lookup"><span data-stu-id="b7817-243">Config</span></span>                                |
| <span data-ttu-id="b7817-244">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="b7817-244">NuGet Config</span></span>                                 | `nugetconfig`   |              | <span data-ttu-id="b7817-245">Config</span><span class="sxs-lookup"><span data-stu-id="b7817-245">Config</span></span>                                |
| <span data-ttu-id="b7817-246">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="b7817-246">Web Config</span></span>                                   | `webconfig`     |              | <span data-ttu-id="b7817-247">Config</span><span class="sxs-lookup"><span data-stu-id="b7817-247">Config</span></span>                                |
| <span data-ttu-id="b7817-248">Файл решения</span><span class="sxs-lookup"><span data-stu-id="b7817-248">Solution File</span></span>                                | `sln`           |              | <span data-ttu-id="b7817-249">Решение</span><span class="sxs-lookup"><span data-stu-id="b7817-249">Solution</span></span>                              |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="b7817-250">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b7817-250">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="b7817-251">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b7817-251">The command contains a default list of templates.</span></span> <span data-ttu-id="b7817-252">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b7817-252">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="b7817-253">В следующей таблице показаны шаблоны, которые устанавливаются с пакетом SDK для .NET Core 2.0.0.</span><span class="sxs-lookup"><span data-stu-id="b7817-253">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.0.</span></span> <span data-ttu-id="b7817-254">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="b7817-254">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="b7817-255">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="b7817-255">Templates</span></span>                                    | <span data-ttu-id="b7817-256">Краткое имя</span><span class="sxs-lookup"><span data-stu-id="b7817-256">Short Name</span></span>    | <span data-ttu-id="b7817-257">Язык</span><span class="sxs-lookup"><span data-stu-id="b7817-257">Language</span></span>     | <span data-ttu-id="b7817-258">Tags</span><span class="sxs-lookup"><span data-stu-id="b7817-258">Tags</span></span>                |
|----------------------------------------------|---------------|--------------|---------------------|
| <span data-ttu-id="b7817-259">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="b7817-259">Console Application</span></span>                          | `console`     | <span data-ttu-id="b7817-260">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b7817-260">[C#], F#, VB</span></span> | <span data-ttu-id="b7817-261">Общее/консоль</span><span class="sxs-lookup"><span data-stu-id="b7817-261">Common/Console</span></span>      |
| <span data-ttu-id="b7817-262">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="b7817-262">Class library</span></span>                                | `classlib`    | <span data-ttu-id="b7817-263">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b7817-263">[C#], F#, VB</span></span> | <span data-ttu-id="b7817-264">Общее/библиотека</span><span class="sxs-lookup"><span data-stu-id="b7817-264">Common/Library</span></span>      |
| <span data-ttu-id="b7817-265">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="b7817-265">Unit Test Project</span></span>                            | `mstest`      | <span data-ttu-id="b7817-266">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b7817-266">[C#], F#, VB</span></span> | <span data-ttu-id="b7817-267">Тест/MSTest</span><span class="sxs-lookup"><span data-stu-id="b7817-267">Test/MSTest</span></span>         |
| <span data-ttu-id="b7817-268">Тестовый проект xUnit</span><span class="sxs-lookup"><span data-stu-id="b7817-268">xUnit Test Project</span></span>                           | `xunit`       | <span data-ttu-id="b7817-269">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b7817-269">[C#], F#, VB</span></span> | <span data-ttu-id="b7817-270">Тест/xUnit</span><span class="sxs-lookup"><span data-stu-id="b7817-270">Test/xUnit</span></span>          |
| <span data-ttu-id="b7817-271">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7817-271">ASP.NET Core Empty</span></span>                           | `web`         | <span data-ttu-id="b7817-272">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b7817-272">[C#], F#</span></span>     | <span data-ttu-id="b7817-273">Веб/пусто</span><span class="sxs-lookup"><span data-stu-id="b7817-273">Web/Empty</span></span>           |
| <span data-ttu-id="b7817-274">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="b7817-274">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="b7817-275">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b7817-275">[C#], F#</span></span>     | <span data-ttu-id="b7817-276">Веб/MVC</span><span class="sxs-lookup"><span data-stu-id="b7817-276">Web/MVC</span></span>             |
| <span data-ttu-id="b7817-277">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7817-277">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="b7817-278">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7817-278">[C#]</span></span>         | <span data-ttu-id="b7817-279">Веб/MVC и Razor Pages</span><span class="sxs-lookup"><span data-stu-id="b7817-279">Web/MVC/Razor Pages</span></span> |
| <span data-ttu-id="b7817-280">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="b7817-280">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="b7817-281">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7817-281">[C#]</span></span>         | <span data-ttu-id="b7817-282">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="b7817-282">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="b7817-283">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="b7817-283">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="b7817-284">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7817-284">[C#]</span></span>         | <span data-ttu-id="b7817-285">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="b7817-285">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="b7817-286">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="b7817-286">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="b7817-287">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7817-287">[C#]</span></span>         | <span data-ttu-id="b7817-288">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="b7817-288">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="b7817-289">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7817-289">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="b7817-290">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b7817-290">[C#], F#</span></span>     | <span data-ttu-id="b7817-291">Веб/веб-API</span><span class="sxs-lookup"><span data-stu-id="b7817-291">Web/WebAPI</span></span>          |
| <span data-ttu-id="b7817-292">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="b7817-292">global.json file</span></span>                             | `globaljson`  |              | <span data-ttu-id="b7817-293">Config</span><span class="sxs-lookup"><span data-stu-id="b7817-293">Config</span></span>              |
| <span data-ttu-id="b7817-294">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="b7817-294">Nuget Config</span></span>                                 | `nugetconfig` |              | <span data-ttu-id="b7817-295">Config</span><span class="sxs-lookup"><span data-stu-id="b7817-295">Config</span></span>              |
| <span data-ttu-id="b7817-296">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="b7817-296">Web Config</span></span>                                   | `webconfig`   |              | <span data-ttu-id="b7817-297">Config</span><span class="sxs-lookup"><span data-stu-id="b7817-297">Config</span></span>              |
| <span data-ttu-id="b7817-298">Файл решения</span><span class="sxs-lookup"><span data-stu-id="b7817-298">Solution File</span></span>                                | `sln`         |              | <span data-ttu-id="b7817-299">Решение</span><span class="sxs-lookup"><span data-stu-id="b7817-299">Solution</span></span>            |
| <span data-ttu-id="b7817-300">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="b7817-300">Razor Page</span></span>                                   | `page`        |              | <span data-ttu-id="b7817-301">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b7817-301">Web/ASP.NET</span></span>         |
| <span data-ttu-id="b7817-302">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="b7817-302">MVC ViewImports</span></span>                              | `viewimports` |              | <span data-ttu-id="b7817-303">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b7817-303">Web/ASP.NET</span></span>         |
| <span data-ttu-id="b7817-304">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="b7817-304">MVC ViewStart</span></span>                                | `viewstart`   |              | <span data-ttu-id="b7817-305">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b7817-305">Web/ASP.NET</span></span>         |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b7817-306">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b7817-306">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="b7817-307">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b7817-307">The command contains a default list of templates.</span></span> <span data-ttu-id="b7817-308">Используйте `dotnet new -all`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b7817-308">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="b7817-309">В следующей таблице показаны шаблоны, которые устанавливаются с пакетом SDK для .NET Core 1.0.1.</span><span class="sxs-lookup"><span data-stu-id="b7817-309">The following table shows the templates that come pre-installed with the .NET Core SDK 1.0.1.</span></span> <span data-ttu-id="b7817-310">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="b7817-310">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="b7817-311">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="b7817-311">Templates</span></span>            | <span data-ttu-id="b7817-312">Краткое имя</span><span class="sxs-lookup"><span data-stu-id="b7817-312">Short Name</span></span>    | <span data-ttu-id="b7817-313">Язык</span><span class="sxs-lookup"><span data-stu-id="b7817-313">Language</span></span> | <span data-ttu-id="b7817-314">Tags</span><span class="sxs-lookup"><span data-stu-id="b7817-314">Tags</span></span>           |
|----------------------|---------------|----------|----------------|
| <span data-ttu-id="b7817-315">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="b7817-315">Console Application</span></span>  | `console`     | <span data-ttu-id="b7817-316">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b7817-316">[C#], F#</span></span> | <span data-ttu-id="b7817-317">Общее/консоль</span><span class="sxs-lookup"><span data-stu-id="b7817-317">Common/Console</span></span> |
| <span data-ttu-id="b7817-318">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="b7817-318">Class library</span></span>        | `classlib`    | <span data-ttu-id="b7817-319">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b7817-319">[C#], F#</span></span> | <span data-ttu-id="b7817-320">Общее/библиотека</span><span class="sxs-lookup"><span data-stu-id="b7817-320">Common/Library</span></span> |
| <span data-ttu-id="b7817-321">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="b7817-321">Unit Test Project</span></span>    | `mstest`      | <span data-ttu-id="b7817-322">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b7817-322">[C#], F#</span></span> | <span data-ttu-id="b7817-323">Тест/MSTest</span><span class="sxs-lookup"><span data-stu-id="b7817-323">Test/MSTest</span></span>    |
| <span data-ttu-id="b7817-324">Тестовый проект xUnit</span><span class="sxs-lookup"><span data-stu-id="b7817-324">xUnit Test Project</span></span>   | `xunit`       | <span data-ttu-id="b7817-325">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b7817-325">[C#], F#</span></span> | <span data-ttu-id="b7817-326">Тест/xUnit</span><span class="sxs-lookup"><span data-stu-id="b7817-326">Test/xUnit</span></span>     |
| <span data-ttu-id="b7817-327">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7817-327">ASP.NET Core Empty</span></span>   | `web`         | <span data-ttu-id="b7817-328">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7817-328">[C#]</span></span>     | <span data-ttu-id="b7817-329">Веб/пусто</span><span class="sxs-lookup"><span data-stu-id="b7817-329">Web/Empty</span></span>      |
| <span data-ttu-id="b7817-330">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7817-330">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="b7817-331">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b7817-331">[C#], F#</span></span> | <span data-ttu-id="b7817-332">Веб/MVC</span><span class="sxs-lookup"><span data-stu-id="b7817-332">Web/MVC</span></span>        |
| <span data-ttu-id="b7817-333">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7817-333">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="b7817-334">[C#]</span><span class="sxs-lookup"><span data-stu-id="b7817-334">[C#]</span></span>     | <span data-ttu-id="b7817-335">Веб/веб-API</span><span class="sxs-lookup"><span data-stu-id="b7817-335">Web/WebAPI</span></span>     |
| <span data-ttu-id="b7817-336">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="b7817-336">Nuget Config</span></span>         | `nugetconfig` |          | <span data-ttu-id="b7817-337">Config</span><span class="sxs-lookup"><span data-stu-id="b7817-337">Config</span></span>         |
| <span data-ttu-id="b7817-338">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="b7817-338">Web Config</span></span>           | `webconfig`   |          | <span data-ttu-id="b7817-339">Config</span><span class="sxs-lookup"><span data-stu-id="b7817-339">Config</span></span>         |
| <span data-ttu-id="b7817-340">Файл решения</span><span class="sxs-lookup"><span data-stu-id="b7817-340">Solution File</span></span>        | `sln`         |          | <span data-ttu-id="b7817-341">Решение</span><span class="sxs-lookup"><span data-stu-id="b7817-341">Solution</span></span>       |

---

## <a name="options"></a><span data-ttu-id="b7817-342">Параметры</span><span class="sxs-lookup"><span data-stu-id="b7817-342">Options</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="b7817-343">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="b7817-343">.NET Core 2.2</span></span>](#tab/netcore22)

`--dry-run`

<span data-ttu-id="b7817-344">Отображает сводку того, что произойдет, если выполнить команду и это приведет к созданию шаблона.</span><span class="sxs-lookup"><span data-stu-id="b7817-344">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span>

`--force`

<span data-ttu-id="b7817-345">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="b7817-345">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="b7817-346">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="b7817-346">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="b7817-347">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="b7817-347">Prints out help for the command.</span></span> <span data-ttu-id="b7817-348">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="b7817-348">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="b7817-349">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="b7817-349">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="b7817-350">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="b7817-350">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="b7817-351">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="b7817-351">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="b7817-352">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="b7817-352">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="b7817-353">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="b7817-353">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="b7817-354">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="b7817-354">Lists templates containing the specified name.</span></span> <span data-ttu-id="b7817-355">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="b7817-355">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="b7817-356">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-356">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="b7817-357">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="b7817-357">The language of the template to create.</span></span> <span data-ttu-id="b7817-358">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="b7817-358">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="b7817-359">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b7817-359">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="b7817-360">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="b7817-360">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="b7817-361">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="b7817-361">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="b7817-362">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b7817-362">The name for the created output.</span></span> <span data-ttu-id="b7817-363">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="b7817-363">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="b7817-364">Задает источник пакетов NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="b7817-364">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b7817-365">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="b7817-365">Location to place the generated output.</span></span> <span data-ttu-id="b7817-366">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="b7817-366">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="b7817-367">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="b7817-367">Filters templates based on available types.</span></span> <span data-ttu-id="b7817-368">Предопределенные значения: "project", "item" или "other".</span><span class="sxs-lookup"><span data-stu-id="b7817-368">Predefined values are "project", "item", or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="b7817-369">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="b7817-369">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="b7817-370">При исключении значения `<PATH|NUGET_ID>` отображаются все установленные пакеты шаблонов и связанные с ними шаблоны.</span><span class="sxs-lookup"><span data-stu-id="b7817-370">When excluding the `<PATH|NUGET_ID>` value, all currently installed template packs and their associated templates are displayed.</span></span>

> [!NOTE]
> <span data-ttu-id="b7817-371">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="b7817-371">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="b7817-372">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="b7817-372">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="b7817-373">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="b7817-373">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="b7817-374">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b7817-374">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="b7817-375">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="b7817-375">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="b7817-376">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="b7817-376">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="b7817-377">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="b7817-377">Prints out help for the command.</span></span> <span data-ttu-id="b7817-378">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="b7817-378">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="b7817-379">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="b7817-379">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="b7817-380">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="b7817-380">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="b7817-381">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="b7817-381">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="b7817-382">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="b7817-382">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="b7817-383">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="b7817-383">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="b7817-384">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="b7817-384">Lists templates containing the specified name.</span></span> <span data-ttu-id="b7817-385">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="b7817-385">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="b7817-386">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-386">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="b7817-387">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="b7817-387">The language of the template to create.</span></span> <span data-ttu-id="b7817-388">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="b7817-388">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="b7817-389">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b7817-389">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="b7817-390">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="b7817-390">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="b7817-391">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="b7817-391">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="b7817-392">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b7817-392">The name for the created output.</span></span> <span data-ttu-id="b7817-393">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="b7817-393">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="b7817-394">Задает источник пакетов NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="b7817-394">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b7817-395">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="b7817-395">Location to place the generated output.</span></span> <span data-ttu-id="b7817-396">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="b7817-396">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="b7817-397">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="b7817-397">Filters templates based on available types.</span></span> <span data-ttu-id="b7817-398">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="b7817-398">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="b7817-399">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="b7817-399">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="b7817-400">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="b7817-400">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="b7817-401">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="b7817-401">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="b7817-402">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="b7817-402">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="b7817-403">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b7817-403">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="b7817-404">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="b7817-404">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="b7817-405">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="b7817-405">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="b7817-406">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="b7817-406">Prints out help for the command.</span></span> <span data-ttu-id="b7817-407">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="b7817-407">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="b7817-408">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="b7817-408">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="b7817-409">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="b7817-409">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="b7817-410">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="b7817-410">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="b7817-411">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="b7817-411">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="b7817-412">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="b7817-412">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="b7817-413">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="b7817-413">Lists templates containing the specified name.</span></span> <span data-ttu-id="b7817-414">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="b7817-414">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="b7817-415">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-415">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="b7817-416">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="b7817-416">The language of the template to create.</span></span> <span data-ttu-id="b7817-417">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="b7817-417">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="b7817-418">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b7817-418">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="b7817-419">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="b7817-419">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="b7817-420">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="b7817-420">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="b7817-421">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b7817-421">The name for the created output.</span></span> <span data-ttu-id="b7817-422">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="b7817-422">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b7817-423">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="b7817-423">Location to place the generated output.</span></span> <span data-ttu-id="b7817-424">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="b7817-424">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="b7817-425">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="b7817-425">Filters templates based on available types.</span></span> <span data-ttu-id="b7817-426">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="b7817-426">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="b7817-427">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="b7817-427">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="b7817-428">Чтобы удалить шаблон, используя путь к исходному пакету `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="b7817-428">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="b7817-429">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="b7817-429">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="b7817-430">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="b7817-430">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="b7817-431">Если вам не удается определить аргумент `PATH` или `NUGET_ID`, необходимый для удаления шаблона, выполните команду `dotnet new --uninstall` без аргумента. В результате будут перечислены все установленные шаблоны и аргумент, необходимый для их удаления.</span><span class="sxs-lookup"><span data-stu-id="b7817-431">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b7817-432">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b7817-432">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="b7817-433">Показывает все шаблоны определенного типа проекта при запуске в контексте одной только команды `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="b7817-433">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="b7817-434">При запуске в контексте конкретного шаблона, например `dotnet new web -all`, `-all` интерпретируется как флаг принудительного создания.</span><span class="sxs-lookup"><span data-stu-id="b7817-434">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="b7817-435">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="b7817-435">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="b7817-436">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="b7817-436">Prints out help for the command.</span></span> <span data-ttu-id="b7817-437">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="b7817-437">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="b7817-438">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="b7817-438">Lists templates containing the specified name.</span></span> <span data-ttu-id="b7817-439">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="b7817-439">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="b7817-440">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-440">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="b7817-441">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="b7817-441">The language of the template to create.</span></span> <span data-ttu-id="b7817-442">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="b7817-442">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="b7817-443">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b7817-443">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="b7817-444">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="b7817-444">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="b7817-445">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="b7817-445">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="b7817-446">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b7817-446">The name for the created output.</span></span> <span data-ttu-id="b7817-447">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="b7817-447">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b7817-448">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="b7817-448">Location to place the generated output.</span></span> <span data-ttu-id="b7817-449">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="b7817-449">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="b7817-450">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="b7817-450">Template options</span></span>

<span data-ttu-id="b7817-451">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="b7817-451">Each project template may have additional options available.</span></span> <span data-ttu-id="b7817-452">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="b7817-452">The core templates have the following additional options:</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="b7817-453">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="b7817-453">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="b7817-454">**Консоль**</span><span class="sxs-lookup"><span data-stu-id="b7817-454">**console**</span></span>

<span data-ttu-id="b7817-455">`--langVersion <VERSION_NUMBER>` — задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-455">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="b7817-456">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="b7817-456">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="b7817-457">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="b7817-457">Not supported for F#.</span></span>

<span data-ttu-id="b7817-458">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b7817-458">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7817-459">**angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="b7817-459">**angular, react, reactredux**</span></span>

<span data-ttu-id="b7817-460">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="b7817-460">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="b7817-461">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b7817-461">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7817-462">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b7817-462">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="b7817-463">Этот параметр применяется, только если `IndividualAuth` или `OrganizationalAuth` не используются.</span><span class="sxs-lookup"><span data-stu-id="b7817-463">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="b7817-464">**razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="b7817-464">**razorclasslib**</span></span>

<span data-ttu-id="b7817-465">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b7817-465">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7817-466">**classlib**</span><span class="sxs-lookup"><span data-stu-id="b7817-466">**classlib**</span></span>

<span data-ttu-id="b7817-467">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="b7817-467">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b7817-468">Значения: `netcoreapp2.2` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="b7817-468">Values: `netcoreapp2.2` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="b7817-469">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="b7817-469">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="b7817-470">`--langVersion <VERSION_NUMBER>` — задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-470">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="b7817-471">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="b7817-471">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="b7817-472">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="b7817-472">Not supported for F#.</span></span>

<span data-ttu-id="b7817-473">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b7817-473">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7817-474">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="b7817-474">**mstest, xunit**</span></span>

<span data-ttu-id="b7817-475">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="b7817-475">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="b7817-476">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b7817-476">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7817-477">**nunit**</span><span class="sxs-lookup"><span data-stu-id="b7817-477">**nunit**</span></span>

<span data-ttu-id="b7817-478">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="b7817-478">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b7817-479">Значение по умолчанию — `netcoreapp2.1`.</span><span class="sxs-lookup"><span data-stu-id="b7817-479">The default value is `netcoreapp2.1`.</span></span>

<span data-ttu-id="b7817-480">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="b7817-480">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="b7817-481">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b7817-481">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7817-482">**page**</span><span class="sxs-lookup"><span data-stu-id="b7817-482">**page**</span></span>

<span data-ttu-id="b7817-483">`-na|--namespace <NAMESPACE_NAME>` — пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="b7817-483">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="b7817-484">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="b7817-484">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="b7817-485">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="b7817-485">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="b7817-486">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="b7817-486">**viewimports**</span></span>

<span data-ttu-id="b7817-487">`-na|--namespace <NAMESPACE_NAME>` — пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="b7817-487">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="b7817-488">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="b7817-488">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="b7817-489">**web**</span><span class="sxs-lookup"><span data-stu-id="b7817-489">**web**</span></span>

<span data-ttu-id="b7817-490">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="b7817-490">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="b7817-491">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b7817-491">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7817-492">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b7817-492">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="b7817-493">Этот параметр применяется, только если `IndividualAuth` или `OrganizationalAuth` не используются.</span><span class="sxs-lookup"><span data-stu-id="b7817-493">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="b7817-494">**mvc, webapp**</span><span class="sxs-lookup"><span data-stu-id="b7817-494">**mvc, webapp**</span></span>

<span data-ttu-id="b7817-495">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b7817-495">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="b7817-496">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="b7817-496">The possible values are:</span></span>

- <span data-ttu-id="b7817-497">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b7817-497">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="b7817-498">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="b7817-498">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="b7817-499">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="b7817-499">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="b7817-500">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="b7817-500">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="b7817-501">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="b7817-501">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="b7817-502">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="b7817-502">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="b7817-503">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="b7817-503">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b7817-504">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-504">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7817-505">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="b7817-505">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="b7817-506">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-506">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b7817-507">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-507">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7817-508">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-508">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="b7817-509">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-509">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7817-510">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-510">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="b7817-511">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-511">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7817-512">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="b7817-512">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b7817-513">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-513">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="b7817-514">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="b7817-514">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="b7817-515">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-515">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="b7817-516">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-516">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="b7817-517">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="b7817-517">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="b7817-518">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="b7817-518">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="b7817-519">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-519">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7817-520">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="b7817-520">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="b7817-521">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="b7817-521">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b7817-522">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-522">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b7817-523">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="b7817-523">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="b7817-524">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="b7817-524">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="b7817-525">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-525">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7817-526">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="b7817-526">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="b7817-527">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="b7817-527">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="b7817-528">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-528">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="b7817-529">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="b7817-529">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="b7817-530">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b7817-530">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="b7817-531">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="b7817-531">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="b7817-532">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="b7817-532">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="b7817-533">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="b7817-533">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b7817-534">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-534">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7817-535">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b7817-535">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7817-536">**webapi**</span><span class="sxs-lookup"><span data-stu-id="b7817-536">**webapi**</span></span>

<span data-ttu-id="b7817-537">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b7817-537">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="b7817-538">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="b7817-538">The possible values are:</span></span>

- <span data-ttu-id="b7817-539">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b7817-539">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="b7817-540">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="b7817-540">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="b7817-541">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="b7817-541">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="b7817-542">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="b7817-542">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="b7817-543">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="b7817-543">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b7817-544">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-544">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7817-545">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="b7817-545">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="b7817-546">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-546">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b7817-547">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-547">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7817-548">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="b7817-548">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b7817-549">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-549">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b7817-550">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="b7817-550">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="b7817-551">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-551">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="b7817-552">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-552">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="b7817-553">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="b7817-553">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="b7817-554">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="b7817-554">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="b7817-555">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-555">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7817-556">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="b7817-556">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="b7817-557">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="b7817-557">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b7817-558">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b7817-559">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="b7817-559">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="b7817-560">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="b7817-560">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="b7817-561">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-561">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="b7817-562">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="b7817-562">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="b7817-563">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b7817-563">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="b7817-564">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="b7817-564">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="b7817-565">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="b7817-565">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="b7817-566">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="b7817-566">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b7817-567">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-567">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7817-568">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b7817-568">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7817-569">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="b7817-569">**globaljson**</span></span>

<span data-ttu-id="b7817-570">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="b7817-570">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="b7817-571">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b7817-571">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="b7817-572">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="b7817-572">**console, angular, react, reactredux, razorclasslib**</span></span>

<span data-ttu-id="b7817-573">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b7817-573">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7817-574">**classlib**</span><span class="sxs-lookup"><span data-stu-id="b7817-574">**classlib**</span></span>

<span data-ttu-id="b7817-575">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="b7817-575">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b7817-576">Значения: `netcoreapp2.1` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="b7817-576">Values: `netcoreapp2.1` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="b7817-577">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="b7817-577">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="b7817-578">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b7817-578">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7817-579">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="b7817-579">**mstest, xunit**</span></span>

<span data-ttu-id="b7817-580">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="b7817-580">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="b7817-581">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b7817-581">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7817-582">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="b7817-582">**globaljson**</span></span>

<span data-ttu-id="b7817-583">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="b7817-583">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="b7817-584">**web**</span><span class="sxs-lookup"><span data-stu-id="b7817-584">**web**</span></span>

<span data-ttu-id="b7817-585">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="b7817-585">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="b7817-586">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b7817-586">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7817-587">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b7817-587">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="b7817-588">Этот параметр применяется, только если `IndividualAuth` или `OrganizationalAuth` не используются.</span><span class="sxs-lookup"><span data-stu-id="b7817-588">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="b7817-589">**webapi**</span><span class="sxs-lookup"><span data-stu-id="b7817-589">**webapi**</span></span>

<span data-ttu-id="b7817-590">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b7817-590">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="b7817-591">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="b7817-591">The possible values are:</span></span>

- <span data-ttu-id="b7817-592">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b7817-592">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="b7817-593">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="b7817-593">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="b7817-594">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="b7817-594">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="b7817-595">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="b7817-595">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="b7817-596">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="b7817-596">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b7817-597">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-597">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7817-598">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="b7817-598">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="b7817-599">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-599">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b7817-600">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-600">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7817-601">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="b7817-601">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b7817-602">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-602">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b7817-603">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="b7817-603">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="b7817-604">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-604">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="b7817-605">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-605">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="b7817-606">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="b7817-606">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="b7817-607">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="b7817-607">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="b7817-608">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-608">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7817-609">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="b7817-609">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="b7817-610">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="b7817-610">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b7817-611">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-611">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b7817-612">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="b7817-612">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="b7817-613">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="b7817-613">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="b7817-614">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-614">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="b7817-615">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="b7817-615">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="b7817-616">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="b7817-616">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b7817-617">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-617">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7817-618">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b7817-618">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7817-619">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b7817-619">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="b7817-620">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="b7817-620">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="b7817-621">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="b7817-621">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="b7817-622">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="b7817-622">**mvc, razor**</span></span>

<span data-ttu-id="b7817-623">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b7817-623">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="b7817-624">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="b7817-624">The possible values are:</span></span>

- <span data-ttu-id="b7817-625">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b7817-625">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="b7817-626">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="b7817-626">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="b7817-627">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="b7817-627">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="b7817-628">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="b7817-628">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="b7817-629">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="b7817-629">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="b7817-630">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="b7817-630">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="b7817-631">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="b7817-631">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b7817-632">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-632">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7817-633">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="b7817-633">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="b7817-634">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-634">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b7817-635">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-635">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7817-636">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-636">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="b7817-637">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-637">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7817-638">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-638">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="b7817-639">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-639">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7817-640">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="b7817-640">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b7817-641">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-641">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="b7817-642">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="b7817-642">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="b7817-643">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-643">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="b7817-644">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-644">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="b7817-645">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="b7817-645">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="b7817-646">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="b7817-646">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="b7817-647">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-647">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7817-648">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="b7817-648">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="b7817-649">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="b7817-649">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b7817-650">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-650">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b7817-651">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="b7817-651">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="b7817-652">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="b7817-652">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="b7817-653">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-653">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7817-654">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="b7817-654">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="b7817-655">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="b7817-655">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="b7817-656">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-656">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="b7817-657">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="b7817-657">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="b7817-658">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="b7817-658">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="b7817-659">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="b7817-659">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b7817-660">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-660">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7817-661">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b7817-661">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7817-662">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b7817-662">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="b7817-663">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="b7817-663">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="b7817-664">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="b7817-664">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="b7817-665">**page**</span><span class="sxs-lookup"><span data-stu-id="b7817-665">**page**</span></span>

<span data-ttu-id="b7817-666">`-na|--namespace <NAMESPACE_NAME>` — пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="b7817-666">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="b7817-667">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="b7817-667">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="b7817-668">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="b7817-668">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="b7817-669">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="b7817-669">**viewimports**</span></span>

<span data-ttu-id="b7817-670">`-na|--namespace <NAMESPACE_NAME>` — пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="b7817-670">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="b7817-671">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="b7817-671">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="b7817-672">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b7817-672">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="b7817-673">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="b7817-673">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="b7817-674">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b7817-674">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7817-675">**classlib**</span><span class="sxs-lookup"><span data-stu-id="b7817-675">**classlib**</span></span>

<span data-ttu-id="b7817-676">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="b7817-676">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b7817-677">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="b7817-677">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="b7817-678">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="b7817-678">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="b7817-679">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b7817-679">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7817-680">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="b7817-680">**mstest, xunit**</span></span>

<span data-ttu-id="b7817-681">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="b7817-681">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="b7817-682">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b7817-682">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7817-683">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="b7817-683">**globaljson**</span></span>

<span data-ttu-id="b7817-684">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="b7817-684">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="b7817-685">**web**</span><span class="sxs-lookup"><span data-stu-id="b7817-685">**web**</span></span>

<span data-ttu-id="b7817-686">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="b7817-686">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="b7817-687">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b7817-687">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7817-688">**webapi**</span><span class="sxs-lookup"><span data-stu-id="b7817-688">**webapi**</span></span>

<span data-ttu-id="b7817-689">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b7817-689">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="b7817-690">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="b7817-690">The possible values are:</span></span>

- <span data-ttu-id="b7817-691">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b7817-691">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="b7817-692">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="b7817-692">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="b7817-693">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="b7817-693">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="b7817-694">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="b7817-694">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="b7817-695">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="b7817-695">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b7817-696">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-696">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7817-697">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="b7817-697">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="b7817-698">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-698">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b7817-699">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-699">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7817-700">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="b7817-700">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b7817-701">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-701">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b7817-702">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="b7817-702">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="b7817-703">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-703">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="b7817-704">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-704">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="b7817-705">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="b7817-705">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="b7817-706">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="b7817-706">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="b7817-707">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-707">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7817-708">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="b7817-708">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="b7817-709">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="b7817-709">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b7817-710">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-710">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b7817-711">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="b7817-711">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="b7817-712">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="b7817-712">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="b7817-713">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-713">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="b7817-714">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="b7817-714">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="b7817-715">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="b7817-715">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b7817-716">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-716">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7817-717">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b7817-717">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7817-718">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="b7817-718">**mvc, razor**</span></span>

<span data-ttu-id="b7817-719">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b7817-719">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="b7817-720">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="b7817-720">The possible values are:</span></span>

- <span data-ttu-id="b7817-721">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b7817-721">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="b7817-722">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="b7817-722">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="b7817-723">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="b7817-723">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="b7817-724">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="b7817-724">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="b7817-725">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="b7817-725">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="b7817-726">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="b7817-726">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="b7817-727">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="b7817-727">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b7817-728">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-728">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7817-729">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="b7817-729">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="b7817-730">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-730">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b7817-731">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-731">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7817-732">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-732">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="b7817-733">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-733">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7817-734">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-734">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="b7817-735">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-735">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7817-736">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="b7817-736">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b7817-737">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-737">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="b7817-738">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="b7817-738">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="b7817-739">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="b7817-739">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="b7817-740">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-740">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="b7817-741">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="b7817-741">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="b7817-742">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="b7817-742">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="b7817-743">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-743">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7817-744">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="b7817-744">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="b7817-745">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="b7817-745">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b7817-746">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-746">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b7817-747">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="b7817-747">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="b7817-748">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="b7817-748">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="b7817-749">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-749">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b7817-750">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="b7817-750">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="b7817-751">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="b7817-751">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="b7817-752">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b7817-752">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="b7817-753">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="b7817-753">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="b7817-754">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="b7817-754">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="b7817-755">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="b7817-755">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b7817-756">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b7817-756">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b7817-757">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="b7817-757">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b7817-758">**page**</span><span class="sxs-lookup"><span data-stu-id="b7817-758">**page**</span></span>

<span data-ttu-id="b7817-759">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="b7817-759">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="b7817-760">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="b7817-760">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="b7817-761">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="b7817-761">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="b7817-762">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="b7817-762">**viewimports**</span></span>

<span data-ttu-id="b7817-763">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="b7817-763">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="b7817-764">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="b7817-764">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b7817-765">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b7817-765">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="b7817-766">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="b7817-766">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="b7817-767">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="b7817-767">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b7817-768">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="b7817-768">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="b7817-769">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="b7817-769">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="b7817-770">**classlib**</span><span class="sxs-lookup"><span data-stu-id="b7817-770">**classlib**</span></span>

<span data-ttu-id="b7817-771">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="b7817-771">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b7817-772">Значения: `netcoreapp1.0`, `netcoreapp1.1` или с `netstandard1.0` по `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="b7817-772">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="b7817-773">Значение по умолчанию — `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="b7817-773">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="b7817-774">**mvc**</span><span class="sxs-lookup"><span data-stu-id="b7817-774">**mvc**</span></span>

<span data-ttu-id="b7817-775">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="b7817-775">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b7817-776">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="b7817-776">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="b7817-777">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="b7817-777">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="b7817-778">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b7817-778">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="b7817-779">Значения: `None` или `Individual`.</span><span class="sxs-lookup"><span data-stu-id="b7817-779">Values: `None` or `Individual`.</span></span> <span data-ttu-id="b7817-780">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="b7817-780">The default value is `None`.</span></span>

<span data-ttu-id="b7817-781">`-uld|--use-local-db` — указывает, следует ли использовать LocalDB вместо SQLite.</span><span class="sxs-lookup"><span data-stu-id="b7817-781">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="b7817-782">Значения: `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="b7817-782">Values: `true` or `false`.</span></span> <span data-ttu-id="b7817-783">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="b7817-783">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="b7817-784">Примеры</span><span class="sxs-lookup"><span data-stu-id="b7817-784">Examples</span></span>

<span data-ttu-id="b7817-785">Создайте проект консольного приложения на C#, указав имя шаблона:</span><span class="sxs-lookup"><span data-stu-id="b7817-785">Create a C# console application project by specifying the template name:</span></span>

`dotnet new "Console Application"`

<span data-ttu-id="b7817-786">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="b7817-786">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="b7817-787">Создание проекта библиотеки классов .NET Standard в указанном каталоге (доступно только при использовании пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="b7817-787">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="b7817-788">Создайте новый проект MVC ASP.NET Core C# в текущем каталоге без проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="b7817-788">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="b7817-789">Создайте новый проект xUnit:</span><span class="sxs-lookup"><span data-stu-id="b7817-789">Create a new xUnit project:</span></span>

`dotnet new xunit`

<span data-ttu-id="b7817-790">Перечислите все шаблоны, доступные для MVC:</span><span class="sxs-lookup"><span data-stu-id="b7817-790">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="b7817-791">Список всех шаблонов, соответствующих подстроке *we*.</span><span class="sxs-lookup"><span data-stu-id="b7817-791">List all templates matching the *we* substring.</span></span> <span data-ttu-id="b7817-792">Точное совпадение не найдено, поэтому сравнение подстрок выполняется по короткому имени и столбцам имен.</span><span class="sxs-lookup"><span data-stu-id="b7817-792">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

`dotnet new we -l`

<span data-ttu-id="b7817-793">Попытайтесь вызвать шаблон, соответствующий *ng*.</span><span class="sxs-lookup"><span data-stu-id="b7817-793">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="b7817-794">Если точное совпадение не найдено, выведите шаблоны с частичным совпадением.</span><span class="sxs-lookup"><span data-stu-id="b7817-794">If a single match can't be determined, list the templates that are partial matches.</span></span>

`dotnet new ng`

<span data-ttu-id="b7817-795">Установите версию 2.0 шаблонов одностраничного приложения для ASP.NET Core (параметр команды доступен в .NET Core SDK 1.1 и более поздних версиях):</span><span class="sxs-lookup"><span data-stu-id="b7817-795">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="b7817-796">Создайте *global.json* в текущем каталоге, указав версию пакета SDK 2.0.0 (доступно только для пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="b7817-796">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="b7817-797">См. также</span><span class="sxs-lookup"><span data-stu-id="b7817-797">See also</span></span>

- [<span data-ttu-id="b7817-798">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="b7817-798">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="b7817-799">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="b7817-799">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="b7817-800">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="b7817-800">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="b7817-801">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="b7817-801">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
