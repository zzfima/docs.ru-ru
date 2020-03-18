---
title: Новые возможности .NET Standard
description: В этой статье перечислены новые возможности и улучшения в каждой новой версии платформы .NET Standard.
ms.custom: updateeachrelease
ms.date: 04/12/2018
ms.technology: dotnet-standard
ms.openlocfilehash: a90df0360211c3b02f4f2d8697890180099c5807
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "76921059"
---
# <a name="whats-new-in-the-net-standard"></a><span data-ttu-id="d1d95-103">Новые возможности .NET Standard</span><span class="sxs-lookup"><span data-stu-id="d1d95-103">What's new in the .NET Standard</span></span>

<span data-ttu-id="d1d95-104">.NET Standard — это формальная спецификация, определяющая ряд версий с набором интерфейсов API, которые должны быть доступны во всех реализациях .NET, соответствующих определенной версии стандарта.</span><span class="sxs-lookup"><span data-stu-id="d1d95-104">The .NET Standard is a formal specification that defines a versioned set of APIs that must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="d1d95-105">Решение .NET Standard ориентировано на разработчиков библиотек.</span><span class="sxs-lookup"><span data-stu-id="d1d95-105">The .NET Standard is targeted at library developers.</span></span> <span data-ttu-id="d1d95-106">Библиотека, которая предназначена для некоторой версии .NET Standard, может использоваться в любой реализации .NET Framework, .NET Core или Xamarin, совместимой с той же версией стандарта.</span><span class="sxs-lookup"><span data-stu-id="d1d95-106">A library that targets a .NET Standard version can be used on any .NET Framework, .NET Core, or Xamarin implementation that supports that version of the standard.</span></span>

<span data-ttu-id="d1d95-107">Сейчас последней версией является .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="d1d95-107">The most recent version of the .NET Standard is 2.0.</span></span> <span data-ttu-id="d1d95-108">Она входит в пакет SDK для .NET Core 2.0, а также в Visual Studio 2017 версии 15.3 при установленной рабочей нагрузке .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d1d95-108">It is included with the .NET Core 2.0 SDK, as well as with Visual Studio 2017 version 15.3 with the .NET Core workload installed.</span></span>

## <a name="supported-net-implementations"></a><span data-ttu-id="d1d95-109">Поддерживаемые реализации .NET</span><span class="sxs-lookup"><span data-stu-id="d1d95-109">Supported .NET implementations</span></span>

<span data-ttu-id="d1d95-110">.NET Standard 2.0 поддерживается следующими реализациями .NET:</span><span class="sxs-lookup"><span data-stu-id="d1d95-110">The .NET Standard 2.0 is supported by the following .NET implementations:</span></span>

- <span data-ttu-id="d1d95-111">.NET Core 2.0 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="d1d95-111">.NET Core 2.0 or later</span></span>
- <span data-ttu-id="d1d95-112">.NET Framework 4.6.1 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="d1d95-112">.NET Framework 4.6.1 or later</span></span>
- <span data-ttu-id="d1d95-113">Mono 5.4 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="d1d95-113">Mono 5.4 or later</span></span>
- <span data-ttu-id="d1d95-114">Xamarin.iOS 10.14 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="d1d95-114">Xamarin.iOS 10.14 or later</span></span>
- <span data-ttu-id="d1d95-115">Xamarin.Mac 3.8 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="d1d95-115">Xamarin.Mac 3.8 or later</span></span>
- <span data-ttu-id="d1d95-116">Xamarin.Android 8.0 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="d1d95-116">Xamarin.Android 8.0 or later</span></span>
- <span data-ttu-id="d1d95-117">Универсальная платформа Windows 10.0.16299 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="d1d95-117">Universal Windows Platform 10.0.16299 or later</span></span>

## <a name="whats-new-in-the-net-standard-20"></a><span data-ttu-id="d1d95-118">Новые возможности .NET Standard 2.0</span><span class="sxs-lookup"><span data-stu-id="d1d95-118">What's new in the .NET Standard 2.0</span></span>

