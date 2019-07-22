---
title: Команда dotnet new
description: Команда dotnet new создает проекты .NET Core на основе указанного шаблона.
ms.date: 05/06/2019
ms.openlocfilehash: f8bc8cb59ae6e421f4e9bd05925376399939056d
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65878317"
---
# <a name="dotnet-new"></a><span data-ttu-id="52c07-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="52c07-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="52c07-104">name</span><span class="sxs-lookup"><span data-stu-id="52c07-104">Name</span></span>

<span data-ttu-id="52c07-105">`dotnet new` - создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="52c07-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="52c07-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="52c07-106">Synopsis</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="52c07-107">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="52c07-107">.NET Core 2.2</span></span>](#tab/netcore22)

```console
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="52c07-108">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="52c07-108">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="52c07-109">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="52c07-109">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="52c07-110">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="52c07-110">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="52c07-111">Описание</span><span class="sxs-lookup"><span data-stu-id="52c07-111">Description</span></span>

<span data-ttu-id="52c07-112">Команда `dotnet new` предоставляет удобный способ инициализации проекта .NET Core.</span><span class="sxs-lookup"><span data-stu-id="52c07-112">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="52c07-113">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="52c07-113">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="52c07-114">Аргументы</span><span class="sxs-lookup"><span data-stu-id="52c07-114">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="52c07-115">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="52c07-115">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="52c07-116">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="52c07-116">Each template might have specific options you can pass.</span></span> <span data-ttu-id="52c07-117">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="52c07-117">For more information, see [Template options](#template-options).</span></span>

<span data-ttu-id="52c07-118">Если значение `TEMPLATE` не в точности совпадает с текстом в столбце **Шаблоны** или **Короткое имя**, для этих двух столбцов выполняется поиск совпадений в подстроках.</span><span class="sxs-lookup"><span data-stu-id="52c07-118">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column, a substring match is performed on those two columns.</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="52c07-119">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="52c07-119">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="52c07-120">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="52c07-120">The command contains a default list of templates.</span></span> <span data-ttu-id="52c07-121">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="52c07-121">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="52c07-122">В следующей таблице показаны шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.2.100.</span><span class="sxs-lookup"><span data-stu-id="52c07-122">The following table shows the templates that come pre-installed with the .NET Core SDK 2.2.100.</span></span> <span data-ttu-id="52c07-123">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="52c07-123">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="52c07-124">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="52c07-124">Templates</span></span>                                    | <span data-ttu-id="52c07-125">Краткое имя</span><span class="sxs-lookup"><span data-stu-id="52c07-125">Short Name</span></span>        | <span data-ttu-id="52c07-126">Язык</span><span class="sxs-lookup"><span data-stu-id="52c07-126">Language</span></span>     | <span data-ttu-id="52c07-127">Теги</span><span class="sxs-lookup"><span data-stu-id="52c07-127">Tags</span></span>                                  |
|----------------------------------------------|-------------------|--------------|---------------------------------------|
| <span data-ttu-id="52c07-128">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="52c07-128">Console Application</span></span>                          | `console`         | <span data-ttu-id="52c07-129">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="52c07-129">[C#], F#, VB</span></span> | <span data-ttu-id="52c07-130">Общее/консоль</span><span class="sxs-lookup"><span data-stu-id="52c07-130">Common/Console</span></span>                        |
| <span data-ttu-id="52c07-131">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="52c07-131">Class library</span></span>                                | `classlib`        | <span data-ttu-id="52c07-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="52c07-132">[C#], F#, VB</span></span> | <span data-ttu-id="52c07-133">Общее/библиотека</span><span class="sxs-lookup"><span data-stu-id="52c07-133">Common/Library</span></span>                        |
| <span data-ttu-id="52c07-134">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="52c07-134">Unit Test Project</span></span>                            | `mstest`          | <span data-ttu-id="52c07-135">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="52c07-135">[C#], F#, VB</span></span> | <span data-ttu-id="52c07-136">Тест/MSTest</span><span class="sxs-lookup"><span data-stu-id="52c07-136">Test/MSTest</span></span>                           |
| <span data-ttu-id="52c07-137">Тестовый проект NUnit 3</span><span class="sxs-lookup"><span data-stu-id="52c07-137">NUnit 3 Test Project</span></span>                         | `nunit`           | <span data-ttu-id="52c07-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="52c07-138">[C#], F#, VB</span></span> | <span data-ttu-id="52c07-139">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="52c07-139">Test/NUnit</span></span>                            |
| <span data-ttu-id="52c07-140">Элемент теста NUnit 3</span><span class="sxs-lookup"><span data-stu-id="52c07-140">NUnit 3 Test Item</span></span>                            | `nunit-test`      | <span data-ttu-id="52c07-141">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="52c07-141">[C#], F#, VB</span></span> | <span data-ttu-id="52c07-142">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="52c07-142">Test/NUnit</span></span>                            |
| <span data-ttu-id="52c07-143">Тестовый проект xUnit</span><span class="sxs-lookup"><span data-stu-id="52c07-143">xUnit Test Project</span></span>                           | `xunit`           | <span data-ttu-id="52c07-144">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="52c07-144">[C#], F#, VB</span></span> | <span data-ttu-id="52c07-145">Тест/xUnit</span><span class="sxs-lookup"><span data-stu-id="52c07-145">Test/xUnit</span></span>                            |
| <span data-ttu-id="52c07-146">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="52c07-146">Razor Page</span></span>                                   | `page`            | <span data-ttu-id="52c07-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="52c07-147">[C#]</span></span>         | <span data-ttu-id="52c07-148">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="52c07-148">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="52c07-149">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="52c07-149">MVC ViewImports</span></span>                              | `viewimports`     | <span data-ttu-id="52c07-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="52c07-150">[C#]</span></span>         | <span data-ttu-id="52c07-151">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="52c07-151">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="52c07-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="52c07-152">MVC ViewStart</span></span>                                | `viewstart`       | <span data-ttu-id="52c07-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="52c07-153">[C#]</span></span>         | <span data-ttu-id="52c07-154">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="52c07-154">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="52c07-155">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="52c07-155">ASP.NET Core Empty</span></span>                           | `web`             | <span data-ttu-id="52c07-156">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="52c07-156">[C#], F#</span></span>     | <span data-ttu-id="52c07-157">Веб/пусто</span><span class="sxs-lookup"><span data-stu-id="52c07-157">Web/Empty</span></span>                             |
| <span data-ttu-id="52c07-158">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="52c07-158">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`             | <span data-ttu-id="52c07-159">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="52c07-159">[C#], F#</span></span>     | <span data-ttu-id="52c07-160">Веб/MVC</span><span class="sxs-lookup"><span data-stu-id="52c07-160">Web/MVC</span></span>                               |
| <span data-ttu-id="52c07-161">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="52c07-161">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="52c07-162">`webapp`, `razor`</span><span class="sxs-lookup"><span data-stu-id="52c07-162">`webapp`, `razor`</span></span> | <span data-ttu-id="52c07-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="52c07-163">[C#]</span></span>         | <span data-ttu-id="52c07-164">Веб/MVC и Razor Pages</span><span class="sxs-lookup"><span data-stu-id="52c07-164">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="52c07-165">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="52c07-165">ASP.NET Core with Angular</span></span>                    | `angular`         | <span data-ttu-id="52c07-166">[C#]</span><span class="sxs-lookup"><span data-stu-id="52c07-166">[C#]</span></span>         | <span data-ttu-id="52c07-167">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="52c07-167">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="52c07-168">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="52c07-168">ASP.NET Core with React.js</span></span>                   | `react`           | <span data-ttu-id="52c07-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="52c07-169">[C#]</span></span>         | <span data-ttu-id="52c07-170">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="52c07-170">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="52c07-171">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="52c07-171">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`      | <span data-ttu-id="52c07-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="52c07-172">[C#]</span></span>         | <span data-ttu-id="52c07-173">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="52c07-173">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="52c07-174">Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="52c07-174">Razor Class Library</span></span>                          | `razorclasslib`   | <span data-ttu-id="52c07-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="52c07-175">[C#]</span></span>         | <span data-ttu-id="52c07-176">Веб/Razor/Библиотека/Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="52c07-176">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="52c07-177">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="52c07-177">ASP.NET Core Web API</span></span>                         | `webapi`          | <span data-ttu-id="52c07-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="52c07-178">[C#], F#</span></span>     | <span data-ttu-id="52c07-179">Веб/веб-API</span><span class="sxs-lookup"><span data-stu-id="52c07-179">Web/WebAPI</span></span>                            |
| <span data-ttu-id="52c07-180">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="52c07-180">global.json file</span></span>                             | `globaljson`      |              | <span data-ttu-id="52c07-181">Config</span><span class="sxs-lookup"><span data-stu-id="52c07-181">Config</span></span>                                |
| <span data-ttu-id="52c07-182">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="52c07-182">NuGet Config</span></span>                                 | `nugetconfig`     |              | <span data-ttu-id="52c07-183">Config</span><span class="sxs-lookup"><span data-stu-id="52c07-183">Config</span></span>                                |
| <span data-ttu-id="52c07-184">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="52c07-184">Web Config</span></span>                                   | `webconfig`       |              | <span data-ttu-id="52c07-185">Config</span><span class="sxs-lookup"><span data-stu-id="52c07-185">Config</span></span>                                |
| <span data-ttu-id="52c07-186">Файл решения</span><span class="sxs-lookup"><span data-stu-id="52c07-186">Solution File</span></span>                                | `sln`             |              | <span data-ttu-id="52c07-187">Решение</span><span class="sxs-lookup"><span data-stu-id="52c07-187">Solution</span></span>                              |

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="52c07-188">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="52c07-188">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="52c07-189">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="52c07-189">The command contains a default list of templates.</span></span> <span data-ttu-id="52c07-190">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="52c07-190">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="52c07-191">В приведенной ниже таблице представлены шаблоны, которые устанавливаются вместе с пакетом SDK для .NET Core 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="52c07-191">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="52c07-192">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="52c07-192">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="52c07-193">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="52c07-193">Templates</span></span>                                    | <span data-ttu-id="52c07-194">Краткое имя</span><span class="sxs-lookup"><span data-stu-id="52c07-194">Short Name</span></span>      | <span data-ttu-id="52c07-195">Язык</span><span class="sxs-lookup"><span data-stu-id="52c07-195">Language</span></span>     | <span data-ttu-id="52c07-196">Теги</span><span class="sxs-lookup"><span data-stu-id="52c07-196">Tags</span></span>                                  |
|----------------------------------------------|-----------------|--------------|---------------------------------------|
| <span data-ttu-id="52c07-197">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="52c07-197">Console Application</span></span>                          | `console`       | <span data-ttu-id="52c07-198">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="52c07-198">[C#], F#, VB</span></span> | <span data-ttu-id="52c07-199">Общее/консоль</span><span class="sxs-lookup"><span data-stu-id="52c07-199">Common/Console</span></span>                        |
| <span data-ttu-id="52c07-200">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="52c07-200">Class library</span></span>                                | `classlib`      | <span data-ttu-id="52c07-201">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="52c07-201">[C#], F#, VB</span></span> | <span data-ttu-id="52c07-202">Общее/библиотека</span><span class="sxs-lookup"><span data-stu-id="52c07-202">Common/Library</span></span>                        |
| <span data-ttu-id="52c07-203">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="52c07-203">Unit Test Project</span></span>                            | `mstest`        | <span data-ttu-id="52c07-204">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="52c07-204">[C#], F#, VB</span></span> | <span data-ttu-id="52c07-205">Тест/MSTest</span><span class="sxs-lookup"><span data-stu-id="52c07-205">Test/MSTest</span></span>                           |
| <span data-ttu-id="52c07-206">Тестовый проект xUnit</span><span class="sxs-lookup"><span data-stu-id="52c07-206">xUnit Test Project</span></span>                           | `xunit`         | <span data-ttu-id="52c07-207">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="52c07-207">[C#], F#, VB</span></span> | <span data-ttu-id="52c07-208">Тест/xUnit</span><span class="sxs-lookup"><span data-stu-id="52c07-208">Test/xUnit</span></span>                            |
| <span data-ttu-id="52c07-209">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="52c07-209">Razor Page</span></span>                                   | `page`          | <span data-ttu-id="52c07-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="52c07-210">[C#]</span></span>         | <span data-ttu-id="52c07-211">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="52c07-211">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="52c07-212">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="52c07-212">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="52c07-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="52c07-213">[C#]</span></span>         | <span data-ttu-id="52c07-214">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="52c07-214">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="52c07-215">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="52c07-215">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="52c07-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="52c07-216">[C#]</span></span>         | <span data-ttu-id="52c07-217">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="52c07-217">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="52c07-218">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="52c07-218">ASP.NET Core Empty</span></span>                           | `web`           | <span data-ttu-id="52c07-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="52c07-219">[C#], F#</span></span>     | <span data-ttu-id="52c07-220">Веб/пусто</span><span class="sxs-lookup"><span data-stu-id="52c07-220">Web/Empty</span></span>                             |
| <span data-ttu-id="52c07-221">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="52c07-221">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="52c07-222">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="52c07-222">[C#], F#</span></span>     | <span data-ttu-id="52c07-223">Веб/MVC</span><span class="sxs-lookup"><span data-stu-id="52c07-223">Web/MVC</span></span>                               |
| <span data-ttu-id="52c07-224">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="52c07-224">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="52c07-225">[C#]</span><span class="sxs-lookup"><span data-stu-id="52c07-225">[C#]</span></span>         | <span data-ttu-id="52c07-226">Веб/MVC и Razor Pages</span><span class="sxs-lookup"><span data-stu-id="52c07-226">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="52c07-227">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="52c07-227">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="52c07-228">[C#]</span><span class="sxs-lookup"><span data-stu-id="52c07-228">[C#]</span></span>         | <span data-ttu-id="52c07-229">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="52c07-229">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="52c07-230">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="52c07-230">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="52c07-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="52c07-231">[C#]</span></span>         | <span data-ttu-id="52c07-232">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="52c07-232">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="52c07-233">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="52c07-233">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="52c07-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="52c07-234">[C#]</span></span>         | <span data-ttu-id="52c07-235">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="52c07-235">Web/MVC/SPA</span></span>                           | 
| <span data-ttu-id="52c07-236">Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="52c07-236">Razor Class Library</span></span>                          | `razorclasslib` | <span data-ttu-id="52c07-237">[C#]</span><span class="sxs-lookup"><span data-stu-id="52c07-237">[C#]</span></span>         | <span data-ttu-id="52c07-238">Веб/Razor/Библиотека/Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="52c07-238">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="52c07-239">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="52c07-239">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="52c07-240">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="52c07-240">[C#], F#</span></span>     | <span data-ttu-id="52c07-241">Веб/веб-API</span><span class="sxs-lookup"><span data-stu-id="52c07-241">Web/WebAPI</span></span>                            |
| <span data-ttu-id="52c07-242">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="52c07-242">global.json file</span></span>                             | `globaljson`    |              | <span data-ttu-id="52c07-243">Config</span><span class="sxs-lookup"><span data-stu-id="52c07-243">Config</span></span>                                |
| <span data-ttu-id="52c07-244">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="52c07-244">NuGet Config</span></span>                                 | `nugetconfig`   |              | <span data-ttu-id="52c07-245">Config</span><span class="sxs-lookup"><span data-stu-id="52c07-245">Config</span></span>                                |
| <span data-ttu-id="52c07-246">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="52c07-246">Web Config</span></span>                                   | `webconfig`     |              | <span data-ttu-id="52c07-247">Config</span><span class="sxs-lookup"><span data-stu-id="52c07-247">Config</span></span>                                |
| <span data-ttu-id="52c07-248">Файл решения</span><span class="sxs-lookup"><span data-stu-id="52c07-248">Solution File</span></span>                                | `sln`           |              | <span data-ttu-id="52c07-249">Решение</span><span class="sxs-lookup"><span data-stu-id="52c07-249">Solution</span></span>                              |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="52c07-250">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="52c07-250">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="52c07-251">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="52c07-251">The command contains a default list of templates.</span></span> <span data-ttu-id="52c07-252">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="52c07-252">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="52c07-253">В следующей таблице показаны шаблоны, которые устанавливаются с пакетом SDK для .NET Core 2.0.0.</span><span class="sxs-lookup"><span data-stu-id="52c07-253">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.0.</span></span> <span data-ttu-id="52c07-254">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="52c07-254">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="52c07-255">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="52c07-255">Templates</span></span>                                    | <span data-ttu-id="52c07-256">Краткое имя</span><span class="sxs-lookup"><span data-stu-id="52c07-256">Short Name</span></span>    | <span data-ttu-id="52c07-257">Язык</span><span class="sxs-lookup"><span data-stu-id="52c07-257">Language</span></span>     | <span data-ttu-id="52c07-258">Теги</span><span class="sxs-lookup"><span data-stu-id="52c07-258">Tags</span></span>                |
|----------------------------------------------|---------------|--------------|---------------------|
| <span data-ttu-id="52c07-259">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="52c07-259">Console Application</span></span>                          | `console`     | <span data-ttu-id="52c07-260">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="52c07-260">[C#], F#, VB</span></span> | <span data-ttu-id="52c07-261">Общее/консоль</span><span class="sxs-lookup"><span data-stu-id="52c07-261">Common/Console</span></span>      |
| <span data-ttu-id="52c07-262">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="52c07-262">Class library</span></span>                                | `classlib`    | <span data-ttu-id="52c07-263">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="52c07-263">[C#], F#, VB</span></span> | <span data-ttu-id="52c07-264">Общее/библиотека</span><span class="sxs-lookup"><span data-stu-id="52c07-264">Common/Library</span></span>      |
| <span data-ttu-id="52c07-265">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="52c07-265">Unit Test Project</span></span>                            | `mstest`      | <span data-ttu-id="52c07-266">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="52c07-266">[C#], F#, VB</span></span> | <span data-ttu-id="52c07-267">Тест/MSTest</span><span class="sxs-lookup"><span data-stu-id="52c07-267">Test/MSTest</span></span>         |
| <span data-ttu-id="52c07-268">Тестовый проект xUnit</span><span class="sxs-lookup"><span data-stu-id="52c07-268">xUnit Test Project</span></span>                           | `xunit`       | <span data-ttu-id="52c07-269">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="52c07-269">[C#], F#, VB</span></span> | <span data-ttu-id="52c07-270">Тест/xUnit</span><span class="sxs-lookup"><span data-stu-id="52c07-270">Test/xUnit</span></span>          |
| <span data-ttu-id="52c07-271">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="52c07-271">ASP.NET Core Empty</span></span>                           | `web`         | <span data-ttu-id="52c07-272">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="52c07-272">[C#], F#</span></span>     | <span data-ttu-id="52c07-273">Веб/пусто</span><span class="sxs-lookup"><span data-stu-id="52c07-273">Web/Empty</span></span>           |
| <span data-ttu-id="52c07-274">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="52c07-274">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="52c07-275">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="52c07-275">[C#], F#</span></span>     | <span data-ttu-id="52c07-276">Веб/MVC</span><span class="sxs-lookup"><span data-stu-id="52c07-276">Web/MVC</span></span>             |
| <span data-ttu-id="52c07-277">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="52c07-277">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="52c07-278">[C#]</span><span class="sxs-lookup"><span data-stu-id="52c07-278">[C#]</span></span>         | <span data-ttu-id="52c07-279">Веб/MVC и Razor Pages</span><span class="sxs-lookup"><span data-stu-id="52c07-279">Web/MVC/Razor Pages</span></span> |
| <span data-ttu-id="52c07-280">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="52c07-280">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="52c07-281">[C#]</span><span class="sxs-lookup"><span data-stu-id="52c07-281">[C#]</span></span>         | <span data-ttu-id="52c07-282">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="52c07-282">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="52c07-283">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="52c07-283">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="52c07-284">[C#]</span><span class="sxs-lookup"><span data-stu-id="52c07-284">[C#]</span></span>         | <span data-ttu-id="52c07-285">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="52c07-285">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="52c07-286">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="52c07-286">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="52c07-287">[C#]</span><span class="sxs-lookup"><span data-stu-id="52c07-287">[C#]</span></span>         | <span data-ttu-id="52c07-288">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="52c07-288">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="52c07-289">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="52c07-289">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="52c07-290">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="52c07-290">[C#], F#</span></span>     | <span data-ttu-id="52c07-291">Веб/веб-API</span><span class="sxs-lookup"><span data-stu-id="52c07-291">Web/WebAPI</span></span>          |
| <span data-ttu-id="52c07-292">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="52c07-292">global.json file</span></span>                             | `globaljson`  |              | <span data-ttu-id="52c07-293">Config</span><span class="sxs-lookup"><span data-stu-id="52c07-293">Config</span></span>              |
| <span data-ttu-id="52c07-294">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="52c07-294">Nuget Config</span></span>                                 | `nugetconfig` |              | <span data-ttu-id="52c07-295">Config</span><span class="sxs-lookup"><span data-stu-id="52c07-295">Config</span></span>              |
| <span data-ttu-id="52c07-296">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="52c07-296">Web Config</span></span>                                   | `webconfig`   |              | <span data-ttu-id="52c07-297">Config</span><span class="sxs-lookup"><span data-stu-id="52c07-297">Config</span></span>              |
| <span data-ttu-id="52c07-298">Файл решения</span><span class="sxs-lookup"><span data-stu-id="52c07-298">Solution File</span></span>                                | `sln`         |              | <span data-ttu-id="52c07-299">Решение</span><span class="sxs-lookup"><span data-stu-id="52c07-299">Solution</span></span>            |
| <span data-ttu-id="52c07-300">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="52c07-300">Razor Page</span></span>                                   | `page`        |              | <span data-ttu-id="52c07-301">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="52c07-301">Web/ASP.NET</span></span>         |
| <span data-ttu-id="52c07-302">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="52c07-302">MVC ViewImports</span></span>                              | `viewimports` |              | <span data-ttu-id="52c07-303">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="52c07-303">Web/ASP.NET</span></span>         |
| <span data-ttu-id="52c07-304">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="52c07-304">MVC ViewStart</span></span>                                | `viewstart`   |              | <span data-ttu-id="52c07-305">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="52c07-305">Web/ASP.NET</span></span>         |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="52c07-306">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="52c07-306">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="52c07-307">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="52c07-307">The command contains a default list of templates.</span></span> <span data-ttu-id="52c07-308">Используйте `dotnet new -all`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="52c07-308">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="52c07-309">В следующей таблице показаны шаблоны, которые устанавливаются с пакетом SDK для .NET Core 1.0.1.</span><span class="sxs-lookup"><span data-stu-id="52c07-309">The following table shows the templates that come pre-installed with the .NET Core SDK 1.0.1.</span></span> <span data-ttu-id="52c07-310">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="52c07-310">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="52c07-311">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="52c07-311">Templates</span></span>            | <span data-ttu-id="52c07-312">Краткое имя</span><span class="sxs-lookup"><span data-stu-id="52c07-312">Short Name</span></span>    | <span data-ttu-id="52c07-313">Язык</span><span class="sxs-lookup"><span data-stu-id="52c07-313">Language</span></span> | <span data-ttu-id="52c07-314">Теги</span><span class="sxs-lookup"><span data-stu-id="52c07-314">Tags</span></span>           |
|----------------------|---------------|----------|----------------|
| <span data-ttu-id="52c07-315">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="52c07-315">Console Application</span></span>  | `console`     | <span data-ttu-id="52c07-316">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="52c07-316">[C#], F#</span></span> | <span data-ttu-id="52c07-317">Общее/консоль</span><span class="sxs-lookup"><span data-stu-id="52c07-317">Common/Console</span></span> |
| <span data-ttu-id="52c07-318">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="52c07-318">Class library</span></span>        | `classlib`    | <span data-ttu-id="52c07-319">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="52c07-319">[C#], F#</span></span> | <span data-ttu-id="52c07-320">Общее/библиотека</span><span class="sxs-lookup"><span data-stu-id="52c07-320">Common/Library</span></span> |
| <span data-ttu-id="52c07-321">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="52c07-321">Unit Test Project</span></span>    | `mstest`      | <span data-ttu-id="52c07-322">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="52c07-322">[C#], F#</span></span> | <span data-ttu-id="52c07-323">Тест/MSTest</span><span class="sxs-lookup"><span data-stu-id="52c07-323">Test/MSTest</span></span>    |
| <span data-ttu-id="52c07-324">Тестовый проект xUnit</span><span class="sxs-lookup"><span data-stu-id="52c07-324">xUnit Test Project</span></span>   | `xunit`       | <span data-ttu-id="52c07-325">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="52c07-325">[C#], F#</span></span> | <span data-ttu-id="52c07-326">Тест/xUnit</span><span class="sxs-lookup"><span data-stu-id="52c07-326">Test/xUnit</span></span>     |
| <span data-ttu-id="52c07-327">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="52c07-327">ASP.NET Core Empty</span></span>   | `web`         | <span data-ttu-id="52c07-328">[C#]</span><span class="sxs-lookup"><span data-stu-id="52c07-328">[C#]</span></span>     | <span data-ttu-id="52c07-329">Веб/пусто</span><span class="sxs-lookup"><span data-stu-id="52c07-329">Web/Empty</span></span>      |
| <span data-ttu-id="52c07-330">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="52c07-330">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="52c07-331">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="52c07-331">[C#], F#</span></span> | <span data-ttu-id="52c07-332">Веб/MVC</span><span class="sxs-lookup"><span data-stu-id="52c07-332">Web/MVC</span></span>        |
| <span data-ttu-id="52c07-333">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="52c07-333">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="52c07-334">[C#]</span><span class="sxs-lookup"><span data-stu-id="52c07-334">[C#]</span></span>     | <span data-ttu-id="52c07-335">Веб/веб-API</span><span class="sxs-lookup"><span data-stu-id="52c07-335">Web/WebAPI</span></span>     |
| <span data-ttu-id="52c07-336">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="52c07-336">Nuget Config</span></span>         | `nugetconfig` |          | <span data-ttu-id="52c07-337">Config</span><span class="sxs-lookup"><span data-stu-id="52c07-337">Config</span></span>         |
| <span data-ttu-id="52c07-338">Веб-конфигурация</span><span class="sxs-lookup"><span data-stu-id="52c07-338">Web Config</span></span>           | `webconfig`   |          | <span data-ttu-id="52c07-339">Config</span><span class="sxs-lookup"><span data-stu-id="52c07-339">Config</span></span>         |
| <span data-ttu-id="52c07-340">Файл решения</span><span class="sxs-lookup"><span data-stu-id="52c07-340">Solution File</span></span>        | `sln`         |          | <span data-ttu-id="52c07-341">Решение</span><span class="sxs-lookup"><span data-stu-id="52c07-341">Solution</span></span>       |

---

## <a name="options"></a><span data-ttu-id="52c07-342">Параметры</span><span class="sxs-lookup"><span data-stu-id="52c07-342">Options</span></span>

# <a name="net-core-22tabnetcore22"></a><span data-ttu-id="52c07-343">[.NET Core 2.2](#tab/netcore22).</span><span class="sxs-lookup"><span data-stu-id="52c07-343">[.NET Core 2.2](#tab/netcore22)</span></span>

`--dry-run`

<span data-ttu-id="52c07-344">Отображает сводку того, что произойдет, если выполнить команду и это приведет к созданию шаблона.</span><span class="sxs-lookup"><span data-stu-id="52c07-344">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span>

`--force`

<span data-ttu-id="52c07-345">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="52c07-345">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="52c07-346">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="52c07-346">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="52c07-347">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="52c07-347">Prints out help for the command.</span></span> <span data-ttu-id="52c07-348">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="52c07-348">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="52c07-349">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="52c07-349">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="52c07-350">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="52c07-350">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="52c07-351">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="52c07-351">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="52c07-352">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="52c07-352">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="52c07-353">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="52c07-353">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="52c07-354">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="52c07-354">Lists templates containing the specified name.</span></span> <span data-ttu-id="52c07-355">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="52c07-355">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="52c07-356">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-356">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="52c07-357">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="52c07-357">The language of the template to create.</span></span> <span data-ttu-id="52c07-358">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="52c07-358">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="52c07-359">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="52c07-359">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="52c07-360">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="52c07-360">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="52c07-361">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="52c07-361">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="52c07-362">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="52c07-362">The name for the created output.</span></span> <span data-ttu-id="52c07-363">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="52c07-363">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="52c07-364">Задает источник пакетов NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="52c07-364">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="52c07-365">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="52c07-365">Location to place the generated output.</span></span> <span data-ttu-id="52c07-366">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="52c07-366">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="52c07-367">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="52c07-367">Filters templates based on available types.</span></span> <span data-ttu-id="52c07-368">Предопределенные значения: "project", "item" или "other".</span><span class="sxs-lookup"><span data-stu-id="52c07-368">Predefined values are "project", "item", or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="52c07-369">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="52c07-369">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="52c07-370">При исключении значения `<PATH|NUGET_ID>` отображаются все установленные пакеты шаблонов и связанные с ними шаблоны.</span><span class="sxs-lookup"><span data-stu-id="52c07-370">When excluding the `<PATH|NUGET_ID>` value, all currently installed template packs and their associated templates are displayed.</span></span>

> [!NOTE]
> <span data-ttu-id="52c07-371">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="52c07-371">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="52c07-372">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="52c07-372">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="52c07-373">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="52c07-373">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="52c07-374">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="52c07-374">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="52c07-375">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="52c07-375">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="52c07-376">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="52c07-376">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="52c07-377">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="52c07-377">Prints out help for the command.</span></span> <span data-ttu-id="52c07-378">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="52c07-378">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="52c07-379">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="52c07-379">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="52c07-380">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="52c07-380">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="52c07-381">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="52c07-381">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="52c07-382">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="52c07-382">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="52c07-383">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="52c07-383">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="52c07-384">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="52c07-384">Lists templates containing the specified name.</span></span> <span data-ttu-id="52c07-385">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="52c07-385">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="52c07-386">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-386">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="52c07-387">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="52c07-387">The language of the template to create.</span></span> <span data-ttu-id="52c07-388">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="52c07-388">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="52c07-389">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="52c07-389">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="52c07-390">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="52c07-390">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="52c07-391">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="52c07-391">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="52c07-392">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="52c07-392">The name for the created output.</span></span> <span data-ttu-id="52c07-393">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="52c07-393">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="52c07-394">Задает источник пакетов NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="52c07-394">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="52c07-395">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="52c07-395">Location to place the generated output.</span></span> <span data-ttu-id="52c07-396">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="52c07-396">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="52c07-397">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="52c07-397">Filters templates based on available types.</span></span> <span data-ttu-id="52c07-398">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="52c07-398">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="52c07-399">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="52c07-399">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="52c07-400">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="52c07-400">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="52c07-401">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="52c07-401">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="52c07-402">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="52c07-402">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="52c07-403">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="52c07-403">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="52c07-404">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="52c07-404">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="52c07-405">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="52c07-405">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="52c07-406">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="52c07-406">Prints out help for the command.</span></span> <span data-ttu-id="52c07-407">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="52c07-407">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="52c07-408">Устанавливает исходный пакет или пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="52c07-408">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="52c07-409">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="52c07-409">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="52c07-410">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="52c07-410">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="52c07-411">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="52c07-411">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="52c07-412">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="52c07-412">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="52c07-413">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="52c07-413">Lists templates containing the specified name.</span></span> <span data-ttu-id="52c07-414">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="52c07-414">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="52c07-415">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-415">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="52c07-416">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="52c07-416">The language of the template to create.</span></span> <span data-ttu-id="52c07-417">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="52c07-417">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="52c07-418">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="52c07-418">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="52c07-419">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="52c07-419">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="52c07-420">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="52c07-420">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="52c07-421">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="52c07-421">The name for the created output.</span></span> <span data-ttu-id="52c07-422">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="52c07-422">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="52c07-423">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="52c07-423">Location to place the generated output.</span></span> <span data-ttu-id="52c07-424">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="52c07-424">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="52c07-425">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="52c07-425">Filters templates based on available types.</span></span> <span data-ttu-id="52c07-426">Предварительно определенные значения: project, item и other.</span><span class="sxs-lookup"><span data-stu-id="52c07-426">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="52c07-427">Удаляет исходный пакет или пакет шаблона по указанному пути `PATH` или идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="52c07-427">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="52c07-428">Чтобы удалить шаблон, используя путь к исходному пакету `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="52c07-428">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="52c07-429">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="52c07-429">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="52c07-430">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="52c07-430">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="52c07-431">Если вам не удается определить аргумент `PATH` или `NUGET_ID`, необходимый для удаления шаблона, выполните команду `dotnet new --uninstall` без аргумента. В результате будут перечислены все установленные шаблоны и аргумент, необходимый для их удаления.</span><span class="sxs-lookup"><span data-stu-id="52c07-431">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="52c07-432">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="52c07-432">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="52c07-433">Показывает все шаблоны определенного типа проекта при запуске в контексте одной только команды `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="52c07-433">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="52c07-434">При запуске в контексте конкретного шаблона, например `dotnet new web -all`, `-all` интерпретируется как флаг принудительного создания.</span><span class="sxs-lookup"><span data-stu-id="52c07-434">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="52c07-435">Это требуется, когда выходной каталог уже содержит проект.</span><span class="sxs-lookup"><span data-stu-id="52c07-435">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="52c07-436">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="52c07-436">Prints out help for the command.</span></span> <span data-ttu-id="52c07-437">Его можно вызвать для самой команды `dotnet new` или для любого шаблона, например `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="52c07-437">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="52c07-438">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="52c07-438">Lists templates containing the specified name.</span></span> <span data-ttu-id="52c07-439">При вызове для команды `dotnet new` перечисляет возможные шаблоны, доступные для заданного каталога.</span><span class="sxs-lookup"><span data-stu-id="52c07-439">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="52c07-440">Например, если каталог уже содержит проект, он не будет перечислять все шаблоны проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-440">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="52c07-441">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="52c07-441">The language of the template to create.</span></span> <span data-ttu-id="52c07-442">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="52c07-442">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="52c07-443">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="52c07-443">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="52c07-444">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="52c07-444">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="52c07-445">В таких случаях необходимо заключить значение параметра языка в символы, например `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="52c07-445">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="52c07-446">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="52c07-446">The name for the created output.</span></span> <span data-ttu-id="52c07-447">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="52c07-447">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="52c07-448">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="52c07-448">Location to place the generated output.</span></span> <span data-ttu-id="52c07-449">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="52c07-449">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="52c07-450">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="52c07-450">Template options</span></span>

<span data-ttu-id="52c07-451">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="52c07-451">Each project template may have additional options available.</span></span> <span data-ttu-id="52c07-452">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="52c07-452">The core templates have the following additional options:</span></span>

# <a name="net-core-22tabnetcore22"></a><span data-ttu-id="52c07-453">[.NET Core 2.2](#tab/netcore22).</span><span class="sxs-lookup"><span data-stu-id="52c07-453">[.NET Core 2.2](#tab/netcore22)</span></span>

<span data-ttu-id="52c07-454">**Консоль**</span><span class="sxs-lookup"><span data-stu-id="52c07-454">**console**</span></span>

<span data-ttu-id="52c07-455">`--langVersion <VERSION_NUMBER>` — задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-455">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="52c07-456">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="52c07-456">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="52c07-457">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="52c07-457">Not supported for F#.</span></span>

<span data-ttu-id="52c07-458">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="52c07-458">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="52c07-459">**angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="52c07-459">**angular, react, reactredux**</span></span>

<span data-ttu-id="52c07-460">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="52c07-460">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="52c07-461">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="52c07-461">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="52c07-462">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="52c07-462">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="52c07-463">Этот параметр применяется, только если `IndividualAuth` или `OrganizationalAuth` не используются.</span><span class="sxs-lookup"><span data-stu-id="52c07-463">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="52c07-464">**razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="52c07-464">**razorclasslib**</span></span>

<span data-ttu-id="52c07-465">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="52c07-465">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="52c07-466">**classlib**</span><span class="sxs-lookup"><span data-stu-id="52c07-466">**classlib**</span></span>

<span data-ttu-id="52c07-467">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="52c07-467">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="52c07-468">Значения: `netcoreapp2.2` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="52c07-468">Values: `netcoreapp2.2` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="52c07-469">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="52c07-469">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="52c07-470">`--langVersion <VERSION_NUMBER>` — задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-470">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="52c07-471">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="52c07-471">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="52c07-472">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="52c07-472">Not supported for F#.</span></span>

<span data-ttu-id="52c07-473">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="52c07-473">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="52c07-474">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="52c07-474">**mstest, xunit**</span></span>

<span data-ttu-id="52c07-475">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="52c07-475">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="52c07-476">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="52c07-476">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="52c07-477">**nunit**</span><span class="sxs-lookup"><span data-stu-id="52c07-477">**nunit**</span></span>

<span data-ttu-id="52c07-478">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="52c07-478">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="52c07-479">Значение по умолчанию — `netcoreapp2.1`.</span><span class="sxs-lookup"><span data-stu-id="52c07-479">The default value is `netcoreapp2.1`.</span></span>

<span data-ttu-id="52c07-480">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="52c07-480">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="52c07-481">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="52c07-481">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="52c07-482">**page**</span><span class="sxs-lookup"><span data-stu-id="52c07-482">**page**</span></span>

<span data-ttu-id="52c07-483">`-na|--namespace <NAMESPACE_NAME>` — пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="52c07-483">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="52c07-484">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="52c07-484">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="52c07-485">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="52c07-485">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="52c07-486">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="52c07-486">**viewimports**</span></span>

<span data-ttu-id="52c07-487">`-na|--namespace <NAMESPACE_NAME>` — пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="52c07-487">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="52c07-488">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="52c07-488">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="52c07-489">**web**</span><span class="sxs-lookup"><span data-stu-id="52c07-489">**web**</span></span>

<span data-ttu-id="52c07-490">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="52c07-490">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="52c07-491">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="52c07-491">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="52c07-492">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="52c07-492">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="52c07-493">Этот параметр применяется, только если `IndividualAuth` или `OrganizationalAuth` не используются.</span><span class="sxs-lookup"><span data-stu-id="52c07-493">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="52c07-494">**mvc, webapp**</span><span class="sxs-lookup"><span data-stu-id="52c07-494">**mvc, webapp**</span></span>

<span data-ttu-id="52c07-495">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="52c07-495">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="52c07-496">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="52c07-496">The possible values are:</span></span>

- <span data-ttu-id="52c07-497">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="52c07-497">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="52c07-498">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="52c07-498">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="52c07-499">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="52c07-499">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="52c07-500">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="52c07-500">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="52c07-501">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="52c07-501">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="52c07-502">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="52c07-502">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="52c07-503">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="52c07-503">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="52c07-504">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-504">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="52c07-505">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="52c07-505">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="52c07-506">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-506">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="52c07-507">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-507">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="52c07-508">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-508">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="52c07-509">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-509">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="52c07-510">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-510">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="52c07-511">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-511">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="52c07-512">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="52c07-512">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="52c07-513">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-513">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="52c07-514">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="52c07-514">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="52c07-515">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-515">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="52c07-516">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-516">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="52c07-517">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="52c07-517">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="52c07-518">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="52c07-518">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="52c07-519">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-519">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="52c07-520">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="52c07-520">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="52c07-521">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="52c07-521">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="52c07-522">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-522">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="52c07-523">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="52c07-523">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="52c07-524">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="52c07-524">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="52c07-525">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-525">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="52c07-526">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="52c07-526">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="52c07-527">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="52c07-527">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="52c07-528">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-528">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="52c07-529">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="52c07-529">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="52c07-530">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="52c07-530">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="52c07-531">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="52c07-531">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="52c07-532">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="52c07-532">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="52c07-533">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="52c07-533">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="52c07-534">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-534">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="52c07-535">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="52c07-535">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="52c07-536">**webapi**</span><span class="sxs-lookup"><span data-stu-id="52c07-536">**webapi**</span></span>

<span data-ttu-id="52c07-537">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="52c07-537">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="52c07-538">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="52c07-538">The possible values are:</span></span>

- <span data-ttu-id="52c07-539">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="52c07-539">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="52c07-540">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="52c07-540">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="52c07-541">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="52c07-541">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="52c07-542">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="52c07-542">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="52c07-543">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="52c07-543">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="52c07-544">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-544">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="52c07-545">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="52c07-545">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="52c07-546">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-546">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="52c07-547">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-547">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="52c07-548">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="52c07-548">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="52c07-549">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-549">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="52c07-550">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="52c07-550">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="52c07-551">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-551">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="52c07-552">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-552">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="52c07-553">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="52c07-553">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="52c07-554">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="52c07-554">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="52c07-555">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-555">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="52c07-556">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="52c07-556">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="52c07-557">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="52c07-557">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="52c07-558">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="52c07-559">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="52c07-559">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="52c07-560">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="52c07-560">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="52c07-561">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-561">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="52c07-562">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="52c07-562">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="52c07-563">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="52c07-563">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="52c07-564">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="52c07-564">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="52c07-565">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="52c07-565">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="52c07-566">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="52c07-566">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="52c07-567">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-567">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="52c07-568">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="52c07-568">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="52c07-569">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="52c07-569">**globaljson**</span></span>

<span data-ttu-id="52c07-570">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="52c07-570">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="52c07-571">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="52c07-571">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="52c07-572">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="52c07-572">**console, angular, react, reactredux, razorclasslib**</span></span>

<span data-ttu-id="52c07-573">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="52c07-573">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="52c07-574">**classlib**</span><span class="sxs-lookup"><span data-stu-id="52c07-574">**classlib**</span></span>

<span data-ttu-id="52c07-575">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="52c07-575">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="52c07-576">Значения: `netcoreapp2.1` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="52c07-576">Values: `netcoreapp2.1` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="52c07-577">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="52c07-577">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="52c07-578">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="52c07-578">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="52c07-579">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="52c07-579">**mstest, xunit**</span></span>

<span data-ttu-id="52c07-580">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="52c07-580">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="52c07-581">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="52c07-581">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="52c07-582">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="52c07-582">**globaljson**</span></span>

<span data-ttu-id="52c07-583">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="52c07-583">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="52c07-584">**web**</span><span class="sxs-lookup"><span data-stu-id="52c07-584">**web**</span></span>

<span data-ttu-id="52c07-585">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="52c07-585">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="52c07-586">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="52c07-586">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="52c07-587">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="52c07-587">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="52c07-588">Этот параметр применяется, только если `IndividualAuth` или `OrganizationalAuth` не используются.</span><span class="sxs-lookup"><span data-stu-id="52c07-588">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="52c07-589">**webapi**</span><span class="sxs-lookup"><span data-stu-id="52c07-589">**webapi**</span></span>

<span data-ttu-id="52c07-590">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="52c07-590">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="52c07-591">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="52c07-591">The possible values are:</span></span>

- <span data-ttu-id="52c07-592">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="52c07-592">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="52c07-593">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="52c07-593">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="52c07-594">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="52c07-594">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="52c07-595">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="52c07-595">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="52c07-596">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="52c07-596">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="52c07-597">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-597">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="52c07-598">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="52c07-598">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="52c07-599">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-599">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="52c07-600">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-600">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="52c07-601">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="52c07-601">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="52c07-602">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-602">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="52c07-603">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="52c07-603">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="52c07-604">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-604">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="52c07-605">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-605">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="52c07-606">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="52c07-606">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="52c07-607">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="52c07-607">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="52c07-608">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-608">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="52c07-609">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="52c07-609">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="52c07-610">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="52c07-610">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="52c07-611">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-611">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="52c07-612">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="52c07-612">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="52c07-613">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="52c07-613">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="52c07-614">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-614">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="52c07-615">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="52c07-615">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="52c07-616">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="52c07-616">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="52c07-617">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-617">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="52c07-618">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="52c07-618">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="52c07-619">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="52c07-619">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="52c07-620">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="52c07-620">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="52c07-621">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="52c07-621">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="52c07-622">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="52c07-622">**mvc, razor**</span></span>

<span data-ttu-id="52c07-623">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="52c07-623">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="52c07-624">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="52c07-624">The possible values are:</span></span>

- <span data-ttu-id="52c07-625">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="52c07-625">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="52c07-626">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="52c07-626">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="52c07-627">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="52c07-627">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="52c07-628">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="52c07-628">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="52c07-629">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="52c07-629">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="52c07-630">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="52c07-630">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="52c07-631">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="52c07-631">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="52c07-632">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-632">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="52c07-633">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="52c07-633">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="52c07-634">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-634">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="52c07-635">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-635">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="52c07-636">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-636">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="52c07-637">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-637">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="52c07-638">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-638">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="52c07-639">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-639">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="52c07-640">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="52c07-640">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="52c07-641">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-641">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="52c07-642">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="52c07-642">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="52c07-643">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-643">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="52c07-644">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-644">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="52c07-645">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="52c07-645">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="52c07-646">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="52c07-646">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="52c07-647">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-647">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="52c07-648">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="52c07-648">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="52c07-649">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="52c07-649">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="52c07-650">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-650">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="52c07-651">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="52c07-651">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="52c07-652">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="52c07-652">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="52c07-653">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-653">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="52c07-654">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="52c07-654">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="52c07-655">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="52c07-655">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="52c07-656">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-656">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="52c07-657">`--exclude-launch-settings` — исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="52c07-657">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="52c07-658">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="52c07-658">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="52c07-659">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="52c07-659">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="52c07-660">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-660">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="52c07-661">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="52c07-661">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="52c07-662">`--no-https` — проекту не требуется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="52c07-662">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="52c07-663">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="52c07-663">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="52c07-664">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="52c07-664">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="52c07-665">**page**</span><span class="sxs-lookup"><span data-stu-id="52c07-665">**page**</span></span>

<span data-ttu-id="52c07-666">`-na|--namespace <NAMESPACE_NAME>` — пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="52c07-666">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="52c07-667">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="52c07-667">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="52c07-668">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="52c07-668">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="52c07-669">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="52c07-669">**viewimports**</span></span>

<span data-ttu-id="52c07-670">`-na|--namespace <NAMESPACE_NAME>` — пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="52c07-670">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="52c07-671">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="52c07-671">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="52c07-672">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="52c07-672">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="52c07-673">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="52c07-673">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="52c07-674">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="52c07-674">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="52c07-675">**classlib**</span><span class="sxs-lookup"><span data-stu-id="52c07-675">**classlib**</span></span>

<span data-ttu-id="52c07-676">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="52c07-676">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="52c07-677">Значения: `netcoreapp2.0` для создания библиотеки классов .NET Core или `netstandard2.0` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="52c07-677">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="52c07-678">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="52c07-678">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="52c07-679">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="52c07-679">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="52c07-680">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="52c07-680">**mstest, xunit**</span></span>

<span data-ttu-id="52c07-681">`-p|--enable-pack` — включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="52c07-681">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="52c07-682">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="52c07-682">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="52c07-683">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="52c07-683">**globaljson**</span></span>

<span data-ttu-id="52c07-684">`--sdk-version <VERSION_NUMBER>` — задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="52c07-684">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="52c07-685">**web**</span><span class="sxs-lookup"><span data-stu-id="52c07-685">**web**</span></span>

<span data-ttu-id="52c07-686">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="52c07-686">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="52c07-687">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="52c07-687">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="52c07-688">**webapi**</span><span class="sxs-lookup"><span data-stu-id="52c07-688">**webapi**</span></span>

<span data-ttu-id="52c07-689">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="52c07-689">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="52c07-690">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="52c07-690">The possible values are:</span></span>

- <span data-ttu-id="52c07-691">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="52c07-691">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="52c07-692">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="52c07-692">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="52c07-693">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="52c07-693">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="52c07-694">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="52c07-694">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="52c07-695">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="52c07-695">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="52c07-696">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-696">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="52c07-697">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="52c07-697">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="52c07-698">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-698">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="52c07-699">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-699">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="52c07-700">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="52c07-700">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="52c07-701">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-701">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="52c07-702">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="52c07-702">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="52c07-703">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-703">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="52c07-704">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-704">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="52c07-705">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="52c07-705">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="52c07-706">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="52c07-706">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="52c07-707">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-707">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="52c07-708">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="52c07-708">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="52c07-709">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="52c07-709">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="52c07-710">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-710">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="52c07-711">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="52c07-711">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="52c07-712">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="52c07-712">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="52c07-713">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-713">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="52c07-714">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="52c07-714">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="52c07-715">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="52c07-715">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="52c07-716">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-716">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="52c07-717">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="52c07-717">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="52c07-718">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="52c07-718">**mvc, razor**</span></span>

<span data-ttu-id="52c07-719">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="52c07-719">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="52c07-720">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="52c07-720">The possible values are:</span></span>

- <span data-ttu-id="52c07-721">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="52c07-721">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="52c07-722">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="52c07-722">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="52c07-723">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="52c07-723">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="52c07-724">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="52c07-724">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="52c07-725">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="52c07-725">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="52c07-726">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="52c07-726">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="52c07-727">`--aad-b2c-instance <INSTANCE>` — экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="52c07-727">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="52c07-728">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-728">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="52c07-729">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="52c07-729">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="52c07-730">`-ssp|--susi-policy-id <ID>` — идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-730">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="52c07-731">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-731">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="52c07-732">`-rp|--reset-password-policy-id <ID>` — идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-732">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="52c07-733">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-733">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="52c07-734">`-ep|--edit-profile-policy-id <ID>` — идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-734">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="52c07-735">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-735">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="52c07-736">`--aad-instance <INSTANCE>` — экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="52c07-736">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="52c07-737">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-737">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="52c07-738">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="52c07-738">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="52c07-739">`--client-id <ID>` — идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="52c07-739">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="52c07-740">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-740">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="52c07-741">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="52c07-741">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="52c07-742">`--domain <DOMAIN>` — домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="52c07-742">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="52c07-743">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-743">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="52c07-744">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="52c07-744">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="52c07-745">`--tenant-id <ID>` — идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="52c07-745">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="52c07-746">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-746">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="52c07-747">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="52c07-747">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="52c07-748">`--callback-path <PATH>` — путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="52c07-748">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="52c07-749">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-749">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="52c07-750">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="52c07-750">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="52c07-751">`-r|--org-read-access` — предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="52c07-751">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="52c07-752">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="52c07-752">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="52c07-753">`--use-launch-settings` — включает файл *launchSettings.json* в создаваемые выходные данные шаблона.</span><span class="sxs-lookup"><span data-stu-id="52c07-753">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="52c07-754">`--use-browserlink` — включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="52c07-754">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="52c07-755">`-uld|--use-local-db` — указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="52c07-755">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="52c07-756">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="52c07-756">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="52c07-757">`--no-restore` — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="52c07-757">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="52c07-758">**page**</span><span class="sxs-lookup"><span data-stu-id="52c07-758">**page**</span></span>

<span data-ttu-id="52c07-759">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="52c07-759">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="52c07-760">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="52c07-760">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="52c07-761">`-np|--no-pagemodel` — создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="52c07-761">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="52c07-762">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="52c07-762">**viewimports**</span></span>

<span data-ttu-id="52c07-763">`-na|--namespace <NAMESPACE_NAME>` — пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="52c07-763">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="52c07-764">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="52c07-764">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="52c07-765">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="52c07-765">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="52c07-766">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="52c07-766">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="52c07-767">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="52c07-767">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="52c07-768">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="52c07-768">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="52c07-769">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="52c07-769">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="52c07-770">**classlib**</span><span class="sxs-lookup"><span data-stu-id="52c07-770">**classlib**</span></span>

<span data-ttu-id="52c07-771">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="52c07-771">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="52c07-772">Значения: `netcoreapp1.0`, `netcoreapp1.1` или с `netstandard1.0` по `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="52c07-772">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="52c07-773">Значение по умолчанию — `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="52c07-773">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="52c07-774">**mvc**</span><span class="sxs-lookup"><span data-stu-id="52c07-774">**mvc**</span></span>

<span data-ttu-id="52c07-775">`-f|--framework <FRAMEWORK>` — указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="52c07-775">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="52c07-776">Значения: `netcoreapp1.0` или `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="52c07-776">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="52c07-777">Значение по умолчанию — `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="52c07-777">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="52c07-778">`-au|--auth <AUTHENTICATION_TYPE>` — тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="52c07-778">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="52c07-779">Значения: `None` или `Individual`.</span><span class="sxs-lookup"><span data-stu-id="52c07-779">Values: `None` or `Individual`.</span></span> <span data-ttu-id="52c07-780">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="52c07-780">The default value is `None`.</span></span>

<span data-ttu-id="52c07-781">`-uld|--use-local-db` — указывает, следует ли использовать LocalDB вместо SQLite.</span><span class="sxs-lookup"><span data-stu-id="52c07-781">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="52c07-782">Значения: `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="52c07-782">Values: `true` or `false`.</span></span> <span data-ttu-id="52c07-783">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="52c07-783">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="52c07-784">Примеры</span><span class="sxs-lookup"><span data-stu-id="52c07-784">Examples</span></span>

<span data-ttu-id="52c07-785">Создайте проект консольного приложения на C#, указав имя шаблона:</span><span class="sxs-lookup"><span data-stu-id="52c07-785">Create a C# console application project by specifying the template name:</span></span>

`dotnet new "Console Application"`

<span data-ttu-id="52c07-786">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="52c07-786">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="52c07-787">Создание проекта библиотеки классов .NET Standard в указанном каталоге (доступно только при использовании пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="52c07-787">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="52c07-788">Создайте новый проект MVC ASP.NET Core C# в текущем каталоге без проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="52c07-788">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="52c07-789">Создайте новый проект xUnit:</span><span class="sxs-lookup"><span data-stu-id="52c07-789">Create a new xUnit project:</span></span>

`dotnet new xunit`

<span data-ttu-id="52c07-790">Перечислите все шаблоны, доступные для MVC:</span><span class="sxs-lookup"><span data-stu-id="52c07-790">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="52c07-791">Список всех шаблонов, соответствующих подстроке *we*.</span><span class="sxs-lookup"><span data-stu-id="52c07-791">List all templates matching the *we* substring.</span></span> <span data-ttu-id="52c07-792">Точное совпадение не найдено, поэтому сравнение подстрок выполняется по короткому имени и столбцам имен.</span><span class="sxs-lookup"><span data-stu-id="52c07-792">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

`dotnet new we -l`

<span data-ttu-id="52c07-793">Попытайтесь вызвать шаблон, соответствующий *ng*.</span><span class="sxs-lookup"><span data-stu-id="52c07-793">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="52c07-794">Если точное совпадение не найдено, выведите шаблоны с частичным совпадением.</span><span class="sxs-lookup"><span data-stu-id="52c07-794">If a single match can't be determined, list the templates that are partial matches.</span></span>

`dotnet new ng`

<span data-ttu-id="52c07-795">Установите версию 2.0 шаблонов одностраничного приложения для ASP.NET Core (параметр команды доступен в .NET Core SDK 1.1 и более поздних версиях):</span><span class="sxs-lookup"><span data-stu-id="52c07-795">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="52c07-796">Создайте *global.json* в текущем каталоге, указав версию пакета SDK 2.0.0 (доступно только для пакета SDK для .NET Core 2.0 или более поздней версии):</span><span class="sxs-lookup"><span data-stu-id="52c07-796">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="52c07-797">См. также</span><span class="sxs-lookup"><span data-stu-id="52c07-797">See also</span></span>

- [<span data-ttu-id="52c07-798">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="52c07-798">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="52c07-799">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="52c07-799">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)
- [<span data-ttu-id="52c07-800">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="52c07-800">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="52c07-801">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="52c07-801">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
