---
title: Кроссплатформенное нацеливание для библиотек .NET
description: Рекомендации по созданию кроссплатформенных библиотек .NET.
ms.date: 08/12/2019
ms.openlocfilehash: 61adff3759984554bb83531b4f9d8a49e29c929c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "76731459"
---
# <a name="cross-platform-targeting"></a><span data-ttu-id="de52d-103">Кроссплатформенное нацеливание</span><span class="sxs-lookup"><span data-stu-id="de52d-103">Cross-platform targeting</span></span>

<span data-ttu-id="de52d-104">Современная версия .NET поддерживает различные операционные системы и устройства.</span><span class="sxs-lookup"><span data-stu-id="de52d-104">Modern .NET supports multiple operating systems and devices.</span></span> <span data-ttu-id="de52d-105">Важно, чтобы библиотеки .NET с открытым кодом обеспечивали поддержку максимального спектра разработок, будь то веб-сайт, созданный на ASP.NET и размещенный в Azure, или .NET- игра на Unity.</span><span class="sxs-lookup"><span data-stu-id="de52d-105">It's important for .NET open-source libraries to support as many developers as possible, whether they're building an ASP.NET website hosted in Azure, or a .NET game in Unity.</span></span>

## <a name="net-standard"></a><span data-ttu-id="de52d-106">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="de52d-106">.NET Standard</span></span>

<span data-ttu-id="de52d-107">Добавить в библиотеку .NET. кроссплатформенную поддержку лучше всего с помощью .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="de52d-107">.NET Standard is the best way to add cross-platform support to a .NET library.</span></span> <span data-ttu-id="de52d-108">[.NET Standard](../net-standard.md) — это спецификация API-интерфейсов .NET, которые доступны во всех реализациях .NET.</span><span class="sxs-lookup"><span data-stu-id="de52d-108">[.NET Standard](../net-standard.md) is a specification of .NET APIs that are available on all .NET implementations.</span></span> <span data-ttu-id="de52d-109">Нацеливание на .NET Standard позволяет создавать библиотеки, которые могут использовать API-интерфейсы определенной версии .NET Standard, т. е. такие библиотеки могут использоваться на всех платформах, на которых реализуется определенная версия .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="de52d-109">Targeting .NET Standard lets you produce libraries that are constrained to use APIs that are in a given version of .NET Standard, which means it's usable by all platforms that implement that version of the .NET Standard.</span></span>

<span data-ttu-id="de52d-110">![.NET Standard](./media/cross-platform-targeting/platforms-netstandard.png ".NET Standard")</span><span class="sxs-lookup"><span data-stu-id="de52d-110">![.NET Standard](./media/cross-platform-targeting/platforms-netstandard.png ".NET Standard")</span></span>

<span data-ttu-id="de52d-111">Нацеливание на .NET Standard и успешная компиляция проекта не гарантируют, что библиотека будет успешно работать на всех платформах.</span><span class="sxs-lookup"><span data-stu-id="de52d-111">Targeting .NET Standard, and successfully compiling your project, doesn't guarantee the library will run successfully on all platforms:</span></span>

1. <span data-ttu-id="de52d-112">API-интерфейсы для конкретных платформ не будут работать на других платформах.</span><span class="sxs-lookup"><span data-stu-id="de52d-112">Platform-specific APIs will fail on other platforms.</span></span> <span data-ttu-id="de52d-113">К примеру, <xref:Microsoft.Win32.Registry?displayProperty=nameWithType> будет нормально работать в ОС Windows и вызывать исключение <xref:System.PlatformNotSupportedException> в любой другой операционной системе.</span><span class="sxs-lookup"><span data-stu-id="de52d-113">For example, <xref:Microsoft.Win32.Registry?displayProperty=nameWithType> will succeed on Windows and throw <xref:System.PlatformNotSupportedException> when used on any other OS.</span></span>
2. <span data-ttu-id="de52d-114">API-интерфейсы могут работать по-разному.</span><span class="sxs-lookup"><span data-stu-id="de52d-114">APIs can behave differently.</span></span> <span data-ttu-id="de52d-115">Например, поддерживающие рефлексию API-интерфейсы демонстрируют другие показатели производительности, если приложение использует компиляцию AOT на платформе iOS или UWP.</span><span class="sxs-lookup"><span data-stu-id="de52d-115">For example, reflection APIs have different performance characteristics when an application uses ahead-of-time compilation on iOS or UWP.</span></span>

