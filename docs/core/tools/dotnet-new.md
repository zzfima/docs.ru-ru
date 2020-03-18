---
title: Команда dotnet new
description: Команда dotnet new создает проекты .NET Core на основе указанного шаблона.
ms.date: 02/13/2020
ms.openlocfilehash: d3c609419596b123f5bfb3ca85cf292a61154a70
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398031"
---
# <a name="dotnet-new"></a><span data-ttu-id="f2981-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="f2981-103">dotnet new</span></span>

<span data-ttu-id="f2981-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="f2981-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="f2981-105">Имя</span><span class="sxs-lookup"><span data-stu-id="f2981-105">Name</span></span>

<span data-ttu-id="f2981-106">`dotnet new` - создает проект, файл конфигурации или решений на основе указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="f2981-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f2981-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f2981-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name]
    [--nuget-source] [-o|--output] [-u|--uninstall] [--update-apply] [--update-check] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

## <a name="description"></a><span data-ttu-id="f2981-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="f2981-108">Description</span></span>

<span data-ttu-id="f2981-109">Команда `dotnet new` создает проект .NET Core или другие артефакты на основе шаблона.</span><span class="sxs-lookup"><span data-stu-id="f2981-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="f2981-110">Она вызывает [подсистему шаблонов](https://github.com/dotnet/templating), чтобы создать артефакты на диске на основе заданных параметров и шаблона.</span><span class="sxs-lookup"><span data-stu-id="f2981-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="f2981-111">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f2981-111">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="f2981-112">Шаблон для создания экземпляров при вызове команды.</span><span class="sxs-lookup"><span data-stu-id="f2981-112">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="f2981-113">Каждый шаблон может иметь отдельные параметры, доступные для передачи.</span><span class="sxs-lookup"><span data-stu-id="f2981-113">Each template might have specific options you can pass.</span></span> <span data-ttu-id="f2981-114">Дополнительные сведения см. в разделе [Параметры шаблона](#template-options).</span><span class="sxs-lookup"><span data-stu-id="f2981-114">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="f2981-115">Вы можете запустить `dotnet new --list`, чтобы просмотреть список всех установленных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="f2981-115">You can run `dotnet new --list` to see a list of all installed templates.</span></span> <span data-ttu-id="f2981-116">Если значение `TEMPLATE` не совпадает в точности с текстом в столбце **Шаблоны** или **Короткое имя** из возвращаемой таблицы, для этих двух столбцов выполняется поиск совпадений в подстроках.</span><span class="sxs-lookup"><span data-stu-id="f2981-116">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="f2981-117">Начиная с пакета SDK для .NET Core 3.0, интерфейс командной строки выполняет поиск шаблонов в NuGet.org при вызове команды `dotnet new` в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="f2981-117">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="f2981-118">если CLI не может найти совпадение шаблона при вызове `dotnet new`, даже частичное;</span><span class="sxs-lookup"><span data-stu-id="f2981-118">If the CLI can’t find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="f2981-119">если доступна более новая версия шаблона.</span><span class="sxs-lookup"><span data-stu-id="f2981-119">If there’s a newer version of the template available.</span></span> <span data-ttu-id="f2981-120">В этом случае проект или артефакт создается, но CLI предупреждает об обновленной версии шаблона.</span><span class="sxs-lookup"><span data-stu-id="f2981-120">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="f2981-121">Команда содержит список шаблонов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f2981-121">The command contains a default list of templates.</span></span> <span data-ttu-id="f2981-122">Используйте `dotnet new -l`, чтобы получить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="f2981-122">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="f2981-123">В следующей таблице показаны шаблоны, которые устанавливаются с пакетом SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f2981-123">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="f2981-124">Язык по умолчанию для шаблона указан внутри квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="f2981-124">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="f2981-125">Нажмите на ссылку с коротким названием, чтобы увидеть конкретные параметры шаблона.</span><span class="sxs-lookup"><span data-stu-id="f2981-125">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="f2981-126">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="f2981-126">Templates</span></span>                                    | <span data-ttu-id="f2981-127">короткое имя;</span><span class="sxs-lookup"><span data-stu-id="f2981-127">Short name</span></span>                      | <span data-ttu-id="f2981-128">Язык</span><span class="sxs-lookup"><span data-stu-id="f2981-128">Language</span></span>     | <span data-ttu-id="f2981-129">Теги</span><span class="sxs-lookup"><span data-stu-id="f2981-129">Tags</span></span>                                  | <span data-ttu-id="f2981-130">Введенный</span><span class="sxs-lookup"><span data-stu-id="f2981-130">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="f2981-131">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="f2981-131">Console Application</span></span>                          | [<span data-ttu-id="f2981-132">Консоль</span><span class="sxs-lookup"><span data-stu-id="f2981-132">console</span></span>](#console)             | <span data-ttu-id="f2981-133">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="f2981-133">[C#], F#, VB</span></span> | <span data-ttu-id="f2981-134">Общее/консоль</span><span class="sxs-lookup"><span data-stu-id="f2981-134">Common/Console</span></span>                        | <span data-ttu-id="f2981-135">1,0</span><span class="sxs-lookup"><span data-stu-id="f2981-135">1.0</span></span>        |
| <span data-ttu-id="f2981-136">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="f2981-136">Class library</span></span>                                | [<span data-ttu-id="f2981-137">classlib</span><span class="sxs-lookup"><span data-stu-id="f2981-137">classlib</span></span>](#classlib)           | <span data-ttu-id="f2981-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="f2981-138">[C#], F#, VB</span></span> | <span data-ttu-id="f2981-139">Общее/библиотека</span><span class="sxs-lookup"><span data-stu-id="f2981-139">Common/Library</span></span>                        | <span data-ttu-id="f2981-140">1,0</span><span class="sxs-lookup"><span data-stu-id="f2981-140">1.0</span></span>        |
| <span data-ttu-id="f2981-141">Приложение WPF</span><span class="sxs-lookup"><span data-stu-id="f2981-141">WPF Application</span></span>                              | [<span data-ttu-id="f2981-142">wpf</span><span class="sxs-lookup"><span data-stu-id="f2981-142">wpf</span></span>](#wpf)                     | <span data-ttu-id="f2981-143">[C#]</span><span class="sxs-lookup"><span data-stu-id="f2981-143">[C#]</span></span>         | <span data-ttu-id="f2981-144">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="f2981-144">Common/WPF</span></span>                            | <span data-ttu-id="f2981-145">3,0</span><span class="sxs-lookup"><span data-stu-id="f2981-145">3.0</span></span>        |
| <span data-ttu-id="f2981-146">Библиотека классов WPF</span><span class="sxs-lookup"><span data-stu-id="f2981-146">WPF Class library</span></span>                            | [<span data-ttu-id="f2981-147">wpflib</span><span class="sxs-lookup"><span data-stu-id="f2981-147">wpflib</span></span>](#wpf)                  | <span data-ttu-id="f2981-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="f2981-148">[C#]</span></span>         | <span data-ttu-id="f2981-149">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="f2981-149">Common/WPF</span></span>                            | <span data-ttu-id="f2981-150">3,0</span><span class="sxs-lookup"><span data-stu-id="f2981-150">3.0</span></span>        |
| <span data-ttu-id="f2981-151">Библиотека настраиваемых элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="f2981-151">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="f2981-152">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="f2981-152">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="f2981-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="f2981-153">[C#]</span></span>         | <span data-ttu-id="f2981-154">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="f2981-154">Common/WPF</span></span>                            | <span data-ttu-id="f2981-155">3,0</span><span class="sxs-lookup"><span data-stu-id="f2981-155">3.0</span></span>        |
| <span data-ttu-id="f2981-156">Библиотека пользовательских элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="f2981-156">WPF User Control Library</span></span>                     | [<span data-ttu-id="f2981-157">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="f2981-157">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="f2981-158">[C#]</span><span class="sxs-lookup"><span data-stu-id="f2981-158">[C#]</span></span>         | <span data-ttu-id="f2981-159">Общее/WPF</span><span class="sxs-lookup"><span data-stu-id="f2981-159">Common/WPF</span></span>                            | <span data-ttu-id="f2981-160">3,0</span><span class="sxs-lookup"><span data-stu-id="f2981-160">3.0</span></span>        |
| <span data-ttu-id="f2981-161">Приложение Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="f2981-161">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="f2981-162">winforms</span><span class="sxs-lookup"><span data-stu-id="f2981-162">winforms</span></span>](#winforms)           | <span data-ttu-id="f2981-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="f2981-163">[C#]</span></span>         | <span data-ttu-id="f2981-164">Общее (WinForms)</span><span class="sxs-lookup"><span data-stu-id="f2981-164">Common/WinForms</span></span>                       | <span data-ttu-id="f2981-165">3,0</span><span class="sxs-lookup"><span data-stu-id="f2981-165">3.0</span></span>        |
| <span data-ttu-id="f2981-166">Библиотека классов для Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="f2981-166">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="f2981-167">winformslib</span><span class="sxs-lookup"><span data-stu-id="f2981-167">winformslib</span></span>](#winforms)        | <span data-ttu-id="f2981-168">[C#]</span><span class="sxs-lookup"><span data-stu-id="f2981-168">[C#]</span></span>         | <span data-ttu-id="f2981-169">Общее (WinForms)</span><span class="sxs-lookup"><span data-stu-id="f2981-169">Common/WinForms</span></span>                       | <span data-ttu-id="f2981-170">3,0</span><span class="sxs-lookup"><span data-stu-id="f2981-170">3.0</span></span>        |
| <span data-ttu-id="f2981-171">Служба Worker Service</span><span class="sxs-lookup"><span data-stu-id="f2981-171">Worker Service</span></span>                               | [<span data-ttu-id="f2981-172">рабочая роль</span><span class="sxs-lookup"><span data-stu-id="f2981-172">worker</span></span>](#web-others)           | <span data-ttu-id="f2981-173">[C#]</span><span class="sxs-lookup"><span data-stu-id="f2981-173">[C#]</span></span>         | <span data-ttu-id="f2981-174">Общее/Рабочая роль/Веб</span><span class="sxs-lookup"><span data-stu-id="f2981-174">Common/Worker/Web</span></span>                     | <span data-ttu-id="f2981-175">3,0</span><span class="sxs-lookup"><span data-stu-id="f2981-175">3.0</span></span>        |
| <span data-ttu-id="f2981-176">Проект модульного теста</span><span class="sxs-lookup"><span data-stu-id="f2981-176">Unit Test Project</span></span>                            | [<span data-ttu-id="f2981-177">mstest</span><span class="sxs-lookup"><span data-stu-id="f2981-177">mstest</span></span>](#test)                 | <span data-ttu-id="f2981-178">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="f2981-178">[C#], F#, VB</span></span> | <span data-ttu-id="f2981-179">Тест/MSTest</span><span class="sxs-lookup"><span data-stu-id="f2981-179">Test/MSTest</span></span>                           | <span data-ttu-id="f2981-180">1,0</span><span class="sxs-lookup"><span data-stu-id="f2981-180">1.0</span></span>        |
| <span data-ttu-id="f2981-181">Тестовый проект NUnit 3</span><span class="sxs-lookup"><span data-stu-id="f2981-181">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="f2981-182">nunit</span><span class="sxs-lookup"><span data-stu-id="f2981-182">nunit</span></span>](#nunit)                  | <span data-ttu-id="f2981-183">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="f2981-183">[C#], F#, VB</span></span> | <span data-ttu-id="f2981-184">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="f2981-184">Test/NUnit</span></span>                            | <span data-ttu-id="f2981-185">2.1.400</span><span class="sxs-lookup"><span data-stu-id="f2981-185">2.1.400</span></span>    |
| <span data-ttu-id="f2981-186">Элемент теста NUnit 3</span><span class="sxs-lookup"><span data-stu-id="f2981-186">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="f2981-187">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="f2981-187">[C#], F#, VB</span></span> | <span data-ttu-id="f2981-188">Тест/NUnit</span><span class="sxs-lookup"><span data-stu-id="f2981-188">Test/NUnit</span></span>                            | <span data-ttu-id="f2981-189">2.2</span><span class="sxs-lookup"><span data-stu-id="f2981-189">2.2</span></span>        |
| <span data-ttu-id="f2981-190">Тестовый проект xUnit</span><span class="sxs-lookup"><span data-stu-id="f2981-190">xUnit Test Project</span></span>                           | [<span data-ttu-id="f2981-191">xunit</span><span class="sxs-lookup"><span data-stu-id="f2981-191">xunit</span></span>](#test)                  | <span data-ttu-id="f2981-192">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="f2981-192">[C#], F#, VB</span></span> | <span data-ttu-id="f2981-193">Тест/xUnit</span><span class="sxs-lookup"><span data-stu-id="f2981-193">Test/xUnit</span></span>                            | <span data-ttu-id="f2981-194">1,0</span><span class="sxs-lookup"><span data-stu-id="f2981-194">1.0</span></span>        |
| <span data-ttu-id="f2981-195">Компонент Razor</span><span class="sxs-lookup"><span data-stu-id="f2981-195">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="f2981-196">[C#]</span><span class="sxs-lookup"><span data-stu-id="f2981-196">[C#]</span></span>         | <span data-ttu-id="f2981-197">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f2981-197">Web/ASP.NET</span></span>                           | <span data-ttu-id="f2981-198">3,0</span><span class="sxs-lookup"><span data-stu-id="f2981-198">3.0</span></span>        |
| <span data-ttu-id="f2981-199">Страница Razor</span><span class="sxs-lookup"><span data-stu-id="f2981-199">Razor Page</span></span>                                   | [<span data-ttu-id="f2981-200">page</span><span class="sxs-lookup"><span data-stu-id="f2981-200">page</span></span>](#page)                   | <span data-ttu-id="f2981-201">[C#]</span><span class="sxs-lookup"><span data-stu-id="f2981-201">[C#]</span></span>         | <span data-ttu-id="f2981-202">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f2981-202">Web/ASP.NET</span></span>                           | <span data-ttu-id="f2981-203">2.0</span><span class="sxs-lookup"><span data-stu-id="f2981-203">2.0</span></span>        |
| <span data-ttu-id="f2981-204">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="f2981-204">MVC ViewImports</span></span>                              | [<span data-ttu-id="f2981-205">viewimports</span><span class="sxs-lookup"><span data-stu-id="f2981-205">viewimports</span></span>](#namespace)       | <span data-ttu-id="f2981-206">[C#]</span><span class="sxs-lookup"><span data-stu-id="f2981-206">[C#]</span></span>         | <span data-ttu-id="f2981-207">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f2981-207">Web/ASP.NET</span></span>                           | <span data-ttu-id="f2981-208">2.0</span><span class="sxs-lookup"><span data-stu-id="f2981-208">2.0</span></span>        |
| <span data-ttu-id="f2981-209">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="f2981-209">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="f2981-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="f2981-210">[C#]</span></span>         | <span data-ttu-id="f2981-211">Веб/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f2981-211">Web/ASP.NET</span></span>                           | <span data-ttu-id="f2981-212">2.0</span><span class="sxs-lookup"><span data-stu-id="f2981-212">2.0</span></span>        |
| <span data-ttu-id="f2981-213">Серверное приложение Blazor</span><span class="sxs-lookup"><span data-stu-id="f2981-213">Blazor Server App</span></span>                            | [<span data-ttu-id="f2981-214">blazorserver</span><span class="sxs-lookup"><span data-stu-id="f2981-214">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="f2981-215">[C#]</span><span class="sxs-lookup"><span data-stu-id="f2981-215">[C#]</span></span>         | <span data-ttu-id="f2981-216">Веб/Blazor</span><span class="sxs-lookup"><span data-stu-id="f2981-216">Web/Blazor</span></span>                            | <span data-ttu-id="f2981-217">3,0</span><span class="sxs-lookup"><span data-stu-id="f2981-217">3.0</span></span>        |
| <span data-ttu-id="f2981-218">Пустой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f2981-218">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="f2981-219">web</span><span class="sxs-lookup"><span data-stu-id="f2981-219">web</span></span>](#web)                     | <span data-ttu-id="f2981-220">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="f2981-220">[C#], F#</span></span>     | <span data-ttu-id="f2981-221">Веб/пусто</span><span class="sxs-lookup"><span data-stu-id="f2981-221">Web/Empty</span></span>                             | <span data-ttu-id="f2981-222">1,0</span><span class="sxs-lookup"><span data-stu-id="f2981-222">1.0</span></span>        |
| <span data-ttu-id="f2981-223">Веб-приложение ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="f2981-223">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="f2981-224">mvc</span><span class="sxs-lookup"><span data-stu-id="f2981-224">mvc</span></span>](#web-options)             | <span data-ttu-id="f2981-225">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="f2981-225">[C#], F#</span></span>     | <span data-ttu-id="f2981-226">Веб/MVC</span><span class="sxs-lookup"><span data-stu-id="f2981-226">Web/MVC</span></span>                               | <span data-ttu-id="f2981-227">1,0</span><span class="sxs-lookup"><span data-stu-id="f2981-227">1.0</span></span>        |
| <span data-ttu-id="f2981-228">Веб-приложение ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f2981-228">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="f2981-229">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="f2981-229">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="f2981-230">[C#]</span><span class="sxs-lookup"><span data-stu-id="f2981-230">[C#]</span></span>         | <span data-ttu-id="f2981-231">Веб/MVC и Razor Pages</span><span class="sxs-lookup"><span data-stu-id="f2981-231">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="f2981-232">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="f2981-232">2.2, 2.0</span></span>   |
| <span data-ttu-id="f2981-233">ASP.NET Core с Angular</span><span class="sxs-lookup"><span data-stu-id="f2981-233">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="f2981-234">angular</span><span class="sxs-lookup"><span data-stu-id="f2981-234">angular</span></span>](#spa)                 | <span data-ttu-id="f2981-235">[C#]</span><span class="sxs-lookup"><span data-stu-id="f2981-235">[C#]</span></span>         | <span data-ttu-id="f2981-236">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="f2981-236">Web/MVC/SPA</span></span>                           | <span data-ttu-id="f2981-237">2.0</span><span class="sxs-lookup"><span data-stu-id="f2981-237">2.0</span></span>        |
| <span data-ttu-id="f2981-238">ASP.NET Core с React.js</span><span class="sxs-lookup"><span data-stu-id="f2981-238">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="f2981-239">react</span><span class="sxs-lookup"><span data-stu-id="f2981-239">react</span></span>](#spa)                   | <span data-ttu-id="f2981-240">[C#]</span><span class="sxs-lookup"><span data-stu-id="f2981-240">[C#]</span></span>         | <span data-ttu-id="f2981-241">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="f2981-241">Web/MVC/SPA</span></span>                           | <span data-ttu-id="f2981-242">2.0</span><span class="sxs-lookup"><span data-stu-id="f2981-242">2.0</span></span>        |
| <span data-ttu-id="f2981-243">ASP.NET Core с React.js и Redux</span><span class="sxs-lookup"><span data-stu-id="f2981-243">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="f2981-244">reactredux</span><span class="sxs-lookup"><span data-stu-id="f2981-244">reactredux</span></span>](#reactredux)       | <span data-ttu-id="f2981-245">[C#]</span><span class="sxs-lookup"><span data-stu-id="f2981-245">[C#]</span></span>         | <span data-ttu-id="f2981-246">MVC/Веб/SPA</span><span class="sxs-lookup"><span data-stu-id="f2981-246">Web/MVC/SPA</span></span>                           | <span data-ttu-id="f2981-247">2.0</span><span class="sxs-lookup"><span data-stu-id="f2981-247">2.0</span></span>        |
| <span data-ttu-id="f2981-248">Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="f2981-248">Razor Class Library</span></span>                          | [<span data-ttu-id="f2981-249">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="f2981-249">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="f2981-250">[C#]</span><span class="sxs-lookup"><span data-stu-id="f2981-250">[C#]</span></span>         | <span data-ttu-id="f2981-251">Веб/Razor/Библиотека/Библиотека классов Razor</span><span class="sxs-lookup"><span data-stu-id="f2981-251">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="f2981-252">2.1</span><span class="sxs-lookup"><span data-stu-id="f2981-252">2.1</span></span>        |
| <span data-ttu-id="f2981-253">Веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f2981-253">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="f2981-254">webapi</span><span class="sxs-lookup"><span data-stu-id="f2981-254">webapi</span></span>](#webapi)               | <span data-ttu-id="f2981-255">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="f2981-255">[C#], F#</span></span>     | <span data-ttu-id="f2981-256">Веб/веб-API</span><span class="sxs-lookup"><span data-stu-id="f2981-256">Web/WebAPI</span></span>                            | <span data-ttu-id="f2981-257">1,0</span><span class="sxs-lookup"><span data-stu-id="f2981-257">1.0</span></span>        |
| <span data-ttu-id="f2981-258">Служба ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="f2981-258">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="f2981-259">grpc</span><span class="sxs-lookup"><span data-stu-id="f2981-259">grpc</span></span>](#web-others)             | <span data-ttu-id="f2981-260">[C#]</span><span class="sxs-lookup"><span data-stu-id="f2981-260">[C#]</span></span>         | <span data-ttu-id="f2981-261">Веб/gRPC</span><span class="sxs-lookup"><span data-stu-id="f2981-261">Web/gRPC</span></span>                              | <span data-ttu-id="f2981-262">3,0</span><span class="sxs-lookup"><span data-stu-id="f2981-262">3.0</span></span>        |
| <span data-ttu-id="f2981-263">Файл буфера протокола</span><span class="sxs-lookup"><span data-stu-id="f2981-263">Protocol Buffer File</span></span>                         | [<span data-ttu-id="f2981-264">proto</span><span class="sxs-lookup"><span data-stu-id="f2981-264">proto</span></span>](#namespace)             |              | <span data-ttu-id="f2981-265">Веб/gRPC</span><span class="sxs-lookup"><span data-stu-id="f2981-265">Web/gRPC</span></span>                              | <span data-ttu-id="f2981-266">3,0</span><span class="sxs-lookup"><span data-stu-id="f2981-266">3.0</span></span>        |
| <span data-ttu-id="f2981-267">Файл dotnet gitignore</span><span class="sxs-lookup"><span data-stu-id="f2981-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="f2981-268">Config</span><span class="sxs-lookup"><span data-stu-id="f2981-268">Config</span></span>                                | <span data-ttu-id="f2981-269">3,0</span><span class="sxs-lookup"><span data-stu-id="f2981-269">3.0</span></span>        |
| <span data-ttu-id="f2981-270">Файл global.json</span><span class="sxs-lookup"><span data-stu-id="f2981-270">global.json file</span></span>                             | [<span data-ttu-id="f2981-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="f2981-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="f2981-272">Config</span><span class="sxs-lookup"><span data-stu-id="f2981-272">Config</span></span>                                | <span data-ttu-id="f2981-273">2.0</span><span class="sxs-lookup"><span data-stu-id="f2981-273">2.0</span></span>        |
| <span data-ttu-id="f2981-274">Конфигурация NuGet</span><span class="sxs-lookup"><span data-stu-id="f2981-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="f2981-275">Config</span><span class="sxs-lookup"><span data-stu-id="f2981-275">Config</span></span>                                | <span data-ttu-id="f2981-276">1,0</span><span class="sxs-lookup"><span data-stu-id="f2981-276">1.0</span></span>        |
| <span data-ttu-id="f2981-277">Локальное средство файла манифеста dotnet</span><span class="sxs-lookup"><span data-stu-id="f2981-277">dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="f2981-278">Config</span><span class="sxs-lookup"><span data-stu-id="f2981-278">Config</span></span>                                | <span data-ttu-id="f2981-279">3,0</span><span class="sxs-lookup"><span data-stu-id="f2981-279">3.0</span></span>        |
| <span data-ttu-id="f2981-280">Файл веб-конфигурации</span><span class="sxs-lookup"><span data-stu-id="f2981-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="f2981-281">Config</span><span class="sxs-lookup"><span data-stu-id="f2981-281">Config</span></span>                                | <span data-ttu-id="f2981-282">1,0</span><span class="sxs-lookup"><span data-stu-id="f2981-282">1.0</span></span>        |
| <span data-ttu-id="f2981-283">Файл решения</span><span class="sxs-lookup"><span data-stu-id="f2981-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="f2981-284">Решение</span><span class="sxs-lookup"><span data-stu-id="f2981-284">Solution</span></span>                              | <span data-ttu-id="f2981-285">1,0</span><span class="sxs-lookup"><span data-stu-id="f2981-285">1.0</span></span>        |

## <a name="options"></a><span data-ttu-id="f2981-286">Параметры</span><span class="sxs-lookup"><span data-stu-id="f2981-286">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="f2981-287">Отображает сводку того, что произойдет, если выполнить команду.</span><span class="sxs-lookup"><span data-stu-id="f2981-287">Displays a summary of what would happen if the given command were run.</span></span> <span data-ttu-id="f2981-288">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="f2981-288">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="f2981-289">Принудительное создание содержимого, даже если при этом изменяются существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="f2981-289">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="f2981-290">Это необходимо, когда выбранный шаблон переопределяет существующие файлы в выходном каталоге.</span><span class="sxs-lookup"><span data-stu-id="f2981-290">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="f2981-291">Распечатывает справку для команды.</span><span class="sxs-lookup"><span data-stu-id="f2981-291">Prints out help for the command.</span></span> <span data-ttu-id="f2981-292">Его можно вызвать для самой команды `dotnet new` или для любого шаблона.</span><span class="sxs-lookup"><span data-stu-id="f2981-292">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="f2981-293">Например, `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="f2981-293">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="f2981-294">Устанавливает пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="f2981-294">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="f2981-295">Если вы хотите установить предварительную версию пакета шаблонов, необходимо указать версию в формате `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="f2981-295">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="f2981-296">По умолчанию `dotnet new` передает \* для версии, что указывает на последнюю стабильную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="f2981-296">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="f2981-297">См. пример в разделе [Примеры](#examples).</span><span class="sxs-lookup"><span data-stu-id="f2981-297">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="f2981-298">Если при выполнении этой команды версия шаблона уже была установлена, шаблон будет обновлен до указанной версии или до последней стабильной версии, если версию не указано.</span><span class="sxs-lookup"><span data-stu-id="f2981-298">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="f2981-299">Сведения о создании пользовательских шаблонов см. в статье [Пользовательские шаблоны для команды dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="f2981-299">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="f2981-300">Перечисляет шаблоны с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="f2981-300">Lists templates containing the specified name.</span></span> <span data-ttu-id="f2981-301">Если имя не указано, перечисляются все шаблоны.</span><span class="sxs-lookup"><span data-stu-id="f2981-301">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="f2981-302">Язык создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="f2981-302">The language of the template to create.</span></span> <span data-ttu-id="f2981-303">Допустимый язык зависит от шаблона (см. значения по умолчанию в разделе об [аргументах](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="f2981-303">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="f2981-304">Не является допустимым для некоторых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="f2981-304">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="f2981-305">Некоторые оболочки интерпретируют `#` как специальный символ.</span><span class="sxs-lookup"><span data-stu-id="f2981-305">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="f2981-306">В этих случаях заключите значение языкового параметра в кавычки.</span><span class="sxs-lookup"><span data-stu-id="f2981-306">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="f2981-307">Например, `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="f2981-307">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="f2981-308">Имя создаваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="f2981-308">The name for the created output.</span></span> <span data-ttu-id="f2981-309">Если имя не указано, используется имя текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="f2981-309">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source`**

  <span data-ttu-id="f2981-310">Задает источник пакетов NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="f2981-310">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="f2981-311">Доступно начиная с пакета SDK для .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="f2981-311">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="f2981-312">Расположение, в котором размещаются созданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="f2981-312">Location to place the generated output.</span></span> <span data-ttu-id="f2981-313">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="f2981-313">The default is the current directory.</span></span>

- **`--type`**

  <span data-ttu-id="f2981-314">Фильтрует шаблоны по доступным типам.</span><span class="sxs-lookup"><span data-stu-id="f2981-314">Filters templates based on available types.</span></span> <span data-ttu-id="f2981-315">Предопределенные значения: "project", "item" или "other".</span><span class="sxs-lookup"><span data-stu-id="f2981-315">Predefined values are "project", "item", or "other".</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="f2981-316">Удаляет пакет шаблона из указанного пути `PATH` или по указанному идентификатору `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="f2981-316">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="f2981-317">Если значение `<PATH|NUGET_ID>` не указано, отображаются все установленные пакеты шаблонов и связанные с ними шаблоны.</span><span class="sxs-lookup"><span data-stu-id="f2981-317">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="f2981-318">Не указывайте номер версии, если задаете `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="f2981-318">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="f2981-319">Если вы не указываете параметр в этой опции, команда перечисляет установленные шаблоны и подробные сведения о них.</span><span class="sxs-lookup"><span data-stu-id="f2981-319">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="f2981-320">Чтобы удалить шаблон с помощью `PATH`, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="f2981-320">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="f2981-321">Например, *C:/Users/\<ПОЛЬЗОВАТЕЛЬ>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* — нет.</span><span class="sxs-lookup"><span data-stu-id="f2981-321">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="f2981-322">Путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="f2981-322">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="f2981-323">Проверяет наличие обновлений для установленных в настоящее время пакетов шаблонов и устанавливает их.</span><span class="sxs-lookup"><span data-stu-id="f2981-323">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="f2981-324">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f2981-324">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="f2981-325">Проверяет наличие обновлений для установленных в настоящее время пакетов шаблонов.</span><span class="sxs-lookup"><span data-stu-id="f2981-325">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="f2981-326">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f2981-326">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="f2981-327">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="f2981-327">Template options</span></span>

<span data-ttu-id="f2981-328">Каждый шаблон проекта может содержать дополнительные доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="f2981-328">Each project template may have additional options available.</span></span> <span data-ttu-id="f2981-329">Основные шаблоны имеют следующие дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="f2981-329">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="f2981-330">console</span><span class="sxs-lookup"><span data-stu-id="f2981-330">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="f2981-331">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="f2981-331">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="f2981-332">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f2981-332">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="f2981-333">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="f2981-333">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="f2981-334">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="f2981-334">SDK version</span></span> | <span data-ttu-id="f2981-335">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f2981-335">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="f2981-336">3.1</span><span class="sxs-lookup"><span data-stu-id="f2981-336">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="f2981-337">3,0</span><span class="sxs-lookup"><span data-stu-id="f2981-337">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="f2981-338">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="f2981-338">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="f2981-339">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="f2981-339">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="f2981-340">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="f2981-340">Not supported for F#.</span></span> <span data-ttu-id="f2981-341">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="f2981-341">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="f2981-342">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="f2981-342">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="f2981-343">Если указано — во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="f2981-343">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="f2981-344">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="f2981-344">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="f2981-345">classlib</span><span class="sxs-lookup"><span data-stu-id="f2981-345">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="f2981-346">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="f2981-346">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="f2981-347">Значения: `netcoreapp<version>` для создания библиотеки классов .NET Core или `netstandard<version>` для создания стандартной библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="f2981-347">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="f2981-348">Значение по умолчанию — `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="f2981-348">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="f2981-349">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="f2981-349">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="f2981-350">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="f2981-350">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="f2981-351">Не поддерживается для F#.</span><span class="sxs-lookup"><span data-stu-id="f2981-351">Not supported for F#.</span></span> <span data-ttu-id="f2981-352">Доступно начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="f2981-352">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="f2981-353">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="f2981-353">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="f2981-354">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="f2981-354">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf"></a> <span data-ttu-id="f2981-355">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="f2981-355">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="f2981-356">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="f2981-356">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="f2981-357">Значение по умолчанию — `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="f2981-357">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="f2981-358">Доступно, начиная с пакета SDK для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="f2981-358">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="f2981-359">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="f2981-359">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="f2981-360">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="f2981-360">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="f2981-361">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="f2981-361">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="f2981-362">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="f2981-362">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms"></a> <span data-ttu-id="f2981-363">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="f2981-363">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="f2981-364">Задает свойство `LangVersion` в созданном файле проекта.</span><span class="sxs-lookup"><span data-stu-id="f2981-364">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="f2981-365">Например, вам требуется `--langVersion 7.3`, чтобы использовать C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="f2981-365">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="f2981-366">Список версий C# по умолчанию см. в разделе [Значения по умолчанию](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="f2981-366">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="f2981-367">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="f2981-367">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web-others"></a> <span data-ttu-id="f2981-368">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="f2981-368">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="f2981-369">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="f2981-369">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="f2981-370">Значение по умолчанию — `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="f2981-370">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="f2981-371">Доступно, начиная с пакета SDK для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="f2981-371">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="f2981-372">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="f2981-372">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="f2981-373">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="f2981-373">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="test"></a><span data-ttu-id="f2981-374">тmstest, xunit</span><span class="sxs-lookup"><span data-stu-id="f2981-374">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="f2981-375">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="f2981-375">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="f2981-376">Параметр доступен, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f2981-376">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="f2981-377">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="f2981-377">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="f2981-378">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="f2981-378">SDK version</span></span> | <span data-ttu-id="f2981-379">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f2981-379">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="f2981-380">3.1</span><span class="sxs-lookup"><span data-stu-id="f2981-380">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="f2981-381">3,0</span><span class="sxs-lookup"><span data-stu-id="f2981-381">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="f2981-382">Включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="f2981-382">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="f2981-383">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="f2981-383">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="f2981-384">nunit</span><span class="sxs-lookup"><span data-stu-id="f2981-384">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="f2981-385">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="f2981-385">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="f2981-386">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="f2981-386">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="f2981-387">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="f2981-387">SDK version</span></span> | <span data-ttu-id="f2981-388">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f2981-388">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="f2981-389">3.1</span><span class="sxs-lookup"><span data-stu-id="f2981-389">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="f2981-390">3,0</span><span class="sxs-lookup"><span data-stu-id="f2981-390">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="f2981-391">2.2</span><span class="sxs-lookup"><span data-stu-id="f2981-391">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="f2981-392">2.1</span><span class="sxs-lookup"><span data-stu-id="f2981-392">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="f2981-393">Включает упаковку проекта с помощью команды [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="f2981-393">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="f2981-394">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="f2981-394">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="f2981-395">страница</span><span class="sxs-lookup"><span data-stu-id="f2981-395">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="f2981-396">Пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="f2981-396">Namespace for the generated code.</span></span> <span data-ttu-id="f2981-397">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="f2981-397">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="f2981-398">Создает страницу без PageModel.</span><span class="sxs-lookup"><span data-stu-id="f2981-398">Creates the page without a PageModel.</span></span>

***

### <a name="namespace"></a> <span data-ttu-id="f2981-399">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="f2981-399">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="f2981-400">Пространство имен для сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="f2981-400">Namespace for the generated code.</span></span> <span data-ttu-id="f2981-401">Значение по умолчанию — `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="f2981-401">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="f2981-402">blazorserver</span><span class="sxs-lookup"><span data-stu-id="f2981-402">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="f2981-403">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f2981-403">The type of authentication to use.</span></span> <span data-ttu-id="f2981-404">Вы можете выбрать</span><span class="sxs-lookup"><span data-stu-id="f2981-404">The possible values are:</span></span>

  - <span data-ttu-id="f2981-405">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="f2981-405">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="f2981-406">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="f2981-406">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="f2981-407">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="f2981-407">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="f2981-408">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="f2981-408">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="f2981-409">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="f2981-409">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="f2981-410">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="f2981-410">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="f2981-411">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="f2981-411">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="f2981-412">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f2981-412">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="f2981-413">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="f2981-413">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="f2981-414">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="f2981-414">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="f2981-415">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f2981-415">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="f2981-416">Идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="f2981-416">The reset password policy ID for this project.</span></span> <span data-ttu-id="f2981-417">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f2981-417">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="f2981-418">Идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="f2981-418">The edit profile policy ID for this project.</span></span> <span data-ttu-id="f2981-419">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f2981-419">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="f2981-420">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="f2981-420">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="f2981-421">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="f2981-421">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="f2981-422">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="f2981-422">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="f2981-423">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="f2981-423">The Client ID for this project.</span></span> <span data-ttu-id="f2981-424">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="f2981-424">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="f2981-425">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="f2981-425">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="f2981-426">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="f2981-426">The domain for the directory tenant.</span></span> <span data-ttu-id="f2981-427">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f2981-427">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="f2981-428">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="f2981-428">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="f2981-429">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="f2981-429">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="f2981-430">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="f2981-430">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="f2981-431">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="f2981-431">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="f2981-432">Путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="f2981-432">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="f2981-433">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f2981-433">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="f2981-434">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="f2981-434">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="f2981-435">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="f2981-435">Allows this application read-access to the directory.</span></span> <span data-ttu-id="f2981-436">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="f2981-436">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="f2981-437">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="f2981-437">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="f2981-438">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f2981-438">Turns off HTTPS.</span></span> <span data-ttu-id="f2981-439">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются для `--auth`.</span><span class="sxs-lookup"><span data-stu-id="f2981-439">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="f2981-440">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="f2981-440">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="f2981-441">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f2981-441">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="f2981-442">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="f2981-442">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="f2981-443">web</span><span class="sxs-lookup"><span data-stu-id="f2981-443">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="f2981-444">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="f2981-444">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="f2981-445">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="f2981-445">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="f2981-446">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="f2981-446">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="f2981-447">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="f2981-447">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="f2981-448">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="f2981-448">SDK version</span></span> | <span data-ttu-id="f2981-449">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f2981-449">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="f2981-450">3.1</span><span class="sxs-lookup"><span data-stu-id="f2981-450">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="f2981-451">3,0</span><span class="sxs-lookup"><span data-stu-id="f2981-451">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="f2981-452">2.1</span><span class="sxs-lookup"><span data-stu-id="f2981-452">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="f2981-453">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="f2981-453">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="f2981-454">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f2981-454">Turns off HTTPS.</span></span>

***

### <a name="web-options"></a> <span data-ttu-id="f2981-455">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="f2981-455">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="f2981-456">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f2981-456">The type of authentication to use.</span></span> <span data-ttu-id="f2981-457">Вы можете выбрать</span><span class="sxs-lookup"><span data-stu-id="f2981-457">The possible values are:</span></span>

  - <span data-ttu-id="f2981-458">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="f2981-458">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="f2981-459">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="f2981-459">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="f2981-460">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="f2981-460">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="f2981-461">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="f2981-461">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="f2981-462">`MultiOrg` — проверка подлинности организации для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="f2981-462">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="f2981-463">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="f2981-463">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="f2981-464">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="f2981-464">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="f2981-465">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f2981-465">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="f2981-466">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="f2981-466">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="f2981-467">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="f2981-467">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="f2981-468">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f2981-468">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="f2981-469">Идентификатор политики сброса паролей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="f2981-469">The reset password policy ID for this project.</span></span> <span data-ttu-id="f2981-470">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f2981-470">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="f2981-471">Идентификатор политики изменения профилей для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="f2981-471">The edit profile policy ID for this project.</span></span> <span data-ttu-id="f2981-472">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f2981-472">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="f2981-473">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="f2981-473">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="f2981-474">Используется с проверкой подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="f2981-474">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="f2981-475">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="f2981-475">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="f2981-476">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="f2981-476">The Client ID for this project.</span></span> <span data-ttu-id="f2981-477">Используется с проверкой подлинности `IndividualB2C`, `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="f2981-477">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="f2981-478">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="f2981-478">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="f2981-479">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="f2981-479">The domain for the directory tenant.</span></span> <span data-ttu-id="f2981-480">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f2981-480">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="f2981-481">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="f2981-481">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="f2981-482">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="f2981-482">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="f2981-483">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="f2981-483">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="f2981-484">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="f2981-484">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="f2981-485">Путь запроса по базовому пути кода URI перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="f2981-485">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="f2981-486">Используется с проверкой подлинности `SingleOrg` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f2981-486">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="f2981-487">Значение по умолчанию — `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="f2981-487">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="f2981-488">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="f2981-488">Allows this application read-access to the directory.</span></span> <span data-ttu-id="f2981-489">Применяется только при проверке подлинности `SingleOrg` или `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="f2981-489">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="f2981-490">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="f2981-490">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="f2981-491">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f2981-491">Turns off HTTPS.</span></span> <span data-ttu-id="f2981-492">Этот параметр применяется, только если `Individual`, `IndividualB2C`, `SingleOrg` или `MultiOrg` не используются.</span><span class="sxs-lookup"><span data-stu-id="f2981-492">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="f2981-493">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="f2981-493">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="f2981-494">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f2981-494">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="f2981-495">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="f2981-495">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="f2981-496">Параметр доступен, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f2981-496">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="f2981-497">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="f2981-497">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="f2981-498">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="f2981-498">SDK version</span></span> | <span data-ttu-id="f2981-499">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f2981-499">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="f2981-500">3.1</span><span class="sxs-lookup"><span data-stu-id="f2981-500">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="f2981-501">3,0</span><span class="sxs-lookup"><span data-stu-id="f2981-501">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="f2981-502">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="f2981-502">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="f2981-503">Включает BrowserLink в проект.</span><span class="sxs-lookup"><span data-stu-id="f2981-503">Includes BrowserLink in the project.</span></span> <span data-ttu-id="f2981-504">Опция не доступна в .NET Core 2.2 и 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="f2981-504">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

***

### <a name="spa"></a> <span data-ttu-id="f2981-505">angular, react</span><span class="sxs-lookup"><span data-stu-id="f2981-505">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="f2981-506">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f2981-506">The type of authentication to use.</span></span> <span data-ttu-id="f2981-507">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f2981-507">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="f2981-508">Вы можете выбрать</span><span class="sxs-lookup"><span data-stu-id="f2981-508">The possible values are:</span></span>

  - <span data-ttu-id="f2981-509">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="f2981-509">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="f2981-510">`Individual` — индивидуальная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="f2981-510">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="f2981-511">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="f2981-511">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="f2981-512">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="f2981-512">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="f2981-513">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f2981-513">Turns off HTTPS.</span></span> <span data-ttu-id="f2981-514">Данная опция применяется только в том случае, если проверкой подлинности является `None`.</span><span class="sxs-lookup"><span data-stu-id="f2981-514">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="f2981-515">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="f2981-515">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="f2981-516">Применяется только при проверке подлинности `Individual` или `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f2981-516">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="f2981-517">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f2981-517">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="f2981-518">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="f2981-518">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="f2981-519">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="f2981-519">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="f2981-520">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="f2981-520">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="f2981-521">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="f2981-521">SDK version</span></span> | <span data-ttu-id="f2981-522">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f2981-522">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="f2981-523">3.1</span><span class="sxs-lookup"><span data-stu-id="f2981-523">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="f2981-524">3,0</span><span class="sxs-lookup"><span data-stu-id="f2981-524">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="f2981-525">2.1</span><span class="sxs-lookup"><span data-stu-id="f2981-525">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="f2981-526">reactredux</span><span class="sxs-lookup"><span data-stu-id="f2981-526">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="f2981-527">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="f2981-527">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="f2981-528">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="f2981-528">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="f2981-529">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="f2981-529">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="f2981-530">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="f2981-530">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="f2981-531">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="f2981-531">SDK version</span></span> | <span data-ttu-id="f2981-532">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f2981-532">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="f2981-533">3.1</span><span class="sxs-lookup"><span data-stu-id="f2981-533">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="f2981-534">3,0</span><span class="sxs-lookup"><span data-stu-id="f2981-534">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="f2981-535">2.1</span><span class="sxs-lookup"><span data-stu-id="f2981-535">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="f2981-536">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="f2981-536">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="f2981-537">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f2981-537">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="f2981-538">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="f2981-538">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="f2981-539">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="f2981-539">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="f2981-540">Поддерживает добавление традиционных страниц Razor и представлений в дополнение к компонентам этой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="f2981-540">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="f2981-541">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f2981-541">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="f2981-542">webapi</span><span class="sxs-lookup"><span data-stu-id="f2981-542">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="f2981-543">Тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f2981-543">The type of authentication to use.</span></span> <span data-ttu-id="f2981-544">Вы можете выбрать</span><span class="sxs-lookup"><span data-stu-id="f2981-544">The possible values are:</span></span>

  - <span data-ttu-id="f2981-545">`None` — без проверки подлинности (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="f2981-545">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="f2981-546">`IndividualB2C` — индивидуальная проверка подлинности с помощью Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="f2981-546">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="f2981-547">`SingleOrg` — проверка подлинности организации для отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="f2981-547">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="f2981-548">`Windows` — проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="f2981-548">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="f2981-549">Экземпляр Azure Active Directory B2C, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="f2981-549">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="f2981-550">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f2981-550">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="f2981-551">Значение по умолчанию — `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="f2981-551">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="f2981-552">Идентификатор политики входа и регистрации для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="f2981-552">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="f2981-553">Используется с проверкой подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f2981-553">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="f2981-554">Экземпляр Azure Active Directory, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="f2981-554">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="f2981-555">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="f2981-555">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="f2981-556">Значение по умолчанию — `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="f2981-556">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="f2981-557">Идентификатор клиента для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="f2981-557">The Client ID for this project.</span></span> <span data-ttu-id="f2981-558">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="f2981-558">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="f2981-559">Значение по умолчанию — `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="f2981-559">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="f2981-560">Домен клиента каталога.</span><span class="sxs-lookup"><span data-stu-id="f2981-560">The domain for the directory tenant.</span></span> <span data-ttu-id="f2981-561">Используется с проверкой подлинности `IndividualB2C` или `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="f2981-561">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="f2981-562">Значение по умолчанию — `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="f2981-562">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="f2981-563">Идентификатор TenantId каталога, к которому устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="f2981-563">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="f2981-564">Используется с проверкой подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="f2981-564">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="f2981-565">Значение по умолчанию — `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="f2981-565">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="f2981-566">Предоставляет приложению доступ к каталогу для чтения.</span><span class="sxs-lookup"><span data-stu-id="f2981-566">Allows this application read-access to the directory.</span></span> <span data-ttu-id="f2981-567">Применяется только при проверке подлинности `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="f2981-567">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="f2981-568">Исключает файл *launchSettings.json* из создаваемого шаблона.</span><span class="sxs-lookup"><span data-stu-id="f2981-568">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="f2981-569">Отключает протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f2981-569">Turns off HTTPS.</span></span> <span data-ttu-id="f2981-570">`app.UseHsts` и `app.UseHttpsRedirection` не добавляются к `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="f2981-570">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="f2981-571">Этот параметр применяется, только если `IndividualB2C` или `SingleOrg` не используются для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f2981-571">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="f2981-572">Указывает, что вместо SQLite следует использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="f2981-572">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="f2981-573">Применяется только при проверке подлинности `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f2981-573">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="f2981-574">Указывает целевую [платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="f2981-574">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="f2981-575">Опция не доступна в .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="f2981-575">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="f2981-576">В следующей таблице приведены значения по умолчанию в соответствии с версией пакета SDK, которую вы используете:</span><span class="sxs-lookup"><span data-stu-id="f2981-576">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="f2981-577">Версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="f2981-577">SDK version</span></span> | <span data-ttu-id="f2981-578">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f2981-578">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="f2981-579">3.1</span><span class="sxs-lookup"><span data-stu-id="f2981-579">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="f2981-580">3,0</span><span class="sxs-lookup"><span data-stu-id="f2981-580">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="f2981-581">2.1</span><span class="sxs-lookup"><span data-stu-id="f2981-581">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="f2981-582">Во время создания проекта не выполняется неявное восстановление.</span><span class="sxs-lookup"><span data-stu-id="f2981-582">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="f2981-583">globaljson</span><span class="sxs-lookup"><span data-stu-id="f2981-583">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="f2981-584">Задает версию пакета SDK для .NET Core, используемую в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="f2981-584">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="f2981-585">Примеры</span><span class="sxs-lookup"><span data-stu-id="f2981-585">Examples</span></span>

- <span data-ttu-id="f2981-586">Создайте проект консольного приложения на C#, указав имя шаблона:</span><span class="sxs-lookup"><span data-stu-id="f2981-586">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="f2981-587">Создание проекта консольного приложения F# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="f2981-587">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="f2981-588">Создайте проект библиотеки классов .NET Standard в указанном каталоге:</span><span class="sxs-lookup"><span data-stu-id="f2981-588">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="f2981-589">Создайте новый проект MVC ASP.NET Core C# в текущем каталоге без проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="f2981-589">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="f2981-590">Создайте новый проект xUnit:</span><span class="sxs-lookup"><span data-stu-id="f2981-590">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="f2981-591">Перечислите все шаблоны, доступные для одностраничных приложений (SPA):</span><span class="sxs-lookup"><span data-stu-id="f2981-591">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="f2981-592">Список всех шаблонов, соответствующих подстроке *we*.</span><span class="sxs-lookup"><span data-stu-id="f2981-592">List all templates matching the *we* substring.</span></span> <span data-ttu-id="f2981-593">Точное совпадение не найдено, поэтому сравнение подстрок выполняется по короткому имени и столбцам имен.</span><span class="sxs-lookup"><span data-stu-id="f2981-593">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="f2981-594">Попытайтесь вызвать шаблон, соответствующий *ng*.</span><span class="sxs-lookup"><span data-stu-id="f2981-594">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="f2981-595">Если точное совпадение не найдено, выведите шаблоны с частичным совпадением.</span><span class="sxs-lookup"><span data-stu-id="f2981-595">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="f2981-596">Установите версию 2.0 шаблонов SPA для ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="f2981-596">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="f2981-597">Перечислите установленные шаблоны и подробную информацию о них, в том числе и о том, как их удалить:</span><span class="sxs-lookup"><span data-stu-id="f2981-597">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="f2981-598">Создайте *global.json* в текущем каталоге, установив версию SDK на 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="f2981-598">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="f2981-599">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f2981-599">See also</span></span>

- [<span data-ttu-id="f2981-600">Пользовательские шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="f2981-600">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="f2981-601">Создание пользовательского шаблона для dotnet</span><span class="sxs-lookup"><span data-stu-id="f2981-601">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="f2981-602">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="f2981-602">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="f2981-603">Доступные шаблоны для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="f2981-603">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
