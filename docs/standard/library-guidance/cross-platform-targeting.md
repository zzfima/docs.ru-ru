---
title: Для различных версий платформ
description: Практические рекомендации для создания кросс платформенные библиотеки .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 72fa891d5b1054af485a98d89b4efb11d6b0018b
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374908"
---
# <a name="cross-platform-targeting"></a><span data-ttu-id="e8285-103">Для различных версий платформ</span><span class="sxs-lookup"><span data-stu-id="e8285-103">Cross-platform targeting</span></span>

<span data-ttu-id="e8285-104">Современные .NET поддерживает несколько операционных систем и устройств.</span><span class="sxs-lookup"><span data-stu-id="e8285-104">Modern .NET supports multiple operating systems and devices.</span></span> <span data-ttu-id="e8285-105">Очень важно для библиотек .NET с открытым кодом для поддержки как многие разработчики максимально ли они создают на веб-сайте ASP.NET, размещенного в Azure или .NET игры в Unity.</span><span class="sxs-lookup"><span data-stu-id="e8285-105">It's important for .NET open-source libraries to support as many developers as possible, whether they're building an ASP.NET website hosted in Azure, or a .NET game in Unity.</span></span>

## <a name="net-standard"></a><span data-ttu-id="e8285-106">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="e8285-106">.NET Standard</span></span>

<span data-ttu-id="e8285-107">.NET standard — это лучший способ добавления Поддержка разных платформ в библиотеку .NET.</span><span class="sxs-lookup"><span data-stu-id="e8285-107">.NET Standard is the best way to add cross-platform support to a .NET library.</span></span> <span data-ttu-id="e8285-108">[.NET standard](../net-standard.md) — это спецификация API-интерфейсы .NET, которые доступны во всех реализациях .NET.</span><span class="sxs-lookup"><span data-stu-id="e8285-108">[.NET Standard](../net-standard.md) is a specification of .NET APIs that are available on all .NET implementations.</span></span> <span data-ttu-id="e8285-109">Применение .NET Standard позволяет создавать библиотеки, которые являются ограниченными использовать API-интерфейсы, которые находятся в данной версии .NET Standard, это означает, что его можно использовать на всех платформах, которые реализуют эту версию .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e8285-109">Targeting .NET Standard lets you produce libraries that are constrained to use APIs that are in a given version of .NET Standard, which means it's usable by all platforms that implement that version of the .NET Standard.</span></span>

<span data-ttu-id="e8285-110">![.NET standard](./media/cross-platform-targeting/platforms-netstandard.png ".NET Standard")</span><span class="sxs-lookup"><span data-stu-id="e8285-110">![.NET Standard](./media/cross-platform-targeting/platforms-netstandard.png ".NET Standard")</span></span>

<span data-ttu-id="e8285-111">Применение .NET Standard, а также успешно компиляцию проекта, не гарантирует, что библиотека будет успешно выполняться на всех платформах:</span><span class="sxs-lookup"><span data-stu-id="e8285-111">Targeting .NET Standard, and successfully compiling your project, doesn't guarantee the library will run successfully on all platforms:</span></span>

1. <span data-ttu-id="e8285-112">API для конкретных платформ не удастся на других платформах.</span><span class="sxs-lookup"><span data-stu-id="e8285-112">Platform-specific APIs will fail on other platforms.</span></span> <span data-ttu-id="e8285-113">Например <xref:Microsoft.Win32.Registry?displayProperty=nameWithType> будет успешно выполнено на Windows и исключение <xref:System.PlatformNotSupportedException> при использовании в любой операционной системе.</span><span class="sxs-lookup"><span data-stu-id="e8285-113">For example, <xref:Microsoft.Win32.Registry?displayProperty=nameWithType> will succeed on Windows and throw <xref:System.PlatformNotSupportedException> when used on any other OS.</span></span>
2. <span data-ttu-id="e8285-114">API-интерфейсы могут вести себя по-разному.</span><span class="sxs-lookup"><span data-stu-id="e8285-114">APIs can behave differently.</span></span> <span data-ttu-id="e8285-115">Например отражение API-интерфейсы имеют разные характеристики производительности при компиляции ahead-of-time использования приложением на iOS и универсальной платформы Windows.</span><span class="sxs-lookup"><span data-stu-id="e8285-115">For example, reflection APIs have different performance characteristics when an application uses ahead-of-time compilation on iOS or UWP.</span></span>

> [!TIP]
> <span data-ttu-id="e8285-116">Команде разработчиков .NET [предлагает анализатор Roslyn](../analyzers/api-analyzer.md) помогут вам оценить возможные причины этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="e8285-116">The .NET team [offers a Roslyn analyzer](../analyzers/api-analyzer.md) to help you discover possible issues.</span></span>

