---
title: Модель расширяемости CLI .NET Core
description: Узнайте, как можно расширить .NET Core CLI.
ms.date: 04/12/2017
ms.openlocfilehash: 56a9cedc090ddca446c0ee1a60f2ca49590e7635
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451159"
---
# <a name="net-core-cli-extensibility-model"></a><span data-ttu-id="050cc-103">Модель расширяемости CLI .NET Core</span><span class="sxs-lookup"><span data-stu-id="050cc-103">.NET Core CLI extensibility model</span></span>

<span data-ttu-id="050cc-104">В этой статье показано, как можно разными способами расширить .NET Core CLI, и описаны сценарии для каждого из способов.</span><span class="sxs-lookup"><span data-stu-id="050cc-104">This article covers the different ways you can extend the .NET Core CLI and explain the scenarios that drive each one of them.</span></span>
<span data-ttu-id="050cc-105">Вы увидите, как пользоваться средствами и создавать различные типы средств.</span><span class="sxs-lookup"><span data-stu-id="050cc-105">You'll see how to consume the tools as well as how to build the different types of tools.</span></span>

## <a name="how-to-extend-the-cli"></a><span data-ttu-id="050cc-106">Расширение CLI</span><span class="sxs-lookup"><span data-stu-id="050cc-106">How to extend the CLI</span></span>
<span data-ttu-id="050cc-107">CLI можно расширить тремя способами:</span><span class="sxs-lookup"><span data-stu-id="050cc-107">The CLI can be extended in three main ways:</span></span>

