---
title: "Новые возможности .NET Standard"
ms.custom: updateeachrelease
ms.date: 11/08/2017
ms.prod: .net
ms.topic: article
ms.technology: dotnet-standard
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3a5833bdfcf1e3433ea82403908e9a06a88cde27
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="whats-new-in-the-net-standard"></a><span data-ttu-id="a8e6a-102">Новые возможности .NET Standard</span><span class="sxs-lookup"><span data-stu-id="a8e6a-102">What's new in the .NET Standard</span></span>

<span data-ttu-id="a8e6a-103">.NET Standard — это формальная спецификация, определяющая ряд версий с набором интерфейсов API, которые должны быть доступны во всех реализациях .NET, соответствующих определенной версии стандарта.</span><span class="sxs-lookup"><span data-stu-id="a8e6a-103">The .NET Standard is a formal specification that defines a versioned set of APIs which must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="a8e6a-104">Решение .NET Standard ориентировано на разработчиков библиотек.</span><span class="sxs-lookup"><span data-stu-id="a8e6a-104">The .NET Standard is targeted at library developers.</span></span> <span data-ttu-id="a8e6a-105">Библиотека, которая предназначена для некоторой версии .NET Standard, может использоваться в любой реализации .NET Framework, .NET Core или Xamarin, совместимой с той же версией стандарта.</span><span class="sxs-lookup"><span data-stu-id="a8e6a-105">A library that targets a .NET Standard version can be used on any .NET Framework, .NET Core, or Xamarin implementation that supports that version of the standard.</span></span>

<span data-ttu-id="a8e6a-106">Сейчас последней версией является .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="a8e6a-106">The most recent version of the .NET Standard is 2.0.</span></span> <span data-ttu-id="a8e6a-107">Она входит в пакет SDK для .NET Core 2.0, а также в Visual Studio 2017 версии 15.3 при установке с рабочей нагрузкой .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a8e6a-107">It is included with the .NET Core 2.0 SDK, as well as with Visual Studio 2017 Version 15.3 with the .NET Core workload installed.</span></span>

## <a name="supported-net-implementations"></a><span data-ttu-id="a8e6a-108">Поддерживаемые реализации .NET</span><span class="sxs-lookup"><span data-stu-id="a8e6a-108">Supported .NET implementations</span></span>

<span data-ttu-id="a8e6a-109">.NET Standard 2.0 поддерживается следующими реализациями .NET:</span><span class="sxs-lookup"><span data-stu-id="a8e6a-109">The .NET Standard 2.0 is supported by the following .NET implementations:</span></span>

- <span data-ttu-id="a8e6a-110">.NET Core 2.0;</span><span class="sxs-lookup"><span data-stu-id="a8e6a-110">.NET Core 2.0</span></span>
- <span data-ttu-id="a8e6a-111">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="a8e6a-111">.NET Framework 4.6.1</span></span>
- <span data-ttu-id="a8e6a-112">Mono 5.4</span><span class="sxs-lookup"><span data-stu-id="a8e6a-112">Mono 5.4</span></span>
- <span data-ttu-id="a8e6a-113">Xamarin.iOS 10.14</span><span class="sxs-lookup"><span data-stu-id="a8e6a-113">Xamarin.iOS 10.14</span></span>
- <span data-ttu-id="a8e6a-114">Xamarin.Mac 3.8</span><span class="sxs-lookup"><span data-stu-id="a8e6a-114">Xamarin.Mac 3.8</span></span>
- <span data-ttu-id="a8e6a-115">Xamarin.Android 8.0;</span><span class="sxs-lookup"><span data-stu-id="a8e6a-115">Xamarin.Android 8.0</span></span>
- <span data-ttu-id="a8e6a-116">универсальная платформа Windows 10.0.16299.</span><span class="sxs-lookup"><span data-stu-id="a8e6a-116">Universal Windows Platform 10.0.16299</span></span>

