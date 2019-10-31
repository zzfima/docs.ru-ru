---
title: Как использовать Часовые пояса в арифметических действиях с датами и временем
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], arithmetic operations
- arithmetic operations [.NET Framework], dates and times
- dates [.NET Framework], adding and subtracting
ms.assetid: 83dd898d-1338-415d-8cd6-445377ab7871
ms.openlocfilehash: 1acd53fad6b0ab173f855850353339190ebdd893
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132539"
---
# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a>Как использовать Часовые пояса в арифметических действиях с датами и временем

Обычно при выполнении арифметических операций с датами и временем с помощью значений <xref:System.DateTime> или <xref:System.DateTimeOffset> в результате не будут отражены правила коррекции часовых поясов. Это справедливо, даже если часовой пояс значения даты и времени четко идентифицируем (например, если свойство <xref:System.DateTime.Kind%2A> имеет значение <xref:System.DateTimeKind.Local>). В этом разделе показано, как выполнять арифметические операции с значениями даты и времени, относящимися к определенному часовому поясу. Результаты арифметических операций при этом будут учитывать правила коррекции часовых поясов.

### <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a>Применение правил коррекции в вычислениях с датами и временем

1. Необходимо каким-либо способом тесно связать значения даты и времени с соответствующим часовым поясом. К примеру, можно объявить структуру, которая будет содержать значение даты и времени вместе с данными о часовом поясе. В следующем примере этот подход используется для связывания значения <xref:System.DateTime> со своим часовым поясом.

   [!code-csharp[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#6)]
   [!code-vb[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#6)]

2. Преобразуйте время в время в формате UTC, вызвав либо метод <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A>, либо метод <xref:System.TimeZoneInfo.ConvertTime%2A>.

3. Далее следует выполнить необходимые арифметические действия над временем UTC.

4. Преобразуйте время из времени UTC в часовой пояс исходного времени, вызвав метод <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>.

## <a name="example"></a>Пример

В следующем примере к 9 марта 2008 г., 1:30 центрального стандартного времени прибавляется два часа и тридцать минут. Переход на летнее время в этом часовом поясе происходит на 30 минут позже, в 2:00 9 марта, 2008 г. Поскольку в этом примере выполнены четыре шага, описанные в предыдущем разделе, он правильно возвращает итоговое время, равное 5:00 9 марта, 2008 г.

[!code-csharp[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual8.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual8.vb#8)]

Значения <xref:System.DateTime> и <xref:System.DateTimeOffset> не связаны ни с одним часовым поясом, к которому они могут принадлежать. Для того чтобы арифметические действия с датами и временем выполнялись таким образом, что правила коррекции часовых поясов учитывались бы автоматически, сведения о часовом поясе, к которому относятся значения даты и времени, должны быть известны и непосредственно доступны. Это означает, что значения даты и времени должны быть тесно связаны с часовым поясом. Для того, чтобы этого добиться, существует целый ряд способов, некоторые из них перечислены ниже.

- Предположим, что все значения времени, используемые в приложении, принадлежат к определенному часовому поясу. Хотя этот подход вполне применим во многих случаях, его гибкость и, возможно, переносимость имеют ограничения.

- Следует определить тип, в котором значение даты и времени тесно связано с часовым поясом, включив эти данные в состав типа в качестве полей. Этот подход используется в примере кода — в нем определяется структура для хранения даты, времени и часового пояса в двух полях структуры.

В примере показано, как выполнять арифметические операции с <xref:System.DateTime> значениями, чтобы к результату были применены правила коррекции часовых поясов. Однако <xref:System.DateTimeOffset> значения можно использовать так же просто. В следующем примере показано, как можно адаптировать код в исходном примере для использования <xref:System.DateTimeOffset> вместо <xref:System.DateTime> значений.

[!code-csharp[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#7)]

Обратите внимание, что если это сложение выполняется просто со значением <xref:System.DateTimeOffset> без предварительного преобразования его в формат UTC, результат отражает правильный момент времени, но его смещение не отражается на назначенном часовом поясе для этого времени.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

- , Что <xref:System> пространство имен должно быть импортировано с помощью оператора `using` C# (требуется в коде).

## <a name="see-also"></a>См. также

- [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
- [Выполнение арифметических операций с датами и временем](../../../docs/standard/datetime/performing-arithmetic-operations.md)
