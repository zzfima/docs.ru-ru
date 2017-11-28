---
title: "Практическое руководство. Извлечение дня недели из конкретной даты"
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
- formatting [.NET Framework], dates
- DateTime.DayOfWeek property
- DateTime.ToString method
- dates [.NET Framework], retrieving week information
- DateTimeOffset.DayOfWeek property
- dates [.NET Framework], day of week
- Weekday function
- day of week [.NET Framework]
- extracting day of week
- weekday names
- WeekdayName function
- numbers [.NET Framework], day of week
- formatting [.NET Framework], time
- DateTimeOffset.ToString method
- full weekday names
ms.assetid: 1c9bef76-5634-46cf-b91c-9b9eb72091d7
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3accb01eb8c5edb8b3e245020b43c5a94a8bb4cd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-extract-the-day-of-the-week-from-a-specific-date"></a><span data-ttu-id="ebfb4-102">Практическое руководство. Извлечение дня недели из конкретной даты</span><span class="sxs-lookup"><span data-stu-id="ebfb4-102">How to: Extract the Day of the Week from a Specific Date</span></span>
<span data-ttu-id="ebfb4-103">Платформа .NET Framework упрощает определение дня недели и отображение локализованного дня для определенной даты.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-103">The .NET Framework makes it easy to determine the ordinal day of the week for a particular date, and to display the localized weekday name for a particular date.</span></span> <span data-ttu-id="ebfb4-104">Значение перечисления, которое указывает день недели, соответствующий определенной дате, можно получить из свойства <xref:System.DateTime.DayOfWeek%2A> или <xref:System.DateTimeOffset.DayOfWeek%2A>.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-104">An enumerated value that indicates the day of the week corresponding to a particular date is available from the <xref:System.DateTime.DayOfWeek%2A> or <xref:System.DateTimeOffset.DayOfWeek%2A> property.</span></span> <span data-ttu-id="ebfb4-105">Напротив, получение названия дня недели — это операция форматирования, которую можно выполнить с помощью метода форматирования, например метода `ToString` значения даты и времени или метода <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-105">In contrast, retrieving the weekday name is a formatting operation that can be performed by calling a formatting method, such as a date and time value's `ToString` method or the <xref:System.String.Format%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ebfb4-106">В этом разделе показано, как выполнить эти операции форматирования.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-106">This topic shows how to perform these formatting operations.</span></span>  
  
### <a name="to-extract-a-number-indicating-the-day-of-the-week-from-a-specific-date"></a><span data-ttu-id="ebfb4-107">Извлечение числа, обозначающего день недели, из определенной даты</span><span class="sxs-lookup"><span data-stu-id="ebfb4-107">To extract a number indicating the day of the week from a specific date</span></span>  
  
1.  <span data-ttu-id="ebfb4-108">Если вы работаете со строковым представлением даты, преобразуйте ее в значение типа <xref:System.DateTime> или <xref:System.DateTimeOffset>, используя статичный метод <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> или <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-108">If you are working with the string representation of a date, convert it to a <xref:System.DateTime> or a <xref:System.DateTimeOffset> value by using the static <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> or <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="ebfb4-109">Используйте свойство <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> или <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=nameWithType> для получения значения типа <xref:System.DayOfWeek>, которое указывает день недели.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-109">Use the <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> or <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=nameWithType> property to retrieve a <xref:System.DayOfWeek> value that indicates the day of the week.</span></span>  
  
