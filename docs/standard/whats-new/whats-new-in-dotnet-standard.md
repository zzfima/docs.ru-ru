---
title: "Новые возможности .NET Standard"
ms.custom: updateeachrelease
ms.date: 11/08/2017
ms.prod: .net
ms.topic: article
ms.technology: dotnet-standard
ms.##devlang: dotnet
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e938c009b79af3b2f36094bbb74f4d38baeeac0b
ms.sourcegitcommit: 281070dee88db86ec3bb4634d5f558d1a4e159dd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2017
---
# <a name="whats-new-in-the-net-standard"></a><span data-ttu-id="fa727-102">Новые возможности .NET Standard</span><span class="sxs-lookup"><span data-stu-id="fa727-102">What's new in the .NET Standard</span></span>

<span data-ttu-id="fa727-103">.NET Standard имеет формальные спецификация, определяющая набор с версиями интерфейсы API, которые должны быть доступны в реализациях .NET, соответствующие этой версии стандарта.</span><span class="sxs-lookup"><span data-stu-id="fa727-103">The .NET Standard is a formal specification that defines a versioned set of APIs which must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="fa727-104">Решение .NET Standard ориентировано на разработчиков библиотек.</span><span class="sxs-lookup"><span data-stu-id="fa727-104">The .NET Standard is targeted at library developers.</span></span> <span data-ttu-id="fa727-105">Это библиотека, которая ссылается на версию .NET Standard можно использовать в любой реализации .NET Framework, .NET Core или Xamarin, совместимый с этой версией стандартной.</span><span class="sxs-lookup"><span data-stu-id="fa727-105">A library that targets a .NET Standard version can be used on any .NET Framework, .NET Core, or Xamarin implementation that supports that version of the standard.</span></span>

<span data-ttu-id="fa727-106">Самую последнюю версию .NET Standard является версия 2.0.</span><span class="sxs-lookup"><span data-stu-id="fa727-106">The most recent version of the .NET Standard is 2.0.</span></span> <span data-ttu-id="fa727-107">Он включен с помощью пакета SDK .NET Core 2.0, а также с Visual Studio 2017 г. версия 15,3 с рабочей нагрузкой .NET Core установлен.</span><span class="sxs-lookup"><span data-stu-id="fa727-107">It is included with the .NET Core 2.0 SDK, as well as with Visual Studio 2017 Version 15.3 with the .NET Core workload installed.</span></span>

## <a name="supported-net-implementations"></a><span data-ttu-id="fa727-108">Поддерживаемые реализаций .NET</span><span class="sxs-lookup"><span data-stu-id="fa727-108">Supported .NET implementations</span></span>

<span data-ttu-id="fa727-109">Стандартная .NET 2.0 поддерживается следующими реализациями .NET:</span><span class="sxs-lookup"><span data-stu-id="fa727-109">The .NET Standard 2.0 is supported by the following .NET implementations:</span></span>

- <span data-ttu-id="fa727-110">.NET core 2.0</span><span class="sxs-lookup"><span data-stu-id="fa727-110">.NET Core 2.0</span></span>
- <span data-ttu-id="fa727-111">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="fa727-111">.NET Framework 4.6.1</span></span>
- <span data-ttu-id="fa727-112">Моно 5.4.</span><span class="sxs-lookup"><span data-stu-id="fa727-112">Mono 5.4</span></span>
- <span data-ttu-id="fa727-113">Xamarin.iOS 10.14</span><span class="sxs-lookup"><span data-stu-id="fa727-113">Xamarin.iOS 10.14</span></span>
- <span data-ttu-id="fa727-114">Xamarin.Mac 3.8</span><span class="sxs-lookup"><span data-stu-id="fa727-114">Xamarin.Mac 3.8</span></span>
- <span data-ttu-id="fa727-115">Xamarin.Android 8.0</span><span class="sxs-lookup"><span data-stu-id="fa727-115">Xamarin.Android 8.0</span></span>
- <span data-ttu-id="fa727-116">Универсальная платформа Windows 10.0.16299</span><span class="sxs-lookup"><span data-stu-id="fa727-116">Universal Windows Platform 10.0.16299</span></span>

