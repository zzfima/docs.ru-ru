---
title: "Модель расширяемости CLI .NET Core"
description: "Модель расширяемости CLI .NET Core"
keywords: "CLI, расширяемость, пользовательские команды, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 11/13/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 1bebd25a-120f-48d3-8c25-c89965afcbcd
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: 2cf58161a75894a12f47cf67a5760dc26f9d261c

---

# <a name="net-core-cli-extensibility-model"></a>Модель расширяемости CLI .NET Core 

## <a name="overview"></a>Обзор
В этом документе рассматриваются основные способы расширения средств интерфейса командной строки (CLI) и приводятся сценарии, в которых используется каждое из этих средств. В ней вкратце описывается использование средств, а также приводятся замечания по созданию средств обоих типов. 

## <a name="how-to-extend-cli-tools"></a>Расширение средств CLI
Средства CLI предварительной версии 3 можно расширять тремя основными способами:

1. посредством пакетов NuGet для каждого отдельного проекта;
2. Посредством пакетов NuGet с использованием пользовательских целевых объектов.  
3. посредством системного пути;

Три указанных выше механизма расширяемости не являются взаимоисключающими: вы можете использовать все, только один из них или их сочетание. Выбор зависит в первую очередь от цели, которой вы стремитесь достичь своим расширением.

## <a name="per-project-based-extensibility"></a>Расширяемость на основе отдельных проектов
Средства для отдельных проектов — это [платформозависимые развертывания](../deploying/index.md), которые распространяются как пакеты NuGet. Средства доступны только в контексте проекта, который ссылается на них и для которого они восстанавливаются. Вызов вне контекста проекта (например, вне каталога, содержащего проект) завершится сбоем, так как команду не удастся найти.

Эти средства идеально подходят для создания серверов, так как для них не требуется ничего, кроме файла проекта. Процесс сборки выполняет восстановление для соответствующего проекта, и средства становятся доступны. Проекты на таких языках, как F#, также относятся к этой категории. В конце концов, каждый проект может быть написан только на одном языке. 

