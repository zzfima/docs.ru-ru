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
ms.openlocfilehash: 2e668cf3f909ed4b89f05ca63dfe69051c1d9066
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122266"
---
# <a name="performing-arithmetic-operations-with-dates-and-times"></a>Выполнение арифметических операций с датами и временем

Несмотря на то, что структуры <xref:System.DateTime> и <xref:System.DateTimeOffset> предоставляют члены, выполняющие арифметические операции с их значениями, результаты арифметических операций сильно отличаются. В этом разделе рассматриваются эти различия, приводятся сведения о них в степени осведомленности о часовых поясах в данных даты и времени, а также рассматривается выполнение операций с полной поддержкой часовых поясов с использованием данных даты и времени.

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a>Сравнения и арифметические операции со значениями типа DateTime

Свойство <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> позволяет присваивать <xref:System.DateTimeKind>у значение даты и времени, чтобы указать, представляет ли оно местное время, время в формате UTC или время в неопределенном часовом поясе. Однако эти ограниченные сведения о часовом поясе игнорируются при сравнении или выполнении арифметических операций с датами и временем для <xref:System.DateTimeKind> значений. Это демонстрируется в следующем примере, где текущее местное время сравнивается с текущим временем в формате UTC.

[!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]

Метод <xref:System.DateTime.CompareTo%28System.DateTime%29> показывает, что местное время раньше (меньше) времени в поясе UTC, а операция вычитания свидетельствует о том, что разница между временем в поясе UTC и местным временем для систем в тихоокеанском стандартном часовом поясе США составляет семь часов. Тем не менее, поскольку эти значения дают различные представления одного и того же момента времени, в данном случае очевидно, что причина этого различия целиком кроется в смещении местного часового пояса относительно времени в формате UTC.

В общем случае свойство <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> не влияет на результаты, возвращаемые <xref:System.DateTime.Kind>ным методом сравнения и арифметическими методами (как сравнение двух идентичных точек во времени указывает), хотя это может повлиять на интерпретацию этих результатов. Пример:

- Результат выполнения любой арифметической операции с двумя значениями даты и времени, свойства <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> которых равны <xref:System.DateTimeKind>, отражает фактический интервал времени между двумя значениями. Аналогичным образом результат сравнения двух таких значений даты и времени будет точно отражать соотношение между временами.

- Результат любой операции арифметического или сравнения с двумя значениями даты и времени, свойства <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> которых равны <xref:System.DateTimeKind> или в двух значениях даты и времени с различными значениями свойств <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> отражает разницу в времени между двумя данные.

- Арифметические операции или операции сравнения, выполняемые над местными значениями даты и времени, не учитывают допустимость или недопустимость конкретных значений; не учитывают они и какие-либо правила коррекции, необходимые при переводе местного часового пояса на зимнее или летнее время.

- В результат любой операции, сравнивающей или вычисляющей разницу между временем в формате UTC и местным временем, входит временной интервал, равный смещению местного часового пояса относительно времени в формате UTC.

- Любая операция, которая сравнивает или вычисляет разницу между неуказанным временем и временем в формате UTC или местным временем, соответствует простому времени. Различия между часовыми поясами не учитываются, и в результате не отражено применение правил коррекции часовых поясов.

- Любая операция, которая сравнивает или вычисляет разницу между двумя неуказанными значениями времени, может включать неизвестный интервал, который отражает временную разницу между двумя различными часовыми поясами.

Существует множество ситуаций, в которых разницы часовых поясов не влияют на вычисления даты и времени (для некоторых из них см. раздел [Выбор между DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)) или в контексте данных даты и времени. Определяет значение операций сравнения или арифметической операции.

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a>Сравнения и арифметические операции со значениями DateTimeOffset

