---
title: "Справочник по CSPROJ-файлу | Microsoft Docs"
description: "Различия между существующими файлами и файлами CSPROJ .NET Core"
keywords: "справочник, CSPROJ, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/03/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdc29497-64f2-4d11-a21b-4097e0bdf5c9
translationtype: Human Translation
ms.sourcegitcommit: b4fb772973607b94e120377879a5dbdde2a25271
ms.openlocfilehash: cd0b59b4a91dc4a83d73db55d8d0e611f73f63a6
ms.lasthandoff: 03/15/2017

---

# <a name="additions-to-the-csproj-format-for-net-core"></a>Дополнения к формату CSPROJ для .NET Core

В этом документе перечислены изменения, внесенные в файлы проекта при перемещении из *project.json* в *CSPROJ* и [MSBuild](https://github.com/Microsoft/MSBuild). Дополнительную информацию, которая касается синтаксиса файла проекта в общем, и справку см. в документации по [файлу проекта MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-project-file-schema-reference).  

## <a name="implicit-package-references"></a>Неявные ссылки на пакет
Теперь неявные ссылки на метапакеты указываются в зависимости от целевой платформы, указанной в свойстве `<TargetFramework>` или `<TargetFrameworks>` файла проекта. Если целевая платформа равна `netcoreap1.x`, указывается ссылка на соответствующую версию метапакета `Microsoft.NETCore.App`. В противном случае, если целевая платформа равна `netstandard1.x`, указывается ссылка на соответствующую версию метапакета `NetStandard.Library`.

В отношении остальной части поведения все средства будут работать должным образом, а основная часть жестов остается прежней (например, `dotnet restore`). 

### <a name="recommendations"></a>Рекомендации
Так как теперь на метапакеты `Microsoft.NETCore.App` или `NetStandard.Library` теперь указываются неявные ссылки, ниже приведены наши рекомендации по данной теме:

* Никогда не указывайте явную ссылку на метапакеты `Microsoft.NETCore.App` или `NetStandard.Library` через свойство `<PackageReference>` в файле проекта.
* Если нужна определенная версия среды выполнения, вместо ссылки на метапакет следует использовать свойство `<RuntimeFrameworkVersion>` в проекте (например, `1.0.4`).
    * Это может произойти, например, когда вы используете [автономные развертывания](../deploying/index.md#self-contained-deployments-scd) и нуждаетесь в определенной версии исправления 1.0.0 LTS для среды выполнения.
* Если вам нужна конкретная версия метапакета `NetStandard.Library`, можно использовать свойство `<NetStandardImplicitPackageVersion>` и установите требуемую версию. 

## <a name="default-compilation-includes-in-net-core-projects"></a>Компиляция по умолчанию, включенная в проекты .NET Core
В рамках перехода на формат *CSPROJ* в последних версиях пакета SDK мы перенесли включения и исключения по умолчанию для элементов Compile и внедренные ресурсы в файлы свойств пакета SDK. Это означает, что вам больше не нужно указывать эти элементы в файле проекта. 

Основной причиной этого является стремление очистить ваш файл проекта от всего лишнего. Значения по умолчанию в пакете SDK должны охватывать наиболее распространенные варианты использования, поэтому нет необходимости повторять их в каждом создаваемом проекте. Это позволяет уменьшить файлы проекта и гораздо проще читать их, а также вносить правки вручную. 

Следующая таблица показывает, какой элемент и какие [стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) включены и исключены в пакете SDK: 

| Элемент              | Стандартная маска включения                               | Стандартная маска исключения                                                     | Стандартная маска удаления                  |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| Компилятор              | \*\*/\*.cs (или другие расширения языка) | \*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc     | Н/Д                          |
| ВнедренныйРесурс     | \*\*/\*.resx                                 | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | Н/Д                          |
| Нет                 | \*\*/\*                                      | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | - \*\*/\*.cs; \*\*/\*.resx |

Если в вашем проекте имеются стандартные маски и вы пытаетесь выполнить его сборку с помощью новейшего пакета SDK, появится следующая ошибка:

> Duplicate Compile items were included. The .NET SDK includes Compile items from your project directory by default. You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file. (Включены повторяющиеся элементы Compile. По умолчанию пакет SDK для .NET включает элементы Compile из каталога проекта. Можно удалить эти элементы из файла проекта или задать для свойства "EnableDefaultCompileItems" значение "false", чтобы явно включить их в файл проекта.) 

Чтобы обойти эту ошибку, можно либо удалить явные элементы `Compile`, которые соответствуют указанным в предыдущей таблице, либо установить для свойства `<EnableDefaultCompileItems>` значение `false`, как показано ниже:

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
Указание значения `false` для этого свойства переопределяет неявное включение, в результате чего возвращается поведение для предыдущих пакетов SDK, где требовалось задавать стандартные маски по умолчанию в проекте. 

Это изменение не затрагивает основные механизмы других включений. Но если вы хотите указать, например, отдельные файлы для публикации вместе со своим приложением, для этого можно по-прежнему использовать привычные механизмы в *CSPROJ* (например, элемент `<Content>`).

### <a name="recommendation"></a>Рекомендация
При использовании CSPROJ рекомендуется удалить из проекта стандартные маски по умолчанию и добавить пути к файлам стандартных масок только для тех артефактов, которые нужны приложению или библиотеке в различных сценариях (среда выполнения, упаковка NuGet и т. д.).


## <a name="additions"></a>Добавления

### <a name="sdk-attribute"></a>Атрибут Sdk 
Элемент `<Project>` файла *CSPROJ* имеет новый атрибут `Sdk`. `Sdk` определяет, какой пакет SDK будет использоваться проектом. Пакет SDK, согласно описанию в [документе о слоях](cli-msbuild-architecture.md), является набором [задач](https://docs.microsoft.com/visualstudio/msbuild/msbuild-tasks) и [целевых объектов](https://docs.microsoft.com/visualstudio/msbuild/msbuild-targets) MSBuild, способным выполнять сборку кода .NET Core. Мы предоставляем два основных пакета SDK с инструментами для .NET Core:

1. пакет SDK для .NET Core с идентификатором `Microsoft.NET.Sdk`;
2. веб-пакет SDK для .NET Core с идентификатором `Microsoft.NET.Sdk.Web`.

Чтобы использовать инструменты и выполнять сборку кода .NET Core, в качестве значения атрибута `Sdk` в элементе `<Project>` нужно задать один из этих идентификаторов. 

### <a name="packagereference"></a>PackageReference
Элемент, определяющий зависимость NuGet в проекте. Атрибут `Include` указывает идентификатор пакета. 

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a>Версия
`Version` указывает версию пакета для восстановления. Этот элемент подчиняется правилам схемы управления версиями NuGet.

#### <a name="includeassets-excludeassets-and-privateassets"></a>IncludeAssets, ExcludeAssets и PrivateAssets
Атрибут `IncludeAssets` указывает, какие ресурсы пакета, указанные `<PackageReference>`, следует использовать. 

Атрибут `ExcludeAssets` указывает, какие ресурсы пакета, указанные `<PackageReference>`, не следует использовать.

Атрибут `PrivateAssets` указывает, какие ресурсы пакета, указанные `<PackageReference>`, следует использовать. Но они не должны передаваться в следующий проект. 

> [!NOTE]
> `PrivateAssets` эквивалентен элементу *project.json*/*xproj* `SuppressParent`.

Эти атрибуты могут содержать по меньшей мере один из перечисленных ниже элементов.

* `Compile` — содержимое папки lib доступно для компиляции.
* `Runtime` — содержимое папки среды выполнения распределяется.
* `ContentFiles` — используется содержимое папки *contentfiles*.
* `Build` — используются свойства и целевые объекты в папке сборки.
* `Native` — содержимое копируется из основных ресурсов в папку выходных данных среды выполнения.
* `Analyzers` — используются анализаторы.

Кроме того, атрибут может содержать следующие значения.

* `None` — не используется ни один ресурс.
* `All` — используются все ресурсы.

### <a name="dotnetclitoolreference"></a>DotNetCliToolReference
Элемент `<DotNetCliToolReference>` указывает средство интерфейса командной строки, которое пользователь хочет восстановить в контексте проекта. Этот элемент используется вместо узла `tools` в файле *project.json*. 

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

#### <a name="version"></a>Версия
`Version` указывает версию пакета для восстановления. Этот атрибут подчиняется правилам схемы управления версиями NuGet.

### <a name="runtimeidentifiers"></a>RuntimeIdentifiers
Элемент `<RuntimeIdentifiers>` позволяет указать для проекта список [идентификаторов среды выполнения ((RID)](../rid-catalog.md) (в качестве разделителя используется точка с запятой). Идентификаторы среды выполнения позволяют публиковать автономные развертывания. 

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```


### <a name="runtimeidentifier"></a>RuntimeIdentifier
Элемент `<RuntimeIdentifier>` позволяет указать для проекта только один [идентификатор среды выполнения](../rid-catalog.md). Идентификаторы среды выполнения позволяют опубликовать автономное развертывание. 

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```


### <a name="packagetargetfallback"></a>PackageTargetFallback 
Элемент `<PackageTargetFallback>` позволяет указать набор совместимых целевых объектов, которые следует использовать при восстановлении пакетов. Он разрешает пакетам, использующим dotnet [TxM (моникер целевой версии x)](https://docs.microsoft.com/nuget/schema/target-frameworks), взаимодействовать с пакетами, которые не объявляют dotnet TxM. Если в проекте используется dotnet TxM, все пакеты, от которых вы зависите, должны также содержать dotnet TxM. В противном случае нужно добавить `<PackageTargetFallback>` в проект, чтобы обеспечить совместимость с платформами, отличными от dotnet. 

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
При переходе к MSbuild мы переместили входные метаданные, которые использовались при упаковке пакета NuGet из *project.json* в файлы *CSPROJ*. Входными данными являются свойства MSBuild, поэтому они должны входить в группу `<PropertyGroup>`. Ниже представлен список свойств, которые используются как входные данные в процессе упаковки при использовании команды `dotnet pack` или целевого объекта `Pack` MSBuild, входящего в SDK. 

### <a name="ispackable"></a>IsPackable
Логическое значение, которое указывает, можно ли упаковать проект. Значение по умолчанию — `true`. 

### <a name="packageversion"></a>PackageVersion
Указывает версию, которую будет иметь итоговый пакет. Принимает все формы строки версии NuGet. По умолчанию используется значение `$(Version)`, то есть значение свойства `Version` в проекте. 

### <a name="packageid"></a>PackageId
Указывает имя для итогового пакета. Если значение не указано, операция `pack` по умолчанию использует в качестве имени пакета `AssemblyName` или имя каталога. 

### <a name="title"></a>Заголовок
Понятный заголовок пакета, обычно используемый при отображении пользовательского интерфейса, как на сайте nuget.org и в диспетчере пакетов Visual Studio. Если значение не указано, используется идентификатор пакета.

### <a name="authors"></a>Authors
Разделенный точками с запятой список авторов пакетов, совпадающих с именами профилей на сайте nuget.org. Они отображаются в коллекции NuGet на сайте nuget.org и используются для перекрестных ссылок на пакеты тех же авторов.

### <a name="description"></a>Описание
Подробное описание пакета для отображения пользовательского интерфейса.

### <a name="copyright"></a>Copyright
Сведения об авторских правах для пакета.

### <a name="packagerequirelicenseacceptance"></a>PackageRequireLicenseAcceptance
Логическое значение, указывающее, должен ли клиент просить потребителя принять условия лицензии перед установкой пакета. Значение по умолчанию — `false`.

### <a name="packagelicenseurl"></a>PackageLicenseUrl
URL-адрес лицензии, применимой к пакету.

### <a name="packageprojecturl"></a>PackageProjectUrl
URL-адрес для домашней страницы пакета, часто указываемый при отображении пользовательского интерфейса, также как и nuget.org.

### <a name="packageiconurl"></a>PackageIconUrl
URL-адрес для изображения размером 64x64 с прозрачным фоном, используемого в качестве значка для пакета при отображении пользовательского интерфейса.

### <a name="packagereleasenotes"></a>PackageReleaseNotes
Заметки о выпуске для пакета.

### <a name="packagetags"></a>PackageTags
Разделенный точками с запятой список тегов, обозначающий пакет.

### <a name="packageoutputpath"></a>PackageOutputPath
Определяет выходной путь для размещения упакованного пакета. Значение по умолчанию — `$(OutputPath)`. 

### <a name="includesymbols"></a>IncludeSymbols
Это логическое значение указывает, должен ли пакет создавать дополнительный пакет символов при упаковке проекта. Этот пакет будет иметь расширение *.symbols.nupkg* и копировать PDB-файлы, а также библиотеки DLL и другие выходные файлы.

### <a name="includesource"></a>IncludeSource
Это логическое значение указывает, должен ли процесс упаковки создавать исходный пакет. Исходный пакет содержит библиотеку исходного кода, а также файлы PDB. Исходные файлы помещаются в каталог `src/ProjectName` итогового файла пакета. 

### <a name="istool"></a>IsTool
Указывает, копируются ли все выходные файлы в папку *tools* вместо папки *lib*. Обратите внимание, что это свойство отличается от `DotNetCliTool`, которое указывается путем задания `PackageType` в файле *CSPROJ*.

### <a name="repositoryurl"></a>RepositoryUrl
Указывает URL-адрес репозитория, где находится исходный код для пакета или откуда выполняется его сборка. 

### <a name="repositorytype"></a>RepositoryType
Указывает тип репозитория. Значение по умолчанию — "git". 

### <a name="nopackageanalysis"></a>NoPackageAnalysis
Указывает, что пакету не нужно запускать анализ пакета после его сборки.

### <a name="minclientversion"></a>MinClientVersion
Указывает минимальную версию клиента NuGet, который может установить этот пакет с использованием nuget.exe и диспетчера пакетов Visual Studio.

### <a name="includebuildoutput"></a>IncludeBuildOutput
Это логическое значение указывает, следует ли упаковывать выходные сборки в файл *NUPKG*.

### <a name="includecontentinpack"></a>IncludeContentInPack
Это логическое значение указывает, будут ли все элементы, имеющие тип `Content`, автоматически включены в итоговый пакет. Значение по умолчанию — `true`. 

### <a name="buildoutputtargetfolder"></a>BuildOutputTargetFolder
Указывает папку для размещения выходных сборок. Выходные сборки (и другие выходные файлы) копируются в соответствующие папки платформы.

### <a name="contenttargetfolders"></a>ContentTargetFolders
Это свойство указывает расположение по умолчанию, куда следует помещать все файлы содержимого, для которых не указан `PackagePath`. Значение по умолчанию — "content;contentFiles".

### <a name="nuspecfile"></a>NuspecFile
Относительный или абсолютный путь к файлу *NUSPEC*, используемому для упаковки. 

> [!NOTE]
> Если файл *NUSPEC* указан, он используется для упаковки в **монопольном порядке**, а любые сведения в проектах не используются. 

### <a name="nuspecbasepath"></a>NuspecBasePath
Базовый путь для файла *NUSPEC*.

### <a name="nuspecproperties"></a>NuspecProperties
Список разделенных точками с запятой пар "ключ-значение".

