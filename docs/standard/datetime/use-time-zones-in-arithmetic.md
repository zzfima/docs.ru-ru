---
title: 'Практическое: использование часовых поясов в арифметических операций'
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c9f7b2623b4ed766fb44b46c3f54caa962c07eb
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "44041526"
---
# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a>Практическое: использование часовых поясов в арифметических операций

Как правило, при выполнения дату и время арифметических <xref:System.DateTime> или <xref:System.DateTimeOffset> значения, результат не отражают правила коррекции часовых поясов. Это верно, даже если часовой пояс значения даты и времени четко определен (например, в том случае, когда <xref:System.DateTime.Kind%2A> свойству <xref:System.DateTimeKind.Local>). В этом разделе показано, как выполнять арифметические операции над значениями даты и времени, которые принадлежат к определенному часовому поясу. Результаты арифметических операций при этом будут учитывать правила коррекции часовых поясов.

### <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a>Применение правил коррекции в вычислениях с датами и временем

1. Необходимо каким-либо способом тесно связать значения даты и времени с соответствующим часовым поясом. К примеру, можно объявить структуру, которая будет содержать значение даты и времени вместе с данными о часовом поясе. В следующем примере используется этот подход, чтобы связать <xref:System.DateTime> значение с его часовым поясом.

   [!code-csharp[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#6)]
   [!code-vb[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#6)]

2. Преобразования времени в формате UTC в формате UTC с помощью вызова <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> метод или <xref:System.TimeZoneInfo.ConvertTime%2A> метод.

3. Далее следует выполнить необходимые арифметические действия над временем UTC.

4. Преобразовать время от времени UTC в исходное время связаны с часовым поясом, вызвав <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> метод.

## <a name="example"></a>Пример

В следующем примере к 9 марта 2008 г., 1:30 центрального стандартного времени прибавляется два часа и тридцать минут. Переход на летнее время в этом часовом поясе происходит на 30 минут позже, в 2:00 9 марта, 2008 г. Поскольку в этом примере выполнены четыре шага, описанные в предыдущем разделе, он правильно возвращает итоговое время, равное 5:00 9 марта, 2008 г.

[!code-csharp[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual8.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual8.vb#8)]

Оба <xref:System.DateTime> и <xref:System.DateTimeOffset> значения являются отделяется от любой часовой пояс, к которому они могут относиться. Для того чтобы арифметические действия с датами и временем выполнялись таким образом, что правила коррекции часовых поясов учитывались бы автоматически, сведения о часовом поясе, к которому относятся значения даты и времени, должны быть известны и непосредственно доступны. Это означает, что значения даты и времени должны быть тесно связаны с часовым поясом. Для того, чтобы этого добиться, существует целый ряд способов, некоторые из них перечислены ниже.

* Предположим, что все значения времени, используемые в приложении, принадлежат к определенному часовому поясу. Хотя этот подход вполне применим во многих случаях, его гибкость и, возможно, переносимость имеют ограничения.

* Следует определить тип, в котором значение даты и времени тесно связано с часовым поясом, включив эти данные в состав типа в качестве полей. Этот подход используется в примере кода — в нем определяется структура для хранения даты, времени и часового пояса в двух полях структуры.

В примере способов выполнения арифметических операций с <xref:System.DateTime> значений, чтобы результат применения правила коррекции часового пояса. Тем не менее <xref:System.DateTimeOffset> значения могут использоваться в легко. В следующем примере показано, как в примере исходного кода могут быть адаптированы к использованию <xref:System.DateTimeOffset> вместо <xref:System.DateTime> значения.

[!code-csharp[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#7)]

Обратите внимание, что если эта операция выполняется над <xref:System.DateTimeOffset> значение без сначала преобразуется в формат UTC, результат будет соответствовать правильному моменту времени, но его смещение не соответствующим образом изменит заданный часовой пояс для времени.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

* Чтобы добавить в проект ссылку на библиотеку System.Core.dll.

* Что <xref:System> импорт пространства имен с помощью `using` инструкции (обязательно в коде C#).

## <a name="see-also"></a>См. также

* [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
* [Выполнение арифметических операций с датами и временем](../../../docs/standard/datetime/performing-arithmetic-operations.md)
