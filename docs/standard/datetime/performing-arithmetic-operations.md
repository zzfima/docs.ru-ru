---
title: Выполнение арифметических операций с датами и временем
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- times [.NET Framework], arithmetic operations
- dates [.NET Framework], arithmetic operations
- time zones [.NET Framework], arithmetic operations
- arithmetic operations [.NET Framework], dates and times
- dates [.NET Framework], comparing
- DateTime structure, arithmetic operations
- DateTimeOffset structure, arithmetic operations
ms.assetid: 87c7ddf2-f15e-48af-8602-b3642237e6d0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5bbd5afb89d2b992e06583c7427c1a25a5b8f273
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="performing-arithmetic-operations-with-dates-and-times"></a>Выполнение арифметических операций с датами и временем

Несмотря на то что оба <xref:System.DateTime> и <xref:System.DateTimeOffset> структуры предоставляют члены, которые выполняют арифметические операции над значениями, результаты арифметических операций очень различаются. В этом разделе эти различия, связывающее их в градусы сведения о часовом поясе в данных даты и времени и рассматриваются как полностью выполнять операции учитывать часового пояса, использование данных даты и времени.

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a>Сравнения и арифметические операции со значениями типа DateTime

<xref:System.DateTime.Kind%2A?displayProperty=nameWithType> Свойство позволяет <xref:System.DateTimeKind> значения даты и времени, чтобы указать, представляет ли оно местное время, универсальное глобальное (UTC) или время в неопределенном часовом поясе. Тем не менее, это ограниченные сведения о часовом поясе учитывается при сравнении или выполнении арифметических операций на <xref:System.DateTimeKind> значения. Это демонстрируется в следующем примере, где текущее местное время сравнивается с текущим временем в формате UTC.

[!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]

<xref:System.DateTime.CompareTo%28System.DateTime%29> Метод сообщает, что местное время предшествует (или менее) в формате UTC, а операция вычитания указывает, что разница между временем UTC и местным временем для системы в США. США составляет семь часов. Тем не менее, поскольку эти значения дают различные представления одного и того же момента времени, в данном случае очевидно, что причина этого различия целиком кроется в смещении местного часового пояса относительно времени в формате UTC.

Как правило <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> свойства не влияет на результаты, возвращенные <xref:System.DateTime.Kind> методы сравнения и арифметических (как показывает результат сравнения двух идентичных моментов времени), несмотря на то, что может повлиять на интерпретацию этих результатов. Пример:

* Выполнить результатом любой арифметической операции над двумя значениями даты и времени, <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> свойства обоих равно <xref:System.DateTimeKind> отражает фактический интервал времени между двумя значениями. Аналогичным образом результат сравнения двух таких значений даты и времени будет точно отражать соотношение между временами.

* Результатом любой арифметической операции сравнения операции или выполнить над двумя значениями даты и времени, <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> свойства обоих равно <xref:System.DateTimeKind> или над двумя значениями даты и времени с различными <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> значения свойств отражает разницу во времени между этими двумя значениями.

* Арифметические операции или операции сравнения, выполняемые над местными значениями даты и времени, не учитывают допустимость или недопустимость конкретных значений; не учитывают они и какие-либо правила коррекции, необходимые при переводе местного часового пояса на зимнее или летнее время.

* В результат любой операции, сравнивающей или вычисляющей разницу между временем в формате UTC и местным временем, входит временной интервал, равный смещению местного часового пояса относительно времени в формате UTC.

* Любая операция, которая сравнивает или вычисляет разницу между неуказанным временем и временем в формате UTC или местным временем, соответствует простому времени. Различия между часовыми поясами не учитываются, и в результате не отражено применение правил коррекции часовых поясов.

* Любая операция, которая сравнивает или вычисляет разницу между двумя неуказанными значениями времени, может включать неизвестный интервал, который отражает временную разницу между двумя различными часовыми поясами.

Существует множество сценариев, в какой часовой пояс различия не влияют на вычисления даты и времени (Описание некоторых из них см. в разделе [Выбор между DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)) или в котором контекст для даты и времени данных определяет суть операций сравнения или арифметических операций.

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a>Сравнения и арифметические операции со значениями DateTimeOffset

