---
title: Создание шаблона проекта для dotnet new
description: Из этой статьи вы узнаете, как создать шаблон проекта для команды dotnet new.
author: thraka
ms.date: 06/25/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: f53f4037f832265a35f65bf2e5096c7e5a37bcf1
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503535"
---
# <a name="tutorial-create-a-project-template"></a><span data-ttu-id="200df-103">Учебник. Создание шаблона проекта</span><span class="sxs-lookup"><span data-stu-id="200df-103">Tutorial: Create a project template</span></span>

<span data-ttu-id="200df-104">С помощью .NET Core вы можете создавать и развертывать шаблоны, которые генерируют проекты, файлы и даже ресурсы.</span><span class="sxs-lookup"><span data-stu-id="200df-104">With .NET Core, you can create and deploy templates that generate projects, files, even resources.</span></span> <span data-ttu-id="200df-105">Это руководство представляет собой вторую часть серии, в которой описано, как создавать, устанавливать и удалять шаблоны с помощью команды `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="200df-105">This tutorial is part two of a series that teaches you how to create, install, and uninstall, templates for use with the `dotnet new` command.</span></span>

<span data-ttu-id="200df-106">Из этой части вы узнаете, как выполнять такие задачи:</span><span class="sxs-lookup"><span data-stu-id="200df-106">In this part of the series you'll learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="200df-107">создание ресурсов для шаблона проекта;</span><span class="sxs-lookup"><span data-stu-id="200df-107">Create the resources of a project template</span></span>
> * <span data-ttu-id="200df-108">создание папки и файла конфигурации шаблона;</span><span class="sxs-lookup"><span data-stu-id="200df-108">Create the template config folder and file</span></span>
> * <span data-ttu-id="200df-109">установка шаблона из файла;</span><span class="sxs-lookup"><span data-stu-id="200df-109">Install a template from a file path</span></span>
> * <span data-ttu-id="200df-110">тестирование шаблона элемента;</span><span class="sxs-lookup"><span data-stu-id="200df-110">Test an item template</span></span>
> * <span data-ttu-id="200df-111">удаление шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="200df-111">Uninstall an item template</span></span>

## <a name="prerequisites"></a><span data-ttu-id="200df-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="200df-112">Prerequisites</span></span>

* <span data-ttu-id="200df-113">Изучите [первую часть](cli-templates-create-item-template.md) этой серии руководств.</span><span class="sxs-lookup"><span data-stu-id="200df-113">Complete [part 1](cli-templates-create-item-template.md) of this tutorial series.</span></span>
* <span data-ttu-id="200df-114">Откройте терминал и перейдите к папке _working\templates_.</span><span class="sxs-lookup"><span data-stu-id="200df-114">Open a terminal and navigate to the _working\templates_ folder.</span></span>

## <a name="create-a-project-template"></a><span data-ttu-id="200df-115">Создание шаблона проекта</span><span class="sxs-lookup"><span data-stu-id="200df-115">Create a project template</span></span>

<span data-ttu-id="200df-116">Шаблоны проектов предоставляют готовые проекты, которые упрощают пользователям взаимодействие с рабочим набором кода.</span><span class="sxs-lookup"><span data-stu-id="200df-116">Project templates produce ready-to-run projects that make it easy for users to start with a working set of code.</span></span> <span data-ttu-id="200df-117">.NET Core включает несколько шаблонов проектов, например консольное приложение или библиотеку класса.</span><span class="sxs-lookup"><span data-stu-id="200df-117">.NET Core includes a few project templates such as a console application or a class library.</span></span> <span data-ttu-id="200df-118">В этом описано, как создать консольный проект, который включает поддержку C# 8.0 и создает точку входа `async main`.</span><span class="sxs-lookup"><span data-stu-id="200df-118">In this example, you'll create a new console project that enables C# 8.0 and produces an `async main` entry point.</span></span>

<span data-ttu-id="200df-119">В окне терминала перейдите к папке _working\templates_ и создайте вложенную папку с именем _consoleasync_.</span><span class="sxs-lookup"><span data-stu-id="200df-119">In your terminal, navigate to the _working\templates_ folder and create a new subfolder named _consoleasync_.</span></span> <span data-ttu-id="200df-120">Откройте созданную папку и выполните команду `dotnet new console`, чтобы создать стандартное консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="200df-120">Enter the subfolder and run `dotnet new console` to generate the standard console application.</span></span> <span data-ttu-id="200df-121">Чтобы создать новый шаблон, созданные им файлы нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="200df-121">You'll be editing the files produced by this template to create a new template.</span></span>

```console
working
└───templates
    └───consoleasync
            consoleasync.csproj
            Program.cs
