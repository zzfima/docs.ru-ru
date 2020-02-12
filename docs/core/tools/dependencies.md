---
title: Управление зависимостями в средствах .NET Core
description: Сведения об управлении зависимостями с помощью средств .NET Core.
ms.date: 03/06/2017
ms.openlocfilehash: 916daca0240c10dc63ca96048590a426bc51d450
ms.sourcegitcommit: feb42222f1430ca7b8115ae45e7a38fc4a1ba623
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2020
ms.locfileid: "76965624"
---
# <a name="manage-dependencies-with-net-core-sdk-10"></a>Управление зависимостями с помощью пакета SDK для .NET Core 1.0

Помимо переноса проектов .NET Core из файла project.json в CSPROJ-файл и на платформу MSBuild произошло еще одно значительное изменение, которое привело к унификации файла проекта и ресурсов, обеспечивающих отслеживание зависимостей. Для проектов .NET Core это аналогично функции, которую раньше выполнял файл project.json. Не существует отдельного файла JSON или XML для отслеживания зависимостей NuGet. Вместе с этим изменением в синтаксис csproj также добавлен другой тип *ссылки* — `<PackageReference>`.

В этом документе описывается новый тип ссылки. Кроме того, в нем показано, как добавлять в проекты зависимость пакетов, используя этот новый тип ссылки.

## <a name="the-new-packagereference-element"></a>Новый элемент \<PackageReference>

Элемент `<PackageReference>` имеет следующую базовую структуру:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

Если вы знакомы с платформой MSBuild, она покажется вам похожей на другие, уже существующие ссылочные типы. Ключевым является инструкция `Include`, указывающая идентификатор пакета, который нужно добавить в проект. Дочерний элемент `<Version>` указывает версию, которую необходимо получить. Версии указываются в соответствии с [правилами версий NuGet](/nuget/create-packages/dependency-versions#version-ranges).

> [!NOTE]
> Если вы не знакомы с синтаксисом проектов и файлов, см. дополнительные сведения в [справочной документации по проектам MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference).

Зависимость, доступная только в конкретном целевом объекте, добавляется с использованием условий, как показано в следующем примере:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

Зависимость будет допустимой только при сборке для указанного целевого объекта. Элемент `$(TargetFramework)` в этом условии представляет собой задаваемое в проекте свойство MSBuild. Для наиболее распространенных приложений .NET Core это не требуется.

## <a name="add-a-dependency-to-the-project"></a>Добавление зависимости в проект

Добавить зависимость в проект очень просто. Ниже показано, как добавить в проект Json.NET версии `9.0.1`. Это применимо и к любой другой зависимости NuGet.

Файл проекта содержит как минимум два узла `<ItemGroup>`. В одном из узлов уже есть элементы `<PackageReference>`. Вы можете добавить зависимость в этот узел или создать новый — результат от этого не изменится.

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
