---
title: "Практическое руководство. Создание часовых поясов с правилами коррекции | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "правило коррекции [платформа .NET Framework]"
  - "часовые пояса [платформа .NET Framework], и правила коррекции"
  - "часовые пояса [платформа .NET Framework], создание"
ms.assetid: c52ef192-13a9-435f-8015-3b12eae8c47c
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Создание часовых поясов с правилами коррекции
Точные сведения о часовом поясе, необходимые приложению, могут отсутствовать в конкретной системе по нескольким причинам:  
  
-   Часовой пояс не был определен в реестре локальной системы.  
  
-   Данные о часовом поясе были изменены или удалены из реестра.  
  
-   Для часового пояса отсутствуют точные сведения о правилах коррекции часового пояса для конкретного исторического периода.  
  
 В этих случаях можно вызвать метод <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>, чтобы определить часовой пояс, необходимый приложению.  Можно использовать перегрузки этого метода для создания часовых поясов с использованием или без использования правил коррекции.  Если для часового пояса поддерживается переход на летнее время, можно определить фиксированные или плавающие правила перехода. \(Определения этих терминов содержатся в разделе "Терминология часовых поясов" раздела [Общие сведения о часовых поясах](../../../docs/standard/datetime/time-zone-overview.md).\)  
  
> [!IMPORTANT]
>  Пользовательские часовые пояса, созданные посредством вызова метода <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>, не добавляются в реестр.  Вместо этого к ним можно получить доступ только через ссылку на объект, возвращаемую методом <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>.  
  
 В этом разделе показано, как создать часовой пояс с правилами коррекции.  Чтобы создать часовой пояс, который не поддерживает правила коррекции при переходе на летнее время, см. раздел [Практическое руководство. Создание часовых поясов без правил коррекции](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md).  
  
### Создание часового пояса с правилами коррекции  
  
1.  Для каждой коррекции \(то есть для каждого перехода со стандартного времени и обратно за определенный временной интервал\) выполните следующее:  
  
    1.  Задайте начальное время перехода для коррекции часового пояса.  
  
         Необходимо вызвать метод <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=fullName> и передать ему значение <xref:System.DateTime>, определяющее время перехода, целочисленное значение, определяющее месяц перехода, целочисленное значение, определяющее неделю, на которой происходит переход и значение <xref:System.DayOfWeek>, которое определяет день недели, когда происходит переход.  Вызов этого метода создает экземпляр объекта <xref:System.TimeZoneInfo.TransitionTime>.  
  
    2.  Задайте конечное время перехода для коррекции часового пояса.  Для этого необходимо вызвать метод <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=fullName>.  Вызов этого метода создает второй экземпляр объекта <xref:System.TimeZoneInfo.TransitionTime>.  
  
    3.  Вызовите метод <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> и передайте ему действительные начальные и конечные даты коррекции, объект <xref:System.TimeSpan>, который определяет количество времени в переходе, и два объекта <xref:System.TimeZoneInfo.TransitionTime>, которые определяют, когда происходит переход на летнее время и обратно.  Вызов этого метода создает экземпляр объекта <xref:System.TimeZoneInfo.AdjustmentRule>.  
  
    4.  Присвойте объект <xref:System.TimeZoneInfo.AdjustmentRule> массиву объектов <xref:System.TimeZoneInfo.AdjustmentRule>.  
  
2.  Определите отображаемое название часового пояса.  Отображаемое название должно соответствовать стандартному формату, в котором смещение часового пояса от универсального синхронизированного времени \(UTC\) заключается в круглые скобки, после чего следует строка, определяющая часовой пояс, один или несколько городов часового пояса, или одну или несколько стран или регионов в этом часовом поясе.  
  
3.  Определите название стандартного времени часового пояса.  Как правило, эта строка также используется в качестве идентификатора часового пояса.  
  
4.  Определите название летнего времени часового пояса.  
  
5.  Если необходимо использовать другой идентификатор, отличный от стандартного названия часового пояса, определите идентификатор часового пояса.  
  
6.  Создайте объект <xref:System.TimeSpan>, который определяет смещение часового пояса от времени UTC.  Часовые пояса со временем, которое позже времени UTC, имеют положительное смещение.  Часовые пояса со временем, опережающим время UTC, имеют отрицательное смещение.  
  
7.  Вызовите метод [TimeZoneInfo.CreateCustomTimeZone\(String, TimeSpan, String, String, String, TimeZoneInfo.AdjustmentRule\<xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=fullName> для создания нового часового пояса.  
  
## Пример  
 В следующем примере определяется центральный стандартный часовой пояс США, который содержит правила коррекции для различных интервалов времени с 1918 года по настоящее время.  
  
 [!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
 [!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]  
  
 Часовой пояс, созданный в этом примере, имеет несколько правил коррекции.  Необходимо соблюдать осторожность, чтобы действительные начальные и конечные даты одного правила коррекции не перекрывались с датами другого правила коррекции.  При наличии перекрывания создается исключение <xref:System.InvalidTimeZoneException>.  
  
 Для плавающих правил коррекции, значение 5 передается параметру `week` метода <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A>, чтобы указать, что переход происходит на последней неделе конкретного месяца.  
  
 При создании массива объектов <xref:System.TimeZoneInfo.AdjustmentRule> для использования в методе [TimeZoneInfo.CreateCustomTimeZone\(String, TimeSpan, String, String, String, TimeZoneInfo.AdjustmentRule\<xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=fullName> код мог бы инициализировать массив с размером, равным числу коррекций, создаваемых для часового пояса.  Вместо этого данный пример кода вызывает метод <xref:System.Collections.Generic.List%601.Add%2A> для добавления всех правил коррекции в универсальную коллекцию <xref:System.Collections.Generic.List%601> объектов <xref:System.TimeZoneInfo.AdjustmentRule>.  Затем код вызывает метод <xref:System.Collections.Generic.List%601.CopyTo%2A>, чтобы скопировать элементы этой коллекции в массив.  
  
 Также в примере используется метод <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> для определения коррекций, фиксированных по дате.  Это аналогично вызову метода <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A>, за исключением того, что из параметров перехода ему необходимы только время, месяц и день.  
  
 Пример можно протестировать с помощью следующего кода:  
  
 [!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
 [!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Чтобы ссылка на System.Core.dll была добавлена в проект.  
  
-   Чтобы был осуществлен импорт следующих пространств имен:  
  
     [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
     [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]  
  
## См. также  
 [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)   
 [Общие сведения о часовых поясах](../../../docs/standard/datetime/time-zone-overview.md)   
 [Практическое руководство. Создание часовых поясов без правил коррекции](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)