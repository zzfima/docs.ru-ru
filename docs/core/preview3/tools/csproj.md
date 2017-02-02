---
title: "Справочник по CSPROJ-файлу | Microsoft Docs"
description: "Различия между существующими файлами и файлами CSPROJ .NET Core"
keywords: "справочник, CSPROJ, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 10/12/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdc29497-64f2-4d11-a21b-4097e0bdf5c9
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: dfa7cc0f7005269b4e2560c8bbc8b049ed02cc1a

---

# <a name="additions-to-the-csproj-format-for-net-core"></a>Дополнения к формату CSPROJ для .NET Core

[!INCLUDE[preview-warning](../../../includes/warning.md)]

В этом обзорном документе перечислены изменения, внесенные в CSPROJ-файлы при переходе с `project.json` на `csproj` и [MSBuild](https://github.com/Microsoft/MSBuild). Дополнительную информацию, которая касается синтаксиса файла проекта в общем, и справку см. в документации по [файлу проекта MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-project-file-schema-reference).  

## <a name="additions"></a>Добавления

### <a name="packagereference"></a>PackageReference
Определяет зависимость NuGet в проекте. Атрибут `Include` указывает идентификатор пакета. 

```xml
<PackageReference Include="<package-id>">
    <Version></Version>
    <PrivateAssets></PrivateAssets>
    <IncludeAssets></IncludeAssets>
    <ExcludeAssets></ExcludeAssets>
</PackageReference>
```

#### <a name="version"></a>Версия
`<Version>` указывает версию пакета для восстановления. Этот элемент подчиняется правилам схемы управления версиями NuGet.

#### <a name="includeassets"></a>IncludeAssets
Дочерний элемент `<IncludeAssets>` указывает, какие ресурсы пакета, указанные родительским элементом `<PackageReference>`, следует использовать. 

Элемент может одержать одно из следующих значений (или несколько).

* Compile — содержимое папки lib доступно для компиляции.
* Runtime — содержимое папки среды выполнения распределяется.
* ContentFiles — используется содержимое папки contentfiles.
* Build — используются свойства и целевые объекты в папке сборки.
* Native — содержимое копируется из основных ресурсов в папку выходных данных среды выполнения.
* Analyzers — используются анализаторы.

Или элемент может содержать следующие значения.

* None — не используется ни один ресурс.
* All — используются все ресурсы.

#### <a name="excludeassets"></a>ExcludeAssets
Дочерний элемент `<ExcludeAssets>` указывает, какие ресурсы пакета, указанные родительским элементом `<PackageReference>`, не следует использовать.

Элемент может одержать одно из следующих значений (или несколько).

* Compile — содержимое папки lib доступно для компиляции.
* Runtime — содержимое папки среды выполнения распределяется.
* ContentFiles — используется содержимое папки contentfiles.
* Build — используются свойства и целевые объекты в папке сборки.
* Native — содержимое копируется из основных ресурсов в папку выходных данных среды выполнения.
* Analyzers — используются анализаторы.

Или элемент может содержать следующие значения.

* None — не используется ни один ресурс.
* All — используются все ресурсы.

#### <a name="privateassets"></a>PrivateAssets
Дочерний элемент `<PrivateAssets>` указывает, какие ресурсы пакета, указанные родительским элементом `<PackageReference>`, следует использовать. Но они не должны передаваться в следующий проект. 

> [!NOTE]
> Это новый термин для элемента project.json/xproj `SuppressParent`. 

Элемент может одержать одно из следующих значений (или несколько).

* Compile — содержимое папки lib доступно для компиляции.
* Runtime — содержимое папки среды выполнения распределяется.
* ContentFiles — используется содержимое папки contentfiles.
* Build — используются свойства и целевые объекты в папке сборки.
* Native — содержимое копируется из основных ресурсов в папку выходных данных среды выполнения.
* Analyzers — используются анализаторы.

Или элемент может содержать следующие значения.

* None — не используется ни один ресурс.
* All — используются все ресурсы.

### <a name="dotnetclitoolreference"></a>DotnetCliToolReference
Элемент `<DotnetCliToolReference>` указывает средство интерфейса командной строки, которое пользователь хочет восстановить в контексте проекта. Этот элемент используется вместо узла `tools` в файле `project.json`. 

#### <a name="version"></a>Версия
`<Version>` указывает версию пакета для восстановления. Этот элемент подчиняется правилам схемы управления версиями NuGet.

### <a name="runtimeidentifiers"></a>RuntimeIdentifiers
Элемент `<RuntimeIdentifiers>` позволяет указать для проекта список [идентификаторов среды выполнения ((RID)](../../rid-catalog.md) (в качестве разделителя используется точка с запятой). Идентификаторы позволяют публиковать автономные развертывания. 


<!--HONumber=Jan17_HO3-->


