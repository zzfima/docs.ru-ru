---
title: Тип данных Date
ms.date: 07/20/2015
f1_keywords:
- vb.Date
helpviewer_keywords:
- Date data type
- dates [Visual Basic], Visual Basic data types
- times [Visual Basic], Date data type
- Date literals [Visual Basic]
- data values [Visual Basic]
- times [Visual Basic], Visual Basic data types
- dates [Visual Basic], Date data type
- data types [Visual Basic], assigning
- literals [Visual Basic], Date
- '# specifier for Date literals'
ms.assetid: d9edf5b0-e85e-438b-a1cf-1f321e7c831b
ms.openlocfilehash: 972df72874753a0f1213f3a4942468c59e3913ce
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344024"
---
# <a name="date-data-type-visual-basic"></a><span data-ttu-id="63b19-102">Тип данных Date (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63b19-102">Date Data Type (Visual Basic)</span></span>

<span data-ttu-id="63b19-103">Содержит 64-разрядные (8-байтные) значения IEEE, представляющие даты в диапазоне от 1 января 0001 года до 31 декабря 9999 года и время от 00:00:00 (полночь) до 23:59:9999999.</span><span class="sxs-lookup"><span data-stu-id="63b19-103">Holds IEEE 64-bit (8-byte) values that represent dates ranging from January 1 of the year 0001 through December 31 of the year 9999, and times from 12:00:00 AM (midnight) through 11:59:59.9999999 PM.</span></span> <span data-ttu-id="63b19-104">Каждое приращение представляет 100 наносекунд затраченного времени с начала 1 января 1 года по григорианскому календарю.</span><span class="sxs-lookup"><span data-stu-id="63b19-104">Each increment represents 100 nanoseconds of elapsed time since the beginning of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="63b19-105">Максимальное значение представляет 100 наносекунд перед началом 1 января 10 000 года.</span><span class="sxs-lookup"><span data-stu-id="63b19-105">The maximum value represents 100 nanoseconds before the beginning of January 1 of the year 10000.</span></span>

## <a name="remarks"></a><span data-ttu-id="63b19-106">Заметки</span><span class="sxs-lookup"><span data-stu-id="63b19-106">Remarks</span></span>

<span data-ttu-id="63b19-107">Используйте тип данных `Date`, содержащий значения даты, времени или даты и времени.</span><span class="sxs-lookup"><span data-stu-id="63b19-107">Use the `Date` data type to contain date values, time values, or date and time values.</span></span>

<span data-ttu-id="63b19-108">Значение по умолчанию `Date`: 0:00:00 (полночь) 1 января 0001 года.</span><span class="sxs-lookup"><span data-stu-id="63b19-108">The default value of `Date` is 0:00:00 (midnight) on January 1, 0001.</span></span>

<span data-ttu-id="63b19-109">Текущие дату и время можно получить из класса <xref:Microsoft.VisualBasic.DateAndTime>.</span><span class="sxs-lookup"><span data-stu-id="63b19-109">You can get the current date and time from the <xref:Microsoft.VisualBasic.DateAndTime> class.</span></span>

## <a name="format-requirements"></a><span data-ttu-id="63b19-110">Требования к формату</span><span class="sxs-lookup"><span data-stu-id="63b19-110">Format Requirements</span></span>

<span data-ttu-id="63b19-111">Необходимо заключить литерал `Date` в символы решетки (`# #`).</span><span class="sxs-lookup"><span data-stu-id="63b19-111">You must enclose a `Date` literal within number signs (`# #`).</span></span> <span data-ttu-id="63b19-112">Необходимо указать значение даты в формате М/д/гггг, например `#5/31/1993#`, или гггг-ММ-дд, например `#1993-5-31#`.</span><span class="sxs-lookup"><span data-stu-id="63b19-112">You must specify the date value in the format M/d/yyyy, for example `#5/31/1993#`, or yyyy-MM-dd, for example `#1993-5-31#`.</span></span> <span data-ttu-id="63b19-113">При указании года сначала можно использовать символы косой черты.</span><span class="sxs-lookup"><span data-stu-id="63b19-113">You can use slashes when specifying the year first.</span></span>  <span data-ttu-id="63b19-114">Это требование не зависит от языкового стандарта и настроек формата времени и даты компьютера.</span><span class="sxs-lookup"><span data-stu-id="63b19-114">This requirement is independent of your locale and your computer's date and time format settings.</span></span>