1. [<span data-ttu-id="050cc-108">С помощью пакетов NuGet для каждого отдельного проекта</span><span class="sxs-lookup"><span data-stu-id="050cc-108">Via NuGet packages on a per-project basis</span></span>](#per-project-based-extensibility)

   <span data-ttu-id="050cc-109">Средства для отдельных проектов включены в контекст проекта, но их легко установить с помощью восстановления.</span><span class="sxs-lookup"><span data-stu-id="050cc-109">Per-project tools are contained within the project's context, but they allow easy installation through restoration.</span></span>

2. [<span data-ttu-id="050cc-110">С помощью пакетов NuGet и пользовательских целевых объектов</span><span class="sxs-lookup"><span data-stu-id="050cc-110">Via NuGet packages with custom targets</span></span>](#custom-targets)

   <span data-ttu-id="050cc-111">Пользовательские целевые объекты позволяют с легкостью расширить процедуру сборки с помощью настраиваемых задач.</span><span class="sxs-lookup"><span data-stu-id="050cc-111">Custom targets allow you to easily extend the build process with custom tasks.</span></span>

3. [<span data-ttu-id="050cc-112">С помощью системной переменной PATH</span><span class="sxs-lookup"><span data-stu-id="050cc-112">Via the system's PATH</span></span>](#path-based-extensibility)

   <span data-ttu-id="050cc-113">Подход на основе пути подходит для общих межпроектных средств, которые могут использоваться на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="050cc-113">PATH-based tools are good for general, cross-project tools that are usable on a single machine.</span></span>

<span data-ttu-id="050cc-114">Три указанных выше механизма расширяемости не являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="050cc-114">The three extensibility mechanisms outlined above are not exclusive.</span></span> <span data-ttu-id="050cc-115">Вы можете использовать один механизм, все механизмы или любое их сочетание.</span><span class="sxs-lookup"><span data-stu-id="050cc-115">You can use one, or all, or a combination of them.</span></span> <span data-ttu-id="050cc-116">Выбор механизма зависит в первую очередь от цели, которой вы стремитесь достичь за счет расширения.</span><span class="sxs-lookup"><span data-stu-id="050cc-116">Which one to pick depends largely on the goal you are trying to achieve with your extension.</span></span>

## <a name="per-project-based-extensibility"></a><span data-ttu-id="050cc-117">Расширяемость на основе отдельных проектов</span><span class="sxs-lookup"><span data-stu-id="050cc-117">Per-project based extensibility</span></span>
<span data-ttu-id="050cc-118">Средства для отдельных проектов — это [развертывания, зависимые от платформы](../deploying/index.md#publish-runtime-dependent), которые распространяются как пакеты NuGet.</span><span class="sxs-lookup"><span data-stu-id="050cc-118">Per-project tools are [framework-dependent deployments](../deploying/index.md#publish-runtime-dependent) that are distributed as NuGet packages.</span></span> <span data-ttu-id="050cc-119">Средства доступны только в контексте проекта, который ссылается на них и для которого они восстанавливаются.</span><span class="sxs-lookup"><span data-stu-id="050cc-119">Tools are only available in the context of the project that references them and for which they are restored.</span></span> <span data-ttu-id="050cc-120">Вызов вне контекста проекта (например, вне каталога, содержащего проект) завершится с ошибкой из-за того, что не удается найти команду.</span><span class="sxs-lookup"><span data-stu-id="050cc-120">Invocation outside of the context of the project (for example, outside of the directory that contains the project) will fail because the command cannot be found.</span></span>

<span data-ttu-id="050cc-121">Эти средства идеально подходят для создания серверов, так как для них не требуется ничего, кроме файла проекта.</span><span class="sxs-lookup"><span data-stu-id="050cc-121">These tools are perfect for build servers, since nothing outside of the project file is needed.</span></span> <span data-ttu-id="050cc-122">Процесс сборки выполняет восстановление для соответствующего проекта, и средства становятся доступны.</span><span class="sxs-lookup"><span data-stu-id="050cc-122">The build process runs restore for the project it builds and tools will be available.</span></span> <span data-ttu-id="050cc-123">К этой категории также относятся проекты на таких языках, как F#, так как каждый проект может быть написан только на одном языке.</span><span class="sxs-lookup"><span data-stu-id="050cc-123">Language projects, such as F#, are also in this category since each project can only be written in one specific language.</span></span>

<span data-ttu-id="050cc-124">Наконец, эта модель расширяемости обеспечивает поддержку создания средств, которым требуется доступ к выходным данным сборки проекта.</span><span class="sxs-lookup"><span data-stu-id="050cc-124">Finally, this extensibility model provides support for creation of tools that need access to the built output of the project.</span></span> <span data-ttu-id="050cc-125">Например, различные средства просмотра Razor в приложениях MVC [ASP.NET](https://www.asp.net/) попадают в эту категорию.</span><span class="sxs-lookup"><span data-stu-id="050cc-125">For instance, various Razor view tools in [ASP.NET](https://www.asp.net/) MVC applications fall into this category.</span></span>

### <a name="consuming-per-project-tools"></a><span data-ttu-id="050cc-126">Использование средств для отдельных проектов</span><span class="sxs-lookup"><span data-stu-id="050cc-126">Consuming per-project tools</span></span>
<span data-ttu-id="050cc-127">Для каждого средства, который нужно использовать, необходимо добавить элемент `<DotNetCliToolReference>` в файл проекта.</span><span class="sxs-lookup"><span data-stu-id="050cc-127">Consuming these tools requires you to add a `<DotNetCliToolReference>` element to your project file for each tool you want to use.</span></span> <span data-ttu-id="050cc-128">В элементе `<DotNetCliToolReference>` нужно сослаться на пакет, в котором находится средство, и указать необходимую версию.</span><span class="sxs-lookup"><span data-stu-id="050cc-128">Inside the `<DotNetCliToolReference>` element, you reference the package in which the tool resides and specify the version you need.</span></span> <span data-ttu-id="050cc-129">После выполнения команды [`dotnet restore`](dotnet-restore.md) средство и его зависимости восстанавливаются.</span><span class="sxs-lookup"><span data-stu-id="050cc-129">After running [`dotnet restore`](dotnet-restore.md), the tool and its dependencies are restored.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="050cc-130">Для средств, выполнение которых требует загрузки выходных данных сборки проекта, обычно имеется еще одна зависимость, которая указывается в списке стандартных зависимостей в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="050cc-130">For tools that need to load the build output of the project for execution, there is usually another dependency which is listed under the regular dependencies in the project file.</span></span> <span data-ttu-id="050cc-131">Так как интерфейс командной строки использует MSBuild в качестве подсистемы сборки, рекомендуется записать эти части средства в виде пользовательских [целевых объектов](/visualstudio/msbuild/msbuild-targets) и [задач](/visualstudio/msbuild/msbuild-tasks) MSBuild: так они смогут участвовать в общем процессе сборки.</span><span class="sxs-lookup"><span data-stu-id="050cc-131">Since CLI uses MSBuild as its build engine, we recommend that these parts of the tool be written as custom MSBuild [targets](/visualstudio/msbuild/msbuild-targets) and [tasks](/visualstudio/msbuild/msbuild-tasks), since they can then take part in the overall build process.</span></span> <span data-ttu-id="050cc-132">Кроме того, они легко могут получить любые данные, генерируемые во время сборки, например расположение выходных файлов, текущую создаваемую конфигурацию и т. д.</span><span class="sxs-lookup"><span data-stu-id="050cc-132">Also, they can get any and all data easily that is produced via the build, such as the location of the output files, the current configuration being built, and so on.</span></span> <span data-ttu-id="050cc-133">Все эти данные превращаются в набор свойств MSBuild, которые могут быть считаны из любого целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="050cc-133">All this information becomes a set of MSBuild properties that can be read from any target.</span></span> <span data-ttu-id="050cc-134">Далее в этом документе вы узнаете, как добавить пользовательский целевой объект с помощью NuGet.</span><span class="sxs-lookup"><span data-stu-id="050cc-134">You can see how to add a custom target using NuGet later in this document.</span></span>

<span data-ttu-id="050cc-135">Рассмотрим пример добавления простого средства на основе узла tools в простой проект.</span><span class="sxs-lookup"><span data-stu-id="050cc-135">Let's review an example of adding a simple tools-only tool to a simple project.</span></span> <span data-ttu-id="050cc-136">Предположим, что есть команда `dotnet-api-search`, которая позволяет искать указанный интерфейс API в пакетах NuGet. Вот файл проекта консольного приложения, которое использует это средство:</span><span class="sxs-lookup"><span data-stu-id="050cc-136">Given an example command called `dotnet-api-search` that allows you to search through the NuGet packages for the specified API, here is a console application's project file that uses that tool:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>

  <!-- The tools reference -->
  <ItemGroup>
    <DotNetCliToolReference Include="dotnet-api-search" Version="1.0.0" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="050cc-137">Элемент `<DotNetCliToolReference>` имеет структуру, подобную структуре элемента `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="050cc-137">The `<DotNetCliToolReference>` element is structured in a similar way as the `<PackageReference>` element.</span></span> <span data-ttu-id="050cc-138">Для восстановления потребуются идентификатор пакета, содержащего средство, и его версия.</span><span class="sxs-lookup"><span data-stu-id="050cc-138">It needs the package ID of the package containing the tool and its version to be able to restore.</span></span>

### <a name="building-tools"></a><span data-ttu-id="050cc-139">Создание средств</span><span class="sxs-lookup"><span data-stu-id="050cc-139">Building tools</span></span>
<span data-ttu-id="050cc-140">Как было сказано ранее, средства — это просто переносимые консольные приложения.</span><span class="sxs-lookup"><span data-stu-id="050cc-140">As mentioned, tools are just portable console applications.</span></span> <span data-ttu-id="050cc-141">Сборка средств выполняется так же, как и сборка других консольных приложений.</span><span class="sxs-lookup"><span data-stu-id="050cc-141">You build tools as you would build any other console application.</span></span>
<span data-ttu-id="050cc-142">После сборки используйте команду [`dotnet pack`](dotnet-pack.md), чтобы создать пакет NuGet (NUPKG-файл), содержащий код, сведения о зависимостях и т. д.</span><span class="sxs-lookup"><span data-stu-id="050cc-142">After you build it, you use the [`dotnet pack`](dotnet-pack.md) command to create a NuGet package (.nupkg file) that contains your code, information about its dependencies, and so on.</span></span> <span data-ttu-id="050cc-143">Имя пакета может быть любым, но содержащееся в нем приложение, то есть двоичный файл средства, должно соответствовать соглашению `dotnet-<command>`, чтобы среда `dotnet` могла вызывать его.</span><span class="sxs-lookup"><span data-stu-id="050cc-143">You can give any name to the package, but the application inside, the actual tool binary, has to conform to the convention of `dotnet-<command>` in order for `dotnet` to be able to invoke it.</span></span>

> [!NOTE]
> <span data-ttu-id="050cc-144">В версиях-кандидатах до 3 средств командной строки .NET Core при работе команды `dotnet pack` возникала ошибка, из-за которой файл *.runtimeconfig.json* не упаковывался вместе со средством.</span><span class="sxs-lookup"><span data-stu-id="050cc-144">In pre-RC3 versions of the .NET Core command-line tools, the `dotnet pack` command had a bug that caused the *.runtimeconfig.json* to not be packed with the tool.</span></span> <span data-ttu-id="050cc-145">Из-за отсутствия файла происходили ошибки в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="050cc-145">Lacking that file results in errors at runtime.</span></span> <span data-ttu-id="050cc-146">При возникновении такой ситуации установите последнюю версию средства и повторите `dotnet pack`.</span><span class="sxs-lookup"><span data-stu-id="050cc-146">If you encounter this behavior, be sure to update to the latest tooling and try the `dotnet pack` again.</span></span>

<span data-ttu-id="050cc-147">Так как средства — это переносимые приложения, то для запуска средства у пользователя должна быть установлена та версия библиотек .NET Core, которая использовалась для сборки средства.</span><span class="sxs-lookup"><span data-stu-id="050cc-147">Since tools are portable applications, the user consuming the tool must have the version of the .NET Core libraries that the tool was built against in order to run the tool.</span></span> <span data-ttu-id="050cc-148">Зависимости, которые использует средство и которые не содержатся в библиотеках .NET Core, восстанавливаются и помещаются в кэш NuGet.</span><span class="sxs-lookup"><span data-stu-id="050cc-148">Any other dependency that the tool uses and that is not contained within the .NET Core libraries is restored and placed in the NuGet cache.</span></span> <span data-ttu-id="050cc-149">Таким образом, средство в целом выполняется с помощью сборок из библиотек .NET Core, а также сборок из кэша NuGet.</span><span class="sxs-lookup"><span data-stu-id="050cc-149">The entire tool is, therefore, run using the assemblies from the .NET Core libraries as well as assemblies from the NuGet cache.</span></span>

<span data-ttu-id="050cc-150">Подобные средства имеют схему зависимостей, которая никак не связана со схемой зависимостей проекта, использующего эти средства.</span><span class="sxs-lookup"><span data-stu-id="050cc-150">These kinds of tools have a dependency graph that is completely separate from the dependency graph of the project that uses them.</span></span> <span data-ttu-id="050cc-151">В ходе восстановления сначала восстанавливаются зависимости проекта, а затем каждое из средств и их зависимости.</span><span class="sxs-lookup"><span data-stu-id="050cc-151">The restore process first restores the project's dependencies and then restores each of the tools and their dependencies.</span></span>

<span data-ttu-id="050cc-152">Вы можете найти более подробные примеры и различные сочетания в [репозитории CLI .NET Core](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestProjects).</span><span class="sxs-lookup"><span data-stu-id="050cc-152">You can find richer examples and different combinations of this in the [.NET Core CLI repo](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestProjects).</span></span>
<span data-ttu-id="050cc-153">Вы также можете найти [реализацию используемых средств](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestPackages) в том же репозитории.</span><span class="sxs-lookup"><span data-stu-id="050cc-153">You can also see the [implementation of tools used](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestPackages) in the same repo.</span></span>

## <a name="custom-targets"></a><span data-ttu-id="050cc-154">Пользовательские целевые объекты</span><span class="sxs-lookup"><span data-stu-id="050cc-154">Custom targets</span></span>

<span data-ttu-id="050cc-155">NuGet позволяет [упаковывать пользовательские целевые объекты MSBuild и файлы свойств](/nuget/create-packages/creating-a-package#include-msbuild-props-and-targets-in-a-package).</span><span class="sxs-lookup"><span data-stu-id="050cc-155">NuGet has the capability to [package custom MSBuild targets and props files](/nuget/create-packages/creating-a-package#include-msbuild-props-and-targets-in-a-package).</span></span> <span data-ttu-id="050cc-156">В связи с переключением .NET Core на использование MSBuild к проектам .NET Core теперь применяется тот же механизм расширяемости.</span><span class="sxs-lookup"><span data-stu-id="050cc-156">With the move of the .NET Core to use MSBuild, the same mechanism of extensibility now applies to .NET Core projects.</span></span> <span data-ttu-id="050cc-157">Этот тип расширяемости можно использовать для оптимизации процедуры сборки, получения доступа к любым артефактам в процессе сборки (например, к созданным файлам), проверки конфигурации, с помощью которой вызывается сборка, и т. д.</span><span class="sxs-lookup"><span data-stu-id="050cc-157">You would use this type of extensibility when you want to extend the build process, or when you want to access any of the artifacts in the build process, such as generated files, or you want to inspect the configuration under which the build is invoked, and so on.</span></span>

<span data-ttu-id="050cc-158">В следующем примере показан целевой файл проекта, в котором используется синтаксис `csproj`.</span><span class="sxs-lookup"><span data-stu-id="050cc-158">In the following example, you can see the target's project file using the `csproj` syntax.</span></span> <span data-ttu-id="050cc-159">С помощью этого синтаксиса определяются объекты, которые будут упакованы командой [`dotnet pack`](dotnet-pack.md): целевые файлы, а также сборки помещаются в каталог *build* внутри пакета.</span><span class="sxs-lookup"><span data-stu-id="050cc-159">This instructs the [`dotnet pack`](dotnet-pack.md) command what to package, placing the targets files as well as the assemblies into the *build* folder inside the package.</span></span> <span data-ttu-id="050cc-160">Обратите внимание, что свойство `Label` для элемента `<ItemGroup>` установлено в значение `dotnet pack instructions`, и под ним определен целевой объект.</span><span class="sxs-lookup"><span data-stu-id="050cc-160">Notice the `<ItemGroup>` element that has the `Label` property set to `dotnet pack instructions`, and the Target defined beneath it.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <Description>Sample Packer</Description>
    <VersionPrefix>0.1.0-preview</VersionPrefix>
    <TargetFramework>netstandard1.3</TargetFramework>
    <DebugType>portable</DebugType>
    <AssemblyName>SampleTargets.PackerTarget</AssemblyName>
  </PropertyGroup>
  <ItemGroup>
    <EmbeddedResource Include="Resources\Pkg\dist-template.xml;compiler\resources\**\*" Exclude="bin\**;obj\**;**\*.xproj;packages\**" />
    <None Include="build\SampleTargets.PackerTarget.targets" />
  </ItemGroup>
  <ItemGroup Label="dotnet pack instructions">
    <Content Include="build\*.targets">
      <Pack>true</Pack>
      <PackagePath>build\</PackagePath>
    </Content>
  </ItemGroup>
  <Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">
    <!-- Collect these items inside a target that runs after build but before packaging. -->
    <ItemGroup>
      <Content Include="$(OutputPath)\*.dll;$(OutputPath)\*.json">
        <Pack>true</Pack>
        <PackagePath>build\</PackagePath>
      </Content>
    </ItemGroup>
  </Target>
  <ItemGroup>
    <PackageReference Include="Microsoft.Extensions.DependencyModel" Version="1.0.1-beta-000933"/>
    <PackageReference Include="Microsoft.Build.Framework" Version="0.1.0-preview-00028-160627" />
    <PackageReference Include="Microsoft.Build.Utilities.Core" Version="0.1.0-preview-00028-160627" />
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
  <ItemGroup />
  <PropertyGroup Label="Globals">
    <ProjectGuid>463c66f0-921d-4d34-8bde-7c9d0bffaf7b</ProjectGuid>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(TargetFramework)' == 'netstandard1.3' ">
    <DefineConstants>$(DefineConstants);NETSTANDARD1_3</DefineConstants>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)' == 'Release' ">
    <DefineConstants>$(DefineConstants);RELEASE</DefineConstants>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="050cc-161">Для использования пользовательских целевых объектов задается элемент `<PackageReference>`, указывающий на пакет и его версию внутри проекта, который расширяется.</span><span class="sxs-lookup"><span data-stu-id="050cc-161">Consuming custom targets is done by providing a `<PackageReference>` that points to the package and its version inside the project that is being extended.</span></span> <span data-ttu-id="050cc-162">В отличие от средств пакет пользовательских целевых объектов входит в замыкание зависимостей исходного проекта.</span><span class="sxs-lookup"><span data-stu-id="050cc-162">Unlike the tools, the custom targets package does get included into the consuming project's dependency closure.</span></span>

<span data-ttu-id="050cc-163">Использование пользовательского целевого объекта зависит только от способа настройки.</span><span class="sxs-lookup"><span data-stu-id="050cc-163">Using the custom target depends solely on how you configure it.</span></span> <span data-ttu-id="050cc-164">Так как это целевой объект MSBuild, он может зависеть от заданного целевого объекта, запускаться после другого целевого объекта, а также быть вызван вручную с помощью команды `dotnet msbuild -t:<target-name>`.</span><span class="sxs-lookup"><span data-stu-id="050cc-164">Since it's an MSBuild target, it can depend on a given target, run after another target and can also be manually invoked using the `dotnet msbuild -t:<target-name>` command.</span></span>

<span data-ttu-id="050cc-165">Однако для удобства пользователей можно объединить средства для отдельных проектов и пользовательские целевые объекты.</span><span class="sxs-lookup"><span data-stu-id="050cc-165">However, if you want to provide a better user experience to your users, you can combine per-project tools and custom targets.</span></span> <span data-ttu-id="050cc-166">В этом случае средство для отдельного проекта будет принимать все необходимые параметры и преобразовывать их в необходимый вызов [`dotnet msbuild`](dotnet-msbuild.md) для целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="050cc-166">In this scenario, the per-project tool would essentially just accept whatever needed parameters and would translate that into the required [`dotnet msbuild`](dotnet-msbuild.md) invocation that would execute the target.</span></span> <span data-ttu-id="050cc-167">Пример подобного типа синергии можно увидеть в репозитории [примеров хакатона MVP Summit 2016](https://github.com/dotnet/MVPSummitHackathon2016) в проекте [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer).</span><span class="sxs-lookup"><span data-stu-id="050cc-167">You can see a sample of this kind of synergy on the [MVP Summit 2016 Hackathon samples](https://github.com/dotnet/MVPSummitHackathon2016) repo in the [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer) project.</span></span>

## <a name="path-based-extensibility"></a><span data-ttu-id="050cc-168">Расширяемость на основе пути</span><span class="sxs-lookup"><span data-stu-id="050cc-168">PATH-based extensibility</span></span>
<span data-ttu-id="050cc-169">Расширяемость на основе пути обычно используется на компьютерах разработки, на которых требуется средство, которое охватывает более одного проекта.</span><span class="sxs-lookup"><span data-stu-id="050cc-169">PATH-based extensibility is usually used for development machines where you need a tool that conceptually covers more than a single project.</span></span> <span data-ttu-id="050cc-170">Основным недостатком такого механизма расширения является его привязка к компьютеру, на котором размещается средство.</span><span class="sxs-lookup"><span data-stu-id="050cc-170">The main drawback of this extension mechanism is that it's tied to the machine where the tool exists.</span></span> <span data-ttu-id="050cc-171">Если средство требуется на другом компьютере, его необходимо развернуть.</span><span class="sxs-lookup"><span data-stu-id="050cc-171">If you need it on another machine, you would have to deploy it.</span></span>

<span data-ttu-id="050cc-172">Такая схема расширяемости набора средств CLI очень проста.</span><span class="sxs-lookup"><span data-stu-id="050cc-172">This pattern of CLI toolset extensibility is very simple.</span></span> <span data-ttu-id="050cc-173">Как указано в [обзоре CLI .NET Core](index.md), драйвер `dotnet` может выполнять любую команду, имя которой соответствует соглашению `dotnet-<command>`.</span><span class="sxs-lookup"><span data-stu-id="050cc-173">As covered in the [.NET Core CLI overview](index.md), `dotnet` driver can run any command that is named after the `dotnet-<command>` convention.</span></span> <span data-ttu-id="050cc-174">Логика разрешения по умолчанию сначала проверяет несколько расположений и в конечном итоге переключается на системный путь.</span><span class="sxs-lookup"><span data-stu-id="050cc-174">The default resolution logic first probes several locations and finally falls back to the system PATH.</span></span> <span data-ttu-id="050cc-175">Если запрошенная команда существует по системному пути и является двоичным файлом, который можно вызвать, драйвер `dotnet` вызовет ее.</span><span class="sxs-lookup"><span data-stu-id="050cc-175">If the requested command exists in the system PATH and is a binary that can be invoked, `dotnet` driver will invoke it.</span></span>

<span data-ttu-id="050cc-176">Файл должен быть исполняемым.</span><span class="sxs-lookup"><span data-stu-id="050cc-176">The file must be executable.</span></span> <span data-ttu-id="050cc-177">В системах Unix это означает любой файл с битом выполнения, заданным посредством `chmod +x`.</span><span class="sxs-lookup"><span data-stu-id="050cc-177">On Unix systems, this means anything that has the execute bit set via `chmod +x`.</span></span> <span data-ttu-id="050cc-178">В Windows можно использовать файлы *cmd*.</span><span class="sxs-lookup"><span data-stu-id="050cc-178">On Windows, you can use *cmd* files.</span></span>

<span data-ttu-id="050cc-179">В качестве примера рассмотрим очень простую реализацию программы "Hello World".</span><span class="sxs-lookup"><span data-stu-id="050cc-179">Let's take a look at the very simple implementation of a "Hello World" tool.</span></span> <span data-ttu-id="050cc-180">В Windows мы будем использовать как `bash`, так и `cmd`.</span><span class="sxs-lookup"><span data-stu-id="050cc-180">We will use both `bash` and `cmd` on Windows.</span></span>
<span data-ttu-id="050cc-181">Следующая команда просто выводит текст "Hello World" в консоль.</span><span class="sxs-lookup"><span data-stu-id="050cc-181">The following command will simply echo "Hello World" to the console.</span></span>

```bash
#!/bin/bash

echo "Hello World!"
```

```cmd
echo "Hello World"
```

<span data-ttu-id="050cc-182">В Mac OS можно сохранить этот скрипт как `dotnet-hello` и задать его бит выполнения с помощью `chmod +x dotnet-hello`.</span><span class="sxs-lookup"><span data-stu-id="050cc-182">On macOS, we can save this script as `dotnet-hello` and set its executable bit with `chmod +x dotnet-hello`.</span></span> <span data-ttu-id="050cc-183">Затем можно создать символьную ссылку на него в `/usr/local/bin` с помощью команды `ln -s <full_path>/dotnet-hello /usr/local/bin/`.</span><span class="sxs-lookup"><span data-stu-id="050cc-183">We can then create a symbolic link to it in `/usr/local/bin` using the command `ln -s <full_path>/dotnet-hello /usr/local/bin/`.</span></span> <span data-ttu-id="050cc-184">Это позволит вызывать команду с использованием синтаксиса `dotnet hello`.</span><span class="sxs-lookup"><span data-stu-id="050cc-184">This will make it possible to invoke the command using the `dotnet hello` syntax.</span></span>

<span data-ttu-id="050cc-185">В Windows можно сохранить этот сценарий как `dotnet-hello.cmd` и поместить его в расположение, которое находится в системном пути (или добавить в папку, которая уже находится в системном пути).</span><span class="sxs-lookup"><span data-stu-id="050cc-185">On Windows, we can save this script as `dotnet-hello.cmd` and put it in a location that is in a system path (or you can add it to a folder that is already in the path).</span></span> <span data-ttu-id="050cc-186">После этого для запуска этого примера достаточно использовать команду `dotnet hello`.</span><span class="sxs-lookup"><span data-stu-id="050cc-186">After this, you can just use `dotnet hello` to run this example.</span></span>