<span data-ttu-id="e8285-117">**СДЕЛАТЬ ✔️** начинаются с включая `netstandard2.0` целевой объект.</span><span class="sxs-lookup"><span data-stu-id="e8285-117">**✔️ DO** start with including a `netstandard2.0` target.</span></span>

> <span data-ttu-id="e8285-118">Наиболее универсальные библиотеки не нужен API вне .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="e8285-118">Most general-purpose libraries should not need APIs outside of .NET Standard 2.0.</span></span> <span data-ttu-id="e8285-119">.NET standard 2.0 поддерживается на всех современных платформах и является рекомендуемым способом обеспечить поддержку нескольких платформ с помощью одного целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="e8285-119">.NET Standard 2.0 is supported by all modern platforms and is the recommended way to support multiple platforms with one target.</span></span>

<span data-ttu-id="e8285-120">**ИЗБЕГАЙТЕ ❌** включая `netstandard1.x` целевой объект.</span><span class="sxs-lookup"><span data-stu-id="e8285-120">**❌ AVOID** including a `netstandard1.x` target.</span></span>

> <span data-ttu-id="e8285-121">.NET standard 1.x распространяется в виде комплексного набора пакетов NuGet, который создает диаграмму зависимостей большой пакет и приводит к разработчикам, загрузка много пакетов при сборке.</span><span class="sxs-lookup"><span data-stu-id="e8285-121">.NET Standard 1.x is distributed as a granular set of NuGet packages, which creates a large package dependency graph and results in developers downloading a lot of packages when building.</span></span> <span data-ttu-id="e8285-122">Современные платформы .NET, включая .NET Framework 4.6.1, UWP и Xamarin, поддержка .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="e8285-122">Modern .NET platforms, including .NET Framework 4.6.1, UWP and Xamarin, all support .NET Standard 2.0.</span></span> <span data-ttu-id="e8285-123">Следует выбирать только .NET Standard 1.x, если необходимо специально предназначенных для более старых платформ.</span><span class="sxs-lookup"><span data-stu-id="e8285-123">You should only target .NET Standard 1.x if you specifically need to target an older platform.</span></span>

<span data-ttu-id="e8285-124">**СДЕЛАТЬ ✔️** включают `netstandard2.0` целевой, если требуется `netstandard1.x` целевой объект.</span><span class="sxs-lookup"><span data-stu-id="e8285-124">**✔️ DO** include a `netstandard2.0` target if you require a `netstandard1.x` target.</span></span>

> <span data-ttu-id="e8285-125">Все платформы, которые поддерживают .NET Standard 2.0 будет использовать `netstandard2.0` ориентированы и использовать преимущества меньшего графика пакета во время более старых платформ по-прежнему будет работать и откат к использованию `netstandard1.x` целевой объект.</span><span class="sxs-lookup"><span data-stu-id="e8285-125">All platforms supporting .NET Standard 2.0 will use the `netstandard2.0` target and benefit from having a smaller package graph while older platforms will still work and fall back to using the `netstandard1.x` target.</span></span>

<span data-ttu-id="e8285-126">**❌ НЕ** включают целевой объект .NET Standard, если библиотека зависит от модели приложений для конкретных платформ.</span><span class="sxs-lookup"><span data-stu-id="e8285-126">**❌ DO NOT** include a .NET Standard target if the library relies on a platform-specific app model.</span></span>

> <span data-ttu-id="e8285-127">Например библиотеки набора средств элементов управления универсальной платформы Windows зависит от модель приложения, которая доступна только для универсальной платформы Windows.</span><span class="sxs-lookup"><span data-stu-id="e8285-127">For example, a UWP control toolkit library depends on an app model that is only available on UWP.</span></span> <span data-ttu-id="e8285-128">Модели определенного приложения API-интерфейсы будет недоступен в .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e8285-128">App model specific APIs will not be available in .NET Standard.</span></span>

## <a name="multi-targeting"></a><span data-ttu-id="e8285-129">Настройка для различных версий</span><span class="sxs-lookup"><span data-stu-id="e8285-129">Multi-targeting</span></span>

<span data-ttu-id="e8285-130">Иногда необходимо получить доступ к API-интерфейсам конкретной платформы из ваших библиотек.</span><span class="sxs-lookup"><span data-stu-id="e8285-130">Sometimes you need to access framework-specific APIs from your libraries.</span></span> <span data-ttu-id="e8285-131">Лучший способ вызова API конкретной платформы с помощью многоплатформенного нацеливания, который выполнит сборку проекта для многих [целевых платформ .NET](../frameworks.md) , а не только для одного.</span><span class="sxs-lookup"><span data-stu-id="e8285-131">The best way to call framework-specific APIs is using multi-targeting, which builds your project for many [.NET target frameworks](../frameworks.md) rather than for just one.</span></span>

