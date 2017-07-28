---
title: "Практическое руководство. Отображение миллисекунд в значениях даты и времени | Microsoft Docs"
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
  - "даты [платформа .NET Framework], миллисекунды"
  - "DateTime.ToString - метод"
  - "отображение данных даты и времени"
  - "миллисекунды [платформа .NET Framework]"
  - "время [платформа .NET Framework], миллисекунды"
ms.assetid: ae1a0610-90b9-4877-8eb6-4e30bc5e00cf
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Отображение миллисекунд в значениях даты и времени
Методы форматирования даты и времени по умолчанию, такие как <xref:System.DateTime.ToString?displayProperty=fullName>, включают в себя часы, минуты и секунды значения времени, но не содержат миллисекунды.  В этом разделе показано, как включить компонент миллисекунд даты и времени в форматированные строки даты и времени.  
  
### Отображение компонента миллисекунд для значения DateTime  
  
1.  При работе со строковым представлением даты, преобразуйте его в значение <xref:System.DateTime> или в значение <xref:System.DateTimeOffset> с помощью статического метода <xref:System.DateTime.Parse%28System.String%29?displayProperty=fullName> или метода <xref:System.DateTimeOffset.Parse%28System.String%29?displayProperty=fullName>.  
  
2.  Чтобы извлечь строковое представление компонента миллисекунд, вызовите метод <xref:System.DateTime.ToString%28System.String%29?displayProperty=fullName> или метод <xref:System.DateTimeOffset.ToString%2A> значения даты и времени и передайте шаблон пользовательского формата `fff` или `FFF` отдельно или с другим спецификатором пользовательского формата в качестве параметра `format`.  
  
## Пример  
 В этом примере на консоль по отдельности выводятся компонент миллисекунд <xref:System.DateTime> и значение <xref:System.DateTimeOffset>, содержащиеся в более длинной строке даты и времени.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#1)]
 [!code-vb[Formatting.HowTo.Millisecond#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#1)]  
  
 Шаблон форматирования `fff` содержит конечные нули в значении миллисекунд.  Шаблон форматирования `FFF` запрещает их.  В следующем примере показана эта разница.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#2)]
 [!code-vb[Formatting.HowTo.Millisecond#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#2)]  
  
 Проблема с определением полного спецификатора пользовательского формата, содержащего компонент миллисекунд, состоит в том, что он жестко задает формат, который может не соответствовать взаимному расположению элементов времени в текущих региональных параметрах.  Лучшим вариантом будет его извлечение из шаблонов отображения даты и времени, определенных объектом текущих региональных параметров <xref:System.Globalization.DateTimeFormatInfo>, и его изменение с целью включения миллисекунд.  В примере также демонстрируется этот подход.  Извлекается полный шаблон даты и времени для текущих региональных параметров из свойства <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=fullName>. Затем вставляется пользовательский шаблон `.ffff` после шаблона секунд.  Обратите внимание, что в примере используется регулярное выражение для выполнения этой операции в одном методе.  
  
 Можно также использовать спецификатор пользовательского формата, чтобы отобразить дробную часть секунд, отличную от миллисекунд.  Например, спецификатор пользовательского формата `f` или `F` отображает десятые доли секунды, спецификатор `ff` или `FF` — сотые доли секунды, а спецификатор `ffff` или `FFFF` — десятитысячные доли секунды.  Дробные части миллисекунд усекаются, а не округляются в возвращаемой строке.  Эти спецификаторы формата используются в следующем примере.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#3)]
 [!code-vb[Formatting.HowTo.Millisecond#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#3)]  
  
> [!NOTE]
>  Имеется возможность отображать малые дробные части секунды, например десятитысячные или стотысячные доли секунды.  Однако эти значения могут не иметь смысла.  Точность значений даты и времени зависит от разрешения системных часов.  В Windows NT 3.5 и более поздних версий, а также в операционных системах [!INCLUDE[windowsver](../../../includes/windowsver-md.md)], разрешение часов приблизительно равно 10 – 15 миллисекундам.  
  
## Компиляция кода  
 Откомпилируйте код из командной строки, используя csc.exe или vb.exe.  Чтобы откомпилировать код в [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], поместите его в шаблон проекта консольного приложения.  
  
## См. также  
 <xref:System.Globalization.DateTimeFormatInfo>   
 [Строки настраиваемых форматов даты и времени](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)