> [!TIP]
> <span data-ttu-id="de52d-116">Команда разработчиков .NET рекомендует использовать [анализатор Roslyn](../analyzers/api-analyzer.md), чтобы обнаружить потенциальные проблемы.</span><span class="sxs-lookup"><span data-stu-id="de52d-116">The .NET team [offers a Roslyn analyzer](../analyzers/api-analyzer.md) to help you discover possible issues.</span></span>

<span data-ttu-id="de52d-117">✔️ ️СЛЕДУЕТ в первую очередь указать целевую платформу `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="de52d-117">✔️ DO start with including a `netstandard2.0` target.</span></span>

> <span data-ttu-id="de52d-118">Большинству универсальных библиотек не нужны API за пределами .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="de52d-118">Most general-purpose libraries should not need APIs outside of .NET Standard 2.0.</span></span> <span data-ttu-id="de52d-119">Платформу .NET Standard 2.0 поддерживают все современные платформы. Ее рекомендуется использовать всегда, когда нужно реализовать кроссплатформенность с помощью одной целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="de52d-119">.NET Standard 2.0 is supported by all modern platforms and is the recommended way to support multiple platforms with one target.</span></span>

<span data-ttu-id="de52d-120">❌ НЕЖЕЛАТЕЛЬНО указывать целевую платформу `netstandard1.x`.</span><span class="sxs-lookup"><span data-stu-id="de52d-120">❌ AVOID including a `netstandard1.x` target.</span></span>

> <span data-ttu-id="de52d-121">.NET Standard 1.x распространяется в виде набора небольших пакетов NuGet, что создает большую схему зависимостей пакетов и приводит к тому, что разработчики во время компиляции скачивают много пакетов.</span><span class="sxs-lookup"><span data-stu-id="de52d-121">.NET Standard 1.x is distributed as a granular set of NuGet packages, which creates a large package dependency graph and results in developers downloading a lot of packages when building.</span></span> <span data-ttu-id="de52d-122">Все современные платформы .NET, включая .NET Framework 4.6.1, UWP и Xamarin, поддерживают .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="de52d-122">Modern .NET platforms, including .NET Framework 4.6.1, UWP and Xamarin, all support .NET Standard 2.0.</span></span> <span data-ttu-id="de52d-123">.NET Standard 1.x следует указывать, только если вам специально нужна более старая платформа.</span><span class="sxs-lookup"><span data-stu-id="de52d-123">You should only target .NET Standard 1.x if you specifically need to target an older platform.</span></span>

<span data-ttu-id="de52d-124">✔️ СЛЕДУЕТ указать `netstandard2.0`, если вам требуется целевая платформа `netstandard1.x`.</span><span class="sxs-lookup"><span data-stu-id="de52d-124">✔️ DO include a `netstandard2.0` target if you require a `netstandard1.x` target.</span></span>

> <span data-ttu-id="de52d-125">Все платформы, которые поддерживают .NET Standard 2.0, будут использовать целевую платформу `netstandard2.0`, а граф пакетов будет меньшим. При этом старые платформы также будут работать, но использовать они будут целевую платформу `netstandard1.x`.</span><span class="sxs-lookup"><span data-stu-id="de52d-125">All platforms supporting .NET Standard 2.0 will use the `netstandard2.0` target and benefit from having a smaller package graph while older platforms will still work and fall back to using the `netstandard1.x` target.</span></span>

<span data-ttu-id="de52d-126">❌ НЕ СЛЕДУЕТ указывать целевую платформу .NET Standard, если библиотека зависит от модели приложений для определенной платформы.</span><span class="sxs-lookup"><span data-stu-id="de52d-126">❌ DO NOT include a .NET Standard target if the library relies on a platform-specific app model.</span></span>

> <span data-ttu-id="de52d-127">Например, библиотека средств управления UWP зависит от модели приложений, которая доступна только для UWP.</span><span class="sxs-lookup"><span data-stu-id="de52d-127">For example, a UWP control toolkit library depends on an app model that is only available on UWP.</span></span> <span data-ttu-id="de52d-128">API-интерфейсы для определенных моделей приложений недоступны в .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="de52d-128">App model specific APIs will not be available in .NET Standard.</span></span>

## <a name="multi-targeting"></a><span data-ttu-id="de52d-129">Настройка для различных версий</span><span class="sxs-lookup"><span data-stu-id="de52d-129">Multi-targeting</span></span>

<span data-ttu-id="de52d-130">Иногда из библиотек необходимо получить доступ к API-интерфейсам конкретной платформы.</span><span class="sxs-lookup"><span data-stu-id="de52d-130">Sometimes you need to access framework-specific APIs from your libraries.</span></span> <span data-ttu-id="de52d-131">Многоплатформенное нацеливание — лучший способ вызова API определенной платформы. Это означает, что проект создается с поддержкой не одной, а нескольких [требуемых версий .NET](../frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="de52d-131">The best way to call framework-specific APIs is using multi-targeting, which builds your project for many [.NET target frameworks](../frameworks.md) rather than for just one.</span></span>

<span data-ttu-id="de52d-132">Чтобы пользователям не приходилось компилировать проект под разные платформы, старайтесь писать код под NET Standard плюс под еще одну или несколько определенных платформ.</span><span class="sxs-lookup"><span data-stu-id="de52d-132">To shield your consumers from having to build for individual frameworks, you should strive to have a .NET Standard output plus one or more framework-specific outputs.</span></span> <span data-ttu-id="de52d-133">В случае с многоплатформенным нацеливанием все сборки упаковываются в один пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="de52d-133">With multi-targeting, all assemblies are packaged inside a single NuGet package.</span></span> <span data-ttu-id="de52d-134">Таким образом пользователи будут ссылаться на один пакет, а NuGet будет выбирать подходящую реализацию.</span><span class="sxs-lookup"><span data-stu-id="de52d-134">Consumers can then reference the same package and NuGet will pick the appropriate implementation.</span></span> <span data-ttu-id="de52d-135">Библиотека .NET Standard выступает в качестве резервной. Она используется всегда, за исключением случаев, когда пакет NuGet предлагает реализацию под определенную платформу.</span><span class="sxs-lookup"><span data-stu-id="de52d-135">Your .NET Standard library serves as the fallback library that is used everywhere, except for the cases where your NuGet package offers a framework-specific implementation.</span></span> <span data-ttu-id="de52d-136">Многоплатформенное нацеливание позволяет использовать условную компиляцию кода и вызывать API-интерфейсы определенных платформ.</span><span class="sxs-lookup"><span data-stu-id="de52d-136">Multi-targeting allows you to use conditional compilation in your code and call framework-specific APIs.</span></span>

<span data-ttu-id="de52d-137">![Пакет NuGet с несколькими сборками](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "Пакет NuGet с несколькими сборками")</span><span class="sxs-lookup"><span data-stu-id="de52d-137">![NuGet package with multiple assemblies](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "NuGet package with multiple assemblies")</span></span>

<span data-ttu-id="de52d-138">✔ РЕКОМЕНДУЕТСЯ (помимо нацеливания на .NET Standard) также указать реализации .NET.</span><span class="sxs-lookup"><span data-stu-id="de52d-138">✔️ CONSIDER targeting .NET implementations in addition to .NET Standard.</span></span>

> <span data-ttu-id="de52d-139">Нацеливание на реализации .NET позволяет вызывать API-интерфейсы определенных платформ, которые не включены в .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="de52d-139">Targeting .NET implementations allows you to call platform-specific APIs that are outside of .NET Standard.</span></span>
>
> <span data-ttu-id="de52d-140">При этом не стоит исключать .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="de52d-140">Do not drop support for .NET Standard when you do this.</span></span> <span data-ttu-id="de52d-141">Вместо этого выдайте исключение из реализации и предложите использовать API, поддерживающие нужные возможности.</span><span class="sxs-lookup"><span data-stu-id="de52d-141">Instead, throw from the implementation and offer capability APIs.</span></span> <span data-ttu-id="de52d-142">Таким образом библиотека окажется универсальной и будет поддерживать активацию функций в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="de52d-142">This way, your library can be used anywhere and supports runtime light-up of features.</span></span>

```csharp
public static class GpsLocation
{
    // This project uses multi-targeting to expose device-specific APIs to .NET Standard.
    public static async Task<(double latitude, double longitude)> GetCoordinatesAsync()
    {
#if NET461
        return CallDotNetFramworkApi();
#elif WINDOWS_UWP
        return CallUwpApi();
#else
        throw new PlatformNotSupportedException();
#endif
    }

