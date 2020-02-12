---
title: Дополнения к формату CSPROJ для .NET Core
description: Различия между существующими файлами и файлами CSPROJ .NET Core
ms.date: 04/08/2019
ms.openlocfilehash: 202c1867ae6404db074e6196b28ffe5f453ef5bf
ms.sourcegitcommit: feb42222f1430ca7b8115ae45e7a38fc4a1ba623
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2020
ms.locfileid: "76965611"
---
# <a name="additions-to-the-csproj-format-for-net-core"></a>Дополнения к формату CSPROJ для .NET Core

В этом документе перечислены изменения, внесенные в файлы проекта при перемещении из *project.json* в *CSPROJ* и [MSBuild](https://github.com/Microsoft/MSBuild). Дополнительную информацию, которая касается синтаксиса файла проекта в общем, и справку см. в документации по [файлу проекта MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference).

## <a name="implicit-package-references"></a>Неявные ссылки на пакет

Теперь неявные ссылки на метапакеты указываются в зависимости от целевой платформы, указанной в свойстве `<TargetFramework>` или `<TargetFrameworks>` файла проекта. Если свойство `<TargetFramework>` указано, свойство `<TargetFrameworks>` игнорируется независимо от порядка. Дополнительную информацию см. в статье [Пакеты, метапакеты и платформы](../packages.md).

```xml
 <PropertyGroup>
   <TargetFramework>netcoreapp2.1</TargetFramework>
 </PropertyGroup>
 ```

 ```xml
 <PropertyGroup>
   <TargetFrameworks>netcoreapp2.1;net462</TargetFrameworks>
 </PropertyGroup>
 ```

### <a name="recommendations"></a>Рекомендации

Так как теперь указываются неявные ссылки на метапакеты `Microsoft.NETCore.App` или `NETStandard.Library`, следует учитывать приведенные ниже рекомендации:

- Ориентируясь на .NET Core или .NET Standard, никогда не указывайте явную ссылку на метапакеты `Microsoft.NETCore.App` или `NETStandard.Library` через элемент `<PackageReference>` в файле проекта.
- Если при ориентации на .NET Core нужна определенная версия среды выполнения, вместо ссылки на метапакет следует использовать свойство `<RuntimeFrameworkVersion>` в проекте (например, `1.0.4`).
  - Это может произойти, например, когда вы используете [автономные развертывания](../deploying/index.md#self-contained-deployments-scd) и нуждаетесь в определенной версии исправления 1.0.0 LTS для среды выполнения.
- Если при ориентации на .NET Standard вам нужна конкретная версия метапакета `NETStandard.Library`, можно использовать свойство `<NetStandardImplicitPackageVersion>` и установить требуемую версию.
- Не добавляйте и не обновляйте ссылки на метапакет `Microsoft.NETCore.App` или `NETStandard.Library` явным образом в проектах .NET Framework. Если при использовании пакета NuGet на основе .NET Standard требуется любая версия `NETStandard.Library`, NuGet автоматически устанавливает ее.

## <a name="implicit-version-for-some-package-references"></a>Неявное указание версий для некоторых ссылок на пакет

В большинстве случаев при использовании [`<PackageReference>`](#packagereference) требуется указать атрибут `Version`, чтобы определить используемую версию пакета NuGet. Атрибут необязательно указывать, если используется .NET Core 2.1 или 2.2 со ссылкой на [Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage-app) или [Microsoft.AspNetCore.All](/aspnet/core/fundamentals/metapackage). Пакет SDK для .NET Core позволяет автоматически выбрать версию этих пакетов, которая должна использоваться.

### <a name="recommendation"></a>Рекомендация

Если вы ссылаетесь на пакеты `Microsoft.AspNetCore.App` или `Microsoft.AspNetCore.All`, не указывайте их версии. Если версия указана, пакет SDK может выдать предупреждение NETSDK1071. Чтобы устранить это предупреждение, удалите версию пакета, как показано в следующем примере:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.AspNetCore.App" />
</ItemGroup>
```

> Известная проблема. Пакет SDK для .NET Core 2.1 поддерживал только такой синтаксис, если в проекте также использовался Microsoft.NET.Sdk.Web. Эта проблема устранена в пакете SDK для .NET Core 2.2.

Эти ссылки на метапакеты ASP.NET Core немного отличаются от ссылок на обычные пакеты NuGet. [Зависящие от платформы развертывания](../deploying/index.md#framework-dependent-deployments-fdd) приложений, для которых используются эти метапакеты, автоматически получают все преимущества общей платформы ASP.NET Core. Если используются метапакеты, с приложением **не** развертываются ресурсы из указанных по ссылке пакетов NuGet ASP.NET Core — общая платформа ASP.NET Core уже содержит эти ресурсы. Для ускорения запуска приложения ресурсы в общей платформе предварительно оптимизируются. Дополнительные сведения об общей платформе см. в статье [Упаковка дистрибутивов .NET Core](../distribution-packaging.md).

Если версия *указана*, она рассматривается как *минимальная* версия общей платформы ASP.NET Core для зависимых от платформы развертываний, а также как *точная* версия для автономных развертываний. Это может привести к следующим результатам:

- Если на сервере установлена более ранняя версия ASP.NET Core, чем указанная в PackageReference, процесс .NET Core не удастся запустить. Обновления метапакета часто доступны на сайте NuGet.org раньше, чем в средах размещения, таких как Azure. Обновление версии PackageReference в ASP.NET Core может привести к сбою развернутого приложения.
- Если приложение развертывается как [автономное развертывание](../deploying/index.md#self-contained-deployments-scd), оно не может содержать последние обновления системы безопасности для .NET Core. Если версия не указана, пакет SDK может автоматически включить последнюю версию ASP.NET Core в автономное развертывание.

## <a name="default-compilation-includes-in-net-core-projects"></a>Компиляция по умолчанию, включенная в проекты .NET Core

В рамках перехода на формат *CSPROJ* в последних версиях пакета SDK мы перенесли включения и исключения по умолчанию для элементов Compile и внедренные ресурсы в файлы свойств пакета SDK. Это означает, что вам больше не нужно указывать эти элементы в файле проекта.

Основной причиной этого является стремление очистить ваш файл проекта от всего лишнего. Значения по умолчанию в пакете SDK должны охватывать наиболее распространенные варианты использования, поэтому нет необходимости повторять их в каждом создаваемом проекте. Это позволяет уменьшить файлы проекта и гораздо проще читать их, а также вносить правки вручную.

Следующая таблица показывает, какой элемент и какие [стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) включены и исключены в пакете SDK:

| Элемент           | Стандартная маска включения                              | Стандартная маска исключения                                                  | Стандартная маска удаления              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| Компилятор           | \*\*/\*.cs (или другие расширения языка) | \*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc  | Н/Д                      |
| ВнедренныйРесурс  | \*\*/\*.resx                              | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | Н/Д                      |
| Отсутствуют              | \*\*/\*                                   | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | \*\*/\*.cs; \*\*/\*.resx   |

> [!NOTE]
> **Стандартная маска исключения** всегда исключает папки `./bin` и `./obj`, которые представлены свойствами MSBuild `$(BaseOutputPath)` и `$(BaseIntermediateOutputPath)` соответственно. В целом все исключения представляются свойством `$(DefaultItemExcludes)`.

Если в вашем проекте имеются стандартные маски и вы пытаетесь выполнить его сборку с помощью новейшего пакета SDK, появится следующая ошибка:

> Duplicate Compile items were included. The .NET SDK includes Compile items from your project directory by default. You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file. (Включены повторяющиеся элементы Compile. По умолчанию пакет SDK для .NET включает элементы Compile из каталога проекта. Можно удалить эти элементы из файла проекта или задать для свойства "EnableDefaultCompileItems" значение "false", чтобы явно включить их в файл проекта.)

Чтобы обойти эту ошибку, можно либо удалить явные элементы `Compile`, которые соответствуют указанным в предыдущей таблице, либо установить для свойства `<EnableDefaultCompileItems>` значение `false`, как показано ниже:

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

Указание значения `false` для этого свойства отключает неявное включение, в результате чего возвращается поведение для предыдущих пакетов SDK, где требовалось задавать стандартные маски по умолчанию в проекте.

Это изменение не затрагивает основные механизмы других включений. Но если вы хотите указать, например, отдельные файлы для публикации вместе со своим приложением, для этого можно по-прежнему использовать привычные механизмы в *CSPROJ* (например, элемент `<Content>`).

`<EnableDefaultCompileItems>` отключает только стандартные маски `Compile`, не затрагивая все остальные, например неявную стандартную маску `None`, которая также применяется к элементам \*.cs. Из-за этого **обозреватель решений** продолжит показывать элементы \*.cs как часть проекта, включенную в виде элементов `None`. Аналогичным образом, можно задать `<EnableDefaultNoneItems>` как false для отключения неявной стандартной маски `None`:

```xml
<PropertyGroup>
    <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

Чтобы отключить **все неявные стандартные маски**, можно задать для свойства `<EnableDefaultItems>` значение `false`, как в следующем примере:

```xml
<PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a>Как просмотреть весь проект в представлении MSBuild

Хотя эти изменения csproj значительно упростили файлы проекта, возможно, вы захотите просмотреть полностью развернутый пакет в представлении MSBuild после включения пакета SDK и его целевых объектов. Выполните предварительную обработку проекта, [включив](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) в команду [`dotnet msbuild`](dotnet-msbuild.md) параметр `/pp`. Это позволит просмотреть сведения об импортированных файлах, их источниках, вкладе в сборку без фактического создания проекта:

`dotnet msbuild -pp:fullproject.xml`

Если проект имеет несколько требуемых версий .NET Framework, результаты выполнения команды должны касаться только одной из них. Эту версию следует указать в качестве свойства MSBuild:

`dotnet msbuild -p:TargetFramework=netcoreapp2.0 -pp:fullproject.xml`

## <a name="additions"></a>Добавления

### <a name="sdk-attribute"></a>Атрибут Sdk

Корневой элемент `<Project>` файла *CSPROJ* имеет новый атрибут `Sdk`. `Sdk` определяет, какой пакет SDK будет использоваться проектом. Пакет SDK, согласно описанию в [документе о слоях](cli-msbuild-architecture.md), является набором [задач](/visualstudio/msbuild/msbuild-tasks) и [целевых объектов](/visualstudio/msbuild/msbuild-targets) MSBuild, способным выполнять сборку кода .NET Core. Для .NET Core доступны следующие пакеты SDK:

1. пакет SDK для .NET Core с идентификатором `Microsoft.NET.Sdk`;
2. веб-пакет SDK для .NET Core с идентификатором `Microsoft.NET.Sdk.Web`.
3. пакет SDK для библиотеки классов Razor для .NET Core с идентификатором `Microsoft.NET.Sdk.Razor`.
4. Служба рабочей роли .NET Core с идентификатором `Microsoft.NET.Sdk.Worker` (с версии .NET Core 3.0)
5. .NET Core WinForms и WPF с идентификатором `Microsoft.NET.Sdk.WindowsDesktop` (с версии .NET Core 3.0)

Чтобы использовать инструменты и выполнять сборку кода .NET Core, в качестве значения атрибута `Sdk` в элементе `<Project>` нужно задать один из этих идентификаторов.

### <a name="packagereference"></a>PackageReference

Элемент `<PackageReference>` указывает [зависимость NuGet в проекте](/nuget/consume-packages/package-references-in-project-files). Атрибут `Include` указывает идентификатор пакета.

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a>Version

Обязательный атрибут `Version` указывает версию пакета для восстановления. Этот атрибут подчиняется правилам схемы [управления версиями NuGet](/nuget/reference/package-versioning#version-ranges-and-wildcards). По умолчанию выбирается минимальная из заданных версий (включительно). Например, если указать `Version="1.2.3"`, это будет эквивалентно нотации NuGet `[1.2.3, )` и означает, что при разрешении пакет будет иметь версию 1.2.3, если она доступна, или более высокую, если нет.

#### <a name="includeassets-excludeassets-and-privateassets"></a>IncludeAssets, ExcludeAssets и PrivateAssets

Атрибут `IncludeAssets` указывает, какие ресурсы пакета, указанные `<PackageReference>`, следует использовать. По умолчанию включаются все ресурсы пакета.

Атрибут `ExcludeAssets` указывает, какие ресурсы пакета, указанные `<PackageReference>`, не следует использовать.

Атрибут `PrivateAssets` указывает, какие ресурсы пакета, указанные `<PackageReference>`, следует использовать, но не следует передавать в следующий проект. Если этот атрибут отсутствует, ресурсы `Analyzers`, `Build` и `ContentFiles` по умолчанию являются частными.

> [!NOTE]
> `PrivateAssets` эквивалентен элементу *project.json*/*xproj* `SuppressParent`.

Эти атрибуты могут содержать один или несколько следующих элементов (если их больше одного, они разделяются точкой с запятой `;`):

- `Compile` — содержимое папки *lib* доступно для компиляции.
- `Runtime` — содержимое папки *runtime* распределяется.
- `ContentFiles` — используется содержимое папки *contentfiles*.
- `Build` — используются свойства и целевые объекты в папке *build*.
- `Native` — содержимое копируется из основных ресурсов в папку *output* среды выполнения.
- `Analyzers` — используются анализаторы.

Кроме того, атрибут может содержать следующие значения.

- `None` — не используется ни один ресурс.
- `All` — используются все ресурсы.

### <a name="dotnetclitoolreference"></a>DotNetCliToolReference

Элемент `<DotNetCliToolReference>` указывает средство интерфейса командной строки, которое пользователь хочет восстановить в контексте проекта. Этот элемент используется вместо узла `tools` в файле *project.json*.

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

Обратите внимание, что `DotNetCliToolReference` [теперь считается нерекомендуемый](https://github.com/dotnet/announcements/issues/107). Вместо него используйте [локальные средства .NET Core](https://aka.ms/local-tools).

#### <a name="version"></a>Version

`Version` указывает версию пакета для восстановления. Этот атрибут подчиняется правилам схемы [управления версиями NuGet](/nuget/create-packages/dependency-versions#version-ranges). По умолчанию выбирается минимальная из заданных версий (включительно). Например, если указать `Version="1.2.3"`, это будет эквивалентно нотации NuGet `[1.2.3, )` и означает, что при разрешении пакет будет иметь версию 1.2.3, если она доступна, или более высокую, если нет.

### <a name="runtimeidentifiers"></a>RuntimeIdentifiers

Элемент свойства `<RuntimeIdentifiers>` позволяет указать для проекта список [идентификаторов среды выполнения (RID)](../rid-catalog.md) (в качестве разделителя используется точка с запятой).
Идентификаторы позволяют публиковать автономные развертывания.

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a>RuntimeIdentifier

Элемент свойства `<RuntimeIdentifier>` позволяет указать для проекта только один [идентификатор среды выполнения](../rid-catalog.md). Идентификатор среды выполнения позволяет опубликовать автономное развертывание.

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

Используйте `<RuntimeIdentifiers>` (во множественном числе) вместо этого, если вам нужна публикация для различных сред. `<RuntimeIdentifier>` может ускорить создание сборок, когда требуется только одна среда выполнения.

### <a name="packagetargetfallback"></a>PackageTargetFallback

Элемент свойства `<PackageTargetFallback>` позволяет указать набор совместимых целевых объектов, которые следует использовать при восстановлении пакетов. Он разрешает пакетам, использующим dotnet [TxM (моникер целевой версии x)](/nuget/schema/target-frameworks), взаимодействовать с пакетами, которые не объявляют dotnet TxM. Если в проекте используется dotnet TxM, все пакеты, от которых вы зависите, должны также содержать dotnet TxM. В противном случае нужно добавить `<PackageTargetFallback>` в проект, чтобы обеспечить совместимость с платформами, отличными от dotnet.

В следующем примере приводятся резервные варианты для всех целевых объектов в проекте:

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

В следующем примере приводятся резервные варианты только для целевого объекта `netcoreapp2.1`:

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp2.1'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="build-events"></a>События сборки

Способ, которым события перед сборкой и после сборки указываются в файле проекта, изменился. Свойства PreBuildEvent и PostBuildEvent не рекомендуется использовать в проектах с форматом в стиле пакета SDK из-за того, что такие макросы, как $(ProjectDir), не будут разрешаться. Например, следующий код больше не поддерживается:

```xml
<PropertyGroup>
    <PreBuildEvent>"$(ProjectDir)PreBuildEvent.bat" "$(ProjectDir)..\" "$(ProjectDir)" "$(TargetDir)" />
</PropertyGroup>
```

Для проектов в стиле пакета SDK используйте целевой объект MSBuild с именем `PreBuild` или `PostBuild` и задайте свойство `BeforeTargets` для `PreBuild` или свойство `AfterTargets` для `PostBuild`. В предыдущем примере используйте такой код:

```xml
<Target Name="PreBuild" BeforeTargets="PreBuildEvent">
    <Exec Command="&quot;$(ProjectDir)PreBuildEvent.bat&quot; &quot;$(ProjectDir)..\&quot; &quot;$(ProjectDir)&quot; &quot;$(TargetDir)&quot;" />
</Target>

<Target Name="PostBuild" AfterTargets="PostBuildEvent">
   <Exec Command="echo Output written to $(TargetDir)" />
</Target>
```

> [!NOTE]
>Для целевых объектов MSBuild можно использовать любое имя, но интегрированная среда разработки Visual Studio распознает целевые объекты `PreBuild` и `PostBuild`, поэтому мы рекомендуем использовать эти имена, чтобы можно было изменять команды в интегрированной среде разработки Visual Studio.

## <a name="nuget-metadata-properties"></a>Свойства метаданных NuGet

При переходе к MSBuild мы переместили входные метаданные, которые использовались при упаковке пакета NuGet из *project.json* в файлы *CSPROJ*. Входными данными являются свойства MSBuild, поэтому они должны входить в группу `<PropertyGroup>`. Ниже представлен список свойств, которые используются как входные данные в процессе упаковки при использовании команды `dotnet pack` или целевого объекта `Pack` MSBuild, входящего в SDK:

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

### <a name="packagedescription"></a>PackageDescription

Подробное описание пакета для отображения пользовательского интерфейса.

### <a name="description"></a>Описание

Подробное описание сборки. Если `PackageDescription` не указывать, это свойство также будет использоваться в качестве описания пакета.

### <a name="copyright"></a>Copyright

Сведения об авторских правах для пакета.

### <a name="packagerequirelicenseacceptance"></a>PackageRequireLicenseAcceptance

Логическое значение, указывающее, должен ли клиент просить потребителя принять условия лицензии перед установкой пакета. Значение по умолчанию — `false`.

### <a name="packagelicenseexpression"></a>PackageLicenseExpression

[Идентификатор лицензии SPDX](https://spdx.org/licenses/) или выражение. Например, `Apache-2.0`.

Здесь приведен полный список [идентификаторов лицензии SPDX](https://spdx.org/licenses/). Если используется выражение типа лицензии, NuGet.org принимает только утвержденные OSI или FSF лицензии.

Точный синтаксис выражений лицензии описан ниже в спецификации метаязыка [ABNF](https://tools.ietf.org/html/rfc5234).

```abnf
license-id            = <short form license identifier from https://spdx.org/spdx-specification-21-web-version#h.luq9dgcle9mo>

license-exception-id  = <short form license exception identifier from https://spdx.org/spdx-specification-21-web-version#h.ruv3yl8g6czd>

simple-expression = license-id / license-id”+”

compound-expression =  1*1(simple-expression /
                simple-expression "WITH" license-exception-id /
                compound-expression "AND" compound-expression /
                compound-expression "OR" compound-expression ) /
                "(" compound-expression ")" )

license-expression =  1*1(simple-expression / compound-expression / UNLICENSED)
```

> [!NOTE]
> За один раз можно указать только одно из свойств `PackageLicenseExpression`, `PackageLicenseFile` и `PackageLicenseUrl`.

### <a name="packagelicensefile"></a>PackageLicenseFile

Путь к файлу лицензии в пакете, если вы используете лицензию, которой не назначен идентификатор SPDX, или пользовательскую лицензию (в противном случае предпочтительнее использовать свойство `PackageLicenseExpression`).

Заменяет свойство `PackageLicenseUrl`, не может сочетаться со свойством `PackageLicenseExpression`. Требуется Visual Studio версии 15.9.4 и пакет SDK для .NET 2.1.502, 2.2.101 и выше.

Вам необходимо убедиться, что файл лицензии упакован. Для этого явно добавьте его в проект. Пример использования:

```xml
<PropertyGroup>
  <PackageLicenseFile>LICENSE.txt</PackageLicenseFile>
</PropertyGroup>
<ItemGroup>
  <None Include="licenses\LICENSE.txt" Pack="true" PackagePath="$(PackageLicenseFile)"/>
</ItemGroup>
```

### <a name="packagelicenseurl"></a>PackageLicenseUrl

URL-адрес лицензии, применимой к пакету. (_Отмечено как нерекомендуемое начиная с Visual Studio версии 15.9.4, пакета SDK для .NET 2.1.502 и 2.2.101._ )

### <a name="packageiconurl"></a>PackageIconUrl

URL-адрес для изображения размером 64x64 с прозрачным фоном, используемого в качестве значка для пакета при отображении пользовательского интерфейса.

### <a name="packagereleasenotes"></a>PackageReleaseNotes

Заметки о выпуске для пакета.

### <a name="packagetags"></a>PackageTags

Разделенный точками с запятой список тегов, обозначающий пакет.

### <a name="packageoutputpath"></a>PackageOutputPath

Определяет выходной путь для размещения упакованного пакета. Значение по умолчанию — `$(OutputPath)`.

### <a name="includesymbols"></a>IncludeSymbols
Это логическое значение указывает, должен ли пакет создавать дополнительный пакет символов при упаковке проекта. Форматом пакета символов управляет свойство `SymbolPackageFormat`.

### <a name="symbolpackageformat"></a>SymbolPackageFormat
Задает формат пакета символов. Если задано symbols.nupkg, создается пакет символов в старом формате с расширением *. symbols.nupkg*, содержащий PDB-файлы, библиотеки DLL и другие выходные файлы. Если задано snupkg, создается пакет символов snupkg, содержащий переносимые PDB-файлы. По умолчанию задано symbols.nupkg.

### <a name="includesource"></a>IncludeSource

Это логическое значение указывает, должен ли процесс упаковки создавать исходный пакет. Исходный пакет содержит библиотеку исходного кода, а также файлы PDB. Исходные файлы помещаются в каталог `src/ProjectName` итогового файла пакета.

### <a name="istool"></a>IsTool

Указывает, копируются ли все выходные файлы в папку *tools* вместо папки *lib*. Это свойство отличается от `DotNetCliTool`, которое указывается путем задания `PackageType` в файле *CSPROJ*.

### <a name="repositoryurl"></a>RepositoryUrl

Указывает URL-адрес репозитория, где находится исходный код для пакета или откуда выполняется его сборка.

### <a name="repositorytype"></a>RepositoryType

Указывает тип репозитория. Значение по умолчанию — "git".

### <a name="repositorybranch"></a>RepositoryBranch
Указывает имя исходной ветки в репозитории. Если проект упакован в пакет NuGet, он добавляется в метаданные пакета.

### <a name="repositorycommit"></a>RepositoryCommit
Необязательная фиксация или набор изменений репозитория для указания источника, на основе которого был создан пакет. Необходимо также указать `RepositoryUrl`, чтобы включить это свойство. Если проект упакован в пакет NuGet, эта фиксация или набор изменений добавляются в метаданные пакета.

### <a name="nopackageanalysis"></a>NoPackageAnalysis

Указывает, что пакету не нужно запускать анализ пакета после его сборки.

### <a name="minclientversion"></a>MinClientVersion

Указывает минимальную версию клиента NuGet, который может установить этот пакет с использованием nuget.exe и диспетчера пакетов Visual Studio.

### <a name="includebuildoutput"></a>IncludeBuildOutput

Это логическое значение указывает, следует ли упаковывать выходные сборки в файл *NUPKG*.

### <a name="includecontentinpack"></a>IncludeContentInPack

Это логическое значение указывает, будут ли все элементы, имеющие тип `Content`, автоматически включены в итоговый пакет. Значение по умолчанию — `true`.

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

## <a name="assemblyinfo-properties"></a>Свойства AssemblyInfo

[Атрибуты сборки](../../standard/assembly/set-attributes.md), которые обычно содержатся в файле *AssemblyInfo*, теперь автоматически создаются на основе свойств.

### <a name="properties-per-attribute"></a>Свойства каждого атрибута

Как показано в следующей таблице, каждый атрибут имеет два свойства: одно управляет содержимым атрибута, а второе отключает его создание.

| Атрибут                                                      | Свойство.               | Свойство, используемое для отключения                             |
|----------------------------------------------------------------|------------------------|-------------------------------------------------|
| <xref:System.Reflection.AssemblyCompanyAttribute>              | `Company`              | `GenerateAssemblyCompanyAttribute`              |
| <xref:System.Reflection.AssemblyConfigurationAttribute>        | `Configuration`        | `GenerateAssemblyConfigurationAttribute`        |
| <xref:System.Reflection.AssemblyCopyrightAttribute>            | `Copyright`            | `GenerateAssemblyCopyrightAttribute`            |
| <xref:System.Reflection.AssemblyDescriptionAttribute>          | `Description`          | `GenerateAssemblyDescriptionAttribute`          |
| <xref:System.Reflection.AssemblyFileVersionAttribute>          | `FileVersion`          | `GenerateAssemblyFileVersionAttribute`          |
| <xref:System.Reflection.AssemblyInformationalVersionAttribute> | `InformationalVersion` | `GenerateAssemblyInformationalVersionAttribute` |
| <xref:System.Reflection.AssemblyProductAttribute>              | `Product`              | `GenerateAssemblyProductAttribute`              |
| <xref:System.Reflection.AssemblyTitleAttribute>                | `AssemblyTitle`        | `GenerateAssemblyTitleAttribute`                |
| <xref:System.Reflection.AssemblyVersionAttribute>              | `AssemblyVersion`      | `GenerateAssemblyVersionAttribute`              |
| <xref:System.Resources.NeutralResourcesLanguageAttribute>      | `NeutralLanguage`      | `GenerateNeutralResourcesLanguageAttribute`     |

Примечания.

- `AssemblyVersion` и `FileVersion` по умолчанию имеют значение `$(Version)` без суффикса. Например, если для `$(Version)` нужно указать `1.2.3-beta.4`, то значением будет `1.2.3`.
- По умолчанию для `InformationalVersion` используется значение `$(Version)`.
- `InformationalVersion` имеет значение `$(SourceRevisionId)`, которое добавляется, если указано свойство. Его можно отключить с помощью `IncludeSourceRevisionInInformationalVersion`.
- Свойства `Copyright` и `Description` также используются для метаданных NuGet.
- Свойство `Configuration` является общим для всего процесса сборки, и задается с помощью параметра `--configuration` команд `dotnet`.

### <a name="generateassemblyinfo"></a>GenerateAssemblyInfo

Логическое свойство, которое позволяет включить или отключить создание всех свойств AssemblyInfo. Значение по умолчанию — `true`.

### <a name="generatedassemblyinfofile"></a>GeneratedAssemblyInfoFile

Путь к файлу сведений о созданной сборке. По умолчанию это путь к файлу в каталоге объектов `$(IntermediateOutputPath)`.