3.  <span data-ttu-id="ebfb4-110">При необходимости приведите (в C#) или преобразуйте (в Visual Basic) значение <xref:System.DayOfWeek> в целочисленный тип.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-110">If necessary, cast (in C#) or convert (in Visual Basic) the <xref:System.DayOfWeek> value to an integer.</span></span>  
  
 <span data-ttu-id="ebfb4-111">Следующий пример отображает целое число, представляющее день недели для определенной даты.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-111">The following example displays an integer that represents the day of the week of a specific date.</span></span>  
  
 [!code-csharp[Formatting.Howto.WeekdayName#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/weekdaynumber7.cs#7)]
 [!code-vb[Formatting.Howto.WeekdayName#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/weekdaynumber7.vb#7)]  
  
### <a name="to-extract-the-abbreviated-weekday-name-from-a-specific-date"></a><span data-ttu-id="ebfb4-112">Извлечение сокращенного названия дня недели из определенной даты</span><span class="sxs-lookup"><span data-stu-id="ebfb4-112">To extract the abbreviated weekday name from a specific date</span></span>  
  
1.  <span data-ttu-id="ebfb4-113">Если вы работаете со строковым представлением даты, преобразуйте ее в значение типа <xref:System.DateTime> или <xref:System.DateTimeOffset>, используя статичный метод <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> или <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-113">If you are working with the string representation of a date, convert it to a <xref:System.DateTime> or a <xref:System.DateTimeOffset> value by using the static <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> or <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="ebfb4-114">Вы можете извлечь сокращенное название дня недели для текущих или заданных региональных параметров:</span><span class="sxs-lookup"><span data-stu-id="ebfb4-114">You can extract the abbreviated weekday name of the current culture or of a specific culture:</span></span>  
  
    1.  <span data-ttu-id="ebfb4-115">Чтобы извлечь сокращенное название дня недели для текущих региональных параметров, вызовите метод <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> значения даты и времени или метод экземпляра <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> и передайте строку "ddd" в параметре `format`.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-115">To extract the abbreviated weekday name for the current culture, call the date and time value's <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> instance method, and pass the string "ddd" as the `format` parameter.</span></span> <span data-ttu-id="ebfb4-116">В следующем примере показано использование метода <xref:System.DateTime.ToString%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-116">The following example illustrates the call to the <xref:System.DateTime.ToString%28System.String%29> method.</span></span>  
  
         [!code-csharp[Formatting.Howto.WeekdayName#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/abbrname1.cs#1)]
         [!code-vb[Formatting.Howto.WeekdayName#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/abbrname1.vb#1)]  
  
    2.  <span data-ttu-id="ebfb4-117">Чтобы извлечь сокращенное название дня недели для заданных региональных параметров, вызовите метод <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> значения даты и времени или метод экземпляра <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-117">To extract the abbreviated weekday name for a specific culture, call the date and time value’s <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> instance method.</span></span> <span data-ttu-id="ebfb4-118">Передайте строку "ddd" в параметре `format`.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-118">Pass the string "ddd" as the `format` parameter.</span></span> <span data-ttu-id="ebfb4-119">Передайте объект <xref:System.Globalization.CultureInfo> или <xref:System.Globalization.DateTimeFormatInfo>, представляющий региональные параметры, для которых требуется получить название дня недели, в параметре `provider`.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-119">Pass either a <xref:System.Globalization.CultureInfo> or a <xref:System.Globalization.DateTimeFormatInfo> object that represents the culture whose weekday name you want to retrieve as the `provider` parameter.</span></span> <span data-ttu-id="ebfb4-120">В следующем коде показан вызов метода <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> с использованием объекта <xref:System.Globalization.CultureInfo>, представляющего региональные параметры fr-FR.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-120">The following code illustrates a call to the <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> method using a <xref:System.Globalization.CultureInfo> object that represents the fr-FR culture.</span></span>  
  
         [!code-csharp[Formatting.Howto.WeekdayName#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/abbrname2.cs#2)]
         [!code-vb[Formatting.Howto.WeekdayName#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/abbrname2.vb#2)]  
  
### <a name="to-extract-the-full-weekday-name-from-a-specific-date"></a><span data-ttu-id="ebfb4-121">Извлечение полного названия дня недели из определенной даты</span><span class="sxs-lookup"><span data-stu-id="ebfb4-121">To extract the full weekday name from a specific date</span></span>  
  
1.  <span data-ttu-id="ebfb4-122">Если вы работаете со строковым представлением даты, преобразуйте ее в значение типа <xref:System.DateTime> или <xref:System.DateTimeOffset>, используя статичный метод <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> или <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-122">If you are working with the string representation of a date, convert it to a <xref:System.DateTime> or a <xref:System.DateTimeOffset> value by using the static <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> or <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="ebfb4-123">Вы можете извлечь полное название дня недели для текущих или заданных региональных параметров:</span><span class="sxs-lookup"><span data-stu-id="ebfb4-123">You can extract the full weekday name of the current culture or of a specific culture:</span></span>  
  
    1.  <span data-ttu-id="ebfb4-124">Чтобы извлечь полное название дня недели для текущих региональных параметров, вызовите метод <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> значения даты и времени или метод экземпляра <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> и передайте строку "dddd" в параметре `format`.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-124">To extract the weekday name for the current culture, call the date and time value’s <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> instance method, and pass the string "dddd" as the `format` parameter.</span></span> <span data-ttu-id="ebfb4-125">В следующем примере показано использование метода <xref:System.DateTime.ToString%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-125">The following example illustrates the call to the <xref:System.DateTime.ToString%28System.String%29> method.</span></span>  
  
         [!code-csharp[Formatting.Howto.WeekdayName#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/fullname4.cs#4)]
         [!code-vb[Formatting.Howto.WeekdayName#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/fullname4.vb#4)]  
  
    2.  <span data-ttu-id="ebfb4-126">Чтобы извлечь полное название дня недели для заданных региональных параметров, вызовите метод <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> значения даты и времени или метод экземпляра <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-126">To extract the weekday name for a specific culture, call the date and time value’s <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> instance method.</span></span> <span data-ttu-id="ebfb4-127">Передайте строку "dddd" в параметре `format`.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-127">Pass the string "dddd" as the `format` parameter.</span></span> <span data-ttu-id="ebfb4-128">Передайте объект <xref:System.Globalization.CultureInfo> или <xref:System.Globalization.DateTimeFormatInfo>, представляющий региональные параметры, для которых требуется получить название дня недели, в параметре `provider`.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-128">Pass either a <xref:System.Globalization.CultureInfo> or a <xref:System.Globalization.DateTimeFormatInfo> object that represents the culture whose weekday name you want to retrieve as the `provider` parameter.</span></span> <span data-ttu-id="ebfb4-129">В следующем коде показан вызов метода <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> с использованием объекта <xref:System.Globalization.CultureInfo>, представляющего региональные параметры es-ES.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-129">The following code illustrates a call to the <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> method using a <xref:System.Globalization.CultureInfo> object that represents the es-ES culture.</span></span>  
  
         [!code-csharp[Formatting.Howto.WeekdayName#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/fullname5.cs#5)]
         [!code-vb[Formatting.Howto.WeekdayName#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/fullname5.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="ebfb4-130">Пример</span><span class="sxs-lookup"><span data-stu-id="ebfb4-130">Example</span></span>  
 <span data-ttu-id="ebfb4-131">В этом примере показаны вызовы свойств <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> и <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=nameWithType>, а также методов <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> и <xref:System.DateTimeOffset.ToString%2A?displayProperty=nameWithType> для получения числа, представляющего день недели, сокращенное и полное название дня недели для определенной даты.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-131">The example illustrates calls to the <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> and <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=nameWithType> properties and the <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> and <xref:System.DateTimeOffset.ToString%2A?displayProperty=nameWithType> methods to retrieve the number that represents the day of the week, the abbreviated weekday name, and the full weekday name for a particular date.</span></span>  
  
 [!code-csharp[Formatting.Howto.WeekdayName#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/example6.cs#6)]
 [!code-vb[Formatting.Howto.WeekdayName#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/example6.vb#6)]  
  
 <span data-ttu-id="ebfb4-132">Отдельные языки могут предоставлять возможности, дублирующие или дополняющие функции [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ebfb4-132">Individual languages may provide functionality that duplicates or supplements the functionality provided by the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="ebfb4-133">Например, Visual Basic предоставляет две такие функции:</span><span class="sxs-lookup"><span data-stu-id="ebfb4-133">For example, Visual Basic includes two such functions:</span></span>  
  
-   <span data-ttu-id="ebfb4-134">`Weekday`, которая возвращает число, обозначающее день недели для определенной даты.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-134">`Weekday`, which returns a number that indicates the day of the week of a particular date.</span></span> <span data-ttu-id="ebfb4-135">Функция считает порядковое значение первого дня недели равным 1, а свойство <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> — равным 0.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-135">It considers the ordinal value of the first day of the week to be one, whereas the <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> property considers it to be zero.</span></span>  
  
-   <span data-ttu-id="ebfb4-136">`WeekdayName`, которая возвращает название дня недели для текущих региональных параметров, которое соответствует определенному номеру дня недели.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-136">`WeekdayName`, which returns the name of the week in the current culture that corresponds to a particular weekday number.</span></span>  
  
 <span data-ttu-id="ebfb4-137">В следующем примере показано использование функций `Weekday` и `WeekdayName` Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-137">The following example illustrates the use of the Visual Basic `Weekday` and `WeekdayName` functions.</span></span>  
  
 [!code-vb[Formatting.HowTo.WeekdayName#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/example9.vb#9)]  
  
 <span data-ttu-id="ebfb4-138">Вы также можете использовать значение, возвращенное свойством <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType>, для получения названия дня недели для определенной даты.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-138">You can also use the value returned by the <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> property to retrieve the weekday name of a particular date.</span></span> <span data-ttu-id="ebfb4-139">Для этого требуется просто вызвать метод <xref:System.Enum.ToString%2A> для значения <xref:System.DayOfWeek>, возвращенного свойством.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-139">This requires only a call to the <xref:System.Enum.ToString%2A> method on the <xref:System.DayOfWeek> value returned by the property.</span></span> <span data-ttu-id="ebfb4-140">Однако этот способ не позволяет получить локализованное название дня недели для текущих региональных параметров, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ebfb4-140">However, this technique does not produce a localized weekday name for the current culture, as the following example illustrates.</span></span>  
  
 [!code-csharp[Formatting.HowTo.WeekdayName#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/Howto1.cs#8)]
 [!code-vb[Formatting.HowTo.WeekdayName#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/Howto1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="ebfb4-141">См. также</span><span class="sxs-lookup"><span data-stu-id="ebfb4-141">See Also</span></span>  
 [<span data-ttu-id="ebfb4-142">Выполнение операций форматирования</span><span class="sxs-lookup"><span data-stu-id="ebfb4-142">Performing Formatting Operations</span></span>](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [<span data-ttu-id="ebfb4-143">Standard Date and Time Format Strings</span><span class="sxs-lookup"><span data-stu-id="ebfb4-143">Standard Date and Time Format Strings</span></span>](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)  
 [<span data-ttu-id="ebfb4-144">Custom Date and Time Format Strings</span><span class="sxs-lookup"><span data-stu-id="ebfb4-144">Custom Date and Time Format Strings</span></span>](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)
