---
title: Анализ зависимостей для переноса кода в .NET Core
description: Научитесь анализировать внешние зависимости, чтобы перенести свой проект из .NET Framework в .NET Core.
author: cartermp
ms.date: 12/07/2018
ms.custom: seodec18
ms.openlocfilehash: 36d1c1d2090a0fb9e6f48fe519d15897579df2d5
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72521474"
---
# <a name="analyze-your-dependencies-to-port-code-to-net-core"></a><span data-ttu-id="77006-103">Анализ зависимостей для переноса кода в .NET Core</span><span class="sxs-lookup"><span data-stu-id="77006-103">Analyze your dependencies to port code to .NET Core</span></span>

<span data-ttu-id="77006-104">Для переноса кода в .NET Core или .NET Standard требуется понимать свои зависимости.</span><span class="sxs-lookup"><span data-stu-id="77006-104">To port your code to .NET Core or .NET Standard, you must understand your dependencies.</span></span> <span data-ttu-id="77006-105">Внешние зависимости — это несобираемые вами [пакеты NuGet](#analyze-referenced-nuget-packages-in-your-projects) или [библиотеки DLL](#analyze-dependencies-that-arent-nuget-packages), на которые вы ссылаетесь в своем проекте.</span><span class="sxs-lookup"><span data-stu-id="77006-105">External dependencies are the [NuGet packages](#analyze-referenced-nuget-packages-in-your-projects) or [DLLs](#analyze-dependencies-that-arent-nuget-packages) you reference in your project, but that you don't build.</span></span> <span data-ttu-id="77006-106">Оцените каждую зависимость и составьте план на непредвиденные случаи в отношении тех зависимостей, которые не совместимы с .NET Core.</span><span class="sxs-lookup"><span data-stu-id="77006-106">Evaluate each dependency and develop a contingency plan for the ones that aren't compatible with .NET Core.</span></span> <span data-ttu-id="77006-107">В этой статье показано, как определить совместимость зависимости с .NET Core.</span><span class="sxs-lookup"><span data-stu-id="77006-107">Here's how to determine if a dependency is compatible with .NET Core.</span></span>

## <a name="analyze-referenced-nuget-packages-in-your-projects"></a><span data-ttu-id="77006-108">Анализ упоминаемых посредством ссылки пакетов NuGet в вашем проекте</span><span class="sxs-lookup"><span data-stu-id="77006-108">Analyze referenced NuGet packages in your projects</span></span>

<span data-ttu-id="77006-109">Если в своем проекте вы ссылаетесь на пакеты NuGet, необходимо проверить, совместимы ли они с .NET Core.</span><span class="sxs-lookup"><span data-stu-id="77006-109">If you reference NuGet packages in your project, you need to verify if they're compatible with .NET Core.</span></span>
<span data-ttu-id="77006-110">Этого можно добиться двумя способами:</span><span class="sxs-lookup"><span data-stu-id="77006-110">There are two ways to accomplish that:</span></span>

- <span data-ttu-id="77006-111">[С помощью приложения обозревателя пакетов NuGet](#analyze-nuget-packages-using-nuget-package-explorer).</span><span class="sxs-lookup"><span data-stu-id="77006-111">[Using the NuGet Package Explorer app](#analyze-nuget-packages-using-nuget-package-explorer)</span></span>
- <span data-ttu-id="77006-112">[С помощью сайта nuget.org](#analyze-nuget-packages-using-nugetorg).</span><span class="sxs-lookup"><span data-stu-id="77006-112">[Using the nuget.org site](#analyze-nuget-packages-using-nugetorg)</span></span>

<span data-ttu-id="77006-113">Если анализ пакетов покажет, что они не совместимы с .NET Core и предназначены только для использования с .NET Framework, можно проверить, поможет ли выполнить перенос [режим совместимости .NET Framework](#net-framework-compatibility-mode).</span><span class="sxs-lookup"><span data-stu-id="77006-113">After analyzing the packages, if they're not compatible with .NET Core and only target .NET Framework, you can check if the [.NET Framework compatibility mode](#net-framework-compatibility-mode) can help with your porting process.</span></span>

### <a name="analyze-nuget-packages-using-nuget-package-explorer"></a><span data-ttu-id="77006-114">Анализ пакетов NuGet с помощью обозревателя пакетов NuGet</span><span class="sxs-lookup"><span data-stu-id="77006-114">Analyze NuGet packages using NuGet Package Explorer</span></span>

<span data-ttu-id="77006-115">Пакет NuGet представляет собой набор папок со сборками для конкретных платформ.</span><span class="sxs-lookup"><span data-stu-id="77006-115">A NuGet package is itself a set of folders that contain platform-specific assemblies.</span></span> <span data-ttu-id="77006-116">Поэтому необходимо проверить, существует ли папка, которая содержит совместимую сборку внутри пакета.</span><span class="sxs-lookup"><span data-stu-id="77006-116">So you need to check if there's a folder that contains a compatible assembly inside the package.</span></span>

<span data-ttu-id="77006-117">Проще всего просматривать папки пакета NuGet с помощью инструмента [Обозреватель пакетов NuGet](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer).</span><span class="sxs-lookup"><span data-stu-id="77006-117">The easiest way to inspect NuGet Package folders is to use the [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) tool.</span></span> <span data-ttu-id="77006-118">После установки выполните следующие действия, чтобы увидеть имена папок:</span><span class="sxs-lookup"><span data-stu-id="77006-118">After installing it, use the following steps to see the folder names:</span></span>

1. <span data-ttu-id="77006-119">Откройте обозреватель пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="77006-119">Open the NuGet Package Explorer.</span></span>
2. <span data-ttu-id="77006-120">Щелкните **Открыть пакет из веб-канала**.</span><span class="sxs-lookup"><span data-stu-id="77006-120">Click **Open package from online feed**.</span></span>
3. <span data-ttu-id="77006-121">Выполните поиск по имени пакета.</span><span class="sxs-lookup"><span data-stu-id="77006-121">Search for the name of the package.</span></span>
4. <span data-ttu-id="77006-122">Выберите имя пакета в результатах поиска и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="77006-122">Select the package name from the search results and click **open**.</span></span>
5. <span data-ttu-id="77006-123">Разверните папку *lib* в правой части окна и просмотрите имена папок.</span><span class="sxs-lookup"><span data-stu-id="77006-123">Expand the *lib* folder on the right-hand side and look at folder names.</span></span>

<span data-ttu-id="77006-124">Найдите папку с любым из следующих имен:</span><span class="sxs-lookup"><span data-stu-id="77006-124">Look for a folder with any of the following names:</span></span>

```
netstandard1.0
netstandard1.1
netstandard1.2
netstandard1.3
netstandard1.4
netstandard1.5
netstandard1.6
netstandard2.0
netcoreapp1.0
netcoreapp1.1
netcoreapp2.0
netcoreapp2.1
netcoreapp2.2
portable-net45-win8
portable-win8-wpa8
portable-net451-win81
portable-net45-win8-wpa8-wpa81
```

<span data-ttu-id="77006-125">Эти значения — [моникеры целевых платформ (TFM)](../../standard/frameworks.md), которые соответствуют версиям [.NET Standard](../../standard/net-standard.md), .NET Core и традиционным профилям переносимой библиотеки классов (PCL), совместимым с .NET Core.</span><span class="sxs-lookup"><span data-stu-id="77006-125">These values are the [Target Framework Monikers (TFMs)](../../standard/frameworks.md) that map to versions of the [.NET Standard](../../standard/net-standard.md), .NET Core, and traditional Portable Class Library (PCL) profiles that are compatible with .NET Core.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77006-126">При просмотре поддерживаемых пакетом моникеров TFM обратите внимание, что, несмотря на совместимость, `netcoreapp*` предназначен только для проектов .NET Core, но не для проектов .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="77006-126">When looking at the TFMs that a package supports, note that `netcoreapp*`, while compatible, is for .NET Core projects only and not for .NET Standard projects.</span></span>
> <span data-ttu-id="77006-127">Библиотека, предназначенная только для `netcoreapp*`, но не для `netstandard*`, может использоваться только другими приложениями .NET Core.</span><span class="sxs-lookup"><span data-stu-id="77006-127">A library that only targets `netcoreapp*` and not `netstandard*` can only be consumed by other .NET Core apps.</span></span>

### <a name="analyze-nuget-packages-using-nugetorg"></a><span data-ttu-id="77006-128">Анализ пакетов NuGet с помощью сайта nuget.org</span><span class="sxs-lookup"><span data-stu-id="77006-128">Analyze NuGet packages using nuget.org</span></span>

<span data-ttu-id="77006-129">Кроме того, поддерживаемые каждым пакетом TFM можно просмотреть на сайте [nuget.org](https://www.nuget.org/) в разделе **Зависимости** страницы пакета.</span><span class="sxs-lookup"><span data-stu-id="77006-129">Alternatively, you can see the TFMs that each package supports on [nuget.org](https://www.nuget.org/) under the **Dependencies** section of the package page.</span></span>

<span data-ttu-id="77006-130">С помощью этого сайта легко проверить совместимость, однако информация о **зависимостях** доступна не для всех пакетов.</span><span class="sxs-lookup"><span data-stu-id="77006-130">Although using the site is an easier method to verify the compatibility, **Dependencies** information is not available on the site for all packages.</span></span>

### <a name="net-framework-compatibility-mode"></a><span data-ttu-id="77006-131">Режим совместимости .NET Framework</span><span class="sxs-lookup"><span data-stu-id="77006-131">.NET Framework compatibility mode</span></span>

<span data-ttu-id="77006-132">Анализ пакетов NuGet может показать, что они предназначены только для платформы .NET Framework, как и большинство пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="77006-132">After analyzing the NuGet packages, you might find that they only target the .NET Framework, as most NuGet packages do.</span></span>

<span data-ttu-id="77006-133">Начиная с .NET Standard 2.0, доступен режим совместимости .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="77006-133">Starting with .NET Standard 2.0, the .NET Framework compatibility mode was introduced.</span></span> <span data-ttu-id="77006-134">Этот режим совместимости позволяет проектам .NET Standard и .NET Core ссылаться на библиотеки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="77006-134">This compatibility mode allows .NET Standard and .NET Core projects to reference .NET Framework libraries.</span></span> <span data-ttu-id="77006-135">Создание ссылок на библиотеки .NET Framework не работает для всех проектов, например, если библиотека использует API WPF, то делает возможным разблокировку множества сценариев переноса.</span><span class="sxs-lookup"><span data-stu-id="77006-135">Referencing .NET Framework libraries doesn't work for all projects, such as if the library uses Windows Presentation Foundation (WPF) APIs, but it does unblock many porting scenarios.</span></span>

<span data-ttu-id="77006-136">Ссылаясь в своем проекте на пакеты NuGet, предназначенные для .NET Framework, например [Huitian.PowerCollections](https://www.nuget.org/packages/Huitian.PowerCollections), вы получаете предупреждение об откате пакета ([NU1701](/nuget/reference/errors-and-warnings/nu1701)), как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="77006-136">When you reference NuGet packages that target the .NET Framework in your project, such as [Huitian.PowerCollections](https://www.nuget.org/packages/Huitian.PowerCollections), you get a package fallback warning ([NU1701](/nuget/reference/errors-and-warnings/nu1701)) similar to the following example:</span></span>

`NU1701: Package ‘Huitian.PowerCollections 1.0.0’ was restored using ‘.NETFramework,Version=v4.6.1’ instead of the project target framework ‘.NETStandard,Version=v2.0’. This package may not be fully compatible with your project.`

<span data-ttu-id="77006-137">Это предупреждение отображается при добавлении пакета и каждый раз при выполнении сборки, чтобы вы обязательно протестировали этот пакет в своем проекте.</span><span class="sxs-lookup"><span data-stu-id="77006-137">That warning is displayed when you add the package and every time you build to make sure you test that package with your project.</span></span> <span data-ttu-id="77006-138">Если проект работает надлежащим образом, можно отключить это предупреждение, изменив свойства пакета в Visual Studio или путем редактирования файла проекта в привычном редакторе кода вручную.</span><span class="sxs-lookup"><span data-stu-id="77006-138">If your project is working as expected, you can suppress that warning by editing the package properties in Visual Studio or by manually editing the project file in your favorite code editor.</span></span>

<span data-ttu-id="77006-139">Чтобы отключить это предупреждение путем редактирования файла проекта, найдите запись `PackageReference` для пакета, предупреждение для которого требуется отключить, и добавьте атрибут `NoWarn`.</span><span class="sxs-lookup"><span data-stu-id="77006-139">To suppress the warning by editing the project file, find the `PackageReference` entry for the package you want to suppress the warning for and add the `NoWarn` attribute.</span></span> <span data-ttu-id="77006-140">Атрибут `NoWarn` принимает разделенный запятыми список всех идентификаторов предупреждений.</span><span class="sxs-lookup"><span data-stu-id="77006-140">The `NoWarn` attribute accepts a comma-separated list of all the warning IDs.</span></span> <span data-ttu-id="77006-141">В следующем примере показано отключение предупреждения `NU1701` для пакета `Huitian.PowerCollections` путем редактирования файла проекта вручную:</span><span class="sxs-lookup"><span data-stu-id="77006-141">The following example shows how to suppress the `NU1701` warning for the `Huitian.PowerCollections` package by editing your project file manually:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Huitian.PowerCollections" Version="1.0.0" NoWarn="NU1701" />
</ItemGroup>
```

<span data-ttu-id="77006-142">Дополнительные сведения о том, как отключить предупреждения компилятора в Visual Studio, см. в разделе [Подавление предупреждений для пакетов NuGet](/visualstudio/ide/how-to-suppress-compiler-warnings#suppress-warnings-for-nuget-packages).</span><span class="sxs-lookup"><span data-stu-id="77006-142">For more information on how to suppress compiler warnings in Visual Studio, see [Suppressing warnings for NuGet packages](/visualstudio/ide/how-to-suppress-compiler-warnings#suppress-warnings-for-nuget-packages).</span></span>

## <a name="port-your-packages-to-packagereference"></a><span data-ttu-id="77006-143">Перенос собственных пакетов в `PackageReference`</span><span class="sxs-lookup"><span data-stu-id="77006-143">Port your packages to `PackageReference`</span></span>

<span data-ttu-id="77006-144">[PackageReference](/nuget/consume-packages/package-references-in-project-files) используется в .NET Core для указания зависимостей пакета.</span><span class="sxs-lookup"><span data-stu-id="77006-144">.NET Core uses [PackageReference](/nuget/consume-packages/package-references-in-project-files) to specify package dependencies.</span></span> <span data-ttu-id="77006-145">Если вы указываете пакеты с помощью файла [packages.config](/nuget/reference/packages-config), вам нужно будет преобразовать его в `PackageReference`.</span><span class="sxs-lookup"><span data-stu-id="77006-145">If you are using [packages.config](/nuget/reference/packages-config) to specify your packages, you will need to convert over to `PackageReference`.</span></span>

<span data-ttu-id="77006-146">Дополнительные сведения см. в статье [Перенос из packages.config в PackageReference](/nuget/reference/migrate-packages-config-to-package-reference).</span><span class="sxs-lookup"><span data-stu-id="77006-146">You can learn more at [Migrate from packages.config to PackageReference](/nuget/reference/migrate-packages-config-to-package-reference).</span></span>

## <a name="what-to-do-when-your-nuget-package-dependency-doesnt-run-on-net-core"></a><span data-ttu-id="77006-147">Что делать, если зависимость пакета NuGet не работает в .NET Core</span><span class="sxs-lookup"><span data-stu-id="77006-147">What to do when your NuGet package dependency doesn't run on .NET Core</span></span>

<span data-ttu-id="77006-148">Если пакет NuGet, от которого зависит ваш проект, не работает в .NET Core, можно предпринять ряд мер:</span><span class="sxs-lookup"><span data-stu-id="77006-148">There are a few things you can do if a NuGet package you depend on doesn't run on .NET Core:</span></span>

1. <span data-ttu-id="77006-149">Если проект имеет открытый исходный код и размещается на каком либо ресурсе, наподобие GitHub, вы можете обратиться к разработчикам напрямую.</span><span class="sxs-lookup"><span data-stu-id="77006-149">If the project is open source and hosted somewhere like GitHub, you can engage the developers directly.</span></span>
2. <span data-ttu-id="77006-150">Вы можете обратитесь к автору непосредственно на [nuget.org](https://www.nuget.org/). Найдите пакет и нажмите кнопку **Связаться с владельцами** в левой стороне страницы пакета.</span><span class="sxs-lookup"><span data-stu-id="77006-150">You can contact the author directly on [nuget.org](https://www.nuget.org/). Search for the package and click **Contact Owners** on the left-hand side of the package's page.</span></span>
3. <span data-ttu-id="77006-151">Можно найти другой пакет, который будет выполнять те же функции и работать в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="77006-151">You can search for another package that runs on .NET Core that accomplishes the same task as the package you were using.</span></span>
4. <span data-ttu-id="77006-152">Вы можете попытаться создать пакет с аналогичным кодом самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="77006-152">You can attempt to write the code the package was doing yourself.</span></span>
5. <span data-ttu-id="77006-153">Вы можете устранить зависимость от пакета, изменив функциональность приложения, по крайней мере до тех пор пока не станет доступна совместимая версия пакета.</span><span class="sxs-lookup"><span data-stu-id="77006-153">You could eliminate the dependency on the package by changing the functionality of your app, at least until a compatible version of the package becomes available.</span></span>

<span data-ttu-id="77006-154">Помните, что обслуживанием проектов с открытым исходным кодом и выпуском пакетов NuGet часто занимаются волонтеры.</span><span class="sxs-lookup"><span data-stu-id="77006-154">Remember that open-source project maintainers and NuGet package publishers are often volunteers.</span></span> <span data-ttu-id="77006-155">Они делают эту работу, потому что им важна соответствующая область деятельности, причем безвозмездно, часто в свободное от основной занятости время.</span><span class="sxs-lookup"><span data-stu-id="77006-155">They contribute because they care about a given domain, do it for free, and often have a different daytime job.</span></span> <span data-ttu-id="77006-156">Помните об этом, обращаясь к ним за поддержкой при использовании пакетов .NET Core.</span><span class="sxs-lookup"><span data-stu-id="77006-156">So be mindful of that when contacting them to ask for .NET Core support.</span></span>

<span data-ttu-id="77006-157">Если ни один из описанных выше способов не помог решить проблему, возможно, придется отложить перенос кода в .NET Core на более позднюю дату.</span><span class="sxs-lookup"><span data-stu-id="77006-157">If you can't resolve your issue with any of the above, you may have to port to .NET Core at a later date.</span></span>

<span data-ttu-id="77006-158">Команда разработчиков .NET хотела бы узнать, поддержку каких библиотек в .NET Core следует реализовать в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="77006-158">The .NET Team would like to know which libraries are the most important to support with .NET Core.</span></span> <span data-ttu-id="77006-159">Сообщить о нужных вам библиотеках можно в электронном сообщении по адресу dotnet@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="77006-159">You can send an email to dotnet@microsoft.com about the libraries you'd like to use.</span></span>

## <a name="analyze-dependencies-that-arent-nuget-packages"></a><span data-ttu-id="77006-160">Анализ зависимостей, которые не являются пакетами NuGet</span><span class="sxs-lookup"><span data-stu-id="77006-160">Analyze dependencies that aren't NuGet packages</span></span>

<span data-ttu-id="77006-161">Возможно, вы используете зависимость, которая не является пакетом NuGet, например библиотеку DLL в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="77006-161">You may have a dependency that isn't a NuGet package, such as a DLL in the file system.</span></span> <span data-ttu-id="77006-162">Единственный способ определить переносимость такой зависимости — запустить [средство .NET Portability Analyzer](https://github.com/Microsoft/dotnet-apiport).</span><span class="sxs-lookup"><span data-stu-id="77006-162">The only way to determine the portability of that dependency is to run the [.NET Portability Analyzer](https://github.com/Microsoft/dotnet-apiport) tool.</span></span> <span data-ttu-id="77006-163">Это средство может анализировать сборки, предназначенные для .NET Framework, и идентифицировать API, которые невозможно перенести на другие платформы .NET, например .NET Core.</span><span class="sxs-lookup"><span data-stu-id="77006-163">The tool can analyze assemblies that target the .NET Framework and identify APIs that aren't portable to other .NET platforms such as .NET Core.</span></span> <span data-ttu-id="77006-164">Можно запустить средство в качестве консольного приложения или [расширения Visual Studio](../../standard/analyzers/portability-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="77006-164">You can run the tool as a console application or as a [Visual Studio extension](../../standard/analyzers/portability-analyzer.md).</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="77006-165">Вперед</span><span class="sxs-lookup"><span data-stu-id="77006-165">Next</span></span>](libraries.md)
