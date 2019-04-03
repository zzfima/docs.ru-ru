---
title: Дополнения к формату CSPROJ для .NET Core
description: Различия между существующими файлами и файлами CSPROJ .NET Core
ms.date: 09/22/2017
ms.openlocfilehash: e196be28f622873359153f32c5dd9b0b5a514c0f
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58654657"
---
# <a name="additions-to-the-csproj-format-for-net-core"></a><span data-ttu-id="2973d-103">Дополнения к формату CSPROJ для .NET Core</span><span class="sxs-lookup"><span data-stu-id="2973d-103">Additions to the csproj format for .NET Core</span></span>

<span data-ttu-id="2973d-104">В этом документе перечислены изменения, внесенные в файлы проекта при перемещении из *project.json* в *CSPROJ* и [MSBuild](https://github.com/Microsoft/MSBuild).</span><span class="sxs-lookup"><span data-stu-id="2973d-104">This document outlines the changes that were added to the project files as part of the move from *project.json* to *csproj* and [MSBuild](https://github.com/Microsoft/MSBuild).</span></span> <span data-ttu-id="2973d-105">Дополнительную информацию, которая касается синтаксиса файла проекта в общем, и справку см. в документации по [файлу проекта MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="2973d-105">For more information about general project file syntax and reference, see [the MSBuild project file](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation.</span></span>

## <a name="implicit-package-references"></a><span data-ttu-id="2973d-106">Неявные ссылки на пакет</span><span class="sxs-lookup"><span data-stu-id="2973d-106">Implicit package references</span></span>

<span data-ttu-id="2973d-107">Теперь неявные ссылки на метапакеты указываются в зависимости от целевой платформы, указанной в свойстве `<TargetFramework>` или `<TargetFrameworks>` файла проекта.</span><span class="sxs-lookup"><span data-stu-id="2973d-107">Metapackages are implicitly referenced based on the target framework(s) specified in the `<TargetFramework>` or `<TargetFrameworks>` property of your project file.</span></span> <span data-ttu-id="2973d-108">Если свойство `<TargetFramework>` указано, свойство `<TargetFrameworks>` игнорируется независимо от порядка.</span><span class="sxs-lookup"><span data-stu-id="2973d-108">`<TargetFrameworks>` is ignored if `<TargetFramework>` is specified, independent of order.</span></span>

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

### <a name="recommendations"></a><span data-ttu-id="2973d-109">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="2973d-109">Recommendations</span></span>

<span data-ttu-id="2973d-110">Так как теперь указываются неявные ссылки на метапакеты `Microsoft.NETCore.App` или `NetStandard.Library`, следует учитывать приведенные ниже рекомендации:</span><span class="sxs-lookup"><span data-stu-id="2973d-110">Since `Microsoft.NETCore.App` or `NetStandard.Library` metapackages are implicitly referenced, the following are our recommended best practices:</span></span>

* <span data-ttu-id="2973d-111">Ориентируясь на .NET Core или .NET Standard, никогда не указывайте явную ссылку на метапакеты `Microsoft.NETCore.App` или `NetStandard.Library` через элемент `<PackageReference>` в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="2973d-111">When targeting .NET Core or .NET Standard, never have an explicit reference to the `Microsoft.NETCore.App` or `NetStandard.Library` metapackages via a `<PackageReference>` item in your project file.</span></span>
* <span data-ttu-id="2973d-112">Если при ориентации на .NET Core нужна определенная версия среды выполнения, вместо ссылки на метапакет следует использовать свойство `<RuntimeFrameworkVersion>` в проекте (например, `1.0.4`).</span><span class="sxs-lookup"><span data-stu-id="2973d-112">If you need a specific version of the runtime when targeting .NET Core, you should use the `<RuntimeFrameworkVersion>` property in your project (for example, `1.0.4`) instead of referencing the metapackage.</span></span>
    * <span data-ttu-id="2973d-113">Это может произойти, например, когда вы используете [автономные развертывания](../deploying/index.md#self-contained-deployments-scd) и нуждаетесь в определенной версии исправления 1.0.0 LTS для среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2973d-113">This might happen if you are using [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) and you need a specific patch version of 1.0.0 LTS runtime, for example.</span></span>
* <span data-ttu-id="2973d-114">Если при ориентации на .NET Standard вам нужна конкретная версия метапакета `NetStandard.Library`, можно использовать свойство `<NetStandardImplicitPackageVersion>` и установить требуемую версию.</span><span class="sxs-lookup"><span data-stu-id="2973d-114">If you need a specific version of the `NetStandard.Library` metapackage when targeting .NET Standard, you can use the `<NetStandardImplicitPackageVersion>` property and set the version you need.</span></span>
* <span data-ttu-id="2973d-115">Не добавляйте и не обновляйте ссылки на метапакет `Microsoft.NETCore.App` или `NetStandard.Library` явным образом в проектах .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2973d-115">Don't explicitly add or update references to either the `Microsoft.NETCore.App` or `NetStandard.Library` metapackage in .NET Framework projects.</span></span> <span data-ttu-id="2973d-116">Если при использовании пакета NuGet на основе .NET Standard требуется любая версия `NetStandard.Library`, NuGet автоматически устанавливает ее.</span><span class="sxs-lookup"><span data-stu-id="2973d-116">If any version of `NetStandard.Library` is needed when using a .NET Standard-based NuGet package, NuGet automatically installs that version.</span></span>

## <a name="default-compilation-includes-in-net-core-projects"></a><span data-ttu-id="2973d-117">Компиляция по умолчанию, включенная в проекты .NET Core</span><span class="sxs-lookup"><span data-stu-id="2973d-117">Default compilation includes in .NET Core projects</span></span>
<span data-ttu-id="2973d-118">В рамках перехода на формат *CSPROJ* в последних версиях пакета SDK мы перенесли включения и исключения по умолчанию для элементов Compile и внедренные ресурсы в файлы свойств пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="2973d-118">With the move to the *csproj* format in the latest SDK versions, we've moved the default includes and excludes for compile items and embedded resources to the SDK properties files.</span></span> <span data-ttu-id="2973d-119">Это означает, что вам больше не нужно указывать эти элементы в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="2973d-119">This means that you no longer need to specify these items in your project file.</span></span>

<span data-ttu-id="2973d-120">Основной причиной этого является стремление очистить ваш файл проекта от всего лишнего.</span><span class="sxs-lookup"><span data-stu-id="2973d-120">The main reason for doing this is to reduce the clutter in your project file.</span></span> <span data-ttu-id="2973d-121">Значения по умолчанию в пакете SDK должны охватывать наиболее распространенные варианты использования, поэтому нет необходимости повторять их в каждом создаваемом проекте.</span><span class="sxs-lookup"><span data-stu-id="2973d-121">The defaults that are present in the SDK should cover most common use cases, so there is no need to repeat them in every project that you create.</span></span> <span data-ttu-id="2973d-122">Это позволяет уменьшить файлы проекта и гораздо проще читать их, а также вносить правки вручную.</span><span class="sxs-lookup"><span data-stu-id="2973d-122">This leads to smaller project files that are much easier to understand as well as edit by hand, if needed.</span></span>

<span data-ttu-id="2973d-123">Следующая таблица показывает, какой элемент и какие [стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) включены и исключены в пакете SDK:</span><span class="sxs-lookup"><span data-stu-id="2973d-123">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are both included and excluded in the SDK:</span></span>

| <span data-ttu-id="2973d-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="2973d-124">Element</span></span>           | <span data-ttu-id="2973d-125">Стандартная маска включения</span><span class="sxs-lookup"><span data-stu-id="2973d-125">Include glob</span></span>                              | <span data-ttu-id="2973d-126">Стандартная маска исключения</span><span class="sxs-lookup"><span data-stu-id="2973d-126">Exclude glob</span></span>                                                  | <span data-ttu-id="2973d-127">Стандартная маска удаления</span><span class="sxs-lookup"><span data-stu-id="2973d-127">Remove glob</span></span>              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| <span data-ttu-id="2973d-128">Компилятор</span><span class="sxs-lookup"><span data-stu-id="2973d-128">Compile</span></span>           | <span data-ttu-id="2973d-129">\*\*/\*.cs (или другие расширения языка)</span><span class="sxs-lookup"><span data-stu-id="2973d-129">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="2973d-130">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="2973d-130">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="2973d-131">Н/Д</span><span class="sxs-lookup"><span data-stu-id="2973d-131">N/A</span></span>                      |
| <span data-ttu-id="2973d-132">ВнедренныйРесурс</span><span class="sxs-lookup"><span data-stu-id="2973d-132">EmbeddedResource</span></span>  | <span data-ttu-id="2973d-133">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="2973d-133">\*\*/\*.resx</span></span>                              | <span data-ttu-id="2973d-134">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="2973d-134">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="2973d-135">Н/Д</span><span class="sxs-lookup"><span data-stu-id="2973d-135">N/A</span></span>                      |
| <span data-ttu-id="2973d-136">Нет</span><span class="sxs-lookup"><span data-stu-id="2973d-136">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="2973d-137">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="2973d-137">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="2973d-138">\*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="2973d-138">\*\*/\*.cs; \*\*/\*.resx</span></span>   |

> [!NOTE]
> <span data-ttu-id="2973d-139">**Стандартная маска исключения** всегда исключает папки `./bin` и `./obj`, которые представлены свойствами MSBuild `$(BaseOutputPath)` и `$(BaseIntermediateOutputPath)` соответственно.</span><span class="sxs-lookup"><span data-stu-id="2973d-139">**Exclude glob** always excludes the `./bin` and `./obj` folders, which are represented by the `$(BaseOutputPath)` and `$(BaseIntermediateOutputPath)` MSBuild properties, respectively.</span></span> <span data-ttu-id="2973d-140">В целом все исключения представляются свойством `$(DefaultItemExcludes)`.</span><span class="sxs-lookup"><span data-stu-id="2973d-140">As a whole, all excludes are represented by `$(DefaultItemExcludes)`.</span></span>

<span data-ttu-id="2973d-141">Если в вашем проекте имеются стандартные маски и вы пытаетесь выполнить его сборку с помощью новейшего пакета SDK, появится следующая ошибка:</span><span class="sxs-lookup"><span data-stu-id="2973d-141">If you have globs in your project and you try to build it using the newest SDK, you'll get the following error:</span></span>

> <span data-ttu-id="2973d-142">Duplicate Compile items were included.</span><span class="sxs-lookup"><span data-stu-id="2973d-142">Duplicate Compile items were included.</span></span> <span data-ttu-id="2973d-143">The .NET SDK includes Compile items from your project directory by default.</span><span class="sxs-lookup"><span data-stu-id="2973d-143">The .NET SDK includes Compile items from your project directory by default.</span></span> <span data-ttu-id="2973d-144">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file. (Включены повторяющиеся элементы Compile. По умолчанию пакет SDK для .NET включает элементы Compile из каталога проекта. Можно удалить эти элементы из файла проекта или задать для свойства "EnableDefaultCompileItems" значение "false", чтобы явно включить их в файл проекта.)</span><span class="sxs-lookup"><span data-stu-id="2973d-144">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.</span></span>

<span data-ttu-id="2973d-145">Чтобы обойти эту ошибку, можно либо удалить явные элементы `Compile`, которые соответствуют указанным в предыдущей таблице, либо установить для свойства `<EnableDefaultCompileItems>` значение `false`, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="2973d-145">In order to get around this error, you can either remove the explicit `Compile` items that match the ones listed on the previous table, or you can set the `<EnableDefaultCompileItems>` property to `false`, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

<span data-ttu-id="2973d-146">Указание значения `false` для этого свойства отключает неявное включение, в результате чего возвращается поведение для предыдущих пакетов SDK, где требовалось задавать стандартные маски по умолчанию в проекте.</span><span class="sxs-lookup"><span data-stu-id="2973d-146">Setting this property to `false` will disable implicit inclusion, reverting to the behavior of previous SDKs where you had to specify the default globs in your project.</span></span>

<span data-ttu-id="2973d-147">Это изменение не затрагивает основные механизмы других включений.</span><span class="sxs-lookup"><span data-stu-id="2973d-147">This change does not modify the main mechanics of other includes.</span></span> <span data-ttu-id="2973d-148">Но если вы хотите указать, например, отдельные файлы для публикации вместе со своим приложением, для этого можно по-прежнему использовать привычные механизмы в *CSPROJ* (например, элемент `<Content>`).</span><span class="sxs-lookup"><span data-stu-id="2973d-148">However, if you wish to specify, for example, some files to get published with your app, you can still use the known mechanisms in *csproj* for that (for example, the `<Content>` element).</span></span>

<span data-ttu-id="2973d-149">`<EnableDefaultCompileItems>` отключает только стандартные маски `Compile`, не затрагивая все остальные, например неявную стандартную маску `None`, которая также применяется к элементам \*.cs.</span><span class="sxs-lookup"><span data-stu-id="2973d-149">`<EnableDefaultCompileItems>` only disables `Compile` globs but doesn't affect other globs, like the implicit `None` glob, which also applies to \*.cs items.</span></span> <span data-ttu-id="2973d-150">Из-за этого **обозреватель решений** продолжит показывать элементы \*.cs как часть проекта, включенную в виде элементов `None`.</span><span class="sxs-lookup"><span data-stu-id="2973d-150">Because of that, **Solution Explorer** will continue show \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="2973d-151">Аналогичным образом, можно задать `<EnableDefaultNoneItems>` как false для отключения неявной стандартной маски `None`:</span><span class="sxs-lookup"><span data-stu-id="2973d-151">In a similar way, you can set `<EnableDefaultNoneItems>` to false to disable the implicit `None` glob, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

<span data-ttu-id="2973d-152">Чтобы отключить **все неявные стандартные маски**, можно задать для свойства `<EnableDefaultItems>` значение `false`, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="2973d-152">To disable **all implicit globs**, you can set the `<EnableDefaultItems>` property to `false` as in the following example:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a><span data-ttu-id="2973d-153">Как просмотреть весь проект в представлении MSBuild</span><span class="sxs-lookup"><span data-stu-id="2973d-153">How to see the whole project as MSBuild sees it</span></span>

<span data-ttu-id="2973d-154">Хотя эти изменения csproj значительно упростили файлы проекта, возможно, вы захотите просмотреть полностью развернутый пакет в представлении MSBuild после включения пакета SDK и его целевых объектов.</span><span class="sxs-lookup"><span data-stu-id="2973d-154">While those csproj changes greatly simplify project files, you might want to see the fully expanded project as MSBuild sees it once the SDK and its targets are included.</span></span> <span data-ttu-id="2973d-155">Выполните предварительную обработку проекта, [включив](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) в команду [`dotnet msbuild`](dotnet-msbuild.md) параметр `/pp`. Это позволит просмотреть сведения об импортированных файлах, их источниках, вкладе в сборку без фактического создания проекта:</span><span class="sxs-lookup"><span data-stu-id="2973d-155">Preprocess the project with [the `/pp` switch](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) of the [`dotnet msbuild`](dotnet-msbuild.md) command, which shows which files are imported, their sources, and their contributions to the build without actually building the project:</span></span>

`dotnet msbuild -pp:fullproject.xml`

<span data-ttu-id="2973d-156">Если проект имеет несколько требуемых версий .NET Framework, результаты выполнения команды должны касаться только одной из них. Эту версию следует указать в качестве свойства MSBuild:</span><span class="sxs-lookup"><span data-stu-id="2973d-156">If the project has multiple target frameworks, the results of the command should be focused on only one of them by specifying it as an MSBuild property:</span></span>

`dotnet msbuild -p:TargetFramework=netcoreapp2.0 -pp:fullproject.xml`

## <a name="additions"></a><span data-ttu-id="2973d-157">Добавления</span><span class="sxs-lookup"><span data-stu-id="2973d-157">Additions</span></span>

### <a name="sdk-attribute"></a><span data-ttu-id="2973d-158">Атрибут Sdk</span><span class="sxs-lookup"><span data-stu-id="2973d-158">Sdk attribute</span></span>
<span data-ttu-id="2973d-159">Корневой элемент `<Project>` файла *CSPROJ* имеет новый атрибут `Sdk`.</span><span class="sxs-lookup"><span data-stu-id="2973d-159">The root `<Project>` element of the *.csproj* file has a new attribute called `Sdk`.</span></span> <span data-ttu-id="2973d-160">`Sdk` определяет, какой пакет SDK будет использоваться проектом.</span><span class="sxs-lookup"><span data-stu-id="2973d-160">`Sdk` specifies which SDK will be used by the project.</span></span> <span data-ttu-id="2973d-161">Пакет SDK, согласно описанию в [документе о слоях](cli-msbuild-architecture.md), является набором [задач](/visualstudio/msbuild/msbuild-tasks) и [целевых объектов](/visualstudio/msbuild/msbuild-targets) MSBuild, способным выполнять сборку кода .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2973d-161">The SDK, as the [layering document](cli-msbuild-architecture.md) describes, is a set of MSBuild [tasks](/visualstudio/msbuild/msbuild-tasks) and [targets](/visualstudio/msbuild/msbuild-targets) that can build .NET Core code.</span></span> <span data-ttu-id="2973d-162">Мы предоставляем три основных пакета SDK с инструментами для .NET Core:</span><span class="sxs-lookup"><span data-stu-id="2973d-162">We ship three main SDKs with the .NET Core tools:</span></span>

1. <span data-ttu-id="2973d-163">пакет SDK для .NET Core с идентификатором `Microsoft.NET.Sdk`;</span><span class="sxs-lookup"><span data-stu-id="2973d-163">The .NET Core SDK with the ID of `Microsoft.NET.Sdk`</span></span>
2. <span data-ttu-id="2973d-164">веб-пакет SDK для .NET Core с идентификатором `Microsoft.NET.Sdk.Web`.</span><span class="sxs-lookup"><span data-stu-id="2973d-164">The .NET Core web SDK with the ID of `Microsoft.NET.Sdk.Web`</span></span>
3. <span data-ttu-id="2973d-165">пакет SDK для библиотеки классов Razor для .NET Core с идентификатором `Microsoft.NET.Sdk.Razor`.</span><span class="sxs-lookup"><span data-stu-id="2973d-165">The .NET Core Razor Class Library SDK with the ID of `Microsoft.NET.Sdk.Razor`</span></span>

<span data-ttu-id="2973d-166">Чтобы использовать инструменты и выполнять сборку кода .NET Core, в качестве значения атрибута `Sdk` в элементе `<Project>` нужно задать один из этих идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="2973d-166">You need to have the `Sdk` attribute set to one of those IDs on the `<Project>` element in order to use the .NET Core tools and build your code.</span></span>

### <a name="packagereference"></a><span data-ttu-id="2973d-167">PackageReference</span><span class="sxs-lookup"><span data-stu-id="2973d-167">PackageReference</span></span>

<span data-ttu-id="2973d-168">Элемент `<PackageReference>` указывает [зависимость NuGet в проекте](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="2973d-168">A `<PackageReference>` item element specifies a [NuGet dependency in the project](/nuget/consume-packages/package-references-in-project-files).</span></span> <span data-ttu-id="2973d-169">Атрибут `Include` указывает идентификатор пакета.</span><span class="sxs-lookup"><span data-stu-id="2973d-169">The `Include` attribute specifies the package ID.</span></span>

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a><span data-ttu-id="2973d-170">Версия</span><span class="sxs-lookup"><span data-stu-id="2973d-170">Version</span></span>

<span data-ttu-id="2973d-171">Обязательный атрибут `Version` указывает версию пакета для восстановления.</span><span class="sxs-lookup"><span data-stu-id="2973d-171">The required `Version` attribute specifies the version of the package to restore.</span></span> <span data-ttu-id="2973d-172">Этот атрибут подчиняется правилам схемы [управления версиями NuGet](/nuget/reference/package-versioning#version-ranges-and-wildcards).</span><span class="sxs-lookup"><span data-stu-id="2973d-172">The attribute respects the rules of the [NuGet versioning](/nuget/reference/package-versioning#version-ranges-and-wildcards) scheme.</span></span> <span data-ttu-id="2973d-173">По умолчанию выбирается точное соответствие версии.</span><span class="sxs-lookup"><span data-stu-id="2973d-173">The default behavior is an exact version match.</span></span> <span data-ttu-id="2973d-174">Например, если указать `Version="1.2.3"`, это будет эквивалентно нотации NuGet `[1.2.3]` для точного указания версии 1.2.3 пакета.</span><span class="sxs-lookup"><span data-stu-id="2973d-174">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

#### <a name="includeassets-excludeassets-and-privateassets"></a><span data-ttu-id="2973d-175">IncludeAssets, ExcludeAssets и PrivateAssets</span><span class="sxs-lookup"><span data-stu-id="2973d-175">IncludeAssets, ExcludeAssets and PrivateAssets</span></span>

<span data-ttu-id="2973d-176">Атрибут `IncludeAssets` указывает, какие ресурсы пакета, указанные `<PackageReference>`, следует использовать.</span><span class="sxs-lookup"><span data-stu-id="2973d-176">`IncludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed.</span></span> <span data-ttu-id="2973d-177">По умолчанию включаются все ресурсы пакета.</span><span class="sxs-lookup"><span data-stu-id="2973d-177">By default, all package assets are included.</span></span>

<span data-ttu-id="2973d-178">Атрибут `ExcludeAssets` указывает, какие ресурсы пакета, указанные `<PackageReference>`, не следует использовать.</span><span class="sxs-lookup"><span data-stu-id="2973d-178">`ExcludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should not be consumed.</span></span>

<span data-ttu-id="2973d-179">Атрибут `PrivateAssets` указывает, какие ресурсы пакета, указанные `<PackageReference>`, следует использовать, но не следует передавать в следующий проект.</span><span class="sxs-lookup"><span data-stu-id="2973d-179">`PrivateAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed but not flow to the next project.</span></span> <span data-ttu-id="2973d-180">Если этот атрибут отсутствует, ресурсы `Analyzers`, `Build` и `ContentFiles` по умолчанию являются частными.</span><span class="sxs-lookup"><span data-stu-id="2973d-180">The `Analyzers`, `Build` and `ContentFiles` assets are private by default when this attribute is not present.</span></span>

> [!NOTE]
> <span data-ttu-id="2973d-181">`PrivateAssets` эквивалентен элементу *project.json*/*xproj* `SuppressParent`.</span><span class="sxs-lookup"><span data-stu-id="2973d-181">`PrivateAssets` is equivalent to the *project.json*/*xproj* `SuppressParent` element.</span></span>

<span data-ttu-id="2973d-182">Эти атрибуты могут содержать один или несколько следующих элементов (если их больше одного, они разделяются точкой с запятой `;`):</span><span class="sxs-lookup"><span data-stu-id="2973d-182">These attributes can contain one or more of the following items, separated by the semicolon `;` character if more than one is listed:</span></span>

* <span data-ttu-id="2973d-183">`Compile` — содержимое папки lib доступно для компиляции.</span><span class="sxs-lookup"><span data-stu-id="2973d-183">`Compile` – the contents of the lib folder are available to compile against.</span></span>
* <span data-ttu-id="2973d-184">`Runtime` — содержимое папки среды выполнения распределяется.</span><span class="sxs-lookup"><span data-stu-id="2973d-184">`Runtime` – the contents of the runtime folder are distributed.</span></span>
* <span data-ttu-id="2973d-185">`ContentFiles` — используется содержимое папки *contentfiles*.</span><span class="sxs-lookup"><span data-stu-id="2973d-185">`ContentFiles` – the contents of the *contentfiles* folder are used.</span></span>
* <span data-ttu-id="2973d-186">`Build` — используются свойства и целевые объекты в папке сборки.</span><span class="sxs-lookup"><span data-stu-id="2973d-186">`Build` – the props/targets in the build folder are used.</span></span>
* <span data-ttu-id="2973d-187">`Native` — содержимое копируется из основных ресурсов в папку выходных данных среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2973d-187">`Native` – the contents from native assets are copied to the output folder for runtime.</span></span>
* <span data-ttu-id="2973d-188">`Analyzers` — используются анализаторы.</span><span class="sxs-lookup"><span data-stu-id="2973d-188">`Analyzers` – the analyzers are used.</span></span>

<span data-ttu-id="2973d-189">Кроме того, атрибут может содержать следующие значения.</span><span class="sxs-lookup"><span data-stu-id="2973d-189">Alternatively, the attribute can contain:</span></span>

* <span data-ttu-id="2973d-190">`None` — не используется ни один ресурс.</span><span class="sxs-lookup"><span data-stu-id="2973d-190">`None` – none of the assets are used.</span></span>
* <span data-ttu-id="2973d-191">`All` — используются все ресурсы.</span><span class="sxs-lookup"><span data-stu-id="2973d-191">`All` – all assets are used.</span></span>

### <a name="dotnetclitoolreference"></a><span data-ttu-id="2973d-192">DotNetCliToolReference</span><span class="sxs-lookup"><span data-stu-id="2973d-192">DotNetCliToolReference</span></span>
<span data-ttu-id="2973d-193">Элемент `<DotNetCliToolReference>` указывает средство интерфейса командной строки, которое пользователь хочет восстановить в контексте проекта.</span><span class="sxs-lookup"><span data-stu-id="2973d-193">A `<DotNetCliToolReference>` item element specifies the CLI tool that the user wants to restore in the context of the project.</span></span> <span data-ttu-id="2973d-194">Этот элемент используется вместо узла `tools` в файле *project.json*.</span><span class="sxs-lookup"><span data-stu-id="2973d-194">It's a replacement for the `tools` node in *project.json*.</span></span>

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

#### <a name="version"></a><span data-ttu-id="2973d-195">Версия</span><span class="sxs-lookup"><span data-stu-id="2973d-195">Version</span></span>

<span data-ttu-id="2973d-196">`Version` указывает версию пакета для восстановления.</span><span class="sxs-lookup"><span data-stu-id="2973d-196">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="2973d-197">Этот атрибут подчиняется правилам схемы [управления версиями NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="2973d-197">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="2973d-198">По умолчанию выбирается точное соответствие версии.</span><span class="sxs-lookup"><span data-stu-id="2973d-198">The default behavior is an exact version match.</span></span> <span data-ttu-id="2973d-199">Например, если указать `Version="1.2.3"`, это будет эквивалентно нотации NuGet `[1.2.3]` для точного указания версии 1.2.3 пакета.</span><span class="sxs-lookup"><span data-stu-id="2973d-199">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

### <a name="runtimeidentifiers"></a><span data-ttu-id="2973d-200">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="2973d-200">RuntimeIdentifiers</span></span>

<span data-ttu-id="2973d-201">Элемент свойства `<RuntimeIdentifiers>` позволяет указать для проекта список [идентификаторов среды выполнения (RID)](../rid-catalog.md) (в качестве разделителя используется точка с запятой).</span><span class="sxs-lookup"><span data-stu-id="2973d-201">The `<RuntimeIdentifiers>` property element lets you specify a semicolon-delimited list of [Runtime Identifiers (RIDs)](../rid-catalog.md) for the project.</span></span>
<span data-ttu-id="2973d-202">Идентификаторы позволяют публиковать автономные развертывания.</span><span class="sxs-lookup"><span data-stu-id="2973d-202">RIDs enable publishing self-contained deployments.</span></span>

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a><span data-ttu-id="2973d-203">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="2973d-203">RuntimeIdentifier</span></span>

<span data-ttu-id="2973d-204">Элемент свойства `<RuntimeIdentifier>` позволяет указать для проекта только один [идентификатор среды выполнения](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="2973d-204">The `<RuntimeIdentifier>` property element allows you to specify only one [Runtime Identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="2973d-205">Идентификатор среды выполнения позволяет опубликовать автономное развертывание.</span><span class="sxs-lookup"><span data-stu-id="2973d-205">The RID enables publishing a self-contained deployment.</span></span>

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

<span data-ttu-id="2973d-206">Используйте `<RuntimeIdentifiers>` (во множественном числе) вместо этого, если вам нужна публикация для различных сред.</span><span class="sxs-lookup"><span data-stu-id="2973d-206">Use `<RuntimeIdentifiers>` (plural) instead if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="2973d-207">`<RuntimeIdentifier>` может ускорить создание сборок, когда требуется только одна среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="2973d-207">`<RuntimeIdentifier>` can provide faster builds when only a single runtime is required.</span></span>

### <a name="packagetargetfallback"></a><span data-ttu-id="2973d-208">PackageTargetFallback</span><span class="sxs-lookup"><span data-stu-id="2973d-208">PackageTargetFallback</span></span>

<span data-ttu-id="2973d-209">Элемент свойства `<PackageTargetFallback>` позволяет указать набор совместимых целевых объектов, которые следует использовать при восстановлении пакетов.</span><span class="sxs-lookup"><span data-stu-id="2973d-209">The `<PackageTargetFallback>` property element allows you to specify a set of compatible targets to be used when restoring packages.</span></span> <span data-ttu-id="2973d-210">Он разрешает пакетам, использующим dotnet [TxM (моникер целевой версии x)](/nuget/schema/target-frameworks), взаимодействовать с пакетами, которые не объявляют dotnet TxM.</span><span class="sxs-lookup"><span data-stu-id="2973d-210">It's designed to allow packages that use the dotnet [TxM (Target x Moniker)](/nuget/schema/target-frameworks) to operate with packages that don't declare a dotnet TxM.</span></span> <span data-ttu-id="2973d-211">Если в проекте используется dotnet TxM, все пакеты, от которых вы зависите, должны также содержать dotnet TxM. В противном случае нужно добавить `<PackageTargetFallback>` в проект, чтобы обеспечить совместимость с платформами, отличными от dotnet.</span><span class="sxs-lookup"><span data-stu-id="2973d-211">If your project uses the dotnet TxM, then all the packages it depends on must also have a dotnet TxM, unless you add the `<PackageTargetFallback>` to your project in order to allow non-dotnet platforms to be compatible with dotnet.</span></span>

<span data-ttu-id="2973d-212">В следующем примере приводятся резервные варианты для всех целевых объектов в проекте:</span><span class="sxs-lookup"><span data-stu-id="2973d-212">The following example provides the fallbacks for all targets in your project:</span></span>

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

<span data-ttu-id="2973d-213">В следующем примере приводятся резервные варианты только для целевого объекта `netcoreapp2.1`:</span><span class="sxs-lookup"><span data-stu-id="2973d-213">The following example specifies the fallbacks only for the `netcoreapp2.1` target:</span></span>

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp2.1'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="nuget-metadata-properties"></a><span data-ttu-id="2973d-214">Свойства метаданных NuGet</span><span class="sxs-lookup"><span data-stu-id="2973d-214">NuGet metadata properties</span></span>

<span data-ttu-id="2973d-215">При переходе к MSBuild мы переместили входные метаданные, которые использовались при упаковке пакета NuGet из *project.json* в файлы *CSPROJ*.</span><span class="sxs-lookup"><span data-stu-id="2973d-215">With the move to MSBuild, we have moved the input metadata that is used when packing a NuGet package from *project.json* to *.csproj* files.</span></span> <span data-ttu-id="2973d-216">Входными данными являются свойства MSBuild, поэтому они должны входить в группу `<PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="2973d-216">The inputs are MSBuild properties so they have to go within a `<PropertyGroup>` group.</span></span> <span data-ttu-id="2973d-217">Ниже представлен список свойств, которые используются как входные данные в процессе упаковки при использовании команды `dotnet pack` или целевого объекта `Pack` MSBuild, входящего в SDK.</span><span class="sxs-lookup"><span data-stu-id="2973d-217">The following is the list of properties that are used as inputs to the packing process when using the `dotnet pack` command or the `Pack` MSBuild target that is part of the SDK.</span></span>

### <a name="ispackable"></a><span data-ttu-id="2973d-218">IsPackable</span><span class="sxs-lookup"><span data-stu-id="2973d-218">IsPackable</span></span>

<span data-ttu-id="2973d-219">Логическое значение, которое указывает, можно ли упаковать проект.</span><span class="sxs-lookup"><span data-stu-id="2973d-219">A Boolean value that specifies whether the project can be packed.</span></span> <span data-ttu-id="2973d-220">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="2973d-220">The default value is `true`.</span></span>

### <a name="packageversion"></a><span data-ttu-id="2973d-221">PackageVersion</span><span class="sxs-lookup"><span data-stu-id="2973d-221">PackageVersion</span></span>

<span data-ttu-id="2973d-222">Указывает версию, которую будет иметь итоговый пакет.</span><span class="sxs-lookup"><span data-stu-id="2973d-222">Specifies the version that the resulting package will have.</span></span> <span data-ttu-id="2973d-223">Принимает все формы строки версии NuGet.</span><span class="sxs-lookup"><span data-stu-id="2973d-223">Accepts all forms of NuGet version string.</span></span> <span data-ttu-id="2973d-224">По умолчанию используется значение `$(Version)`, то есть значение свойства `Version` в проекте.</span><span class="sxs-lookup"><span data-stu-id="2973d-224">Default is the value of `$(Version)`, that is, of the property `Version` in the project.</span></span>

### <a name="packageid"></a><span data-ttu-id="2973d-225">PackageId</span><span class="sxs-lookup"><span data-stu-id="2973d-225">PackageId</span></span>

<span data-ttu-id="2973d-226">Указывает имя для итогового пакета.</span><span class="sxs-lookup"><span data-stu-id="2973d-226">Specifies the name for the resulting package.</span></span> <span data-ttu-id="2973d-227">Если значение не указано, операция `pack` по умолчанию использует в качестве имени пакета `AssemblyName` или имя каталога.</span><span class="sxs-lookup"><span data-stu-id="2973d-227">If not specified, the `pack` operation will default to using the `AssemblyName` or directory name as the name of the package.</span></span>

### <a name="title"></a><span data-ttu-id="2973d-228">Заголовок</span><span class="sxs-lookup"><span data-stu-id="2973d-228">Title</span></span>

<span data-ttu-id="2973d-229">Понятный заголовок пакета, обычно используемый при отображении пользовательского интерфейса, как на сайте nuget.org и в диспетчере пакетов Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2973d-229">A human-friendly title of the package, typically used in UI displays as on nuget.org and the Package Manager in Visual Studio.</span></span> <span data-ttu-id="2973d-230">Если значение не указано, используется идентификатор пакета.</span><span class="sxs-lookup"><span data-stu-id="2973d-230">If not specified, the package ID is used instead.</span></span>

### <a name="authors"></a><span data-ttu-id="2973d-231">Authors</span><span class="sxs-lookup"><span data-stu-id="2973d-231">Authors</span></span>

<span data-ttu-id="2973d-232">Разделенный точками с запятой список авторов пакетов, совпадающих с именами профилей на сайте nuget.org. Они отображаются в коллекции NuGet на сайте nuget.org и используются для перекрестных ссылок на пакеты тех же авторов.</span><span class="sxs-lookup"><span data-stu-id="2973d-232">A semicolon-separated list of packages authors, matching the profile names on nuget.org. These are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span>

### <a name="packagedescription"></a><span data-ttu-id="2973d-233">PackageDescription</span><span class="sxs-lookup"><span data-stu-id="2973d-233">PackageDescription</span></span>

<span data-ttu-id="2973d-234">Подробное описание пакета для отображения пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="2973d-234">A long description of the package for UI display.</span></span>

### <a name="description"></a><span data-ttu-id="2973d-235">Описание</span><span class="sxs-lookup"><span data-stu-id="2973d-235">Description</span></span>

<span data-ttu-id="2973d-236">Подробное описание сборки.</span><span class="sxs-lookup"><span data-stu-id="2973d-236">A long description for the assembly.</span></span> <span data-ttu-id="2973d-237">Если `PackageDescription` не указывать, это свойство также будет использоваться в качестве описания пакета.</span><span class="sxs-lookup"><span data-stu-id="2973d-237">If `PackageDescription` is not specified then this property is also used as the description of the package.</span></span>

### <a name="copyright"></a><span data-ttu-id="2973d-238">Copyright</span><span class="sxs-lookup"><span data-stu-id="2973d-238">Copyright</span></span>

<span data-ttu-id="2973d-239">Сведения об авторских правах для пакета.</span><span class="sxs-lookup"><span data-stu-id="2973d-239">Copyright details for the package.</span></span>

### <a name="packagerequirelicenseacceptance"></a><span data-ttu-id="2973d-240">PackageRequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="2973d-240">PackageRequireLicenseAcceptance</span></span>

<span data-ttu-id="2973d-241">Логическое значение, указывающее, должен ли клиент просить потребителя принять условия лицензии перед установкой пакета.</span><span class="sxs-lookup"><span data-stu-id="2973d-241">A Boolean value that specifies whether the client must prompt the consumer to accept the package license before installing the package.</span></span> <span data-ttu-id="2973d-242">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="2973d-242">The default is `false`.</span></span>

### <a name="packagelicenseexpression"></a><span data-ttu-id="2973d-243">PackageLicenseExpression</span><span class="sxs-lookup"><span data-stu-id="2973d-243">PackageLicenseExpression</span></span>

<span data-ttu-id="2973d-244">[Идентификатор лицензии SPDX](https://spdx.org/licenses/) или выражение.</span><span class="sxs-lookup"><span data-stu-id="2973d-244">An [SPDX license identifier](https://spdx.org/licenses/) or expression.</span></span> <span data-ttu-id="2973d-245">Например, `Apache-2.0`.</span><span class="sxs-lookup"><span data-stu-id="2973d-245">For example, `Apache-2.0`.</span></span>

<span data-ttu-id="2973d-246">Здесь приведен полный список [идентификаторов лицензии SPDX](https://spdx.org/licenses/).</span><span class="sxs-lookup"><span data-stu-id="2973d-246">Here is the complete list of [SPDX license identifiers](https://spdx.org/licenses/).</span></span> <span data-ttu-id="2973d-247">Если используется выражение типа лицензии, NuGet.org принимает только утвержденные OSI или FSF лицензии.</span><span class="sxs-lookup"><span data-stu-id="2973d-247">NuGet.org accepts only OSI or FSF approved licenses when using license type expression.</span></span>

<span data-ttu-id="2973d-248">Точный синтаксис выражений лицензии описан ниже в спецификации метаязыка [ABNF](https://tools.ietf.org/html/rfc5234).</span><span class="sxs-lookup"><span data-stu-id="2973d-248">The exact syntax of the license expressions is described below in [ABNF](https://tools.ietf.org/html/rfc5234).</span></span>

```cli
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
> <span data-ttu-id="2973d-249">За один раз можно указать только одно из свойств `PackageLicenseExpression`, `PackageLicenseFile` и `PackageLicenseUrl`.</span><span class="sxs-lookup"><span data-stu-id="2973d-249">Only one of `PackageLicenseExpression`, `PackageLicenseFile` and `PackageLicenseUrl` can be specified at a time.</span></span>

### <a name="packagelicensefile"></a><span data-ttu-id="2973d-250">PackageLicenseFile</span><span class="sxs-lookup"><span data-stu-id="2973d-250">PackageLicenseFile</span></span>

<span data-ttu-id="2973d-251">Путь к файлу лицензии в пакете, если вы используете лицензию, которой не назначен идентификатор SPDX, или пользовательскую лицензию (в противном случае предпочтительнее использовать свойство `PackageLicenseExpression`).</span><span class="sxs-lookup"><span data-stu-id="2973d-251">Path to a license file within the package if you are using a license that hasn’t been assigned an SPDX identifier, or it is a custom license (Otherwise `PackageLicenseExpression` is prefered)</span></span>

<span data-ttu-id="2973d-252">Заменяет свойство `PackageLicenseUrl`, не может сочетаться со свойством `PackageLicenseExpression`. Требуется Visual Studio версии 15.9.4, пакет SDK для .NET 2.1.502, 2.2.101 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="2973d-252">Replaces `PackageLicenseUrl`, can't be combined with `PackageLicenseExpression` and requires Visual Studio 15.9.4, .NET SDK 2.1.502 or 2.2.101, or newer.</span></span>

<span data-ttu-id="2973d-253">Вам необходимо убедиться, что файл лицензии упакован. Для этого явно добавьте его в проект. Пример использования:</span><span class="sxs-lookup"><span data-stu-id="2973d-253">You will need to ensure the license file is packed by adding it explicitly to the project, example usage:</span></span>

```xml
<PropertyGroup>
  <PackageLicenseFile>LICENSE.txt</PackageLicenseFile>
</PropertyGroup>
<ItemGroup>
  <None Include="licenses\LICENSE.txt" Pack="true" PackagePath="$(PackageLicenseFile)"/>
</ItemGroup>
```

### <a name="packagelicenseurl"></a><span data-ttu-id="2973d-254">PackageLicenseUrl</span><span class="sxs-lookup"><span data-stu-id="2973d-254">PackageLicenseUrl</span></span>

<span data-ttu-id="2973d-255">URL-адрес лицензии, применимой к пакету.</span><span class="sxs-lookup"><span data-stu-id="2973d-255">An URL to the license that is applicable to the package.</span></span> <span data-ttu-id="2973d-256">(_Отмечено как нерекомендуемое начиная с Visual Studio версии 15.9.4, пакета SDK для .NET 2.1.502 и 2.2.101._)</span><span class="sxs-lookup"><span data-stu-id="2973d-256">(_deprecated since Visual Studio 15.9.4, .NET SDK 2.1.502 and 2.2.101_)</span></span>


### <a name="packageiconurl"></a><span data-ttu-id="2973d-257">PackageIconUrl</span><span class="sxs-lookup"><span data-stu-id="2973d-257">PackageIconUrl</span></span>

<span data-ttu-id="2973d-258">URL-адрес для изображения размером 64x64 с прозрачным фоном, используемого в качестве значка для пакета при отображении пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="2973d-258">A URL for a 64x64 image with transparent background to use as the icon for the package in UI display.</span></span>

### <a name="packagereleasenotes"></a><span data-ttu-id="2973d-259">PackageReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="2973d-259">PackageReleaseNotes</span></span>

<span data-ttu-id="2973d-260">Заметки о выпуске для пакета.</span><span class="sxs-lookup"><span data-stu-id="2973d-260">Release notes for the package.</span></span>

### <a name="packagetags"></a><span data-ttu-id="2973d-261">PackageTags</span><span class="sxs-lookup"><span data-stu-id="2973d-261">PackageTags</span></span>

<span data-ttu-id="2973d-262">Разделенный точками с запятой список тегов, обозначающий пакет.</span><span class="sxs-lookup"><span data-stu-id="2973d-262">A semicolon-delimited list of tags that designates the package.</span></span>

### <a name="packageoutputpath"></a><span data-ttu-id="2973d-263">PackageOutputPath</span><span class="sxs-lookup"><span data-stu-id="2973d-263">PackageOutputPath</span></span>

<span data-ttu-id="2973d-264">Определяет выходной путь для размещения упакованного пакета.</span><span class="sxs-lookup"><span data-stu-id="2973d-264">Determines the output path in which the packed package will be dropped.</span></span> <span data-ttu-id="2973d-265">Значение по умолчанию — `$(OutputPath)`.</span><span class="sxs-lookup"><span data-stu-id="2973d-265">Default is `$(OutputPath)`.</span></span>

### <a name="includesymbols"></a><span data-ttu-id="2973d-266">IncludeSymbols</span><span class="sxs-lookup"><span data-stu-id="2973d-266">IncludeSymbols</span></span>

<span data-ttu-id="2973d-267">Это логическое значение указывает, должен ли пакет создавать дополнительный пакет символов при упаковке проекта.</span><span class="sxs-lookup"><span data-stu-id="2973d-267">This Boolean value indicates whether the package should create an additional symbols package when the project is packed.</span></span> <span data-ttu-id="2973d-268">Этот пакет будет иметь расширение *.symbols.nupkg* и копировать PDB-файлы, а также библиотеки DLL и другие выходные файлы.</span><span class="sxs-lookup"><span data-stu-id="2973d-268">This package will have a *.symbols.nupkg* extension and will copy the PDB files along with the DLL and other output files.</span></span>

### <a name="includesource"></a><span data-ttu-id="2973d-269">IncludeSource</span><span class="sxs-lookup"><span data-stu-id="2973d-269">IncludeSource</span></span>

<span data-ttu-id="2973d-270">Это логическое значение указывает, должен ли процесс упаковки создавать исходный пакет.</span><span class="sxs-lookup"><span data-stu-id="2973d-270">This Boolean value indicates whether the pack process should create a source package.</span></span> <span data-ttu-id="2973d-271">Исходный пакет содержит библиотеку исходного кода, а также файлы PDB.</span><span class="sxs-lookup"><span data-stu-id="2973d-271">The source package contains the library's source code as well as PDB files.</span></span> <span data-ttu-id="2973d-272">Исходные файлы помещаются в каталог `src/ProjectName` итогового файла пакета.</span><span class="sxs-lookup"><span data-stu-id="2973d-272">Source files are put under the `src/ProjectName` directory in the resulting package file.</span></span>

### <a name="istool"></a><span data-ttu-id="2973d-273">IsTool</span><span class="sxs-lookup"><span data-stu-id="2973d-273">IsTool</span></span>

<span data-ttu-id="2973d-274">Указывает, копируются ли все выходные файлы в папку *tools* вместо папки *lib*.</span><span class="sxs-lookup"><span data-stu-id="2973d-274">Specifies whether all output files are copied to the *tools* folder instead of the *lib* folder.</span></span> <span data-ttu-id="2973d-275">Обратите внимание, что это свойство отличается от `DotNetCliTool`, которое указывается путем задания `PackageType` в файле *CSPROJ*.</span><span class="sxs-lookup"><span data-stu-id="2973d-275">Note that this is different from a `DotNetCliTool` which is specified by setting the `PackageType` in the *.csproj* file.</span></span>

### <a name="repositoryurl"></a><span data-ttu-id="2973d-276">RepositoryUrl</span><span class="sxs-lookup"><span data-stu-id="2973d-276">RepositoryUrl</span></span>

<span data-ttu-id="2973d-277">Указывает URL-адрес репозитория, где находится исходный код для пакета или откуда выполняется его сборка.</span><span class="sxs-lookup"><span data-stu-id="2973d-277">Specifies the URL for the repository where the source code for the package resides and/or from which it's being built.</span></span>

### <a name="repositorytype"></a><span data-ttu-id="2973d-278">RepositoryType</span><span class="sxs-lookup"><span data-stu-id="2973d-278">RepositoryType</span></span>

<span data-ttu-id="2973d-279">Указывает тип репозитория.</span><span class="sxs-lookup"><span data-stu-id="2973d-279">Specifies the type of the repository.</span></span> <span data-ttu-id="2973d-280">Значение по умолчанию — "git".</span><span class="sxs-lookup"><span data-stu-id="2973d-280">Default is "git".</span></span>

### <a name="nopackageanalysis"></a><span data-ttu-id="2973d-281">NoPackageAnalysis</span><span class="sxs-lookup"><span data-stu-id="2973d-281">NoPackageAnalysis</span></span>

<span data-ttu-id="2973d-282">Указывает, что пакету не нужно запускать анализ пакета после его сборки.</span><span class="sxs-lookup"><span data-stu-id="2973d-282">Specifies that pack should not run package analysis after building the package.</span></span>

### <a name="minclientversion"></a><span data-ttu-id="2973d-283">MinClientVersion</span><span class="sxs-lookup"><span data-stu-id="2973d-283">MinClientVersion</span></span>

<span data-ttu-id="2973d-284">Указывает минимальную версию клиента NuGet, который может установить этот пакет с использованием nuget.exe и диспетчера пакетов Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2973d-284">Specifies the minimum version of the NuGet client that can install this package, enforced by nuget.exe and the Visual Studio Package Manager.</span></span>

### <a name="includebuildoutput"></a><span data-ttu-id="2973d-285">IncludeBuildOutput</span><span class="sxs-lookup"><span data-stu-id="2973d-285">IncludeBuildOutput</span></span>

<span data-ttu-id="2973d-286">Это логическое значение указывает, следует ли упаковывать выходные сборки в файл *NUPKG*.</span><span class="sxs-lookup"><span data-stu-id="2973d-286">This Boolean values specifies whether the build output assemblies should be packed into the *.nupkg* file or not.</span></span>

### <a name="includecontentinpack"></a><span data-ttu-id="2973d-287">IncludeContentInPack</span><span class="sxs-lookup"><span data-stu-id="2973d-287">IncludeContentInPack</span></span>

<span data-ttu-id="2973d-288">Это логическое значение указывает, будут ли все элементы, имеющие тип `Content`, автоматически включены в итоговый пакет.</span><span class="sxs-lookup"><span data-stu-id="2973d-288">This Boolean value specifies whether any items that have a type of `Content` will be included in the resulting package automatically.</span></span> <span data-ttu-id="2973d-289">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="2973d-289">The default is `true`.</span></span>

### <a name="buildoutputtargetfolder"></a><span data-ttu-id="2973d-290">BuildOutputTargetFolder</span><span class="sxs-lookup"><span data-stu-id="2973d-290">BuildOutputTargetFolder</span></span>

<span data-ttu-id="2973d-291">Указывает папку для размещения выходных сборок.</span><span class="sxs-lookup"><span data-stu-id="2973d-291">Specifies the folder where to place the output assemblies.</span></span> <span data-ttu-id="2973d-292">Выходные сборки (и другие выходные файлы) копируются в соответствующие папки платформы.</span><span class="sxs-lookup"><span data-stu-id="2973d-292">The output assemblies (and other output files) are copied into their respective framework folders.</span></span>

### <a name="contenttargetfolders"></a><span data-ttu-id="2973d-293">ContentTargetFolders</span><span class="sxs-lookup"><span data-stu-id="2973d-293">ContentTargetFolders</span></span>

<span data-ttu-id="2973d-294">Это свойство указывает расположение по умолчанию, куда следует помещать все файлы содержимого, для которых не указан `PackagePath`.</span><span class="sxs-lookup"><span data-stu-id="2973d-294">This property specifies the default location of where all the content files should go if `PackagePath` is not specified for them.</span></span> <span data-ttu-id="2973d-295">Значение по умолчанию — "content;contentFiles".</span><span class="sxs-lookup"><span data-stu-id="2973d-295">The default value is "content;contentFiles".</span></span>

### <a name="nuspecfile"></a><span data-ttu-id="2973d-296">NuspecFile</span><span class="sxs-lookup"><span data-stu-id="2973d-296">NuspecFile</span></span>

<span data-ttu-id="2973d-297">Относительный или абсолютный путь к файлу *NUSPEC*, используемому для упаковки.</span><span class="sxs-lookup"><span data-stu-id="2973d-297">Relative or absolute path to the *.nuspec* file being used for packing.</span></span>

> [!NOTE]
> <span data-ttu-id="2973d-298">Если файл *NUSPEC* указан, он используется для упаковки в **монопольном порядке**, а любые сведения в проектах не используются.</span><span class="sxs-lookup"><span data-stu-id="2973d-298">If the *.nuspec* file is specified, it's used **exclusively** for packaging information and any information in the projects is not used.</span></span>

### <a name="nuspecbasepath"></a><span data-ttu-id="2973d-299">NuspecBasePath</span><span class="sxs-lookup"><span data-stu-id="2973d-299">NuspecBasePath</span></span>

<span data-ttu-id="2973d-300">Базовый путь для файла *NUSPEC*.</span><span class="sxs-lookup"><span data-stu-id="2973d-300">Base path for the *.nuspec* file.</span></span>

### <a name="nuspecproperties"></a><span data-ttu-id="2973d-301">NuspecProperties</span><span class="sxs-lookup"><span data-stu-id="2973d-301">NuspecProperties</span></span>

<span data-ttu-id="2973d-302">Список разделенных точками с запятой пар "ключ-значение".</span><span class="sxs-lookup"><span data-stu-id="2973d-302">Semicolon separated list of key=value pairs.</span></span>

## <a name="assemblyinfo-properties"></a><span data-ttu-id="2973d-303">Свойства AssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="2973d-303">AssemblyInfo properties</span></span>

<span data-ttu-id="2973d-304">[Атрибуты сборки](../../framework/app-domains/set-assembly-attributes.md), которые обычно содержатся в файле *AssemblyInfo*, теперь автоматически создаются на основе свойств.</span><span class="sxs-lookup"><span data-stu-id="2973d-304">[Assembly attributes](../../framework/app-domains/set-assembly-attributes.md) that were typically present in an *AssemblyInfo* file are now automatically generated from properties.</span></span>

### <a name="properties-per-attribute"></a><span data-ttu-id="2973d-305">Свойства каждого атрибута</span><span class="sxs-lookup"><span data-stu-id="2973d-305">Properties per attribute</span></span>

<span data-ttu-id="2973d-306">Каждый атрибут имеет свойства, одно из которых позволяет управлять содержимым атрибута, а другое — отключить создание атрибута, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="2973d-306">Each attribute has a property that control its content and another to disable its generation as shown in the following table:</span></span>

| <span data-ttu-id="2973d-307">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2973d-307">Attribute</span></span>                                                      | <span data-ttu-id="2973d-308">Свойство.</span><span class="sxs-lookup"><span data-stu-id="2973d-308">Property</span></span>               | <span data-ttu-id="2973d-309">Свойство, используемое для отключения</span><span class="sxs-lookup"><span data-stu-id="2973d-309">Property to disable</span></span>                             |
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

<span data-ttu-id="2973d-310">Примечания.</span><span class="sxs-lookup"><span data-stu-id="2973d-310">Notes:</span></span>

* <span data-ttu-id="2973d-311">`AssemblyVersion` и `FileVersion` по умолчанию имеют значение `$(Version)` без суффикса.</span><span class="sxs-lookup"><span data-stu-id="2973d-311">`AssemblyVersion` and `FileVersion` default is to take the value of `$(Version)` without suffix.</span></span> <span data-ttu-id="2973d-312">Например, если для `$(Version)` нужно указать `1.2.3-beta.4`, то значением будет `1.2.3`.</span><span class="sxs-lookup"><span data-stu-id="2973d-312">For example, if `$(Version)` is `1.2.3-beta.4`, then the value would be `1.2.3`.</span></span>
* <span data-ttu-id="2973d-313">По умолчанию для `InformationalVersion` используется значение `$(Version)`.</span><span class="sxs-lookup"><span data-stu-id="2973d-313">`InformationalVersion` defaults to the value of `$(Version)`.</span></span>
* <span data-ttu-id="2973d-314">`InformationalVersion` имеет значение `$(SourceRevisionId)`, которое добавляется, если указано свойство.</span><span class="sxs-lookup"><span data-stu-id="2973d-314">`InformationalVersion` has `$(SourceRevisionId)` appended if the property is present.</span></span> <span data-ttu-id="2973d-315">Его можно отключить с помощью `IncludeSourceRevisionInInformationalVersion`.</span><span class="sxs-lookup"><span data-stu-id="2973d-315">It can be disabled using `IncludeSourceRevisionInInformationalVersion`.</span></span>
* <span data-ttu-id="2973d-316">Свойства `Copyright` и `Description` также используются для метаданных NuGet.</span><span class="sxs-lookup"><span data-stu-id="2973d-316">`Copyright` and `Description` properties are also used for NuGet metadata.</span></span>
* <span data-ttu-id="2973d-317">Свойство `Configuration` является общим для всего процесса сборки, и задается с помощью параметра `--configuration` команд `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="2973d-317">`Configuration` is shared with all the build process and set via the `--configuration` parameter of `dotnet` commands.</span></span>

### <a name="generateassemblyinfo"></a><span data-ttu-id="2973d-318">GenerateAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="2973d-318">GenerateAssemblyInfo</span></span>

<span data-ttu-id="2973d-319">Логическое свойство, которое позволяет включить или отключить создание всех свойств AssemblyInfo.</span><span class="sxs-lookup"><span data-stu-id="2973d-319">A Boolean that enable or disable all the AssemblyInfo generation.</span></span> <span data-ttu-id="2973d-320">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="2973d-320">The default value is `true`.</span></span>

### <a name="generatedassemblyinfofile"></a><span data-ttu-id="2973d-321">GeneratedAssemblyInfoFile</span><span class="sxs-lookup"><span data-stu-id="2973d-321">GeneratedAssemblyInfoFile</span></span>

<span data-ttu-id="2973d-322">Путь к файлу сведений о созданной сборке.</span><span class="sxs-lookup"><span data-stu-id="2973d-322">The path of the generated assembly info file.</span></span> <span data-ttu-id="2973d-323">По умолчанию это путь к файлу в каталоге объектов `$(IntermediateOutputPath)`.</span><span class="sxs-lookup"><span data-stu-id="2973d-323">Default to a file in the `$(IntermediateOutputPath)` (obj) directory.</span></span>