    // Allows callers to check without having to catch PlatformNotSupportedException
    // or replicating the OS check.
    public static bool IsSupported
    {
        get
        {
#if NET461 || WINDOWS_UWP
            return true;
#else
            return false;
#endif
        }
    }
}
```

<span data-ttu-id="de52d-143">❌ НЕЖЕЛАТЕЛЬНО использовать многоплатформенное нацеливание, а также нацеливание с помощью .NET Standard, если исходный код будет одинаковым для всех целевых платформ.</span><span class="sxs-lookup"><span data-stu-id="de52d-143">❌ AVOID multi-targeting as well as targeting .NET Standard, if your source code is the same for all targets.</span></span>

> <span data-ttu-id="de52d-144">NuGet будет автоматически использовать сборку .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="de52d-144">The .NET Standard assembly will automatically be used by NuGet.</span></span> <span data-ttu-id="de52d-145">Нацеливание на отдельные реализации .NET увеличивает размер файла `*.nupkg`, не давая взамен никаких преимуществ.</span><span class="sxs-lookup"><span data-stu-id="de52d-145">Targeting individual .NET implementations increases the `*.nupkg` size for no benefit.</span></span>

<span data-ttu-id="de52d-146">✔️ РЕКОМЕНДУЕТСЯ добавить целевую платформу для `net461`, если вы предлагаете целевую платформу `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="de52d-146">✔️ CONSIDER adding a target for `net461` when you're offering a `netstandard2.0` target.</span></span>