<span data-ttu-id="e8285-132">Чтобы защитить потребителей от необходимости создания для отдельных платформ, следует стремиться имеют в .NET стандартный поток вывода, а также один или несколько выходов зависящие от платформы.</span><span class="sxs-lookup"><span data-stu-id="e8285-132">To shield your consumers from having to build for individual frameworks, you should strive to have a .NET Standard output plus one or more framework-specific outputs.</span></span> <span data-ttu-id="e8285-133">С помощью версий все сборки, упаковываются внутри одного пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="e8285-133">With multi-targeting, all assemblies are packaged inside a single NuGet package.</span></span> <span data-ttu-id="e8285-134">Потребители могут затем ссылаться на тот же пакет и NuGet выбирает соответствующую реализацию.</span><span class="sxs-lookup"><span data-stu-id="e8285-134">Consumers can then reference the same package and NuGet will pick the appropriate implementation.</span></span> <span data-ttu-id="e8285-135">Библиотеки .NET Standard выступает в качестве резервной библиотека, которая является использовать везде, за исключением случаев, где ваш пакет NuGet предлагает реализацию зависящие от платформы.</span><span class="sxs-lookup"><span data-stu-id="e8285-135">Your .NET Standard library serves as the fallback library that is used everywhere, except for the cases where your NuGet package offers a framework-specific implementation.</span></span> <span data-ttu-id="e8285-136">Для различных версий позволяет использовать условную компиляцию кода и вызов API конкретной платформы.</span><span class="sxs-lookup"><span data-stu-id="e8285-136">Multi-targeting allows you to use conditional compilation in your code and call framework-specific APIs.</span></span>

<span data-ttu-id="e8285-137">![Пакет NuGet с несколькими сборками](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "пакета NuGet с помощью нескольких сборок")</span><span class="sxs-lookup"><span data-stu-id="e8285-137">![NuGet package with multiple assemblies](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "NuGet package with multiple assemblies")</span></span>

<span data-ttu-id="e8285-138">**Рассмотрите ВОЗМОЖНОСТЬ ✔️** предназначенных для реализаций .NET, в дополнение к .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e8285-138">**✔️ CONSIDER** targeting .NET implementations in addition to .NET Standard.</span></span>

> <span data-ttu-id="e8285-139">Предназначенных для реализаций .NET позволяет вызывать API конкретных платформ, которые находятся вне .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e8285-139">Targeting .NET implementations allows you to call platform-specific APIs that are outside of .NET Standard.</span></span>
>
> <span data-ttu-id="e8285-140">При этом не удалять поддержка .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e8285-140">Do not drop support for .NET Standard when you do this.</span></span> <span data-ttu-id="e8285-141">Вместо этого исключение от реализации и предоставляют возможности API-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="e8285-141">Instead, throw from the implementation and offer capability APIs.</span></span> <span data-ttu-id="e8285-142">Таким образом, библиотеку можно использовать всякий раз и поддерживает подготовки среды выполнения функций.</span><span class="sxs-lookup"><span data-stu-id="e8285-142">This way, your library can be used anywhere and supports runtime light-up of features.</span></span>

<span data-ttu-id="e8285-143">**ИЗБЕГАЙТЕ ❌** с помощью различных версий с .NET Standard, если исходный код является одинаковым для всех целевых объектов.</span><span class="sxs-lookup"><span data-stu-id="e8285-143">**❌ AVOID** using multi-targeting with .NET Standard if your source code is the same for all targets.</span></span>

> <span data-ttu-id="e8285-144">.NET Standard сборки будут автоматически использоваться с NuGet.</span><span class="sxs-lookup"><span data-stu-id="e8285-144">The .NET Standard assembly will automatically be used by NuGet.</span></span> <span data-ttu-id="e8285-145">Для различных версий отдельных реализаций .NET увеличивает `*.nupkg` размер, не получая никаких преимуществ.</span><span class="sxs-lookup"><span data-stu-id="e8285-145">Targeting individual .NET implementations increases the `*.nupkg` size for no benefit.</span></span>

<span data-ttu-id="e8285-146">**✔️ Попробуйте** добавления целевого объекта для `net461` при вы предлагаете `netstandard2.0` целевой объект.</span><span class="sxs-lookup"><span data-stu-id="e8285-146">**✔️ CONSIDER** adding a target for `net461` when you're offering a `netstandard2.0` target.</span></span> 