<span data-ttu-id="63b19-115">Причина этого ограничения связана с тем, что значение кода никогда не должно изменяться в зависимости от языкового стандарта, который использует приложение.</span><span class="sxs-lookup"><span data-stu-id="63b19-115">The reason for this restriction is that the meaning of your code should never change depending on the locale in which your application is running.</span></span> <span data-ttu-id="63b19-116">Предположим, что литерал `Date` жестко закодирован как `#3/4/1998#`, что это означает 4 марта 1998 года.</span><span class="sxs-lookup"><span data-stu-id="63b19-116">Suppose you hard-code a `Date` literal of `#3/4/1998#` and intend it to mean March 4, 1998.</span></span> <span data-ttu-id="63b19-117">В языковом стандарте, использующем формат дд/мм/гггг, 3/4/1998 компилируется, как предполагается.</span><span class="sxs-lookup"><span data-stu-id="63b19-117">In a locale that uses mm/dd/yyyy, 3/4/1998 compiles as you intend.</span></span> <span data-ttu-id="63b19-118">But suppose you deploy your application in many countries/regions.</span><span class="sxs-lookup"><span data-stu-id="63b19-118">But suppose you deploy your application in many countries/regions.</span></span> <span data-ttu-id="63b19-119">В языковом стандарте, использующем формат мм/дд/гггг, ваш жестко закодированный литерал будет компилироваться как 3 апреля 1998 года.</span><span class="sxs-lookup"><span data-stu-id="63b19-119">In a locale that uses dd/mm/yyyy, your hard-coded literal would compile to April 3, 1998.</span></span> <span data-ttu-id="63b19-120">В языковом стандарте, использующем формат гггг/мм/дд, литерал будет недопустимым (апрель 1998, 0003) и вызовет ошибку компилятора.</span><span class="sxs-lookup"><span data-stu-id="63b19-120">In a locale that uses yyyy/mm/dd, the literal would be invalid (April 1998, 0003) and cause a compiler error.</span></span>

## <a name="workarounds"></a><span data-ttu-id="63b19-121">Методы обхода проблемы</span><span class="sxs-lookup"><span data-stu-id="63b19-121">Workarounds</span></span>

<span data-ttu-id="63b19-122">Для преобразования литерала `Date` в формат языкового стандарта или пользовательский формат, передайте литерал функции <xref:Microsoft.VisualBasic.Strings.Format%2A>, указав стандартный или пользовательский формат даты.</span><span class="sxs-lookup"><span data-stu-id="63b19-122">To convert a `Date` literal to the format of your locale, or to a custom format, supply the literal to the <xref:Microsoft.VisualBasic.Strings.Format%2A> function, specifying either a predefined or user-defined date format.</span></span> <span data-ttu-id="63b19-123">В следующем примере это показано.</span><span class="sxs-lookup"><span data-stu-id="63b19-123">The following example demonstrates this.</span></span>

```vb
MsgBox("The formatted date is " & Format(#5/31/1993#, "dddd, d MMM yyyy"))
```

<span data-ttu-id="63b19-124">Кроме того, для формирования значения даты и времени можно использовать один из перегруженных конструкторов структуры <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="63b19-124">Alternatively, you can use one of the overloaded constructors of the <xref:System.DateTime> structure to assemble a date and time value.</span></span> <span data-ttu-id="63b19-125">В следующем примере создается значение для представления даты и времени 12:14 31 мая, 1993 г.</span><span class="sxs-lookup"><span data-stu-id="63b19-125">The following example creates a value to represent May 31, 1993 at 12:14 in the afternoon.</span></span>

```vb
Dim dateInMay As New System.DateTime(1993, 5, 31, 12, 14, 0)
```

## <a name="hour-format"></a><span data-ttu-id="63b19-126">Часовой формат</span><span class="sxs-lookup"><span data-stu-id="63b19-126">Hour Format</span></span>

<span data-ttu-id="63b19-127">Значение времени можно указать в 12- или 24-часовом формате, например `#1:15:30 PM#` или `#13:15:30#`.</span><span class="sxs-lookup"><span data-stu-id="63b19-127">You can specify the time value in either 12-hour or 24-hour format, for example `#1:15:30 PM#` or `#13:15:30#`.</span></span> <span data-ttu-id="63b19-128">Однако если не указать значение минут или секунд, необходимо указать AM или PM.</span><span class="sxs-lookup"><span data-stu-id="63b19-128">However, if you do not specify either the minutes or the seconds, you must specify AM or PM.</span></span>

## <a name="date-and-time-defaults"></a><span data-ttu-id="63b19-129">Дата и время по умолчанию</span><span class="sxs-lookup"><span data-stu-id="63b19-129">Date and Time Defaults</span></span>