## <a name="whats-new-in-the-net-standard-20"></a><span data-ttu-id="a8e6a-117">Новые возможности .NET Standard 2.0</span><span class="sxs-lookup"><span data-stu-id="a8e6a-117">What's new in the .NET Standard 2.0</span></span>
 
<span data-ttu-id="a8e6a-118">.NET Standard 2.0 содержит следующие новые функции и компоненты.</span><span class="sxs-lookup"><span data-stu-id="a8e6a-118">The .NET Standard 2.0 includes the following new features:</span></span>

<span data-ttu-id="a8e6a-119">**Значительно расширенный набор интерфейсов API**</span><span class="sxs-lookup"><span data-stu-id="a8e6a-119">**A vastly expanded set of APIs**</span></span>

<span data-ttu-id="a8e6a-120">Вплоть до версии 1.6 спецификация .NET Standard содержала сравнительно небольшой набор API-интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="a8e6a-120">Through version 1.6, the .NET Standard included a comparatively small subset of APIs.</span></span> <span data-ttu-id="a8e6a-121">Среди прочего, в их числе не было многих API, которые часто используются на платформах .NET Framework и Xamarin.</span><span class="sxs-lookup"><span data-stu-id="a8e6a-121">Among those excluded were many APIs that were commonly used in the .NET Framework or Xamarin.</span></span> <span data-ttu-id="a8e6a-122">Это усложняет разработку, так как разработчикам приходится искать подходящие средства для замены знакомых API при разработке приложений и библиотек для нескольких реализаций .NET.</span><span class="sxs-lookup"><span data-stu-id="a8e6a-122">This complicates development, since it requires that developers find suitable replacements for familiar APIs when they develop applications and libraries that target multiple .NET implementations.</span></span> <span data-ttu-id="a8e6a-123">В .NET Standard 2.0 это ограничение устранено: в стандарт добавлены более 20 000 интерфейсов API, недоступных в предыдущей версии .NET Standard 1.6.</span><span class="sxs-lookup"><span data-stu-id="a8e6a-123">The .NET Standard 2.0 addresses this limitation by adding over 20,000 more APIs than were available in .NET Standard 1.6, the previous version of the standard.</span></span> <span data-ttu-id="a8e6a-124">Список интерфейсов API, добавленных в .NET Standard 2.0 см. в [документе сравнения возможностей .NET Standard 2.0 и 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span><span class="sxs-lookup"><span data-stu-id="a8e6a-124">For a list of the APIs that have been added to the .NET Standard 2.0, see [.NET Standard 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span> 

<span data-ttu-id="a8e6a-125">Вот лишь некоторые возможности, добавленные в пространство имен <xref:System> .NET Standard 2.0:</span><span class="sxs-lookup"><span data-stu-id="a8e6a-125">Some of the additions to the <xref:System> namespace in .NET Standard 2.0 include:</span></span>

- <span data-ttu-id="a8e6a-126">поддержка класса <xref:System.AppDomain>;</span><span class="sxs-lookup"><span data-stu-id="a8e6a-126">Support for the <xref:System.AppDomain> class.</span></span>
- <span data-ttu-id="a8e6a-127">улучшенная поддержка работы с массивами из дополнительных элементов класса <xref:System.Array>;</span><span class="sxs-lookup"><span data-stu-id="a8e6a-127">Better support for working with arrays from additional members in the <xref:System.Array> class.</span></span>
- <span data-ttu-id="a8e6a-128">улучшенная поддержка работы с атрибутами из дополнительных элементов класса <xref:System.Attribute>;</span><span class="sxs-lookup"><span data-stu-id="a8e6a-128">Better support for working with attributes from additional members in the <xref:System.Attribute> class.</span></span>
- <span data-ttu-id="a8e6a-129">улучшенная поддержка календаря и дополнительных параметров форматирования для значений <xref:System.DateTime>;</span><span class="sxs-lookup"><span data-stu-id="a8e6a-129">Better calendar support and additional formatting options for <xref:System.DateTime> values.</span></span>
- <span data-ttu-id="a8e6a-130">дополнительные возможности округления <xref:System.Decimal>;</span><span class="sxs-lookup"><span data-stu-id="a8e6a-130">Additional <xref:System.Decimal> rounding functionality.</span></span>
- <span data-ttu-id="a8e6a-131">дополнительные функциональные возможности для класса <xref:System.Environment>;</span><span class="sxs-lookup"><span data-stu-id="a8e6a-131">Additional functionality in the <xref:System.Environment> class.</span></span>
- <span data-ttu-id="a8e6a-132">расширенный контроль над сборщиком мусора через класс <xref:System.GC>;</span><span class="sxs-lookup"><span data-stu-id="a8e6a-132">Enhanced control over the garbage collector through the <xref:System.GC> class.</span></span>
- <span data-ttu-id="a8e6a-133">улучшенная поддержка сравнения строк, перечисления и нормализации в классе <xref:System.String>;</span><span class="sxs-lookup"><span data-stu-id="a8e6a-133">Enhanced support for string comparison, enumeration, and normalization in the <xref:System.String> class.</span></span>
- <span data-ttu-id="a8e6a-134">поддержка перехода на летнее время в классах <xref:System.TimeZoneInfo.AdjustmentRule> и <xref:System.TimeZoneInfo.TransitionTime>;</span><span class="sxs-lookup"><span data-stu-id="a8e6a-134">Support for daylight saving adjustments and transition times in the <xref:System.TimeZoneInfo.AdjustmentRule> and <xref:System.TimeZoneInfo.TransitionTime> classes.</span></span>
- <span data-ttu-id="a8e6a-135">значительно улучшенная функциональность класса <xref:System.Type>;</span><span class="sxs-lookup"><span data-stu-id="a8e6a-135">Significantly enhanced functionality in the <xref:System.Type> class.</span></span>
- <span data-ttu-id="a8e6a-136">улучшенная поддержка десериализации объектов исключений благодаря новому конструктору исключений с параметрами <xref:System.Runtime.Serialization.SerializationInfo> и <xref:System.Runtime.Serialization.StreamingContext>.</span><span class="sxs-lookup"><span data-stu-id="a8e6a-136">Better support for deserialization of exception objects by adding an exception constructor with <xref:System.Runtime.Serialization.SerializationInfo> and <xref:System.Runtime.Serialization.StreamingContext> parameters.</span></span>

<span data-ttu-id="a8e6a-137">**Поддержка библиотек .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="a8e6a-137">**Support for .NET Framework libraries**</span></span>

<span data-ttu-id="a8e6a-138">Практически все библиотеки предназначены для .NET Framework, а не .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="a8e6a-138">The overwhelming majority of libraries target the .NET Framework rather than .NET Standard.</span></span> <span data-ttu-id="a8e6a-139">Но при этом большая часть вызовов в этих библиотеках направлена к интерфейсам API .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="a8e6a-139">However, most of the calls in those libraries are to APIs that are included in the .NET Standard 2.0.</span></span> <span data-ttu-id="a8e6a-140">Начиная с .NET Standard 2.0 библиотеки .NET Framework доступны из библиотек .NET Standard через [оболочку совместимости](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification).</span><span class="sxs-lookup"><span data-stu-id="a8e6a-140">Starting with the .NET Standard 2.0, you can access .NET Framework libraries from a .NET Standard library by using a [compatibility shim](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification).</span></span> <span data-ttu-id="a8e6a-141">Этот уровень совместимости прозрачен для разработчиков, то есть от них не требуется никаких действий, чтобы пользоваться библиотеками .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a8e6a-141">This compatibility layer is transparent to developers; you don't have to do anything to take advantage of .NET Framework libraries.</span></span>

<span data-ttu-id="a8e6a-142">Действует только одно требование: API, вызываемые библиотекой классов .NET Framework, должны быть включены в .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="a8e6a-142">The single requirement is that the APIs called by the .NET Framework class library must be included in the .NET Standard 2.0.</span></span>

<span data-ttu-id="a8e6a-143">**Поддержка Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="a8e6a-143">**Support for Visual Basic**</span></span>

<span data-ttu-id="a8e6a-144">Теперь вы можете разрабатывать библиотеки .NET Standard на Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a8e6a-144">You can now develop .NET Standard libraries in Visual Basic.</span></span> <span data-ttu-id="a8e6a-145">Разработчики Visual Basic, использующие Visual Studio 2017 версии 15.3 или более поздней версии с установленной рабочей нагрузкой .NET Core, теперь получают в Visual Studio шаблон библиотеки классов .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="a8e6a-145">For Visual Basic developers using Visual Studio 2017 Version 15.3 or later with the .NET Core workload installed, Visual Studio now includes a .NET Standard Class Library template.</span></span> <span data-ttu-id="a8e6a-146">Разработчики Visual Basic, которые используют другие средства и среды разработки, могут создать проект библиотеки .NET Standard с помощью команды [dotnet new](../../core/tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="a8e6a-146">For Visual Basic developers who use other development tools and environments, you can use the [dotnet new](../../core/tools/dotnet-new.md) command to create a .NET Standard Library project.</span></span> <span data-ttu-id="a8e6a-147">Дополнительные сведения см. в разделе [Поддержка средств для библиотек .NET Standard](#tooling).</span><span class="sxs-lookup"><span data-stu-id="a8e6a-147">For more information, see the [Tooling support for .NET Standard libraries](#tooling).</span></span>

<span data-ttu-id="a8e6a-148"><a name="tooling" />**Поддержка средств для библиотек .NET Standard**</span><span class="sxs-lookup"><span data-stu-id="a8e6a-148"><a name="tooling" />**Tooling support for .NET Standard libraries**</span></span>

<span data-ttu-id="a8e6a-149">С момента выхода .NET Core 2.0 и .NET Standard 2.0 поддержка средств для создания библиотек .NET Standard включена в Visual Studio 2017 и в [.NET Core CLI](../../core/tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="a8e6a-149">With the release of .NET Core 2.0 and .NET Standard 2.0, both Visual Studio 2017 and the [.NET Core Command Line Interface (CLI)](../../core/tools/index.md) include tooling support for creating .NET Standard libraries.</span></span> 

<span data-ttu-id="a8e6a-150">Если у вас установлен Visual Studio с рабочей нагрузкой **для кроссплатформенной разработки .NET Core**, вы можете создать проект библиотеки .NET Standard 2.0 с помощью шаблона проекта, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="a8e6a-150">If you install Visual Studio with the **.NET Core cross-platform development** workload, you can create a .NET Standard 2.0 library project by using a project template, as the following figure shows.</span></span> 

# <a name="ctabcsharp"></a>[<span data-ttu-id="a8e6a-151">C#</span><span class="sxs-lookup"><span data-stu-id="a8e6a-151">C#</span></span>](#tab/csharp)
![Добавление нового проекта библиотеки .NET Standard](./media/std-project-cs.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="a8e6a-153">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8e6a-153">Visual Basic</span></span>](#tab/visual-basic)
<a name="add-new-net-standard-library-projectmediastd-project-vbpng"></a>![Добавление нового проекта библиотеки .NET Standard](./media/std-project-vb.png)
---

<span data-ttu-id="a8e6a-155">Если вы используете .NET Core CLI, указанная ниже команда [dotnet new](../../core/tools/dotnet-new.md) создает проект библиотеки классов, предназначенный для .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="a8e6a-155">If you are using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets the .NET Standard 2.0.</span></span>

```csharp
dotnet new classlib
```
```vb
dotnet new classlib -lang vb
```
  
## <a name="see-also"></a><span data-ttu-id="a8e6a-156">См. также</span><span class="sxs-lookup"><span data-stu-id="a8e6a-156">See Also</span></span>
<span data-ttu-id="a8e6a-157">[.NET Standard](../net-standard.md)
[Объявление о выпуске .NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)</span><span class="sxs-lookup"><span data-stu-id="a8e6a-157">[.NET Standard](../net-standard.md)
[Introducing .NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)</span></span>
