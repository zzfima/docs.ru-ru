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
ms.openlocfilehash: 0db0331620da8337930bfacf5d1bbd9913647afa
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344174"
---
# <a name="performing-arithmetic-operations-with-dates-and-times"></a>Выполнение арифметических операций с датами и временем

Хотя <xref:System.DateTime> и <xref:System.DateTimeOffset> структуры предоставляют членам, которые выполняют арифметические операции по их значениям, результаты арифметических операций очень разные. В этой теме рассматриваются эти различия, они соотносятся со степенями осведомленности о датах и времени и обсуждаются, как выполнять полностью операции по поддержанию часового пояса с использованием данных о дате и времени.

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a>Сравнения и арифметические операции со значениями DateTime

Свойство <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> позволяет <xref:System.DateTimeKind> назначить значение к дате и времени, чтобы указать, представляет ли оно местное время, скоординированное универсальное время (UTC) или время в неустановленном часовом поясе. Однако эта информация ограниченного часового пояса игнорируется при сравнении или выполнении арифметики даты и времени значений. <xref:System.DateTimeKind> Это демонстрируется в следующем примере, где текущее местное время сравнивается с текущим временем в формате UTC.

[!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]

Метод <xref:System.DateTime.CompareTo%28System.DateTime%29> показывает, что местное время раньше (меньше) времени в поясе UTC, а операция вычитания свидетельствует о том, что разница между временем в поясе UTC и местным временем для систем в тихоокеанском стандартном часовом поясе США составляет семь часов. Но поскольку эти два значения обеспечивают различные представления одной точки времени, в данном случае ясно, что временной интервал полностью связан с смещением локального часового пояса от UTC.

В более <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> общем плане свойство не <xref:System.DateTime.Kind> влияет на результаты, возвращенные путем сравнения и арифметических методов (как показывает сравнение двух одинаковых точек времени), хотя это может повлиять на интерпретацию этих результатов. Пример:

- Результат любой арифметической операции, выполненной на <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> двух значениях даты и времени, свойства которых равны, <xref:System.DateTimeKind> отражает фактический временной интервал между двумя значениями. Аналогичным образом результат сравнения двух таких значений даты и времени будет точно отражать соотношение между временами.

- Результат любой арифметической или сравнительных операций, выполняемой <xref:System.DateTimeKind> на двух значениях даты и <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> времени, свойства которых <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> равны или на двух значениях даты и времени с различными значениями свойств, отражают разницу в часовом времени между двумя значениями.

- Арифметические операции или операции сравнения, выполняемые над местными значениями даты и времени, не учитывают допустимость или недопустимость конкретных значений; не учитывают они и какие-либо правила коррекции, необходимые при переводе местного часового пояса на зимнее или летнее время.

- В результат любой операции, сравнивающей или вычисляющей разницу между временем в формате UTC и местным временем, входит временной интервал, равный смещению местного часового пояса относительно времени в формате UTC.

- Любая операция, которая сравнивает или вычисляет разницу между неуказанным временем и временем в формате UTC или местным временем, соответствует простому времени. Различия между часовыми поясами не учитываются, и в результате не отражено применение правил коррекции часовых поясов.

- Любая операция, которая сравнивает или вычисляет разницу между двумя неуказанными значениями времени, может включать неизвестный интервал, который отражает временную разницу между двумя различными часовыми поясами.