```

## <a name="modify-programcs"></a><span data-ttu-id="200df-122">Изменение файла program.cs</span><span class="sxs-lookup"><span data-stu-id="200df-122">Modify Program.cs</span></span>

<span data-ttu-id="200df-123">Откройте файл _program.cs_.</span><span class="sxs-lookup"><span data-stu-id="200df-123">Open up the _program.cs_ file.</span></span> <span data-ttu-id="200df-124">Консольный проект не использует асинхронную точку входа, поэтому мы добавим ее.</span><span class="sxs-lookup"><span data-stu-id="200df-124">The console project doesn't use an asynchronous entry point, so let's add that.</span></span> <span data-ttu-id="200df-125">Измените код на приведенный ниже и сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="200df-125">Change your code to the following and save the file.</span></span>

```csharp
using System;
using System.Threading.Tasks;

namespace consoleasync
{
    class Program
    {
        static async Task Main(string[] args)
        {
            await Console.Out.WriteAsync("Hello World with C# 8.0!");
        }
    }
}
```

## <a name="modify-consoleasynccsproj"></a><span data-ttu-id="200df-126">Изменение файла consoleasync.csproj</span><span class="sxs-lookup"><span data-stu-id="200df-126">Modify consoleasync.csproj</span></span>

<span data-ttu-id="200df-127">Мы изменим версию языка C#, которую использует проект, на 8.0.</span><span class="sxs-lookup"><span data-stu-id="200df-127">Let's update the C# language version the project uses to version 8.0.</span></span> <span data-ttu-id="200df-128">Отредактируйте файл _consoleasync.csproj_ и добавьте параметр `<LangVersion>` для узла `<PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="200df-128">Edit the _consoleasync.csproj_ file and add the `<LangVersion>` setting to a `<PropertyGroup>` node.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.2</TargetFramework>

    <LangVersion>8.0</LangVersion>

  </PropertyGroup>
  
</Project>
```

## <a name="build-the-project"></a><span data-ttu-id="200df-129">Построение проекта</span><span class="sxs-lookup"><span data-stu-id="200df-129">Build the project</span></span>

<span data-ttu-id="200df-130">Перед завершением работы с шаблоном проекта протестируйте его, чтобы проверить правильность компиляции и выполнения.</span><span class="sxs-lookup"><span data-stu-id="200df-130">Before you complete a project template, you should test it to make sure it compiles and runs correctly.</span></span>

<span data-ttu-id="200df-131">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="200df-131">In your terminal, run the following command.</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="200df-132">Вы получите приведенные ниже выходные данные.</span><span class="sxs-lookup"><span data-stu-id="200df-132">You get the following output.</span></span>

```console
Hello World with C# 8.0!
```

<span data-ttu-id="200df-133">Вы можете удалить папки _obj_ и _bin_, созданные после запуска команды `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="200df-133">You can delete the _obj_ and _bin_ folders created by using `dotnet run`.</span></span> <span data-ttu-id="200df-134">Удаление этих файлов гарантирует, что шаблон будет включать только те файлы, которые связаны с шаблоном (без файлов, созданных в результате сборки).</span><span class="sxs-lookup"><span data-stu-id="200df-134">Deleting these files ensures your template only includes the files related to your template and not any files that result of a build action.</span></span>

<span data-ttu-id="200df-135">Теперь, когда вы создали содержимое шаблона, необходимо создать файл конфигурации шаблона в его корневой папке.</span><span class="sxs-lookup"><span data-stu-id="200df-135">Now that you have the content of the template created, you need to create the template config at the root folder of the template.</span></span>

## <a name="create-the-template-config"></a><span data-ttu-id="200df-136">Создание конфигурации шаблона</span><span class="sxs-lookup"><span data-stu-id="200df-136">Create the template config</span></span>

<span data-ttu-id="200df-137">Шаблоны распознаются в .NET Core по специальной папке и файлу конфигурации, которые находятся в корневой папке шаблона.</span><span class="sxs-lookup"><span data-stu-id="200df-137">Templates are recognized in .NET Core by a special folder and config file that exist at the root of your template.</span></span> <span data-ttu-id="200df-138">В нашем случае папка шаблона имеет такое расположение: _working\templates\consoleasync_.</span><span class="sxs-lookup"><span data-stu-id="200df-138">In this tutorial, your template folder is located at _working\templates\consoleasync_.</span></span>

