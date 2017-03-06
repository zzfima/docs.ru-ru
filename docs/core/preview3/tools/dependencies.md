---
title: "Управление зависимостями в средствах .NET Core | Документы Майкрософт"
description: "Сведения об управлении зависимостями с помощью средств .NET Core."
keywords: "CLI, расширяемость, пользовательские команды, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 11/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 74b87cdb-a244-4c13-908c-539118bfeef9
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: cef45d986eb9c4a84a03ee942c29a327c23cabf3

---

# <a name="managing-dependencies-in-net-core-rc4-tooling"></a>Управление зависимостями в средствах версии-кандидата 4 .NETCore

[!INCLUDE[preview-warning](../../../includes/warning.md)]

Помимо переноса проектов .NET Core из файла project.json в CSPROJ-файл и на платформу MSBuild произошло еще одно значительное изменение, которое привело к унификации файла проекта и ресурсов, обеспечивающих отслеживание зависимостей. Для проектов .NET Core это аналогично тому, что раньше выполнял файл project.json. Не существует отдельного файла JSON или XML для отслеживания зависимостей NuGet. Вместе с этим изменением в синтаксис csproj также добавлен другой тип *ссылки* — `<PackageReference>`. 

В этом документе описывается новый тип ссылки. Кроме того, в нем показано, как добавлять в проекты зависимость пакетов, используя этот новый тип ссылки. 

## <a name="the-new-packagereference-element"></a>Новый элемент <PackageReference>
Элемент `<PackageReference>` имеет следующую базовую структуру:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

Если вы знакомы с платформой MSBuild, она покажется вам похожей на другие, уже существующие ссылочные типы. Ключевым является оператор `Include`, указывающий идентификатор пакета, который нужно добавить в проект. Дочерний элемент `<Version>` указывает версию, которую необходимо получить. Версии указываются в соответствии с [правилами версий NuGet](https://docs.microsoft.com/nuget/create-packages/dependency-versions#version-ranges).

> [!NOTE]
> Если вы не знакомы с общими понятиями синтаксиса `csproj`, используйте [справочную документацию по проекту MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-project-file-schema-reference) для ознакомления с ними.  

Добавление зависимости, которая доступна только в конкретном целевом объекте, выполняется с использованием условий, аналогичных в приведенном далее примере.

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp1.0'" />
```

Указанное выше означает, что зависимость будет действительной только в том случае, если для затронутого целевого объекта выполняется сборка. Элемент `$(TargetFramework)` в этом условии представляет собой заданное в проекте свойство MSBuild. Для наиболее распространенных приложений .NET Core это не требуется. 

## <a name="adding-a-dependency-to-your-project"></a>Добавление зависимости в проект
Добавить зависимость в проект очень просто. Ниже показано, как добавить в проект Json.NET версии `9.0.1`. Это применимо и к любой другой зависимости NuGet. 

При открытии файла проекта вы увидите не менее двух узлов `<ItemGroup>`. Можно заметить, что на одном из узлов уже есть элементы `<PackageReference>`. Вы можете добавить новую зависимость на этот узел или создать новый — поступайте по своему усмотрению, так как результат от этого не изменится. 

В этом примере мы будем использовать шаблон по умолчанию, добавленный `dotnet new`. Это простое консольное приложение. При открытии проекта мы сначала видим узел `<ItemGroup>` и существующий на нем элемент `<PackageReference>`. Затем мы добавляем к нему следующее:

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```
После этого мы сохраняем проект и выполняем команду `dotnet restore` для установки зависимости. 

Весь проект выглядит следующим образом:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.0</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
</Project>
```

## <a name="removing-a-dependency-from-the-project"></a>Удаление зависимости из проекта
Чтобы удалить зависимость из файла проекта, достаточно просто удалить `<PackageReference>` из файла проекта.


<!--HONumber=Feb17_HO2-->


