---
title: Сравнение project.json и CSPROJ
description: См. сопоставление между элементами project.json и CSPROJ.
author: natemcmaster
ms.date: 03/13/2017
ms.openlocfilehash: c31590cf34990867b81af4d073846c2952928798
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714133"
---
# <a name="a-mapping-between-projectjson-and-csproj-properties"></a>Сопоставление между свойствами project.json и CSPROJ

Автор: [Nate McMaster](https://github.com/natemcmaster) (Нейт Макмастер)

При разработке инструментария .NET Core были внесены важные структурные изменения, направленные на прекращение поддержки файлов *project.json* и перенос проектов .NET Core на формат MSBuild/CSPROJ.

Эта статья показывает, как параметры из *project.json* представлены в формате MSBuild/CSPROJ. Это поможет вам научиться использовать новый формат и узнать об изменениях, вносимых средствами миграции при обновлении проекта до последней версии инструментария.

## <a name="the-csproj-format"></a>Формат CSPROJ

Новый формат \*.csproj основан на XML. В следующем примере показан корневой узел проекта .NET Core с использованием `Microsoft.NET.Sdk`. Для веб-проектов используется пакет SDK `Microsoft.NET.Sdk.Web`.

```xml
<Project Sdk="Microsoft.NET.Sdk">
...
</Project>
```

## <a name="common-top-level-properties"></a>Общие свойства верхнего уровня

### <a name="name"></a>name

```json
{
  "name": "MyProjectName"
}
```

Больше не поддерживается. В CSPROJ-файле это свойство определяется именем файла проекта, которое обычно соответствует имени каталога. Например, `MyProjectName.csproj`.

По умолчанию имя файла проекта также определяет значение свойств `<AssemblyName>` и `<PackageId>`.

```xml
<PropertyGroup>
  <AssemblyName>MyProjectName</AssemblyName>
  <PackageId>MyProjectName</PackageId>
</PropertyGroup>
```

Значение `<AssemblyName>` будет отличаться от значения `<PackageId>`, если свойство `buildOptions\outputName` было определено в project.json.
Дополнительные сведения см. в разделе [Другие общие параметры сборки](#other-common-build-options).

### <a name="version"></a>version

```json
{
  "version": "1.0.0-alpha-*"
}
```

Используйте свойства `VersionPrefix` и `VersionSuffix`:

```xml
<PropertyGroup>
  <VersionPrefix>1.0.0</VersionPrefix>
  <VersionSuffix>alpha</VersionSuffix>
</PropertyGroup>
```

Можно также использовать свойство `Version`, но это может переопределить параметры версии во время упаковки:

```xml
<PropertyGroup>
  <Version>1.0.0-alpha</Version>
</PropertyGroup>
```

### <a name="other-common-root-level-options"></a>Другие общие параметры корневого уровня

```json
{
  "authors": [ "Anne", "Bob" ],
  "company": "Contoso",
  "language": "en-US",
  "title": "My library",
  "description": "This is my library.\r\nAnd it's really great!",
  "copyright": "Nugetizer 3000",
  "userSecretsId": "xyz123"
}
```

```xml
<PropertyGroup>
  <Authors>Anne;Bob</Authors>
  <Company>Contoso</Company>
  <NeutralLanguage>en-US</NeutralLanguage>
  <AssemblyTitle>My library</AssemblyTitle>
  <Description>This is my library.
And it's really great!</Description>
  <Copyright>Nugetizer 3000</Copyright>
  <UserSecretsId>xyz123</UserSecretsId>
</PropertyGroup>
```

## <a name="frameworks"></a>Инфраструктуры

### <a name="one-target-framework"></a>Одна целевая платформа

```json
{
  "frameworks": {
    "netcoreapp1.0": {}
  }
}
```

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp1.0</TargetFramework>
</PropertyGroup>
```

### <a name="multiple-target-frameworks"></a>Несколько целевых платформ

```json
{
  "frameworks": {
    "netcoreapp1.0": {},
    "net451": {}
  }
}
```

Используйте свойство `TargetFrameworks`, чтобы определить список целевых платформ. Для разделения нескольких значений платформы используйте точку с запятой.

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp1.0;net451</TargetFrameworks>
</PropertyGroup>
```

## <a name="dependencies"></a>зависимости

> [!IMPORTANT]
> Если зависимостью является **проект**, а не пакет, то формат будет отличаться.
> Дополнительные сведения см. в разделе [Тип dependency](#dependency-type).

### <a name="netstandardlibrary-metapackage"></a>Метапакет NETStandard.Library

```json
{
  "dependencies": {
    "NETStandard.Library": "1.6.0"
  }
}
```

```xml
<PropertyGroup>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

### <a name="microsoftnetcoreapp-metapackage"></a>Метапакет Microsoft.NETCore.App

```json
{
  "dependencies": {
    "Microsoft.NETCore.App": "1.0.0"
  }
}
```

```xml
<PropertyGroup>
  <RuntimeFrameworkVersion>1.0.3</RuntimeFrameworkVersion>
</PropertyGroup>
```

Обратите внимание, что значение `<RuntimeFrameworkVersion>` в перенесенном проекте определяется версией установленного пакета SDK.

### <a name="top-level-dependencies"></a>Высокоуровневые зависимости

```json
{
  "dependencies": {
    "Microsoft.AspNetCore": "1.1.0"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.AspNetCore" Version="1.1.0" />
</ItemGroup>
```

### <a name="per-framework-dependencies"></a>Зависимости отдельных платформ

```json
{
  "framework": {
    "net451": {
      "dependencies": {
        "System.Collections.Immutable": "1.3.1"
      }
    },
    "netstandard1.5": {
      "dependencies": {
        "Newtonsoft.Json": "9.0.1"
      }
    }
  }
}
```

```xml
<ItemGroup Condition="'$(TargetFramework)'=='net451'">
  <PackageReference Include="System.Collections.Immutable" Version="1.3.1" />
</ItemGroup>

<ItemGroup Condition="'$(TargetFramework)'=='netstandard1.5'">
  <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
</ItemGroup>
```

### <a name="imports"></a>импорт

```json
{
  "dependencies": {
    "YamlDotNet": "4.0.1-pre309"
  },
  "frameworks": {
    "netcoreapp1.0": {
      "imports": [
        "dnxcore50",
        "dotnet"
      ]
    }
  }
}
```

```xml
<PropertyGroup>
  <PackageTargetFallback>dnxcore50;dotnet</PackageTargetFallback>
</PropertyGroup>
<ItemGroup>
  <PackageReference Include="YamlDotNet" Version="4.0.1-pre309" />
</ItemGroup>
```

### <a name="dependency-type"></a>Тип dependency

#### <a name="type-project"></a>type: project

```json
{
  "dependencies": {
    "MyOtherProject": "1.0.0-*",
    "AnotherProject": {
      "type": "project"
    }
  }
}
```

```xml
<ItemGroup>
  <ProjectReference Include="..\MyOtherProject\MyOtherProject.csproj" />
  <ProjectReference Include="..\AnotherProject\AnotherProject.csproj" />
</ItemGroup>
```

> [!NOTE]
> Нарушает процедуру, по которой `dotnet pack --version-suffix $suffix` определяет версию зависимости для ссылки на проект.

#### <a name="type-build"></a>type: build

```json
{
  "dependencies": {
    "Microsoft.EntityFrameworkCore.Design": {
      "version": "1.1.0",
      "type": "build"
    }
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.EntityFrameworkCore.Design" Version="1.1.0" PrivateAssets="All" />
</ItemGroup>
```

#### <a name="type-platform"></a>type: platform

```json
{
  "dependencies": {
    "Microsoft.NETCore.App": {
      "version": "1.1.0",
      "type": "platform"
    }
  }
}
```

Не имеет эквивалента в CSPROJ.

## <a name="runtimes"></a>runtimes

```json
{
  "runtimes": {
    "win7-x64": {},
    "osx.10.11-x64": {},
    "ubuntu.16.04-x64": {}
  }
}
```

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win7-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="standalone-apps-self-contained-deployment"></a>Автономные приложения (автономное развертывание)

В project.json определение раздела `runtimes` означает, что приложение было автономным во время сборки и публикации.
В MSBuild все проекты являются *портативными* во время сборки, но могут быть опубликованы как автономные.

`dotnet publish --framework netcoreapp1.0 --runtime osx.10.11-x64`

Дополнительные сведения см. в статье [Автономные развертывания (SCD)](../deploying/index.md#self-contained-deployments-scd).

## <a name="tools"></a>средства

```json
{
  "tools": {
    "Microsoft.EntityFrameworkCore.Tools.DotNet": "1.0.0-*"
  }
}
```

```xml
<ItemGroup>
  <DotNetCliToolReference Include="Microsoft.EntityFrameworkCore.Tools.DotNet" Version="1.0.0" />
</ItemGroup>
```

> [!NOTE]
> `imports` для tools не поддерживаются в CSPROJ. Tools, которым требуются imports, не будут работать с новым `Microsoft.NET.Sdk`.

## <a name="buildoptions"></a>buildOptions

См. также раздел [Файлы](#files).

### <a name="emitentrypoint"></a>emitEntryPoint

```json
{
  "buildOptions": {
    "emitEntryPoint": true
  }
}
```

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

Если `emitEntryPoint` имело значение `false`, значение `OutputType` преобразуется в `Library`, которое используется по умолчанию:

```json
{
  "buildOptions": {
    "emitEntryPoint": false
  }
}
```

```xml
<PropertyGroup>
  <OutputType>Library</OutputType>
  <!-- or, omit altogether. It defaults to 'Library' -->
</PropertyGroup>
```

### <a name="keyfile"></a>keyFile

```json
{
  "buildOptions": {
    "keyFile": "MyKey.snk"
  }
}
```

Элемент `keyFile` развертывается в три свойства в MSBuild:

```xml
<PropertyGroup>
  <AssemblyOriginatorKeyFile>MyKey.snk</AssemblyOriginatorKeyFile>
  <SignAssembly>true</SignAssembly>
  <PublicSign Condition="'$(OS)' != 'Windows_NT'">true</PublicSign>
</PropertyGroup>
```

### <a name="other-common-build-options"></a>Другие общие параметры сборки

```json
{
  "buildOptions": {
    "warningsAsErrors": true,
    "nowarn": ["CS0168", "CS0219"],
    "xmlDoc": true,
    "preserveCompilationContext": true,
    "outputName": "Different.AssemblyName",
    "debugType": "portable",
    "allowUnsafe": true,
    "define": ["TEST", "OTHERCONDITION"]
  }
}
```

```xml
<PropertyGroup>
  <TreatWarningsAsErrors>true</TreatWarningsAsErrors>
  <NoWarn>$(NoWarn);CS0168;CS0219</NoWarn>
  <GenerateDocumentationFile>true</GenerateDocumentationFile>
  <PreserveCompilationContext>true</PreserveCompilationContext>
  <AssemblyName>Different.AssemblyName</AssemblyName>
  <DebugType>portable</DebugType>
  <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  <DefineConstants>$(DefineConstants);TEST;OTHERCONDITION</DefineConstants>
</PropertyGroup>
```

## <a name="packoptions"></a>packOptions

См. также раздел [Файлы](#files).

### <a name="common-pack-options"></a>Общие параметры пакета

```json
{
  "packOptions": {
    "summary": "numl is a machine learning library intended to ease the use of using standard modeling techniques for both prediction and clustering.",
    "tags": ["machine learning", "framework"],
    "releaseNotes": "Version 0.9.12-beta",
    "iconUrl": "http://numl.net/images/ico.png",
    "projectUrl": "http://numl.net",
    "licenseUrl": "https://raw.githubusercontent.com/sethjuarez/numl/master/LICENSE.md",
    "requireLicenseAcceptance": false,
    "repository": {
      "type": "git",
      "url": "https://raw.githubusercontent.com/sethjuarez/numl"
    },
    "owners": ["Seth Juarez"]
  }
}
```

```xml
<PropertyGroup>
  <!-- summary is not migrated from project.json, but you can use the <Description> property for that if needed. -->
  <PackageTags>machine learning;framework</PackageTags>
  <PackageReleaseNotes>Version 0.9.12-beta</PackageReleaseNotes>
  <PackageIconUrl>http://numl.net/images/ico.png</PackageIconUrl>
  <PackageProjectUrl>http://numl.net</PackageProjectUrl>
  <PackageLicenseUrl>https://raw.githubusercontent.com/sethjuarez/numl/master/LICENSE.md</PackageLicenseUrl>
  <PackageRequireLicenseAcceptance>false</PackageRequireLicenseAcceptance>
  <RepositoryType>git</RepositoryType>
  <RepositoryUrl>https://raw.githubusercontent.com/sethjuarez/numl</RepositoryUrl>
  <!-- owners is not supported in MSBuild -->
</PropertyGroup>
```

В MSBuild нет эквивалента для элемента `owners`.
Для `summary` можно использовать свойство `<Description>` MSBuild, даже если значение `summary` не переносится на него автоматически, так как это свойство сопоставляется с элементом [`description`](#other-common-root-level-options).

## <a name="scripts"></a>scripts

```json
{
  "scripts": {
    "precompile": "generateCode.cmd",
    "postpublish": [ "obfuscate.cmd", "removeTempFiles.cmd" ]
  }
}
```

Эквивалентом в MSBuild являются [цели](/visualstudio/msbuild/msbuild-targets):

```xml
<Target Name="MyPreCompileTarget" BeforeTargets="Build">
  <Exec Command="generateCode.cmd" />
</Target>

<Target Name="MyPostCompileTarget" AfterTargets="Publish">
  <Exec Command="obfuscate.cmd" />
  <Exec Command="removeTempFiles.cmd" />
</Target>
```

## <a name="runtimeoptions"></a>runtimeOptions

```json
{
  "runtimeOptions": {
    "configProperties": {
      "System.GC.Server": true,
      "System.GC.Concurrent": true,
      "System.GC.RetainVM": true,
      "System.Threading.ThreadPool.MinThreads": 4,
      "System.Threading.ThreadPool.MaxThreads": 25
    }
  }
}
```

Все параметры в этой группе, кроме свойства "System.GC.Server", помещаются в файл *runtimeconfig.template.json* в папке проекта, при этом параметры переносятся до корневого объекта в процессе миграции:

```json
{
  "configProperties": {
    "System.GC.Concurrent": true,
    "System.GC.RetainVM": true,
    "System.Threading.ThreadPool.MinThreads": 4,
    "System.Threading.ThreadPool.MaxThreads": 25
  }
}
```

Свойство "System.GC.Server" переносится в файл CSPROJ:

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

Но все эти значения можно задать в CSPROJ, а также в свойствах MSBuild:

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
  <ConcurrentGarbageCollection>true</ConcurrentGarbageCollection>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  <ThreadPoolMaxThreads>25</ThreadPoolMaxThreads>
</PropertyGroup>
```

## <a name="shared"></a>общие

```json
{
  "shared": "shared/**/*.cs"
}
```

Не поддерживается в CSPROJ. Вместо этого необходимо создать файлы для включения содержимого в ваш файл *NUSPEC*.
Дополнительные сведения см. в разделе [Включение файлов содержимого](/nuget/schema/nuspec#including-content-files).

## <a name="files"></a>файлы

В *project.json* сборку и упаковку можно расширить для компиляции и внедрения из разных папок.
В MSBuild это делается с помощью [элементов](/visualstudio/msbuild/common-msbuild-project-items). Следующий пример описывает типичное преобразование:

```json
{
  "buildOptions": {
    "compile": {
      "copyToOutput": "notes.txt",
      "include": "../Shared/*.cs",
      "exclude": "../Shared/Not/*.cs"
    },
    "embed": {
      "include": "../Shared/*.resx"
    }
  },
  "packOptions": {
    "include": "Views/",
    "mappings": {
      "some/path/in/project.txt": "in/package.txt"
    }
  },
  "publishOptions": {
    "include": [
      "files/",
      "publishnotes.txt"
    ]
  }
}
```

```xml
<ItemGroup>
  <Compile Include="..\Shared\*.cs" Exclude="..\Shared\Not\*.cs" />
  <EmbeddedResource Include="..\Shared\*.resx" />
  <Content Include="Views\**\*" PackagePath="%(Identity)" />
  <None Include="some/path/in/project.txt" Pack="true" PackagePath="in/package.txt" />
  
  <None Include="notes.txt" CopyToOutputDirectory="Always" />
  <!-- CopyToOutputDirectory = { Always, PreserveNewest, Never } -->

  <Content Include="files\**\*" CopyToPublishDirectory="PreserveNewest" />
  <None Include="publishnotes.txt" CopyToPublishDirectory="Always" />
  <!-- CopyToPublishDirectory = { Always, PreserveNewest, Never } -->
</ItemGroup>
```

> [!NOTE]
> Многие из [стандартных масок](https://en.wikipedia.org/wiki/Glob_(programming)) по умолчанию добавляются автоматически с помощью пакета SDK для .NET Core.
> Дополнительные сведения см. в статье [Значения для элемента Compile по умолчанию](https://aka.ms/sdkimplicititems).

Все элементы `ItemGroup` MSBuild поддерживают `Include`, `Exclude` и `Remove`.

Макет пакета внутри NUPKG можно изменить с помощью `PackagePath="path"`.

Кроме `Content`, для большинства групп элементов требуется явное добавление `Pack="true"` для включения в пакет. `Content` помещается в папку *content* пакета, так как для свойства `<IncludeContentInPack>` MSBuild по умолчанию задано значение `true`.
Дополнительные сведения см. в статье [Включение содержимого в пакет](/nuget/schema/msbuild-targets#including-content-in-a-package).

`PackagePath="%(Identity)"` позволяет быстро настроить относительный путь к файлу проекта в качестве пути к пакету.

## <a name="testrunner"></a>testRunner

### <a name="xunit"></a>xUnit

```json
{
  "testRunner": "xunit",
  "dependencies": {
    "dotnet-test-xunit": "<any>"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-*" />
  <PackageReference Include="xunit" Version="2.2.0-*" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0-*" />
</ItemGroup>
```

### <a name="mstest"></a>MSTest

```json
{
  "testRunner": "mstest",
  "dependencies": {
    "dotnet-test-mstest": "<any>"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-*" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.12-*" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.11-*" />
</ItemGroup>
```

## <a name="see-also"></a>См. также

- [Краткий обзор изменений в интерфейсе командной строки](../tools/cli-msbuild-architecture.md)
