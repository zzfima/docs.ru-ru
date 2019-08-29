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
ms.openlocfilehash: 01314c160fc531f5c97a1369c8444dce7f590d53
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106617"
---
# <a name="performing-arithmetic-operations-with-dates-and-times"></a>Выполнение арифметических операций с датами и временем

Несмотря на то, что <xref:System.DateTimeOffset> структуры ипредоставляютчлены,выполняющиеарифметическиеоперациисихзначениями,результатыарифметическихоперацийсильноотличаются.<xref:System.DateTime> В этом разделе рассматриваются эти различия, приводятся сведения о них в степени осведомленности о часовых поясах в данных даты и времени, а также рассматривается выполнение операций с полной поддержкой часовых поясов с использованием данных даты и времени.

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a>Сравнения и арифметические операции со значениями типа DateTime

<xref:System.DateTime.Kind%2A?displayProperty=nameWithType> Свойство позволяетназначитьзначениедатеивремени,чтобыуказать,представляетлиономестноевремя,времявформатеUTCиливремявнеопределенномчасовом<xref:System.DateTimeKind> поясе. Однако эти ограниченные сведения о часовом поясе игнорируются при сравнении или выполнении арифметических операций с датами и временем для <xref:System.DateTimeKind> значений. Это демонстрируется в следующем примере, где текущее местное время сравнивается с текущим временем в формате UTC.

[!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]

<xref:System.DateTime.CompareTo%28System.DateTime%29> Метод сообщает, что местное время предшествует (или меньше) времени UTC, а операция вычитания указывает, что разница между временем в формате UTC и местным временем для системы в США США составляет семь часов. Тем не менее, поскольку эти значения дают различные представления одного и того же момента времени, в данном случае очевидно, что причина этого различия целиком кроется в смещении местного часового пояса относительно времени в формате UTC.

Более того <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> , свойство не влияет на результаты, <xref:System.DateTime.Kind> возвращаемые методами сравнения и арифметическими операциями (так как сравнение двух идентичных точек во времени указывает), хотя это может повлиять на интерпретацию этих результатов. Например:

- Результат выполнения любой арифметической операции с двумя значениями даты и времени, свойства <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> которых равны значению <xref:System.DateTimeKind> фактического интервала времени между двумя значениями. Аналогичным образом результат сравнения двух таких значений даты и времени будет точно отражать соотношение между временами.

- Результат любой операции арифметического или сравнения, выполняемой с двумя значениями даты и времени <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> , свойства которых <xref:System.DateTimeKind> равны или в двух значениях даты и времени <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> с различными значениями свойств, отражает разницу в времени. между двумя значениями.

- Арифметические операции или операции сравнения, выполняемые над местными значениями даты и времени, не учитывают допустимость или недопустимость конкретных значений; не учитывают они и какие-либо правила коррекции, необходимые при переводе местного часового пояса на зимнее или летнее время.

- В результат любой операции, сравнивающей или вычисляющей разницу между временем в формате UTC и местным временем, входит временной интервал, равный смещению местного часового пояса относительно времени в формате UTC.

- Любая операция, которая сравнивает или вычисляет разницу между неуказанным временем и временем в формате UTC или местным временем, соответствует простому времени. Различия между часовыми поясами не учитываются, и в результате не отражено применение правил коррекции часовых поясов.

- Любая операция, которая сравнивает или вычисляет разницу между двумя неуказанными значениями времени, может включать неизвестный интервал, который отражает временную разницу между двумя различными часовыми поясами.

Существует множество ситуаций, в которых разницы часовых поясов не влияют на вычисления даты и времени (для некоторых из них см. раздел [Выбор между DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)) или в контексте данных даты и времени. Определяет значение операций сравнения или арифметической операции.

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a>Сравнения и арифметические операции со значениями DateTimeOffset

