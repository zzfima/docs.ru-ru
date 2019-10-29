---
title: Практическое руководство. Сохранение и восстановление значения даты и времени
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- round-trip date and time values
- dates [.NET Framework], round-trip values
- time zones [.NET Framework], round-trip date and time values
- time [.NET Framework], round-trip values
- formatting strings [.NET Framework], round-trip values
ms.assetid: b609b277-edc6-4c74-b03e-ea73324ecbdb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc3393c27d2955528822c193c36a0f6d86f5c148
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2019
ms.locfileid: "67663795"
---
# <a name="how-to-round-trip-date-and-time-values"></a><span data-ttu-id="c44e0-102">Практическое руководство. Сохранение и восстановление значения даты и времени</span><span class="sxs-lookup"><span data-stu-id="c44e0-102">How to: Round-trip Date and Time Values</span></span>

<span data-ttu-id="c44e0-103">Во многих приложениях значение даты и времени предназначено для однозначного определения одного момента времени.</span><span class="sxs-lookup"><span data-stu-id="c44e0-103">In many applications, a date and time value is intended to unambiguously identify a single point in time.</span></span> <span data-ttu-id="c44e0-104">В этой статье показано, как правильно сохранять и восстанавливать значения <xref:System.DateTime> и <xref:System.DateTimeOffset>, а также значения времени с информацией о часовом поясе, чтобы восстановленное значение определяло то же время, что и сохраненное значение.</span><span class="sxs-lookup"><span data-stu-id="c44e0-104">This topic shows how to save and restore a <xref:System.DateTime> value, a <xref:System.DateTimeOffset> value, and a date and time value with time zone information so that the restored value identifies the same time as the saved value.</span></span>

### <a name="to-round-trip-a-datetime-value"></a><span data-ttu-id="c44e0-105">Выполнение цикла обработки значения DateTime</span><span class="sxs-lookup"><span data-stu-id="c44e0-105">To round-trip a DateTime value</span></span>

1. <span data-ttu-id="c44e0-106">Преобразуйте значение <xref:System.DateTime> в строковое представление с помощью метода <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> с описателем формата "o".</span><span class="sxs-lookup"><span data-stu-id="c44e0-106">Convert the <xref:System.DateTime> value to its string representation by calling the <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> method with the "o" format specifier.</span></span>

2. <span data-ttu-id="c44e0-107">Сохраните строковое представление значения <xref:System.DateTime> в файл или передайте его между процессами, доменами приложений или компьютерами.</span><span class="sxs-lookup"><span data-stu-id="c44e0-107">Save the string representation of the <xref:System.DateTime> value to a file, or pass it across a process, application domain, or machine boundary.</span></span>

3. <span data-ttu-id="c44e0-108">Получите строку, представляющую значение <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="c44e0-108">Retrieve the string that represents the <xref:System.DateTime> value.</span></span>

4. <span data-ttu-id="c44e0-109">Вызовите метод <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> и передайте ему значение <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> в параметре `styles`.</span><span class="sxs-lookup"><span data-stu-id="c44e0-109">Call the <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> method, and pass <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> as the value of the `styles` parameter.</span></span>

<span data-ttu-id="c44e0-110">В следующем примере показано, как выполнить цикл обработки значения <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="c44e0-110">The following example illustrates how to round-trip a <xref:System.DateTime> value.</span></span>

