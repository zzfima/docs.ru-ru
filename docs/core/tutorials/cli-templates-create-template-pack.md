---
title: Создание пакета шаблонов для команды dotnet new
description: Узнайте, как создать файл CSPROJ, с помощью которого выполняется сборка пакета шаблонов для команды dotnet new.
author: thraka
ms.date: 12/10/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: 5bc926861dd6a501d7c2d24bd5f7c4116cc78b2c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503488"
---
# <a name="tutorial-create-a-template-pack"></a><span data-ttu-id="846f3-103">Учебник. Создание пакета шаблонов</span><span class="sxs-lookup"><span data-stu-id="846f3-103">Tutorial: Create a template pack</span></span>

<span data-ttu-id="846f3-104">С помощью .NET Core вы можете создавать и развертывать шаблоны, которые генерируют проекты, файлы и даже ресурсы.</span><span class="sxs-lookup"><span data-stu-id="846f3-104">With .NET Core, you can create and deploy templates that generate projects, files, even resources.</span></span> <span data-ttu-id="846f3-105">Это третья часть серии руководств по созданию, установке и удалению шаблонов с помощью команды `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="846f3-105">This tutorial is part three of a series that teaches you how to create, install, and uninstall templates for use with the `dotnet new` command.</span></span>

<span data-ttu-id="846f3-106">Из этой части вы узнаете, как выполнять такие задачи:</span><span class="sxs-lookup"><span data-stu-id="846f3-106">In this part of the series you'll learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="846f3-107">создание проекта \*.csproj для сборки пакета шаблонов;</span><span class="sxs-lookup"><span data-stu-id="846f3-107">Create a \*.csproj project to build a template pack</span></span>
> * <span data-ttu-id="846f3-108">настройка файла проекта для упаковки;</span><span class="sxs-lookup"><span data-stu-id="846f3-108">Configure the project file for packing</span></span>
> * <span data-ttu-id="846f3-109">установка шаблона из файла пакета NuGet;</span><span class="sxs-lookup"><span data-stu-id="846f3-109">Install a template from a NuGet package file</span></span>
> * <span data-ttu-id="846f3-110">удаление шаблона по идентификатору пакета.</span><span class="sxs-lookup"><span data-stu-id="846f3-110">Uninstall a template by package ID</span></span>

## <a name="prerequisites"></a><span data-ttu-id="846f3-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="846f3-111">Prerequisites</span></span>

* <span data-ttu-id="846f3-112">Изучите [первую](cli-templates-create-item-template.md) и [вторую](cli-templates-create-project-template.md) части этой серии руководств.</span><span class="sxs-lookup"><span data-stu-id="846f3-112">Complete [part 1](cli-templates-create-item-template.md) and [part 2](cli-templates-create-project-template.md) of this tutorial series.</span></span>

  <span data-ttu-id="846f3-113">Для этого руководства используются два шаблона, созданные в ходе работы с первыми двумя руководствами серии.</span><span class="sxs-lookup"><span data-stu-id="846f3-113">This tutorial uses the two templates created in the first two parts of this tutorial.</span></span> <span data-ttu-id="846f3-114">Вы можете использовать другой шаблон, сохранив его в папку _working\templates\\_ .</span><span class="sxs-lookup"><span data-stu-id="846f3-114">You can use a different template as long as you copy the template, as a folder, into the _working\templates\\_ folder.</span></span>

* <span data-ttu-id="846f3-115">Откройте терминал и перейдите в папку _working\templates\\_ .</span><span class="sxs-lookup"><span data-stu-id="846f3-115">Open a terminal and navigate to the _working\\_ folder.</span></span>

## <a name="create-a-template-pack-project"></a><span data-ttu-id="846f3-116">Создание проекта пакета шаблонов</span><span class="sxs-lookup"><span data-stu-id="846f3-116">Create a template pack project</span></span>

<span data-ttu-id="846f3-117">Пакет шаблонов — это один или несколько шаблонов, упакованных в файл.</span><span class="sxs-lookup"><span data-stu-id="846f3-117">A template pack is one or more templates packaged into a file.</span></span> <span data-ttu-id="846f3-118">При установке или удалении пакета все шаблоны, содержащиеся в пакете, соответственно добавляются или удаляются.</span><span class="sxs-lookup"><span data-stu-id="846f3-118">When you install or uninstall a pack, all templates contained in the pack are added or removed, respectively.</span></span> <span data-ttu-id="846f3-119">В предыдущих частях этой серии руководств использовались только отдельные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="846f3-119">The previous parts of this tutorial series only worked with individual templates.</span></span> <span data-ttu-id="846f3-120">Чтобы установить неупакованный шаблон, необходимо скопировать папку шаблона и выполнить его установку из папки.</span><span class="sxs-lookup"><span data-stu-id="846f3-120">To share a non-packed template, you have to copy the template folder and install via that folder.</span></span> <span data-ttu-id="846f3-121">Так как пакет шаблонов может содержать несколько шаблонов и является одним файлом, процесс установки шаблонов упрощается.</span><span class="sxs-lookup"><span data-stu-id="846f3-121">Because a template pack can have more than one template in it, and is a single file, sharing is easier.</span></span>

<span data-ttu-id="846f3-122">Пакет шаблонов — это файл пакета NuGet (_NUPKG_).</span><span class="sxs-lookup"><span data-stu-id="846f3-122">Template packs are represented by a NuGet package (_.nupkg_) file.</span></span> <span data-ttu-id="846f3-123">Как и любой пакет NuGet, пакет шаблонов можно передать в веб-канал NuGet.</span><span class="sxs-lookup"><span data-stu-id="846f3-123">And, like any NuGet package, you can upload the template pack to a NuGet feed.</span></span> <span data-ttu-id="846f3-124">С помощью команды `dotnet new -i` можно установить пакет шаблонов из веб-канала NuGet.</span><span class="sxs-lookup"><span data-stu-id="846f3-124">The `dotnet new -i` command supports installing template pack from a NuGet package feed.</span></span> <span data-ttu-id="846f3-125">Кроме того, пакет шаблонов можно установить непосредственно из файла _NUPKG_.</span><span class="sxs-lookup"><span data-stu-id="846f3-125">Additionally, you can install a template pack from a _.nupkg_ file directly.</span></span>

<span data-ttu-id="846f3-126">Для компиляции кода и создания двоичного файла обычно используется файл проекта C#.</span><span class="sxs-lookup"><span data-stu-id="846f3-126">Normally you use a C# project file to compile code and produce a binary.</span></span> <span data-ttu-id="846f3-127">Но проект также можно использовать для создания пакета шаблонов.</span><span class="sxs-lookup"><span data-stu-id="846f3-127">However, the project can also be used to generate a template pack.</span></span> <span data-ttu-id="846f3-128">Изменив параметры файла _CSPROJ_, можно не выполнять компиляцию кода, а добавить все ресурсы в шаблон.</span><span class="sxs-lookup"><span data-stu-id="846f3-128">By changing the settings of the _.csproj_, you can prevent it from compiling any code and instead include all the assets of your templates as resources.</span></span> <span data-ttu-id="846f3-129">Во время сборки этого проекта создается пакет NuGet с пакетом шаблонов.</span><span class="sxs-lookup"><span data-stu-id="846f3-129">When this project is built, it produces a template pack NuGet package.</span></span>

<span data-ttu-id="846f3-130">Созданный пакет будет содержать [шаблон элемента](cli-templates-create-item-template.md) и [шаблон проекта](cli-templates-create-project-template.md), созданные ранее.</span><span class="sxs-lookup"><span data-stu-id="846f3-130">The pack you'll create will include the [item template](cli-templates-create-item-template.md) and [package template](cli-templates-create-project-template.md) previously created.</span></span> <span data-ttu-id="846f3-131">Так как мы поместили оба шаблона в папку _working\templates\\_ , можно добавить файл _CSPROJ_ в папку _working_.</span><span class="sxs-lookup"><span data-stu-id="846f3-131">Because we grouped the two templates into the _working\templates\\_ folder, we can use the _working_ folder for the _.csproj_ file.</span></span>

<span data-ttu-id="846f3-132">В окне терминала перейдите к папке _working_.</span><span class="sxs-lookup"><span data-stu-id="846f3-132">In your terminal, navigate to the _working_ folder.</span></span> <span data-ttu-id="846f3-133">Создайте проект, задайте ему имя `templatepack` и укажите текущую папку в качестве целевой.</span><span class="sxs-lookup"><span data-stu-id="846f3-133">Create a new project and set the name to `templatepack` and the output folder to the current folder.</span></span>

```dotnetcli
dotnet new console -n templatepack -o .
```

<span data-ttu-id="846f3-134">Параметр `-n` присваивает файлы _.csproj_ имя _templatepack.csproj_.</span><span class="sxs-lookup"><span data-stu-id="846f3-134">The `-n` parameter sets the _.csproj_ filename to _templatepack.csproj_.</span></span> <span data-ttu-id="846f3-135">Параметр `-o` создает файлы в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="846f3-135">The `-o` parameter creates the files in the current directory.</span></span> <span data-ttu-id="846f3-136">Отобразится результат примерно такого содержания:</span><span class="sxs-lookup"><span data-stu-id="846f3-136">You should see a result similar to the following output.</span></span>

```dotnetcli
dotnet new console -n templatepack -o .
```

```console
The template "Console Application" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on .\templatepack.csproj...
  Restore completed in 52.38 ms for C:\working\templatepack.csproj.

