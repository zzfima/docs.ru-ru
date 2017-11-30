---
title: "Практическое руководство. Обеспечение однозначности при сохранении и восстановлении значений даты и времени"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 515a29e279cfa8fc100e0612fc19df7abc6a3b36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-round-trip-date-and-time-values"></a><span data-ttu-id="2c87e-102">Практическое руководство. Обеспечение однозначности при сохранении и восстановлении значений даты и времени</span><span class="sxs-lookup"><span data-stu-id="2c87e-102">How to: Round-trip Date and Time Values</span></span>
<span data-ttu-id="2c87e-103">Во многих приложениях значение даты и времени предназначено для однозначного определения одного момента времени.</span><span class="sxs-lookup"><span data-stu-id="2c87e-103">In many applications, a date and time value is intended to unambiguously identify a single point in time.</span></span> <span data-ttu-id="2c87e-104">В этом разделе показано, как сохранять и восстанавливать <xref:System.DateTime> значение <xref:System.DateTimeOffset> значение и значение даты и времени с временем информации о зоне, чтобы восстановленное значение определяет то же время, что и сохраненное значение.</span><span class="sxs-lookup"><span data-stu-id="2c87e-104">This topic shows how to save and restore a <xref:System.DateTime> value, a <xref:System.DateTimeOffset> value, and a date and time value with time zone information so that the restored value identifies the same time as the saved value.</span></span>  
  
### <a name="to-round-trip-a-datetime-value"></a><span data-ttu-id="2c87e-105">Выполнение цикла обработки значения DateTime</span><span class="sxs-lookup"><span data-stu-id="2c87e-105">To round-trip a DateTime value</span></span>  
  
1.  <span data-ttu-id="2c87e-106">Преобразовать <xref:System.DateTime> значение в строковое представление, вызвав <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> метод с помощью описателя формата «o».</span><span class="sxs-lookup"><span data-stu-id="2c87e-106">Convert the <xref:System.DateTime> value to its string representation by calling the <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> method with the "o" format specifier.</span></span>  
  
2.  <span data-ttu-id="2c87e-107">Сохраните строковое представление <xref:System.DateTime> в файл или передайте его между процессами, домен приложения или между компьютерами.</span><span class="sxs-lookup"><span data-stu-id="2c87e-107">Save the string representation of the <xref:System.DateTime> value to a file, or pass it across a process, application domain, or machine boundary.</span></span>  
  
3.  <span data-ttu-id="2c87e-108">Получить строку, представляющую <xref:System.DateTime> значение.</span><span class="sxs-lookup"><span data-stu-id="2c87e-108">Retrieve the string that represents the <xref:System.DateTime> value.</span></span>  
  
4.  <span data-ttu-id="2c87e-109">Вызовите <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> и передайте <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> в качестве значения `styles` параметра.</span><span class="sxs-lookup"><span data-stu-id="2c87e-109">Call the <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> method, and pass <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> as the value of the `styles` parameter.</span></span>  
  
 <span data-ttu-id="2c87e-110">Следующий пример иллюстрирует способ обратного преобразования <xref:System.DateTime> значение.</span><span class="sxs-lookup"><span data-stu-id="2c87e-110">The following example illustrates how to round-trip a <xref:System.DateTime> value.</span></span>  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
 [!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]  
  
 <span data-ttu-id="2c87e-111">При полной совместимости версий <xref:System.DateTime> значение, этот метод успешно сохраняет время локального и универсального времени.</span><span class="sxs-lookup"><span data-stu-id="2c87e-111">When round-tripping a <xref:System.DateTime> value, this technique successfully preserves the time for all local and universal times.</span></span> <span data-ttu-id="2c87e-112">Например, если локальный <xref:System.DateTime> значение сохраняется в системе в США. тихоокеанском стандартном часовом поясе США и восстановлено в системе в центральном стандартном часовом поясе США, восстановленные дата и время будут на два часа больше исходного времени, что отражает разницу во времени между двумя часовыми поясами.</span><span class="sxs-lookup"><span data-stu-id="2c87e-112">For example, if a local <xref:System.DateTime> value is saved on a system in the U.S. Pacific Standard Time zone and is restored on a system in the U.S. Central Standard Time zone, the restored date and time will be two hours later than the original time, which reflects the time difference between the two time zones.</span></span> <span data-ttu-id="2c87e-113">Однако этот способ не всегда точен для неуказанного времени.</span><span class="sxs-lookup"><span data-stu-id="2c87e-113">However, this technique is not necessarily accurate for unspecified times.</span></span> <span data-ttu-id="2c87e-114">Все <xref:System.DateTime> значения которого <xref:System.DateTime.Kind%2A> свойство <xref:System.DateTimeKind.Unspecified> обрабатываются, как если бы они были местного времени.</span><span class="sxs-lookup"><span data-stu-id="2c87e-114">All <xref:System.DateTime> values whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Unspecified> are treated as if they are local times.</span></span> <span data-ttu-id="2c87e-115">Если это не так, <xref:System.DateTime> не будет успешно определять нужный момент времени.</span><span class="sxs-lookup"><span data-stu-id="2c87e-115">If this is not the case, the <xref:System.DateTime> will not successfully identify the correct point in time.</span></span> <span data-ttu-id="2c87e-116">Чтобы устранить это ограничение, нужно тесно связать значение даты и времени с его часовым поясом для операций сохранения и восстановления.</span><span class="sxs-lookup"><span data-stu-id="2c87e-116">The workaround for this limitation is to tightly couple a date and time value with its time zone for the save and restore operation.</span></span>  
  