Есть много сценариев, в которых разница в часовом поясе не влияет на расчеты даты и времени (для обсуждения некоторых из них [см. Выбор между DateTime, DateTimeOffset, TimeSpan и Time'oneInfo)](../../../docs/standard/datetime/choosing-between-datetime.md)или в которых контекст данных о дате и времени определяет значение сравнения или арифметических операций.

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a>Сравнения и арифметические операции со значениями DateTimeOffset

Значение <xref:System.DateTimeOffset> включает в себя не только дату и время, но и смещение, которое однозначно определяет эту дату и время по отношению к UTC. Это позволяет определить равенство несколько иначе, чем для <xref:System.DateTimeOffset> ценностей. В <xref:System.DateTime> то время как значения равны, если они <xref:System.DateTimeOffset> имеют одинаковое значение даты и времени, значения равны, если они оба относятся к одной и той же точке времени. Это делает <xref:System.DateTimeOffset> значение более точным и менее нуждающимся в интерпретации при использовании в сравнениях и в большинстве арифметических операций, которые определяют интервал между двумя датами и временем. Следующий пример, <xref:System.DateTimeOffset> эквивалентный предыдущему примеру, который <xref:System.DateTimeOffset> сравнивал локальные значения и значения UTC, иллюстрирует эту разницу в поведении.

[!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]

В этом примере <xref:System.DateTimeOffset.CompareTo%2A> метод указывает, что текущее местное время и текущее <xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)> время UTC равны, а <xref:System.TimeSpan.Zero?displayProperty=nameWithType>вычитание значений указывает на то, что разница между двумя разами .

Главное ограничение <xref:System.DateTimeOffset> использования значений в арифметике <xref:System.DateTimeOffset> даты и времени состоит в том, что, хотя значения имеют некоторую осведомленность о часовом поясе, они не в полной мере осведомлены о часовом поясе. Хотя <xref:System.DateTimeOffset> смещение значения отражает смещение часового пояса <xref:System.DateTimeOffset> от UTC, когда переменная сначала присваиваетзначение значение, оно становится отмежеванным от часового пояса после этого. Поскольку оно больше не связано напрямую с распознаваемым временем, правила коррекции часовых поясов больше не будут учитываться при сложении и вычитании интервалов даты и времени.

Чтобы проиллюстрировать, переход к летнее время в центральном часовом поясе США происходит в 2:00 утра. 9 марта, 2008 г. Это означает, что при прибавлении двух с половиной часов к 1:30 утра 9 марта 2008 г. центрального стандартного времени США должно получиться 5:00 утра 9 марта, 2008 г. Однако, как показано в следующем примере, результатом сложения является 4:00 утра 9 марта, 2008 г. Обратите внимание, что результат этой операции действительно представляет собой правильный момент времени, хотя это не время в часовом поясе, в котором мы заинтересованы (то есть, он не имеет ожидаемого смещения часового пояса).

[!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]

## <a name="arithmetic-operations-with-times-in-time-zones"></a>Арифметические операции со временем в часовых поясах

Класс <xref:System.TimeZoneInfo> включает в себя ряд методов преобразования, которые автоматически применяют сярепритки при преобразовании времени из одного часового пояса в другой. следующие основные параметры.

- И <xref:System.TimeZoneInfo.ConvertTime%2A> <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A> методы, которые преобразуют время между любыми двумя часовых пояса.

- <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> Методы <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> и методы, которые преобразуют время в определенном часовом поясе в UTC или преобразуют UTC в время в определенном часовом поясе.

Для получения подробной информации [см.](../../../docs/standard/datetime/converting-between-time-zones.md)

Класс <xref:System.TimeZoneInfo> не предоставляет никаких методов, которые автоматически применяют правила корректировки при выполнении арифметики даты и времени. Тем не менее, этого можно добиться, преобразовав время в часовом поясе во время в формате UTC, выполнив арифметическую операцию и преобразовав время UTC обратно во время в часовом поясе. Для получения подробной информации, [см. Как: Использование часовых поясов в дату и время арифметики](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md).

Например, следующий код аналогичен предыдущему коду, в котором 2,5 часа добавлялись к 2:00 утра 9 марта, 2008 г. Тем не менее, поскольку в этом примере перед выполнением арифметических действий над датой и временем центральное стандартное время преобразуется во время в формате UTC, а затем результат преобразуется из времени UTC обратно в центральное стандартное время, полученное время соответствует переходу центрального стандартного часового пояса на летнее время.

[!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]

## <a name="see-also"></a>См. также

- [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
- [Практическое руководство. Использование часовых поясов в арифметических операциях с датами и временем](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)
