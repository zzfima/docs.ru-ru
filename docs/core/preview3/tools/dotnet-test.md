---
title: "Команда dotnet-test | Пакет SDK для .NET Core"
description: "Команда dotnet test служит для выполнения модульных тестов в проекте."
keywords: "dotnet-test, CLI, команда CLI, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 10/07/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 3a0fa917-eb0a-4d7e-9217-d06e65455675
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: 66c9f949980612f6e21b6d441c004cc09f4eb7d3

---

#<a name="dotnet-test"></a>dotnet-test

## <a name="name"></a>Имя

`dotnet-test` — .NET драйвер тестов

## <a name="synopsis"></a>Краткий обзор

`dotnet test [project] [--help] 
    [--settings] [--listTests] [--testCaseFilter] 
    [--testAdapterPath] [--logger] 
    [--configuration] [--output] [--framework] [--diag]
    [--noBuild]`  

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

`--noBuild` 

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



<!--HONumber=Nov16_HO3-->