Объект <xref:System.DateTimeOffset> значение включает не только дату и время, но также смещение, которое однозначно определяет, даты и времени относительно времени UTC. Это дает возможность определить равенство несколько иначе, чем для <xref:System.DateTimeOffset> значения. В то время как <xref:System.DateTime> значения равны, если они имеют одинаковые значения даты и времени, <xref:System.DateTimeOffset> значения равны, если они ссылаются на один момент времени. Это делает <xref:System.DateTimeOffset> значение более точными и менее контекстно-зависимым при использовании в сравнении и в большинстве арифметических операций, которые определяют интервал между двумя значениями даты и времени. В следующем примере является <xref:System.DateTimeOffset> эквивалент в предыдущем примере, где сравнение локальной и UTC <xref:System.DateTimeOffset> значений, иллюстрирует разницу в поведении.

[!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]

В этом примере <xref:System.DateTimeOffset.CompareTo%2A> метод означает, что текущее местное время и текущее время в формате UTC равенства и вычитание <xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)> значения указывает, что разница между двумя значениями времени <xref:System.TimeSpan.Zero?displayProperty=nameWithType>.

Главным препятствием для использования <xref:System.DateTimeOffset> значения в арифметических операций является, несмотря на то что <xref:System.DateTimeOffset> значения имеют некоторые сведения о часовом поясе, не полностью часовом поясе. Несмотря на то что <xref:System.DateTimeOffset> смещение отражает смещение часового пояса от времени UTC, когда <xref:System.DateTimeOffset> переменной вначале присваивается значение, он становится отменить связь с часовым поясом соответственно. Поскольку оно больше не связано напрямую с распознаваемым временем, правила коррекции часовых поясов больше не будут учитываться при сложении и вычитании интервалов даты и времени.

Пример: переход на летнее время в зоне центрального стандартного времени США происходит в 2:00 утра 9 марта, 2008 г. Это означает, что при прибавлении двух с половиной часов к 1:30 утра 9 марта 2008 г. центрального стандартного времени США должно получиться 5:00 утра 9 марта, 2008 г. Однако, как показано в следующем примере, результатом сложения является 4:00 утра 9 марта, 2008 г. Обратите внимание, что такой результат данной операции представляет правильный момент времени, хотя и не является временем в искомом часовом поясе (в результате не содержится ожидаемое смещение часового пояса).

[!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]

## <a name="arithmetic-operations-with-times-in-time-zones"></a>Арифметические операции со временем в часовых поясах

<xref:System.TimeZoneInfo> Класс содержит ряд методов преобразования, которые автоматически применяют правила коррекции при переводе значения времени из одного часового пояса в другой. В число этих требований входят следующие:

* <xref:System.TimeZoneInfo.ConvertTime%2A> И <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A> методы, которые преобразуют значения времени между любыми двумя часовыми поясами.

* <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> И <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> методы, которые преобразуют время в заданном часовом поясе в формат UTC, или преобразовать во время в заданном часовом поясе UTC.

Дополнительные сведения см. в разделе [преобразование времени в разных часовых поясах](../../../docs/standard/datetime/converting-between-time-zones.md).

<xref:System.TimeZoneInfo.ConvertTimeToUtc(System.DateTime)> Класс предоставляет методы, которые автоматически применяют правила коррекции при выполнении арифметических операций. Тем не менее, этого можно добиться, преобразовав время в часовом поясе во время в формате UTC, выполнив арифметическую операцию и преобразовав время UTC обратно во время в часовом поясе. Дополнительные сведения см. в разделе [как: использование часовых поясов в арифметических операций](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md).

Например, следующий код аналогичен предыдущему коду, в котором 2,5 часа добавлялись к 2:00 утра 9 марта, 2008 г. Тем не менее, поскольку в этом примере перед выполнением арифметических действий над датой и временем центральное стандартное время преобразуется во время в формате UTC, а затем результат преобразуется из времени UTC обратно в центральное стандартное время, полученное время соответствует переходу центрального стандартного часового пояса на летнее время.

[!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]

## <a name="see-also"></a>См. также

[Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
[как: использование часовых поясов в арифметических операций](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)
