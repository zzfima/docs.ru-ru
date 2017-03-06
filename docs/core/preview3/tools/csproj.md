---
title: "Справочник по CSPROJ-файлу | Microsoft Docs"
description: "Различия между существующими файлами и файлами CSPROJ .NET Core"
keywords: "справочник, CSPROJ, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 07/02/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdc29497-64f2-4d11-a21b-4097e0bdf5c9
translationtype: Human Translation
ms.sourcegitcommit: 0402707f98af8b716b041ba1260162cd227918cc
ms.openlocfilehash: 98f6ced2a199bdbe2f91f46e48ffd3ac52438cf8

---

# <a name="additions-to-the-csproj-format-for-net-core"></a>Дополнения к формату CSPROJ для .NET Core

[!INCLUDE[preview-warning](../../../includes/warning.md)]

В этом обзорном документе перечислены изменения, внесенные в CSPROJ-файлы при переходе с `project.json` на `csproj` и [MSBuild](https://github.com/Microsoft/MSBuild). Дополнительную информацию, которая касается синтаксиса файла проекта в общем, и справку см. в документации по [файлу проекта MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-project-file-schema-reference).  

## <a name="additions"></a>Добавления

* Элемент PackageReference, который определяет зависимость NuGet в проекте. Атрибут `Include` указывает идентификатор пакета. 

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

## <a name="version"></a>Версия
`Version` указывает версию пакета для восстановления. Этот элемент подчиняется правилам схемы управления версиями NuGet.

## <a name="includeassets"></a>IncludeAssets
Атрибут `IncludeAssets` указывает, какие ресурсы пакета, указанные `<PackageReference>`, следует использовать. 

Атрибут может содержать по меньшей мере одно из перечисленных ниже значений.

* `Compile` — содержимое папки lib доступно для компиляции.
* `Runtime` — содержимое папки среды выполнения распределяется.
* `ContentFiles` — используется содержимое папки contentfiles.
* `Build` — используются свойства и целевые объекты в папке сборки.
* `Native` — содержимое копируется из основных ресурсов в папку выходных данных среды выполнения.
* `Analyzers` — используются анализаторы.

Кроме того, атрибут может содержать следующие значения.

* `None` — не используется ни один ресурс.
* `All` — используются все ресурсы.

## <a name="excludeassets"></a>ExcludeAssets
Атрибут `ExcludeAssets` указывает, какие ресурсы пакета, указанные `<PackageReference>`, не следует использовать.

Атрибут может содержать по меньшей мере одно из перечисленных ниже значений.

* `Compile` — содержимое папки lib доступно для компиляции.
* `Runtime` — содержимое папки среды выполнения распределяется.
* `ContentFiles` — используется содержимое папки contentfiles.
* `Build` — используются свойства и целевые объекты в папке сборки.
* `Native` — содержимое копируется из основных ресурсов в папку выходных данных среды выполнения.
* `Analyzers` — используются анализаторы.

Или элемент может содержать следующие значения.

* `None` — не используется ни один ресурс.
* `All` — используются все ресурсы.

## <a name="privateassets"></a>PrivateAssets
Атрибут `PrivateAssets` указывает, какие ресурсы пакета, указанные `<PackageReference>`, следует использовать. Но они не должны передаваться в следующий проект. 

> [!NOTE]
> Это новый термин для элемента project.json/xproj `SuppressParent`. 

Атрибут может содержать по меньшей мере одно из перечисленных ниже значений.

* `Compile` — содержимое папки lib доступно для компиляции.
* `Runtime` — содержимое папки среды выполнения распределяется.
* `ContentFiles` — используется содержимое папки contentfiles.
* `Build` — используются свойства и целевые объекты в папке сборки.
* `Native` — содержимое копируется из основных ресурсов в папку выходных данных среды выполнения.
* `Analyzers` — используются анализаторы.

Кроме того, атрибут может содержать следующие значения.

* `None` — не используется ни один ресурс.
* `All` — используются все ресурсы.

* Элемент `<DotnetCliToolReference>` DotnetCliToolReference указывает средство интерфейса командной строки, которое пользователь хочет восстановить в контексте проекта. Этот элемент используется вместо узла `tools` в файле `project.json`. 

```xml
<DotnetCliToolReference Include="<package-id>" Version="" />
```

## <a name="version"></a>Версия
`Version` указывает версию пакета для восстановления. Этот атрибут подчиняется правилам схемы управления версиями NuGet.

* Элемент `<RuntimeIdentifiers>` RuntimeIdentifiers позволяет указать для проекта список [идентификаторов среды выполнения](../../rid-catalog.md) (в качестве разделителя используется точка с запятой). Идентификаторы среды выполнения позволяют публиковать автономные развертывания. 

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```


* Элемент `<RuntieIdentifier>` RuntimeIdentifier позволяет указать для проекта только [идентификатор среды выполнения](../../rid-catalog.md). Идентификаторы среды выполнения позволяют опубликовать автономное развертывание. 

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```


* Элемент `<PackageTargetFallback>` PackageTargetFallback позволяет указать набор совместимых целевых объектов, которые следует использовать при восстановлении пакетов. Он разрешает пакетам, использующим dotnet TxM, взаимодействовать с пакетами, которые не объявляют dotnet TxM. Если в проекте используется dotnet TxM, все пакеты, от которых вы зависите, должны также содержать dotnet TxM. В противном случае нужно добавить `<PackageTargetFallback>` в проект, чтобы обеспечить совместимость с платформами, отличными от dotnet. 

В следующем примере приводятся резервные варианты для всех целевых объектов в проекте: 

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

В следующем примере приводятся резервные варианты только для целевого объекта `netcoreapp1.0`:

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp1.0'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="nuget-metadata-properties"></a>Свойства метаданных NuGet
При переходе к MSbuild мы переместили входные метаданные, которые использовались при упаковке пакета NuGet из project.json в CSPROJ-файлы. Входные данные — это свойства MSBuild. Ниже представлен список свойств, которые используются как входные данные в процессе упаковки при использовании команды `dotnet pack` или целевого объекта `Pack` MSBuild, входящего в SDK. 

* IsPackable
* PackageVersion
* PackageId
* Заголовок
* Authors
* Описание
* Copyright
* PackageRequireLicenseAcceptance
* PackageLicenseUrl
* PackageProjectUrl
* PackageIconUrl
* PackageReleaseNotes
* PackageTags
* PackageOutputPath
* IncludeSymbols
* IncludeSource
* PackageTypes
* IsTool
* RepositoryUrl
* RepositoryType
* NoPackageAnalysis
* MinClientVersion
* IncludeBuildOutput
* IncludeContentInPack
* BuildOutputTargetFolder
* ContentTargetFolders
* NuspecFile
* NuspecBasePath
* NuspecProperties


<!--HONumber=Feb17_HO2-->