### <a name="to-round-trip-a-datetimeoffset-value"></a><span data-ttu-id="2c87e-117">Выполнение цикла обработки значения DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="2c87e-117">To round-trip a DateTimeOffset value</span></span>  
  
1.  <span data-ttu-id="2c87e-118">Преобразовать <xref:System.DateTimeOffset> значение в строковое представление, вызвав <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> метод с помощью описателя формата «o».</span><span class="sxs-lookup"><span data-stu-id="2c87e-118">Convert the <xref:System.DateTimeOffset> value to its string representation by calling the <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> method with the "o" format specifier.</span></span>  
  
2.  <span data-ttu-id="2c87e-119">Сохраните строковое представление <xref:System.DateTimeOffset> в файл или передайте его между процессами, домен приложения или между компьютерами.</span><span class="sxs-lookup"><span data-stu-id="2c87e-119">Save the string representation of the <xref:System.DateTimeOffset> value to a file, or pass it across a process, application domain, or machine boundary.</span></span>  
  
3.  <span data-ttu-id="2c87e-120">Получить строку, представляющую <xref:System.DateTimeOffset> значение.</span><span class="sxs-lookup"><span data-stu-id="2c87e-120">Retrieve the string that represents the <xref:System.DateTimeOffset> value.</span></span>  
  
4.  <span data-ttu-id="2c87e-121">Вызовите <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> и передайте <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> в качестве значения `styles` параметра.</span><span class="sxs-lookup"><span data-stu-id="2c87e-121">Call the <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> method, and pass <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> as the value of the `styles` parameter.</span></span>  
  
 <span data-ttu-id="2c87e-122">Следующий пример иллюстрирует способ обратного преобразования <xref:System.DateTimeOffset> значение.</span><span class="sxs-lookup"><span data-stu-id="2c87e-122">The following example illustrates how to round-trip a <xref:System.DateTimeOffset> value.</span></span>  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
 [!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]  
  
 <span data-ttu-id="2c87e-123">Этот метод всегда однозначно идентифицирует <xref:System.DateTimeOffset> значение как единственный момент времени.</span><span class="sxs-lookup"><span data-stu-id="2c87e-123">This technique always unambiguously identifies a <xref:System.DateTimeOffset> value as a single point in time.</span></span> <span data-ttu-id="2c87e-124">Значение затем может быть преобразован в формате UTC, вызвав <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> метод, или его можно преобразовать во время в заданном часовом поясе, вызвав <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> или <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="2c87e-124">The value can then be converted to Coordinated Universal Time (UTC) by calling the <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> method, or it can be converted to the time in a particular time zone by calling the <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> or <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="2c87e-125">Основным ограничением этого метода является эту дату и время арифметические операции, при выполнении <xref:System.DateTimeOffset> значение, представляющее время в заданном часовом поясе, может возвратить неточные результаты для этого часового пояса.</span><span class="sxs-lookup"><span data-stu-id="2c87e-125">The major limitation of this technique is that date and time arithmetic, when performed on a <xref:System.DateTimeOffset> value that represents the time in a particular time zone, may not produce accurate results for that time zone.</span></span> <span data-ttu-id="2c87e-126">Это, поскольку при <xref:System.DateTimeOffset> создается значение, он отсоединяется от его часовым поясом.</span><span class="sxs-lookup"><span data-stu-id="2c87e-126">This is because when a <xref:System.DateTimeOffset> value is instantiated, it is disassociated from its time zone.</span></span> <span data-ttu-id="2c87e-127">Таким образом, правила коррекции часового пояса не могут быть больше применены при выполнении вычислений с датами и временем.</span><span class="sxs-lookup"><span data-stu-id="2c87e-127">Therefore, that time zone's adjustment rules can no longer be applied when you perform date and time calculations.</span></span> <span data-ttu-id="2c87e-128">Можно обойти эту проблему, определив пользовательский тип, который содержит значение даты и времени с его соответствующим часовым поясом.</span><span class="sxs-lookup"><span data-stu-id="2c87e-128">You can work around this problem by defining a custom type that includes both a date and time value and its accompanying time zone.</span></span>  
  
### <a name="to-round-trip-a-date-and-time-value-with-its-time-zone"></a><span data-ttu-id="2c87e-129">Для обратного преобразования даты и времени значение с его часовым поясом</span><span class="sxs-lookup"><span data-stu-id="2c87e-129">To round-trip a date and time value with its time zone</span></span>  
  