<span data-ttu-id="63b19-130">Если не указать дату в литерале даты и времени, Visual Basic задает часть даты как 1 января 0001 года.</span><span class="sxs-lookup"><span data-stu-id="63b19-130">If you do not include a date in a date/time literal, Visual Basic sets the date part of the value to January 1, 0001.</span></span> <span data-ttu-id="63b19-131">Если в литерал даты и времени не включено время, Visual Basic задает часть значения времени как начало дня, то есть полночь (0:00:00).</span><span class="sxs-lookup"><span data-stu-id="63b19-131">If you do not include a time in a date/time literal, Visual Basic sets the time part of the value to the start of the day, that is, midnight (0:00:00).</span></span>

## <a name="type-conversions"></a><span data-ttu-id="63b19-132">Преобразования типов</span><span class="sxs-lookup"><span data-stu-id="63b19-132">Type Conversions</span></span>

<span data-ttu-id="63b19-133">При преобразовании значения `Date` типа `String` Visual Basic отображает дату в формате короткой даты, определяемом языковым стандартом времени выполнения. Время отображается в формате времени (12- или 24-часовом), определяемом языковым стандартом времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="63b19-133">If you convert a `Date` value to the `String` type, Visual Basic renders the date according to the short date format specified by the run-time locale, and it renders the time according to the time format (either 12-hour or 24-hour) specified by the run-time locale.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="63b19-134">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="63b19-134">Programming Tips</span></span>

- <span data-ttu-id="63b19-135">**Interop Considerations.**</span><span class="sxs-lookup"><span data-stu-id="63b19-135">**Interop Considerations.**</span></span> <span data-ttu-id="63b19-136">При взаимодействие с компонентами, которые не написаны для платформы .NET Framework (например, автоматизация или COM-объекты), необходимо помнить, что в других средах типы даты и времени несовместимы с типом `Date` Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="63b19-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that date/time types in other environments are not compatible with the Visual Basic `Date` type.</span></span> <span data-ttu-id="63b19-137">Если вы передаете аргумент даты и времени такому компоненту, объявите его `Double`, а не как `Date` в новом коде Visual Basic и используйте методы преобразования <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> и <xref:System.DateTime.ToOADate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="63b19-137">If you are passing a date/time argument to such a component, declare it as `Double` instead of `Date` in your new Visual Basic code, and use the conversion methods <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> and <xref:System.DateTime.ToOADate%2A?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="63b19-138">**Type Characters.**</span><span class="sxs-lookup"><span data-stu-id="63b19-138">**Type Characters.**</span></span> <span data-ttu-id="63b19-139">`Date` has no literal type character or identifier type character.</span><span class="sxs-lookup"><span data-stu-id="63b19-139">`Date` has no literal type character or identifier type character.</span></span> <span data-ttu-id="63b19-140">Однако компилятор обрабатывает литералы, заключенные в решетки (`# #`), как `Date`.</span><span class="sxs-lookup"><span data-stu-id="63b19-140">However, the compiler treats literals enclosed within number signs (`# #`) as `Date`.</span></span>

- <span data-ttu-id="63b19-141">**Framework Type.**</span><span class="sxs-lookup"><span data-stu-id="63b19-141">**Framework Type.**</span></span> <span data-ttu-id="63b19-142">В .NET Framework данный тип соответствует структуре <xref:System.DateTime?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="63b19-142">The corresponding type in the .NET Framework is the <xref:System.DateTime?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="63b19-143">Пример</span><span class="sxs-lookup"><span data-stu-id="63b19-143">Example</span></span>

<span data-ttu-id="63b19-144">Переменная или константа типа данных `Date` содержит дату и время.</span><span class="sxs-lookup"><span data-stu-id="63b19-144">A variable or constant of the `Date` data type holds both the date and the time.</span></span> <span data-ttu-id="63b19-145">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="63b19-145">The following example illustrates this.</span></span>

```vb
Dim someDateAndTime As Date = #8/13/2002 12:14 PM#
```

## <a name="see-also"></a><span data-ttu-id="63b19-146">См. также</span><span class="sxs-lookup"><span data-stu-id="63b19-146">See also</span></span>

- <xref:System.DateTime?displayProperty=nameWithType>
- [<span data-ttu-id="63b19-147">Типы данных</span><span class="sxs-lookup"><span data-stu-id="63b19-147">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="63b19-148">Строки стандартных форматов даты и времени</span><span class="sxs-lookup"><span data-stu-id="63b19-148">Standard Date and Time Format Strings</span></span>](../../../standard/base-types/standard-date-and-time-format-strings.md)
- [<span data-ttu-id="63b19-149">Строки настраиваемых форматов даты и времени</span><span class="sxs-lookup"><span data-stu-id="63b19-149">Custom Date and Time Format Strings</span></span>](../../../standard/base-types/custom-date-and-time-format-strings.md)
- [<span data-ttu-id="63b19-150">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="63b19-150">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="63b19-151">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="63b19-151">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="63b19-152">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="63b19-152">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