Restore succeeded.
```

<span data-ttu-id="846f3-137">Затем откройте файл _templatepack.csproj_ в редакторе и замените содержимое следующим кодом XML:</span><span class="sxs-lookup"><span data-stu-id="846f3-137">Next, open the _templatepack.csproj_ file in your favorite editor and replace the content with the following XML:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <PackageType>Template</PackageType>
    <PackageVersion>1.0</PackageVersion>
    <PackageId>AdatumCorporation.Utility.Templates</PackageId>
    <Title>AdatumCorporation Templates</Title>
    <Authors>Me</Authors>
    <Description>Templates to use when creating an application for Adatum Corporation.</Description>
    <PackageTags>dotnet-new;templates;contoso</PackageTags>

    <TargetFramework>netstandard2.0</TargetFramework>

    <IncludeContentInPack>true</IncludeContentInPack>
    <IncludeBuildOutput>false</IncludeBuildOutput>
    <ContentTargetFolders>content</ContentTargetFolders>
  </PropertyGroup>

  <ItemGroup>
    <Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />
    <Compile Remove="**\*" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="846f3-138">Параметры `<PropertyGroup>` в приведенном выше коде XML разделены на три группы.</span><span class="sxs-lookup"><span data-stu-id="846f3-138">The `<PropertyGroup>` settings in the XML above is broken into three groups.</span></span> <span data-ttu-id="846f3-139">Первая группа отвечает за свойства, необходимые для пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="846f3-139">The first group deals with properties required for a NuGet package.</span></span> <span data-ttu-id="846f3-140">Три параметра `<Package` отвечают за свойства пакета NuGet, необходимые для обнаружения пакета в веб-канале NuGet.</span><span class="sxs-lookup"><span data-stu-id="846f3-140">The three `<Package` settings have to do with the NuGet package properties to identify your package on a NuGet feed.</span></span> <span data-ttu-id="846f3-141">В частности, значение `<PackageId>` позволяет удалить пакет шаблонов по имени и не указывать путь к его каталогу.</span><span class="sxs-lookup"><span data-stu-id="846f3-141">Specifically the `<PackageId>` value is used to uninstall the template pack with a single name instead of a directory path.</span></span> <span data-ttu-id="846f3-142">Оно также позволяет установить пакет шаблонов из веб-канала NuGet.</span><span class="sxs-lookup"><span data-stu-id="846f3-142">It can also be used to install the template pack from a NuGet feed.</span></span> <span data-ttu-id="846f3-143">Остальные параметры, такие как `<Title>` и `<PackageTags>`, отвечают за метаданные, отображаемые в веб-канале NuGet.</span><span class="sxs-lookup"><span data-stu-id="846f3-143">The remaining settings such as `<Title>` and `<PackageTags>` have to do with metadata displayed on the NuGet feed.</span></span> <span data-ttu-id="846f3-144">См. подробнее о параметрах NuGet в описании [свойств NuGet и MSBuild](/nuget/reference/msbuild-targets).</span><span class="sxs-lookup"><span data-stu-id="846f3-144">For more information about NuGet settings, see [NuGet and MSBuild properties](/nuget/reference/msbuild-targets).</span></span>

<span data-ttu-id="846f3-145">Параметр `<TargetFramework>` необходимо задать так, чтобы MSBuild правильно запускался при выполнении команды pack для компиляции и упаковки проекта.</span><span class="sxs-lookup"><span data-stu-id="846f3-145">The `<TargetFramework>` setting must be set so that MSBuild will run properly when you run the pack command to compile and pack the project.</span></span>

<span data-ttu-id="846f3-146">Последние три параметра отвечают за правильную настройку проекта — добавление шаблонов в соответствующую папку в пакете NuGet при его создании.</span><span class="sxs-lookup"><span data-stu-id="846f3-146">The last three settings have to do with configuring the project correctly to include the templates in the appropriate folder in the NuGet pack when it's created.</span></span>

<span data-ttu-id="846f3-147">`<ItemGroup>` содержит два параметра.</span><span class="sxs-lookup"><span data-stu-id="846f3-147">The `<ItemGroup>` contains two settings.</span></span> <span data-ttu-id="846f3-148">Первый параметр `<Content>` добавляет все содержимое папки _templates_ в виде содержимого.</span><span class="sxs-lookup"><span data-stu-id="846f3-148">First, the `<Content>` setting includes everything in the _templates_ folder as content.</span></span> <span data-ttu-id="846f3-149">Он также предотвращает добавление папки _bin_ или _obj_ и компиляцию кода (если вы выполняли тестирование и компиляцию шаблонов).</span><span class="sxs-lookup"><span data-stu-id="846f3-149">It's also set to exclude any _bin_ folder or _obj_ folder to prevent any compiled code (if you tested and compiled your templates) from being included.</span></span> <span data-ttu-id="846f3-150">Второй параметр `<Compile>` предотвращает компиляцию файлов кода независимо от их расположения.</span><span class="sxs-lookup"><span data-stu-id="846f3-150">Second, the `<Compile>` setting excludes all code files from compiling no matter where they're located.</span></span> <span data-ttu-id="846f3-151">Этот параметр не позволяет проекту, используемому для созданию пакета шаблонов, компилировать код в иерархии папки _templates_.</span><span class="sxs-lookup"><span data-stu-id="846f3-151">This setting prevents the project being used to create a template pack from trying to compile the code in the _templates_ folder hierarchy.</span></span>

## <a name="build-and-install"></a><span data-ttu-id="846f3-152">Сборка и установка</span><span class="sxs-lookup"><span data-stu-id="846f3-152">Build and install</span></span>

<span data-ttu-id="846f3-153">Сохраните этот файл, а затем выполните команду pack.</span><span class="sxs-lookup"><span data-stu-id="846f3-153">Save this file and then run the pack command</span></span>

```dotnetcli
dotnet pack
```

<span data-ttu-id="846f3-154">Эта команда выполнит сборку проекта и создаст пакет NuGet в папке _working\bin\Debug_.</span><span class="sxs-lookup"><span data-stu-id="846f3-154">This command will build your project and create a NuGet package in This should be the _working\bin\Debug_ folder.</span></span>

```dotnetcli
dotnet pack
```

```console
Microsoft (R) Build Engine version 16.2.0-preview-19278-01+d635043bd for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 123.86 ms for C:\working\templatepack.csproj.

  templatepack -> C:\working\bin\Debug\netstandard2.0\templatepack.dll
  Successfully created package 'C:\working\bin\Debug\AdatumCorporation.Utility.Templates.1.0.0.nupkg'.
