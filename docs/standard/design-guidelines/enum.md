---
title: "Разработка перечислений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b7e1686dca2b96e339917b6dd4861f0f43d20d66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="enum-design"></a><span data-ttu-id="ae350-102">Разработка перечислений</span><span class="sxs-lookup"><span data-stu-id="ae350-102">Enum Design</span></span>
<span data-ttu-id="ae350-103">Перечислимые типы — это особая разновидность типа значения.</span><span class="sxs-lookup"><span data-stu-id="ae350-103">Enums are a special kind of value type.</span></span> <span data-ttu-id="ae350-104">Существует два типа перечислений: простые перечисления и флага перечисления.</span><span class="sxs-lookup"><span data-stu-id="ae350-104">There are two kinds of enums: simple enums and flag enums.</span></span>  
  
 <span data-ttu-id="ae350-105">Простые перечисления представляют небольшие наборы закрытых вариантов.</span><span class="sxs-lookup"><span data-stu-id="ae350-105">Simple enums represent small closed sets of choices.</span></span> <span data-ttu-id="ae350-106">Распространенным примером простое перечисление — это набор цветов.</span><span class="sxs-lookup"><span data-stu-id="ae350-106">A common example of the simple enum is a set of colors.</span></span>  
  
 <span data-ttu-id="ae350-107">Флаг перечисления предназначены для поддержки побитовых операций над значения перечисления.</span><span class="sxs-lookup"><span data-stu-id="ae350-107">Flag enums are designed to support bitwise operations on the enum values.</span></span> <span data-ttu-id="ae350-108">Распространенным примером перечисление флагов приведен список параметров.</span><span class="sxs-lookup"><span data-stu-id="ae350-108">A common example of the flags enum is a list of options.</span></span>  
  
 <span data-ttu-id="ae350-109">**✓ СДЕЛАТЬ** использовать enum для строго типизированных параметров, свойств и возвращаемых значений, которые представляют собой наборы значений.</span><span class="sxs-lookup"><span data-stu-id="ae350-109">**✓ DO** use an enum to strongly type parameters, properties, and return values that represent sets of values.</span></span>  
  
 <span data-ttu-id="ae350-110">**✓ СДЕЛАТЬ** предпочтительнее использовать вместо статических констант перечисления.</span><span class="sxs-lookup"><span data-stu-id="ae350-110">**✓ DO** favor using an enum instead of static constants.</span></span>  
  
 <span data-ttu-id="ae350-111">**X не** использовать enum для открытых наборов (например, версия операционной системы, имена друзьями, и т. д.).</span><span class="sxs-lookup"><span data-stu-id="ae350-111">**X DO NOT** use an enum for open sets (such as the operating system version, names of your friends, etc.).</span></span>  
  
 <span data-ttu-id="ae350-112">**X не** предоставляют значения зарезервированных перечисления, которые предназначены для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="ae350-112">**X DO NOT** provide reserved enum values that are intended for future use.</span></span>  
  
 <span data-ttu-id="ae350-113">Можно всегда просто добавить значения с существующие перечислением в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="ae350-113">You can always simply add values to the existing enum at a later stage.</span></span> <span data-ttu-id="ae350-114">В разделе [добавления значения к перечислениям](#add_value) Дополнительные сведения о добавлении значения в перечислениях.</span><span class="sxs-lookup"><span data-stu-id="ae350-114">See [Adding Values to Enums](#add_value) for more details on adding values to enums.</span></span> <span data-ttu-id="ae350-115">Зарезервированные значения просто засоряет ряд real значений и, как правило, привести к ошибкам пользователей.</span><span class="sxs-lookup"><span data-stu-id="ae350-115">Reserved values just pollute the set of real values and tend to lead to user errors.</span></span>  
  
 <span data-ttu-id="ae350-116">**X ИЗБЕГАЙТЕ** открытым доступом перечислений с только одним значением.</span><span class="sxs-lookup"><span data-stu-id="ae350-116">**X AVOID** publicly exposing enums with only one value.</span></span>  
  
 <span data-ttu-id="ae350-117">Распространенной практикой для обеспечения будущего расширения интерфейсов API C — Добавление зарезервированного параметров в сигнатуры методов.</span><span class="sxs-lookup"><span data-stu-id="ae350-117">A common practice for ensuring future extensibility of C APIs is to add reserved parameters to method signatures.</span></span> <span data-ttu-id="ae350-118">Зарезервированные параметры такого рода может быть выражен как перечисления значение по умолчанию один.</span><span class="sxs-lookup"><span data-stu-id="ae350-118">Such reserved parameters can be expressed as enums with a single default value.</span></span> <span data-ttu-id="ae350-119">Это не должна выполняться в управляемых интерфейсов API.</span><span class="sxs-lookup"><span data-stu-id="ae350-119">This should not be done in managed APIs.</span></span> <span data-ttu-id="ae350-120">Перегрузка метода позволяет добавление параметров в будущих выпусках.</span><span class="sxs-lookup"><span data-stu-id="ae350-120">Method overloading allows adding parameters in future releases.</span></span>  
  
 <span data-ttu-id="ae350-121">**X не** включать значения sentinel в перечислениях.</span><span class="sxs-lookup"><span data-stu-id="ae350-121">**X DO NOT** include sentinel values in enums.</span></span>  
  
 <span data-ttu-id="ae350-122">Несмотря на то, что иногда они полезны для разработчиков framework, значения sentinel понятны пользователям платформы.</span><span class="sxs-lookup"><span data-stu-id="ae350-122">Although they are sometimes helpful to framework developers, sentinel values are confusing to users of the framework.</span></span> <span data-ttu-id="ae350-123">Они используются для отслеживания состояния перечисления, а не выполняется одно из значений из набора, представленный перечисления.</span><span class="sxs-lookup"><span data-stu-id="ae350-123">They are used to track the state of the enum rather than being one of the values from the set represented by the enum.</span></span>  
  
 <span data-ttu-id="ae350-124">**✓ СДЕЛАТЬ** укажите значение 0 в простые перечисления.</span><span class="sxs-lookup"><span data-stu-id="ae350-124">**✓ DO** provide a value of zero on simple enums.</span></span>  
  
 <span data-ttu-id="ae350-125">Рассмотрите возможность вызова значение нечто похожее на «None».</span><span class="sxs-lookup"><span data-stu-id="ae350-125">Consider calling the value something like "None."</span></span> <span data-ttu-id="ae350-126">Если такое значение не подходит для данного конкретного перечисления, наиболее распространенные по умолчанию для перечисления должно быть назначено значение базовое значение равно нулю.</span><span class="sxs-lookup"><span data-stu-id="ae350-126">If such a value is not appropriate for this particular enum, the most common default value for the enum should be assigned the underlying value of zero.</span></span>  
  
 <span data-ttu-id="ae350-127">**✓ Попробуйте** с помощью <xref:System.Int32> (по умолчанию в большинстве языков программирования) как базовый тип перечисления, если верно любое из следующих:</span><span class="sxs-lookup"><span data-stu-id="ae350-127">**✓ CONSIDER** using <xref:System.Int32> (the default in most programming languages) as the underlying type of an enum unless any of the following is true:</span></span>  
  
-   <span data-ttu-id="ae350-128">Перечисление является перечисление флагов и иметь более 32 флагов, или планируется в будущем.</span><span class="sxs-lookup"><span data-stu-id="ae350-128">The enum is a flags enum and you have more than 32 flags, or expect to have more in the future.</span></span>  
  
-   <span data-ttu-id="ae350-129">Базовый тип должен отличаться от <xref:System.Int32> для более простого взаимодействия с неуправляемым кодом, ожидается перечислений другого размера.</span><span class="sxs-lookup"><span data-stu-id="ae350-129">The underlying type needs to be different than <xref:System.Int32> for easier interoperability with unmanaged code expecting different-size enums.</span></span>  
  
-   <span data-ttu-id="ae350-130">Базовый тип меньшего размера приведет к значительной экономии пространства.</span><span class="sxs-lookup"><span data-stu-id="ae350-130">A smaller underlying type would result in substantial savings in space.</span></span> <span data-ttu-id="ae350-131">Если ожидается, что перечисление используется главным образом в качестве аргумента для потока управления, размер имеет небольшое значение.</span><span class="sxs-lookup"><span data-stu-id="ae350-131">If you expect the enum to be used mainly as an argument for flow of control, the size makes little difference.</span></span> <span data-ttu-id="ae350-132">Размер экономии может привести к значительной если:</span><span class="sxs-lookup"><span data-stu-id="ae350-132">The size savings might be significant if:</span></span>  
  
    -   <span data-ttu-id="ae350-133">Предполагается, что перечисление для использования в качестве поля в очень часто экземпляра структуры или класса.</span><span class="sxs-lookup"><span data-stu-id="ae350-133">You expect the enum to be used as a field in a very frequently instantiated structure or class.</span></span>  
  
    -   <span data-ttu-id="ae350-134">Предполагается, что пользователи не могли создавать большие массивы или коллекции экземпляров перечислений.</span><span class="sxs-lookup"><span data-stu-id="ae350-134">You expect users to create large arrays or collections of the enum instances.</span></span>  
  
    -   <span data-ttu-id="ae350-135">Предполагается, что большое число экземпляров перечисления должно быть сериализовано.</span><span class="sxs-lookup"><span data-stu-id="ae350-135">You expect a large number of instances of the enum to be serialized.</span></span>  
  
 <span data-ttu-id="ae350-136">Для использования в памяти, имейте в виду, что управляемые объекты всегда являются `DWORD`-выровнены, поэтому фактически требуется несколько перечислений или другие небольшие структуры в экземпляре для пакета на более мелкие перечисление с Чтобы провести различие, поскольку размер общего экземпляра всегда будет округляться до `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="ae350-136">For in-memory usage, be aware that managed objects are always `DWORD`-aligned, so you effectively need multiple enums or other small structures in an instance to pack a smaller enum with in order to make a difference, because the total instance size is always going to be rounded up to a `DWORD`.</span></span>  
  
 <span data-ttu-id="ae350-137">**✓ СДЕЛАТЬ** имя флага перечисления с множественного числа существительных и субстантивных словосочетаний и простые перечисления атрибутом существительные в единственном числе или субстантивные словосочетания.</span><span class="sxs-lookup"><span data-stu-id="ae350-137">**✓ DO** name flag enums with plural nouns or noun phrases and simple enums with singular nouns or noun phrases.</span></span>  
  
 <span data-ttu-id="ae350-138">**X не** расширить <xref:System.Enum?displayProperty=nameWithType> напрямую.</span><span class="sxs-lookup"><span data-stu-id="ae350-138">**X DO NOT** extend <xref:System.Enum?displayProperty=nameWithType> directly.</span></span>  
  
 <span data-ttu-id="ae350-139"><xref:System.Enum?displayProperty=nameWithType>Это специальный тип используется средой CLR для создания перечислений, определяемой пользователем.</span><span class="sxs-lookup"><span data-stu-id="ae350-139"><xref:System.Enum?displayProperty=nameWithType> is a special type used by the CLR to create user-defined enumerations.</span></span> <span data-ttu-id="ae350-140">Большинство языков программирования предоставляют программный элемент, который предоставляет доступ к этой функции.</span><span class="sxs-lookup"><span data-stu-id="ae350-140">Most programming languages provide a programming element that gives you access to this functionality.</span></span> <span data-ttu-id="ae350-141">Например, в C# `enum` определить перечисление используется ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="ae350-141">For example, in C# the `enum` keyword is used to define an enumeration.</span></span>  
  
<a name="design"></a>   
### <a name="designing-flag-enums"></a><span data-ttu-id="ae350-142">Разработка перечислений флагов</span><span class="sxs-lookup"><span data-stu-id="ae350-142">Designing Flag Enums</span></span>  
 <span data-ttu-id="ae350-143">**СДЕЛАТЬ ✓** применить <xref:System.FlagsAttribute?displayProperty=nameWithType> для перечислений флагов.</span><span class="sxs-lookup"><span data-stu-id="ae350-143">**✓ DO** apply the <xref:System.FlagsAttribute?displayProperty=nameWithType> to flag enums.</span></span> <span data-ttu-id="ae350-144">Этот атрибут не применяется для простых перечислениях.</span><span class="sxs-lookup"><span data-stu-id="ae350-144">Do not apply this attribute to simple enums.</span></span>  
  
 <span data-ttu-id="ae350-145">**✓ СДЕЛАТЬ** используют степень числа 2 для значений перечисления флагов, поэтому они могут быть свободно объединены с помощью битовой операции или.</span><span class="sxs-lookup"><span data-stu-id="ae350-145">**✓ DO** use powers of two for the flag enum values so they can be freely combined using the bitwise OR operation.</span></span>  
  
 <span data-ttu-id="ae350-146">**✓ Попробуйте** предоставляет специальные перечислимых значений для часто используется сочетание флагов.</span><span class="sxs-lookup"><span data-stu-id="ae350-146">**✓ CONSIDER** providing special enum values for commonly used combinations of flags.</span></span>  
  
 <span data-ttu-id="ae350-147">Побитовые операции сложной и не должно быть обязательным для простых задач.</span><span class="sxs-lookup"><span data-stu-id="ae350-147">Bitwise operations are an advanced concept and should not be required for simple tasks.</span></span> <span data-ttu-id="ae350-148"><xref:System.IO.FileAccess.ReadWrite>Примером может служить специальное значение.</span><span class="sxs-lookup"><span data-stu-id="ae350-148"><xref:System.IO.FileAccess.ReadWrite> is an example of such a special value.</span></span>  
  
 <span data-ttu-id="ae350-149">**X ИЗБЕГАЙТЕ** Создание перечисления флага, где определенные комбинации значений являются недопустимыми.</span><span class="sxs-lookup"><span data-stu-id="ae350-149">**X AVOID** creating flag enums where certain combinations of values are invalid.</span></span>  
  
 <span data-ttu-id="ae350-150">**X ИЗБЕГАЙТЕ** с помощью флага нулевые значения перечисления, если значение представляет «все флаги сняты» и соответствующим образом, как предписано следующем правиле с именем.</span><span class="sxs-lookup"><span data-stu-id="ae350-150">**X AVOID** using flag enum values of zero unless the value represents "all flags are cleared" and is named appropriately, as prescribed by the next guideline.</span></span>  
  
 <span data-ttu-id="ae350-151">**СДЕЛАТЬ ✓** имя нулевое значение флага перечисления `None`.</span><span class="sxs-lookup"><span data-stu-id="ae350-151">**✓ DO** name the zero value of flag enums `None`.</span></span> <span data-ttu-id="ae350-152">Для перечисления флага значение всегда должно означать «все флаги сняты».</span><span class="sxs-lookup"><span data-stu-id="ae350-152">For a flag enum, the value must always mean "all flags are cleared."</span></span>  
  
<a name="add_value"></a>   
### <a name="adding-value-to-enums"></a><span data-ttu-id="ae350-153">Добавив значение перечисления</span><span class="sxs-lookup"><span data-stu-id="ae350-153">Adding Value to Enums</span></span>  
 <span data-ttu-id="ae350-154">Это очень часто, чтобы обнаружить, что необходимо добавить значения перечисления, после его уже были доставлены.</span><span class="sxs-lookup"><span data-stu-id="ae350-154">It is very common to discover that you need to add values to an enum after you have already shipped it.</span></span> <span data-ttu-id="ae350-155">Нет потенциальных проблем совместимости приложений при созданное значение возвращается с существующие интерфейсы API, поскольку плохо написанных приложений может неправильно обрабатывает новое значение.</span><span class="sxs-lookup"><span data-stu-id="ae350-155">There is a potential application compatibility problem when the newly added value is returned from an existing API, because poorly written applications might not handle the new value correctly.</span></span>  
  
 <span data-ttu-id="ae350-156">**✓ Попробуйте** Добавление значения перечислений, несмотря на риск совместимость небольших.</span><span class="sxs-lookup"><span data-stu-id="ae350-156">**✓ CONSIDER** adding values to enums, despite a small compatibility risk.</span></span>  
  
 <span data-ttu-id="ae350-157">При наличии реальные данные о совместимости приложений, вызванных дополнения для перечисления, рассмотрите возможность добавления новых API, который возвращает старое и новое значения и устаревание старый API, который следует продолжить возврат только старые значения.</span><span class="sxs-lookup"><span data-stu-id="ae350-157">If you have real data about application incompatibilities caused by additions to an enum, consider adding a new API that returns the new and old values, and deprecate the old API, which should continue returning just the old values.</span></span> <span data-ttu-id="ae350-158">Это позволит гарантировать, что существующие приложения оставаться совместимым.</span><span class="sxs-lookup"><span data-stu-id="ae350-158">This will ensure that your existing applications remain compatible.</span></span>  
  
 <span data-ttu-id="ae350-159">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="ae350-159">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ae350-160">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="ae350-160">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae350-161">См. также</span><span class="sxs-lookup"><span data-stu-id="ae350-161">See Also</span></span>  
 [<span data-ttu-id="ae350-162">Рекомендации по проектированию типа</span><span class="sxs-lookup"><span data-stu-id="ae350-162">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="ae350-163">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="ae350-163">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