<span data-ttu-id="d1d95-119">.NET Standard 2.0 содержит следующие новые функции и компоненты.</span><span class="sxs-lookup"><span data-stu-id="d1d95-119">The .NET Standard 2.0 includes the following new features:</span></span>

### <a name="a-vastly-expanded-set-of-apis"></a><span data-ttu-id="d1d95-120">Значительно расширенный набор интерфейсов API</span><span class="sxs-lookup"><span data-stu-id="d1d95-120">A vastly expanded set of APIs</span></span>

<span data-ttu-id="d1d95-121">Вплоть до версии 1.6 спецификация .NET Standard содержала сравнительно небольшой набор API-интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="d1d95-121">Through version 1.6, the .NET Standard included a comparatively small subset of APIs.</span></span> <span data-ttu-id="d1d95-122">Среди прочего, в их числе не было многих API, которые часто используются на платформах .NET Framework и Xamarin.</span><span class="sxs-lookup"><span data-stu-id="d1d95-122">Among those excluded were many APIs that were commonly used in the .NET Framework or Xamarin.</span></span> <span data-ttu-id="d1d95-123">Это усложняет разработку, так как разработчикам приходится искать подходящие средства для замены знакомых API при разработке приложений и библиотек для нескольких реализаций .NET.</span><span class="sxs-lookup"><span data-stu-id="d1d95-123">This complicates development, since it requires that developers find suitable replacements for familiar APIs when they develop applications and libraries that target multiple .NET implementations.</span></span> <span data-ttu-id="d1d95-124">В .NET Standard 2.0 это ограничение устранено: в стандарт добавлены более 20 000 интерфейсов API, недоступных в предыдущей версии .NET Standard 1.6.</span><span class="sxs-lookup"><span data-stu-id="d1d95-124">The .NET Standard 2.0 addresses this limitation by adding over 20,000 more APIs than were available in .NET Standard 1.6, the previous version of the standard.</span></span> <span data-ttu-id="d1d95-125">Список интерфейсов API, добавленных в .NET Standard 2.0 см. в [документе сравнения возможностей .NET Standard 2.0 и 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span><span class="sxs-lookup"><span data-stu-id="d1d95-125">For a list of the APIs that have been added to the .NET Standard 2.0, see [.NET Standard 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span>

<span data-ttu-id="d1d95-126">Вот лишь некоторые возможности, добавленные в пространство имен <xref:System> .NET Standard 2.0:</span><span class="sxs-lookup"><span data-stu-id="d1d95-126">Some of the additions to the <xref:System> namespace in .NET Standard 2.0 include:</span></span>

- <span data-ttu-id="d1d95-127">поддержка класса <xref:System.AppDomain>;</span><span class="sxs-lookup"><span data-stu-id="d1d95-127">Support for the <xref:System.AppDomain> class.</span></span>
- <span data-ttu-id="d1d95-128">улучшенная поддержка работы с массивами из дополнительных элементов класса <xref:System.Array>;</span><span class="sxs-lookup"><span data-stu-id="d1d95-128">Better support for working with arrays from additional members in the <xref:System.Array> class.</span></span>
- <span data-ttu-id="d1d95-129">улучшенная поддержка работы с атрибутами из дополнительных элементов класса <xref:System.Attribute>;</span><span class="sxs-lookup"><span data-stu-id="d1d95-129">Better support for working with attributes from additional members in the <xref:System.Attribute> class.</span></span>
- <span data-ttu-id="d1d95-130">улучшенная поддержка календаря и дополнительных параметров форматирования для значений <xref:System.DateTime>;</span><span class="sxs-lookup"><span data-stu-id="d1d95-130">Better calendar support and additional formatting options for <xref:System.DateTime> values.</span></span>
- <span data-ttu-id="d1d95-131">дополнительные возможности округления <xref:System.Decimal>;</span><span class="sxs-lookup"><span data-stu-id="d1d95-131">Additional <xref:System.Decimal> rounding functionality.</span></span>
- <span data-ttu-id="d1d95-132">дополнительные функциональные возможности для класса <xref:System.Environment>;</span><span class="sxs-lookup"><span data-stu-id="d1d95-132">Additional functionality in the <xref:System.Environment> class.</span></span>
- <span data-ttu-id="d1d95-133">расширенный контроль над сборщиком мусора через класс <xref:System.GC>;</span><span class="sxs-lookup"><span data-stu-id="d1d95-133">Enhanced control over the garbage collector through the <xref:System.GC> class.</span></span>
- <span data-ttu-id="d1d95-134">улучшенная поддержка сравнения строк, перечисления и нормализации в классе <xref:System.String>;</span><span class="sxs-lookup"><span data-stu-id="d1d95-134">Enhanced support for string comparison, enumeration, and normalization in the <xref:System.String> class.</span></span>
- <span data-ttu-id="d1d95-135">поддержка перехода на летнее время в классах <xref:System.TimeZoneInfo.AdjustmentRule> и <xref:System.TimeZoneInfo.TransitionTime>;</span><span class="sxs-lookup"><span data-stu-id="d1d95-135">Support for daylight saving adjustments and transition times in the <xref:System.TimeZoneInfo.AdjustmentRule> and <xref:System.TimeZoneInfo.TransitionTime> classes.</span></span>
- <span data-ttu-id="d1d95-136">значительно улучшенная функциональность класса <xref:System.Type>;</span><span class="sxs-lookup"><span data-stu-id="d1d95-136">Significantly enhanced functionality in the <xref:System.Type> class.</span></span>
- <span data-ttu-id="d1d95-137">улучшенная поддержка десериализации объектов исключений благодаря новому конструктору исключений с параметрами <xref:System.Runtime.Serialization.SerializationInfo> и <xref:System.Runtime.Serialization.StreamingContext>.</span><span class="sxs-lookup"><span data-stu-id="d1d95-137">Better support for deserialization of exception objects by adding an exception constructor with <xref:System.Runtime.Serialization.SerializationInfo> and <xref:System.Runtime.Serialization.StreamingContext> parameters.</span></span>

### <a name="support-for-net-framework-libraries"></a><span data-ttu-id="d1d95-138">Поддержка библиотек .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d1d95-138">Support for .NET Framework libraries</span></span>

<span data-ttu-id="d1d95-139">Практически все библиотеки предназначены для .NET Framework, а не .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="d1d95-139">The overwhelming majority of libraries target the .NET Framework rather than .NET Standard.</span></span> <span data-ttu-id="d1d95-140">Но при этом большая часть вызовов в этих библиотеках направлена к интерфейсам API .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="d1d95-140">However, most of the calls in those libraries are to APIs that are included in the .NET Standard 2.0.</span></span> <span data-ttu-id="d1d95-141">Начиная с .NET Standard 2.0 библиотеки .NET Framework доступны из библиотек .NET Standard через [оболочку совместимости](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#assembly-unification).</span><span class="sxs-lookup"><span data-stu-id="d1d95-141">Starting with the .NET Standard 2.0, you can access .NET Framework libraries from a .NET Standard library by using a [compatibility shim](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#assembly-unification).</span></span> <span data-ttu-id="d1d95-142">Этот уровень совместимости прозрачен для разработчиков, то есть от них не требуется никаких действий, чтобы пользоваться библиотеками .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d1d95-142">This compatibility layer is transparent to developers; you don't have to do anything to take advantage of .NET Framework libraries.</span></span>

<span data-ttu-id="d1d95-143">Действует только одно требование: API, вызываемые библиотекой классов .NET Framework, должны быть включены в .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="d1d95-143">The single requirement is that the APIs called by the .NET Framework class library must be included in the .NET Standard 2.0.</span></span>

### <a name="support-for-visual-basic"></a><span data-ttu-id="d1d95-144">Поддержка Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d1d95-144">Support for Visual Basic</span></span>

<span data-ttu-id="d1d95-145">Теперь вы можете разрабатывать библиотеки .NET Standard на Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d1d95-145">You can now develop .NET Standard libraries in Visual Basic.</span></span> <span data-ttu-id="d1d95-146">Разработчики Visual Basic, использующие Visual Studio 2017 версии 15.3 или более поздней версии с установленной рабочей нагрузкой .NET Core, теперь получают в Visual Studio шаблон библиотеки классов .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="d1d95-146">For Visual Basic developers using Visual Studio 2017 version 15.3 or later with the .NET Core workload installed, Visual Studio now includes a .NET Standard Class Library template.</span></span> <span data-ttu-id="d1d95-147">Разработчики Visual Basic, которые используют другие средства и среды разработки, могут создать проект библиотеки .NET Standard с помощью команды [dotnet new](../../core/tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="d1d95-147">For Visual Basic developers who use other development tools and environments, you can use the [dotnet new](../../core/tools/dotnet-new.md) command to create a .NET Standard Library project.</span></span> <span data-ttu-id="d1d95-148">Дополнительные сведения см. в разделе [Поддержка средств для библиотек .NET Standard](#tooling-support-for-net-standard-libraries).</span><span class="sxs-lookup"><span data-stu-id="d1d95-148">For more information, see the [Tooling support for .NET Standard libraries](#tooling-support-for-net-standard-libraries).</span></span>

### <a name="tooling-support-for-net-standard-libraries"></a><span data-ttu-id="d1d95-149">Поддержка средств для библиотек .NET Standard</span><span class="sxs-lookup"><span data-stu-id="d1d95-149">Tooling support for .NET Standard libraries</span></span>

<span data-ttu-id="d1d95-150">С момента выхода .NET Core 2.0 и .NET Standard 2.0 поддержка средств для создания библиотек .NET Standard включена в Visual Studio 2017 и [.NET Core CLI](../../core/tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="d1d95-150">With the release of .NET Core 2.0 and .NET Standard 2.0, both Visual Studio 2017 and the [.NET Core CLI](../../core/tools/index.md) include tooling support for creating .NET Standard libraries.</span></span>

<span data-ttu-id="d1d95-151">Если у вас установлен Visual Studio с рабочей нагрузкой **для кроссплатформенной разработки .NET Core**, вы можете создать проект библиотеки .NET Standard 2.0 с помощью шаблона проекта, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="d1d95-151">If you install Visual Studio with the **.NET Core cross-platform development** workload, you can create a .NET Standard 2.0 library project by using a project template, as the following figure shows:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[<span data-ttu-id="d1d95-152">C#</span><span class="sxs-lookup"><span data-stu-id="d1d95-152">C#</span></span>](#tab/csharp)

![Добавление нового проекта библиотеки .NET Standard](./media/std-project-cs.png)

<span data-ttu-id="d1d95-154">Если вы используете .NET Core CLI, указанная ниже команда [dotnet new](../../core/tools/dotnet-new.md) создает проект библиотеки классов, предназначенный для .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="d1d95-154">If you're using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets the .NET Standard 2.0:</span></span>

```dotnetcli
dotnet new classlib
```

# <a name="visual-basic"></a>[<span data-ttu-id="d1d95-155">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d1d95-155">Visual Basic</span></span>](#tab/vb)

![Добавление нового проекта библиотеки .NET Standard](./media/std-project-vb.png)

<span data-ttu-id="d1d95-157">Если вы используете .NET Core CLI, указанная ниже команда [dotnet new](../../core/tools/dotnet-new.md) создает проект библиотеки классов, предназначенный для .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="d1d95-157">If you're using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets the .NET Standard 2.0:</span></span>

```dotnetcli
dotnet new classlib -lang vb
```

---

## <a name="see-also"></a><span data-ttu-id="d1d95-158">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d1d95-158">See also</span></span>

- [<span data-ttu-id="d1d95-159">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="d1d95-159">.NET Standard</span></span>](../net-standard.md)
- [<span data-ttu-id="d1d95-160">Введение в .NET Standard</span><span class="sxs-lookup"><span data-stu-id="d1d95-160">Introducing .NET Standard</span></span>](https://devblogs.microsoft.com/dotnet/introducing-net-standard/)