1.  <span data-ttu-id="2c87e-130">Определите класс или структуру с двумя полями.</span><span class="sxs-lookup"><span data-stu-id="2c87e-130">Define a class or a structure with two fields.</span></span> <span data-ttu-id="2c87e-131">Первое поле имеет либо <xref:System.DateTime> или <xref:System.DateTimeOffset> , а второй — <xref:System.TimeZoneInfo> объекта.</span><span class="sxs-lookup"><span data-stu-id="2c87e-131">The first field is either a <xref:System.DateTime> or a <xref:System.DateTimeOffset> object, and the second is a <xref:System.TimeZoneInfo> object.</span></span> <span data-ttu-id="2c87e-132">Следующий пример является простой версией такого типа.</span><span class="sxs-lookup"><span data-stu-id="2c87e-132">The following example is a simple version of such a type.</span></span>  
  
     [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
     [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]  
  
2.  <span data-ttu-id="2c87e-133">Пометить класс с <xref:System.SerializableAttribute> атрибута.</span><span class="sxs-lookup"><span data-stu-id="2c87e-133">Mark the class with the <xref:System.SerializableAttribute> attribute.</span></span>  
  
3.  <span data-ttu-id="2c87e-134">Сериализация объекта с использованием <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="2c87e-134">Serialize the object using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> method.</span></span>  
  
4.  <span data-ttu-id="2c87e-135">Восстановите объект с помощью <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="2c87e-135">Restore the object using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> method.</span></span>  
  
5.  <span data-ttu-id="2c87e-136">Приведите (в C#) или преобразуйте (в Visual Basic) Десериализованный объект к объекту соответствующего типа.</span><span class="sxs-lookup"><span data-stu-id="2c87e-136">Cast (in C#) or convert (in Visual Basic) the deserialized object to an object of the appropriate type.</span></span>  
  
 <span data-ttu-id="2c87e-137">В следующем примере показано, как цикл обработки объекта, сохраняет сведения о дате и времени и часового пояса.</span><span class="sxs-lookup"><span data-stu-id="2c87e-137">The following example illustrates how to round-trip an object that stores both date and time and time zone information.</span></span>  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
 [!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]  
  
 <span data-ttu-id="2c87e-138">Этот метод всегда должен однозначно отражать правильной точки времени оба до и после его сохранения и восстановления, что реализация комбинированный объект даты и времени и часового пояса не разрешают значения даты, будут синхронизироваться с значение часового пояса.</span><span class="sxs-lookup"><span data-stu-id="2c87e-138">This technique should always unambiguously reflect the correct point of time both before and after it is saved and restored, provided that the implementation of the combined date and time and time zone object does not allow the date value to become out of sync with the time zone value.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2c87e-139">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="2c87e-139">Compiling the Code</span></span>  
 <span data-ttu-id="2c87e-140">Для этих примеров требуются:</span><span class="sxs-lookup"><span data-stu-id="2c87e-140">These examples require:</span></span>  
  
-   <span data-ttu-id="2c87e-141">Что импортируются следующие пространства имен с помощью C# `using` инструкций или [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="2c87e-141">That the following namespaces be imported with C# `using` statements or [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `Imports` statements:</span></span>  
  
    -   <span data-ttu-id="2c87e-142"><xref:System>(Только C#).</span><span class="sxs-lookup"><span data-stu-id="2c87e-142"><xref:System> (C# only).</span></span>  
  
    -   <span data-ttu-id="2c87e-143"><xref:System.Globalization?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2c87e-143"><xref:System.Globalization?displayProperty=nameWithType>.</span></span>  
  
    -   <span data-ttu-id="2c87e-144"><xref:System.IO?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2c87e-144"><xref:System.IO?displayProperty=nameWithType>.</span></span>  
  
    -   <span data-ttu-id="2c87e-145"><xref:System.Runtime.Serialization?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2c87e-145"><xref:System.Runtime.Serialization?displayProperty=nameWithType>.</span></span>  
  
    -   <span data-ttu-id="2c87e-146"><xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2c87e-146"><xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="2c87e-147">Ссылка на библиотеку System.Core.dll.</span><span class="sxs-lookup"><span data-stu-id="2c87e-147">A reference to System.Core.dll.</span></span>  
  
-   <span data-ttu-id="2c87e-148">Каждый пример кода, отличный от `DateInTimeZone` класса, должны включены в класс или модуль Visual Basic, упакован в методы и вызывать из `Main` метод.</span><span class="sxs-lookup"><span data-stu-id="2c87e-148">Each code example, other than the `DateInTimeZone` class, should be included in a class or Visual Basic module, wrapped in methods, and called from the `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c87e-149">См. также</span><span class="sxs-lookup"><span data-stu-id="2c87e-149">See Also</span></span>  
 [<span data-ttu-id="2c87e-150">Выполнение операций форматирования</span><span class="sxs-lookup"><span data-stu-id="2c87e-150">Performing Formatting Operations</span></span>](../../../docs/standard/base-types/performing-formatting-operations.md)  
 <span data-ttu-id="2c87e-151">[Выбор между типами DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="2c87e-151">[Choosing Between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)</span></span>  
 [<span data-ttu-id="2c87e-152">Standard Date and Time Format Strings</span><span class="sxs-lookup"><span data-stu-id="2c87e-152">Standard Date and Time Format Strings</span></span>](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)
