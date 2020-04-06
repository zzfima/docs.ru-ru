---
title: Практическое руководство. Отображение дат в календарях, отличных от григорианского
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [.NET Framework], dates
- dates [.NET Framework], formatting
- calendars [.NET Framework], displaying dates
- displaying date and time data
ms.assetid: ed324eff-4aff-4a76-b6c0-04e6c0d8f5a9
ms.openlocfilehash: 8d02b74f63ec5b6260679ae4cea04791681ec238
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523917"
---
# <a name="how-to-display-dates-in-non-gregorian-calendars"></a>Практическое руководство. Отображение дат в календарях, отличных от григорианского
Для типов<xref:System.DateTime> и <xref:System.DateTimeOffset> в качестве календаря по умолчанию используется григорианский календарь. Это означает, что вызов метода `ToString` для значения даты и времени выведет строковое представление даты и времени по григорианскому календарю даже в том случае, если значение даты и времени создавалось с помощью другого календаря. Это показано в следующем примере, в котором двумя разными способами создаются значения даты и времени с персидским календарем. При вызове метода <xref:System.DateTime.ToString%2A> значения даты и времени по-прежнему отображаются в григорианском календаре. В этом примере представлены два часто используемых неверных способа отображения даты в заданном календаре.  
  
 [!code-csharp[Formatting.HowTo.Calendar#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#1)]
 [!code-vb[Formatting.HowTo.Calendar#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#1)]  
  
 Для отображения даты в конкретном календаре можно использовать два различных способа. Для первого необходимо, чтобы календарь был установлен в качестве календаря по умолчанию в соответствующих региональных параметрах. Второй может использоваться с любым календарем.  
  
### <a name="to-display-the-date-for-a-cultures-default-calendar"></a>Отображение даты в календаре, который является календарем по умолчанию доя определенного языка и региональных параметров  
  
1. Создайте экземпляр календаря, производного от класса <xref:System.Globalization.Calendar>, который представляет нужный календарь.  
  
2. Создайте экземпляр объекта <xref:System.Globalization.CultureInfo>, который представляет нужные язык и региональные параметры для отображения даты.  
  
3. Вызовите метод <xref:System.Array.Exists%2A?displayProperty=nameWithType>, чтобы определить, является ли объект календаря элементом массива, возвращаемого свойством <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>. Если это так, то календарь можно использовать в качестве календаря по умолчанию для объекта <xref:System.Globalization.CultureInfo>. Если это не является элементом массива, следуйте инструкциям в разделе "Отображение даты в любом календаре".  
  
4. Присвойте объект календаря в качестве значения свойству <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A> в объекте <xref:System.Globalization.DateTimeFormatInfo>, который возвращается свойством <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>.  
  
    > [!NOTE]
    > Класс <xref:System.Globalization.CultureInfo> также содержит свойство <xref:System.Globalization.CultureInfo.Calendar%2A>. Но это свойство доступно только для чтения и является константой, то есть не изменяется в соответствии с новым календарем по умолчанию, присвоенным свойству <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType>.  
  
5. Вызовите метод <xref:System.DateTime.ToString%2A> или <xref:System.DateTime.ToString%2A>, передав ему объект <xref:System.Globalization.CultureInfo>, для которого мы на предыдущем шаге изменили календарь по умолчанию.  
  
### <a name="to-display-the-date-in-any-calendar"></a>Отображение даты в любом календаре  
  
1. Создайте экземпляр календаря, производного от класса <xref:System.Globalization.Calendar>, который представляет нужный календарь.  
  
2. Определите, какие элементы даты и времени должны отображаться в строковом представлении значения даты и времени.  
  
3. Для каждого элемента даты и времени, который требуется отобразить, вызовите метод `Get`... объекта календаря. метод. Доступны указанные далее методы.  
  
    - <xref:System.Globalization.Calendar.GetYear%2A> отвечает за отображение года в соответствующем календаре.  
  
    - <xref:System.Globalization.Calendar.GetMonth%2A> отвечает за отображение месяца в соответствующем календаре.  
  
    - <xref:System.Globalization.Calendar.GetDayOfMonth%2A> отвечает за отображение числа дней в месяце в соответствующем календаре.  
  
    - <xref:System.Globalization.Calendar.GetHour%2A> отвечает за отображение часа дня в соответствующем календаре.  
  
    - <xref:System.Globalization.Calendar.GetMinute%2A> отвечает за отображение минут в часе в соответствующем календаре.  
  
    - <xref:System.Globalization.Calendar.GetSecond%2A> отвечает за отображение секунд в минуте в соответствующем календаре.  
  
    - <xref:System.Globalization.Calendar.GetMilliseconds%2A> отвечает за отображение миллисекунд в секунде в соответствующем календаре.  
  
## <a name="example"></a>Пример  
 В примере отображается дата с помощью двух различных календарей. Отображается дата после определения исламского календаря в качестве календаря по умолчанию для региональных параметров ar-JO, а также дата с помощью персидского календаря, который не поддерживается в региональных параметрах fa-IR как дополнительный календарь.  
  
 [!code-csharp[Formatting.HowTo.Calendar#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#2)]
 [!code-vb[Formatting.HowTo.Calendar#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#2)]  
  
 Каждый объект <xref:System.Globalization.CultureInfo> может поддерживать один или несколько календарей, что указано в свойстве <xref:System.Globalization.CultureInfo.OptionalCalendars%2A>. Один из них обозначается как календарь по умолчанию для выбранных языка и региональных параметров. Он доступен через свойство только для чтения <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType>. Другие дополнительные календари можно назначить как календари по умолчанию. Для этого объект <xref:System.Globalization.Calendar>, который представляет календарь, присваивается свойству <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType>, возвращаемому свойством <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>. Однако некоторые календари, например персидский календарь (класс <xref:System.Globalization.PersianCalendar>), не могут служить дополнительными календарями для языка и региональных параметров.  
  
 В примере определяется повторно используемый служебный класс календаря `CalendarUtility` для обработки множества данных, связанных с созданием строкового представления даты с помощью конкретного календаря. В классе `CalendarUtility`представлены следующие члены:  
  
- Параметризованный конструктор, единственным параметром которого является объект <xref:System.Globalization.Calendar> для представления даты. Он присваивается закрытому полю класса.  
  
- Закрытый метод `CalendarExists`, логическое значение которого обозначает, поддерживается ли календарь (представленный объектом `CalendarUtility`) объектом <xref:System.Globalization.CultureInfo>, который передан в метод в качестве параметра. При помощи этого метода создается оболочка для вызова метода <xref:System.Array.Exists%2A?displayProperty=nameWithType>, в который передается массив <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>.  
  
- Закрытый метод `HasSameName`, назначенный делегату <xref:System.Predicate%601>, который передается в качестве параметра в метод <xref:System.Array.Exists%2A?displayProperty=nameWithType>. Каждый элемент массива передается методу до тех пор, пока метод не вернет значение `true`. Этот метод определяет, совпадает ли имя дополнительного календаря с именем календаря, представленного объектом `CalendarUtility`.  
  
- Перегруженный открытый метод `DisplayDate`, в который передаются два параметра: значение <xref:System.DateTime> или <xref:System.DateTimeOffset> для отображения в календаре, представленном объектом `CalendarUtility`, а также язык и региональные параметры, правила форматирования которых нужно применить. Его поведение при возврате строкового представления даты зависит от того, поддерживается ли целевой календарь в языке и региональных параметрах, правила форматирования которых будут использоваться.  
  
 Независимо от календаря, используемого в этом примере для создания значения <xref:System.DateTime> или <xref:System.DateTimeOffset>, это значение обычно выражается в виде григорианской даты. Это происходит потому, что в типах <xref:System.DateTime> и <xref:System.DateTimeOffset> не сохраняются никакие данные календаря. Внутренне они представлены как число тактов, прошедших с момента полуночи 1 января 0001 г. Интерпретация этого числа зависит от календаря. Для большинства языков и региональных параметров по умолчанию используется григорианский календарь.
