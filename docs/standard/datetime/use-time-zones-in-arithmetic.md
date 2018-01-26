---
title: "Как: использование часовых поясов в арифметических операций"
ms.custom: 
ms.date: 04/10/2017
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
- time zones [.NET Framework], arithmetic operations
- arithmetic operations [.NET Framework], dates and times
- dates [.NET Framework], adding and subtracting
ms.assetid: 83dd898d-1338-415d-8cd6-445377ab7871
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: bcffc98d763c125ac44c1048a7c89c8f6a1e89f1
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a>Как: использование часовых поясов в арифметических операций

Как правило, при выполнения даты и времени с помощью арифметических <xref:System.DateTime> или <xref:System.DateTimeOffset> значения, результат не отражает все правила коррекции часового пояса. Это верно, даже если часовой пояс значения даты и времени не четко идентифицируемый (например, в том случае, когда <xref:System.DateTime.Kind%2A> свойству <xref:System.DateTimeKind.Local>). В этом разделе показано, как выполнять арифметические операции над значениями даты и времени, принадлежащие к определенному часовому поясу. Результаты арифметических операций при этом будут учитывать правила коррекции часовых поясов.

### <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a>Применение правил коррекции в вычислениях с датами и временем

1. Необходимо каким-либо способом тесно связать значения даты и времени с соответствующим часовым поясом. К примеру, можно объявить структуру, которая будет содержать значение даты и времени вместе с данными о часовом поясе. В следующем примере этот подход используется для связывания <xref:System.DateTime> значение с его часовым поясом.

   [!code-csharp[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#6)]
   [!code-vb[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#6)]

2. Преобразование времени в формате UTC с помощью вызова <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> метода или <xref:System.TimeZoneInfo.ConvertTime%2A> метод.

3. Далее следует выполнить необходимые арифметические действия над временем UTC.

4. Преобразовать исходное время связаны с часовым поясом время от времени UTC, вызвав <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> метод.

## <a name="example"></a>Пример

В следующем примере к 9 марта 2008 г., 1:30 центрального стандартного времени прибавляется два часа и тридцать минут. Переход на летнее время в этом часовом поясе происходит на 30 минут позже, в 2:00 9 марта, 2008 г. Поскольку в этом примере выполнены четыре шага, описанные в предыдущем разделе, он правильно возвращает итоговое время, равное 5:00 9 марта, 2008 г.

[!code-csharp[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual8.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual8.vb#8)]

Оба <xref:System.DateTime> и <xref:System.DateTimeOffset> значения перестают быть связанными с любой часовой пояс, к которому они могут относиться. Для того чтобы арифметические действия с датами и временем выполнялись таким образом, что правила коррекции часовых поясов учитывались бы автоматически, сведения о часовом поясе, к которому относятся значения даты и времени, должны быть известны и непосредственно доступны. Это означает, что значения даты и времени должны быть тесно связаны с часовым поясом. Для того, чтобы этого добиться, существует целый ряд способов, некоторые из них перечислены ниже.

* Предположим, что все значения времени, используемые в приложении, принадлежат к определенному часовому поясу. Хотя этот подход вполне применим во многих случаях, его гибкость и, возможно, переносимость имеют ограничения.

* Следует определить тип, в котором значение даты и времени тесно связано с часовым поясом, включив эти данные в состав типа в качестве полей. Этот подход используется в примере кода — в нем определяется структура для хранения даты, времени и часового пояса в двух полях структуры.

В примере иллюстрируется выполнять арифметические операции над <xref:System.DateTime> значений, чтобы результат применения правил коррекции часового пояса. Тем не менее <xref:System.DateTimeOffset> значения можно использовать так же просто. В следующем примере показано, как может быть адаптирован для использования кода в исходном примере <xref:System.DateTimeOffset> вместо <xref:System.DateTime> значения.

[!code-csharp[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#7)]

Обратите внимание, что если эта операция выполняется над <xref:System.DateTimeOffset> значение без сначала преобразования его в формат UTC, то результат будет соответствовать нужный момент времени, но его смещение не будет отражать, заданном часовом поясе по времени.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

* Чтобы ссылка на System.Core.dll была добавлена в проект.

* Что <xref:System> импортировать пространство имен с `using` инструкции (обязательно в коде C#).

## <a name="see-also"></a>См. также

[Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
[выполнения арифметических операций с датами и временем](../../../docs/standard/datetime/performing-arithmetic-operations.md)
