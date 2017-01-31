---
title: "Команда dotnet-test | Microsoft Docs"
description: "Команда `dotnet test` служит для выполнения модульных тестов в проекте."
keywords: "dotnet-test, CLI, команда CLI, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 10/07/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 4bf0aef4-148a-41c6-bb95-0a9e1af8762e
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: fb4627f5f8754ff3432d92e20dff2684a92fbeb5

---

#<a name="dotnet-test-tooling-preview-4"></a>dotnet-test (предварительная версия 4 инструментов)

> [!WARNING]
> Эта статья применима к инструментам .NET Core (предварительная версия 4) для версии-кандидата Visual Studio 2017. Версия этой статьи об инструментах .NET Core (предварительная версия 2): [dotnet-test](../../tools/dotnet-test.md).

## <a name="name"></a>Имя

`dotnet-test` — .NET драйвер тестов

## <a name="synopsis"></a>Краткий обзор

`dotnet test [project] [--help] 
    [--settings] [--listTests] [--testCaseFilter] 
    [--testAdapterPath] [--logger] 
    [--configuration] [--output] [--framework] [--diag]
    [--no-build]`  

## <a name="description"></a>Описание

Команда `dotnet test` служит для выполнения модульных тестов в проекте. Модульные тесты — это проекты библиотек классов, которые имеют зависимости от среды модульного тестирования (например, NUnit или xUnit) и средства запуска тестов dotnet для этой среды. Они упаковываются в пакеты NuGet и восстанавливаются как обычные зависимости проекта.

Для тестирования проектов также нужно указать средство выполнения тестов. Для этого используется обычный элемент `<PackageReference>`, как показано в следующем образце файла проекта:

```xml
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.0</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <Compile Include="**\*.cs" />
    <EmbeddedResource Include="**\*.resx" />
  </ItemGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.NETCore.App">
      <Version>1.0.1</Version>
    </PackageReference>
    <PackageReference Include="Microsoft.NET.Sdk">
      <Version>1.0.0-alpha-20161104-2</Version>
      <PrivateAssets>All</PrivateAssets>
    </PackageReference>
    <PackageReference Include="Microsoft.NET.Test.Sdk">
      <Version>15.0.0-preview-20161024-02</Version>
    </PackageReference>
    <PackageReference Include="xunit">
      <Version>2.2.0-beta3-build3402</Version>
    </PackageReference>
    <PackageReference Include="xunit.runner.visualstudio">
      <Version>2.2.0-beta4-build1188</Version>
    </PackageReference>
  </ItemGroup>

  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
</Project>
```

## <a name="options"></a>Параметры

`[project]`
    
Указывает путь к тестовому проекту. Если значение не задано, по умолчанию используется текущий каталог.

`-h|--help`

Выводит краткую справку по команде.

`-s | --settings <SETTINGS_FILE>`

Параметры, используемые при выполнении тестов. 

`-lt | --listTests`

Отображение списка всех обнаруженных тестов в текущем проекте. 

`-tcf | --testCaseFilter <EXPRESSION>`

Фильтрация тестов в текущем проекте с помощью заданного выражения. 

`-tap | --testAdapterPath <TEST_ADAPTER_PATH>`

Использование адаптеров пользовательского теста из указанного пути в ходе этого теста. 

`--logger <LOGGER>`

Укажите средство ведения журнала результатов тестирования. 

`-c|--configuration <Debug|Release>`

Конфигурация для сборки. Значение по умолчанию — `Release`. 

`-o|--output [OUTPUT_DIRECTORY]`

Каталог, в котором выполняется поиск двоичных файлов для выполнения.

`-f|--framework [FRAMEWORK]`

Поиск тестовых двоичных файлов для определенной платформы.

`-r|--runtime [RUNTIME_IDENTIFIER]`

Поиск тестовых двоичных файлов для указанной среды выполнения.

`--no-build` 

Не выполняет сборку тестового проекта перед его запуском. 

`-d | --diag <DIAGNOSTICS_FILE>`

Включение режима диагностики для платформы тестирования и запись диагностических сообщений в указанный файл. 

## <a name="examples"></a>Примеры

Выполнение тестов в проекте в текущем каталоге:

`dotnet test` 

Выполнение тестов в проекте test1:

`dotnet test ~/projects/test1/test1.csproj` 

## <a name="see-also"></a>См. также

[Платформы](../../../standard/frameworks.md)

[Каталог идентификаторов сред выполнения (RID)](../../rid-catalog.md)



<!--HONumber=Jan17_HO3-->


