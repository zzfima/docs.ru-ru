---
title: Команда dotnet new
description: Команда dotnet new создает проекты .NET Core на основе указанного шаблона.
ms.date: 05/06/2019
ms.openlocfilehash: b61b5fd53f470c30b636026fa19ebfad834d6354
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117667"
---
# <a name="dotnet-new"></a><span data-ttu-id="cf88a-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="cf88a-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="cf88a-104">name</span><span class="sxs-lookup"><span data-stu-id="cf88a-104">Name</span></span>

<span data-ttu-id="cf88a-105">`dotnet new` - создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="cf88a-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cf88a-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cf88a-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="cf88a-107">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="cf88a-107">.NET Core 2.2</span></span>](#tab/netcore22)

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="cf88a-108">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cf88a-108">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="cf88a-109">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="cf88a-109">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="cf88a-110">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cf88a-110">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="cf88a-111">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="cf88a-111">Description</span></span>

<span data-ttu-id="cf88a-112">Команда `dotnet new` предоставляет удобный способ инициализации проекта .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cf88a-112">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="cf88a-113">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="cf88a-113">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="cf88a-114">Аргументы</span><span class="sxs-lookup"><span data-stu-id="cf88a-114">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="cf88a-115">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="cf88a-115">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="cf88a-116">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="cf88a-116">Each template might have specific options you can pass.</span></span> <span data-ttu-id="cf88a-117">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="cf88a-117">For more information, see [Template options](#template-options).</span></span>