> <span data-ttu-id="de52d-147">Некоторые проблемы с использованием .NET Standard 2.0 в .NET Framework были устраненные в .NET Framework версии 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="de52d-147">Using .NET Standard 2.0 from .NET Framework has some issues that were addressed in .NET Framework 4.7.2.</span></span> <span data-ttu-id="de52d-148">Можно улучшить работу разработчиков, которые по-прежнему используют .NET Framework версий 4.6.1 — 4.7.1, предложив им двоичный файл, скомпилированный для .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="de52d-148">You can improve the experience for developers that are still on .NET Framework 4.6.1 - 4.7.1 by offering them a binary that is built for .NET Framework 4.6.1.</span></span>

<span data-ttu-id="de52d-149">✔️ DO Распространение библиотеки с помощью пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="de52d-149">✔️ DO distribute your library using a NuGet package.</span></span>

> <span data-ttu-id="de52d-150">NuGet определит для разработчиков наиболее подходящую целевую платформу и избавит их от необходимости выбирать подходящую реализацию.</span><span class="sxs-lookup"><span data-stu-id="de52d-150">NuGet will select the best target for the developer and shield them having to pick the appropriate implementation.</span></span>

<span data-ttu-id="de52d-151">✔️ СЛЕДУЕТ использовать свойство `TargetFrameworks` файла проекта при многоплатформенном нацеливании.</span><span class="sxs-lookup"><span data-stu-id="de52d-151">✔️ DO use a project file's `TargetFrameworks` property when multi-targeting.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <!-- This project will output netstandard2.0 and net461 assemblies -->
    <TargetFrameworks>netstandard2.0;net461</TargetFrameworks>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="de52d-152">✔ РЕКОМЕНДУЕТСЯ использовать [MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras) при многоплатформенном нацеливании на UWP и Xamarin, так как это значительно упрощает файл проекта.</span><span class="sxs-lookup"><span data-stu-id="de52d-152">✔️ CONSIDER using [MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras) when multi-targeting for UWP and Xamarin as it greatly simplifies your project file.</span></span>

