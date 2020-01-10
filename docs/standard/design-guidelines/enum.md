---
title: Разработка перечислений
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
ms.openlocfilehash: 130e9b4e7f8d7076d1dc3f21f51dc07a68799bbe
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709456"
---
# <a name="enum-design"></a><span data-ttu-id="f4921-102">Разработка перечислений</span><span class="sxs-lookup"><span data-stu-id="f4921-102">Enum Design</span></span>

<span data-ttu-id="f4921-103">Перечисления являются особым видом типа значения.</span><span class="sxs-lookup"><span data-stu-id="f4921-103">Enums are a special kind of value type.</span></span> <span data-ttu-id="f4921-104">Существует два вида перечислений: Простые перечисления и Флаговые перечисления.</span><span class="sxs-lookup"><span data-stu-id="f4921-104">There are two kinds of enums: simple enums and flag enums.</span></span>

<span data-ttu-id="f4921-105">Простые перечисления представляют небольшие закрытые наборы вариантов выбора.</span><span class="sxs-lookup"><span data-stu-id="f4921-105">Simple enums represent small closed sets of choices.</span></span> <span data-ttu-id="f4921-106">Распространенным примером простого перечисления является набор цветов.</span><span class="sxs-lookup"><span data-stu-id="f4921-106">A common example of the simple enum is a set of colors.</span></span>

<span data-ttu-id="f4921-107">Перечисление флагов предназначено для поддержки побитовых операций над значениями перечисления.</span><span class="sxs-lookup"><span data-stu-id="f4921-107">Flag enums are designed to support bitwise operations on the enum values.</span></span> <span data-ttu-id="f4921-108">Распространенным примером перечисления Flags является список параметров.</span><span class="sxs-lookup"><span data-stu-id="f4921-108">A common example of the flags enum is a list of options.</span></span>

<span data-ttu-id="f4921-109">**✓ DO** использовать enum для строго типизированных параметров, свойств и возвращаемых значений, которые представляют собой наборы значений.</span><span class="sxs-lookup"><span data-stu-id="f4921-109">**✓ DO** use an enum to strongly type parameters, properties, and return values that represent sets of values.</span></span>

<span data-ttu-id="f4921-110">**✓ DO** предпочтительнее использовать вместо статических констант перечисления.</span><span class="sxs-lookup"><span data-stu-id="f4921-110">**✓ DO** favor using an enum instead of static constants.</span></span>

<span data-ttu-id="f4921-111">**X DO NOT** использовать enum для открытых наборов (например, версия операционной системы, имена друзьями, и т. д.).</span><span class="sxs-lookup"><span data-stu-id="f4921-111">**X DO NOT** use an enum for open sets (such as the operating system version, names of your friends, etc.).</span></span>

<span data-ttu-id="f4921-112">**X DO NOT** предоставляют значения зарезервированных перечисления, которые предназначены для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="f4921-112">**X DO NOT** provide reserved enum values that are intended for future use.</span></span>