<xref:System.DateTimeOffset> значение включает не только дату и время, но и смещение, которое однозначно определяет эту дату и время относительно времени в формате UTC. Это дает возможность определить равенство несколько иначе, чем для <xref:System.DateTimeOffset> значений. В то время как <xref:System.DateTime> значения равны, если они имеют одинаковые значения даты и времени, <xref:System.DateTimeOffset> значения равны, если они ссылаются на один и тот же момент времени. Это делает <xref:System.DateTimeOffset> значение более точным и меньшим при необходимости интерпретации при использовании в сравнениях и в большинстве арифметических операций, определяющих интервал между двумя датами и временем. В следующем примере, который является <xref:System.DateTimeOffset> эквивалент предыдущего примера, который сравнивает значения Local и UTC <xref:System.DateTimeOffset>, демонстрирует это различие в поведении.

[!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]

В этом примере метод <xref:System.DateTimeOffset.CompareTo%2A> указывает, что текущее местное время и текущее время в формате UTC равны, а вычитание значений <xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)> указывает на то, что разница между двумя значениями времени — <xref:System.TimeSpan.Zero?displayProperty=nameWithType>.

Главным ограничением использования <xref:System.DateTimeOffset> значений в арифметических операциях с датами и временем является то, что, хотя <xref:System.DateTimeOffset> значения имеют определенные сведения о часовых поясах, они не поддерживают полную поддержку часовых поясов. Хотя смещение <xref:System.DateTimeOffset> значения отражает смещение часового пояса от времени в формате UTC, когда переменной <xref:System.DateTimeOffset> сначала присваивается значение, оно становится несвязанным с часовым поясом впоследствии. Поскольку оно больше не связано напрямую с распознаваемым временем, правила коррекции часовых поясов больше не будут учитываться при сложении и вычитании интервалов даты и времени.

Для иллюстрации переход на летнее время в центральном стандартном часовом поясе США выполняется в 2:00 утра. 9 марта, 2008 г. Это означает, что при прибавлении двух с половиной часов к 1:30 утра 9 марта 2008 г. центрального стандартного времени США должно получиться 5:00 утра 9 марта, 2008 г. Однако, как показано в следующем примере, результатом сложения является 4:00 утра 9 марта, 2008 г. Обратите внимание, что такой результат данной операции представляет правильный момент времени, хотя и не является временем в искомом часовом поясе (в результате не содержится ожидаемое смещение часового пояса).

[!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]

## <a name="arithmetic-operations-with-times-in-time-zones"></a>Арифметические операции со временем в часовых поясах

Класс <xref:System.TimeZoneInfo> включает ряд методов преобразования, которые автоматически применяют корректировки при преобразовании времени из одного часового пояса в другой. В число этих требований входят следующие:

- Методы <xref:System.TimeZoneInfo.ConvertTime%2A> и <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>, которые преобразуют время между двумя часовыми поясами.

- Методы <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> и <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A>, которые преобразуют время в определенном часовом поясе в формате UTC или преобразуют время в формате UTC в определенное время в определенном часовом поясе.

Дополнительные сведения см. в разделе [Преобразование времени между часовыми поясами](../../../docs/standard/datetime/converting-between-time-zones.md).

Класс <xref:System.TimeZoneInfo.ConvertTimeToUtc(System.DateTime)> не предоставляет методов, которые автоматически применяют правила коррекции при выполнении арифметических операций с датами и временем. Тем не менее, этого можно добиться, преобразовав время в часовом поясе во время в формате UTC, выполнив арифметическую операцию и преобразовав время UTC обратно во время в часовом поясе. Дополнительные сведения см. в разделе [как использовать Часовые пояса в арифметических действиях с датами и временем](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md).

Например, следующий код аналогичен предыдущему коду, в котором 2,5 часа добавлялись к 2:00 утра 9 марта, 2008 г. Тем не менее, поскольку в этом примере перед выполнением арифметических действий над датой и временем центральное стандартное время преобразуется во время в формате UTC, а затем результат преобразуется из времени UTC обратно в центральное стандартное время, полученное время соответствует переходу центрального стандартного часового пояса на летнее время.

[!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]

## <a name="see-also"></a>См. также

- [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
- [Практическое руководство. Использование часовых поясов в арифметических операциях с датами и временем](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)