```

<span data-ttu-id="846f3-155">Затем установите файл пакета шаблонов с помощью команды `dotnet new -i PATH_TO_NUPKG_FILE`.</span><span class="sxs-lookup"><span data-stu-id="846f3-155">Next, install the template pack file with the `dotnet new -i PATH_TO_NUPKG_FILE` command.</span></span>

```console
C:\working> dotnet new -i C:\working\bin\Debug\AdatumCorporation.Utility.Templates.1.0.0.nupkg
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Example templates: string extensions              stringext             [C#]              Common/Code
Console Application                               console               [C#], F#, VB      Common/Console
Example templates: async project                  consoleasync          [C#]              Common/Console/C#8
Class library                                     classlib              [C#], F#, VB      Common/Library
```

<span data-ttu-id="846f3-156">Если пакет NuGet был передан в веб-канал NuGet, можно использовать команду `dotnet new -i PACKAGEID`, в которой `PACKAGEID` совпадает с параметром `<PackageId>` из файла _CSPROJ_.</span><span class="sxs-lookup"><span data-stu-id="846f3-156">If you uploaded the NuGet package to a NuGet feed, you can use the `dotnet new -i PACKAGEID` command where `PACKAGEID` is the same as the `<PackageId>` setting from the _.csproj_ file.</span></span> <span data-ttu-id="846f3-157">Этот идентификатор пакета совпадает с идентификатором пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="846f3-157">This package ID is the same as the NuGet package identifier.</span></span>

## <a name="uninstall-the-template-pack"></a><span data-ttu-id="846f3-158">Удаление пакета шаблонов</span><span class="sxs-lookup"><span data-stu-id="846f3-158">Uninstall the template pack</span></span>

<span data-ttu-id="846f3-159">Независимо от того, как был установлен пакет шаблонов (непосредственно из файла _NUPKG_ или из веб-канала NuGet), процедура удаления пакета шаблонов будет одинаковой.</span><span class="sxs-lookup"><span data-stu-id="846f3-159">No matter how you installed the template pack, either with the _.nupkg_ file directly or by NuGet feed, removing a template pack is the same.</span></span> <span data-ttu-id="846f3-160">Определите `<PackageId>` шаблона, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="846f3-160">Use the `<PackageId>` of the template you want to uninstall.</span></span> <span data-ttu-id="846f3-161">Вы можете отобразить список всех установленных шаблонов, выполнив команду `dotnet new -u`.</span><span class="sxs-lookup"><span data-stu-id="846f3-161">You can get a list of templates that are installed by running the `dotnet new -u` command.</span></span>

```dotnetcli
dotnet new -u
```

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
  AdatumCorporation.Utility.Templates
    Templates:
      Example templates: async project (consoleasync) C#
      Example templates: string extensions (stringext) C#
```

<span data-ttu-id="846f3-162">Выполните команду `dotnet new -u AdatumCorporation.Utility.Templates`, чтобы удалить шаблон.</span><span class="sxs-lookup"><span data-stu-id="846f3-162">Run `dotnet new -u AdatumCorporation.Utility.Templates` to uninstall the template.</span></span> <span data-ttu-id="846f3-163">Команда `dotnet new` выводит справочную информацию без сведений о ранее установленных шаблонах.</span><span class="sxs-lookup"><span data-stu-id="846f3-163">The `dotnet new` command will output help information that should omit the templates you previously installed.</span></span>

<span data-ttu-id="846f3-164">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="846f3-164">Congratulations!</span></span> <span data-ttu-id="846f3-165">Вы выполнили установку и удаление пакета шаблонов.</span><span class="sxs-lookup"><span data-stu-id="846f3-165">you've installed and uninstalled a template pack.</span></span>

## <a name="next-steps"></a><span data-ttu-id="846f3-166">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="846f3-166">Next steps</span></span>

<span data-ttu-id="846f3-167">Дополнительные сведения о шаблонах см. в статье [Пользовательские шаблоны для команды dotnet new](../tools/custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="846f3-167">To learn more about templates, most of which you've already learned, see the [Custom templates for dotnet new](../tools/custom-templates.md) article.</span></span>

* [<span data-ttu-id="846f3-168">Вики-сайт, посвященный репозиторию dotnet/templating в GitHub</span><span class="sxs-lookup"><span data-stu-id="846f3-168">dotnet/templating GitHub repo Wiki</span></span>](https://github.com/dotnet/templating/wiki)
* [<span data-ttu-id="846f3-169">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="846f3-169">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
* [<span data-ttu-id="846f3-170">Схема *template.json* в хранилище схем JSON</span><span class="sxs-lookup"><span data-stu-id="846f3-170">*template.json* schema at the JSON Schema Store</span></span>](http://json.schemastore.org/template)
