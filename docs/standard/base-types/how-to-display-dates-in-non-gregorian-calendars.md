---
title: "Практическое руководство. Отображение дат в календарях, отличных от григорианского | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "форматирование [платформа .NET Framework], даты"
  - "даты [платформа .NET Framework], форматирование"
  - "календари [платформа .NET Framework], отображение дат"
  - "отображение данных даты и времени"
ms.assetid: ed324eff-4aff-4a76-b6c0-04e6c0d8f5a9
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Отображение дат в календарях, отличных от григорианского
Типы <xref:System.DateTime> и <xref:System.DateTimeOffset> используют григорианский календарь в качестве календаря по умолчанию.  Это означает, что вызов метода `ToString` для значения даты и времени выведет строковое представление даты и времени в григорианском календаре даже в том случае, если значение даты и времени создавалось с помощью другого календаря.  Это показано в следующем примере, в котором используется два различных способа создания значения даты и времени с персидским календарем. Однако при вызове метода <xref:System.DateTime.ToString%2A> значения даты и времени в нем по\-прежнему отображаются в григорианском календаре.  В этом примере представлены два часто используемых неверных способа отображения даты в заданном календаре.  
  
 [!code-csharp[Formatting.HowTo.Calendar#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#1)]
 [!code-vb[Formatting.HowTo.Calendar#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#1)]  
  
 Для отображения даты в конкретном календаре можно использовать два различных способа.  Для первого необходимо, чтобы календарь был установлен в качестве календаря по умолчанию в соответствующих региональных параметрах.  Второй может использоваться с любым календарем.  
  
### Отображение даты в календаре, который является календарем по умолчанию в определенных региональных параметрах  
  
1.  Создайте экземпляр календаря, производного от класса <xref:System.Globalization.Calendar>, представляющего календарь, который будет использоваться.  
  
2.  Создайте экземпляр объекта <xref:System.Globalization.CultureInfo>, представляющего региональные параметры, которые будут использоваться для отображения даты.  
  
3.  Вызовите метод <xref:System.Array.Exists%2A?displayProperty=fullName>, чтобы определить, является ли объект календаря элементом массива, возвращенного свойством <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=fullName>.  Это означает, что календарь может использоваться в качестве календаря по умолчанию для объекта <xref:System.Globalization.CultureInfo>.  Если он не является элементом массива, следуйте инструкциям в разделе "Отображение даты в любом календаре".  
  
4.  Присвойте объект календаря свойству <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A> объекта <xref:System.Globalization.DateTimeFormatInfo>, возвращаемого свойством <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=fullName>.  
  
    > [!NOTE]
    >  Класс <xref:System.Globalization.CultureInfo> также имеет свойство <xref:System.Globalization.CultureInfo.Calendar%2A>.  Однако это свойство только для чтения и является константой. Оно не изменяется для отражения нового календаря по умолчанию, присвоенного свойству <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=fullName>.  
  
5.  Вызовите метод <xref:System.DateTime.ToString%2A> или метод <xref:System.DateTime.ToString%2A> и передайте ему объект <xref:System.Globalization.CultureInfo>, для которого на предыдущем шаге был изменен календарь по умолчанию.  
  
### Отображение даты в любом календаре  
  
1.  Создайте экземпляр календаря, производного от класса <xref:System.Globalization.Calendar>, представляющего календарь, который будет использоваться.  
  
2.  Определите, какие элементы даты и времени должны отображаться в строковом представлении значения даты и времени.  
  
3.  Для каждого элемента даты и времени, который требуется отобразить, вызовите метод объекта календаря `Get`.  Доступны следующие методы:  
  
    -   <xref:System.Globalization.Calendar.GetYear%2A> — отображение года в соответствующем календаре.  
  
    -   <xref:System.Globalization.Calendar.GetMonth%2A> — отображение месяца в соответствующем календаре.  
  
    -   <xref:System.Globalization.Calendar.GetDayOfMonth%2A> — отображение числа дней в месяце в соответствующем календаре.  
  
    -   <xref:System.Globalization.Calendar.GetHour%2A> — отображение часа дня в соответствующем календаре.  
  
    -   <xref:System.Globalization.Calendar.GetMinute%2A> — отображение минут в часе в соответствующем календаре.  
  
    -   <xref:System.Globalization.Calendar.GetSecond%2A> — отображение секунд в минуте в соответствующем календаре.  
  
    -   <xref:System.Globalization.Calendar.GetMilliseconds%2A> — отображение миллисекунд в секунде в соответствующем календаре.  
  
## Пример  
 В примере отображается дата с помощью двух различных календарей.  Отображается дата после определения исламского календаря в качестве календаря по умолчанию для региональных параметров ar\-JO, а также дата с помощью персидского календаря, который не поддерживается в региональных параметрах fa\-IR как дополнительный календарь.  
  
 [!code-csharp[Formatting.HowTo.Calendar#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#2)]
 [!code-vb[Formatting.HowTo.Calendar#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#2)]  
  
 Каждый объект <xref:System.Globalization.CultureInfo> может поддерживать один или несколько календарей, которые обозначены свойством <xref:System.Globalization.CultureInfo.OptionalCalendars%2A>.  Один из них обозначается как календарь по умолчанию для региональных параметров и возвращается свойством только для чтения <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=fullName>.  Другие дополнительные календари могут быть назначены как календари по умолчанию путем присваивания объекта <xref:System.Globalization.Calendar>, представляющего календарь, свойству <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=fullName>, возвращаемому свойством <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=fullName>.  Однако некоторые календари, например персидский календарь, представленный классом <xref:System.Globalization.PersianCalendar>, не могут служить дополнительными календарями в любых региональных параметрах.  
  
 В примере определяется повторно используемый служебный класс календаря `CalendarUtility` для обработки множества данных, связанных с созданием строкового представления даты с помощью конкретного календаря.  В классе `CalendarUtility` представлены следующие элементы:  
  
-   Параметризованный конструктор, единственным параметром которого является объект <xref:System.Globalization.Calendar>, которым представлена дата.  Он присваивается закрытому полю класса.  
  
-   Закрытый метод `CalendarExists`, который возвращает логическое значение, показывающее, поддерживается ли календарь, представленный объектом `CalendarUtility`, объектом <xref:System.Globalization.CultureInfo>, переданным методу в качестве параметра.  Этот метод создает оболочку вызова для метода <xref:System.Array.Exists%2A?displayProperty=fullName>, которому он передает массив <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=fullName>.  
  
-   Закрытый метод `HasSameName`, присвоенный делегату <xref:System.Predicate%601>, передается в качестве параметра методу <xref:System.Array.Exists%2A?displayProperty=fullName>.  Каждый элемент массива передается методу до тех пор, пока метод не вернет значение `true`.  Этот метод определяет, совпадает ли имя дополнительного календаря с именем календаря, представленного объектом `CalendarUtility`.  
  
-   Перегруженный открытый метод `DisplayDate`, которому передается два параметра: значение <xref:System.DateTime> или <xref:System.DateTimeOffset>, выражаемое в календаре, представленном объектом `CalendarUtility`, а также региональные параметры, правила форматирования которых будут использоваться.  Его поведение при возврате строкового представления даты зависит от того, поддерживается ли целевой календарь в региональных параметрах, правила форматирования которых будут использоваться.  
  
 Независимо от календаря, используемого для создания значения <xref:System.DateTime> или значения <xref:System.DateTimeOffset> в этом примере, это значение обычно выражается в виде григорианской даты.  Это происходит потому, что типы <xref:System.DateTime> и <xref:System.DateTimeOffset> не сохраняют никаких данных календаря.  Внутренне они представлены как число тактов, прошедших с момента полуночи 1 января 0001 года.  Интерпретация этого числа зависит от календаря.  В большинстве региональных параметров по умолчанию используется григорианский календарь.  
  
## Компиляция кода  
 Для этого примера требуется ссылка на System.Core.dll.  
  
 Откомпилируйте код из командной строки, используя csc.exe или vb.exe.  Чтобы откомпилировать код в [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], поместите его в шаблон проекта консольного приложения.  
  
## См. также  
 [Выполнение операций форматирования](../../../docs/standard/base-types/performing-formatting-operations.md)