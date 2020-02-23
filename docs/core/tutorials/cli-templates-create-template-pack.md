---
title: Создание пакета шаблонов для команды dotnet new
description: Узнайте, как создать файл CSPROJ, с помощью которого выполняется сборка пакета шаблонов для команды dotnet new.
author: thraka
ms.date: 12/10/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: 5bc926861dd6a501d7c2d24bd5f7c4116cc78b2c
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503488"
---
# <a name="tutorial-create-a-template-pack"></a>Учебник. Создание пакета шаблонов

С помощью .NET Core вы можете создавать и развертывать шаблоны, которые генерируют проекты, файлы и даже ресурсы. Это третья часть серии руководств по созданию, установке и удалению шаблонов с помощью команды `dotnet new`.

Из этой части вы узнаете, как выполнять такие задачи:

> [!div class="checklist"]
>
> * создание проекта \*.csproj для сборки пакета шаблонов;
> * настройка файла проекта для упаковки;
> * установка шаблона из файла пакета NuGet;
> * удаление шаблона по идентификатору пакета.

## <a name="prerequisites"></a>Предварительные требования

* Изучите [первую](cli-templates-create-item-template.md) и [вторую](cli-templates-create-project-template.md) части этой серии руководств.

  Для этого руководства используются два шаблона, созданные в ходе работы с первыми двумя руководствами серии. Вы можете использовать другой шаблон, сохранив его в папку _working\templates\\_ .

* Откройте терминал и перейдите в папку _working\templates\\_ .

## <a name="create-a-template-pack-project"></a>Создание проекта пакета шаблонов

Пакет шаблонов — это один или несколько шаблонов, упакованных в файл. При установке или удалении пакета все шаблоны, содержащиеся в пакете, соответственно добавляются или удаляются. В предыдущих частях этой серии руководств использовались только отдельные шаблоны. Чтобы установить неупакованный шаблон, необходимо скопировать папку шаблона и выполнить его установку из папки. Так как пакет шаблонов может содержать несколько шаблонов и является одним файлом, процесс установки шаблонов упрощается.

Пакет шаблонов — это файл пакета NuGet (_NUPKG_). Как и любой пакет NuGet, пакет шаблонов можно передать в веб-канал NuGet. С помощью команды `dotnet new -i` можно установить пакет шаблонов из веб-канала NuGet. Кроме того, пакет шаблонов можно установить непосредственно из файла _NUPKG_.

Для компиляции кода и создания двоичного файла обычно используется файл проекта C#. Но проект также можно использовать для создания пакета шаблонов. Изменив параметры файла _CSPROJ_, можно не выполнять компиляцию кода, а добавить все ресурсы в шаблон. Во время сборки этого проекта создается пакет NuGet с пакетом шаблонов.

Созданный пакет будет содержать [шаблон элемента](cli-templates-create-item-template.md) и [шаблон проекта](cli-templates-create-project-template.md), созданные ранее. Так как мы поместили оба шаблона в папку _working\templates\\_ , можно добавить файл _CSPROJ_ в папку _working_.

В окне терминала перейдите к папке _working_. Создайте проект, задайте ему имя `templatepack` и укажите текущую папку в качестве целевой.

```dotnetcli
dotnet new console -n templatepack -o .
```

Параметр `-n` присваивает файлы _.csproj_ имя _templatepack.csproj_. Параметр `-o` создает файлы в текущем каталоге. Отобразится результат примерно такого содержания:

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

Затем откройте файл _templatepack.csproj_ в редакторе и замените содержимое следующим кодом XML:

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

Параметры `<PropertyGroup>` в приведенном выше коде XML разделены на три группы. Первая группа отвечает за свойства, необходимые для пакета NuGet. Три параметра `<Package` отвечают за свойства пакета NuGet, необходимые для обнаружения пакета в веб-канале NuGet. В частности, значение `<PackageId>` позволяет удалить пакет шаблонов по имени и не указывать путь к его каталогу. Оно также позволяет установить пакет шаблонов из веб-канала NuGet. Остальные параметры, такие как `<Title>` и `<PackageTags>`, отвечают за метаданные, отображаемые в веб-канале NuGet. См. подробнее о параметрах NuGet в описании [свойств NuGet и MSBuild](/nuget/reference/msbuild-targets).

Параметр `<TargetFramework>` необходимо задать так, чтобы MSBuild правильно запускался при выполнении команды pack для компиляции и упаковки проекта.

Последние три параметра отвечают за правильную настройку проекта — добавление шаблонов в соответствующую папку в пакете NuGet при его создании.

`<ItemGroup>` содержит два параметра. Первый параметр `<Content>` добавляет все содержимое папки _templates_ в виде содержимого. Он также предотвращает добавление папки _bin_ или _obj_ и компиляцию кода (если вы выполняли тестирование и компиляцию шаблонов). Второй параметр `<Compile>` предотвращает компиляцию файлов кода независимо от их расположения. Этот параметр не позволяет проекту, используемому для созданию пакета шаблонов, компилировать код в иерархии папки _templates_.

## <a name="build-and-install"></a>Сборка и установка

Сохраните этот файл, а затем выполните команду pack.

```dotnetcli
dotnet pack
```

Эта команда выполнит сборку проекта и создаст пакет NuGet в папке _working\bin\Debug_.

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

Затем установите файл пакета шаблонов с помощью команды `dotnet new -i PATH_TO_NUPKG_FILE`.

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

Если пакет NuGet был передан в веб-канал NuGet, можно использовать команду `dotnet new -i PACKAGEID`, в которой `PACKAGEID` совпадает с параметром `<PackageId>` из файла _CSPROJ_. Этот идентификатор пакета совпадает с идентификатором пакета NuGet.

## <a name="uninstall-the-template-pack"></a>Удаление пакета шаблонов

Независимо от того, как был установлен пакет шаблонов (непосредственно из файла _NUPKG_ или из веб-канала NuGet), процедура удаления пакета шаблонов будет одинаковой. Определите `<PackageId>` шаблона, который требуется удалить. Вы можете отобразить список всех установленных шаблонов, выполнив команду `dotnet new -u`.

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

Выполните команду `dotnet new -u AdatumCorporation.Utility.Templates`, чтобы удалить шаблон. Команда `dotnet new` выводит справочную информацию без сведений о ранее установленных шаблонах.

Поздравляем! Вы выполнили установку и удаление пакета шаблонов.

## <a name="next-steps"></a>Следующие шаги

Дополнительные сведения о шаблонах см. в статье [Пользовательские шаблоны для команды dotnet new](../tools/custom-templates.md).

* [Вики-сайт, посвященный репозиторию dotnet/templating в GitHub](https://github.com/dotnet/templating/wiki)
* [Репозиторий dotnet/dotnet-template-samples в GitHub](https://github.com/dotnet/dotnet-template-samples)
* [Схема *template.json* в хранилище схем JSON](http://json.schemastore.org/template)
