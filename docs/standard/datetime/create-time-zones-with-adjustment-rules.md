---
title: "Как: создание часовых поясов с правилами коррекции"
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
- time zones [.NET Framework], creating
- time zones [.NET Framework], and adjustment rules
- adjustment rule [.NET Framework]
ms.assetid: c52ef192-13a9-435f-8015-3b12eae8c47c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: eddc1d400f5f63cb2790fc4c660b70ebfdd0efc1
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-create-time-zones-with-adjustment-rules"></a>Как: создание часовых поясов с правилами коррекции

Точные сведения о часовом поясе, которые требуются для приложения не могут находиться в данной системе по следующим причинам:

* Часовой пояс никогда не был определен в реестре локальной системы.

* Данные о часовом поясе, изменен или удален из реестра.

* Часовой пояс не имеет точные сведения о коррекции часового пояса для конкретного исторического периода.

В этих случаях можно вызвать <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метод, чтобы определить часовой пояс, необходимые для приложения. Создание с или без правил коррекции часового пояса, можно использовать перегрузки этого метода. Если часовой пояс поддерживает летнее время, можно определить с помощью либо правил коррекции фиксированной или плавающей. (Для определения этих терминов см. в разделе «Терминология часовых поясов» [Общие сведения о часовом поясе](../../../docs/standard/datetime/time-zone-overview.md).)

> [!IMPORTANT]
> Пользовательские часовые пояса путем вызова <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метод не добавляются в реестр. Вместо этого они может осуществляться только через ссылку на объект, возвращаемый <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> вызова метода.

В этом разделе показано, как создать часовой пояс с правилами коррекции. Чтобы создать часовой пояс, который не поддерживает правила коррекции для летнего времени, см. [как: создание часовых поясов без правил коррекции](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md).

### <a name="to-create-a-time-zone-with-floating-adjustment-rules"></a>Для создания часовых поясов с правилами коррекции

1. Для каждой коррекции (то есть для каждого перехода со и обратно на стандартное время, за определенный временной интервал) выполните следующие действия:

    1. Определите начальное время перехода для коррекции часового пояса.

       Необходимо вызвать <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> метод и передать его <xref:System.DateTime> значение, определяющее время перехода, целочисленное значение, определяющее месяц перехода, целочисленное значение, определяющее неделю, на котором происходит переход и <xref:System.DayOfWeek> значение, определяющее день недели, в который происходит переход. Вызов этого метода создает <xref:System.TimeZoneInfo.TransitionTime> объекта.

    2. Задайте конечное время перехода для коррекции часового пояса. Это необходимо вызвать <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> метод. Вызов этого метода создает второй экземпляр <xref:System.TimeZoneInfo.TransitionTime> объекта.

    3. Вызовите <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> метод и передайте ему действительные начальные и конечные даты коррекции, <xref:System.TimeSpan> объект, который определяет количество времени в переходе и два <xref:System.TimeZoneInfo.TransitionTime> объектами, которые определяют, когда переход с летнее время время следовать. Вызов этого метода создает <xref:System.TimeZoneInfo.AdjustmentRule> объекта.

    4. Назначьте <xref:System.TimeZoneInfo.AdjustmentRule> объект в массив <xref:System.TimeZoneInfo.AdjustmentRule> объектов.

2. Определите отображаемое имя часового пояса. Отображаемое имя соответствует стандартному формату, в котором смещение часового пояса от времени в формате UTC заключены в круглые скобки, после чего следует строка, определяющая часовой пояс, один или несколько городов, в часовой пояс или один или несколько частей в курс Книга операций или области в часовом поясе.

3. Укажите имя для зимнего времени часового пояса. Как правило эта строка также используется как идентификатор часового пояса.

4. Определите название летнего времени часового пояса.

5. Если вы хотите использовать другой идентификатор, чем стандартное имя часового пояса, определите идентификатор часового пояса.

6. Создать экземпляр <xref:System.TimeSpan> объект, который определяет смещение часового пояса от времени UTC. Часовые пояса со временем, которые позже времени UTC, имеют положительное смещение. Часовые пояса со временем, предшествующих UTC, имеют отрицательное смещение.

7. Вызовите <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> метод для создания нового часового пояса.

## <a name="example"></a>Пример

В следующем примере определяется центральный стандартный часовой пояс для США, который содержит правила коррекции для различных интервалов времени с 1918 к текущей.

[!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
[!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]

Часовой пояс, созданный в этом примере есть несколько правил коррекции. Чтобы убедиться, что действительные начальные и конечные даты одного правила коррекции не перекрывались с датами другого правила коррекции необходимо соблюдать осторожность. При наличии перекрытия <xref:System.InvalidTimeZoneException> возникает исключение.

Для плавающих правил коррекции, значение 5 передается `week` параметр <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> метод для указания, что переход происходит на за последнюю неделю, месяц.

При создании массива <xref:System.TimeZoneInfo.AdjustmentRule> объектов для использования в <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> вызова метода, код может инициализировать массив с размером, равным числу коррекций должны быть созданы для часового пояса. Вместо этого данный пример кода вызывает <xref:System.Collections.Generic.List%601.Add%2A> метод для добавления всех правил коррекции универсальный <xref:System.Collections.Generic.List%601> коллекцию <xref:System.TimeZoneInfo.AdjustmentRule> объектов. Затем код вызывает <xref:System.Collections.Generic.List%601.CopyTo%2A> метод, чтобы скопировать элементы этой коллекции в массив.

В примере также используется <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> метод для определения корректировки фиксированной даты. Это аналогично вызову <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> за исключением того, что он требует только время, месяц и день параметров перехода.

Пример можно протестировать с помощью следующего кода:

[!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
[!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

* Чтобы ссылка на System.Core.dll была добавлена в проект.

* Что импортируется следующие пространства имен:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>См. также

[Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
[Общие сведения о часовом поясе](../../../docs/standard/datetime/time-zone-overview.md)
[как: создание часовых поясов без правил коррекции](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)
