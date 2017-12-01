---
title: "Практическое руководство. Отображение дат в календарях, отличных от григорианского"
ms.custom: 
ms.date: 03/30/2017
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
- formatting [.NET Framework], dates
- dates [.NET Framework], formatting
- calendars [.NET Framework], displaying dates
- displaying date and time data
ms.assetid: ed324eff-4aff-4a76-b6c0-04e6c0d8f5a9
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a79860091e549dcf4eaa7090947f9506eceb6119
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-display-dates-in-non-gregorian-calendars"></a>Практическое руководство. Отображение дат в календарях, отличных от григорианского
<xref:System.DateTime> И <xref:System.DateTimeOffset> типы используют григорианского календаря в качестве календаря по умолчанию. Это означает, что вызов метода `ToString` для значения даты и времени выведет строковое представление даты и времени по григорианскому календарю даже в том случае, если значение даты и времени создавалось с помощью другого календаря. Это показано в следующем примере, который использует два разных способа создания значения даты и времени с персидский календарь, но по-прежнему отображается этих значений даты и времени в григорианском календаре, при вызове <xref:System.DateTime.ToString%2A> метода. В этом примере представлены два часто используемых неверных способа отображения даты в заданном календаре.  
  
 [!code-csharp[Formatting.HowTo.Calendar#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#1)]
 [!code-vb[Formatting.HowTo.Calendar#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#1)]  
  
 Для отображения даты в конкретном календаре можно использовать два различных способа. Для первого необходимо, чтобы календарь был установлен в качестве календаря по умолчанию в соответствующих региональных параметрах. Второй может использоваться с любым календарем.  
  
### <a name="to-display-the-date-for-a-cultures-default-calendar"></a>Отображение даты в календаре, который является календарем по умолчанию доя определенного языка и региональных параметров  
  
1.  Создайте экземпляр календаря, производного от <xref:System.Globalization.Calendar> класс, представляющий календарь, используемый.  
  
2.  Создать экземпляр <xref:System.Globalization.CultureInfo> объект, представляющий язык и региональные параметры, соответствующее которым форматирование будет использоваться для отображения даты.  
  
3.  Вызовите <xref:System.Array.Exists%2A?displayProperty=nameWithType> метод, чтобы определить, является ли объект календаря элемента массива, возвращаемого <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType> свойство. Это означает, что календарь может использоваться в качестве календаря по умолчанию для <xref:System.Globalization.CultureInfo> объекта. Если это не является элементом массива, следуйте инструкциям в разделе "Отображение даты в любом календаре".  
  
4.  Назначьте объект календаря <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A> свойство <xref:System.Globalization.DateTimeFormatInfo> объект, возвращаемый <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> свойство.  
  
    > [!NOTE]
    >  <xref:System.Globalization.CultureInfo> Класс также содержит <xref:System.Globalization.CultureInfo.Calendar%2A> свойство. Однако это только для чтения и константой. не изменяется для отражения нового календаря по умолчанию, назначенные <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType> свойство.  
  
5.  Вызвать либо метод <xref:System.DateTime.ToString%2A> или <xref:System.DateTime.ToString%2A> метода и передать его <xref:System.Globalization.CultureInfo> объект календаря по умолчанию был изменен на предыдущем шаге.  
  
### <a name="to-display-the-date-in-any-calendar"></a>Отображение даты в любом календаре  
  
1.  Создайте экземпляр календаря, производного от <xref:System.Globalization.Calendar> класс, представляющий календарь, используемый.  
  
2.  Определите, какие элементы даты и времени должны отображаться в строковом представлении значения даты и времени.  
  
3.  Для даты и времени в каждого элемента, который требуется отобразить, вызовите объект календаря `Get`... метод. Доступны указанные далее методы.  
  
    -   <xref:System.Globalization.Calendar.GetYear%2A>, для вывода года в соответствующем календаре.  
  
    -   <xref:System.Globalization.Calendar.GetMonth%2A>, для отображения месяца в соответствующем календаре.  
  
    -   <xref:System.Globalization.Calendar.GetDayOfMonth%2A>, чтобы отобразить номер дня месяца в соответствующем календаре.  
  
    -   <xref:System.Globalization.Calendar.GetHour%2A>, чтобы отобразить час дня в соответствующем календаре.  
  
    -   <xref:System.Globalization.Calendar.GetMinute%2A>, отображение минут в течение часа в соответствующем календаре.  
  
    -   <xref:System.Globalization.Calendar.GetSecond%2A>, отображение секунд в минуте в соответствующем календаре.  
  
    -   <xref:System.Globalization.Calendar.GetMilliseconds%2A>, для отображения миллисекунд в секунду в соответствующем календаре.  
  
## <a name="example"></a>Пример  
 В примере отображается дата с помощью двух различных календарей. Отображается дата после определения исламского календаря в качестве календаря по умолчанию для региональных параметров ar-JO, а также дата с помощью персидского календаря, который не поддерживается в региональных параметрах fa-IR как дополнительный календарь.  
  
 [!code-csharp[Formatting.HowTo.Calendar#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#2)]
 [!code-vb[Formatting.HowTo.Calendar#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#2)]  
  
 Каждый <xref:System.Globalization.CultureInfo> объект может поддерживать один или несколько календарей, которые обозначены <xref:System.Globalization.CultureInfo.OptionalCalendars%2A> свойство. Один из них обозначается как календарь культуры по умолчанию и возвращается только для чтения <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType> свойство. Другой дополнительные календари могут быть определены как значение по умолчанию, назначив <xref:System.Globalization.Calendar> , представляющий календарь <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType> свойство, возвращенное <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> свойство. Однако некоторые календари, например персидский календарь, представленный <xref:System.Globalization.PersianCalendar> класса, не могут служить дополнительные календари для любого языка и региональных параметров.  
  
 В примере определяется повторно используемый служебный класс календаря `CalendarUtility` для обработки множества данных, связанных с созданием строкового представления даты с помощью конкретного календаря. В классе `CalendarUtility`представлены следующие члены:  
  
-   Параметризованный конструктор, единственным параметром которого является <xref:System.Globalization.Calendar> объект, в котором для представления даты. Он присваивается закрытому полю класса.  
  
-   `CalendarExists`, частного метода, который возвращает логическое значение, указывающее, является ли календарь, представленный `CalendarUtility` объект поддерживается <xref:System.Globalization.CultureInfo> объект, передаваемый в качестве параметра метода. Этот метод создает оболочку вызова <xref:System.Array.Exists%2A?displayProperty=nameWithType> метод, к которому он передает <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType> массива.  
  
-   `HasSameName`, назначенный закрытый метод <xref:System.Predicate%601> делегат, который передается в качестве параметра <xref:System.Array.Exists%2A?displayProperty=nameWithType> метод. Каждый элемент массива передается методу до тех пор, пока метод не вернет значение `true`. Этот метод определяет, совпадает ли имя дополнительного календаря с именем календаря, представленного объектом `CalendarUtility`.  
  
-   `DisplayDate`, перегруженный открытый метод, который передается два параметра: либо <xref:System.DateTime> или <xref:System.DateTimeOffset> выражаемое в календаре, представленном `CalendarUtility` объект и язык и региональные параметры, правила форматирования которых будут использоваться. Его поведение при возврате строкового представления даты зависит от того, поддерживается ли целевой календарь в языке и региональных параметрах, правила форматирования которых будут использоваться.  
  
 Независимо от того, календарь, используемый для создания <xref:System.DateTime> или <xref:System.DateTimeOffset> значение в этом примере, что значение обычно выраженное как дата григорианского календаря. Это вызвано <xref:System.DateTime> и <xref:System.DateTimeOffset> типов не сохранять никаких данных календаря. Внутренне они представлены как число тактов, прошедших с момента полуночи 1 января 0001 г. Интерпретация этого числа зависит от календаря. Для большинства языков и региональных параметров по умолчанию используется григорианский календарь.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 В этом примере требуется ссылка на библиотеку System.Core.dll.  
  
 Скомпилируйте код из командной строки с помощью csc.exe или vb.exe. Для компиляции кода в [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], поместите его в шаблон проекта консольного приложения.  
  
## <a name="see-also"></a>См. также  
 [Выполнение операций форматирования](../../../docs/standard/base-types/performing-formatting-operations.md)