[!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
[!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]

<span data-ttu-id="c44e0-111">Этот метод позволяет сохранить любое значение локального или универсального времени в процессе обработки значения <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="c44e0-111">When round-tripping a <xref:System.DateTime> value, this technique successfully preserves the time for all local and universal times.</span></span> <span data-ttu-id="c44e0-112">Например, если локальное значение <xref:System.DateTime> сохранено в системе в тихоокеанском стандартном часовом поясе США и восстановлено в системе в центральном стандартном часовом поясе США, восстановленные дата и время будут на два часа больше исходного времени, что отражает разницу во времени между двумя часовыми поясами.</span><span class="sxs-lookup"><span data-stu-id="c44e0-112">For example, if a local <xref:System.DateTime> value is saved on a system in the U.S. Pacific Standard Time zone and is restored on a system in the U.S. Central Standard Time zone, the restored date and time will be two hours later than the original time, which reflects the time difference between the two time zones.</span></span> <span data-ttu-id="c44e0-113">Однако этот способ не всегда точен для неуказанного времени.</span><span class="sxs-lookup"><span data-stu-id="c44e0-113">However, this technique is not necessarily accurate for unspecified times.</span></span> <span data-ttu-id="c44e0-114">Все значения <xref:System.DateTime>, для которых свойство <xref:System.DateTime.Kind%2A> имеет значение <xref:System.DateTimeKind.Unspecified>, обрабатываются как значения местного времени.</span><span class="sxs-lookup"><span data-stu-id="c44e0-114">All <xref:System.DateTime> values whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Unspecified> are treated as if they are local times.</span></span> <span data-ttu-id="c44e0-115">Если это не так, <xref:System.DateTime> не сможет правильно установить нужный момент времени.</span><span class="sxs-lookup"><span data-stu-id="c44e0-115">If this is not the case, the <xref:System.DateTime> will not successfully identify the correct point in time.</span></span> <span data-ttu-id="c44e0-116">Чтобы устранить это ограничение, нужно тесно связать значение даты и времени с его часовым поясом для операций сохранения и восстановления.</span><span class="sxs-lookup"><span data-stu-id="c44e0-116">The workaround for this limitation is to tightly couple a date and time value with its time zone for the save and restore operation.</span></span>

### <a name="to-round-trip-a-datetimeoffset-value"></a><span data-ttu-id="c44e0-117">Выполнение цикла обработки значения DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="c44e0-117">To round-trip a DateTimeOffset value</span></span>

1. <span data-ttu-id="c44e0-118">Преобразуйте значение <xref:System.DateTimeOffset> в строковое представление с помощью метода <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> с описателем формата "o".</span><span class="sxs-lookup"><span data-stu-id="c44e0-118">Convert the <xref:System.DateTimeOffset> value to its string representation by calling the <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> method with the "o" format specifier.</span></span>

2. <span data-ttu-id="c44e0-119">Сохраните строковое представление значения <xref:System.DateTimeOffset> в файл или передайте его между процессами, доменами приложений или компьютерами.</span><span class="sxs-lookup"><span data-stu-id="c44e0-119">Save the string representation of the <xref:System.DateTimeOffset> value to a file, or pass it across a process, application domain, or machine boundary.</span></span>

3. <span data-ttu-id="c44e0-120">Получите строку, представляющую значение <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="c44e0-120">Retrieve the string that represents the <xref:System.DateTimeOffset> value.</span></span>

4. <span data-ttu-id="c44e0-121">Вызовите метод <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> и передайте ему значение <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> в параметре `styles`.</span><span class="sxs-lookup"><span data-stu-id="c44e0-121">Call the <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> method, and pass <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> as the value of the `styles` parameter.</span></span>

<span data-ttu-id="c44e0-122">В следующем примере показано, как выполнить цикл обработки значения <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="c44e0-122">The following example illustrates how to round-trip a <xref:System.DateTimeOffset> value.</span></span>

[!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
[!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]

<span data-ttu-id="c44e0-123">Этот метод всегда однозначно идентифицирует единственный момент времени по значению <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="c44e0-123">This technique always unambiguously identifies a <xref:System.DateTimeOffset> value as a single point in time.</span></span> <span data-ttu-id="c44e0-124">Полученное значение можно преобразовать в формат UTC с помощью метода <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> или в значение времени в определенным часовом поясе с помощью метода <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> или <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c44e0-124">The value can then be converted to Coordinated Universal Time (UTC) by calling the <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> method, or it can be converted to the time in a particular time zone by calling the <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> or <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c44e0-125">Основное ограничение этого способа — арифметические действия с датами и временем, которые могут дать неточные результаты для значения <xref:System.DateTimeOffset>, представляющего время в определенном часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="c44e0-125">The major limitation of this technique is that date and time arithmetic, when performed on a <xref:System.DateTimeOffset> value that represents the time in a particular time zone, may not produce accurate results for that time zone.</span></span> <span data-ttu-id="c44e0-126">Это происходит потому, что значение <xref:System.DateTimeOffset> при создании "открепляется" от сведений о часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="c44e0-126">This is because when a <xref:System.DateTimeOffset> value is instantiated, it is disassociated from its time zone.</span></span> <span data-ttu-id="c44e0-127">Таким образом, правила коррекции часового пояса не могут быть больше применены при выполнении вычислений с датами и временем.</span><span class="sxs-lookup"><span data-stu-id="c44e0-127">Therefore, that time zone's adjustment rules can no longer be applied when you perform date and time calculations.</span></span> <span data-ttu-id="c44e0-128">Можно обойти эту проблему, определив пользовательский тип, который содержит значение даты и времени с его соответствующим часовым поясом.</span><span class="sxs-lookup"><span data-stu-id="c44e0-128">You can work around this problem by defining a custom type that includes both a date and time value and its accompanying time zone.</span></span>

### <a name="to-round-trip-a-date-and-time-value-with-its-time-zone"></a><span data-ttu-id="c44e0-129">Цикл обработки значения даты и времени с часовым поясом</span><span class="sxs-lookup"><span data-stu-id="c44e0-129">To round-trip a date and time value with its time zone</span></span>

1. <span data-ttu-id="c44e0-130">Определите класс или структуру с двумя полями.</span><span class="sxs-lookup"><span data-stu-id="c44e0-130">Define a class or a structure with two fields.</span></span> <span data-ttu-id="c44e0-131">Первое поле содержит объект <xref:System.DateTime> или <xref:System.DateTimeOffset>, а второе — объект <xref:System.TimeZoneInfo>.</span><span class="sxs-lookup"><span data-stu-id="c44e0-131">The first field is either a <xref:System.DateTime> or a <xref:System.DateTimeOffset> object, and the second is a <xref:System.TimeZoneInfo> object.</span></span> <span data-ttu-id="c44e0-132">Следующий пример демонстрирует простой вариант такого типа.</span><span class="sxs-lookup"><span data-stu-id="c44e0-132">The following example is a simple version of such a type.</span></span>

    [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
    [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]

2. <span data-ttu-id="c44e0-133">Отметьте этот класс атрибутом <xref:System.SerializableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c44e0-133">Mark the class with the <xref:System.SerializableAttribute> attribute.</span></span>

3. <span data-ttu-id="c44e0-134">Сериализуйте объект с помощью метода <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c44e0-134">Serialize the object using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> method.</span></span>

4. <span data-ttu-id="c44e0-135">Восстановите объект с помощью метода <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A>.</span><span class="sxs-lookup"><span data-stu-id="c44e0-135">Restore the object using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> method.</span></span>

5. <span data-ttu-id="c44e0-136">Приведите или преобразуйте десериализованный объект (в C#) в объект нужного типа (в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="c44e0-136">Cast (in C#) or convert (in Visual Basic) the deserialized object to an object of the appropriate type.</span></span>

<span data-ttu-id="c44e0-137">В следующем примере описан цикл обработки объекта, позволяющий сохранить сведения о дате, времени и часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="c44e0-137">The following example illustrates how to round-trip an object that stores both date and time and time zone information.</span></span>

[!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
[!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]

<span data-ttu-id="c44e0-138">Этот метод всегда будет однозначно определять правильный момент времени как до, так и после сохранения и восстановления, если реализация комбинированного объекта для даты, времени и часового пояса не допускает рассинхронизацию значений даты и часового пояса.</span><span class="sxs-lookup"><span data-stu-id="c44e0-138">This technique should always unambiguously reflect the correct point of time both before and after it is saved and restored, provided that the implementation of the combined date and time and time zone object does not allow the date value to become out of sync with the time zone value.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="c44e0-139">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="c44e0-139">Compiling the Code</span></span>

<span data-ttu-id="c44e0-140">Для этих примеров требуются:</span><span class="sxs-lookup"><span data-stu-id="c44e0-140">These examples require:</span></span>

- <span data-ttu-id="c44e0-141">Импорт следующих пространств имен с помощью операторов C# `using` или операторов Visual Basic `Imports`:</span><span class="sxs-lookup"><span data-stu-id="c44e0-141">That the following namespaces be imported with C# `using` statements or Visual Basic `Imports` statements:</span></span>

  - <span data-ttu-id="c44e0-142"><xref:System> (только для C#);</span><span class="sxs-lookup"><span data-stu-id="c44e0-142"><xref:System> (C# only).</span></span>

  - <span data-ttu-id="c44e0-143"><xref:System.Globalization?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c44e0-143"><xref:System.Globalization?displayProperty=nameWithType>.</span></span>

  - <span data-ttu-id="c44e0-144"><xref:System.IO?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c44e0-144"><xref:System.IO?displayProperty=nameWithType>.</span></span>

  - <span data-ttu-id="c44e0-145"><xref:System.Runtime.Serialization?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c44e0-145"><xref:System.Runtime.Serialization?displayProperty=nameWithType>.</span></span>

  - <span data-ttu-id="c44e0-146"><xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c44e0-146"><xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="c44e0-147">Все примеры кода, кроме класса `DateInTimeZone`, нужно включить в класс или модуль Visual Basic, упаковать в методы и вызывать из метода `Main`.</span><span class="sxs-lookup"><span data-stu-id="c44e0-147">Each code example, other than the `DateInTimeZone` class, should be included in a class or Visual Basic module, wrapped in methods, and called from the `Main` method.</span></span>

## <a name="see-also"></a><span data-ttu-id="c44e0-148">См. также</span><span class="sxs-lookup"><span data-stu-id="c44e0-148">See also</span></span>

- [<span data-ttu-id="c44e0-149">Выполнение операций форматирования</span><span class="sxs-lookup"><span data-stu-id="c44e0-149">Performing Formatting Operations</span></span>](../../../docs/standard/base-types/performing-formatting-operations.md)
- <span data-ttu-id="c44e0-150">[Выбор между типами DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="c44e0-150">[Choosing Between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)</span></span>
- [<span data-ttu-id="c44e0-151">Строки стандартных форматов даты и времени</span><span class="sxs-lookup"><span data-stu-id="c44e0-151">Standard Date and Time Format Strings</span></span>](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)
