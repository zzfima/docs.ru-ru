---
title: Дополнения к формату CSPROJ для .NET Core
description: Различия между существующими файлами и файлами CSPROJ .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 09/22/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: ed1a25337ac1594d4ca748d0c6f79bdcc038a1e8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="additions-to-the-csproj-format-for-net-core"></a><span data-ttu-id="b8bdc-103">Дополнения к формату CSPROJ для .NET Core</span><span class="sxs-lookup"><span data-stu-id="b8bdc-103">Additions to the csproj format for .NET Core</span></span>

<span data-ttu-id="b8bdc-104">В этом документе перечислены изменения, внесенные в файлы проекта при перемещении из *project.json* в *CSPROJ* и [MSBuild](https://github.com/Microsoft/MSBuild).</span><span class="sxs-lookup"><span data-stu-id="b8bdc-104">This document outlines the changes that were added to the project files as part of the move from *project.json* to *csproj* and [MSBuild](https://github.com/Microsoft/MSBuild).</span></span> <span data-ttu-id="b8bdc-105">Дополнительную информацию, которая касается синтаксиса файла проекта в общем, и справку см. в документации по [файлу проекта MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="b8bdc-105">For more information about general project file syntax and reference, see [the MSBuild project file](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation.</span></span>  

## <a name="implicit-package-references"></a><span data-ttu-id="b8bdc-106">Неявные ссылки на пакет</span><span class="sxs-lookup"><span data-stu-id="b8bdc-106">Implicit package references</span></span>
<span data-ttu-id="b8bdc-107">Теперь неявные ссылки на метапакеты указываются в зависимости от целевой платформы, указанной в свойстве `<TargetFramework>` или `<TargetFrameworks>` файла проекта.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-107">Metapackages are implicitly referenced based on the target framework(s) specified in the `<TargetFramework>` or `<TargetFrameworks>` property of your project file.</span></span> <span data-ttu-id="b8bdc-108">Если свойство `<TargetFramework>` указано, свойство `<TargetFrameworks>` игнорируется независимо от порядка.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-108">`<TargetFrameworks>` is ignored if `<TargetFramework>` is specified, independent of order.</span></span>

```xml
 <PropertyGroup>
   <TargetFramework>netcoreapp1.1</TargetFramework>
 </PropertyGroup>
 ```
 
 ```xml
 <PropertyGroup>
   <TargetFrameworks>netcoreapp1.1;net462</TargetFrameworks>
 </PropertyGroup>
 ```

### <a name="recommendations"></a><span data-ttu-id="b8bdc-109">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="b8bdc-109">Recommendations</span></span>
<span data-ttu-id="b8bdc-110">Так как теперь указываются неявные ссылки на метапакеты `Microsoft.NETCore.App` или `NetStandard.Library`, следует учитывать приведенные ниже рекомендации:</span><span class="sxs-lookup"><span data-stu-id="b8bdc-110">Since `Microsoft.NETCore.App` or `NetStandard.Library` metapackages are implicitly referenced, the following are our recommended best practices:</span></span>

* <span data-ttu-id="b8bdc-111">Ориентируясь на .NET Core или .NET Standard, никогда не указывайте явную ссылку на метапакеты `Microsoft.NETCore.App` или `NetStandard.Library` через элемент `<PackageReference>` в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-111">When targeting .NET Core or .NET Standard, never have an explicit reference to the `Microsoft.NETCore.App` or `NetStandard.Library` metapackages via a `<PackageReference>` item in your project file.</span></span>
* <span data-ttu-id="b8bdc-112">Если при ориентации на .NET Core нужна определенная версия среды выполнения, вместо ссылки на метапакет следует использовать свойство `<RuntimeFrameworkVersion>` в проекте (например, `1.0.4`).</span><span class="sxs-lookup"><span data-stu-id="b8bdc-112">If you need a specific version of the runtime when targeting .NET Core, you should use the `<RuntimeFrameworkVersion>` property in your project (for example, `1.0.4`) instead of referencing the metapackage.</span></span>
    * <span data-ttu-id="b8bdc-113">Это может произойти, например, когда вы используете [автономные развертывания](../deploying/index.md#self-contained-deployments-scd) и нуждаетесь в определенной версии исправления 1.0.0 LTS для среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-113">This might happen if you are using [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) and you need a specific patch version of 1.0.0 LTS runtime, for example.</span></span>
* <span data-ttu-id="b8bdc-114">Если при ориентации на .NET Standard вам нужна конкретная версия метапакета `NetStandard.Library`, можно использовать свойство `<NetStandardImplicitPackageVersion>` и установить требуемую версию.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-114">If you need a specific version of the `NetStandard.Library` metapackage when targeting .NET Standard, you can use the `<NetStandardImplicitPackageVersion>` property and set the version you need.</span></span>
* <span data-ttu-id="b8bdc-115">Не добавляйте и не обновляйте ссылки на метапакет `Microsoft.NETCore.App` или `NetStandard.Library` явным образом в проектах .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-115">Don't explicitly add or update references to either the `Microsoft.NETCore.App` or `NetStandard.Library` metapackage in .NET Framework projects.</span></span> <span data-ttu-id="b8bdc-116">Если при использовании пакета NuGet на основе .NET Standard требуется любая версия `NetStandard.Library`, NuGet автоматически устанавливает ее.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-116">If any version of `NetStandard.Library` is needed when using a .NET Standard-based NuGet package, NuGet automatically installs that version.</span></span>

## <a name="default-compilation-includes-in-net-core-projects"></a><span data-ttu-id="b8bdc-117">Компиляция по умолчанию, включенная в проекты .NET Core</span><span class="sxs-lookup"><span data-stu-id="b8bdc-117">Default compilation includes in .NET Core projects</span></span>
<span data-ttu-id="b8bdc-118">В рамках перехода на формат *CSPROJ* в последних версиях пакета SDK мы перенесли включения и исключения по умолчанию для элементов Compile и внедренные ресурсы в файлы свойств пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-118">With the move to the *csproj* format in the latest SDK versions, we've moved the default includes and excludes for compile items and embedded resources to the SDK properties files.</span></span> <span data-ttu-id="b8bdc-119">Это означает, что вам больше не нужно указывать эти элементы в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-119">This means that you no longer need to specify these items in your project file.</span></span> 

<span data-ttu-id="b8bdc-120">Основной причиной этого является стремление очистить ваш файл проекта от всего лишнего.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-120">The main reason for doing this is to reduce the clutter in your project file.</span></span> <span data-ttu-id="b8bdc-121">Значения по умолчанию в пакете SDK должны охватывать наиболее распространенные варианты использования, поэтому нет необходимости повторять их в каждом создаваемом проекте.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-121">The defaults that are present in the SDK should cover most common use cases, so there is no need to repeat them in every project that you create.</span></span> <span data-ttu-id="b8bdc-122">Это позволяет уменьшить файлы проекта и гораздо проще читать их, а также вносить правки вручную.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-122">This leads to smaller project files that are much easier to understand as well as edit by hand, if needed.</span></span> 

<span data-ttu-id="b8bdc-123">Следующая таблица показывает, какой элемент и какие [стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) включены и исключены в пакете SDK:</span><span class="sxs-lookup"><span data-stu-id="b8bdc-123">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are both included and excluded in the SDK:</span></span> 

| <span data-ttu-id="b8bdc-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="b8bdc-124">Element</span></span>           | <span data-ttu-id="b8bdc-125">Стандартная маска включения</span><span class="sxs-lookup"><span data-stu-id="b8bdc-125">Include glob</span></span>                              | <span data-ttu-id="b8bdc-126">Стандартная маска исключения</span><span class="sxs-lookup"><span data-stu-id="b8bdc-126">Exclude glob</span></span>                                                  | <span data-ttu-id="b8bdc-127">Стандартная маска удаления</span><span class="sxs-lookup"><span data-stu-id="b8bdc-127">Remove glob</span></span>                |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| <span data-ttu-id="b8bdc-128">Компилятор</span><span class="sxs-lookup"><span data-stu-id="b8bdc-128">Compile</span></span>           | <span data-ttu-id="b8bdc-129">\*\*/\*.cs (или другие расширения языка)</span><span class="sxs-lookup"><span data-stu-id="b8bdc-129">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="b8bdc-130">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="b8bdc-130">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="b8bdc-131">Н/Д</span><span class="sxs-lookup"><span data-stu-id="b8bdc-131">N/A</span></span>                        |
| <span data-ttu-id="b8bdc-132">ВнедренныйРесурс</span><span class="sxs-lookup"><span data-stu-id="b8bdc-132">EmbeddedResource</span></span>  | <span data-ttu-id="b8bdc-133">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="b8bdc-133">\*\*/\*.resx</span></span>                              | <span data-ttu-id="b8bdc-134">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="b8bdc-134">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="b8bdc-135">Н/Д</span><span class="sxs-lookup"><span data-stu-id="b8bdc-135">N/A</span></span>                        |
| <span data-ttu-id="b8bdc-136">Нет</span><span class="sxs-lookup"><span data-stu-id="b8bdc-136">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="b8bdc-137">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="b8bdc-137">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="b8bdc-138">- \*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="b8bdc-138">- \*\*/\*.cs; \*\*/\*.resx</span></span> |

<span data-ttu-id="b8bdc-139">Если в вашем проекте имеются стандартные маски и вы пытаетесь выполнить его сборку с помощью новейшего пакета SDK, появится следующая ошибка:</span><span class="sxs-lookup"><span data-stu-id="b8bdc-139">If you have globs in your project and you try to build it using the newest SDK, you'll get the following error:</span></span>

> <span data-ttu-id="b8bdc-140">Duplicate Compile items were included.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-140">Duplicate Compile items were included.</span></span> <span data-ttu-id="b8bdc-141">The .NET SDK includes Compile items from your project directory by default.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-141">The .NET SDK includes Compile items from your project directory by default.</span></span> <span data-ttu-id="b8bdc-142">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file. (Включены повторяющиеся элементы Compile. По умолчанию пакет SDK для .NET включает элементы Compile из каталога проекта. Можно удалить эти элементы из файла проекта или задать для свойства "EnableDefaultCompileItems" значение "false", чтобы явно включить их в файл проекта.)</span><span class="sxs-lookup"><span data-stu-id="b8bdc-142">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.</span></span> 

<span data-ttu-id="b8bdc-143">Чтобы обойти эту ошибку, можно либо удалить явные элементы `Compile`, которые соответствуют указанным в предыдущей таблице, либо установить для свойства `<EnableDefaultCompileItems>` значение `false`, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="b8bdc-143">In order to get around this error, you can either remove the explicit `Compile` items that match the ones listed on the previous table, or you can set the `<EnableDefaultCompileItems>` property to `false`, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
<span data-ttu-id="b8bdc-144">Указание значения `false` для этого свойства переопределяет неявное включение, в результате чего возвращается поведение для предыдущих пакетов SDK, где требовалось задавать стандартные маски по умолчанию в проекте.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-144">Setting this property to `false` will override implicit inclusion and the behavior will revert back to the previous SDKs where you had to specify the default globs in your project.</span></span> 

<span data-ttu-id="b8bdc-145">Это изменение не затрагивает основные механизмы других включений.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-145">This change does not modify the main mechanics of other includes.</span></span> <span data-ttu-id="b8bdc-146">Но если вы хотите указать, например, отдельные файлы для публикации вместе со своим приложением, для этого можно по-прежнему использовать привычные механизмы в *CSPROJ* (например, элемент `<Content>`).</span><span class="sxs-lookup"><span data-stu-id="b8bdc-146">However, if you wish to specify, for example, some files to get published with your app, you can still use the known mechanisms in *csproj* for that (for example, the `<Content>` element).</span></span>

<span data-ttu-id="b8bdc-147">`<EnableDefaultCompileItems>` отключает только стандартные маски `Compile`, не затрагивая все остальные, например неявную стандартную маску `None`, которая также применяется к элементам \*.cs.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-147">`<EnableDefaultCompileItems>` only disables `Compile` globs but doesn't affect other globs, like the implicit `None` glob, which also applies to \*.cs items.</span></span> <span data-ttu-id="b8bdc-148">Из-за этого **обозреватель решений** продолжит показывать элементы \*.cs как часть проекта, включенную в виде элементов `None`.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-148">Because of that, **Solution Explorer** will continue show \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="b8bdc-149">Аналогичным образом, можно использовать `<EnableDefaultNoneItems>` для отключения неявной стандартной маски `None`.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-149">In a similar way, you can use `<EnableDefaultNoneItems>` to disable the implicit `None` glob.</span></span>

<span data-ttu-id="b8bdc-150">Чтобы отключить **все неявные стандартные маски**, можно задать для свойства `<EnableDefaultItems>` значение `false`, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="b8bdc-150">To disable **all implicit globs**, you can set the `<EnableDefaultItems>` property to `false` as in the following example:</span></span>
```xml
<PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

### <a name="recommendation"></a><span data-ttu-id="b8bdc-151">Рекомендация</span><span class="sxs-lookup"><span data-stu-id="b8bdc-151">Recommendation</span></span>
<span data-ttu-id="b8bdc-152">При использовании CSPROJ мы советуем удалить из проекта стандартные маски по умолчанию и добавить пути к файлам стандартных масок только для тех артефактов, которые нужны приложению или библиотеке в различных сценариях (например, среда выполнения и упаковка NuGet).</span><span class="sxs-lookup"><span data-stu-id="b8bdc-152">With csproj, we recommend that you remove the default globs from your project and only add file paths with globs for those artifacts that your app/library needs for various scenarios (for example, runtime and NuGet packaging).</span></span>

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a><span data-ttu-id="b8bdc-153">Как просмотреть весь проект в представлении MSBuild</span><span class="sxs-lookup"><span data-stu-id="b8bdc-153">How to see the whole project as MSBuild sees it</span></span>

<span data-ttu-id="b8bdc-154">Хотя эти изменения csproj значительно упростили файлы проекта, возможно, вы захотите просмотреть полностью развернутый пакет в представлении MSBuild после включения пакета SDK и его целевых объектов.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-154">While those csproj changes greatly simplify project files, you might want to see the fully expanded project as MSBuild sees it once the SDK and its targets are included.</span></span> <span data-ttu-id="b8bdc-155">Выполните предварительную обработку проекта, [включив](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) в команду [`dotnet msbuild`](dotnet-msbuild.md) параметр `/pp`. Это позволит просмотреть сведения об импортированных файлах, их источниках, вкладе в сборку без фактического создания проекта:</span><span class="sxs-lookup"><span data-stu-id="b8bdc-155">Preprocess the project with [the `/pp` switch](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) of the [`dotnet msbuild`](dotnet-msbuild.md) command, which shows which files are imported, their sources, and their contributions to the build without actually building the project:</span></span>

`dotnet msbuild /pp:fullproject.xml`

<span data-ttu-id="b8bdc-156">Если проект имеет несколько требуемых версий .NET Framework, результаты выполнения команды должны касаться только одной из них. Эту версию следует указать в качестве свойства MSBuild:</span><span class="sxs-lookup"><span data-stu-id="b8bdc-156">If the project has multiple target frameworks, the results of the command should be focused on only one of them by specifying it as an MSBuild property:</span></span>

`dotnet msbuild /p:TargetFramework=netcoreapp2.0 /pp:fullproject.xml`

## <a name="additions"></a><span data-ttu-id="b8bdc-157">Добавления</span><span class="sxs-lookup"><span data-stu-id="b8bdc-157">Additions</span></span>

### <a name="sdk-attribute"></a><span data-ttu-id="b8bdc-158">Атрибут Sdk</span><span class="sxs-lookup"><span data-stu-id="b8bdc-158">Sdk attribute</span></span> 
<span data-ttu-id="b8bdc-159">Элемент `<Project>` файла *CSPROJ* имеет новый атрибут `Sdk`.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-159">The `<Project>` element of the *.csproj* file has a new attribute called `Sdk`.</span></span> <span data-ttu-id="b8bdc-160">`Sdk` определяет, какой пакет SDK будет использоваться проектом.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-160">`Sdk` specifies which SDK will be used by the project.</span></span> <span data-ttu-id="b8bdc-161">Пакет SDK, согласно описанию в [документе о слоях](cli-msbuild-architecture.md), является набором [задач](/visualstudio/msbuild/msbuild-tasks) и [целевых объектов](/visualstudio/msbuild/msbuild-targets) MSBuild, способным выполнять сборку кода .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-161">The SDK, as the [layering document](cli-msbuild-architecture.md) describes, is a set of MSBuild [tasks](/visualstudio/msbuild/msbuild-tasks) and [targets](/visualstudio/msbuild/msbuild-targets) that can build .NET Core code.</span></span> <span data-ttu-id="b8bdc-162">Мы предоставляем два основных пакета SDK с инструментами для .NET Core:</span><span class="sxs-lookup"><span data-stu-id="b8bdc-162">We ship two main SDKs with the .NET Core tools:</span></span>

1. <span data-ttu-id="b8bdc-163">пакет SDK для .NET Core с идентификатором `Microsoft.NET.Sdk`;</span><span class="sxs-lookup"><span data-stu-id="b8bdc-163">The .NET Core SDK with the ID of `Microsoft.NET.Sdk`</span></span>
2. <span data-ttu-id="b8bdc-164">веб-пакет SDK для .NET Core с идентификатором `Microsoft.NET.Sdk.Web`.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-164">The .NET Core web SDK with the ID of `Microsoft.NET.Sdk.Web`</span></span>

<span data-ttu-id="b8bdc-165">Чтобы использовать инструменты и выполнять сборку кода .NET Core, в качестве значения атрибута `Sdk` в элементе `<Project>` нужно задать один из этих идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-165">You need to have the `Sdk` attribute set to one of those IDs on the `<Project>` element in order to use the .NET Core tools and build your code.</span></span> 

### <a name="packagereference"></a><span data-ttu-id="b8bdc-166">PackageReference</span><span class="sxs-lookup"><span data-stu-id="b8bdc-166">PackageReference</span></span>
<span data-ttu-id="b8bdc-167">Элемент, определяющий зависимость NuGet в проекте.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-167">Item that specifies a NuGet dependency in the project.</span></span> <span data-ttu-id="b8bdc-168">Атрибут `Include` указывает идентификатор пакета.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-168">The `Include` attribute specifies the package ID.</span></span> 

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a><span data-ttu-id="b8bdc-169">Версия</span><span class="sxs-lookup"><span data-stu-id="b8bdc-169">Version</span></span>
<span data-ttu-id="b8bdc-170">`Version` указывает версию пакета для восстановления.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-170">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="b8bdc-171">Этот атрибут подчиняется правилам схемы [управления версиями NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="b8bdc-171">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="b8bdc-172">По умолчанию выбирается точное соответствие версии.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-172">The default behavior is an exact version match.</span></span> <span data-ttu-id="b8bdc-173">Например, если указать `Version="1.2.3"`, это будет эквивалентно нотации NuGet `[1.2.3]` для точного указания версии 1.2.3 пакета.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-173">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

#### <a name="includeassets-excludeassets-and-privateassets"></a><span data-ttu-id="b8bdc-174">IncludeAssets, ExcludeAssets и PrivateAssets</span><span class="sxs-lookup"><span data-stu-id="b8bdc-174">IncludeAssets, ExcludeAssets and PrivateAssets</span></span>
<span data-ttu-id="b8bdc-175">Атрибут `IncludeAssets` указывает, какие ресурсы пакета, указанные `<PackageReference>`, следует использовать.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-175">`IncludeAssets` attribute specifies what assets belonging to the package specified by `<PackageReference>` should be consumed.</span></span> 

<span data-ttu-id="b8bdc-176">Атрибут `ExcludeAssets` указывает, какие ресурсы пакета, указанные `<PackageReference>`, не следует использовать.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-176">`ExcludeAssets` attribute specifies what assets belonging to the package specified by `<PackageReference>` should not be consumed.</span></span>

<span data-ttu-id="b8bdc-177">Атрибут `PrivateAssets` указывает, какие ресурсы пакета, указанные `<PackageReference>`, следует использовать. Но они не должны передаваться в следующий проект.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-177">`PrivateAssets` attribute specifies what assets belonging to the package specified by `<PackageReference>` should be consumed but that they should not flow to the next project.</span></span> 

> [!NOTE]
> <span data-ttu-id="b8bdc-178">`PrivateAssets` эквивалентен элементу *project.json*/*xproj* `SuppressParent`.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-178">`PrivateAssets` is equivalent to the *project.json*/*xproj* `SuppressParent` element.</span></span>

<span data-ttu-id="b8bdc-179">Эти атрибуты могут содержать по меньшей мере один из перечисленных ниже элементов.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-179">These attributes can contain one or more of the following items:</span></span>

* <span data-ttu-id="b8bdc-180">`Compile` — содержимое папки lib доступно для компиляции.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-180">`Compile` – the contents of the lib folder are available to compile against.</span></span>
* <span data-ttu-id="b8bdc-181">`Runtime` — содержимое папки среды выполнения распределяется.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-181">`Runtime` – the contents of the runtime folder are distributed.</span></span>
* <span data-ttu-id="b8bdc-182">`ContentFiles` — используется содержимое папки *contentfiles*.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-182">`ContentFiles` – the contents of the *contentfiles* folder are used.</span></span>
* <span data-ttu-id="b8bdc-183">`Build` — используются свойства и целевые объекты в папке сборки.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-183">`Build` – the props/targets in the build folder are used.</span></span>
* <span data-ttu-id="b8bdc-184">`Native` — содержимое копируется из основных ресурсов в папку выходных данных среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-184">`Native` – the contents from native assets are copied to the output folder for runtime.</span></span>
* <span data-ttu-id="b8bdc-185">`Analyzers` — используются анализаторы.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-185">`Analyzers` – the analyzers are used.</span></span>

<span data-ttu-id="b8bdc-186">Кроме того, атрибут может содержать следующие значения.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-186">Alternatively, the attribute can contain:</span></span>

* <span data-ttu-id="b8bdc-187">`None` — не используется ни один ресурс.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-187">`None` – none of the assets are used.</span></span>
* <span data-ttu-id="b8bdc-188">`All` — используются все ресурсы.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-188">`All` – all assets are used.</span></span>

### <a name="dotnetclitoolreference"></a><span data-ttu-id="b8bdc-189">DotNetCliToolReference</span><span class="sxs-lookup"><span data-stu-id="b8bdc-189">DotNetCliToolReference</span></span>
<span data-ttu-id="b8bdc-190">Элемент `<DotNetCliToolReference>` указывает средство интерфейса командной строки, которое пользователь хочет восстановить в контексте проекта.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-190">`<DotNetCliToolReference>` item element specifies the CLI tool that the user wants to restore in the context of the project.</span></span> <span data-ttu-id="b8bdc-191">Этот элемент используется вместо узла `tools` в файле *project.json*.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-191">It's a replacement for the `tools` node in *project.json*.</span></span> 

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

#### <a name="version"></a><span data-ttu-id="b8bdc-192">Версия</span><span class="sxs-lookup"><span data-stu-id="b8bdc-192">Version</span></span>
<span data-ttu-id="b8bdc-193">`Version` указывает версию пакета для восстановления.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-193">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="b8bdc-194">Этот атрибут подчиняется правилам схемы [управления версиями NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="b8bdc-194">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="b8bdc-195">По умолчанию выбирается точное соответствие версии.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-195">The default behavior is an exact version match.</span></span> <span data-ttu-id="b8bdc-196">Например, если указать `Version="1.2.3"`, это будет эквивалентно нотации NuGet `[1.2.3]` для точного указания версии 1.2.3 пакета.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-196">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

### <a name="runtimeidentifiers"></a><span data-ttu-id="b8bdc-197">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="b8bdc-197">RuntimeIdentifiers</span></span>
<span data-ttu-id="b8bdc-198">Элемент `<RuntimeIdentifiers>` позволяет указать для проекта список [идентификаторов среды выполнения ((RID)](../rid-catalog.md) (в качестве разделителя используется точка с запятой).</span><span class="sxs-lookup"><span data-stu-id="b8bdc-198">The `<RuntimeIdentifiers>` element lets you specify a semicolon-delimited list of [Runtime Identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="b8bdc-199">Идентификаторы среды выполнения позволяют публиковать автономные развертывания.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-199">RIDs enable publishing a self-contained deployments.</span></span> 

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a><span data-ttu-id="b8bdc-200">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="b8bdc-200">RuntimeIdentifier</span></span>
<span data-ttu-id="b8bdc-201">Элемент `<RuntimeIdentifier>` позволяет указать для проекта только один [идентификатор среды выполнения](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="b8bdc-201">The `<RuntimeIdentifier>` element allows you to specify only one [Runtime Identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="b8bdc-202">Идентификаторы среды выполнения позволяют опубликовать автономное развертывание.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-202">RIDs enable publishing a self-contained deployment.</span></span> 

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

### <a name="packagetargetfallback"></a><span data-ttu-id="b8bdc-203">PackageTargetFallback</span><span class="sxs-lookup"><span data-stu-id="b8bdc-203">PackageTargetFallback</span></span> 
<span data-ttu-id="b8bdc-204">Элемент `<PackageTargetFallback>` позволяет указать набор совместимых целевых объектов, которые следует использовать при восстановлении пакетов.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-204">The `<PackageTargetFallback>` element allows you to specify a set of compatible targets to be used when restoring packages.</span></span> <span data-ttu-id="b8bdc-205">Он разрешает пакетам, использующим dotnet [TxM (моникер целевой версии x)](/nuget/schema/target-frameworks), взаимодействовать с пакетами, которые не объявляют dotnet TxM.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-205">It's designed to allow packages that use the dotnet [TxM (Target x Moniker)](/nuget/schema/target-frameworks) to operate with packages that don't declare a dotnet TxM.</span></span> <span data-ttu-id="b8bdc-206">Если в проекте используется dotnet TxM, все пакеты, от которых вы зависите, должны также содержать dotnet TxM. В противном случае нужно добавить `<PackageTargetFallback>` в проект, чтобы обеспечить совместимость с платформами, отличными от dotnet.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-206">If your project uses the dotnet TxM, then all the packages it depends on must also have a dotnet TxM, unless you add the `<PackageTargetFallback>` to your project in order to allow non-dotnet platforms to be compatible with dotnet.</span></span> 

<span data-ttu-id="b8bdc-207">В следующем примере приводятся резервные варианты для всех целевых объектов в проекте:</span><span class="sxs-lookup"><span data-stu-id="b8bdc-207">The following example provides the fallbacks for all targets in your project:</span></span> 

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

<span data-ttu-id="b8bdc-208">В следующем примере приводятся резервные варианты только для целевого объекта `netcoreapp1.0`:</span><span class="sxs-lookup"><span data-stu-id="b8bdc-208">The following example specifies the fallbacks only for the `netcoreapp1.0` target:</span></span>

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp1.0'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="nuget-metadata-properties"></a><span data-ttu-id="b8bdc-209">Свойства метаданных NuGet</span><span class="sxs-lookup"><span data-stu-id="b8bdc-209">NuGet metadata properties</span></span>
<span data-ttu-id="b8bdc-210">При переходе к MSbuild мы переместили входные метаданные, которые использовались при упаковке пакета NuGet из *project.json* в файлы *CSPROJ*.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-210">With the move to MSbuild, we have moved the input metadata that is used when packing a NuGet package from *project.json* to *.csproj* files.</span></span> <span data-ttu-id="b8bdc-211">Входными данными являются свойства MSBuild, поэтому они должны входить в группу `<PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-211">The inputs are MSBuild properties so they have to go within a `<PropertyGroup>` group.</span></span> <span data-ttu-id="b8bdc-212">Ниже представлен список свойств, которые используются как входные данные в процессе упаковки при использовании команды `dotnet pack` или целевого объекта `Pack` MSBuild, входящего в SDK.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-212">The following is the list of properties that are used as inputs to the packing process when using the `dotnet pack` command or the `Pack` MSBuild target that is part of the SDK.</span></span> 

### <a name="ispackable"></a><span data-ttu-id="b8bdc-213">IsPackable</span><span class="sxs-lookup"><span data-stu-id="b8bdc-213">IsPackable</span></span>
<span data-ttu-id="b8bdc-214">Логическое значение, которое указывает, можно ли упаковать проект.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-214">A Boolean value that specifies whether the project can be packed.</span></span> <span data-ttu-id="b8bdc-215">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-215">The default value is `true`.</span></span> 

### <a name="packageversion"></a><span data-ttu-id="b8bdc-216">PackageVersion</span><span class="sxs-lookup"><span data-stu-id="b8bdc-216">PackageVersion</span></span>
<span data-ttu-id="b8bdc-217">Указывает версию, которую будет иметь итоговый пакет.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-217">Specifies the version that the resulting package will have.</span></span> <span data-ttu-id="b8bdc-218">Принимает все формы строки версии NuGet.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-218">Accepts all forms of NuGet version string.</span></span> <span data-ttu-id="b8bdc-219">По умолчанию используется значение `$(Version)`, то есть значение свойства `Version` в проекте.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-219">Default is the value of `$(Version)`, that is, of the property `Version` in the project.</span></span> 

### <a name="packageid"></a><span data-ttu-id="b8bdc-220">PackageId</span><span class="sxs-lookup"><span data-stu-id="b8bdc-220">PackageId</span></span>
<span data-ttu-id="b8bdc-221">Указывает имя для итогового пакета.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-221">Specifies the name for the resulting package.</span></span> <span data-ttu-id="b8bdc-222">Если значение не указано, операция `pack` по умолчанию использует в качестве имени пакета `AssemblyName` или имя каталога.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-222">If not specified, the `pack` operation will default to using the `AssemblyName` or directory name as the name of the package.</span></span> 

### <a name="title"></a><span data-ttu-id="b8bdc-223">Заголовок</span><span class="sxs-lookup"><span data-stu-id="b8bdc-223">Title</span></span>
<span data-ttu-id="b8bdc-224">Понятный заголовок пакета, обычно используемый при отображении пользовательского интерфейса, как на сайте nuget.org и в диспетчере пакетов Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-224">A human-friendly title of the package, typically used in UI displays as on nuget.org and the Package Manager in Visual Studio.</span></span> <span data-ttu-id="b8bdc-225">Если значение не указано, используется идентификатор пакета.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-225">If not specified, the package ID is used instead.</span></span>

### <a name="authors"></a><span data-ttu-id="b8bdc-226">Authors</span><span class="sxs-lookup"><span data-stu-id="b8bdc-226">Authors</span></span>
<span data-ttu-id="b8bdc-227">Разделенный точками с запятой список авторов пакетов, совпадающих с именами профилей на сайте nuget.org. Они отображаются в коллекции NuGet на сайте nuget.org и используются для перекрестных ссылок на пакеты тех же авторов.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-227">A semicolon-separated list of packages authors, matching the profile names on nuget.org. These are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span>

### <a name="description"></a><span data-ttu-id="b8bdc-228">Описание:</span><span class="sxs-lookup"><span data-stu-id="b8bdc-228">Description</span></span>
<span data-ttu-id="b8bdc-229">Подробное описание пакета для отображения пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-229">A long description of the package for UI display.</span></span>

### <a name="copyright"></a><span data-ttu-id="b8bdc-230">Copyright</span><span class="sxs-lookup"><span data-stu-id="b8bdc-230">Copyright</span></span>
<span data-ttu-id="b8bdc-231">Сведения об авторских правах для пакета.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-231">Copyright details for the package.</span></span>

### <a name="packagerequirelicenseacceptance"></a><span data-ttu-id="b8bdc-232">PackageRequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="b8bdc-232">PackageRequireLicenseAcceptance</span></span>
<span data-ttu-id="b8bdc-233">Логическое значение, указывающее, должен ли клиент просить потребителя принять условия лицензии перед установкой пакета.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-233">A Boolean value that specifies whether the client must prompt the consumer to accept the package license before installing the package.</span></span> <span data-ttu-id="b8bdc-234">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-234">The default is `false`.</span></span>

### <a name="packagelicenseurl"></a><span data-ttu-id="b8bdc-235">PackageLicenseUrl</span><span class="sxs-lookup"><span data-stu-id="b8bdc-235">PackageLicenseUrl</span></span>
<span data-ttu-id="b8bdc-236">URL-адрес лицензии, применимой к пакету.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-236">An URL to the license that is applicable to the package.</span></span>

### <a name="packageprojecturl"></a><span data-ttu-id="b8bdc-237">PackageProjectUrl</span><span class="sxs-lookup"><span data-stu-id="b8bdc-237">PackageProjectUrl</span></span>
<span data-ttu-id="b8bdc-238">URL-адрес для домашней страницы пакета, часто указываемый при отображении пользовательского интерфейса, также как и nuget.org.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-238">A URL for the package's home page, often shown in UI displays as well as nuget.org.</span></span>

### <a name="packageiconurl"></a><span data-ttu-id="b8bdc-239">PackageIconUrl</span><span class="sxs-lookup"><span data-stu-id="b8bdc-239">PackageIconUrl</span></span>
<span data-ttu-id="b8bdc-240">URL-адрес для изображения размером 64x64 с прозрачным фоном, используемого в качестве значка для пакета при отображении пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-240">A URL for a 64x64 image with transparent background to use as the icon for the package in UI display.</span></span>

### <a name="packagereleasenotes"></a><span data-ttu-id="b8bdc-241">PackageReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="b8bdc-241">PackageReleaseNotes</span></span>
<span data-ttu-id="b8bdc-242">Заметки о выпуске для пакета.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-242">Release notes for the package.</span></span>

### <a name="packagetags"></a><span data-ttu-id="b8bdc-243">PackageTags</span><span class="sxs-lookup"><span data-stu-id="b8bdc-243">PackageTags</span></span>
<span data-ttu-id="b8bdc-244">Разделенный точками с запятой список тегов, обозначающий пакет.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-244">A semicolon-delimited list of tags that designates the package.</span></span>

### <a name="packageoutputpath"></a><span data-ttu-id="b8bdc-245">PackageOutputPath</span><span class="sxs-lookup"><span data-stu-id="b8bdc-245">PackageOutputPath</span></span>
<span data-ttu-id="b8bdc-246">Определяет выходной путь для размещения упакованного пакета.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-246">Determines the output path in which the packed package will be dropped.</span></span> <span data-ttu-id="b8bdc-247">Значение по умолчанию — `$(OutputPath)`.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-247">Default is `$(OutputPath)`.</span></span> 

### <a name="includesymbols"></a><span data-ttu-id="b8bdc-248">IncludeSymbols</span><span class="sxs-lookup"><span data-stu-id="b8bdc-248">IncludeSymbols</span></span>
<span data-ttu-id="b8bdc-249">Это логическое значение указывает, должен ли пакет создавать дополнительный пакет символов при упаковке проекта.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-249">This Boolean value indicates whether the package should create an additional symbols package when the project is packed.</span></span> <span data-ttu-id="b8bdc-250">Этот пакет будет иметь расширение *.symbols.nupkg* и копировать PDB-файлы, а также библиотеки DLL и другие выходные файлы.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-250">This package will have a *.symbols.nupkg* extension and will copy the PDB files along with the DLL and other output files.</span></span>

### <a name="includesource"></a><span data-ttu-id="b8bdc-251">IncludeSource</span><span class="sxs-lookup"><span data-stu-id="b8bdc-251">IncludeSource</span></span>
<span data-ttu-id="b8bdc-252">Это логическое значение указывает, должен ли процесс упаковки создавать исходный пакет.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-252">This Boolean value indicates whether the pack process should create a source package.</span></span> <span data-ttu-id="b8bdc-253">Исходный пакет содержит библиотеку исходного кода, а также файлы PDB.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-253">The source package contains the library's source code as well as PDB files.</span></span> <span data-ttu-id="b8bdc-254">Исходные файлы помещаются в каталог `src/ProjectName` итогового файла пакета.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-254">Source files are put under the `src/ProjectName` directory in the resulting package file.</span></span> 

### <a name="istool"></a><span data-ttu-id="b8bdc-255">IsTool</span><span class="sxs-lookup"><span data-stu-id="b8bdc-255">IsTool</span></span>
<span data-ttu-id="b8bdc-256">Указывает, копируются ли все выходные файлы в папку *tools* вместо папки *lib*.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-256">Specifies whether all output files are copied to the *tools* folder instead of the *lib* folder.</span></span> <span data-ttu-id="b8bdc-257">Обратите внимание, что это свойство отличается от `DotNetCliTool`, которое указывается путем задания `PackageType` в файле *CSPROJ*.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-257">Note that this is different from a `DotNetCliTool` which is specified by setting the `PackageType` in the *.csproj* file.</span></span>

### <a name="repositoryurl"></a><span data-ttu-id="b8bdc-258">RepositoryUrl</span><span class="sxs-lookup"><span data-stu-id="b8bdc-258">RepositoryUrl</span></span>
<span data-ttu-id="b8bdc-259">Указывает URL-адрес репозитория, где находится исходный код для пакета или откуда выполняется его сборка.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-259">Specifies the URL for the repository where the source code for the package resides and/or from which it's being built.</span></span> 

### <a name="repositorytype"></a><span data-ttu-id="b8bdc-260">RepositoryType</span><span class="sxs-lookup"><span data-stu-id="b8bdc-260">RepositoryType</span></span>
<span data-ttu-id="b8bdc-261">Указывает тип репозитория.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-261">Specifies the type of the repository.</span></span> <span data-ttu-id="b8bdc-262">Значение по умолчанию — "git".</span><span class="sxs-lookup"><span data-stu-id="b8bdc-262">Default is "git".</span></span> 

### <a name="nopackageanalysis"></a><span data-ttu-id="b8bdc-263">NoPackageAnalysis</span><span class="sxs-lookup"><span data-stu-id="b8bdc-263">NoPackageAnalysis</span></span>
<span data-ttu-id="b8bdc-264">Указывает, что пакету не нужно запускать анализ пакета после его сборки.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-264">Specifies that pack should not run package analysis after building the package.</span></span>

### <a name="minclientversion"></a><span data-ttu-id="b8bdc-265">MinClientVersion</span><span class="sxs-lookup"><span data-stu-id="b8bdc-265">MinClientVersion</span></span>
<span data-ttu-id="b8bdc-266">Указывает минимальную версию клиента NuGet, который может установить этот пакет с использованием nuget.exe и диспетчера пакетов Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-266">Specifies the minimum version of the NuGet client that can install this package, enforced by nuget.exe and the Visual Studio Package Manager.</span></span>

### <a name="includebuildoutput"></a><span data-ttu-id="b8bdc-267">IncludeBuildOutput</span><span class="sxs-lookup"><span data-stu-id="b8bdc-267">IncludeBuildOutput</span></span>
<span data-ttu-id="b8bdc-268">Это логическое значение указывает, следует ли упаковывать выходные сборки в файл *NUPKG*.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-268">This Boolean values specifies whether the build output assemblies should be packed into the *.nupkg* file or not.</span></span>

### <a name="includecontentinpack"></a><span data-ttu-id="b8bdc-269">IncludeContentInPack</span><span class="sxs-lookup"><span data-stu-id="b8bdc-269">IncludeContentInPack</span></span>
<span data-ttu-id="b8bdc-270">Это логическое значение указывает, будут ли все элементы, имеющие тип `Content`, автоматически включены в итоговый пакет.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-270">This Boolean value specifies whether any items that have a type of `Content` will be included in the resulting package automatically.</span></span> <span data-ttu-id="b8bdc-271">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-271">The default is `true`.</span></span> 

### <a name="buildoutputtargetfolder"></a><span data-ttu-id="b8bdc-272">BuildOutputTargetFolder</span><span class="sxs-lookup"><span data-stu-id="b8bdc-272">BuildOutputTargetFolder</span></span>
<span data-ttu-id="b8bdc-273">Указывает папку для размещения выходных сборок.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-273">Specifies the folder where to place the output assemblies.</span></span> <span data-ttu-id="b8bdc-274">Выходные сборки (и другие выходные файлы) копируются в соответствующие папки платформы.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-274">The output assemblies (and other output files) are copied into their respective framework folders.</span></span>

### <a name="contenttargetfolders"></a><span data-ttu-id="b8bdc-275">ContentTargetFolders</span><span class="sxs-lookup"><span data-stu-id="b8bdc-275">ContentTargetFolders</span></span>
<span data-ttu-id="b8bdc-276">Это свойство указывает расположение по умолчанию, куда следует помещать все файлы содержимого, для которых не указан `PackagePath`.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-276">This property specifies the default location of where all the content files should go if `PackagePath` is not specified for them.</span></span> <span data-ttu-id="b8bdc-277">Значение по умолчанию — "content;contentFiles".</span><span class="sxs-lookup"><span data-stu-id="b8bdc-277">The default value is "content;contentFiles".</span></span>

### <a name="nuspecfile"></a><span data-ttu-id="b8bdc-278">NuspecFile</span><span class="sxs-lookup"><span data-stu-id="b8bdc-278">NuspecFile</span></span>
<span data-ttu-id="b8bdc-279">Относительный или абсолютный путь к файлу *NUSPEC*, используемому для упаковки.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-279">Relative or absolute path to the *.nuspec* file being used for packing.</span></span> 

> [!NOTE]
> <span data-ttu-id="b8bdc-280">Если файл *NUSPEC* указан, он используется для упаковки в **монопольном порядке**, а любые сведения в проектах не используются.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-280">If the *.nuspec* file is specified, it's used **exclusively** for packaging information and any information in the projects is not used.</span></span> 

### <a name="nuspecbasepath"></a><span data-ttu-id="b8bdc-281">NuspecBasePath</span><span class="sxs-lookup"><span data-stu-id="b8bdc-281">NuspecBasePath</span></span>
<span data-ttu-id="b8bdc-282">Базовый путь для файла *NUSPEC*.</span><span class="sxs-lookup"><span data-stu-id="b8bdc-282">Base path for the *.nuspec* file.</span></span>

### <a name="nuspecproperties"></a><span data-ttu-id="b8bdc-283">NuspecProperties</span><span class="sxs-lookup"><span data-stu-id="b8bdc-283">NuspecProperties</span></span>
<span data-ttu-id="b8bdc-284">Список разделенных точками с запятой пар "ключ-значение".</span><span class="sxs-lookup"><span data-stu-id="b8bdc-284">Semicolon separated list of key=value pairs.</span></span>