<xref:System.DateTimeOffset> Значение включает не только дату и время, но и смещение, которое однозначно определяет эту дату и время относительно времени в формате UTC. Это дает возможность определить равенство несколько иначе, чем для <xref:System.DateTimeOffset> значений. В то время как <xref:System.DateTimeOffset> значенияравны,еслиониимеютодинаковыезначениядатыивремени,значенияравны,еслиониссылаютсянаодинитотжемоментвремени.<xref:System.DateTime> Это делает <xref:System.DateTimeOffset> значение более точным и меньшим при необходимости интерпретации при использовании в сравнениях и в большинстве арифметических операций, определяющих интервал между двумя датами и временем. В следующем примере, который является <xref:System.DateTimeOffset> аналогом предыдущего примера, сравниваемого с локальным и UTC <xref:System.DateTimeOffset> -значениями, показано различие в поведении.

[!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]

В этом примере <xref:System.DateTimeOffset.CompareTo%2A> метод указывает, что текущее местное время и текущее время в формате UTC равны, а <xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)> вычитание значений указывает, что разница <xref:System.TimeSpan.Zero?displayProperty=nameWithType>между двумя значениями времени равна.

Главным ограничением использования значений <xref:System.DateTimeOffset> в арифметических операциях с датами и временем <xref:System.DateTimeOffset> является то, что хотя значения имеют определенные Часовые пояса, они не поддерживают полную поддержку часовых поясов. Хотя смещение <xref:System.DateTimeOffset> значения отражает смещение часового пояса от времени в формате UTC, когда переменной сначала присваивается значение, она становится несвязанной с часовым поясом впоследствии. <xref:System.DateTimeOffset> Поскольку оно больше не связано напрямую с распознаваемым временем, правила коррекции часовых поясов больше не будут учитываться при сложении и вычитании интервалов даты и времени.

Пример: переход на летнее время в зоне центрального стандартного времени США происходит в 2:00 утра 9 марта, 2008 г. Это означает, что при прибавлении двух с половиной часов к 1:30 утра 9 марта 2008 г. центрального стандартного времени США должно получиться 5:00 утра 9 марта, 2008 г. Однако, как показано в следующем примере, результатом сложения является 4:00 утра 9 марта, 2008 г. Обратите внимание, что такой результат данной операции представляет правильный момент времени, хотя и не является временем в искомом часовом поясе (в результате не содержится ожидаемое смещение часового пояса).

[!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]

## <a name="arithmetic-operations-with-times-in-time-zones"></a>Арифметические операции со временем в часовых поясах

<xref:System.TimeZoneInfo> Класс включает ряд методов преобразования, которые автоматически применяют корректировки при преобразовании времени из одного часового пояса в другой. следующие основные параметры.

- Методы <xref:System.TimeZoneInfo.ConvertTime%2A> и<xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A> , которые преобразуют время между любыми двумя часовыми поясами.

- Методы <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> и<xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> , которые преобразуют время в определенном часовом поясе в формате UTC или преобразуют время в формате UTC в определенный часовой пояс.

Дополнительные сведения см. в разделе [Преобразование времени между](../../../docs/standard/datetime/converting-between-time-zones.md)часовыми поясами.

<xref:System.TimeZoneInfo.ConvertTimeToUtc(System.DateTime)> Класс не предоставляет методы, которые автоматически применяют правила коррекции при выполнении арифметических действий с датами и временем. Тем не менее, этого можно добиться, преобразовав время в часовом поясе во время в формате UTC, выполнив арифметическую операцию и преобразовав время UTC обратно во время в часовом поясе. Подробную информацию см. в разделе [Практическое руководство. Используйте Часовые пояса в арифметических операциях](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)с датами и временем.

Например, следующий код аналогичен предыдущему коду, в котором 2,5 часа добавлялись к 2:00 утра 9 марта, 2008 г. Тем не менее, поскольку в этом примере перед выполнением арифметических действий над датой и временем центральное стандартное время преобразуется во время в формате UTC, а затем результат преобразуется из времени UTC обратно в центральное стандартное время, полученное время соответствует переходу центрального стандартного часового пояса на летнее время.

[!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]

## <a name="see-also"></a>См. также

- [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
- [Практическое руководство. Использование часовых поясов в арифметических операциях с датами и временем](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)
