---
title: "Строки пользовательского формата TimeSpan"
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
- format spexifiers, custom time interval
- format strings
- formatting [.NET Framework], time interval
- custom time interval format strings
- formatting [.NET Framework], time
- custom TimeSpan format strings
ms.assetid: a63ebf55-7269-416b-b4f5-286f6c03bf0e
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7302b17beb5ce20ec2bd8865149fe2e0bae9cee4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="custom-timespan-format-strings"></a>Строки пользовательского формата TimeSpan
Объект <xref:System.TimeSpan> строка формата определяет строковое представление <xref:System.TimeSpan> значение, полученное в результате операции форматирования. Строка настраиваемого формата состоит из одного или нескольких пользовательских <xref:System.TimeSpan> описателях вместе с любым числом буквенных символов. Любая строка, которая не является [стандартную строку формата TimeSpan](../../../docs/standard/base-types/standard-timespan-format-strings.md) интерпретируется как строка настраиваемого <xref:System.TimeSpan> строка формата.  
  
> [!IMPORTANT]
>  Пользовательский <xref:System.TimeSpan> описателей формата не включают разделяющие символы, символы, которые отделяют дни от часов, часов, минут или секунд от долей секунд. Вместо этого эти символы должны быть включены в строку настраиваемого формата как строковые литералы. Например, строка `"dd\.hh\:mm"` определяет точку (.) как разделитель дней и часов и двоеточие (:) как разделитель часов и минут.  
>   
>  Настраиваемые спецификаторы формата <xref:System.TimeSpan> также не содержат символ знака, позволяющий различать положительные и отрицательные временные интервалы. Чтобы включить символ знака, необходимо построить строку формата с помощью условной логики. См. пример в разделе [Остальные символы](#Other).  
  
 Строковые представления <xref:System.TimeSpan> значения создаются вызовами перегрузок <xref:System.TimeSpan.ToString%2A?displayProperty=nameWithType> метода и методами, поддерживающими составное форматирование, такими как <xref:System.String.Format%2A?displayProperty=nameWithType>. Дополнительные сведения см. в разделах [Типы форматирования](../../../docs/standard/base-types/formatting-types.md) и [Составное форматирование](../../../docs/standard/base-types/composite-formatting.md). Следующий пример иллюстрирует использование строк пользовательского формата в операциях форматирования.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customformatexample1.cs#1)]
 [!code-vb[Conceptual.TimeSpan.Custom#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customformatexample1.vb#1)]  
  
 Настраиваемый <xref:System.TimeSpan> строки формата также используются программой <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> и <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> методы для определения требуемый формат входных строк для операций анализа. (Анализ преобразует строковое представление значения в это значение). В следующем примере показано использование строк стандартного формата в операциях анализа.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customparseexample1.cs#2)]
 [!code-vb[Conceptual.TimeSpan.Custom#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customparseexample1.vb#2)]  
  
<a name="table"></a>Следующая таблица описывает настраиваемых даты и времени описателей формата.  
  
|Описатель формата|Описание|Пример|  
|----------------------|-----------------|-------------|  
|"d", "%d"|Число целых дней в интервале времени.<br /><br /> Дополнительные сведения см. в подразделе [Настраиваемый описатель формата d](#dSpecifier).|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `%d` --> "6"<br /><br /> `d\.hh\:mm` --> "6.14:32"|  
|«дд» — «dddddddd»|Число целых дней в интервале времени, при необходимости дополненное предшествующими нулями.<br /><br /> Дополнительные сведения: [«Дд» — «dddddddd» настраиваемых описателей формата](#ddSpecifier).|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `ddd` --> "006"<br /><br /> `dd\.hh\:mm` --> "06.14:32"|  
|"h", "%h"|Число целых часов в интервале времени, не учтенных в качестве составной части дней. Нуль не предшествует однозначным числам, обозначающим часы.<br /><br /> Дополнительные сведения см. в подразделе [Настраиваемый описатель формата h](#hSpecifier).|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `%h` --> "14"<br /><br /> `hh\:mm` --> "14:32"|  
|"чч"|Число целых часов в интервале времени, не учтенных в качестве составной части дней. Однозначным числам, обозначающим часы, предшествует нуль.<br /><br /> Дополнительные сведения см. в подразделе [Настраиваемый описатель формата hh](#hhSpecifier).|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `hh` --> "14"<br /><br /> `new TimeSpan(6, 8, 32, 17, 685):`<br /><br /> `hh` --> 08|  
|"m", "%m"|Число целых минут в интервале времени, не учтенных в качестве составной части часов или дней. Нуль не предшествует однозначным числам, обозначающим минуты.<br /><br /> Дополнительные сведения см. в подразделе [Настраиваемый описатель формата m](#mSpecifier).|`new TimeSpan(6, 14, 8, 17, 685):`<br /><br /> `%m` --> "8"<br /><br /> `h\:m` --> "14:8"|  
|"mm"|Число целых минут в интервале времени, не учтенных в качестве составной части часов или дней. Однозначным числам, обозначающим минуты, предшествует нуль.<br /><br /> Дополнительные сведения см. в подразделе [Настраиваемый описатель формата mm](#mmSpecifier).|`new TimeSpan(6, 14, 8, 17, 685):`<br /><br /> `mm` --> "08"<br /><br /> `new TimeSpan(6, 8, 5, 17, 685):`<br /><br /> `d\.hh\:mm\:ss` --> 6.08:05:17|  
|"s", "%s"|Число целых секунд в интервале времени, не учтенных в качестве составной части часов, дней или минут. Нуль не предшествует однозначным числам, обозначающим секунды.<br /><br /> Дополнительные сведения см. в подразделе [Настраиваемый описатель формата s](#sSpecifier).|`TimeSpan.FromSeconds(12.965)`:<br /><br /> `%s` --> 12<br /><br /> `s\.fff` --> 12.965|  
|"сс"|Число целых секунд в интервале времени, не учтенных в качестве составной части часов, дней или минут.  Однозначным числам, обозначающим секунды, предшествует нуль.<br /><br /> Дополнительные сведения см. в подразделе [Настраиваемый описатель формата ss](#ssSpecifier).|`TimeSpan.FromSeconds(6.965)`:<br /><br /> `ss` --> 06<br /><br /> `ss\.fff` --> 06.965|  
|"f", "%f"|Десятые доли секунды в интервале времени.<br /><br /> Дополнительные сведения см. в подразделе [Настраиваемый описатель формата f](#fSpecifier).|`TimeSpan.FromSeconds(6.895)`:<br /><br /> `f` --> 8<br /><br /> `ss\.f` --> 06.8|  
|"ff"|Сотые доли секунды в интервале времени.<br /><br /> Дополнительные сведения:[настраиваемый описатель формата «ff»](#ffSpecifier).|`TimeSpan.FromSeconds(6.895)`:<br /><br /> `ff` --> 89<br /><br /> `ss\.ff` --> 06.89|  
|"fff"|Миллисекунды в интервале времени.<br /><br /> Дополнительные сведения см. в подразделе [Настраиваемый описатель формата FFF](#f3Specifier).|`TimeSpan.FromSeconds(6.895)`:<br /><br /> `fff` --> 895<br /><br /> `ss\.fff` --> 06.895|  
|"ffff"|Десятитысячные доли секунды в интервале времени.<br /><br /> Дополнительные сведения см. в подразделе [Настраиваемый описатель формата FFFF](#f4Specifier).|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `ffff` --> 8954<br /><br /> `ss\.ffff` --> 06.8954|  
|"fffff"|Стотысячные доли секунды в интервале времени.<br /><br /> Дополнительные сведения см. в подразделе [Настраиваемый описатель формата FFFFF](#f5Specifier).|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `fffff` --> 89543<br /><br /> `ss\.fffff` --> 06.89543|  
|"ffffff"|Миллионные доли секунды в интервале времени.<br /><br /> Дополнительные сведения см. в подразделе [Настраиваемый описатель формата FFFFFF](#f6Specifier).|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `ffffff` --> 895432<br /><br /> `ss\.ffffff` --> 06.895432|  
|"fffffff"|Десятимиллионные доли секунды (или дробные такты) в интервале времени.<br /><br /> Дополнительные сведения см. в подразделе [Настраиваемый описатель формата FFFFFFF](#f7Specifier).|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `fffffff` --> 8954321<br /><br /> `ss\.fffffff` --> 06.8954321|  
|"F", "%F"|Десятые доли секунды в интервале времени. Если цифра равна нулю, то ничего не отображается.<br /><br /> Дополнительные сведения см. в подразделе [Настраиваемый описатель формата f](#F_Specifier).|`TimeSpan.Parse("00:00:06.32")`:<br /><br /> `%F`: 3<br /><br /> `TimeSpan.Parse("0:0:3.091")`:<br /><br /> `ss\.F`: 03.|  
|"FF"|Сотые доли секунды в интервале времени. Любые нули в конце дробной части или два нуля не включаются.<br /><br /> Дополнительные сведения см. в подразделе [Настраиваемый описатель формата FF](#FF_Specifier).|`TimeSpan.Parse("00:00:06.329")`:<br /><br /> `FF`: 32<br /><br /> `TimeSpan.Parse("0:0:3.101")`:<br /><br /> `ss\.FF`: 03.1|  
|"FFF"|Миллисекунды в интервале времени. Любые нули в конце дробной части не включаются.<br /><br /> Дополнительная информация:|`TimeSpan.Parse("00:00:06.3291")`:<br /><br /> `FFF`: 329<br /><br /> `TimeSpan.Parse("0:0:3.1009")`:<br /><br /> `ss\.FFF`: 03.1|  
|"FFFF"|Десятитысячные доли секунды в интервале времени. Любые нули в конце дробной части не включаются.<br /><br /> Дополнительные сведения см. в подразделе [Настраиваемый описатель формата FFFF](#F4_Specifier).|`TimeSpan.Parse("00:00:06.32917")`:<br /><br /> `FFFFF`: 3291<br /><br /> `TimeSpan.Parse("0:0:3.10009")`:<br /><br /> `ss\.FFFF`: 03.1|  
|"FFFFF"|Стотысячные доли секунды в интервале времени. Любые нули в конце дробной части не включаются.<br /><br /> Дополнительные сведения см. в подразделе [Настраиваемый описатель формата FFFFF](#F5_Specifier).|`TimeSpan.Parse("00:00:06.329179")`:<br /><br /> `FFFFF`: 32917<br /><br /> `TimeSpan.Parse("0:0:3.100009")`:<br /><br /> `ss\.FFFFF`: 03.1|  
|"FFFFFF"|Миллионные доли секунды в интервале времени. Любые нули в конце дробной части не отображаются.<br /><br /> Дополнительные сведения см. в подразделе [Настраиваемый описатель формата FFFFFF](#F6_Specifier).|`TimeSpan.Parse("00:00:06.3291791")`:<br /><br /> `FFFFFF`: 329179<br /><br /> `TimeSpan.Parse("0:0:3.1000009")`:<br /><br /> `ss\.FFFFFF`: 03.1|  
|"FFFFFFF"|Десятимиллионные доли секунды в интервале времени. Любые нули в конце дробной части или семь нулей не отображаются.<br /><br /> Дополнительные сведения см. в подразделе [Настраиваемый описатель формата FFFFFFF](#F7_Specifier).|`TimeSpan.Parse("00:00:06.3291791")`:<br /><br /> `FFFFFF`: 3291791<br /><br /> `TimeSpan.Parse("0:0:3.1900000")`:<br /><br /> `ss\.FFFFFF`: 03.19|  
|*"строка*"|Буквенный разделитель строк.<br /><br /> Дополнительные сведения: [остальные символы](#Other).|`new TimeSpan(14, 32, 17):`<br /><br /> `hh':'mm':'ss` --> "14:32:17"|  
|\|Escape-символ.<br /><br /> Дополнительные сведения:[остальные символы](#Other).|`new TimeSpan(14, 32, 17):`<br /><br /> `hh\:mm\:ss` --> "14:32:17"|  
|Любой другой знак|Любой другой символ, не являющийся escape-символом, интерпретируется как описатель настраиваемого формата.<br /><br /> Дополнительные сведения: [другие символы](#Other).|`new TimeSpan(14, 32, 17):`<br /><br /> `hh\:mm\:ss` --> "14:32:17"|  
  
<a name="dSpecifier"></a>   
## <a name="the-d-custom-format-specifier"></a>Настраиваемый описатель формата "d"  
 Описатель настраиваемого формата «d» выводит значение <xref:System.TimeSpan.Days%2A?displayProperty=nameWithType> свойства, которое представляет число полных дней в интервале времени. Он выводит полное число дней в <xref:System.TimeSpan> значение, даже если значение состоит из нескольких цифр. Если значение <xref:System.TimeSpan.Days%2A?displayProperty=nameWithType> равно нулю, описатель выводит «0».  
  
 Если используется единственный описатель настраиваемого формата "d", необходимо задать "%d" для избежания неверной интерпретации в качестве строки стандартного формата. Ниже приведен пример.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#3)]
 [!code-vb[Conceptual.TimeSpan.Custom#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#3)]  
  
 В следующем примере показано использование описателя настраиваемого формата "d".  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#4)]
 [!code-vb[Conceptual.TimeSpan.Custom#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#4)]  
  
 [К таблице](#table)  
  
<a name="ddSpecifier"></a>   
## <a name="the-dd-dddddddd-custom-format-specifiers"></a>Описатели настраиваемого формата "dd"-"dddddddd"  
 «Dd», «ddd», «dddd», «ддддд», «dddddd», «ццццццц» и «dddddddd» настраиваемых описателей формата вывода значение <xref:System.TimeSpan.Days%2A?displayProperty=nameWithType> свойства, которое представляет число полных дней в интервале времени.  
  
 Выходная строка включает минимальное количество знаков, заданных числом символов "d" в описателе формата; при необходимости она дополняется предшествующими нулями. Если количество цифр в числе дней превышает число символов "d" в описателе формата, в результирующей строке выводится полное число дней.  
  
 В следующем примере эти описатели формата для отображения строкового представления двух <xref:System.TimeSpan> значения. Значение компонента дней первого временного интервала равно нулю; значение компонента дней второго — 365.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#5)]
 [!code-vb[Conceptual.TimeSpan.Custom#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#5)]  
  
 [К таблице](#table)  
  
<a name="hSpecifier"></a>   
## <a name="the-h-custom-format-specifier"></a>Настраиваемый описатель формата "h"  
 Описатель настраиваемого формата «h» выводит значение <xref:System.TimeSpan.Hours%2A?displayProperty=nameWithType> свойства, которое представляет число целых часов в интервале времени, не учитывается в качестве части его дневного компонента. Он возвращает однозначное строковое значение, если значение <xref:System.TimeSpan.Hours%2A?displayProperty=nameWithType> свойства — от 0 до 9, и возвращает двузначное строковое значение, если значение <xref:System.TimeSpan.Hours%2A?displayProperty=nameWithType> свойства лежит в диапазоне от 10 до 23.  
  
 Если используется единственный описатель настраиваемого формата "h", необходимо задать "%h" для избежания неверной интерпретации в качестве строки стандартного формата. Ниже приведен пример.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#6)]
 [!code-vb[Conceptual.TimeSpan.Custom#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#6)]  
  
 Как правило, в операции анализа входная строка, которая содержит только одно число, интерпретируется как число дней. Можно использовать описатель настраиваемого формата "%h" вместо того, чтобы интерпретировать числовую строку как количество часов. Ниже приведен пример.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#8)]
 [!code-vb[Conceptual.TimeSpan.Custom#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#8)]  
  
 В следующем примере показано использование описателя настраиваемого формата "h".  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#7)]
 [!code-vb[Conceptual.TimeSpan.Custom#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#7)]  
  
 [К таблице](#table)  
  
<a name="hhSpecifier"></a>   
## <a name="the-hh-custom-format-specifier"></a>Настраиваемый описатель формата "hh"  
 Описатель настраиваемого формата «hh» выводит значение <xref:System.TimeSpan.Hours%2A?displayProperty=nameWithType> свойства, которое представляет число целых часов в интервале времени, не учитывается в качестве части его дневного компонента. Выходная строка включает предшествующий нуль для значений от 0 до 9.  
  
 Как правило, в операции анализа входная строка, которая содержит только одно число, интерпретируется как число дней. Можно использовать описатель настраиваемого формата "hh" вместо того, чтобы интерпретировать числовую строку как количество часов. Ниже приведен пример.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#9)]
 [!code-vb[Conceptual.TimeSpan.Custom#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#9)]  
  
 В следующем примере показано использование описателя настраиваемого формата "hh".  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#10)]
 [!code-vb[Conceptual.TimeSpan.Custom#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#10)]  
  
 [К таблице](#table)  
  
<a name="mSpecifier"></a>   
## <a name="the-m-custom-format-specifier"></a>Настраиваемый описатель формата "m"  
 Описатель настраиваемого формата «m» выводит значение <xref:System.TimeSpan.Minutes%2A?displayProperty=nameWithType> свойства, которое представляет число целых минут в интервале времени, не учитывается в качестве части его дневного компонента. Он возвращает однозначное строковое значение, если значение <xref:System.TimeSpan.Minutes%2A?displayProperty=nameWithType> свойства — от 0 до 9, и возвращает двузначное строковое значение, если значение <xref:System.TimeSpan.Minutes%2A?displayProperty=nameWithType> свойства лежит в диапазоне от 10 до 59.  
  
 Если используется единственный описатель настраиваемого формата "m", необходимо задать "%m" для избежания неверной интерпретации в качестве строки стандартного формата. Ниже приведен пример.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#6)]
 [!code-vb[Conceptual.TimeSpan.Custom#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#6)]  
  
 Как правило, в операции анализа входная строка, которая содержит только одно число, интерпретируется как число дней. Можно использовать описатель настраиваемого формата "%m" вместо того, чтобы интерпретировать числовую строку как количество часов. Ниже приведен пример.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#11)]
 [!code-vb[Conceptual.TimeSpan.Custom#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#11)]  
  
 В следующем примере показано использование описателя настраиваемого формата "m".  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#12)]
 [!code-vb[Conceptual.TimeSpan.Custom#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#12)]  
  
 [К таблице](#table)  
  
<a name="mmSpecifier"></a>   
## <a name="the-mm-custom-format-specifier"></a>Настраиваемый описатель формата "mm"  
 Описатель настраиваемого формата «mm» выводит значение <xref:System.TimeSpan.Minutes%2A?displayProperty=nameWithType> свойства, которое представляет число целых минут в интервале времени, не включенный в состав компонента его часов или дней. Выходная строка включает предшествующий нуль для значений от 0 до 9.  
  
 Как правило, в операции анализа входная строка, которая содержит только одно число, интерпретируется как число дней. Можно использовать описатель настраиваемого формата "mm" вместо того, чтобы интерпретировать числовую строку как количество минут. Ниже приведен пример.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#13)]
 [!code-vb[Conceptual.TimeSpan.Custom#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#13)]  
  
 В следующем примере показано использование описателя настраиваемого формата "mm".  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#14)]
 [!code-vb[Conceptual.TimeSpan.Custom#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#14)]  
  
 [К таблице](#table)  
  
<a name="sSpecifier"></a>   
## <a name="the-s-custom-format-specifier"></a>Настраиваемый описатель формата "s"  
 Описатель настраиваемого формата «s» выводит значение <xref:System.TimeSpan.Seconds%2A?displayProperty=nameWithType> свойства, которое представляет число целых секунд в интервале времени, который не является частью часов, дней или компонент минут. Он возвращает однозначное строковое значение, если значение <xref:System.TimeSpan.Seconds%2A?displayProperty=nameWithType> свойства — от 0 до 9, и возвращает двузначное строковое значение, если значение <xref:System.TimeSpan.Seconds%2A?displayProperty=nameWithType> свойства лежит в диапазоне от 10 до 59.  
  
 Если используется единственный описатель настраиваемого формата "s", необходимо задать "%s" для избежания неверной интерпретации в качестве строки стандартного формата. Ниже приведен пример.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#15)]
 [!code-vb[Conceptual.TimeSpan.Custom#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#15)]  
  
 Как правило, в операции анализа входная строка, которая содержит только одно число, интерпретируется как число дней. Можно использовать описатель настраиваемого формата "%s" вместо того, чтобы интерпретировать числовую строку как количество секунд. Ниже приведен пример.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#17)]
 [!code-vb[Conceptual.TimeSpan.Custom#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#17)]  
  
 В следующем примере показано использование описателя настраиваемого формата "s".  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#16)]
 [!code-vb[Conceptual.TimeSpan.Custom#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#16)]  
  
 [К таблице](#table)  
  
<a name="ssSpecifier"></a>   
## <a name="the-ss-custom-format-specifier"></a>Настраиваемый описатель формата "ss"  
 Описатель настраиваемого формата «ss» выводит значение <xref:System.TimeSpan.Seconds%2A?displayProperty=nameWithType> свойства, которое представляет число целых секунд в интервале времени, который не является частью часов, дней или компонент минут. Выходная строка включает предшествующий нуль для значений от 0 до 9.  
  
 Как правило, в операции анализа входная строка, которая содержит только одно число, интерпретируется как число дней. Можно использовать описатель настраиваемого формата "ss" вместо того, чтобы интерпретировать числовую строку как количество секунд. Ниже приведен пример.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#18)]
 [!code-vb[Conceptual.TimeSpan.Custom#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#18)]  
  
 В следующем примере показано использование описателя настраиваемого формата "ss".  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#19)]
 [!code-vb[Conceptual.TimeSpan.Custom#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#19)]  
  
 [К таблице](#table)  
  
<a name="fSpecifier"></a>   
## <a name="thef-custom-format-specifier"></a>Описатель настраиваемого формата «f»  
 Описатель настраиваемого формата "f" выводит десятые доли секунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. В операции анализа, которая вызывает <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> или <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> метод, входная строка должна содержать ровно одной цифрой дробной части.  
  
 Если используется единственный описатель настраиваемого формата "f", необходимо задать "%f" для избежания неверной интерпретации в качестве строки стандартного формата.  
  
 Следующий пример использует описатель настраиваемого формата «f» для отображения десятые доли секунды в <xref:System.TimeSpan> значение. "f" используется сначала только как описатель формата, а затем объединяется с описателем "s" в строке настраиваемого формата.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
 [!code-vb[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]  
  
 [К таблице](#table)  
  
<a name="ffSpecifier"></a>   
## <a name="the-ff-custom-format-specifier"></a>Настраиваемый описатель формата "ff"  
 Описатель настраиваемого формата "ff" выводит сотые доли секунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. В операции анализа, которая вызывает <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> или <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> метод, входная строка должна содержать ровно две цифры дробной части.  
  
 Следующий пример описатель настраиваемого формата «ff» используется для отображения сотые доли секунды в <xref:System.TimeSpan> значение. "ff" используется сначала только как описатель формата, а затем объединяется с описателем "s" в строке настраиваемого формата.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
 [!code-vb[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]  
  
 [К таблице](#table)  
  
<a name="f3Specifier"></a>   
## <a name="the-fff-custom-format-specifier"></a>Настраиваемый описатель формата "fff"  
 Описатель настраиваемого формата "fff" (c тремя символами "f") выводит миллисекунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. В операции анализа, которая вызывает <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> или <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> метод, входная строка должна содержать ровно три цифр дробной части.  
  
 Следующий пример описатель настраиваемого формата «fff» используется для отображения миллисекунд в <xref:System.TimeSpan> значение. "fff" используется сначала только как описатель формата, а затем объединяется с описателем "s" в строке настраиваемого формата.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
 [!code-vb[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]  
  
 [К таблице](#table)  
  
<a name="f4Specifier"></a>   
## <a name="the-ffff-custom-format-specifier"></a>Настраиваемый описатель формата "ffff"  
 Описатель настраиваемого формата "ffff" (с четырьмя символами "f") выводит десятитысячные доли секунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. В операции анализа, которая вызывает <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> или <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> метод, входная строка должна содержать только четыре дробные цифры.  
  
 Следующий пример использует описатель настраиваемого формата «ffff» для отображения десятитысячных долей секунды в <xref:System.TimeSpan> значение. "ffff" используется сначала только как описатель формата, а затем объединяется с описателем "s" в строке настраиваемого формата.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
 [!code-vb[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]  
  
 [К таблице](#table)  
  
<a name="f5Specifier"></a>   
## <a name="the-fffff-custom-format-specifier"></a>Настраиваемый описатель формата "fffff"  
 Описатель настраиваемого формата "fffff" (с пятью символами "f") выводит стотысячные доли секунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. В операции анализа, которая вызывает <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> или <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> метод, входная строка должна содержать ровно пять цифр дробной части.  
  
 Следующий пример использует описатель настраиваемого формата «fffff» для отображения стотысячных долей секунды в <xref:System.TimeSpan> значение. "fffff" используется сначала только как описатель формата, а затем объединяется с описателем "s" в строке настраиваемого формата.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
 [!code-vb[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]  
  
 [К таблице](#table)  
  
<a name="f6Specifier"></a>   
## <a name="the-ffffff-custom-format-specifier"></a>Настраиваемый описатель формата "ffffff"  
 Описатель настраиваемого формата "ffffff" (с шестью символами "f") выводит миллионные доли секунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. В операции анализа, которая вызывает <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> или <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> метод, входная строка должна содержать только шесть дробных разрядов.  
  
 Следующий пример использует описатель настраиваемого формата «ffffff» для отображения миллионных долей секунды в <xref:System.TimeSpan> значение. Он используется сначала только как описатель формата, а затем объединяется с описателем "s" в строке настраиваемого формата.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
 [!code-vb[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]  
  
 [К таблице](#table)  
  
<a name="f7Specifier"></a>   
## <a name="the-fffffff-custom-format-specifier"></a>Настраиваемый описатель формата "fffffff"  
 Описатель настраиваемого формата "fffffff" (с семью символами "f") выводит десятимиллионные доли секунды (или дробное число тактов) в интервале времени. В операции анализа, которая вызывает <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> или <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> метод, входная строка должна содержать только семь цифр дробной части.  
  
 Следующий пример использует описатель настраиваемого формата «fffffff» для отображения долей количество тактов в <xref:System.TimeSpan> значение. Он используется сначала только как описатель формата, а затем объединяется с описателем "s" в строке настраиваемого формата.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
 [!code-vb[Conceptual.TimeSpan.Custom#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]  
  
 [К таблице](#table)  
  
<a name="F_Specifier"></a>   
## <a name="the-f-custom-format-specifier"></a>Настраиваемый описатель формата "F"  
 Описатель настраиваемого формата "F" выводит десятые доли секунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. Если значение десятых долей секунды временного интервала равно нулю, оно не включается в строку результата. В операции анализа, которая вызывает <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> или <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> , наличие десятые доли секунды является необязательным.  
  
 Если используется единственный описатель настраиваемого формата "F", необходимо задать "%F" для избежания неверной интерпретации в качестве строки стандартного формата.  
  
 Следующий пример использует описатель настраиваемого формата «F» для отображения десятые доли секунды в <xref:System.TimeSpan> значение. Этот описатель настраиваемого формата также используется в операции анализа.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#21)]
 [!code-vb[Conceptual.TimeSpan.Custom#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#21)]  
  
 [К таблице](#table)  
  
<a name="FF_Specifier"></a>   
## <a name="the-ff-custom-format-specifier"></a>Настраиваемый описатель формата "FF"  
 Описатель настраиваемого формата "FF" выводит сотые доли секунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. Результирующая строка не включает нули в конце дробной части. В операции анализа, которая вызывает <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> или <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> , наличие десятых и сотые доли секунды является необязательным.  
  
 Следующий пример описатель настраиваемого формата «FF» используется для отображения сотые доли секунды в <xref:System.TimeSpan> значение. Этот описатель настраиваемого формата также используется в операции анализа.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#22](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#22)]
 [!code-vb[Conceptual.TimeSpan.Custom#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#22)]  
  
 [К таблице](#table)  
  
<a name="F3_Specifier"></a>   
## <a name="the-fff-custom-format-specifier"></a>Настраиваемый описатель формата "FFF"  
 Описатель настраиваемого формата "FFF" (c тремя символами "F") выводит миллисекунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. Результирующая строка не включает нули в конце дробной части. В операции анализа, которая вызывает <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> или <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> , наличие десятых, сотые и тысячных долей секунды является необязательным.  
  
 Следующий пример описатель настраиваемого формата «FFF» используется для отображения тысячные доли секунды в <xref:System.TimeSpan> значение. Этот описатель настраиваемого формата также используется в операции анализа.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#23](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#23)]
 [!code-vb[Conceptual.TimeSpan.Custom#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#23)]  
  
 [К таблице](#table)  
  
<a name="F4_Specifier"></a>   
## <a name="the-ffff-custom-format-specifier"></a>Настраиваемый описатель формата "FFFF"  
 Описатель настраиваемого формата "FFFF" (с четырьмя символами "F") выводит десятитысячные доли секунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. Результирующая строка не включает нули в конце дробной части. В операции анализа, которая вызывает <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> или <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> , наличие десятых, сотые, тысячных и десятитысячных долей секунды является необязательным.  
  
 Следующий пример использует описатель настраиваемого формата «FFFF» для отображения десятитысячных долей секунды в <xref:System.TimeSpan> значение. Описатель настраиваемого формата "FFFF" также используется в операции анализа.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#24](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#24)]
 [!code-vb[Conceptual.TimeSpan.Custom#24](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#24)]  
  
 [К таблице](#table)  
  
<a name="F5_Specifier"></a>   
## <a name="the-fffff-custom-format-specifier"></a>Настраиваемый описатель формата "FFFFF"  
 Описатель настраиваемого формата "FFFFF" (с пятью символами "F") выводит стотысячные доли секунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. Результирующая строка не включает нули в конце дробной части. В операции анализа, которая вызывает <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> или <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> , наличие десятых, сотые, тысячных, десятитысячных и стотысячных долей секунды является необязательным.  
  
 Следующий пример использует описатель настраиваемого формата «FFFFF» для отображения стотысячных долей секунды в <xref:System.TimeSpan> значение. Описатель настраиваемого формата "FFFFF" также используется в операции анализа.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#25](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#25)]
 [!code-vb[Conceptual.TimeSpan.Custom#25](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#25)]  
  
 [К таблице](#table)  
  
<a name="F6_Specifier"></a>   
## <a name="the-ffffff-custom-format-specifier"></a>Настраиваемый описатель формата "FFFFFF"  
 Описатель настраиваемого формата "FFFFFF" (с шестью символами "F") выводит миллионные доли секунды в интервале времени. В операции форматирования все оставшиеся цифры дробной части усекаются. Результирующая строка не включает нули в конце дробной части. В операции анализа, которая вызывает <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> или <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> , наличие десятых, сотые, тысячные доли, десятитысячных, стотысячных и миллионных долей секунды является необязательным.  
  
 Следующий пример использует описатель настраиваемого формата «FFFFFF» для отображения миллионных долей секунды в <xref:System.TimeSpan> значение. Этот описатель настраиваемого формата также используется в операции анализа.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#26](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#26)]
 [!code-vb[Conceptual.TimeSpan.Custom#26](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#26)]  
  
 [К таблице](#table)  
  
<a name="F7_Specifier"></a>   
## <a name="the-fffffff-custom-format-specifier"></a>Настраиваемый описатель формата "FFFFFFF"  
 Описатель настраиваемого формата "FFFFFFF" (с семью символами "F") выводит десятимиллионные доли секунды (или дробное число тактов) в интервале времени. Результирующая строка не включает нули в конце дробной части. В операции анализа, которая вызывает <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> или <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> , наличие семь цифр дробной части во входной строке является необязательным.  
  
 Следующий пример использует описатель настраиваемого формата «FFFFFFF» для отображения дробных частей секунды в <xref:System.TimeSpan> значение. Этот описатель настраиваемого формата также используется в операции анализа.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#27](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#27)]
 [!code-vb[Conceptual.TimeSpan.Custom#27](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#27)]  
  
 [К таблице](#table)  
  
<a name="Other"></a>   
## <a name="other-characters"></a>Остальные символы  
 Любой другой символ в строке формата, не являющийся escape-символом, включая знак пробела, интерпретируется как описатель настраиваемого формата. В большинстве случаев наличие любого другого, не являющегося escape-символом, приводит <xref:System.FormatException>.  
  
 Существует два способа включить литеральный символ в строку формата.  
  
-   Заключить его в одиночные кавычки (разделитель строк-литералов).  
  
-   Укажите перед ним обратную косую черту («\\»), который интерпретируется как escape-символ. Это означает, что в C# строка формата должна представлять собой символ @-quoted или что литеральный символ должен быть предварен дополнительной обратной косой чертой.  
  
     В некоторых случаях может быть необходимо использовать условную логику, чтобы включить escape-символ в строку формата. В следующем примере условная логика используется для включения символа знака для отрицательных временных интервалов.  
  
     [!code-csharp[Conceptual.TimeSpan.Custom#29](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/negativevalues1.cs#29)]
     [!code-vb[Conceptual.TimeSpan.Custom#29](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/negativevalues1.vb#29)]  
  
 .NET не определяет грамматику для разделителей в интервалах времени. Это означает, что разделители между днями и часами, часами и минутами, минутами и секундами, секундами и долями секунд должны быть обработаны как символьные литералы в строке формата.  
  
 В следующем примере используются как escape-символ, так и одиночная кавычка для определения строки настраиваемого формата, которая включает слово "minutes" в выходной строке.  
  
 [!code-csharp[Conceptual.TimeSpan.Custom#28](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/literal1.cs#28)]
 [!code-vb[Conceptual.TimeSpan.Custom#28](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/literal1.vb#28)]  
  
 [К таблице](#table)  
  
## <a name="see-also"></a>См. также  
 [Типы форматирования](../../../docs/standard/base-types/formatting-types.md)  
 [Строки стандартного формата TimeSpan](../../../docs/standard/base-types/standard-timespan-format-strings.md)
