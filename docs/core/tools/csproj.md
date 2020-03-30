---
title: Дополнения к формату CSPROJ для .NET Core
description: Различия между существующими файлами и файлами CSPROJ .NET Core
ms.date: 04/08/2019
ms.openlocfilehash: 9d9e212c9531828a8c2dd51fdd7488c17be41ba2
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134067"
---
# <a name="additions-to-the-csproj-format-for-net-core"></a><span data-ttu-id="04be1-103">Дополнения к формату CSPROJ для .NET Core</span><span class="sxs-lookup"><span data-stu-id="04be1-103">Additions to the csproj format for .NET Core</span></span>

<span data-ttu-id="04be1-104">В этом документе перечислены изменения, внесенные в файлы проекта при перемещении из *project.json* в *CSPROJ* и [MSBuild](https://github.com/Microsoft/MSBuild).</span><span class="sxs-lookup"><span data-stu-id="04be1-104">This document outlines the changes that were added to the project files as part of the move from *project.json* to *csproj* and [MSBuild](https://github.com/Microsoft/MSBuild).</span></span> <span data-ttu-id="04be1-105">Дополнительную информацию, которая касается синтаксиса файла проекта в общем, и справку см. в документации по [файлу проекта MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="04be1-105">For more information about general project file syntax and reference, see [the MSBuild project file](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation.</span></span>

## <a name="implicit-package-references"></a><span data-ttu-id="04be1-106">Неявные ссылки на пакет</span><span class="sxs-lookup"><span data-stu-id="04be1-106">Implicit package references</span></span>

<span data-ttu-id="04be1-107">Теперь неявные ссылки на метапакеты указываются в зависимости от целевой платформы, указанной в свойстве `<TargetFramework>` или `<TargetFrameworks>` файла проекта.</span><span class="sxs-lookup"><span data-stu-id="04be1-107">Metapackages are implicitly referenced based on the target framework(s) specified in the `<TargetFramework>` or `<TargetFrameworks>` property of your project file.</span></span> <span data-ttu-id="04be1-108">Если свойство `<TargetFramework>` указано, свойство `<TargetFrameworks>` игнорируется независимо от порядка.</span><span class="sxs-lookup"><span data-stu-id="04be1-108">`<TargetFrameworks>` is ignored if `<TargetFramework>` is specified, independent of order.</span></span> <span data-ttu-id="04be1-109">Дополнительную информацию см. в статье [Пакеты, метапакеты и платформы](../packages.md).</span><span class="sxs-lookup"><span data-stu-id="04be1-109">For more information, see [Packages, metapackages, and frameworks](../packages.md).</span></span>

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

### <a name="recommendations"></a><span data-ttu-id="04be1-110">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="04be1-110">Recommendations</span></span>

<span data-ttu-id="04be1-111">Так как теперь указываются неявные ссылки на метапакеты `Microsoft.NETCore.App` или `NETStandard.Library`, следует учитывать приведенные ниже рекомендации:</span><span class="sxs-lookup"><span data-stu-id="04be1-111">Since `Microsoft.NETCore.App` or `NETStandard.Library` metapackages are implicitly referenced, the following are our recommended best practices:</span></span>

- <span data-ttu-id="04be1-112">Ориентируясь на .NET Core или .NET Standard, никогда не указывайте явную ссылку на метапакеты `Microsoft.NETCore.App` или `NETStandard.Library` через элемент `<PackageReference>` в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="04be1-112">When targeting .NET Core or .NET Standard, never have an explicit reference to the `Microsoft.NETCore.App` or `NETStandard.Library` metapackages via a `<PackageReference>` item in your project file.</span></span>
- <span data-ttu-id="04be1-113">Если при ориентации на .NET Core нужна определенная версия среды выполнения, вместо ссылки на метапакет следует использовать свойство `<RuntimeFrameworkVersion>` в проекте (например, `1.0.4`).</span><span class="sxs-lookup"><span data-stu-id="04be1-113">If you need a specific version of the runtime when targeting .NET Core, you should use the `<RuntimeFrameworkVersion>` property in your project (for example, `1.0.4`) instead of referencing the metapackage.</span></span>
  - <span data-ttu-id="04be1-114">Это может произойти, например, когда вы используете [автономные развертывания](../deploying/index.md#publish-self-contained) и нуждаетесь в определенной версии исправления 1.0.0 LTS для среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="04be1-114">This might happen if you are using [self-contained deployments](../deploying/index.md#publish-self-contained) and you need a specific patch version of 1.0.0 LTS runtime, for example.</span></span>
- <span data-ttu-id="04be1-115">Если при ориентации на .NET Standard вам нужна конкретная версия метапакета `NETStandard.Library`, можно использовать свойство `<NetStandardImplicitPackageVersion>` и установить требуемую версию.</span><span class="sxs-lookup"><span data-stu-id="04be1-115">If you need a specific version of the `NETStandard.Library` metapackage when targeting .NET Standard, you can use the `<NetStandardImplicitPackageVersion>` property and set the version you need.</span></span>
- <span data-ttu-id="04be1-116">Не добавляйте и не обновляйте ссылки на метапакет `Microsoft.NETCore.App` или `NETStandard.Library` явным образом в проектах .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="04be1-116">Don't explicitly add or update references to either the `Microsoft.NETCore.App` or `NETStandard.Library` metapackage in .NET Framework projects.</span></span> <span data-ttu-id="04be1-117">Если при использовании пакета NuGet на основе .NET Standard требуется любая версия `NETStandard.Library`, NuGet автоматически устанавливает ее.</span><span class="sxs-lookup"><span data-stu-id="04be1-117">If any version of `NETStandard.Library` is needed when using a .NET Standard-based NuGet package, NuGet automatically installs that version.</span></span>

## <a name="implicit-version-for-some-package-references"></a><span data-ttu-id="04be1-118">Неявное указание версий для некоторых ссылок на пакет</span><span class="sxs-lookup"><span data-stu-id="04be1-118">Implicit version for some package references</span></span>

<span data-ttu-id="04be1-119">В большинстве случаев при использовании [`<PackageReference>`](#packagereference) требуется указать атрибут `Version`, чтобы определить используемую версию пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="04be1-119">Most usages of [`<PackageReference>`](#packagereference) require setting the `Version` attribute to specify the NuGet package version to be used.</span></span> <span data-ttu-id="04be1-120">Атрибут необязательно указывать, если используется .NET Core 2.1 или 2.2 со ссылкой на [Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage-app) или [Microsoft.AspNetCore.All](/aspnet/core/fundamentals/metapackage).</span><span class="sxs-lookup"><span data-stu-id="04be1-120">When using .NET Core 2.1 or 2.2 and referencing [Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage-app) or [Microsoft.AspNetCore.All](/aspnet/core/fundamentals/metapackage), however, the  attribute is unnecessary.</span></span> <span data-ttu-id="04be1-121">Пакет SDK для .NET Core позволяет автоматически выбрать версию этих пакетов, которая должна использоваться.</span><span class="sxs-lookup"><span data-stu-id="04be1-121">The .NET Core SDK can automatically select the version of these packages that should be used.</span></span>

### <a name="recommendation"></a><span data-ttu-id="04be1-122">Рекомендация</span><span class="sxs-lookup"><span data-stu-id="04be1-122">Recommendation</span></span>

<span data-ttu-id="04be1-123">Если вы ссылаетесь на пакеты `Microsoft.AspNetCore.App` или `Microsoft.AspNetCore.All`, не указывайте их версии.</span><span class="sxs-lookup"><span data-stu-id="04be1-123">When referencing the `Microsoft.AspNetCore.App` or `Microsoft.AspNetCore.All` packages, do not specify their version.</span></span> <span data-ttu-id="04be1-124">Если версия указана, пакет SDK может выдать предупреждение NETSDK1071.</span><span class="sxs-lookup"><span data-stu-id="04be1-124">If a version is specified, the SDK may produce warning NETSDK1071.</span></span> <span data-ttu-id="04be1-125">Чтобы устранить это предупреждение, удалите версию пакета, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="04be1-125">To fix this warning, remove the package version like in the following example:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.AspNetCore.App" />
</ItemGroup>
```

> <span data-ttu-id="04be1-126">Известная проблема. Пакет SDK для .NET Core 2.1 поддерживал только такой синтаксис, если в проекте также использовался Microsoft.NET.Sdk.Web.</span><span class="sxs-lookup"><span data-stu-id="04be1-126">Known issue: the .NET Core 2.1 SDK only supported this syntax when the project also uses Microsoft.NET.Sdk.Web.</span></span> <span data-ttu-id="04be1-127">Эта проблема устранена в пакете SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="04be1-127">This is resolved in the .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="04be1-128">Эти ссылки на метапакеты ASP.NET Core немного отличаются от ссылок на обычные пакеты NuGet.</span><span class="sxs-lookup"><span data-stu-id="04be1-128">These references to ASP.NET Core metapackages have a slightly different behavior from most normal NuGet packages.</span></span> <span data-ttu-id="04be1-129">[Зависящие от платформы развертывания](../deploying/index.md#publish-runtime-dependent) приложений, для которых используются эти метапакеты, автоматически получают все преимущества общей платформы ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="04be1-129">[Framework-dependent deployments](../deploying/index.md#publish-runtime-dependent) of applications that use these metapackages automatically take advantage of the ASP.NET Core shared framework.</span></span> <span data-ttu-id="04be1-130">Если используются метапакеты, с приложением **не** развертываются ресурсы из указанных по ссылке пакетов NuGet ASP.NET Core — общая платформа ASP.NET Core уже содержит эти ресурсы.</span><span class="sxs-lookup"><span data-stu-id="04be1-130">When you use the metapackages, **no** assets from the referenced ASP.NET Core NuGet packages are deployed with the application—the ASP.NET Core shared framework contains these assets.</span></span> <span data-ttu-id="04be1-131">Для ускорения запуска приложения ресурсы в общей платформе предварительно оптимизируются.</span><span class="sxs-lookup"><span data-stu-id="04be1-131">The assets in the shared framework are optimized for the target platform to improve application startup time.</span></span> <span data-ttu-id="04be1-132">Дополнительные сведения об общей платформе см. в статье [Упаковка дистрибутивов .NET Core](../distribution-packaging.md).</span><span class="sxs-lookup"><span data-stu-id="04be1-132">For more information about shared framework, see [.NET Core distribution packaging](../distribution-packaging.md).</span></span>

<span data-ttu-id="04be1-133">Если версия *указана*, она рассматривается как *минимальная* версия общей платформы ASP.NET Core для зависимых от платформы развертываний, а также как *точная* версия для автономных развертываний.</span><span class="sxs-lookup"><span data-stu-id="04be1-133">If a version *is* specified, it's treated as the *minimum* version of ASP.NET Core shared framework for framework-dependent deployments and as an *exact* version for self-contained deployments.</span></span> <span data-ttu-id="04be1-134">Это может привести к следующим результатам:</span><span class="sxs-lookup"><span data-stu-id="04be1-134">This can have the following consequences:</span></span>

- <span data-ttu-id="04be1-135">Если на сервере установлена более ранняя версия ASP.NET Core, чем указанная в PackageReference, процесс .NET Core не удастся запустить.</span><span class="sxs-lookup"><span data-stu-id="04be1-135">If the version of ASP.NET Core installed on the server is less than the version specified on the PackageReference, the .NET Core process fails to launch.</span></span> <span data-ttu-id="04be1-136">Обновления метапакета часто доступны на сайте NuGet.org раньше, чем в средах размещения, таких как Azure.</span><span class="sxs-lookup"><span data-stu-id="04be1-136">Updates to the metapackage are often available on NuGet.org before updates have been made available in hosting environments such as Azure.</span></span> <span data-ttu-id="04be1-137">Обновление версии PackageReference в ASP.NET Core может привести к сбою развернутого приложения.</span><span class="sxs-lookup"><span data-stu-id="04be1-137">Updating the version on the PackageReference to ASP.NET Core could cause a deployed application to fail.</span></span>
- <span data-ttu-id="04be1-138">Если приложение развертывается как [автономное развертывание](../deploying/index.md#publish-self-contained), оно не может содержать последние обновления системы безопасности для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="04be1-138">If the application is deployed as a [self-contained deployment](../deploying/index.md#publish-self-contained), the application may not contain the latest security updates to .NET Core.</span></span> <span data-ttu-id="04be1-139">Если версия не указана, пакет SDK может автоматически включить последнюю версию ASP.NET Core в автономное развертывание.</span><span class="sxs-lookup"><span data-stu-id="04be1-139">When a version isn't specified, the SDK can automatically include the newest version of ASP.NET Core in the self-contained deployment.</span></span>

## <a name="default-compilation-includes-in-net-core-projects"></a><span data-ttu-id="04be1-140">Компиляция по умолчанию, включенная в проекты .NET Core</span><span class="sxs-lookup"><span data-stu-id="04be1-140">Default compilation includes in .NET Core projects</span></span>

<span data-ttu-id="04be1-141">В рамках перехода на формат *CSPROJ* в последних версиях пакета SDK мы перенесли включения и исключения по умолчанию для элементов Compile и внедренные ресурсы в файлы свойств пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="04be1-141">With the move to the *csproj* format in the latest SDK versions, we've moved the default includes and excludes for compile items and embedded resources to the SDK properties files.</span></span> <span data-ttu-id="04be1-142">Это означает, что вам больше не нужно указывать эти элементы в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="04be1-142">This means that you no longer need to specify these items in your project file.</span></span>

<span data-ttu-id="04be1-143">Основной причиной этого является стремление очистить ваш файл проекта от всего лишнего.</span><span class="sxs-lookup"><span data-stu-id="04be1-143">The main reason for doing this is to reduce the clutter in your project file.</span></span> <span data-ttu-id="04be1-144">Значения по умолчанию в пакете SDK должны охватывать наиболее распространенные варианты использования, поэтому нет необходимости повторять их в каждом создаваемом проекте.</span><span class="sxs-lookup"><span data-stu-id="04be1-144">The defaults that are present in the SDK should cover most common use cases, so there is no need to repeat them in every project that you create.</span></span> <span data-ttu-id="04be1-145">Это позволяет уменьшить файлы проекта и гораздо проще читать их, а также вносить правки вручную.</span><span class="sxs-lookup"><span data-stu-id="04be1-145">This leads to smaller project files that are much easier to understand as well as edit by hand, if needed.</span></span>

<span data-ttu-id="04be1-146">Следующая таблица показывает, какой элемент и какие [стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) включены и исключены в пакете SDK:</span><span class="sxs-lookup"><span data-stu-id="04be1-146">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are both included and excluded in the SDK:</span></span>

| <span data-ttu-id="04be1-147">Элемент</span><span class="sxs-lookup"><span data-stu-id="04be1-147">Element</span></span>           | <span data-ttu-id="04be1-148">Стандартная маска включения</span><span class="sxs-lookup"><span data-stu-id="04be1-148">Include glob</span></span>                              | <span data-ttu-id="04be1-149">Стандартная маска исключения</span><span class="sxs-lookup"><span data-stu-id="04be1-149">Exclude glob</span></span>                                                  | <span data-ttu-id="04be1-150">Стандартная маска удаления</span><span class="sxs-lookup"><span data-stu-id="04be1-150">Remove glob</span></span>              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| <span data-ttu-id="04be1-151">Компилятор</span><span class="sxs-lookup"><span data-stu-id="04be1-151">Compile</span></span>           | <span data-ttu-id="04be1-152">\*\*/\*.cs (или другие расширения языка)</span><span class="sxs-lookup"><span data-stu-id="04be1-152">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="04be1-153">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="04be1-153">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="04be1-154">Н/Д</span><span class="sxs-lookup"><span data-stu-id="04be1-154">N/A</span></span>                      |
| <span data-ttu-id="04be1-155">ВнедренныйРесурс</span><span class="sxs-lookup"><span data-stu-id="04be1-155">EmbeddedResource</span></span>  | <span data-ttu-id="04be1-156">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="04be1-156">\*\*/\*.resx</span></span>                              | <span data-ttu-id="04be1-157">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="04be1-157">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="04be1-158">Н/Д</span><span class="sxs-lookup"><span data-stu-id="04be1-158">N/A</span></span>                      |
| <span data-ttu-id="04be1-159">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="04be1-159">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="04be1-160">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="04be1-160">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="04be1-161">\*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="04be1-161">\*\*/\*.cs; \*\*/\*.resx</span></span>   |

> [!NOTE]
> <span data-ttu-id="04be1-162">**Стандартная маска исключения** всегда исключает папки `./bin` и `./obj`, которые представлены свойствами MSBuild `$(BaseOutputPath)` и `$(BaseIntermediateOutputPath)` соответственно.</span><span class="sxs-lookup"><span data-stu-id="04be1-162">**Exclude glob** always excludes the `./bin` and `./obj` folders, which are represented by the `$(BaseOutputPath)` and `$(BaseIntermediateOutputPath)` MSBuild properties, respectively.</span></span> <span data-ttu-id="04be1-163">В целом все исключения представляются свойством `$(DefaultItemExcludes)`.</span><span class="sxs-lookup"><span data-stu-id="04be1-163">As a whole, all excludes are represented by `$(DefaultItemExcludes)`.</span></span>

<span data-ttu-id="04be1-164">Если в вашем проекте имеются стандартные маски и вы пытаетесь выполнить его сборку с помощью новейшего пакета SDK, появится следующая ошибка:</span><span class="sxs-lookup"><span data-stu-id="04be1-164">If you have globs in your project and you try to build it using the newest SDK, you'll get the following error:</span></span>

> <span data-ttu-id="04be1-165">Duplicate Compile items were included.</span><span class="sxs-lookup"><span data-stu-id="04be1-165">Duplicate Compile items were included.</span></span> <span data-ttu-id="04be1-166">The .NET SDK includes Compile items from your project directory by default.</span><span class="sxs-lookup"><span data-stu-id="04be1-166">The .NET SDK includes Compile items from your project directory by default.</span></span> <span data-ttu-id="04be1-167">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file. (Включены повторяющиеся элементы Compile. По умолчанию пакет SDK для .NET включает элементы Compile из каталога проекта. Можно удалить эти элементы из файла проекта или задать для свойства "EnableDefaultCompileItems" значение "false", чтобы явно включить их в файл проекта.)</span><span class="sxs-lookup"><span data-stu-id="04be1-167">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.</span></span>

<span data-ttu-id="04be1-168">Чтобы обойти эту ошибку, можно либо удалить явные элементы `Compile`, которые соответствуют указанным в предыдущей таблице, либо установить для свойства `<EnableDefaultCompileItems>` значение `false`, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="04be1-168">In order to get around this error, you can either remove the explicit `Compile` items that match the ones listed on the previous table, or you can set the `<EnableDefaultCompileItems>` property to `false`, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

<span data-ttu-id="04be1-169">Указание значения `false` для этого свойства отключает неявное включение, в результате чего возвращается поведение для предыдущих пакетов SDK, где требовалось задавать стандартные маски по умолчанию в проекте.</span><span class="sxs-lookup"><span data-stu-id="04be1-169">Setting this property to `false` will disable implicit inclusion, reverting to the behavior of previous SDKs where you had to specify the default globs in your project.</span></span>

<span data-ttu-id="04be1-170">Это изменение не затрагивает основные механизмы других включений.</span><span class="sxs-lookup"><span data-stu-id="04be1-170">This change does not modify the main mechanics of other includes.</span></span> <span data-ttu-id="04be1-171">Но если вы хотите указать, например, отдельные файлы для публикации вместе со своим приложением, для этого можно по-прежнему использовать привычные механизмы в *CSPROJ* (например, элемент `<Content>`).</span><span class="sxs-lookup"><span data-stu-id="04be1-171">However, if you wish to specify, for example, some files to get published with your app, you can still use the known mechanisms in *csproj* for that (for example, the `<Content>` element).</span></span>

<span data-ttu-id="04be1-172">`<EnableDefaultCompileItems>` отключает только стандартные маски `Compile`, не затрагивая все остальные, например неявную стандартную маску `None`, которая также применяется к элементам \*.cs.</span><span class="sxs-lookup"><span data-stu-id="04be1-172">`<EnableDefaultCompileItems>` only disables `Compile` globs but doesn't affect other globs, like the implicit `None` glob, which also applies to \*.cs items.</span></span> <span data-ttu-id="04be1-173">Из-за этого **обозреватель решений** продолжит показывать элементы \*.cs как часть проекта, включенную в виде элементов `None`.</span><span class="sxs-lookup"><span data-stu-id="04be1-173">Because of that, **Solution Explorer** will continue show \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="04be1-174">Аналогичным образом, можно задать `<EnableDefaultNoneItems>` как false для отключения неявной стандартной маски `None`:</span><span class="sxs-lookup"><span data-stu-id="04be1-174">In a similar way, you can set `<EnableDefaultNoneItems>` to false to disable the implicit `None` glob, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

<span data-ttu-id="04be1-175">Чтобы отключить **все неявные стандартные маски**, можно задать для свойства `<EnableDefaultItems>` значение `false`, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="04be1-175">To disable **all implicit globs**, you can set the `<EnableDefaultItems>` property to `false` as in the following example:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a><span data-ttu-id="04be1-176">Как просмотреть весь проект в представлении MSBuild</span><span class="sxs-lookup"><span data-stu-id="04be1-176">How to see the whole project as MSBuild sees it</span></span>

<span data-ttu-id="04be1-177">Хотя эти изменения csproj значительно упростили файлы проекта, возможно, вы захотите просмотреть полностью развернутый пакет в представлении MSBuild после включения пакета SDK и его целевых объектов.</span><span class="sxs-lookup"><span data-stu-id="04be1-177">While those csproj changes greatly simplify project files, you might want to see the fully expanded project as MSBuild sees it once the SDK and its targets are included.</span></span> <span data-ttu-id="04be1-178">Выполните предварительную обработку проекта, [включив](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) в команду [`dotnet msbuild`](dotnet-msbuild.md) параметр `/pp`. Это позволит просмотреть сведения об импортированных файлах, их источниках, вкладе в сборку без фактического создания проекта:</span><span class="sxs-lookup"><span data-stu-id="04be1-178">Preprocess the project with [the `/pp` switch](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) of the [`dotnet msbuild`](dotnet-msbuild.md) command, which shows which files are imported, their sources, and their contributions to the build without actually building the project:</span></span>

`dotnet msbuild -pp:fullproject.xml`

<span data-ttu-id="04be1-179">Если проект имеет несколько требуемых версий .NET Framework, результаты выполнения команды должны касаться только одной из них. Эту версию следует указать в качестве свойства MSBuild:</span><span class="sxs-lookup"><span data-stu-id="04be1-179">If the project has multiple target frameworks, the results of the command should be focused on only one of them by specifying it as an MSBuild property:</span></span>

`dotnet msbuild -p:TargetFramework=netcoreapp2.0 -pp:fullproject.xml`

## <a name="additions"></a><span data-ttu-id="04be1-180">Добавления</span><span class="sxs-lookup"><span data-stu-id="04be1-180">Additions</span></span>

### <a name="sdk-attribute"></a><span data-ttu-id="04be1-181">Атрибут Sdk</span><span class="sxs-lookup"><span data-stu-id="04be1-181">Sdk attribute</span></span>

<span data-ttu-id="04be1-182">Корневой элемент `<Project>` файла *CSPROJ* имеет новый атрибут `Sdk`.</span><span class="sxs-lookup"><span data-stu-id="04be1-182">The root `<Project>` element of the *.csproj* file has a new attribute called `Sdk`.</span></span> <span data-ttu-id="04be1-183">`Sdk` определяет, какой пакет SDK будет использоваться проектом.</span><span class="sxs-lookup"><span data-stu-id="04be1-183">`Sdk` specifies which SDK will be used by the project.</span></span> <span data-ttu-id="04be1-184">Пакет SDK, согласно описанию в [документе о слоях](cli-msbuild-architecture.md), является набором [задач](/visualstudio/msbuild/msbuild-tasks) и [целевых объектов](/visualstudio/msbuild/msbuild-targets) MSBuild, способным выполнять сборку кода .NET Core.</span><span class="sxs-lookup"><span data-stu-id="04be1-184">The SDK, as the [layering document](cli-msbuild-architecture.md) describes, is a set of MSBuild [tasks](/visualstudio/msbuild/msbuild-tasks) and [targets](/visualstudio/msbuild/msbuild-targets) that can build .NET Core code.</span></span> <span data-ttu-id="04be1-185">Для .NET Core доступны следующие пакеты SDK:</span><span class="sxs-lookup"><span data-stu-id="04be1-185">The following SDKs are available for .NET Core:</span></span>

1. <span data-ttu-id="04be1-186">пакет SDK для .NET Core с идентификатором `Microsoft.NET.Sdk`;</span><span class="sxs-lookup"><span data-stu-id="04be1-186">The .NET Core SDK with the ID of `Microsoft.NET.Sdk`</span></span>
2. <span data-ttu-id="04be1-187">веб-пакет SDK для .NET Core с идентификатором `Microsoft.NET.Sdk.Web`.</span><span class="sxs-lookup"><span data-stu-id="04be1-187">The .NET Core web SDK with the ID of `Microsoft.NET.Sdk.Web`</span></span>
3. <span data-ttu-id="04be1-188">пакет SDK для библиотеки классов Razor для .NET Core с идентификатором `Microsoft.NET.Sdk.Razor`.</span><span class="sxs-lookup"><span data-stu-id="04be1-188">The .NET Core Razor Class Library SDK with the ID of `Microsoft.NET.Sdk.Razor`</span></span>
4. <span data-ttu-id="04be1-189">Служба рабочей роли .NET Core с идентификатором `Microsoft.NET.Sdk.Worker` (с версии .NET Core 3.0)</span><span class="sxs-lookup"><span data-stu-id="04be1-189">The .NET Core Worker Service with the ID of `Microsoft.NET.Sdk.Worker` (since .NET Core 3.0)</span></span>
5. <span data-ttu-id="04be1-190">.NET Core WinForms и WPF с идентификатором `Microsoft.NET.Sdk.WindowsDesktop` (с версии .NET Core 3.0)</span><span class="sxs-lookup"><span data-stu-id="04be1-190">The .NET Core WinForms and WPF with the ID of `Microsoft.NET.Sdk.WindowsDesktop` (since .NET Core 3.0)</span></span>

<span data-ttu-id="04be1-191">Чтобы использовать инструменты и выполнять сборку кода .NET Core, в качестве значения атрибута `Sdk` в элементе `<Project>` нужно задать один из этих идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="04be1-191">You need to have the `Sdk` attribute set to one of those IDs on the `<Project>` element in order to use the .NET Core tools and build your code.</span></span>

### <a name="packagereference"></a><span data-ttu-id="04be1-192">PackageReference</span><span class="sxs-lookup"><span data-stu-id="04be1-192">PackageReference</span></span>

<span data-ttu-id="04be1-193">Элемент `<PackageReference>` указывает [зависимость NuGet в проекте](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="04be1-193">A `<PackageReference>` item element specifies a [NuGet dependency in the project](/nuget/consume-packages/package-references-in-project-files).</span></span> <span data-ttu-id="04be1-194">Атрибут `Include` указывает идентификатор пакета.</span><span class="sxs-lookup"><span data-stu-id="04be1-194">The `Include` attribute specifies the package ID.</span></span>

```xml
<PackageReference Include="package-id" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a><span data-ttu-id="04be1-195">Version</span><span class="sxs-lookup"><span data-stu-id="04be1-195">Version</span></span>

<span data-ttu-id="04be1-196">Обязательный атрибут `Version` указывает версию пакета для восстановления.</span><span class="sxs-lookup"><span data-stu-id="04be1-196">The required `Version` attribute specifies the version of the package to restore.</span></span> <span data-ttu-id="04be1-197">Этот атрибут подчиняется правилам схемы [управления версиями NuGet](/nuget/reference/package-versioning#version-ranges-and-wildcards).</span><span class="sxs-lookup"><span data-stu-id="04be1-197">The attribute respects the rules of the [NuGet versioning](/nuget/reference/package-versioning#version-ranges-and-wildcards) scheme.</span></span> <span data-ttu-id="04be1-198">По умолчанию выбирается минимальная из заданных версий (включительно).</span><span class="sxs-lookup"><span data-stu-id="04be1-198">The default behavior is a minimum version, inclusive match.</span></span> <span data-ttu-id="04be1-199">Например, если указать `Version="1.2.3"`, это будет эквивалентно нотации NuGet `[1.2.3, )` и означает, что при разрешении пакет будет иметь версию 1.2.3, если она доступна, или более высокую, если нет.</span><span class="sxs-lookup"><span data-stu-id="04be1-199">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3, )` and means the resolved package will have the version 1.2.3 if available or greater otherwise.</span></span>

#### <a name="includeassets-excludeassets-and-privateassets"></a><span data-ttu-id="04be1-200">IncludeAssets, ExcludeAssets и PrivateAssets</span><span class="sxs-lookup"><span data-stu-id="04be1-200">IncludeAssets, ExcludeAssets, and PrivateAssets</span></span>

<span data-ttu-id="04be1-201">Атрибут `IncludeAssets` указывает, какие ресурсы пакета, указанные `<PackageReference>`, следует использовать.</span><span class="sxs-lookup"><span data-stu-id="04be1-201">`IncludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed.</span></span> <span data-ttu-id="04be1-202">По умолчанию включаются все ресурсы пакета.</span><span class="sxs-lookup"><span data-stu-id="04be1-202">By default, all package assets are included.</span></span>

<span data-ttu-id="04be1-203">Атрибут `ExcludeAssets` указывает, какие ресурсы пакета, указанные `<PackageReference>`, не следует использовать.</span><span class="sxs-lookup"><span data-stu-id="04be1-203">`ExcludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should not be consumed.</span></span>

<span data-ttu-id="04be1-204">Атрибут `PrivateAssets` указывает, какие ресурсы пакета, указанные `<PackageReference>`, следует использовать, но не следует передавать в следующий проект.</span><span class="sxs-lookup"><span data-stu-id="04be1-204">`PrivateAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed but not flow to the next project.</span></span> <span data-ttu-id="04be1-205">Если этот атрибут отсутствует, ресурсы `Analyzers`, `Build` и `ContentFiles` по умолчанию являются частными.</span><span class="sxs-lookup"><span data-stu-id="04be1-205">The `Analyzers`, `Build` and `ContentFiles` assets are private by default when this attribute is not present.</span></span>

> [!NOTE]
> <span data-ttu-id="04be1-206">`PrivateAssets` эквивалентен элементу *project.json*/*xproj* `SuppressParent`.</span><span class="sxs-lookup"><span data-stu-id="04be1-206">`PrivateAssets` is equivalent to the *project.json*/*xproj* `SuppressParent` element.</span></span>

<span data-ttu-id="04be1-207">Эти атрибуты могут содержать один или несколько следующих элементов (если их больше одного, они разделяются точкой с запятой `;`):</span><span class="sxs-lookup"><span data-stu-id="04be1-207">These attributes can contain one or more of the following items, separated by the semicolon `;` character if more than one is listed:</span></span>

- <span data-ttu-id="04be1-208">`Compile` — содержимое папки *lib* доступно для компиляции.</span><span class="sxs-lookup"><span data-stu-id="04be1-208">`Compile` – the contents of the *lib* folder are available to compile against.</span></span>
- <span data-ttu-id="04be1-209">`Runtime` — содержимое папки *runtime* распределяется.</span><span class="sxs-lookup"><span data-stu-id="04be1-209">`Runtime` – the contents of the *runtime* folder are distributed.</span></span>
- <span data-ttu-id="04be1-210">`ContentFiles` — используется содержимое папки *contentfiles*.</span><span class="sxs-lookup"><span data-stu-id="04be1-210">`ContentFiles` – the contents of the *contentfiles* folder are used.</span></span>
- <span data-ttu-id="04be1-211">`Build` — используются свойства и целевые объекты в папке *build*.</span><span class="sxs-lookup"><span data-stu-id="04be1-211">`Build` – the props/targets in the *build* folder are used.</span></span>
- <span data-ttu-id="04be1-212">`Native` — содержимое копируется из основных ресурсов в папку *output* среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="04be1-212">`Native` – the contents from native assets are copied to the *output* folder for runtime.</span></span>
- <span data-ttu-id="04be1-213">`Analyzers` — используются анализаторы.</span><span class="sxs-lookup"><span data-stu-id="04be1-213">`Analyzers` – the analyzers are used.</span></span>

<span data-ttu-id="04be1-214">Кроме того, атрибут может содержать следующие значения.</span><span class="sxs-lookup"><span data-stu-id="04be1-214">Alternatively, the attribute can contain:</span></span>

- <span data-ttu-id="04be1-215">`None` — не используется ни один ресурс.</span><span class="sxs-lookup"><span data-stu-id="04be1-215">`None` – none of the assets are used.</span></span>
- <span data-ttu-id="04be1-216">`All` — используются все ресурсы.</span><span class="sxs-lookup"><span data-stu-id="04be1-216">`All` – all assets are used.</span></span>

### <a name="dotnetclitoolreference"></a><span data-ttu-id="04be1-217">DotNetCliToolReference</span><span class="sxs-lookup"><span data-stu-id="04be1-217">DotNetCliToolReference</span></span>

<span data-ttu-id="04be1-218">Элемент `<DotNetCliToolReference>` указывает средство интерфейса командной строки, которое пользователь хочет восстановить в контексте проекта.</span><span class="sxs-lookup"><span data-stu-id="04be1-218">A `<DotNetCliToolReference>` item element specifies the CLI tool that the user wants to restore in the context of the project.</span></span> <span data-ttu-id="04be1-219">Этот элемент используется вместо узла `tools` в файле *project.json*.</span><span class="sxs-lookup"><span data-stu-id="04be1-219">It's a replacement for the `tools` node in *project.json*.</span></span>

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

<span data-ttu-id="04be1-220">Обратите внимание, что `DotNetCliToolReference` [теперь считается нерекомендуемый](https://github.com/dotnet/announcements/issues/107). Вместо него используйте [локальные средства .NET Core](https://aka.ms/local-tools).</span><span class="sxs-lookup"><span data-stu-id="04be1-220">Note that `DotNetCliToolReference` is [now deprecated](https://github.com/dotnet/announcements/issues/107) in favor of [.NET Core Local Tools](https://aka.ms/local-tools).</span></span>

#### <a name="version"></a><span data-ttu-id="04be1-221">Version</span><span class="sxs-lookup"><span data-stu-id="04be1-221">Version</span></span>

<span data-ttu-id="04be1-222">`Version` указывает версию пакета для восстановления.</span><span class="sxs-lookup"><span data-stu-id="04be1-222">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="04be1-223">Этот атрибут подчиняется правилам схемы [управления версиями NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="04be1-223">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="04be1-224">По умолчанию выбирается минимальная из заданных версий (включительно).</span><span class="sxs-lookup"><span data-stu-id="04be1-224">The default behavior is a minimum version, inclusive match.</span></span> <span data-ttu-id="04be1-225">Например, если указать `Version="1.2.3"`, это будет эквивалентно нотации NuGet `[1.2.3, )` и означает, что при разрешении пакет будет иметь версию 1.2.3, если она доступна, или более высокую, если нет.</span><span class="sxs-lookup"><span data-stu-id="04be1-225">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3, )` and means the resolved package will have the version 1.2.3 if available or greater otherwise.</span></span>

### <a name="runtimeidentifiers"></a><span data-ttu-id="04be1-226">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="04be1-226">RuntimeIdentifiers</span></span>

<span data-ttu-id="04be1-227">Элемент свойства `<RuntimeIdentifiers>` позволяет указать для проекта список [идентификаторов среды выполнения (RID)](../rid-catalog.md) (в качестве разделителя используется точка с запятой).</span><span class="sxs-lookup"><span data-stu-id="04be1-227">The `<RuntimeIdentifiers>` property element lets you specify a semicolon-delimited list of [Runtime Identifiers (RIDs)](../rid-catalog.md) for the project.</span></span>
<span data-ttu-id="04be1-228">Идентификаторы позволяют публиковать автономные развертывания.</span><span class="sxs-lookup"><span data-stu-id="04be1-228">RIDs enable publishing self-contained deployments.</span></span>

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a><span data-ttu-id="04be1-229">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="04be1-229">RuntimeIdentifier</span></span>

<span data-ttu-id="04be1-230">Элемент свойства `<RuntimeIdentifier>` позволяет указать для проекта только один [идентификатор среды выполнения](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="04be1-230">The `<RuntimeIdentifier>` property element allows you to specify only one [Runtime Identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="04be1-231">Идентификатор среды выполнения позволяет опубликовать автономное развертывание.</span><span class="sxs-lookup"><span data-stu-id="04be1-231">The RID enables publishing a self-contained deployment.</span></span>

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

<span data-ttu-id="04be1-232">Используйте `<RuntimeIdentifiers>` (во множественном числе) вместо этого, если вам нужна публикация для различных сред.</span><span class="sxs-lookup"><span data-stu-id="04be1-232">Use `<RuntimeIdentifiers>` (plural) instead if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="04be1-233">`<RuntimeIdentifier>` может ускорить создание сборок, когда требуется только одна среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="04be1-233">`<RuntimeIdentifier>` can provide faster builds when only a single runtime is required.</span></span>

### <a name="packagetargetfallback"></a><span data-ttu-id="04be1-234">PackageTargetFallback</span><span class="sxs-lookup"><span data-stu-id="04be1-234">PackageTargetFallback</span></span>

<span data-ttu-id="04be1-235">Элемент свойства `<PackageTargetFallback>` позволяет указать набор совместимых целевых объектов, которые следует использовать при восстановлении пакетов.</span><span class="sxs-lookup"><span data-stu-id="04be1-235">The `<PackageTargetFallback>` property element allows you to specify a set of compatible targets to be used when restoring packages.</span></span> <span data-ttu-id="04be1-236">Он разрешает пакетам, использующим dotnet [TxM (моникер целевой версии x)](/nuget/schema/target-frameworks), взаимодействовать с пакетами, которые не объявляют dotnet TxM.</span><span class="sxs-lookup"><span data-stu-id="04be1-236">It's designed to allow packages that use the dotnet [TxM (Target x Moniker)](/nuget/schema/target-frameworks) to operate with packages that don't declare a dotnet TxM.</span></span> <span data-ttu-id="04be1-237">Если в проекте используется dotnet TxM, все пакеты, от которых вы зависите, должны также содержать dotnet TxM. В противном случае нужно добавить `<PackageTargetFallback>` в проект, чтобы обеспечить совместимость с платформами, отличными от dotnet.</span><span class="sxs-lookup"><span data-stu-id="04be1-237">If your project uses the dotnet TxM, then all the packages it depends on must also have a dotnet TxM, unless you add the `<PackageTargetFallback>` to your project in order to allow non-dotnet platforms to be compatible with dotnet.</span></span>

<span data-ttu-id="04be1-238">В следующем примере приводятся резервные варианты для всех целевых объектов в проекте:</span><span class="sxs-lookup"><span data-stu-id="04be1-238">The following example provides the fallbacks for all targets in your project:</span></span>

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

<span data-ttu-id="04be1-239">В следующем примере приводятся резервные варианты только для целевого объекта `netcoreapp2.1`:</span><span class="sxs-lookup"><span data-stu-id="04be1-239">The following example specifies the fallbacks only for the `netcoreapp2.1` target:</span></span>

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp2.1'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="build-events"></a><span data-ttu-id="04be1-240">События сборки</span><span class="sxs-lookup"><span data-stu-id="04be1-240">Build events</span></span>

<span data-ttu-id="04be1-241">Способ, которым события перед сборкой и после сборки указываются в файле проекта, изменился.</span><span class="sxs-lookup"><span data-stu-id="04be1-241">The way that pre-build and post-build events are specified in the project file has changed.</span></span> <span data-ttu-id="04be1-242">Свойства PreBuildEvent и PostBuildEvent не рекомендуется использовать в проектах с форматом в стиле пакета SDK из-за того, что такие макросы, как $(ProjectDir), не будут разрешаться.</span><span class="sxs-lookup"><span data-stu-id="04be1-242">The properties PreBuildEvent and PostBuildEvent are not recommended in the SDK-style project format, because macros such as $(ProjectDir) are not resolved.</span></span> <span data-ttu-id="04be1-243">Например, следующий код больше не поддерживается:</span><span class="sxs-lookup"><span data-stu-id="04be1-243">For example, the following code is no longer supported:</span></span>

```xml
<PropertyGroup>
    <PreBuildEvent>"$(ProjectDir)PreBuildEvent.bat" "$(ProjectDir)..\" "$(ProjectDir)" "$(TargetDir)"</PreBuildEvent>
</PropertyGroup>
```

<span data-ttu-id="04be1-244">Для проектов в стиле пакета SDK используйте целевой объект MSBuild с именем `PreBuild` или `PostBuild` и задайте свойство `BeforeTargets` для `PreBuild` или свойство `AfterTargets` для `PostBuild`.</span><span class="sxs-lookup"><span data-stu-id="04be1-244">In SDK-style projects, use an MSBuild target named `PreBuild` or `PostBuild` and set the `BeforeTargets` property for `PreBuild` or the `AfterTargets` property for `PostBuild`.</span></span> <span data-ttu-id="04be1-245">В предыдущем примере используйте такой код:</span><span class="sxs-lookup"><span data-stu-id="04be1-245">For the preceding example, use the following code:</span></span>

```xml
<Target Name="PreBuild" BeforeTargets="PreBuildEvent">
    <Exec Command="&quot;$(ProjectDir)PreBuildEvent.bat&quot; &quot;$(ProjectDir)..\&quot; &quot;$(ProjectDir)&quot; &quot;$(TargetDir)&quot;" />
</Target>

<Target Name="PostBuild" AfterTargets="PostBuildEvent">
   <Exec Command="echo Output written to $(TargetDir)" />
</Target>
```

> [!NOTE]
><span data-ttu-id="04be1-246">Для целевых объектов MSBuild можно использовать любое имя, но интегрированная среда разработки Visual Studio распознает целевые объекты `PreBuild` и `PostBuild`, поэтому мы рекомендуем использовать эти имена, чтобы можно было изменять команды в интегрированной среде разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="04be1-246">You can use any name for the MSBuild targets, but the Visual Studio IDE recognizes `PreBuild` and `PostBuild` targets, so we recommend using those names so that you can edit the commands in the Visual Studio IDE.</span></span>

## <a name="nuget-metadata-properties"></a><span data-ttu-id="04be1-247">Свойства метаданных NuGet</span><span class="sxs-lookup"><span data-stu-id="04be1-247">NuGet metadata properties</span></span>

<span data-ttu-id="04be1-248">При переходе к MSBuild мы переместили входные метаданные, которые использовались при упаковке пакета NuGet из *project.json* в файлы *CSPROJ*.</span><span class="sxs-lookup"><span data-stu-id="04be1-248">With the move to MSBuild, we have moved the input metadata that is used when packing a NuGet package from *project.json* to *.csproj* files.</span></span> <span data-ttu-id="04be1-249">Входными данными являются свойства MSBuild, поэтому они должны входить в группу `<PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="04be1-249">The inputs are MSBuild properties so they have to go within a `<PropertyGroup>` group.</span></span> <span data-ttu-id="04be1-250">Ниже представлен список свойств, которые используются как входные данные в процессе упаковки при использовании команды `dotnet pack` или целевого объекта `Pack` MSBuild, входящего в SDK:</span><span class="sxs-lookup"><span data-stu-id="04be1-250">The following is the list of properties that are used as inputs to the packing process when using the `dotnet pack` command or the `Pack` MSBuild target that is part of the SDK:</span></span>

### <a name="ispackable"></a><span data-ttu-id="04be1-251">IsPackable</span><span class="sxs-lookup"><span data-stu-id="04be1-251">IsPackable</span></span>

<span data-ttu-id="04be1-252">Логическое значение, которое указывает, можно ли упаковать проект.</span><span class="sxs-lookup"><span data-stu-id="04be1-252">A Boolean value that specifies whether the project can be packed.</span></span> <span data-ttu-id="04be1-253">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="04be1-253">The default value is `true`.</span></span>

### <a name="packageversion"></a><span data-ttu-id="04be1-254">PackageVersion</span><span class="sxs-lookup"><span data-stu-id="04be1-254">PackageVersion</span></span>

<span data-ttu-id="04be1-255">Указывает версию, которую будет иметь итоговый пакет.</span><span class="sxs-lookup"><span data-stu-id="04be1-255">Specifies the version that the resulting package will have.</span></span> <span data-ttu-id="04be1-256">Принимает все формы строки версии NuGet.</span><span class="sxs-lookup"><span data-stu-id="04be1-256">Accepts all forms of NuGet version string.</span></span> <span data-ttu-id="04be1-257">По умолчанию используется значение `$(Version)`, то есть значение свойства `Version` в проекте.</span><span class="sxs-lookup"><span data-stu-id="04be1-257">Default is the value of `$(Version)`, that is, of the property `Version` in the project.</span></span>

### <a name="packageid"></a><span data-ttu-id="04be1-258">PackageId</span><span class="sxs-lookup"><span data-stu-id="04be1-258">PackageId</span></span>

<span data-ttu-id="04be1-259">Указывает имя для итогового пакета.</span><span class="sxs-lookup"><span data-stu-id="04be1-259">Specifies the name for the resulting package.</span></span> <span data-ttu-id="04be1-260">Если значение не указано, операция `pack` по умолчанию использует в качестве имени пакета `AssemblyName` или имя каталога.</span><span class="sxs-lookup"><span data-stu-id="04be1-260">If not specified, the `pack` operation will default to using the `AssemblyName` or directory name as the name of the package.</span></span>

### <a name="title"></a><span data-ttu-id="04be1-261">Заголовок</span><span class="sxs-lookup"><span data-stu-id="04be1-261">Title</span></span>

<span data-ttu-id="04be1-262">Понятный заголовок пакета, обычно используемый при отображении пользовательского интерфейса, как на сайте nuget.org и в диспетчере пакетов Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="04be1-262">A human-friendly title of the package, typically used in UI displays as on nuget.org and the Package Manager in Visual Studio.</span></span> <span data-ttu-id="04be1-263">Если значение не указано, используется идентификатор пакета.</span><span class="sxs-lookup"><span data-stu-id="04be1-263">If not specified, the package ID is used instead.</span></span>

### <a name="authors"></a><span data-ttu-id="04be1-264">Authors</span><span class="sxs-lookup"><span data-stu-id="04be1-264">Authors</span></span>

<span data-ttu-id="04be1-265">Разделенный точками с запятой список авторов пакетов, совпадающих с именами профилей на сайте nuget.org. Они отображаются в коллекции NuGet на сайте nuget.org и используются для перекрестных ссылок на пакеты тех же авторов.</span><span class="sxs-lookup"><span data-stu-id="04be1-265">A semicolon-separated list of packages authors, matching the profile names on nuget.org. These are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span>

### <a name="packagedescription"></a><span data-ttu-id="04be1-266">PackageDescription</span><span class="sxs-lookup"><span data-stu-id="04be1-266">PackageDescription</span></span>

<span data-ttu-id="04be1-267">Подробное описание пакета для отображения пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="04be1-267">A long description of the package for UI display.</span></span>

### <a name="description"></a><span data-ttu-id="04be1-268">Описание</span><span class="sxs-lookup"><span data-stu-id="04be1-268">Description</span></span>

<span data-ttu-id="04be1-269">Подробное описание сборки.</span><span class="sxs-lookup"><span data-stu-id="04be1-269">A long description for the assembly.</span></span> <span data-ttu-id="04be1-270">Если `PackageDescription` не указывать, это свойство также будет использоваться в качестве описания пакета.</span><span class="sxs-lookup"><span data-stu-id="04be1-270">If `PackageDescription` is not specified, then this property is also used as the description of the package.</span></span>

### <a name="copyright"></a><span data-ttu-id="04be1-271">Copyright</span><span class="sxs-lookup"><span data-stu-id="04be1-271">Copyright</span></span>

<span data-ttu-id="04be1-272">Сведения об авторских правах для пакета.</span><span class="sxs-lookup"><span data-stu-id="04be1-272">Copyright details for the package.</span></span>

### <a name="packagerequirelicenseacceptance"></a><span data-ttu-id="04be1-273">PackageRequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="04be1-273">PackageRequireLicenseAcceptance</span></span>

<span data-ttu-id="04be1-274">Логическое значение, указывающее, должен ли клиент просить потребителя принять условия лицензии перед установкой пакета.</span><span class="sxs-lookup"><span data-stu-id="04be1-274">A Boolean value that specifies whether the client must prompt the consumer to accept the package license before installing the package.</span></span> <span data-ttu-id="04be1-275">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="04be1-275">The default is `false`.</span></span>

### <a name="developmentdependency"></a><span data-ttu-id="04be1-276">DevelopmentDependency</span><span class="sxs-lookup"><span data-stu-id="04be1-276">DevelopmentDependency</span></span>

<span data-ttu-id="04be1-277">Логическое значение, указывающее на то, помечен ли пакет как зависимость только для разработки, что позволяет запретить его включение в качестве зависимости в другие пакеты.</span><span class="sxs-lookup"><span data-stu-id="04be1-277">A Boolean value that specifies whether the package is marked as a development-only dependency, which prevents the package from being included as a dependency in other packages.</span></span> <span data-ttu-id="04be1-278">При использовании PackageReference (NuGet 4.8 и более поздних версий) этот флаг также указывает на то, что ресурсы времени компиляции исключены из компиляции.</span><span class="sxs-lookup"><span data-stu-id="04be1-278">With PackageReference (NuGet 4.8+), this flag also means that compile-time assets are excluded from compilation.</span></span> <span data-ttu-id="04be1-279">Дополнительные сведения см. в статье [DevelopmentDependency support for PackageReference](https://github.com/NuGet/Home/wiki/DevelopmentDependency-support-for-PackageReference) (Поддержка DevelopmentDependency для PackageReference).</span><span class="sxs-lookup"><span data-stu-id="04be1-279">For more information, see [DevelopmentDependency support for PackageReference](https://github.com/NuGet/Home/wiki/DevelopmentDependency-support-for-PackageReference).</span></span>

### <a name="packagelicenseexpression"></a><span data-ttu-id="04be1-280">PackageLicenseExpression</span><span class="sxs-lookup"><span data-stu-id="04be1-280">PackageLicenseExpression</span></span>

<span data-ttu-id="04be1-281">[Идентификатор лицензии SPDX](https://spdx.org/licenses/) или выражение.</span><span class="sxs-lookup"><span data-stu-id="04be1-281">An [SPDX license identifier](https://spdx.org/licenses/) or expression.</span></span> <span data-ttu-id="04be1-282">Например, `Apache-2.0`.</span><span class="sxs-lookup"><span data-stu-id="04be1-282">For example, `Apache-2.0`.</span></span>

<span data-ttu-id="04be1-283">Здесь приведен полный список [идентификаторов лицензии SPDX](https://spdx.org/licenses/).</span><span class="sxs-lookup"><span data-stu-id="04be1-283">Here is the complete list of [SPDX license identifiers](https://spdx.org/licenses/).</span></span> <span data-ttu-id="04be1-284">Если используется выражение типа лицензии, NuGet.org принимает только утвержденные OSI или FSF лицензии.</span><span class="sxs-lookup"><span data-stu-id="04be1-284">NuGet.org accepts only OSI or FSF approved licenses when using license type expression.</span></span>

<span data-ttu-id="04be1-285">Точный синтаксис выражений лицензии описан ниже в спецификации метаязыка [ABNF](https://tools.ietf.org/html/rfc5234).</span><span class="sxs-lookup"><span data-stu-id="04be1-285">The exact syntax of the license expressions is described below in [ABNF](https://tools.ietf.org/html/rfc5234).</span></span>

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
> <span data-ttu-id="04be1-286">За один раз можно указать только одно из свойств `PackageLicenseExpression`, `PackageLicenseFile` и `PackageLicenseUrl`.</span><span class="sxs-lookup"><span data-stu-id="04be1-286">Only one of `PackageLicenseExpression`, `PackageLicenseFile` and `PackageLicenseUrl` can be specified at a time.</span></span>

### <a name="packagelicensefile"></a><span data-ttu-id="04be1-287">PackageLicenseFile</span><span class="sxs-lookup"><span data-stu-id="04be1-287">PackageLicenseFile</span></span>

<span data-ttu-id="04be1-288">Путь к файлу лицензии в пакете, если вы используете лицензию, которой не назначен идентификатор SPDX, или пользовательскую лицензию (в противном случае предпочтительнее использовать свойство `PackageLicenseExpression`).</span><span class="sxs-lookup"><span data-stu-id="04be1-288">Path to a license file within the package if you are using a license that hasn’t been assigned an SPDX identifier, or it is a custom license (Otherwise `PackageLicenseExpression` is preferred)</span></span>

<span data-ttu-id="04be1-289">Заменяет свойство `PackageLicenseUrl`, не может сочетаться со свойством `PackageLicenseExpression`. Требуется Visual Studio версии 15.9.4 и пакет SDK для .NET 2.1.502, 2.2.101 и выше.</span><span class="sxs-lookup"><span data-stu-id="04be1-289">Replaces `PackageLicenseUrl`, can't be combined with `PackageLicenseExpression`, and requires Visual Studio version 15.9.4 and .NET SDK 2.1.502 or 2.2.101 or newer.</span></span>

<span data-ttu-id="04be1-290">Вам необходимо убедиться, что файл лицензии упакован. Для этого явно добавьте его в проект. Пример использования:</span><span class="sxs-lookup"><span data-stu-id="04be1-290">You will need to ensure the license file is packed by adding it explicitly to the project, example usage:</span></span>

```xml
<PropertyGroup>
  <PackageLicenseFile>LICENSE.txt</PackageLicenseFile>
</PropertyGroup>
<ItemGroup>
  <None Include="licenses\LICENSE.txt" Pack="true" PackagePath="$(PackageLicenseFile)"/>
</ItemGroup>
```

### <a name="packagelicenseurl"></a><span data-ttu-id="04be1-291">PackageLicenseUrl</span><span class="sxs-lookup"><span data-stu-id="04be1-291">PackageLicenseUrl</span></span>

<span data-ttu-id="04be1-292">URL-адрес лицензии, применимой к пакету.</span><span class="sxs-lookup"><span data-stu-id="04be1-292">A URL to the license that is applicable to the package.</span></span> <span data-ttu-id="04be1-293">(_Отмечено как нерекомендуемое начиная с Visual Studio версии 15.9.4, пакета SDK для .NET 2.1.502 и 2.2.101._ )</span><span class="sxs-lookup"><span data-stu-id="04be1-293">(_deprecated since Visual Studio 15.9.4, .NET SDK 2.1.502 and 2.2.101_)</span></span>

### <a name="packageiconurl"></a><span data-ttu-id="04be1-294">PackageIconUrl</span><span class="sxs-lookup"><span data-stu-id="04be1-294">PackageIconUrl</span></span>

<span data-ttu-id="04be1-295">URL-адрес для изображения размером 64x64 с прозрачным фоном, используемого в качестве значка для пакета при отображении пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="04be1-295">A URL for a 64x64 image with transparent background to use as the icon for the package in UI display.</span></span>

### <a name="packagereleasenotes"></a><span data-ttu-id="04be1-296">PackageReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="04be1-296">PackageReleaseNotes</span></span>

<span data-ttu-id="04be1-297">Заметки о выпуске для пакета.</span><span class="sxs-lookup"><span data-stu-id="04be1-297">Release notes for the package.</span></span>

### <a name="packagetags"></a><span data-ttu-id="04be1-298">PackageTags</span><span class="sxs-lookup"><span data-stu-id="04be1-298">PackageTags</span></span>

<span data-ttu-id="04be1-299">Разделенный точками с запятой список тегов, обозначающий пакет.</span><span class="sxs-lookup"><span data-stu-id="04be1-299">A semicolon-delimited list of tags that designates the package.</span></span>

### <a name="packageoutputpath"></a><span data-ttu-id="04be1-300">PackageOutputPath</span><span class="sxs-lookup"><span data-stu-id="04be1-300">PackageOutputPath</span></span>

<span data-ttu-id="04be1-301">Определяет выходной путь для размещения упакованного пакета.</span><span class="sxs-lookup"><span data-stu-id="04be1-301">Determines the output path in which the packed package will be dropped.</span></span> <span data-ttu-id="04be1-302">Значение по умолчанию — `$(OutputPath)`.</span><span class="sxs-lookup"><span data-stu-id="04be1-302">Default is `$(OutputPath)`.</span></span>

### <a name="includesymbols"></a><span data-ttu-id="04be1-303">IncludeSymbols</span><span class="sxs-lookup"><span data-stu-id="04be1-303">IncludeSymbols</span></span>
<span data-ttu-id="04be1-304">Это логическое значение указывает, должен ли пакет создавать дополнительный пакет символов при упаковке проекта.</span><span class="sxs-lookup"><span data-stu-id="04be1-304">This Boolean value indicates whether the package should create an additional symbols package when the project is packed.</span></span> <span data-ttu-id="04be1-305">Форматом пакета символов управляет свойство `SymbolPackageFormat`.</span><span class="sxs-lookup"><span data-stu-id="04be1-305">The symbols package's format is controlled by the `SymbolPackageFormat` property.</span></span>

### <a name="symbolpackageformat"></a><span data-ttu-id="04be1-306">SymbolPackageFormat</span><span class="sxs-lookup"><span data-stu-id="04be1-306">SymbolPackageFormat</span></span>
<span data-ttu-id="04be1-307">Задает формат пакета символов.</span><span class="sxs-lookup"><span data-stu-id="04be1-307">Specifies the format of the symbols package.</span></span> <span data-ttu-id="04be1-308">Если задано symbols.nupkg, создается пакет символов в старом формате с расширением *. symbols.nupkg*, содержащий PDB-файлы, библиотеки DLL и другие выходные файлы.</span><span class="sxs-lookup"><span data-stu-id="04be1-308">If "symbols.nupkg", a legacy symbols package will be created with a *.symbols.nupkg* extension containing PDBs, DLLs, and other output files.</span></span> <span data-ttu-id="04be1-309">Если задано snupkg, создается пакет символов snupkg, содержащий переносимые PDB-файлы.</span><span class="sxs-lookup"><span data-stu-id="04be1-309">If "snupkg", a snupkg symbol package will be created containing the portable PDBs.</span></span> <span data-ttu-id="04be1-310">По умолчанию задано symbols.nupkg.</span><span class="sxs-lookup"><span data-stu-id="04be1-310">Default is "symbols.nupkg".</span></span>

### <a name="includesource"></a><span data-ttu-id="04be1-311">IncludeSource</span><span class="sxs-lookup"><span data-stu-id="04be1-311">IncludeSource</span></span>

<span data-ttu-id="04be1-312">Это логическое значение указывает, должен ли процесс упаковки создавать исходный пакет.</span><span class="sxs-lookup"><span data-stu-id="04be1-312">This Boolean value indicates whether the pack process should create a source package.</span></span> <span data-ttu-id="04be1-313">Исходный пакет содержит библиотеку исходного кода, а также файлы PDB.</span><span class="sxs-lookup"><span data-stu-id="04be1-313">The source package contains the library's source code as well as PDB files.</span></span> <span data-ttu-id="04be1-314">Исходные файлы помещаются в каталог `src/ProjectName` итогового файла пакета.</span><span class="sxs-lookup"><span data-stu-id="04be1-314">Source files are put under the `src/ProjectName` directory in the resulting package file.</span></span>

### <a name="istool"></a><span data-ttu-id="04be1-315">IsTool</span><span class="sxs-lookup"><span data-stu-id="04be1-315">IsTool</span></span>

<span data-ttu-id="04be1-316">Указывает, копируются ли все выходные файлы в папку *tools* вместо папки *lib*.</span><span class="sxs-lookup"><span data-stu-id="04be1-316">Specifies whether all output files are copied to the *tools* folder instead of the *lib* folder.</span></span> <span data-ttu-id="04be1-317">Это свойство отличается от `DotNetCliTool`, которое указывается путем задания `PackageType` в файле *CSPROJ*.</span><span class="sxs-lookup"><span data-stu-id="04be1-317">This is different from a `DotNetCliTool`, which is specified by setting the `PackageType` in the *.csproj* file.</span></span>

### <a name="repositoryurl"></a><span data-ttu-id="04be1-318">RepositoryUrl</span><span class="sxs-lookup"><span data-stu-id="04be1-318">RepositoryUrl</span></span>

<span data-ttu-id="04be1-319">Указывает URL-адрес репозитория, где находится исходный код для пакета или откуда выполняется его сборка.</span><span class="sxs-lookup"><span data-stu-id="04be1-319">Specifies the URL for the repository where the source code for the package resides and/or from which it's being built.</span></span>

### <a name="repositorytype"></a><span data-ttu-id="04be1-320">RepositoryType</span><span class="sxs-lookup"><span data-stu-id="04be1-320">RepositoryType</span></span>

<span data-ttu-id="04be1-321">Указывает тип репозитория.</span><span class="sxs-lookup"><span data-stu-id="04be1-321">Specifies the type of the repository.</span></span> <span data-ttu-id="04be1-322">Значение по умолчанию — "git".</span><span class="sxs-lookup"><span data-stu-id="04be1-322">Default is "git".</span></span>

### <a name="repositorybranch"></a><span data-ttu-id="04be1-323">RepositoryBranch</span><span class="sxs-lookup"><span data-stu-id="04be1-323">RepositoryBranch</span></span>
<span data-ttu-id="04be1-324">Указывает имя исходной ветки в репозитории.</span><span class="sxs-lookup"><span data-stu-id="04be1-324">Specifies the name of the source branch in the repository.</span></span> <span data-ttu-id="04be1-325">Если проект упакован в пакет NuGet, он добавляется в метаданные пакета.</span><span class="sxs-lookup"><span data-stu-id="04be1-325">When the project is packaged in a NuGet package, it's added to the package metadata.</span></span>

### <a name="repositorycommit"></a><span data-ttu-id="04be1-326">RepositoryCommit</span><span class="sxs-lookup"><span data-stu-id="04be1-326">RepositoryCommit</span></span>
<span data-ttu-id="04be1-327">Необязательная фиксация или набор изменений репозитория для указания источника, на основе которого был создан пакет.</span><span class="sxs-lookup"><span data-stu-id="04be1-327">Optional repository commit or changeset to indicate which source the package was built against.</span></span> <span data-ttu-id="04be1-328">Необходимо также указать `RepositoryUrl`, чтобы включить это свойство.</span><span class="sxs-lookup"><span data-stu-id="04be1-328">`RepositoryUrl` must also be specified for this property to be included.</span></span> <span data-ttu-id="04be1-329">Если проект упакован в пакет NuGet, эта фиксация или набор изменений добавляются в метаданные пакета.</span><span class="sxs-lookup"><span data-stu-id="04be1-329">When the project is packaged in a NuGet package, this commit or changeset is added to the package metadata.</span></span>

### <a name="nopackageanalysis"></a><span data-ttu-id="04be1-330">NoPackageAnalysis</span><span class="sxs-lookup"><span data-stu-id="04be1-330">NoPackageAnalysis</span></span>

<span data-ttu-id="04be1-331">Указывает, что пакету не нужно запускать анализ пакета после его сборки.</span><span class="sxs-lookup"><span data-stu-id="04be1-331">Specifies that pack should not run package analysis after building the package.</span></span>

### <a name="minclientversion"></a><span data-ttu-id="04be1-332">MinClientVersion</span><span class="sxs-lookup"><span data-stu-id="04be1-332">MinClientVersion</span></span>

<span data-ttu-id="04be1-333">Указывает минимальную версию клиента NuGet, который может установить этот пакет с использованием nuget.exe и диспетчера пакетов Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="04be1-333">Specifies the minimum version of the NuGet client that can install this package, enforced by nuget.exe and the Visual Studio Package Manager.</span></span>

### <a name="includebuildoutput"></a><span data-ttu-id="04be1-334">IncludeBuildOutput</span><span class="sxs-lookup"><span data-stu-id="04be1-334">IncludeBuildOutput</span></span>

<span data-ttu-id="04be1-335">Это логическое значение указывает, следует ли упаковывать выходные сборки в файл *NUPKG*.</span><span class="sxs-lookup"><span data-stu-id="04be1-335">This Boolean value specifies whether the build output assemblies should be packed into the *.nupkg* file or not.</span></span>

### <a name="includecontentinpack"></a><span data-ttu-id="04be1-336">IncludeContentInPack</span><span class="sxs-lookup"><span data-stu-id="04be1-336">IncludeContentInPack</span></span>

<span data-ttu-id="04be1-337">Это логическое значение указывает, будут ли все элементы, имеющие тип `Content`, автоматически включены в итоговый пакет.</span><span class="sxs-lookup"><span data-stu-id="04be1-337">This Boolean value specifies whether any items that have a type of `Content` will be included in the resulting package automatically.</span></span> <span data-ttu-id="04be1-338">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="04be1-338">The default is `true`.</span></span>

### <a name="buildoutputtargetfolder"></a><span data-ttu-id="04be1-339">BuildOutputTargetFolder</span><span class="sxs-lookup"><span data-stu-id="04be1-339">BuildOutputTargetFolder</span></span>

<span data-ttu-id="04be1-340">Указывает папку для размещения выходных сборок.</span><span class="sxs-lookup"><span data-stu-id="04be1-340">Specifies the folder where to place the output assemblies.</span></span> <span data-ttu-id="04be1-341">Выходные сборки (и другие выходные файлы) копируются в соответствующие папки платформы.</span><span class="sxs-lookup"><span data-stu-id="04be1-341">The output assemblies (and other output files) are copied into their respective framework folders.</span></span>

### <a name="contenttargetfolders"></a><span data-ttu-id="04be1-342">ContentTargetFolders</span><span class="sxs-lookup"><span data-stu-id="04be1-342">ContentTargetFolders</span></span>

<span data-ttu-id="04be1-343">Это свойство указывает расположение по умолчанию, куда следует помещать все файлы содержимого, для которых не указан `PackagePath`.</span><span class="sxs-lookup"><span data-stu-id="04be1-343">This property specifies the default location of where all the content files should go if `PackagePath` is not specified for them.</span></span> <span data-ttu-id="04be1-344">Значение по умолчанию — "content;contentFiles".</span><span class="sxs-lookup"><span data-stu-id="04be1-344">The default value is "content;contentFiles".</span></span>

### <a name="nuspecfile"></a><span data-ttu-id="04be1-345">NuspecFile</span><span class="sxs-lookup"><span data-stu-id="04be1-345">NuspecFile</span></span>

<span data-ttu-id="04be1-346">Относительный или абсолютный путь к файлу *NUSPEC*, используемому для упаковки.</span><span class="sxs-lookup"><span data-stu-id="04be1-346">Relative or absolute path to the *.nuspec* file being used for packing.</span></span>

> [!NOTE]
> <span data-ttu-id="04be1-347">Если файл *NUSPEC* указан, он используется для упаковки в **монопольном порядке**, а любые сведения в проектах не используются.</span><span class="sxs-lookup"><span data-stu-id="04be1-347">If the *.nuspec* file is specified, it's used **exclusively** for packaging information and any information in the projects is not used.</span></span>

### <a name="nuspecbasepath"></a><span data-ttu-id="04be1-348">NuspecBasePath</span><span class="sxs-lookup"><span data-stu-id="04be1-348">NuspecBasePath</span></span>

<span data-ttu-id="04be1-349">Базовый путь для файла *NUSPEC*.</span><span class="sxs-lookup"><span data-stu-id="04be1-349">Base path for the *.nuspec* file.</span></span>

### <a name="nuspecproperties"></a><span data-ttu-id="04be1-350">NuspecProperties</span><span class="sxs-lookup"><span data-stu-id="04be1-350">NuspecProperties</span></span>

<span data-ttu-id="04be1-351">Список разделенных точками с запятой пар "ключ-значение".</span><span class="sxs-lookup"><span data-stu-id="04be1-351">Semicolon separated list of key=value pairs.</span></span>

## <a name="assemblyinfo-properties"></a><span data-ttu-id="04be1-352">Свойства AssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="04be1-352">AssemblyInfo properties</span></span>

<span data-ttu-id="04be1-353">[Атрибуты сборки](../../standard/assembly/set-attributes.md), которые обычно содержатся в файле *AssemblyInfo*, теперь автоматически создаются на основе свойств.</span><span class="sxs-lookup"><span data-stu-id="04be1-353">[Assembly attributes](../../standard/assembly/set-attributes.md) that were typically present in an *AssemblyInfo* file are now automatically generated from properties.</span></span>

### <a name="properties-per-attribute"></a><span data-ttu-id="04be1-354">Свойства каждого атрибута</span><span class="sxs-lookup"><span data-stu-id="04be1-354">Properties per attribute</span></span>

<span data-ttu-id="04be1-355">Как показано в следующей таблице, каждый атрибут имеет два свойства: одно управляет содержимым атрибута, а второе отключает его создание.</span><span class="sxs-lookup"><span data-stu-id="04be1-355">As shown in the following table, each attribute has a property that controls its content and another that disables its generation:</span></span>

| <span data-ttu-id="04be1-356">Атрибут</span><span class="sxs-lookup"><span data-stu-id="04be1-356">Attribute</span></span>                                                      | <span data-ttu-id="04be1-357">Свойство.</span><span class="sxs-lookup"><span data-stu-id="04be1-357">Property</span></span>               | <span data-ttu-id="04be1-358">Свойство, используемое для отключения</span><span class="sxs-lookup"><span data-stu-id="04be1-358">Property to disable</span></span>                             |
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

<span data-ttu-id="04be1-359">Примечания.</span><span class="sxs-lookup"><span data-stu-id="04be1-359">Notes:</span></span>

- <span data-ttu-id="04be1-360">`AssemblyVersion` и `FileVersion` по умолчанию имеют значение `$(Version)` без суффикса.</span><span class="sxs-lookup"><span data-stu-id="04be1-360">`AssemblyVersion` and `FileVersion` default is to take the value of `$(Version)` without suffix.</span></span> <span data-ttu-id="04be1-361">Например, если для `$(Version)` нужно указать `1.2.3-beta.4`, то значением будет `1.2.3`.</span><span class="sxs-lookup"><span data-stu-id="04be1-361">For example, if `$(Version)` is `1.2.3-beta.4`, then the value would be `1.2.3`.</span></span>
- <span data-ttu-id="04be1-362">По умолчанию для `InformationalVersion` используется значение `$(Version)`.</span><span class="sxs-lookup"><span data-stu-id="04be1-362">`InformationalVersion` defaults to the value of `$(Version)`.</span></span>
- <span data-ttu-id="04be1-363">`InformationalVersion` имеет значение `$(SourceRevisionId)`, которое добавляется, если указано свойство.</span><span class="sxs-lookup"><span data-stu-id="04be1-363">`InformationalVersion` has `$(SourceRevisionId)` appended if the property is present.</span></span> <span data-ttu-id="04be1-364">Его можно отключить с помощью `IncludeSourceRevisionInInformationalVersion`.</span><span class="sxs-lookup"><span data-stu-id="04be1-364">It can be disabled using `IncludeSourceRevisionInInformationalVersion`.</span></span>
- <span data-ttu-id="04be1-365">Свойства `Copyright` и `Description` также используются для метаданных NuGet.</span><span class="sxs-lookup"><span data-stu-id="04be1-365">`Copyright` and `Description` properties are also used for NuGet metadata.</span></span>
- <span data-ttu-id="04be1-366">Свойство `Configuration` является общим для всего процесса сборки, и задается с помощью параметра `--configuration` команд `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="04be1-366">`Configuration` is shared with all the build process and set via the `--configuration` parameter of `dotnet` commands.</span></span>

### <a name="generateassemblyinfo"></a><span data-ttu-id="04be1-367">GenerateAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="04be1-367">GenerateAssemblyInfo</span></span>

<span data-ttu-id="04be1-368">Логическое свойство, которое позволяет включить или отключить создание всех свойств AssemblyInfo.</span><span class="sxs-lookup"><span data-stu-id="04be1-368">A Boolean that enable or disable all the AssemblyInfo generation.</span></span> <span data-ttu-id="04be1-369">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="04be1-369">The default value is `true`.</span></span>

### <a name="generatedassemblyinfofile"></a><span data-ttu-id="04be1-370">GeneratedAssemblyInfoFile</span><span class="sxs-lookup"><span data-stu-id="04be1-370">GeneratedAssemblyInfoFile</span></span>

<span data-ttu-id="04be1-371">Путь к файлу сведений о созданной сборке.</span><span class="sxs-lookup"><span data-stu-id="04be1-371">The path of the generated assembly info file.</span></span> <span data-ttu-id="04be1-372">По умолчанию это путь к файлу в каталоге объектов `$(IntermediateOutputPath)`.</span><span class="sxs-lookup"><span data-stu-id="04be1-372">Default to a file in the `$(IntermediateOutputPath)` (obj) directory.</span></span>