<span data-ttu-id="f4921-113">Вы всегда можете просто добавить значения к существующему перечислению на более позднем этапе.</span><span class="sxs-lookup"><span data-stu-id="f4921-113">You can always simply add values to the existing enum at a later stage.</span></span> <span data-ttu-id="f4921-114">Дополнительные сведения о добавлении значений в перечисления см. в разделе [Добавление значений в перечисления](#add_value) .</span><span class="sxs-lookup"><span data-stu-id="f4921-114">See [Adding Values to Enums](#add_value) for more details on adding values to enums.</span></span> <span data-ttu-id="f4921-115">Зарезервированные значения просто засоряла набор реальных значений и обычно ведут к ошибкам пользователя.</span><span class="sxs-lookup"><span data-stu-id="f4921-115">Reserved values just pollute the set of real values and tend to lead to user errors.</span></span>

<span data-ttu-id="f4921-116">**X AVOID** открытым доступом перечислений с только одним значением.</span><span class="sxs-lookup"><span data-stu-id="f4921-116">**X AVOID** publicly exposing enums with only one value.</span></span>

<span data-ttu-id="f4921-117">Распространенной практикой для обеспечения будущего расширяемости C API является добавление зарезервированных параметров в сигнатуры методов.</span><span class="sxs-lookup"><span data-stu-id="f4921-117">A common practice for ensuring future extensibility of C APIs is to add reserved parameters to method signatures.</span></span> <span data-ttu-id="f4921-118">Такие зарезервированные параметры могут быть выражены как перечисления с одним значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f4921-118">Such reserved parameters can be expressed as enums with a single default value.</span></span> <span data-ttu-id="f4921-119">Это не следует делать в управляемых API.</span><span class="sxs-lookup"><span data-stu-id="f4921-119">This should not be done in managed APIs.</span></span> <span data-ttu-id="f4921-120">Перегрузка метода позволяет добавлять параметры в будущих выпусках.</span><span class="sxs-lookup"><span data-stu-id="f4921-120">Method overloading allows adding parameters in future releases.</span></span>

<span data-ttu-id="f4921-121">**X DO NOT** включать значения sentinel в перечислениях.</span><span class="sxs-lookup"><span data-stu-id="f4921-121">**X DO NOT** include sentinel values in enums.</span></span>

<span data-ttu-id="f4921-122">Хотя иногда они полезны разработчикам платформ, значения меток могут сбить с толку пользователей платформы.</span><span class="sxs-lookup"><span data-stu-id="f4921-122">Although they are sometimes helpful to framework developers, sentinel values are confusing to users of the framework.</span></span> <span data-ttu-id="f4921-123">Они используются для отслеживания состояния перечисления, а не одного из значений набора, представленного перечислением.</span><span class="sxs-lookup"><span data-stu-id="f4921-123">They are used to track the state of the enum rather than being one of the values from the set represented by the enum.</span></span>

<span data-ttu-id="f4921-124">**✓ DO** укажите значение 0 в простые перечисления.</span><span class="sxs-lookup"><span data-stu-id="f4921-124">**✓ DO** provide a value of zero on simple enums.</span></span>

<span data-ttu-id="f4921-125">Попробуйте вызвать значение, например "нет".</span><span class="sxs-lookup"><span data-stu-id="f4921-125">Consider calling the value something like "None."</span></span> <span data-ttu-id="f4921-126">Если такое значение не подходит для этого конкретного перечисления, то наиболее распространенному значению перечисления по умолчанию должно быть присвоено базовое значение, равное нулю.</span><span class="sxs-lookup"><span data-stu-id="f4921-126">If such a value is not appropriate for this particular enum, the most common default value for the enum should be assigned the underlying value of zero.</span></span>

<span data-ttu-id="f4921-127">**✓ CONSIDER** с помощью <xref:System.Int32> (по умолчанию в большинстве языков программирования) как базовый тип перечисления, если верно любое из следующих:</span><span class="sxs-lookup"><span data-stu-id="f4921-127">**✓ CONSIDER** using <xref:System.Int32> (the default in most programming languages) as the underlying type of an enum unless any of the following is true:</span></span>

- <span data-ttu-id="f4921-128">Перечисление является перечислением Flags и имеет более 32 флагов или может быть больше в будущем.</span><span class="sxs-lookup"><span data-stu-id="f4921-128">The enum is a flags enum and you have more than 32 flags, or expect to have more in the future.</span></span>

- <span data-ttu-id="f4921-129">Базовый тип должен отличаться от <xref:System.Int32> для упрощения взаимодействия с неуправляемым кодом, ожидающим перечисления разного размера.</span><span class="sxs-lookup"><span data-stu-id="f4921-129">The underlying type needs to be different than <xref:System.Int32> for easier interoperability with unmanaged code expecting different-size enums.</span></span>

- <span data-ttu-id="f4921-130">Базовый тип меньшего размера приведет к значительному экономии пространства.</span><span class="sxs-lookup"><span data-stu-id="f4921-130">A smaller underlying type would result in substantial savings in space.</span></span> <span data-ttu-id="f4921-131">Если предполагается, что перечисление будет использоваться в основном как аргумент для потока управления, размер делает незначительную разницу.</span><span class="sxs-lookup"><span data-stu-id="f4921-131">If you expect the enum to be used mainly as an argument for flow of control, the size makes little difference.</span></span> <span data-ttu-id="f4921-132">Экономия размера может быть значительной, если:</span><span class="sxs-lookup"><span data-stu-id="f4921-132">The size savings might be significant if:</span></span>

  - <span data-ttu-id="f4921-133">Предполагается, что перечисление будет использоваться в качестве поля в очень часто создаваемой структуре или классе.</span><span class="sxs-lookup"><span data-stu-id="f4921-133">You expect the enum to be used as a field in a very frequently instantiated structure or class.</span></span>

  - <span data-ttu-id="f4921-134">Предполагается, что пользователи будут создавать большие массивы или коллекции экземпляров перечисления.</span><span class="sxs-lookup"><span data-stu-id="f4921-134">You expect users to create large arrays or collections of the enum instances.</span></span>

  - <span data-ttu-id="f4921-135">Предполагается, что будет сериализовано большое количество экземпляров перечисления.</span><span class="sxs-lookup"><span data-stu-id="f4921-135">You expect a large number of instances of the enum to be serialized.</span></span>

<span data-ttu-id="f4921-136">При использовании в памяти следует помнить, что управляемые объекты всегда `DWORD`ются по-разному, поэтому в экземпляре необходимо использовать несколько перечислений или другие небольшие структуры для упаковки меньшего перечислимого типа с целью создания разницы, так как общий размер экземпляра всегда будет округляться до `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="f4921-136">For in-memory usage, be aware that managed objects are always `DWORD`-aligned, so you effectively need multiple enums or other small structures in an instance to pack a smaller enum with in order to make a difference, because the total instance size is always going to be rounded up to a `DWORD`.</span></span>

<span data-ttu-id="f4921-137">**✓ DO** имя флага перечисления с множественного числа существительных и субстантивных словосочетаний и простые перечисления атрибутом существительные в единственном числе или субстантивные словосочетания.</span><span class="sxs-lookup"><span data-stu-id="f4921-137">**✓ DO** name flag enums with plural nouns or noun phrases and simple enums with singular nouns or noun phrases.</span></span>

<span data-ttu-id="f4921-138">**X DO NOT** расширить <xref:System.Enum?displayProperty=nameWithType> напрямую.</span><span class="sxs-lookup"><span data-stu-id="f4921-138">**X DO NOT** extend <xref:System.Enum?displayProperty=nameWithType> directly.</span></span>

<span data-ttu-id="f4921-139"><xref:System.Enum?displayProperty=nameWithType> — это специальный тип, используемый средой CLR для создания определяемых пользователем перечислений.</span><span class="sxs-lookup"><span data-stu-id="f4921-139"><xref:System.Enum?displayProperty=nameWithType> is a special type used by the CLR to create user-defined enumerations.</span></span> <span data-ttu-id="f4921-140">Большинство языков программирования предоставляют программный элемент, обеспечивающий доступ к этой функции.</span><span class="sxs-lookup"><span data-stu-id="f4921-140">Most programming languages provide a programming element that gives you access to this functionality.</span></span> <span data-ttu-id="f4921-141">Например, в C# ключевом слове `enum` используется для определения перечисления.</span><span class="sxs-lookup"><span data-stu-id="f4921-141">For example, in C# the `enum` keyword is used to define an enumeration.</span></span>

<a name="design"></a>

### <a name="designing-flag-enums"></a><span data-ttu-id="f4921-142">Разработка перечислений флагов</span><span class="sxs-lookup"><span data-stu-id="f4921-142">Designing Flag Enums</span></span>

<span data-ttu-id="f4921-143">**✓ DO** применить <xref:System.FlagsAttribute?displayProperty=nameWithType> для перечислений флагов.</span><span class="sxs-lookup"><span data-stu-id="f4921-143">**✓ DO** apply the <xref:System.FlagsAttribute?displayProperty=nameWithType> to flag enums.</span></span> <span data-ttu-id="f4921-144">Не применяйте этот атрибут к простым перечислениям.</span><span class="sxs-lookup"><span data-stu-id="f4921-144">Do not apply this attribute to simple enums.</span></span>

<span data-ttu-id="f4921-145">**✓ DO** используют степень числа 2 для значений перечисления флагов, поэтому они могут быть свободно объединены с помощью битовой операции или.</span><span class="sxs-lookup"><span data-stu-id="f4921-145">**✓ DO** use powers of two for the flag enum values so they can be freely combined using the bitwise OR operation.</span></span>

<span data-ttu-id="f4921-146">**✓ CONSIDER** предоставляет специальные перечислимых значений для часто используется сочетание флагов.</span><span class="sxs-lookup"><span data-stu-id="f4921-146">**✓ CONSIDER** providing special enum values for commonly used combinations of flags.</span></span>

<span data-ttu-id="f4921-147">Битовые операции являются сложной концепцией и не должны требоваться для простых задач.</span><span class="sxs-lookup"><span data-stu-id="f4921-147">Bitwise operations are an advanced concept and should not be required for simple tasks.</span></span> <span data-ttu-id="f4921-148"><xref:System.IO.FileAccess.ReadWrite> является примером такого специального значения.</span><span class="sxs-lookup"><span data-stu-id="f4921-148"><xref:System.IO.FileAccess.ReadWrite> is an example of such a special value.</span></span>

<span data-ttu-id="f4921-149">**X AVOID** Создание перечисления флага, где определенные комбинации значений являются недопустимыми.</span><span class="sxs-lookup"><span data-stu-id="f4921-149">**X AVOID** creating flag enums where certain combinations of values are invalid.</span></span>

<span data-ttu-id="f4921-150">**X AVOID** с помощью флага нулевые значения перечисления, если значение представляет «все флаги сняты» и соответствующим образом, как предписано следующем правиле с именем.</span><span class="sxs-lookup"><span data-stu-id="f4921-150">**X AVOID** using flag enum values of zero unless the value represents "all flags are cleared" and is named appropriately, as prescribed by the next guideline.</span></span>

<span data-ttu-id="f4921-151">**✓ DO** имя нулевое значение флага перечисления `None`.</span><span class="sxs-lookup"><span data-stu-id="f4921-151">**✓ DO** name the zero value of flag enums `None`.</span></span> <span data-ttu-id="f4921-152">Для перечислимого типа значение всегда должно означать «все флаги сняты».</span><span class="sxs-lookup"><span data-stu-id="f4921-152">For a flag enum, the value must always mean "all flags are cleared."</span></span>

<a name="add_value"></a>

### <a name="adding-value-to-enums"></a><span data-ttu-id="f4921-153">Добавление значения в перечисления</span><span class="sxs-lookup"><span data-stu-id="f4921-153">Adding Value to Enums</span></span>

<span data-ttu-id="f4921-154">Очень часто обнаруживается, что необходимо добавить значения в перечисление после того, как вы уже отгрузили их.</span><span class="sxs-lookup"><span data-stu-id="f4921-154">It is very common to discover that you need to add values to an enum after you have already shipped it.</span></span> <span data-ttu-id="f4921-155">Существует потенциальная проблема совместимости приложений, когда вновь добавленное значение возвращается из существующего API, так как плохо написанные приложения могут неправильно работать с новым значением.</span><span class="sxs-lookup"><span data-stu-id="f4921-155">There is a potential application compatibility problem when the newly added value is returned from an existing API, because poorly written applications might not handle the new value correctly.</span></span>

<span data-ttu-id="f4921-156">**✓ CONSIDER** Добавление значения перечислений, несмотря на риск совместимость небольших.</span><span class="sxs-lookup"><span data-stu-id="f4921-156">**✓ CONSIDER** adding values to enums, despite a small compatibility risk.</span></span>

<span data-ttu-id="f4921-157">Если у вас есть реальные данные о несовместимости приложений, вызванные дополнениями к перечислению, рассмотрите возможность добавления нового API, возвращающего новые и устаревшие значения, и прекращения использования старого API, который должен возвращать только старые значения.</span><span class="sxs-lookup"><span data-stu-id="f4921-157">If you have real data about application incompatibilities caused by additions to an enum, consider adding a new API that returns the new and old values, and deprecate the old API, which should continue returning just the old values.</span></span> <span data-ttu-id="f4921-158">Это обеспечит совместимость существующих приложений.</span><span class="sxs-lookup"><span data-stu-id="f4921-158">This will ensure that your existing applications remain compatible.</span></span>

<span data-ttu-id="f4921-159">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="f4921-159">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="f4921-160">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="f4921-160">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="f4921-161">См. также:</span><span class="sxs-lookup"><span data-stu-id="f4921-161">See also</span></span>

- [<span data-ttu-id="f4921-162">Рекомендации по разработке типов</span><span class="sxs-lookup"><span data-stu-id="f4921-162">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="f4921-163">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="f4921-163">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