> <span data-ttu-id="e8285-147">С помощью .NET Standard 2.0 с .NET Framework имеет некоторые проблемы, устраненные в .NET Framework 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="e8285-147">Using .NET Standard 2.0 from .NET Framework has some issues that were addressed in .NET Framework 4.7.2.</span></span> <span data-ttu-id="e8285-148">Можно повысить производительность разработчиков, которые по-прежнему используют .NET Framework 4.6.1 — 4.7.1, предложив им двоичный файл, предназначенную для .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="e8285-148">You can improve the experience for developers that are still on .NET Framework 4.6.1 - 4.7.1 by offering them a binary that is built for .NET Framework 4.6.1.</span></span>

<span data-ttu-id="e8285-149">**СДЕЛАТЬ ✔️** распространять библиотеки с помощью пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="e8285-149">**✔️ DO** distribute your library using a NuGet package.</span></span>

> <span data-ttu-id="e8285-150">NuGet будет выберите целевой объект рекомендации для разработчиков и экранировать их нужно выбрать соответствующую реализацию.</span><span class="sxs-lookup"><span data-stu-id="e8285-150">NuGet will select the best target for the developer and shield them having to pick the appropriate implementation.</span></span>

<span data-ttu-id="e8285-151">**СДЕЛАТЬ ✔️** использовать файл проекта `TargetFrameworks` свойства, если для различных версий.</span><span class="sxs-lookup"><span data-stu-id="e8285-151">**✔️ DO** use a project file's `TargetFrameworks` property when multi-targeting.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <!-- This project will output netstandard2.0 and net461 assemblies -->
    <TargetFrameworks>netstandard2.0;net461</TargetFrameworks>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="e8285-152">**Рассмотрите ВОЗМОЖНОСТЬ ✔️** с помощью [MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras) при многоплатформенного нацеливания для универсальной платформы Windows и Xamarin, так как это значительно упрощает файле проекта.</span><span class="sxs-lookup"><span data-stu-id="e8285-152">**✔️ CONSIDER** using [MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras) when multi-targeting for UWP and Xamarin as it greatly simplifies your project file.</span></span>

## <a name="older-targets"></a><span data-ttu-id="e8285-153">Более старые целевых объектов</span><span class="sxs-lookup"><span data-stu-id="e8285-153">Older targets</span></span>

<span data-ttu-id="e8285-154">Платформа .NET поддерживает предназначенных для версий платформы .NET Framework, длинные за пределы поддержки, а также платформы, которые обычно больше не используются.</span><span class="sxs-lookup"><span data-stu-id="e8285-154">.NET supports targeting versions of the .NET Framework that are long out of support as well as platforms that are no longer commonly used.</span></span> <span data-ttu-id="e8285-155">Пока значение в обеспечении работы библиотеки на как максимальное число целевых объектов для максимально того, чтобы обойти отсутствие интерфейсов API можно добавить значительные накладные расходы.</span><span class="sxs-lookup"><span data-stu-id="e8285-155">While there's value in making your library work on as many targets as possible, having to work around missing APIs can add significant overhead.</span></span> <span data-ttu-id="e8285-156">Мы считаем определенных платформ стоят больше не планируется использовать, учитывая их обработки рекламных кампаний и ограничения.</span><span class="sxs-lookup"><span data-stu-id="e8285-156">We believe certain frameworks are no longer worth targeting, considering their reach and limitations.</span></span>

<span data-ttu-id="e8285-157">**❌ НЕ** включать целевой переносимой библиотеки классов (PCL).</span><span class="sxs-lookup"><span data-stu-id="e8285-157">**❌ DO NOT** include a Portable Class Library (PCL) target.</span></span> <span data-ttu-id="e8285-158">Например, `portable-net45+win8+wpa81+wp8`.</span><span class="sxs-lookup"><span data-stu-id="e8285-158">For example, `portable-net45+win8+wpa81+wp8`.</span></span>

> <span data-ttu-id="e8285-159">.NET standard — это современный способ поддержки кросс платформенные библиотеки .NET и заменяет PCL.</span><span class="sxs-lookup"><span data-stu-id="e8285-159">.NET Standard is the modern way to support cross-platform .NET libraries and replaces PCLs.</span></span>

<span data-ttu-id="e8285-160">**❌ НЕ** включить целевые объекты для платформ .NET, которые больше не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="e8285-160">**❌ DO NOT** include targets for .NET platforms that are no longer supported.</span></span> <span data-ttu-id="e8285-161">Например, `SL4`, `WP`.</span><span class="sxs-lookup"><span data-stu-id="e8285-161">For example, `SL4`, `WP`.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="e8285-162">[Назад](./get-started.md)
[Вперед](./strong-naming.md)</span><span class="sxs-lookup"><span data-stu-id="e8285-162">[Previous](./get-started.md)
[Next](./strong-naming.md)</span></span>
