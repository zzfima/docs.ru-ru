---
title: "Средства управления зависимостями в предварительной версии 3 платформы .NET Core"
description: "В предварительной версии 3 изменены механизмы управления зависимостями."
keywords: "CLI, расширяемость, пользовательские команды, .NET Core"
author: blackdwarf
manager: wpickett
ms.date: 11/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 74b87cdb-a244-4c13-908c-539118bfeef9
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: e04d5f3b08c7f6885ed9914a91fc308234e6ce3b

---

<a name="managing-dependencies-in-net-core-preview-3-tooling"></a>Средства управления зависимостями в предварительной версии 3 платформы .NET Core
----------------------------------------------------

# <a name="overview"></a>Обзор
Помимо переноса проектов .NET Core из файла project.json в файл csproj и на платформу MSBuild произошло еще одно значительное изменение, которое привело к унификации файла проекта и ресурсов, позволяющих отслеживать зависимости. Для проектов .NET Core это аналогично тому, что раньше выполнял файл project.json. Не существует отдельного файла JSON или XML для отслеживания зависимостей NuGet. Вместе с этим изменением в синтаксис csproj также добавлен другой тип *ссылки* — `<PackageReference>`. 

В этом документе описывается новый тип ссылки. Кроме того, в нем показано, как добавлять в проекты зависимость пакетов, используя этот новый тип ссылки. 

# <a name="the-new-packagereference-element"></a>Новый элемент <PackageReference>
Элемент `<PackageReference>` имеет следующую базовую структуру:

```xml
<PackageReference Include="<Package_ID>">
    <Version>PACKAGE_VERSION</Version>
</PackageReference>
```

Если вы знакомы с платформой MSBuild, она покажется вам похожей на другие, уже существующие [типы ссылок](). Ключевым является оператор `Include`, указывающий идентификатор пакета, который нужно добавить в проект. Дочерний элемент `<Version>` указывает версию, которую необходимо получить. Версии указываются в соответствии с [правилами версий NuGet](https://docs.nuget.org/ndocs/create-packages/dependency-versions#version-ranges).  

> **Примечание.** Если вы не знакомы с общими понятиями синтаксиса `csproj`, используйте для ознакомления [справочную документацию по проекту MSBuild]().  

Добавление зависимости, которая доступна только в конкретном целевом объекте, выполняется с использованием следующих условий:

```xml
<PackageReference Include="<Package_ID>" Condition="'$(TargetFramework)' == 'netcoreapp1.0'">
    <Version>PACKAGE_VERSION</Version>
</PackageReference>
```

Указанное выше означает, что зависимость будет действительной только в том случае, если для затронутого целевого объекта выполняется сборка. Элемент `$(TargetFramework)` в этом условии представляет собой заданное в проекте свойство MSBuild. Для наиболее распространенных приложений .NET Core это не требуется. 

# <a name="adding-a-dependency-to-your-project"></a>Добавление зависимости в проект
Добавить зависимость в проект очень просто. Ниже показано, как добавить в проект `JSON.net` версии `9.0.1`. Это применимо и к любой другой зависимости NuGet. 

При открытии файла проекта вы увидите не менее двух узлов `<ItemGroup>`. Можно заметить, что на одном из узлов уже есть элементы `<PackageReference>`. Вы можете добавить новую зависимость на этот узел или создать новый — поступайте по своему усмотрению, так как результат от этого не изменится. 

В этом примере мы будем использовать шаблон по умолчанию, добавленный `dotnet new`. Это простое консольное приложение. При открытии проекта мы сначала видим узел `<ItemGroup>` и существующий на нем элемент `<PackageReference>`. Затем мы добавляем к нему следующее:

```xml
<PackageReference Include="Newtonsoft.Json">
    <Version>9.0.1</Version>
</PackageReference>
```
После этого мы сохраняем проект и выполняем команду `dotnet restore` для установки зависимости. 

Весь проект выглядит следующим образом:

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
    <PackageReference Include="Newtonsoft.Json">
        <Version>9.0.1</Version>
    </PackageReference>
    <PackageReference Include="Microsoft.NET.Sdk">
      <Version>1.0.0-alpha-20161104-2</Version>
      <PrivateAssets>All</PrivateAssets>
    </PackageReference>
  </ItemGroup>
  
  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
</Project>
```

# <a name="removing-a-dependency-from-the-project"></a>Удаление зависимости из проекта
Чтобы удалить зависимость из файла проекта, достаточно просто удалить `<PackageReference>` из файла проекта. 





<!--HONumber=Nov16_HO3-->