<span data-ttu-id="cf88a-118">Если значение `TEMPLATE` не в точности совпадает с текстом в столбце **Шаблоны** или **Короткое имя**, для этих двух столбцов выполняется поиск совпадений в подстроках.</span><span class="sxs-lookup"><span data-stu-id="cf88a-118">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column, a substring match is performed on those two columns.</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="cf88a-119">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="cf88a-119">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="cf88a-120">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cf88a-120">The command contains a default list of templates.</span></span> <span data-ttu-id="cf88a-121">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="cf88a-121">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="cf88a-122">В следующей таблице показаны шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.2.100.</span><span class="sxs-lookup"><span data-stu-id="cf88a-122">The following table shows the templates that come pre-installed with the .NET Core SDK 2.2.100.</span></span> <span data-ttu-id="cf88a-123">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="cf88a-123">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="cf88a-124">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="cf88a-124">Templates</span></span>                                    | <span data-ttu-id="cf88a-125">Краткое имя</span><span class="sxs-lookup"><span data-stu-id="cf88a-125">Short Name</span></span>        | <span data-ttu-id="cf88a-126">Язык</span><span class="sxs-lookup"><span data-stu-id="cf88a-126">Language</span></span>     | <span data-ttu-id="cf88a-127">Tags</span><span class="sxs-lookup"><span data-stu-id="cf88a-127">Tags</span></span>                                  |
|----------------------------------------------|-------------------|--------------|---------------------------------------|
| <span data-ttu-id="cf88a-128">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="cf88a-128">Console Application</span></span>                          | `console`         | <span data-ttu-id="cf88a-129">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cf88a-129">[C#], F#, VB</span></span> | <span data-ttu-id="cf88a-130">Общее/консоль</span><span class="sxs-lookup"><span data-stu-id="cf88a-130">Common/Console</span></span>                        |
| <span data-ttu-id="cf88a-131">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="cf88a-131">Class library</span></span>                                | `classlib`        | <span data-ttu-id="cf88a-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cf88a-132">[C#], F#, VB</span></span> | <span data-ttu-id="cf88a-133">Общее/библиотека</span><span class="sxs-lookup"><span data-stu-id="cf88a-133">Common/Library</span></span>                        |
| <span data-ttu-id="cf88a-134">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="cf88a-134">Unit Test Project</span></span>                            | `mstest`          | <span data-ttu-id="cf88a-135">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cf88a-135">[C#], F#, VB</span></span> | <span data-ttu-id="cf88a-136">Тест/MSTest</span><span class="sxs-lookup"><span data-stu-id="cf88a-136">Test/MSTest</span></span>                           |
| <span data-ttu-id="cf88a-137">Тестовый проект NUnit 3</span><span class="sxs-lookup"><span data-stu-id="cf88a-137">NUnit 3 Test Project</span></span>                         | `nunit`           | <span data-ttu-id="cf88a-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cf88a-138">[C#], F#, VB</span></span> | <span data-ttu-id="cf88a-139">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="cf88a-139">Test/NUnit</span></span>                            |
| <span data-ttu-id="cf88a-140">Элемент теста NUnit 3</span><span class="sxs-lookup"><span data-stu-id="cf88a-140">NUnit 3 Test Item</span></span>                            | `nunit-test`      | <span data-ttu-id="cf88a-141">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cf88a-141">[C#], F#, VB</span></span> | <span data-ttu-id="cf88a-142">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="cf88a-142">Test/NUnit</span></span>                            |
| <span data-ttu-id="cf88a-143">Тестовый проект xUnit</span><span class="sxs-lookup"><span data-stu-id="cf88a-143">xUnit Test Project</span></span>                           | `xunit`           | <span data-ttu-id="cf88a-144">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cf88a-144">[C#], F#, VB</span></span> | <span data-ttu-id="cf88a-145">Тест/xUnit</span><span class="sxs-lookup"><span data-stu-id="cf88a-145">Test/xUnit</span></span>                            |
| <span data-ttu-id="cf88a-146">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="cf88a-146">Razor Page</span></span>                                   | `page`            | <span data-ttu-id="cf88a-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="cf88a-147">[C#]</span></span>         | <span data-ttu-id="cf88a-148">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cf88a-148">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="cf88a-149">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="cf88a-149">MVC ViewImports</span></span>                              | `viewimports`     | <span data-ttu-id="cf88a-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="cf88a-150">[C#]</span></span>         | <span data-ttu-id="cf88a-151">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cf88a-151">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="cf88a-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="cf88a-152">MVC ViewStart</span></span>                                | `viewstart`       | <span data-ttu-id="cf88a-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="cf88a-153">[C#]</span></span>         | <span data-ttu-id="cf88a-154">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cf88a-154">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="cf88a-155">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cf88a-155">ASP.NET Core Empty</span></span>                           | `web`             | <span data-ttu-id="cf88a-156">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cf88a-156">[C#], F#</span></span>     | <span data-ttu-id="cf88a-157">Веб/пусто</span><span class="sxs-lookup"><span data-stu-id="cf88a-157">Web/Empty</span></span>                             |
| <span data-ttu-id="cf88a-158">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="cf88a-158">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`             | <span data-ttu-id="cf88a-159">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cf88a-159">[C#], F#</span></span>     | <span data-ttu-id="cf88a-160">Веб/MVC</span><span class="sxs-lookup"><span data-stu-id="cf88a-160">Web/MVC</span></span>                               |
| <span data-ttu-id="cf88a-161">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cf88a-161">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="cf88a-162">`webapp`, `razor`</span><span class="sxs-lookup"><span data-stu-id="cf88a-162">`webapp`, `razor`</span></span> | <span data-ttu-id="cf88a-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="cf88a-163">[C#]</span></span>         | <span data-ttu-id="cf88a-164">Веб/MVC и Razor Pages</span><span class="sxs-lookup"><span data-stu-id="cf88a-164">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="cf88a-165">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="cf88a-165">ASP.NET Core with Angular</span></span>                    | `angular`         | <span data-ttu-id="cf88a-166">[C#]</span><span class="sxs-lookup"><span data-stu-id="cf88a-166">[C#]</span></span>         | <span data-ttu-id="cf88a-167">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="cf88a-167">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="cf88a-168">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="cf88a-168">ASP.NET Core with React.js</span></span>                   | `react`           | <span data-ttu-id="cf88a-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="cf88a-169">[C#]</span></span>         | <span data-ttu-id="cf88a-170">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="cf88a-170">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="cf88a-171">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="cf88a-171">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`      | <span data-ttu-id="cf88a-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="cf88a-172">[C#]</span></span>         | <span data-ttu-id="cf88a-173">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="cf88a-173">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="cf88a-174">Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="cf88a-174">Razor Class Library</span></span>                          | `razorclasslib`   | <span data-ttu-id="cf88a-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="cf88a-175">[C#]</span></span>         | <span data-ttu-id="cf88a-176">Веб/Razor/Библиотека/Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="cf88a-176">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="cf88a-177">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cf88a-177">ASP.NET Core Web API</span></span>                         | `webapi`          | <span data-ttu-id="cf88a-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cf88a-178">[C#], F#</span></span>     | <span data-ttu-id="cf88a-179">Веб/веб-API</span><span class="sxs-lookup"><span data-stu-id="cf88a-179">Web/WebAPI</span></span>                            |
| <span data-ttu-id="cf88a-180">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="cf88a-180">global.json file</span></span>                             | `globaljson`      |              | <span data-ttu-id="cf88a-181">Config</span><span class="sxs-lookup"><span data-stu-id="cf88a-181">Config</span></span>                                |
| <span data-ttu-id="cf88a-182">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="cf88a-182">NuGet Config</span></span>                                 | `nugetconfig`     |              | <span data-ttu-id="cf88a-183">Config</span><span class="sxs-lookup"><span data-stu-id="cf88a-183">Config</span></span>                                |
| <span data-ttu-id="cf88a-184">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="cf88a-184">Web Config</span></span>                                   | `webconfig`       |              | <span data-ttu-id="cf88a-185">Config</span><span class="sxs-lookup"><span data-stu-id="cf88a-185">Config</span></span>                                |
| <span data-ttu-id="cf88a-186">Файл решения</span><span class="sxs-lookup"><span data-stu-id="cf88a-186">Solution File</span></span>                                | `sln`             |              | <span data-ttu-id="cf88a-187">Решение</span><span class="sxs-lookup"><span data-stu-id="cf88a-187">Solution</span></span>                              |

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="cf88a-188">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cf88a-188">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="cf88a-189">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cf88a-189">The command contains a default list of templates.</span></span> <span data-ttu-id="cf88a-190">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="cf88a-190">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="cf88a-191">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="cf88a-191">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="cf88a-192">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="cf88a-192">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="cf88a-193">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="cf88a-193">Templates</span></span>                                    | <span data-ttu-id="cf88a-194">Краткое имя</span><span class="sxs-lookup"><span data-stu-id="cf88a-194">Short Name</span></span>      | <span data-ttu-id="cf88a-195">Язык</span><span class="sxs-lookup"><span data-stu-id="cf88a-195">Language</span></span>     | <span data-ttu-id="cf88a-196">Tags</span><span class="sxs-lookup"><span data-stu-id="cf88a-196">Tags</span></span>                                  |
|----------------------------------------------|-----------------|--------------|---------------------------------------|
| <span data-ttu-id="cf88a-197">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="cf88a-197">Console Application</span></span>                          | `console`       | <span data-ttu-id="cf88a-198">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cf88a-198">[C#], F#, VB</span></span> | <span data-ttu-id="cf88a-199">Общее/консоль</span><span class="sxs-lookup"><span data-stu-id="cf88a-199">Common/Console</span></span>                        |
| <span data-ttu-id="cf88a-200">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="cf88a-200">Class library</span></span>                                | `classlib`      | <span data-ttu-id="cf88a-201">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cf88a-201">[C#], F#, VB</span></span> | <span data-ttu-id="cf88a-202">Общее/библиотека</span><span class="sxs-lookup"><span data-stu-id="cf88a-202">Common/Library</span></span>                        |
| <span data-ttu-id="cf88a-203">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="cf88a-203">Unit Test Project</span></span>                            | `mstest`        | <span data-ttu-id="cf88a-204">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cf88a-204">[C#], F#, VB</span></span> | <span data-ttu-id="cf88a-205">Тест/MSTest</span><span class="sxs-lookup"><span data-stu-id="cf88a-205">Test/MSTest</span></span>                           |
| <span data-ttu-id="cf88a-206">Тестовый проект xUnit</span><span class="sxs-lookup"><span data-stu-id="cf88a-206">xUnit Test Project</span></span>                           | `xunit`         | <span data-ttu-id="cf88a-207">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cf88a-207">[C#], F#, VB</span></span> | <span data-ttu-id="cf88a-208">Тест/xUnit</span><span class="sxs-lookup"><span data-stu-id="cf88a-208">Test/xUnit</span></span>                            |
| <span data-ttu-id="cf88a-209">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="cf88a-209">Razor Page</span></span>                                   | `page`          | <span data-ttu-id="cf88a-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="cf88a-210">[C#]</span></span>         | <span data-ttu-id="cf88a-211">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cf88a-211">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="cf88a-212">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="cf88a-212">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="cf88a-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="cf88a-213">[C#]</span></span>         | <span data-ttu-id="cf88a-214">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cf88a-214">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="cf88a-215">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="cf88a-215">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="cf88a-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="cf88a-216">[C#]</span></span>         | <span data-ttu-id="cf88a-217">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cf88a-217">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="cf88a-218">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cf88a-218">ASP.NET Core Empty</span></span>                           | `web`           | <span data-ttu-id="cf88a-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cf88a-219">[C#], F#</span></span>     | <span data-ttu-id="cf88a-220">Веб/пусто</span><span class="sxs-lookup"><span data-stu-id="cf88a-220">Web/Empty</span></span>                             |
| <span data-ttu-id="cf88a-221">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="cf88a-221">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="cf88a-222">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cf88a-222">[C#], F#</span></span>     | <span data-ttu-id="cf88a-223">Веб/MVC</span><span class="sxs-lookup"><span data-stu-id="cf88a-223">Web/MVC</span></span>                               |
| <span data-ttu-id="cf88a-224">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cf88a-224">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="cf88a-225">[C#]</span><span class="sxs-lookup"><span data-stu-id="cf88a-225">[C#]</span></span>         | <span data-ttu-id="cf88a-226">Веб/MVC и Razor Pages</span><span class="sxs-lookup"><span data-stu-id="cf88a-226">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="cf88a-227">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="cf88a-227">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="cf88a-228">[C#]</span><span class="sxs-lookup"><span data-stu-id="cf88a-228">[C#]</span></span>         | <span data-ttu-id="cf88a-229">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="cf88a-229">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="cf88a-230">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="cf88a-230">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="cf88a-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="cf88a-231">[C#]</span></span>         | <span data-ttu-id="cf88a-232">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="cf88a-232">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="cf88a-233">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="cf88a-233">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="cf88a-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="cf88a-234">[C#]</span></span>         | <span data-ttu-id="cf88a-235">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="cf88a-235">Web/MVC/SPA</span></span>                           | 
| <span data-ttu-id="cf88a-236">Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="cf88a-236">Razor Class Library</span></span>                          | `razorclasslib` | <span data-ttu-id="cf88a-237">[C#]</span><span class="sxs-lookup"><span data-stu-id="cf88a-237">[C#]</span></span>         | <span data-ttu-id="cf88a-238">Веб/Razor/Библиотека/Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="cf88a-238">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="cf88a-239">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cf88a-239">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="cf88a-240">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cf88a-240">[C#], F#</span></span>     | <span data-ttu-id="cf88a-241">Веб/веб-API</span><span class="sxs-lookup"><span data-stu-id="cf88a-241">Web/WebAPI</span></span>                            |
| <span data-ttu-id="cf88a-242">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="cf88a-242">global.json file</span></span>                             | `globaljson`    |              | <span data-ttu-id="cf88a-243">Config</span><span class="sxs-lookup"><span data-stu-id="cf88a-243">Config</span></span>                                |
| <span data-ttu-id="cf88a-244">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="cf88a-244">NuGet Config</span></span>                                 | `nugetconfig`   |              | <span data-ttu-id="cf88a-245">Config</span><span class="sxs-lookup"><span data-stu-id="cf88a-245">Config</span></span>                                |
| <span data-ttu-id="cf88a-246">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="cf88a-246">Web Config</span></span>                                   | `webconfig`     |              | <span data-ttu-id="cf88a-247">Config</span><span class="sxs-lookup"><span data-stu-id="cf88a-247">Config</span></span>                                |
| <span data-ttu-id="cf88a-248">Файл решения</span><span class="sxs-lookup"><span data-stu-id="cf88a-248">Solution File</span></span>                                | `sln`           |              | <span data-ttu-id="cf88a-249">Решение</span><span class="sxs-lookup"><span data-stu-id="cf88a-249">Solution</span></span>                              |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="cf88a-250">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="cf88a-250">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="cf88a-251">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cf88a-251">The command contains a default list of templates.</span></span> <span data-ttu-id="cf88a-252">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="cf88a-252">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="cf88a-253">В следующей таблице показаны шаблоны, которые устанавливаются с пакетом SDK для .NET Core 2.0.0.</span><span class="sxs-lookup"><span data-stu-id="cf88a-253">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.0.</span></span> <span data-ttu-id="cf88a-254">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="cf88a-254">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="cf88a-255">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="cf88a-255">Templates</span></span>                                    | <span data-ttu-id="cf88a-256">Краткое имя</span><span class="sxs-lookup"><span data-stu-id="cf88a-256">Short Name</span></span>    | <span data-ttu-id="cf88a-257">Язык</span><span class="sxs-lookup"><span data-stu-id="cf88a-257">Language</span></span>     | <span data-ttu-id="cf88a-258">Tags</span><span class="sxs-lookup"><span data-stu-id="cf88a-258">Tags</span></span>                |
|----------------------------------------------|---------------|--------------|---------------------|
| <span data-ttu-id="cf88a-259">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="cf88a-259">Console Application</span></span>                          | `console`     | <span data-ttu-id="cf88a-260">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cf88a-260">[C#], F#, VB</span></span> | <span data-ttu-id="cf88a-261">Общее/консоль</span><span class="sxs-lookup"><span data-stu-id="cf88a-261">Common/Console</span></span>      |
| <span data-ttu-id="cf88a-262">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="cf88a-262">Class library</span></span>                                | `classlib`    | <span data-ttu-id="cf88a-263">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cf88a-263">[C#], F#, VB</span></span> | <span data-ttu-id="cf88a-264">Общее/библиотека</span><span class="sxs-lookup"><span data-stu-id="cf88a-264">Common/Library</span></span>      |
| <span data-ttu-id="cf88a-265">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="cf88a-265">Unit Test Project</span></span>                            | `mstest`      | <span data-ttu-id="cf88a-266">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cf88a-266">[C#], F#, VB</span></span> | <span data-ttu-id="cf88a-267">Тест/MSTest</span><span class="sxs-lookup"><span data-stu-id="cf88a-267">Test/MSTest</span></span>         |
| <span data-ttu-id="cf88a-268">Тестовый проект xUnit</span><span class="sxs-lookup"><span data-stu-id="cf88a-268">xUnit Test Project</span></span>                           | `xunit`       | <span data-ttu-id="cf88a-269">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cf88a-269">[C#], F#, VB</span></span> | <span data-ttu-id="cf88a-270">Тест/xUnit</span><span class="sxs-lookup"><span data-stu-id="cf88a-270">Test/xUnit</span></span>          |
| <span data-ttu-id="cf88a-271">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cf88a-271">ASP.NET Core Empty</span></span>                           | `web`         | <span data-ttu-id="cf88a-272">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cf88a-272">[C#], F#</span></span>     | <span data-ttu-id="cf88a-273">Веб/пусто</span><span class="sxs-lookup"><span data-stu-id="cf88a-273">Web/Empty</span></span>           |
| <span data-ttu-id="cf88a-274">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="cf88a-274">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="cf88a-275">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cf88a-275">[C#], F#</span></span>     | <span data-ttu-id="cf88a-276">Веб/MVC</span><span class="sxs-lookup"><span data-stu-id="cf88a-276">Web/MVC</span></span>             |
| <span data-ttu-id="cf88a-277">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cf88a-277">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="cf88a-278">[C#]</span><span class="sxs-lookup"><span data-stu-id="cf88a-278">[C#]</span></span>         | <span data-ttu-id="cf88a-279">Веб/MVC и Razor Pages</span><span class="sxs-lookup"><span data-stu-id="cf88a-279">Web/MVC/Razor Pages</span></span> |
| <span data-ttu-id="cf88a-280">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="cf88a-280">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="cf88a-281">[C#]</span><span class="sxs-lookup"><span data-stu-id="cf88a-281">[C#]</span></span>         | <span data-ttu-id="cf88a-282">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="cf88a-282">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="cf88a-283">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="cf88a-283">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="cf88a-284">[C#]</span><span class="sxs-lookup"><span data-stu-id="cf88a-284">[C#]</span></span>         | <span data-ttu-id="cf88a-285">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="cf88a-285">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="cf88a-286">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="cf88a-286">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="cf88a-287">[C#]</span><span class="sxs-lookup"><span data-stu-id="cf88a-287">[C#]</span></span>         | <span data-ttu-id="cf88a-288">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="cf88a-288">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="cf88a-289">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cf88a-289">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="cf88a-290">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cf88a-290">[C#], F#</span></span>     | <span data-ttu-id="cf88a-291">Веб/веб-API</span><span class="sxs-lookup"><span data-stu-id="cf88a-291">Web/WebAPI</span></span>          |
| <span data-ttu-id="cf88a-292">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="cf88a-292">global.json file</span></span>                             | `globaljson`  |              | <span data-ttu-id="cf88a-293">Config</span><span class="sxs-lookup"><span data-stu-id="cf88a-293">Config</span></span>              |
| <span data-ttu-id="cf88a-294">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="cf88a-294">Nuget Config</span></span>                                 | `nugetconfig` |              | <span data-ttu-id="cf88a-295">Config</span><span class="sxs-lookup"><span data-stu-id="cf88a-295">Config</span></span>              |
| <span data-ttu-id="cf88a-296">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="cf88a-296">Web Config</span></span>                                   | `webconfig`   |              | <span data-ttu-id="cf88a-297">Config</span><span class="sxs-lookup"><span data-stu-id="cf88a-297">Config</span></span>              |
| <span data-ttu-id="cf88a-298">Файл решения</span><span class="sxs-lookup"><span data-stu-id="cf88a-298">Solution File</span></span>                                | `sln`         |              | <span data-ttu-id="cf88a-299">Решение</span><span class="sxs-lookup"><span data-stu-id="cf88a-299">Solution</span></span>            |
| <span data-ttu-id="cf88a-300">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="cf88a-300">Razor Page</span></span>                                   | `page`        |              | <span data-ttu-id="cf88a-301">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cf88a-301">Web/ASP.NET</span></span>         |
| <span data-ttu-id="cf88a-302">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="cf88a-302">MVC ViewImports</span></span>                              | `viewimports` |              | <span data-ttu-id="cf88a-303">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cf88a-303">Web/ASP.NET</span></span>         |
| <span data-ttu-id="cf88a-304">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="cf88a-304">MVC ViewStart</span></span>                                | `viewstart`   |              | <span data-ttu-id="cf88a-305">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cf88a-305">Web/ASP.NET</span></span>         |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="cf88a-306">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cf88a-306">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="cf88a-307">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cf88a-307">The command contains a default list of templates.</span></span> <span data-ttu-id="cf88a-308">Используйте `dotnet new -all`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="cf88a-308">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="cf88a-309">В следующей таблице показаны шаблоны, которые устанавливаются с пакетом SDK для .NET Core 1.0.1.</span><span class="sxs-lookup"><span data-stu-id="cf88a-309">The following table shows the templates that come pre-installed with the .NET Core SDK 1.0.1.</span></span> <span data-ttu-id="cf88a-310">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="cf88a-310">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="cf88a-311">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="cf88a-311">Templates</span></span>            | <span data-ttu-id="cf88a-312">Краткое имя</span><span class="sxs-lookup"><span data-stu-id="cf88a-312">Short Name</span></span>    | <span data-ttu-id="cf88a-313">Язык</span><span class="sxs-lookup"><span data-stu-id="cf88a-313">Language</span></span> | <span data-ttu-id="cf88a-314">Tags</span><span class="sxs-lookup"><span data-stu-id="cf88a-314">Tags</span></span>           |
|----------------------|---------------|----------|----------------|
| <span data-ttu-id="cf88a-315">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="cf88a-315">Console Application</span></span>  | `console`     | <span data-ttu-id="cf88a-316">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cf88a-316">[C#], F#</span></span> | <span data-ttu-id="cf88a-317">Общее/консоль</span><span class="sxs-lookup"><span data-stu-id="cf88a-317">Common/Console</span></span> |
| <span data-ttu-id="cf88a-318">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="cf88a-318">Class library</span></span>        | `classlib`    | <span data-ttu-id="cf88a-319">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cf88a-319">[C#], F#</span></span> | <span data-ttu-id="cf88a-320">Общее/библиотека</span><span class="sxs-lookup"><span data-stu-id="cf88a-320">Common/Library</span></span> |
| <span data-ttu-id="cf88a-321">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="cf88a-321">Unit Test Project</span></span>    | `mstest`      | <span data-ttu-id="cf88a-322">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cf88a-322">[C#], F#</span></span> | <span data-ttu-id="cf88a-323">Тест/MSTest</span><span class="sxs-lookup"><span data-stu-id="cf88a-323">Test/MSTest</span></span>    |
| <span data-ttu-id="cf88a-324">Тестовый проект xUnit</span><span class="sxs-lookup"><span data-stu-id="cf88a-324">xUnit Test Project</span></span>   | `xunit`       | <span data-ttu-id="cf88a-325">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cf88a-325">[C#], F#</span></span> | <span data-ttu-id="cf88a-326">Тест/xUnit</span><span class="sxs-lookup"><span data-stu-id="cf88a-326">Test/xUnit</span></span>     |
| <span data-ttu-id="cf88a-327">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cf88a-327">ASP.NET Core Empty</span></span>   | `web`         | <span data-ttu-id="cf88a-328">[C#]</span><span class="sxs-lookup"><span data-stu-id="cf88a-328">[C#]</span></span>     | <span data-ttu-id="cf88a-329">Веб/пусто</span><span class="sxs-lookup"><span data-stu-id="cf88a-329">Web/Empty</span></span>      |
| <span data-ttu-id="cf88a-330">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cf88a-330">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="cf88a-331">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cf88a-331">[C#], F#</span></span> | <span data-ttu-id="cf88a-332">Веб/MVC</span><span class="sxs-lookup"><span data-stu-id="cf88a-332">Web/MVC</span></span>        |
| <span data-ttu-id="cf88a-333">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cf88a-333">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="cf88a-334">[C#]</span><span class="sxs-lookup"><span data-stu-id="cf88a-334">[C#]</span></span>     | <span data-ttu-id="cf88a-335">Веб/веб-API</span><span class="sxs-lookup"><span data-stu-id="cf88a-335">Web/WebAPI</span></span>     |
| <span data-ttu-id="cf88a-336">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="cf88a-336">Nuget Config</span></span>         | `nugetconfig` |          | <span data-ttu-id="cf88a-337">Config</span><span class="sxs-lookup"><span data-stu-id="cf88a-337">Config</span></span>         |
| <span data-ttu-id="cf88a-338">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="cf88a-338">Web Config</span></span>           | `webconfig`   |          | <span data-ttu-id="cf88a-339">Config</span><span class="sxs-lookup"><span data-stu-id="cf88a-339">Config</span></span>         |
| <span data-ttu-id="cf88a-340">Файл решения</span><span class="sxs-lookup"><span data-stu-id="cf88a-340">Solution File</span></span>        | `sln`         |          | <span data-ttu-id="cf88a-341">Решение</span><span class="sxs-lookup"><span data-stu-id="cf88a-341">Solution</span></span>       |

---

## <a name="options"></a><span data-ttu-id="cf88a-342">Параметры</span><span class="sxs-lookup"><span data-stu-id="cf88a-342">Options</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="cf88a-343">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="cf88a-343">.NET Core 2.2</span></span>](#tab/netcore22)

`--dry-run`

<span data-ttu-id="cf88a-344">Отображает сводку того, что произойдет, если выполнить команду и это приведет к созданию шаблона.</span><span class="sxs-lookup"><span data-stu-id="cf88a-344">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span>

`--force`

<span data-ttu-id="cf88a-345">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="cf88a-345">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="cf88a-346">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="cf88a-346">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="cf88a-347">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="cf88a-347">Prints out help for the command.</span></span> <span data-ttu-id="cf88a-348">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-348">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="cf88a-349">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-349">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="cf88a-350">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-350">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="cf88a-351">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="cf88a-351">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="cf88a-352">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="cf88a-352">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="cf88a-353">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="cf88a-353">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="cf88a-354">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="cf88a-354">Lists templates containing the specified name.</span></span> <span data-ttu-id="cf88a-355">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="cf88a-355">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="cf88a-356">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-356">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="cf88a-357">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="cf88a-357">The language of the template to create.</span></span> <span data-ttu-id="cf88a-358">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="cf88a-358">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="cf88a-359">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="cf88a-359">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="cf88a-360">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="cf88a-360">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="cf88a-361">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-361">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="cf88a-362">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="cf88a-362">The name for the created output.</span></span> <span data-ttu-id="cf88a-363">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="cf88a-363">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="cf88a-364">Задает источник пакетов NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="cf88a-364">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="cf88a-365">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="cf88a-365">Location to place the generated output.</span></span> <span data-ttu-id="cf88a-366">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="cf88a-366">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="cf88a-367">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="cf88a-367">Filters templates based on available types.</span></span> <span data-ttu-id="cf88a-368">Предопределенные значения: "project", "item" или "other".</span><span class="sxs-lookup"><span data-stu-id="cf88a-368">Predefined values are "project", "item", or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="cf88a-369">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-369">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="cf88a-370">При исключении значения `<PATH|NUGET_ID>` отображаются все установленные пакеты шаблонов и связанные с ними шаблоны.</span><span class="sxs-lookup"><span data-stu-id="cf88a-370">When excluding the `<PATH|NUGET_ID>` value, all currently installed template packs and their associated templates are displayed.</span></span>

> [!NOTE]
> <span data-ttu-id="cf88a-371">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="cf88a-371">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="cf88a-372">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="cf88a-372">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="cf88a-373">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="cf88a-373">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="cf88a-374">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cf88a-374">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="cf88a-375">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="cf88a-375">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="cf88a-376">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="cf88a-376">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="cf88a-377">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="cf88a-377">Prints out help for the command.</span></span> <span data-ttu-id="cf88a-378">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-378">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="cf88a-379">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-379">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="cf88a-380">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-380">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="cf88a-381">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="cf88a-381">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="cf88a-382">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="cf88a-382">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="cf88a-383">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="cf88a-383">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="cf88a-384">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="cf88a-384">Lists templates containing the specified name.</span></span> <span data-ttu-id="cf88a-385">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="cf88a-385">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="cf88a-386">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-386">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="cf88a-387">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="cf88a-387">The language of the template to create.</span></span> <span data-ttu-id="cf88a-388">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="cf88a-388">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="cf88a-389">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="cf88a-389">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="cf88a-390">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="cf88a-390">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="cf88a-391">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-391">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="cf88a-392">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="cf88a-392">The name for the created output.</span></span> <span data-ttu-id="cf88a-393">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="cf88a-393">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="cf88a-394">Задает источник пакетов NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="cf88a-394">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="cf88a-395">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="cf88a-395">Location to place the generated output.</span></span> <span data-ttu-id="cf88a-396">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="cf88a-396">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="cf88a-397">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="cf88a-397">Filters templates based on available types.</span></span> <span data-ttu-id="cf88a-398">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="cf88a-398">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="cf88a-399">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-399">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="cf88a-400">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="cf88a-400">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="cf88a-401">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="cf88a-401">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="cf88a-402">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="cf88a-402">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="cf88a-403">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="cf88a-403">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="cf88a-404">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="cf88a-404">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="cf88a-405">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="cf88a-405">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="cf88a-406">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="cf88a-406">Prints out help for the command.</span></span> <span data-ttu-id="cf88a-407">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-407">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="cf88a-408">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-408">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="cf88a-409">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-409">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="cf88a-410">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="cf88a-410">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="cf88a-411">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="cf88a-411">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="cf88a-412">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="cf88a-412">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="cf88a-413">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="cf88a-413">Lists templates containing the specified name.</span></span> <span data-ttu-id="cf88a-414">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="cf88a-414">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="cf88a-415">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-415">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="cf88a-416">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="cf88a-416">The language of the template to create.</span></span> <span data-ttu-id="cf88a-417">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="cf88a-417">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="cf88a-418">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="cf88a-418">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="cf88a-419">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="cf88a-419">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="cf88a-420">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-420">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="cf88a-421">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="cf88a-421">The name for the created output.</span></span> <span data-ttu-id="cf88a-422">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="cf88a-422">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="cf88a-423">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="cf88a-423">Location to place the generated output.</span></span> <span data-ttu-id="cf88a-424">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="cf88a-424">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="cf88a-425">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="cf88a-425">Filters templates based on available types.</span></span> <span data-ttu-id="cf88a-426">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="cf88a-426">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="cf88a-427">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-427">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="cf88a-428">Чтобы удалить шаблон, используя путь к исходному пакету `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="cf88a-428">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="cf88a-429">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="cf88a-429">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="cf88a-430">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="cf88a-430">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="cf88a-431">Если вам не удается определить аргумент `PATH` или `NUGET_ID`, необходимый для удаления шаблона, выполните команду `dotnet new --uninstall` без аргумента. В результате будут перечислены все установленные шаблоны и аргумент, необходимый для их удаления.</span><span class="sxs-lookup"><span data-stu-id="cf88a-431">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="cf88a-432">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cf88a-432">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="cf88a-433">Показывает все шаблоны определенного типа проекта при запуске в контексте одной только команды `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-433">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="cf88a-434">При запуске в контексте конкретного шаблона, например `dotnet new web -all`, `-all` интерпретируется как флаг принудительного создания.</span><span class="sxs-lookup"><span data-stu-id="cf88a-434">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="cf88a-435">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="cf88a-435">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="cf88a-436">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="cf88a-436">Prints out help for the command.</span></span> <span data-ttu-id="cf88a-437">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-437">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="cf88a-438">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="cf88a-438">Lists templates containing the specified name.</span></span> <span data-ttu-id="cf88a-439">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="cf88a-439">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="cf88a-440">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-440">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="cf88a-441">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="cf88a-441">The language of the template to create.</span></span> <span data-ttu-id="cf88a-442">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="cf88a-442">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="cf88a-443">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="cf88a-443">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="cf88a-444">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="cf88a-444">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="cf88a-445">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-445">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="cf88a-446">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="cf88a-446">The name for the created output.</span></span> <span data-ttu-id="cf88a-447">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="cf88a-447">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="cf88a-448">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="cf88a-448">Location to place the generated output.</span></span> <span data-ttu-id="cf88a-449">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="cf88a-449">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="cf88a-450">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="cf88a-450">Template options</span></span>

<span data-ttu-id="cf88a-451">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="cf88a-451">Each project template may have additional options available.</span></span> <span data-ttu-id="cf88a-452">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="cf88a-452">The core templates have the following additional options:</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="cf88a-453">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="cf88a-453">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="cf88a-454">**Консоль**</span><span class="sxs-lookup"><span data-stu-id="cf88a-454">**console**</span></span>

<span data-ttu-id="cf88a-455">`--langVersion <VERSION_NUMBER>` — задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-455">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="cf88a-456">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="cf88a-456">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="cf88a-457">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="cf88a-457">Not supported for F#.</span></span>

<span data-ttu-id="cf88a-458">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="cf88a-458">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cf88a-459">**angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="cf88a-459">**angular, react, reactredux**</span></span>

<span data-ttu-id="cf88a-460">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="cf88a-460">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="cf88a-461">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="cf88a-461">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cf88a-462">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cf88a-462">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="cf88a-463">Этот параметр применяется, только если `IndividualAuth` или `OrganizationalAuth` не используются.</span><span class="sxs-lookup"><span data-stu-id="cf88a-463">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="cf88a-464">**razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="cf88a-464">**razorclasslib**</span></span>

<span data-ttu-id="cf88a-465">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="cf88a-465">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cf88a-466">**classlib**</span><span class="sxs-lookup"><span data-stu-id="cf88a-466">**classlib**</span></span>

<span data-ttu-id="cf88a-467">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="cf88a-467">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="cf88a-468">Значения: `netcoreapp2.2` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="cf88a-468">Values: `netcoreapp2.2` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="cf88a-469">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-469">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="cf88a-470">`--langVersion <VERSION_NUMBER>` — задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-470">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="cf88a-471">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="cf88a-471">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="cf88a-472">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="cf88a-472">Not supported for F#.</span></span>

<span data-ttu-id="cf88a-473">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="cf88a-473">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cf88a-474">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="cf88a-474">**mstest, xunit**</span></span>

<span data-ttu-id="cf88a-475">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="cf88a-475">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="cf88a-476">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="cf88a-476">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cf88a-477">**nunit**</span><span class="sxs-lookup"><span data-stu-id="cf88a-477">**nunit**</span></span>

<span data-ttu-id="cf88a-478">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="cf88a-478">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="cf88a-479">Значение по умолчанию — `netcoreapp2.1`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-479">The default value is `netcoreapp2.1`.</span></span>

<span data-ttu-id="cf88a-480">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="cf88a-480">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="cf88a-481">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="cf88a-481">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cf88a-482">**page**</span><span class="sxs-lookup"><span data-stu-id="cf88a-482">**page**</span></span>

<span data-ttu-id="cf88a-483">`-na|--namespace <NAMESPACE_NAME>` — пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="cf88a-483">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="cf88a-484">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-484">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="cf88a-485">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="cf88a-485">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="cf88a-486">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="cf88a-486">**viewimports**</span></span>

<span data-ttu-id="cf88a-487">`-na|--namespace <NAMESPACE_NAME>` — пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="cf88a-487">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="cf88a-488">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-488">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="cf88a-489">**web**</span><span class="sxs-lookup"><span data-stu-id="cf88a-489">**web**</span></span>

<span data-ttu-id="cf88a-490">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="cf88a-490">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="cf88a-491">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="cf88a-491">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cf88a-492">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cf88a-492">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="cf88a-493">Этот параметр применяется, только если `IndividualAuth` или `OrganizationalAuth` не используются.</span><span class="sxs-lookup"><span data-stu-id="cf88a-493">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="cf88a-494">**mvc, webapp**</span><span class="sxs-lookup"><span data-stu-id="cf88a-494">**mvc, webapp**</span></span>

<span data-ttu-id="cf88a-495">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="cf88a-495">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="cf88a-496">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="cf88a-496">The possible values are:</span></span>

- <span data-ttu-id="cf88a-497">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="cf88a-497">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="cf88a-498">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="cf88a-498">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="cf88a-499">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="cf88a-499">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="cf88a-500">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="cf88a-500">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="cf88a-501">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="cf88a-501">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="cf88a-502">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="cf88a-502">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="cf88a-503">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="cf88a-503">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="cf88a-504">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-504">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="cf88a-505">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-505">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="cf88a-506">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-506">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="cf88a-507">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-507">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cf88a-508">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-508">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="cf88a-509">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-509">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cf88a-510">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-510">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="cf88a-511">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-511">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cf88a-512">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="cf88a-512">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="cf88a-513">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-513">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="cf88a-514">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-514">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="cf88a-515">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-515">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="cf88a-516">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-516">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="cf88a-517">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-517">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="cf88a-518">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="cf88a-518">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="cf88a-519">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-519">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="cf88a-520">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-520">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="cf88a-521">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="cf88a-521">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="cf88a-522">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-522">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="cf88a-523">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-523">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="cf88a-524">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="cf88a-524">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="cf88a-525">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-525">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="cf88a-526">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-526">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="cf88a-527">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="cf88a-527">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="cf88a-528">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-528">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="cf88a-529">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="cf88a-529">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="cf88a-530">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cf88a-530">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="cf88a-531">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-531">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="cf88a-532">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="cf88a-532">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="cf88a-533">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="cf88a-533">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="cf88a-534">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-534">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cf88a-535">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="cf88a-535">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cf88a-536">**webapi**</span><span class="sxs-lookup"><span data-stu-id="cf88a-536">**webapi**</span></span>

<span data-ttu-id="cf88a-537">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="cf88a-537">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="cf88a-538">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="cf88a-538">The possible values are:</span></span>

- <span data-ttu-id="cf88a-539">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="cf88a-539">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="cf88a-540">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="cf88a-540">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="cf88a-541">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="cf88a-541">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="cf88a-542">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="cf88a-542">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="cf88a-543">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="cf88a-543">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="cf88a-544">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-544">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="cf88a-545">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-545">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="cf88a-546">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-546">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="cf88a-547">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-547">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cf88a-548">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="cf88a-548">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="cf88a-549">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-549">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="cf88a-550">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-550">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="cf88a-551">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-551">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="cf88a-552">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-552">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="cf88a-553">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-553">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="cf88a-554">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="cf88a-554">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="cf88a-555">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-555">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="cf88a-556">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-556">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="cf88a-557">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="cf88a-557">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="cf88a-558">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="cf88a-559">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-559">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="cf88a-560">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="cf88a-560">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="cf88a-561">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-561">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="cf88a-562">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="cf88a-562">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="cf88a-563">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cf88a-563">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="cf88a-564">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-564">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="cf88a-565">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="cf88a-565">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="cf88a-566">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="cf88a-566">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="cf88a-567">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-567">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cf88a-568">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="cf88a-568">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cf88a-569">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="cf88a-569">**globaljson**</span></span>

<span data-ttu-id="cf88a-570">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="cf88a-570">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="cf88a-571">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cf88a-571">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="cf88a-572">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="cf88a-572">**console, angular, react, reactredux, razorclasslib**</span></span>

<span data-ttu-id="cf88a-573">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="cf88a-573">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cf88a-574">**classlib**</span><span class="sxs-lookup"><span data-stu-id="cf88a-574">**classlib**</span></span>

<span data-ttu-id="cf88a-575">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="cf88a-575">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="cf88a-576">Значения: `netcoreapp2.1` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="cf88a-576">Values: `netcoreapp2.1` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="cf88a-577">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-577">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="cf88a-578">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="cf88a-578">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cf88a-579">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="cf88a-579">**mstest, xunit**</span></span>

<span data-ttu-id="cf88a-580">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="cf88a-580">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="cf88a-581">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="cf88a-581">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cf88a-582">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="cf88a-582">**globaljson**</span></span>

<span data-ttu-id="cf88a-583">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="cf88a-583">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="cf88a-584">**web**</span><span class="sxs-lookup"><span data-stu-id="cf88a-584">**web**</span></span>

<span data-ttu-id="cf88a-585">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="cf88a-585">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="cf88a-586">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="cf88a-586">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cf88a-587">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cf88a-587">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="cf88a-588">Этот параметр применяется, только если `IndividualAuth` или `OrganizationalAuth` не используются.</span><span class="sxs-lookup"><span data-stu-id="cf88a-588">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="cf88a-589">**webapi**</span><span class="sxs-lookup"><span data-stu-id="cf88a-589">**webapi**</span></span>

<span data-ttu-id="cf88a-590">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="cf88a-590">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="cf88a-591">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="cf88a-591">The possible values are:</span></span>

- <span data-ttu-id="cf88a-592">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="cf88a-592">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="cf88a-593">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="cf88a-593">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="cf88a-594">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="cf88a-594">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="cf88a-595">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="cf88a-595">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="cf88a-596">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="cf88a-596">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="cf88a-597">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-597">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="cf88a-598">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-598">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="cf88a-599">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-599">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="cf88a-600">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-600">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cf88a-601">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="cf88a-601">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="cf88a-602">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-602">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="cf88a-603">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-603">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="cf88a-604">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-604">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="cf88a-605">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-605">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="cf88a-606">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-606">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="cf88a-607">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="cf88a-607">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="cf88a-608">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-608">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="cf88a-609">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-609">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="cf88a-610">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="cf88a-610">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="cf88a-611">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-611">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="cf88a-612">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-612">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="cf88a-613">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="cf88a-613">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="cf88a-614">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-614">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="cf88a-615">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="cf88a-615">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="cf88a-616">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="cf88a-616">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="cf88a-617">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-617">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cf88a-618">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="cf88a-618">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cf88a-619">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cf88a-619">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="cf88a-620">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-620">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="cf88a-621">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="cf88a-621">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="cf88a-622">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="cf88a-622">**mvc, razor**</span></span>

<span data-ttu-id="cf88a-623">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="cf88a-623">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="cf88a-624">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="cf88a-624">The possible values are:</span></span>

- <span data-ttu-id="cf88a-625">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="cf88a-625">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="cf88a-626">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="cf88a-626">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="cf88a-627">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="cf88a-627">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="cf88a-628">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="cf88a-628">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="cf88a-629">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="cf88a-629">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="cf88a-630">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="cf88a-630">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="cf88a-631">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="cf88a-631">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="cf88a-632">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-632">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="cf88a-633">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-633">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="cf88a-634">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-634">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="cf88a-635">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-635">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cf88a-636">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-636">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="cf88a-637">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-637">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cf88a-638">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-638">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="cf88a-639">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-639">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cf88a-640">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="cf88a-640">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="cf88a-641">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-641">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="cf88a-642">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-642">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="cf88a-643">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-643">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="cf88a-644">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-644">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="cf88a-645">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-645">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="cf88a-646">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="cf88a-646">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="cf88a-647">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-647">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="cf88a-648">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-648">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="cf88a-649">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="cf88a-649">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="cf88a-650">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-650">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="cf88a-651">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-651">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="cf88a-652">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="cf88a-652">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="cf88a-653">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-653">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="cf88a-654">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-654">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="cf88a-655">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="cf88a-655">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="cf88a-656">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-656">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="cf88a-657">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="cf88a-657">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="cf88a-658">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="cf88a-658">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="cf88a-659">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="cf88a-659">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="cf88a-660">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-660">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cf88a-661">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="cf88a-661">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cf88a-662">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cf88a-662">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="cf88a-663">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-663">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="cf88a-664">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="cf88a-664">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="cf88a-665">**page**</span><span class="sxs-lookup"><span data-stu-id="cf88a-665">**page**</span></span>

<span data-ttu-id="cf88a-666">`-na|--namespace <NAMESPACE_NAME>` — пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="cf88a-666">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="cf88a-667">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-667">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="cf88a-668">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="cf88a-668">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="cf88a-669">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="cf88a-669">**viewimports**</span></span>

<span data-ttu-id="cf88a-670">`-na|--namespace <NAMESPACE_NAME>` — пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="cf88a-670">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="cf88a-671">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-671">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="cf88a-672">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="cf88a-672">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="cf88a-673">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="cf88a-673">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="cf88a-674">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="cf88a-674">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cf88a-675">**classlib**</span><span class="sxs-lookup"><span data-stu-id="cf88a-675">**classlib**</span></span>

<span data-ttu-id="cf88a-676">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="cf88a-676">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="cf88a-677">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="cf88a-677">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="cf88a-678">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-678">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="cf88a-679">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="cf88a-679">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cf88a-680">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="cf88a-680">**mstest, xunit**</span></span>

<span data-ttu-id="cf88a-681">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="cf88a-681">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="cf88a-682">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="cf88a-682">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cf88a-683">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="cf88a-683">**globaljson**</span></span>

<span data-ttu-id="cf88a-684">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="cf88a-684">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="cf88a-685">**web**</span><span class="sxs-lookup"><span data-stu-id="cf88a-685">**web**</span></span>

<span data-ttu-id="cf88a-686">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="cf88a-686">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="cf88a-687">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="cf88a-687">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cf88a-688">**webapi**</span><span class="sxs-lookup"><span data-stu-id="cf88a-688">**webapi**</span></span>

<span data-ttu-id="cf88a-689">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="cf88a-689">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="cf88a-690">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="cf88a-690">The possible values are:</span></span>

- <span data-ttu-id="cf88a-691">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="cf88a-691">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="cf88a-692">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="cf88a-692">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="cf88a-693">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="cf88a-693">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="cf88a-694">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="cf88a-694">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="cf88a-695">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="cf88a-695">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="cf88a-696">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-696">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="cf88a-697">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-697">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="cf88a-698">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-698">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="cf88a-699">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-699">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cf88a-700">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="cf88a-700">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="cf88a-701">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-701">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="cf88a-702">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-702">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="cf88a-703">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-703">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="cf88a-704">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-704">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="cf88a-705">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-705">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="cf88a-706">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="cf88a-706">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="cf88a-707">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-707">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="cf88a-708">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-708">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="cf88a-709">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="cf88a-709">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="cf88a-710">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-710">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="cf88a-711">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-711">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="cf88a-712">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="cf88a-712">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="cf88a-713">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-713">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="cf88a-714">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="cf88a-714">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="cf88a-715">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="cf88a-715">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="cf88a-716">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-716">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cf88a-717">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="cf88a-717">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cf88a-718">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="cf88a-718">**mvc, razor**</span></span>

<span data-ttu-id="cf88a-719">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="cf88a-719">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="cf88a-720">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="cf88a-720">The possible values are:</span></span>

- <span data-ttu-id="cf88a-721">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="cf88a-721">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="cf88a-722">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="cf88a-722">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="cf88a-723">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="cf88a-723">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="cf88a-724">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="cf88a-724">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="cf88a-725">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="cf88a-725">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="cf88a-726">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="cf88a-726">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="cf88a-727">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="cf88a-727">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="cf88a-728">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-728">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="cf88a-729">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-729">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="cf88a-730">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-730">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="cf88a-731">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-731">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cf88a-732">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-732">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="cf88a-733">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-733">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cf88a-734">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-734">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="cf88a-735">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-735">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cf88a-736">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="cf88a-736">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="cf88a-737">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-737">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="cf88a-738">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-738">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="cf88a-739">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="cf88a-739">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="cf88a-740">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-740">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="cf88a-741">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-741">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="cf88a-742">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="cf88a-742">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="cf88a-743">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-743">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="cf88a-744">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-744">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="cf88a-745">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="cf88a-745">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="cf88a-746">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-746">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="cf88a-747">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-747">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="cf88a-748">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="cf88a-748">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="cf88a-749">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-749">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="cf88a-750">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-750">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="cf88a-751">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="cf88a-751">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="cf88a-752">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-752">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="cf88a-753">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="cf88a-753">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="cf88a-754">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="cf88a-754">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="cf88a-755">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="cf88a-755">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="cf88a-756">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-756">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cf88a-757">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="cf88a-757">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cf88a-758">**page**</span><span class="sxs-lookup"><span data-stu-id="cf88a-758">**page**</span></span>

<span data-ttu-id="cf88a-759">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="cf88a-759">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="cf88a-760">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-760">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="cf88a-761">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="cf88a-761">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="cf88a-762">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="cf88a-762">**viewimports**</span></span>

<span data-ttu-id="cf88a-763">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="cf88a-763">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="cf88a-764">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-764">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="cf88a-765">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cf88a-765">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="cf88a-766">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="cf88a-766">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="cf88a-767">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="cf88a-767">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="cf88a-768">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-768">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="cf88a-769">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-769">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="cf88a-770">**classlib**</span><span class="sxs-lookup"><span data-stu-id="cf88a-770">**classlib**</span></span>

<span data-ttu-id="cf88a-771">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="cf88a-771">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="cf88a-772">Значения: `netcoreapp1.0`, `netcoreapp1.1` или с `netstandard1.0` по `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-772">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="cf88a-773">Значение по умолчанию — `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-773">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="cf88a-774">**mvc**</span><span class="sxs-lookup"><span data-stu-id="cf88a-774">**mvc**</span></span>

<span data-ttu-id="cf88a-775">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="cf88a-775">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="cf88a-776">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-776">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="cf88a-777">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-777">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="cf88a-778">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="cf88a-778">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="cf88a-779">Значения: `None` или `Individual`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-779">Values: `None` or `Individual`.</span></span> <span data-ttu-id="cf88a-780">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-780">The default value is `None`.</span></span>

<span data-ttu-id="cf88a-781">`-uld|--use-local-db` — указывает, следует ли использовать LocalDB вместо SQLite.</span><span class="sxs-lookup"><span data-stu-id="cf88a-781">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="cf88a-782">Значения: `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-782">Values: `true` or `false`.</span></span> <span data-ttu-id="cf88a-783">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="cf88a-783">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="cf88a-784">Примеры</span><span class="sxs-lookup"><span data-stu-id="cf88a-784">Examples</span></span>

<span data-ttu-id="cf88a-785">Создайте проект консольного приложения на C#, указав имя шаблона:</span><span class="sxs-lookup"><span data-stu-id="cf88a-785">Create a C# console application project by specifying the template name:</span></span>

`dotnet new "Console Application"`

<span data-ttu-id="cf88a-786">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="cf88a-786">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="cf88a-787">Создание проекта библиотеки классов .NET Standard в указанном каталоге (доступно только при использовании пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="cf88a-787">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="cf88a-788">Создайте новый проект MVC ASP.NET Core C# в текущем каталоге без проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="cf88a-788">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="cf88a-789">Создайте новый проект xUnit:</span><span class="sxs-lookup"><span data-stu-id="cf88a-789">Create a new xUnit project:</span></span>

`dotnet new xunit`

<span data-ttu-id="cf88a-790">Перечислите все шаблоны, доступные для MVC:</span><span class="sxs-lookup"><span data-stu-id="cf88a-790">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="cf88a-791">Список всех шаблонов, соответствующих подстроке *we*.</span><span class="sxs-lookup"><span data-stu-id="cf88a-791">List all templates matching the *we* substring.</span></span> <span data-ttu-id="cf88a-792">Точное совпадение не найдено, поэтому сравнение подстрок выполняется по короткому имени и столбцам имен.</span><span class="sxs-lookup"><span data-stu-id="cf88a-792">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

`dotnet new we -l`

<span data-ttu-id="cf88a-793">Попытайтесь вызвать шаблон, соответствующий *ng*.</span><span class="sxs-lookup"><span data-stu-id="cf88a-793">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="cf88a-794">Если точное совпадение не найдено, выведите шаблоны с частичным совпадением.</span><span class="sxs-lookup"><span data-stu-id="cf88a-794">If a single match can't be determined, list the templates that are partial matches.</span></span>

`dotnet new ng`

<span data-ttu-id="cf88a-795">Установите версию 2.0 шаблонов одностраничного приложения для ASP.NET Core (параметр команды доступен в .NET Core SDK 1.1 и более поздних версиях):</span><span class="sxs-lookup"><span data-stu-id="cf88a-795">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="cf88a-796">Создайте *global.json* в текущем каталоге, указав версию пакета SDK 2.0.0 (доступно только для пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="cf88a-796">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="cf88a-797">См. также</span><span class="sxs-lookup"><span data-stu-id="cf88a-797">See also</span></span>

- [<span data-ttu-id="cf88a-798">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="cf88a-798">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="cf88a-799">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="cf88a-799">Create a custom template for dotnet new</span></span>](../tutorials/create-custom-template.md)
- [<span data-ttu-id="cf88a-800">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="cf88a-800">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="cf88a-801">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="cf88a-801">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