## <a name="whats-new-in-the-net-standard-20"></a><span data-ttu-id="fa727-117">Новые возможности .NET Standard 2.0</span><span class="sxs-lookup"><span data-stu-id="fa727-117">What's new in the .NET Standard 2.0</span></span>
 
<span data-ttu-id="fa727-118">Стандартная .NET 2.0 включает следующие новые функции:</span><span class="sxs-lookup"><span data-stu-id="fa727-118">The .NET Standard 2.0 includes the following new features:</span></span>

<span data-ttu-id="fa727-119">**Значительно расширенный набор интерфейсов API**</span><span class="sxs-lookup"><span data-stu-id="fa727-119">**A vastly expanded set of APIs**</span></span>

<span data-ttu-id="fa727-120">До версии 1.6 .NET Standard включены сравнительно небольшой набор API-интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="fa727-120">Through version 1.6, the .NET Standard included a comparatively small subset of APIs.</span></span> <span data-ttu-id="fa727-121">Среди тех исключен были многие API, которые часто использовались в .NET Framework или Xamarin.</span><span class="sxs-lookup"><span data-stu-id="fa727-121">Among those excluded were many APIs that were commonly used in the .NET Framework or Xamarin.</span></span> <span data-ttu-id="fa727-122">Это осложняет разработки, так как оно требует разработчикам искать подходящие замены для знакомы API при их разработке приложений и библиотек, предназначенных для нескольких реализаций .NET.</span><span class="sxs-lookup"><span data-stu-id="fa727-122">This complicates development, since it requires that developers find suitable replacements for familiar APIs when they develop applications and libraries that target multiple .NET implementations.</span></span> <span data-ttu-id="fa727-123">Стандартная .NET 2.0 это ограничение адреса путем добавления до 20 000 интерфейсов API не были доступны в стандартных .NET версии 1.6, предыдущие версии стандарта.</span><span class="sxs-lookup"><span data-stu-id="fa727-123">The .NET Standard 2.0 addresses this limitation by adding over 20,000 more APIs than were available in .NET Standard 1.6, the previous version of the standard.</span></span> <span data-ttu-id="fa727-124">Список API, которые были добавлены к стандартной .NET 2.0 см. в разделе [vs .NET 2.0 стандартная 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span><span class="sxs-lookup"><span data-stu-id="fa727-124">For a list of the APIs that have been added to the .NET Standard 2.0, see [.NET Standard 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span> 

<span data-ttu-id="fa727-125">Некоторые добавления к <xref:System> пространства имен в .NET 2.0 стандартная включают:</span><span class="sxs-lookup"><span data-stu-id="fa727-125">Some of the additions to the <xref:System> namespace in .NET Standard 2.0 include:</span></span>

- <span data-ttu-id="fa727-126">Поддержка <xref:System.AppDomain> класса.</span><span class="sxs-lookup"><span data-stu-id="fa727-126">Support for the <xref:System.AppDomain> class.</span></span>
- <span data-ttu-id="fa727-127">Улучшенная поддержка работы с массивами из дополнительных членов в <xref:System.Array> класса.</span><span class="sxs-lookup"><span data-stu-id="fa727-127">Better support for working with arrays from additional members in the <xref:System.Array> class.</span></span>
- <span data-ttu-id="fa727-128">Улучшенная поддержка работа с атрибутами дополнительных членов в <xref:System.Attribute> класса.</span><span class="sxs-lookup"><span data-stu-id="fa727-128">Better support for working with attributes from additional members in the <xref:System.Attribute> class.</span></span>
- <span data-ttu-id="fa727-129">Лучше календарь поддержки и дополнительные параметры форматирования для <xref:System.DateTime> значения.</span><span class="sxs-lookup"><span data-stu-id="fa727-129">Better calendar support and additional formatting options for <xref:System.DateTime> values.</span></span>
- <span data-ttu-id="fa727-130">Дополнительные <xref:System.Decimal> округления функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="fa727-130">Additional <xref:System.Decimal> rounding functionality.</span></span>
- <span data-ttu-id="fa727-131">Дополнительные возможности в <xref:System.Environment> класса.</span><span class="sxs-lookup"><span data-stu-id="fa727-131">Additional functionality in the <xref:System.Environment> class.</span></span>
- <span data-ttu-id="fa727-132">Расширенный контроль над сборщик мусора через <xref:System.GC> класса.</span><span class="sxs-lookup"><span data-stu-id="fa727-132">Enhanced control over the garbage collector through the <xref:System.GC> class.</span></span>
- <span data-ttu-id="fa727-133">Улучшенная поддержка для сравнения строк, перечисления и нормализации в <xref:System.String> класса.</span><span class="sxs-lookup"><span data-stu-id="fa727-133">Enhanced support for string comparison, enumeration, and normalization in the <xref:System.String> class.</span></span>
- <span data-ttu-id="fa727-134">Поддержка летнему корректировки и времени перехода в <xref:System.TimeZoneInfo.AdjustmentRule> и <xref:System.TimeZoneInfo.TransitionTime> классы.</span><span class="sxs-lookup"><span data-stu-id="fa727-134">Support for daylight saving adjustments and transition times in the <xref:System.TimeZoneInfo.AdjustmentRule> and <xref:System.TimeZoneInfo.TransitionTime> classes.</span></span>
- <span data-ttu-id="fa727-135">Значительно улучшено функциональные возможности <xref:System.Type> класса.</span><span class="sxs-lookup"><span data-stu-id="fa727-135">Significantly enhanced functionality in the <xref:System.Type> class.</span></span>
- <span data-ttu-id="fa727-136">Улучшенная поддержка десериализации объектов исключений путем добавления к конструктору исключения с <xref:System.Runtime.Serialization.SerializationInfo> и <xref:System.Runtime.Serialization.StreamingContext> параметров.</span><span class="sxs-lookup"><span data-stu-id="fa727-136">Better support for deserialization of exception objects by adding an exception constructor with <xref:System.Runtime.Serialization.SerializationInfo> and <xref:System.Runtime.Serialization.StreamingContext> parameters.</span></span>

<span data-ttu-id="fa727-137">**Поддержка библиотек .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="fa727-137">**Support for .NET Framework libraries**</span></span>

<span data-ttu-id="fa727-138">Просто огромным большинство библиотек целевой платформы .NET Framework, а не .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="fa727-138">The overwhelming majority of libraries target the .NET Framework rather than .NET Standard.</span></span> <span data-ttu-id="fa727-139">Однако большая часть вызовов в этих библиотек, API-интерфейсов, включенные в стандартный .NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="fa727-139">However, most of the calls in those libraries are to APIs that are included in the .NET Standard 2.0.</span></span> <span data-ttu-id="fa727-140">Начиная с .NET Standard 2.0, доступны библиотеки .NET Framework из .NET Standard библиотеки с помощью [оболочку совместимости](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification).</span><span class="sxs-lookup"><span data-stu-id="fa727-140">Starting with the .NET Standard 2.0, you can access .NET Framework libraries from a .NET Standard library by using a [compatibility shim](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification).</span></span> <span data-ttu-id="fa727-141">Этот уровень совместимости прозрачно для разработчиков; не нужно ничего делать, чтобы воспользоваться преимуществами библиотеки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fa727-141">This compatibility layer is transparent to developers; you don't have to do anything to take advantage of .NET Framework libraries.</span></span>

<span data-ttu-id="fa727-142">Один требуется, что API, вызываемые библиотекой классов .NET Framework должен быть включен в стандартных .NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="fa727-142">The single requirement is that the APIs called by the .NET Framework class library must be included in the .NET Standard 2.0.</span></span>

<span data-ttu-id="fa727-143">**Поддержка Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="fa727-143">**Support for Visual Basic**</span></span>

<span data-ttu-id="fa727-144">Теперь можно разрабатывать .NET стандартных библиотек в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="fa727-144">You can now develop .NET Standard libraries in Visual Basic.</span></span> <span data-ttu-id="fa727-145">Разработчики Visual Basic, с помощью Visual Studio 2017 г. версия 15,3 или более поздней версии с рабочей нагрузкой .NET Core установлены Visual Studio теперь включает шаблон Стандартная библиотека классов .NET.</span><span class="sxs-lookup"><span data-stu-id="fa727-145">For Visual Basic developers using Visual Studio 2017 Version 15.3 or later with the .NET Core workload installed, Visual Studio now includes a .NET Standard Class Library template.</span></span> <span data-ttu-id="fa727-146">Для разработчиков Visual Basic, которые используют другие средства разработки и среды, можно использовать [dotnet новый](../../core/tools/dotnet-new.md) команду, чтобы создать проект стандартной библиотеки .NET.</span><span class="sxs-lookup"><span data-stu-id="fa727-146">For Visual Basic developers who use other development tools and environments, you can use the [dotnet new](../../core/tools/dotnet-new.md) command to create a .NET Standard Library project.</span></span> <span data-ttu-id="fa727-147">Дополнительные сведения см. в разделе [средства поддержки для библиотек .NET Standard](#tooling).</span><span class="sxs-lookup"><span data-stu-id="fa727-147">For more information, see the [Tooling support for .NET Standard libraries](#tooling).</span></span>

<span data-ttu-id="fa727-148"><a name="tooling" />**Поддержка инструментами .NET стандартные библиотеки**</span><span class="sxs-lookup"><span data-stu-id="fa727-148"><a name="tooling" />**Tooling support for .NET Standard libraries**</span></span>

<span data-ttu-id="fa727-149">С выпуском ядра .NET 2.0 и .NET 2.0 Standard, как Visual Studio 2017 г. и [.NET Core интерфейс командной строки (CLI)](../../core/tools/index.md) включает инструменты для создания библиотеки .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="fa727-149">With the release of .NET Core 2.0 and .NET Standard 2.0, both Visual Studio 2017 and the [.NET Core Command Line Interface (CLI)](../../core/tools/index.md) include tooling support for creating .NET Standard libraries.</span></span> 

<span data-ttu-id="fa727-150">При установке Visual Studio с **кросс платформенной разработки .NET Core** рабочей нагрузки, можно создать проект библиотеки .NET Standard 2.0 с помощью шаблона проекта, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="fa727-150">If you install Visual Studio with the **.NET Core cross-platform development** workload, you can create a .NET Standard 2.0 library project by using a project template, as the following figure shows.</span></span> 

# <a name="ctabcsharp"></a>[<span data-ttu-id="fa727-151">C#</span><span class="sxs-lookup"><span data-stu-id="fa727-151">C#</span></span>](#tab/csharp)
![Добавьте новый .NET Standard проект библиотеки](./media/std-project-cs.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="fa727-153">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fa727-153">Visual Basic</span></span>](#tab/visual-basic)
<a name="add-new-net-standard-library-projectmediastd-project-vbpng"></a>![Добавьте новый .NET Standard проект библиотеки](./media/std-project-vb.png)
---

<span data-ttu-id="fa727-155">Если вы используете .NET Core (CLI), следующие [dotnet новый](../../core/tools/dotnet-new.md) команда создает проект библиотеки классов, ориентированном на .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="fa727-155">If you are using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets the .NET Standard 2.0.</span></span>

```csharp
dotnet new classlib
```
```vb
dotnet new classlib -lang vb
```
  
## <a name="see-also"></a><span data-ttu-id="fa727-156">См. также</span><span class="sxs-lookup"><span data-stu-id="fa727-156">See Also</span></span>
<span data-ttu-id="fa727-157">[.NET standard](../net-standard.md)
[введение .NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)</span><span class="sxs-lookup"><span data-stu-id="fa727-157">[.NET Standard](../net-standard.md)
[Introducing .NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)</span></span>
