---
title: Управление зависимостями в средствах .NET Core
description: Сведения об управлении зависимостями с помощью средств .NET Core.
ms.date: 03/06/2017
ms.openlocfilehash: 28280dc05e746cdef4e90870cd4cb528382c45bd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76787864"
---
# <a name="manage-dependencies-with-net-core-sdk-10"></a>Управление зависимостями с помощью пакета SDK для .NET Core 1.0

Помимо переноса проектов .NET Core из файла project.json в CSPROJ-файл и на платформу MSBuild произошло еще одно значительное изменение, которое привело к унификации файла проекта и ресурсов, обеспечивающих отслеживание зависимостей. Для проектов .NET Core это аналогично функции, которую раньше выполнял файл project.json. Не существует отдельного файла JSON или XML для отслеживания зависимостей NuGet. Вместе с этим изменением в синтаксис csproj также добавлен другой тип *ссылки* — `<PackageReference>`.

В этом документе описывается новый тип ссылки. Кроме того, в нем показано, как добавлять в проекты зависимость пакетов, используя этот новый тип ссылки.

## <a name="the-new-packagereference-element"></a>Новый элемент \<PackageReference>

Элемент `<PackageReference>` имеет следующую базовую структуру:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

Если вы знакомы с платформой MSBuild, она покажется вам похожей на другие, уже существующие ссылочные типы. Ключевым является оператор `Include`, указывающий идентификатор пакета, который нужно добавить в проект. Дочерний элемент `<Version>` указывает версию, которую необходимо получить. Версии указываются в соответствии с [правилами версий NuGet](/nuget/create-packages/dependency-versions#version-ranges).

> [!NOTE]
> Если вы не знакомы с общими понятиями синтаксиса `csproj`, используйте [справочную документацию по проекту MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference) для ознакомления с ними.

Добавление зависимости, которая доступна только в конкретном целевом объекте, выполняется с использованием условий, аналогичных в приведенном далее примере.

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

Указанное выше означает, что зависимость будет действительной только в том случае, если для затронутого целевого объекта выполняется сборка. Элемент `$(TargetFramework)` в этом условии представляет собой заданное в проекте свойство MSBuild. Для наиболее распространенных приложений .NET Core это не требуется.

## <a name="add-a-dependency-to-the-project"></a>Добавление зависимости в проект

Добавить зависимость в проект очень просто. Ниже показано, как добавить в проект Json.NET версии `9.0.1`. Это применимо и к любой другой зависимости NuGet.

При открытии файла проекта вы увидите не менее двух узлов `<ItemGroup>`. Можно заметить, что на одном из узлов уже есть элементы `<PackageReference>`. Вы можете добавить новую зависимость в этот узел или создать новый. Поступайте по своему усмотрению, так как результат от этого не изменится.

В приведенном ниже примере используется шаблон по умолчанию, который удаляется командой `dotnet new console`. Это простое консольное приложение. При открытии проекта вы увидите узел `<ItemGroup>`, в котором уже есть элемент `<PackageReference>`. Добавьте к нему следующее:

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

После этого сохраните проект и выполните команду `dotnet restore` для установки зависимости.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Весь проект выглядит следующим образом:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
</Project>
```

## <a name="remove-a-dependency-from-the-project"></a>Удаление зависимости из проекта

Чтобы удалить зависимость из файла проекта, достаточно просто удалить `<PackageReference>` из файла проекта.