<span data-ttu-id="200df-139">При создании шаблона все файлы и папки в этой папке включаются как его часть, кроме специальной папки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="200df-139">When you create a template, all files and folders in the template folder are included as part of the template except for the special config folder.</span></span> <span data-ttu-id="200df-140">Эта папка конфигурации имеет имя _.template.config_.</span><span class="sxs-lookup"><span data-stu-id="200df-140">This config folder is named _.template.config_.</span></span>

<span data-ttu-id="200df-141">Сначала создайте вложенную папку с именем _.template.config_ и откройте ее.</span><span class="sxs-lookup"><span data-stu-id="200df-141">First, create a new subfolder named _.template.config_, enter it.</span></span> <span data-ttu-id="200df-142">Затем создайте файл с именем _template.json_.</span><span class="sxs-lookup"><span data-stu-id="200df-142">Then, create a new file named _template.json_.</span></span> <span data-ttu-id="200df-143">Структура папки должна быть такой, как указано ниже.</span><span class="sxs-lookup"><span data-stu-id="200df-143">Your folder structure should look like this.</span></span>

```console
working
└───templates
    └───consoleasync
        └───.template.config
                template.json
```

<span data-ttu-id="200df-144">Откройте файл _template.json_ в любом текстовом редакторе, вставьте приведенный ниже код JSON и сохраните его.</span><span class="sxs-lookup"><span data-stu-id="200df-144">Open the _template.json_ with your favorite text editor and paste in the following json code and save it.</span></span>

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Me",
  "classifications": [ "Common", "Console", "C#8" ],
  "identity": "ExampleTemplate.AsyncProject",
  "name": "Example templates: async project",
  "shortName": "consoleasync",
  "tags": {
    "language": "C#",
    "type": "project"
  }
}
```

<span data-ttu-id="200df-145">Этот файл конфигурации содержит все параметры шаблона.</span><span class="sxs-lookup"><span data-stu-id="200df-145">This config file contains all of the settings for your template.</span></span> <span data-ttu-id="200df-146">Вы можете увидеть основные параметры, например `name` и `shortName`, но в нем также присутствует параметр `tags/type` со значением `project`.</span><span class="sxs-lookup"><span data-stu-id="200df-146">You can see the basic settings such as `name` and `shortName` but also there's a `tags/type` value that's set to `project`.</span></span> <span data-ttu-id="200df-147">Он указывает на то, что ваш шаблон является шаблоном проекта.</span><span class="sxs-lookup"><span data-stu-id="200df-147">This designates your template as a project template.</span></span> <span data-ttu-id="200df-148">Вы можете создать шаблон любого типа.</span><span class="sxs-lookup"><span data-stu-id="200df-148">There's no restriction on the type of template you create.</span></span> <span data-ttu-id="200df-149">Значения `item` и `project` — это общие рекомендуемые имена .NET Core, которые позволяют без усилий фильтровать типы шаблонов при поиске.</span><span class="sxs-lookup"><span data-stu-id="200df-149">The `item` and `project` values are common names that .NET Core recommends so that users can easily filter the type of template they're searching for.</span></span>

<span data-ttu-id="200df-150">Элемент `classifications` представляет столбец **tags**, который отображается после запуска команды `dotnet new` и получения списка шаблонов.</span><span class="sxs-lookup"><span data-stu-id="200df-150">The `classifications` item represents the **tags** column you see when you run `dotnet new` and get a list of templates.</span></span> <span data-ttu-id="200df-151">Пользователи также могут выполнять поиск по тегам классификации.</span><span class="sxs-lookup"><span data-stu-id="200df-151">Users can also search based on classification tags.</span></span> <span data-ttu-id="200df-152">Не путайте свойство `tags` в JSON-файле со списком тегов `classifications`.</span><span class="sxs-lookup"><span data-stu-id="200df-152">Don't confuse the `tags` property in the json file with the `classifications` tags list.</span></span> <span data-ttu-id="200df-153">Это два разных элемента, которые, к сожалению, имеют одинаковые имена.</span><span class="sxs-lookup"><span data-stu-id="200df-153">They're two different things unfortunately named similarly.</span></span> <span data-ttu-id="200df-154">Полная схема файла *template.json* находится в [хранилище схем JSON](http://json.schemastore.org/template).</span><span class="sxs-lookup"><span data-stu-id="200df-154">The full schema for the *template.json* file is found at the [JSON Schema Store](http://json.schemastore.org/template).</span></span> <span data-ttu-id="200df-155">Дополнительные сведения о файле *template.json* см. на [вики-сайте о шаблонах dotnet](https://github.com/dotnet/templating/wiki).</span><span class="sxs-lookup"><span data-stu-id="200df-155">For more information about the *template.json* file, see the [dotnet templating wiki](https://github.com/dotnet/templating/wiki).</span></span>

<span data-ttu-id="200df-156">Теперь, когда у вас есть допустимый файл _.template.config/template.json_, вы можете установить шаблон.</span><span class="sxs-lookup"><span data-stu-id="200df-156">Now that you have a valid _.template.config/template.json_ file, your template is ready to be installed.</span></span> <span data-ttu-id="200df-157">Перед установкой шаблона убедитесь, что вы удалили все лишние файлы и папки, которые не должны включаться в шаблон, например папки _bin_ или _obj_.</span><span class="sxs-lookup"><span data-stu-id="200df-157">Before you install the template, make sure that you delete any extra files folders and files you don't want included in your template, like the _bin_ or _obj_ folders.</span></span> <span data-ttu-id="200df-158">В окне терминала перейдите к папке _consoleasync_ и выполните команду `dotnet new -i .\`, чтобы установить шаблон, расположенный в текущей папке.</span><span class="sxs-lookup"><span data-stu-id="200df-158">In your terminal, navigate to the _consoleasync_ folder and run `dotnet new -i .\` to install the template located at the current folder.</span></span> <span data-ttu-id="200df-159">Если вы используете операционную систему Linux или macOS, используйте косую черту: `dotnet new -i ./`.</span><span class="sxs-lookup"><span data-stu-id="200df-159">If you're using a Linux or macOS operating system, use a forward slash: `dotnet new -i ./`.</span></span>

<span data-ttu-id="200df-160">Эта команда выводит список установленных шаблонов, в числе которых должен быть и ваш шаблон.</span><span class="sxs-lookup"><span data-stu-id="200df-160">This command outputs the list of templates installed, which should include yours.</span></span>

```dotnetcli
dotnet new -i .\
```

<span data-ttu-id="200df-161">Вы получите результат, аналогичный приведенному ниже.</span><span class="sxs-lookup"><span data-stu-id="200df-161">You get output similar to the following.</span></span>

```console
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Console Application                               console               [C#], F#, VB      Common/Console
Example templates: async project                  consoleasync          [C#]              Common/Console/C#8
Class library                                     classlib              [C#], F#, VB      Common/Library
WPF Application                                   wpf                   [C#], VB          Common/WPF
Windows Forms (WinForms) Application              winforms              [C#], VB          Common/WinForms
Worker Service                                    worker                [C#]              Common/Worker/Web
```

### <a name="test-the-project-template"></a><span data-ttu-id="200df-162">Тестирование шаблона проекта</span><span class="sxs-lookup"><span data-stu-id="200df-162">Test the project template</span></span>

<span data-ttu-id="200df-163">Теперь, когда вы установили шаблон элемента, протестируйте его.</span><span class="sxs-lookup"><span data-stu-id="200df-163">Now that you have an item template installed, test it.</span></span>

1. <span data-ttu-id="200df-164">Перейдите в папку _теста_.</span><span class="sxs-lookup"><span data-stu-id="200df-164">Navigate to the _test_ folder</span></span>

1. <span data-ttu-id="200df-165">Создайте консольное приложение с помощью приведенной ниже команды, которая позволяет создать рабочий проект, который можно без труда протестировать, используя команду `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="200df-165">Create a new console application with the following command which generates a working project you can easily test with the `dotnet run` command.</span></span>

    ```dotnetcli
    dotnet new consoleasync
    ```

    <span data-ttu-id="200df-166">Вы получите приведенные ниже выходные данные.</span><span class="sxs-lookup"><span data-stu-id="200df-166">You get the following output.</span></span>

    ```console
    The template "Example templates: async project" was created successfully.
    ```

1. <span data-ttu-id="200df-167">Запустите проект с помощью приведенной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="200df-167">Run the project using the following command.</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="200df-168">Вы получите приведенные ниже выходные данные.</span><span class="sxs-lookup"><span data-stu-id="200df-168">You get the following output.</span></span>

    ```console
    Hello World with C# 8.0!
    ```

<span data-ttu-id="200df-169">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="200df-169">Congratulations!</span></span> <span data-ttu-id="200df-170">Вы создали и развернули шаблон проекта с помощью .NET Core.</span><span class="sxs-lookup"><span data-stu-id="200df-170">You created and deployed a project template with .NET Core.</span></span> <span data-ttu-id="200df-171">Для подготовки к следующей части этой серии руководств вам необходимо удалить созданный шаблон.</span><span class="sxs-lookup"><span data-stu-id="200df-171">In preparation for the next part of this tutorial series, you must uninstall the template you created.</span></span> <span data-ttu-id="200df-172">Также обязательно удалите все файлы из папки _test_.</span><span class="sxs-lookup"><span data-stu-id="200df-172">Make sure to delete all files from the _test_ folder too.</span></span> <span data-ttu-id="200df-173">Так вы воссоздадите первоначальные условия для работы со следующим разделом этого руководства.</span><span class="sxs-lookup"><span data-stu-id="200df-173">This will get you back to a clean state ready for the next major section of this tutorial.</span></span>

### <a name="uninstall-the-template"></a><span data-ttu-id="200df-174">Удаление шаблона</span><span class="sxs-lookup"><span data-stu-id="200df-174">Uninstall the template</span></span>

<span data-ttu-id="200df-175">Так как вы установили шаблон с указанием пути к файлу, вам нужно удалить его, указав **абсолютный** путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="200df-175">Because you installed the template by using a file path, you must uninstall it with the **absolute** file path.</span></span> <span data-ttu-id="200df-176">Вы можете просмотреть список всех установленных шаблонов, выполнив команду `dotnet new -u`.</span><span class="sxs-lookup"><span data-stu-id="200df-176">You can see a list of templates installed by running the `dotnet new -u` command.</span></span> <span data-ttu-id="200df-177">Ваш шаблон должен быть последним в списке.</span><span class="sxs-lookup"><span data-stu-id="200df-177">Your template should be listed last.</span></span> <span data-ttu-id="200df-178">Удалите шаблон с помощью команды `dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>`, указав путь к нему.</span><span class="sxs-lookup"><span data-stu-id="200df-178">Use the path listed to uninstall your template with the `dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>` command.</span></span>

```dotnetcli
dotnet new -u
```

<span data-ttu-id="200df-179">Вы получите результат, аналогичный приведенному ниже.</span><span class="sxs-lookup"><span data-stu-id="200df-179">You get output similar to the following.</span></span>

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ItemTemplates
    Templates:
      dotnet gitignore file (gitignore)
      global.json file (globaljson)
      NuGet Config (nugetconfig)
      Solution File (sln)
      Dotnet local tool manifest file (tool-manifest)
      Web Config (webconfig)

... cut to save space ...

  NUnit3.DotNetNew.Template
    Templates:
      NUnit 3 Test Project (nunit) C#
      NUnit 3 Test Item (nunit-test) C#
      NUnit 3 Test Project (nunit) F#
      NUnit 3 Test Item (nunit-test) F#
      NUnit 3 Test Project (nunit) VB
      NUnit 3 Test Item (nunit-test) VB
  C:\working\templates\consoleasync
    Templates:
      Example templates: async project (consoleasync) C#
```

<span data-ttu-id="200df-180">Чтобы удалить шаблон, выполните указанную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="200df-180">To uninstall a template, run the following command.</span></span>

```dotnetcli
dotnet new -u C:\working\templates\consoleasync
```

## <a name="next-steps"></a><span data-ttu-id="200df-181">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="200df-181">Next steps</span></span>

<span data-ttu-id="200df-182">В рамках этого руководства вы создали шаблон проекта.</span><span class="sxs-lookup"><span data-stu-id="200df-182">In this tutorial, you created a project template.</span></span> <span data-ttu-id="200df-183">Чтобы узнать, как создать простой в использовании пакетный файл с элементом и шаблонами проектов, перейдите к следующей части этой серии.</span><span class="sxs-lookup"><span data-stu-id="200df-183">To learn how to package both the item and project templates into an easy-to-use file, continue this tutorial series.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="200df-184">Создание пакета шаблонов</span><span class="sxs-lookup"><span data-stu-id="200df-184">Create a template pack</span></span>](cli-templates-create-template-pack.md)