## <a name="older-targets"></a><span data-ttu-id="de52d-153">Старые целевые платформы</span><span class="sxs-lookup"><span data-stu-id="de52d-153">Older targets</span></span>

<span data-ttu-id="de52d-154">.NET поддерживает работу с уже неподдерживаемыми версиями .NET Framework, а также с редко используемыми платформами.</span><span class="sxs-lookup"><span data-stu-id="de52d-154">.NET supports targeting versions of the .NET Framework that are long out of support as well as platforms that are no longer commonly used.</span></span> <span data-ttu-id="de52d-155">Поддержка библиотекой максимального числа платформ в некотором смысле оправдана, но реализация решений для отсутствующих API может привести к значительному увеличению размера библиотеки.</span><span class="sxs-lookup"><span data-stu-id="de52d-155">While there's value in making your library work on as many targets as possible, having to work around missing APIs can add significant overhead.</span></span> <span data-ttu-id="de52d-156">Мы считаем нецелесообразным обеспечивать поддержку некоторых платформ, учитывая их малую распространенность и ограничения.</span><span class="sxs-lookup"><span data-stu-id="de52d-156">We believe certain frameworks are no longer worth targeting, considering their reach and limitations.</span></span>

<span data-ttu-id="de52d-157">❌ НЕ️ СЛЕДУЕТ добавлять целевую платформу переносимой библиотеки классов (PCL).</span><span class="sxs-lookup"><span data-stu-id="de52d-157">❌ DO NOT include a Portable Class Library (PCL) target.</span></span> <span data-ttu-id="de52d-158">Например, `portable-net45+win8+wpa81+wp8`.</span><span class="sxs-lookup"><span data-stu-id="de52d-158">For example, `portable-net45+win8+wpa81+wp8`.</span></span>

> <span data-ttu-id="de52d-159">.NET Standard предлагает современный способ поддержки кроссплатформенных библиотек .NET и полностью заменяет PCL.</span><span class="sxs-lookup"><span data-stu-id="de52d-159">.NET Standard is the modern way to support cross-platform .NET libraries and replaces PCLs.</span></span>

<span data-ttu-id="de52d-160">❌ НЕ СЛЕДУЕТ добавлять поддержку платформ .NET, которые больше не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="de52d-160">❌ DO NOT include targets for .NET platforms that are no longer supported.</span></span> <span data-ttu-id="de52d-161">Например, `SL4`, `WP`.</span><span class="sxs-lookup"><span data-stu-id="de52d-161">For example, `SL4`, `WP`.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="de52d-162">[Назад](get-started.md)
>[Вперед](strong-naming.md)</span><span class="sxs-lookup"><span data-stu-id="de52d-162">[Previous](get-started.md)
[Next](strong-naming.md)</span></span>
