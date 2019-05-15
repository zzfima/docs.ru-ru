---
title: Практическое руководство. Создание часовых поясов с правилами коррекции
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], creating
- time zones [.NET Framework], and adjustment rules
- adjustment rule [.NET Framework]
ms.assetid: c52ef192-13a9-435f-8015-3b12eae8c47c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: face995dbd5ba4b0b12e80bcef10a90b46c093ff
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586408"
---
# <a name="how-to-create-time-zones-with-adjustment-rules"></a>Практическое руководство. Создание часовых поясов с правилами коррекции

Точные сведения о часовом поясе, которые требуются для приложения может отсутствовать в конкретной системе по следующим причинам:

* Часовой пояс никогда не был определен в локального системного реестра.

* Данные о часовом поясе, изменен или удален из реестра.

* Часовой пояс не поддерживает точные сведения о коррекции часового пояса для конкретного исторического периода.

В этих случаях можно вызвать <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метод для определения часового пояса, необходимой для приложения. Можно использовать перегрузки этого метода, создаваемого с или без правил коррекции часового пояса. Если часовой пояс поддерживает летнее время, можно определить с помощью либо правила коррекции fixed или с плавающей запятой. (Для определения этих терминов см. в разделе «Терминология часовых поясов» в [Общие сведения о часовом поясе](../../../docs/standard/datetime/time-zone-overview.md).)

> [!IMPORTANT]
> Пользовательский часовой пояс, созданных вызывающими <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метод не добавляются в реестр. Вместо этого они может осуществляться только через ссылку на объект, возвращаемый <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> вызова метода.

В этом разделе показано, как создание часовых поясов с правилами коррекции. Чтобы создать часовой пояс, который не поддерживает правил коррекции летнего времени, см. в разделе [как: Создание часовых поясов без правил коррекции](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md).

### <a name="to-create-a-time-zone-with-floating-adjustment-rules"></a>Для создания часовых поясов с правилами коррекции

1. Для каждой коррекции (то есть, для каждого перехода со и обратно на стандартное время, через указанный интервал времени) выполните следующие действия:

    1. Определите начальное время перехода для коррекции часового пояса.

       Необходимо вызвать <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> метод и передать его <xref:System.DateTime> значение, определяющее время перехода, целочисленное значение, которое определяет месяц перехода, целочисленное значение, определяющее неделю, на котором происходит переход и <xref:System.DayOfWeek> значение, определяющее день недели, на котором происходит переход. Вызов этого метода создает <xref:System.TimeZoneInfo.TransitionTime> объекта.

    2. Определите конечное время перехода для коррекции часового пояса. Это необходимо, чтобы вызвать <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> метод. Вызов этого метода создает второй экземпляр <xref:System.TimeZoneInfo.TransitionTime> объекта.

    3. Вызовите <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> метод и передать его начала и окончания коррекции, <xref:System.TimeSpan> объект, который определяет количество времени в переходе, а два <xref:System.TimeZoneInfo.TransitionTime> объектами, которые определяют, когда переход с летнее время время относиться. Вызов этого метода создает <xref:System.TimeZoneInfo.AdjustmentRule> объекта.

    4. Назначить <xref:System.TimeZoneInfo.AdjustmentRule> объект в массив <xref:System.TimeZoneInfo.AdjustmentRule> объектов.

2. Определите отображаемое имя часового пояса. Отображаемое имя соответствует стандартному формату, в котором смещение часового пояса от времени в формате UTC, заключенный в круглые скобки и сопровождается строку, которая определяет часовой пояс, один или несколько городов в часовой пояс, или один или несколько из частей в курс заданий или области в часовом поясе.

3. Определите имя для зимнего времени часового пояса. Как правило эта строка также используется как идентификатор часового пояса.

4. Определите имя летнего времени текущего часового пояса.

5. Если вы хотите использовать другой идентификатор, чем стандартное имя часового пояса, определите идентификатор часового пояса.

6. Создать экземпляр <xref:System.TimeSpan> объект, который определяет смещение часового пояса от времени UTC. Часовые пояса со временем, которые прибыли позже, чем UTC, имеют положительное смещение. Часовые пояса со временем, предшествующих UTC, имеют отрицательное смещение.

7. Вызовите <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> метод для создания экземпляра нового часового пояса.

## <a name="example"></a>Пример

В следующем примере определяется стандартного центрального часовой пояс для США, который включает в себя правила коррекции для различных интервалов времени с 1918 по текущую.

[!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
[!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]

Часовой пояс, созданные в этом примере имеет несколько правил коррекции. Чтобы убедиться, что действующие даты начала и окончания одного правила коррекции не будут перекрываться с датами другого правила коррекции необходимо соблюдать осторожность. При наличии перекрытия <xref:System.InvalidTimeZoneException> возникает исключение.

Для плавающие правила коррекции, значение 5 передается `week` параметр <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> метод, чтобы указать, что переход происходит на последней недели определенного месяца.

При создании массива <xref:System.TimeZoneInfo.AdjustmentRule> объектов для использования в <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> вызова метода, код может инициализировать массив до размера, требуемого на число корректировки, создаваемых для часового пояса. Вместо этого данный пример кода вызывает <xref:System.Collections.Generic.List%601.Add%2A> метод для добавления каждого правила коррекции универсальный <xref:System.Collections.Generic.List%601> коллекцию <xref:System.TimeZoneInfo.AdjustmentRule> объектов. Затем код вызывает <xref:System.Collections.Generic.List%601.CopyTo%2A> метод копирования членов этой коллекции в массив.

В примере также используется <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> метод для определения корректировки фиксированной датой. Это аналогично вызову <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> за тем исключением, что он требует только время, месяц и день из параметров перехода.

Пример можно проверить при помощи следующего кода:

[!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
[!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

* Что импортируется следующие пространства имен:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>См. также

- [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
- [Общие сведения о часовых поясах](../../../docs/standard/datetime/time-zone-overview.md)
- [Практическое руководство. Создание часовых поясов без правил коррекции](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)