Наконец, эта модель расширяемости обеспечивает поддержку создания средств, которым требуется доступ к выходным данным сборки проекта. Например, различные средства просмотра Razor в приложениях MVC [ASP.NET](https://www.asp.net/) попадают в эту категорию. 

### <a name="consuming-per-project-tools"></a>Использование средств для отдельных проектов
Для каждого средства, которое нужно использовать, в файле проекта необходимо добавить элемент `<DotNetCliToolReference>`. Внутри элемента `<DotNetCliToolReference>` нужно сослаться на пакет, в котором находится средство, и указать необходимую версию. После выполнения команды `dotnet restore` средство и его зависимости восстанавливаются. 

Для средств, выполнение которых требует загрузки выходных данных сборки проекта, обычно имеется еще одна зависимость, которая указывается в списке стандартных зависимостей в файле проекта. Так как в предварительной версии 3 средств интерфейса командной строки (CLI) в качестве обработчика сборки используется MSBuild, рекомендуется записать эти части средства в виде пользовательских целевых объектов и задач MSBuild, поскольку таким образом они смогут участвовать в общем процессе сборки. Кроме того, они легко могут получить часть или все данные, полученные посредством сборки, например расположение выходных файлов, текущую создаваемую конфигурацию и т. д. В предварительной версии 3 все эти данные принимают вид набора свойств MSBuild, которые могут быть считаны из любого целевого объекта. Далее в этом документе вы узнаете, как добавить пользовательский целевой объект с помощью NuGet. 

Рассмотрим пример добавления простого средства на основе узла tools в простой проект. Предположим, что есть команда `dotnet-api-search`, которая позволяет искать указанный интерфейс API в пакетах NuGet. Вот файл проекта консольного приложения, которое использует это средство:


```xml
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1/TargetFramework>
    <VersionPrefix>1.0.0</VersionPrefix>
  </PropertyGroup>
  <ItemGroup>
    <Compile Include="**\*.cs" />
    <EmbeddedResource Include="**\*.resx" />
  </ItemGroup>
  <ItemGroup>
    <PackageReference Include="Microsoft.NETCore.App">
      <Version>1.1.0</Version>
    </PackageReference>
    <PackageReference Include="Microsoft.NET.Sdk">
      <Version>1.0.0-alpha-20161102-2</Version>
      <PrivateAssets>All</PrivateAssets>
    </PackageReference>
  </ItemGroup>

  <!-- The tools reference -->
  <ItemGroup>
    <DotNetCliToolReference Include="dotnet-api-search">
      <Version></Version>
    </DotNetCliToolReference>
  </ItemGroup>

  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
</Project>
```

Элемент `<DotNetCliToolReference>` имеет структуру, подобную структуре элемента `<PackageReference>`. Ему требуются по крайней мере идентификатор пакета, содержащего средство, и его версия. 

### <a name="building-tools"></a>Создание средств
Как было сказано ранее, средства — это просто переносимые консольные приложения. Они создаются так же, как любые другие консольные приложения. После сборки используйте команду [`dotnet pack`](dotnet-pack.md), чтобы создать пакет NuGet (nupkg), содержащий код, сведения о зависимостях и т. д. Имя пакета может быть любым, но содержащееся в нем приложение, то есть двоичный файл средства, должно соответствовать соглашению `dotnet-<command>`, чтобы среда `dotnet` могла вызывать его. 

В двоичных файлах предварительной версии 3 команда `dotnet pack` не будет упаковывать файл `runtimeconfig.json`, необходимый для запуска средства. Есть два способа упаковки этого файла.

1. Чтобы добавить этот файл, можно создать файл `nuspec` и использовать новую команду `dotnet nuget pack`, доступную в предварительной версии 3 средств CLI.
2. Можно также использовать новый элемент `<Content>` в `<ItemGroup>` в файле проекта, чтобы добавить файл вручную.

Работа с NUSPEC-файлами выходит за рамки данной статьи. Однако вы можете найти много полезных сведений в [официальной документации по NuGet](https://docs.nuget.org/ndocs/create-packages/creating-a-package#the-role-and-structure-of-the--nuspec-file). Ниже приведен пример файла `csproj`, применяемого во втором способе, и его конфигурация.

```xml
  <ItemGroup>
    <Content Include="$(OutputPath)\*.runtimeconfig.json">
      <Pack>true</Pack>
      <PackagePath>lib\$(TargetFramework)</PackagePath>
    </Content>
  </ItemGroup>
```

Этот элемент `<ItemGroup>` дает команде `dotnet pack` указание упаковать все файлы `runtimeconfig.json` в выходном каталоге сборки (заданные переменной `$(OutputPath)`) и разместить его в папку `lib` целевой платформы сборки. Целевая платформа сборки задается подобно выходному пути с помощью свойства MSBuild. После того как она будет задана, полученный NUPKG-файл средства будет содержать все, что требуется для запуска средства.

Так как средства — это переносимые приложения, то для его запуска у пользователя должна быть та версия библиотек .NET Core, для которой выполнялась сборка средства. Зависимости, которые использует средство и которые не содержатся в библиотеках .NET Core, восстанавливаются и помещаются в кэш NuGet. Таким образом, средство в целом выполняется с помощью сборок из библиотек .NET Core, а также сборок из кэша NuGet. 

Подобные средства имеют схему зависимостей, которая никак не связана со схемой зависимостей проекта, использующего эти средства. Процесс восстановления сначала восстанавливает зависимости проекта, а затем восстанавливает каждое из средств и их зависимости. 

Вы можете найти более подробные примеры и различные сочетания в [репозитории CLI .NET Core](https://github.com/dotnet/cli/tree/rel/1.0.0-preview2/TestAssets/TestProjects). Вы также можете найти [реализацию используемых средств](https://github.com/dotnet/cli/tree/rel/1.0.0-preview2/TestAssets/TestPackages) в том же репозитории. 

### <a name="custom-targets"></a>Пользовательские целевые объекты
С помощью NuGet уже некоторое время можно упаковывать пользовательские целевые объекты и PROPS-файлы MSBuild. Официальную документацию, посвященную этому вопросу, можно найти на [сайте документации по NuGet](https://docs.nuget.org/ndocs/create-packages/creating-a-package#including-msbuild-props-and-targets-in-a-package). В связи с переходом на использование MSBuild в средствах CLI к проектам .NET Core применяется тот же механизм расширяемости. Этот тип расширяемости можно использовать для расширения процедуры сборки или при необходимости получить доступ к любым артефактам в этой процедуре, например к созданным файлам, а также для проверки конфигурации, с помощью которой вызывается сборка, и т. д. 

Ниже приведен пример проектного файла целевого объекта для справки. В нем показано, как использовать новый синтаксис `csproj` для указания команде `dotnet pack`, что следует упаковать, чтобы поместить файлы целевых объектов вместе со сборками в папку `build` внутри пакета. Обратите внимание на элемент `<ItemGroup>` ниже, для свойства `Label` которого задано значение "dotnet pack instructions". 

```xml
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />
  <PropertyGroup>
    <Description>Sample Packer</Description>
    <VersionPrefix>0.1.0-preview</VersionPrefix>
    <TargetFramework>netstandard1.3</TargetFramework>
    <DebugType>portable</DebugType>
    <AssemblyName>SampleTargets.PackerTarget</AssemblyName>
  </PropertyGroup>
  <ItemGroup>
    <Compile Include="**\*.cs" Exclude="bin\**;obj\**;**\*.xproj;packages\**" />
    <EmbeddedResource Include="**\*.resx" Exclude="bin\**;obj\**;**\*.xproj;packages\**" />
    <EmbeddedResource Include="Resources\Pkg\dist-template.xml;compiler\resources\**\*" Exclude="bin\**;obj\**;**\*.xproj;packages\**" />
  </ItemGroup>
  <ItemGroup>
    <None Include="build\SampleTargets.PackerTarget.targets" />
  </ItemGroup>
  <ItemGroup Label="dotent pack instructions">
    <Content Include="build\*.targets;$(OutputPath)\*.dll;$(OutputPath)\*.json">
      <Pack>true</Pack>
      <PackagePath>build\</PackagePath>
    </Content>
  </ItemGroup>
  <ItemGroup>
    <PackageReference Include="Microsoft.NET.Sdk">
      <Version>1.0.0-alpha-20161029-1</Version>
      <PrivateAssets>All</PrivateAssets>
    </PackageReference>
    <PackageReference Include="Microsoft.Extensions.DependencyModel">
      <Version>1.0.1-beta-000933</Version>
    </PackageReference>
    <PackageReference Include="Microsoft.Build.Framework">
      <Version>0.1.0-preview-00028-160627</Version>
    </PackageReference>
    <PackageReference Include="Microsoft.Build.Utilities.Core">
      <Version>0.1.0-preview-00028-160627</Version>
    </PackageReference>
    <PackageReference Include="Newtonsoft.Json">
      <Version>9.0.1</Version>
    </PackageReference>
  </ItemGroup>
  <ItemGroup Condition=" '$(TargetFramework)' == 'netstandard1.3' ">
    <PackageReference Include="NETStandard.Library">
      <Version>1.6.0</Version>
    </PackageReference>
  </ItemGroup>
  <ItemGroup />
  <PropertyGroup Condition=" '$(TargetFramework)' == 'netstandard1.3' ">
    <DefineConstants>$(DefineConstants);NETSTANDARD1_3</DefineConstants>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)' == 'Release' ">
    <DefineConstants>$(DefineConstants);RELEASE</DefineConstants>
  </PropertyGroup>
  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
</Project>
```

Для использования пользовательских целевых объектов задается элемент `<PackageReference>`, указывающий на пакет и его версию внутри проекта, который расширяется. В отличие от средств пакет пользовательских целевых объектов входит в замыкание зависимостей исходного проекта. 

Использование пользовательского целевого объекта зависит только от способа настройки. Так как это обычный целевой объект MSBuild, он может зависеть от заданного целевого объекта, запускаться после другого целевого объекта, а также может быть вызван вручную с помощью команды `dotnet msbuild /t:<target-name>`. 

Если вы хотите упростить условия работы пользователей, можно объединить средства для отдельных проектов и пользовательские целевые объекты. В этом случае средство для отдельного проекта будет принимать все необходимые параметры и выполнять преобразование в нужный вызов `dotnet msbuild`, который выполнит целевой объект. Пример подобного типа синергии можно увидеть в репозитории [примеров хакатона MVP Summit 2016](https://github.com/dotnet/MVPSummitHackathon2016) в проекте [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer). 

### <a name="path-based-extensibility"></a>Расширяемость на основе пути
Расширяемость на основе пути обычно используется на компьютерах разработки, на которых требуется средство, которое охватывает более одного проекта. Основным недостатком такого механизма расширения является его привязка к компьютеру, на котором размещается средство. Если средство требуется на другом компьютере, его необходимо развернуть.

Такая схема расширяемости набора средств CLI очень проста. Как указано в [обзоре CLI .NET Core](index.md), драйвер `dotnet` может выполнять любую команду, имя которой соответствует соглашению `dotnet-<command>`. Логика разрешения по умолчанию сначала проверяет несколько расположений и в конечном итоге переключается на системный путь. Если запрошенная команда существует по системному пути и является двоичным файлом, который можно вызвать, драйвер `dotnet` вызовет ее. 

Двоичный файл может быть практически любым файлом, который может выполнить операционная система. В системах Unix это означает любой файл с битом выполнения, заданным посредством `chmod +x`. В Windows это любые файлы, которые система может запускать. 

В качестве примера рассмотрим очень простую реализацию команды `dotnet clean`. Для ее реализации мы используем `bash`. Команда просто удаляет каталоги `bin/` и `obj/` в текущем каталоге. Если в нее передается аргумент `--lock`, она также удаляет файл `project.lock.json`. Полный код команды приводится ниже. 

```bash
#!/bin/bash

# Delete the bin and obj dirs
rm -rf bin/ obj/

LOCK_FILE=$1
if [[ "$LOCK_FILE" = "--lock" ]]; then
    rm project.lock.json
fi


echo "Cleaning complete..."
```

В Mac OS можно сохранить этот скрипт как `dotnet-clean` и задать его бит выполнения с помощью `chmod +x dotnet-clean`. Затем можно создать символьную ссылку на него в `/usr/local/bin` с помощью команды `ln -s dotnet-clean /usr/local/bin/`. Это позволит вызывать чистую команду с использованием синтаксиса `dotnet clean`. Чтобы протестировать эту возможность, создайте приложение, выполните для него команду `dotnet build`, а затем выполните `dotnet clean`. 

## <a name="conclusion"></a>Заключение
Средства CLI .NET Core обеспечивают три основные точки расширяемости. Средства для отдельных проектов включены в контекст проекта, но обеспечивают простую установку путем восстановления. Пользовательские целевые объекты позволяют с легкостью расширить процедуру сборки с помощью настраиваемых задач. Подход на основе пути подходит для общих межпроектных средств, которые могут использоваться на одном компьютере. 




<!--HONumber=Nov16_HO3-->


