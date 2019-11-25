---
title: Строки стандартного формата TimeSpan
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- format specifiers, standard time interval
- format strings
- standard time interval format strings
- standard format strings, time intervals
- format specifiers, time intervals
- time intervals [.NET Framework], formatting
- time [.NET Framework], formatting
- formatting [.NET Framework], time
- standard TimeSpan format strings
- formatting [.NET Framework], time intervals
ms.assetid: 9f6c95eb-63ae-4dcc-9c32-f81985c75794
ms.openlocfilehash: c699ed68606293b1a49a540e00636cf7f56bdf2f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73972096"
---
# <a name="standard-timespan-format-strings"></a>Строки стандартного формата TimeSpan

Строка стандартного формата <xref:System.TimeSpan> использует один описатель формата для определения текстового представления значения <xref:System.TimeSpan>, получаемого после выполнения операции форматирования. Любая строка формата, содержащая более одной буквы, включая пробелы, интерпретируется как строка настраиваемого формата <xref:System.TimeSpan>. Дополнительные сведения см. в разделе [Строки настраиваемого формата TimeSpan](../../../docs/standard/base-types/custom-timespan-format-strings.md).  
  
 Строковые представления значений <xref:System.TimeSpan> создаются вызовами перегрузок метода <xref:System.TimeSpan.ToString%2A?displayProperty=nameWithType>, а также методами, поддерживающими составное форматирование, такими как <xref:System.String.Format%2A?displayProperty=nameWithType>. Дополнительные сведения см. в разделах [Типы форматирования](../../../docs/standard/base-types/formatting-types.md) и [Составное форматирование](../../../docs/standard/base-types/composite-formatting.md). В следующем примере показано использование строк стандартного формата в операциях форматирования.  
  
 [!code-csharp[Conceptual.TimeSpan.Standard#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.standard/cs/formatexample1.cs#2)]
 [!code-vb[Conceptual.TimeSpan.Standard#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.standard/vb/formatexample1.vb#2)]  
  
 Строки стандартного формата <xref:System.TimeSpan> также используется методами <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> и <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> для определения необходимого формата входных строк для операций анализа. (Анализ преобразует строковое представление значения в это значение). В следующем примере показано использование строк стандартного формата в операциях анализа.  
  
 [!code-csharp[Conceptual.TimeSpan.Standard#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.standard/cs/parseexample1.cs#3)]
 [!code-vb[Conceptual.TimeSpan.Standard#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.standard/vb/parseexample1.vb#3)]  
  
В следующей таблице перечислены описатели стандартного формата временных интервалов.  
  
|Описатель формата|name|ОПИСАНИЕ|Примеры|  
|----------------------|----------|-----------------|--------------|  
|"c"|Постоянный (инвариантный) формат|Этот описатель не учитывает язык и региональные параметры. Он принимает форму `[-][d'.']hh':'mm':'ss['.'fffffff]`.<br /><br /> (Строки формата "t" и "T" дают одинаковые результаты).<br /><br /> Дополнительная информация: [Описатель формата константы (c)](#the-constant-c-format-specifier).|`TimeSpan.Zero` -> 00:00:00<br /><br /> `New TimeSpan(0, 0, 30, 0)` -> 00:30:00<br /><br /> `New TimeSpan(3, 17, 25, 30, 500)` -> 3.17:25:30.5000000|  
|"g"|Общий короткий формат|Этот описатель выводит только необходимые данные. Он зависит от языка и региональных параметров и принимает форму `[-][d':']h':'mm':'ss[.FFFFFFF]`.<br /><br /> Дополнительная информация: [Описатель общего короткого формата (g)](#the-general-short-g-format-specifier).|`New TimeSpan(1, 3, 16, 50, 500)` -> 1:3:16:50.5 (en-US)<br /><br /> `New TimeSpan(1, 3, 16, 50, 500)` -> 1:3:16:50,5 (fr-FR)<br /><br /> `New TimeSpan(1, 3, 16, 50, 599)` -> 1:3:16:50.599 (en-US)<br /><br /> `New TimeSpan(1, 3, 16, 50, 599)` -> 1:3:16:50,599 (fr-FR)|  
|"G"|Общий длинный формат|Этот описатель всегда отображает дни и семь цифр после запятой. Он зависит от языка и региональных параметров и принимает форму `[-]d':'hh':'mm':'ss.fffffff`.<br /><br /> Дополнительная информация: [Описатель общего длинного формата (G)](#the-general-long-g-format-specifier).|`New TimeSpan(18, 30, 0)` -> 0:18:30:00.0000000 (en-US)<br /><br /> `New TimeSpan(18, 30, 0)` -> 0:18:30:00,0000000 (fr-FR)|  

## <a name="the-constant-c-format-specifier"></a>Описатель постоянного ("c") формата.  
 Описатель формата "c" возвращает строковое представление значения <xref:System.TimeSpan> в следующем виде:  
  
 [-][*d*.]*hh*:*mm*:*ss*[.*fffffff*]  
  
 Элементы в квадратных скобках ([и]) являются необязательными. Точка (.) и двоеточие (:) являются литеральными символами. В следующей таблице описываются остальные элементы.  
  
|Элемент|ОПИСАНИЕ|  
|-------------|-----------------|  
|*-*|Необязательный знак минуса, который означает отрицательный интервал времени.|  
|*d*|Необязательное число дней без предшествующих нулей.|  
|*hh*|Количество часов в диапазоне от "00" до "23".|  
|*mm*|Количество минут в диапазоне от "00" до "59".|  
|*ss*|Количество секунд в диапазоне от "0" до "59".|  
|*fffffff*|Необязательная доля секунды.  Это значение может входит в диапазон от "0000001» (от одной десятимиллионной секунды) до "9999999" (до 9 999 999 десятимиллионных секунды).|  
  
 В отличие от описателей формата "g" и "G" описатель формата "c" не учитывает язык и региональные параметры. Он создает строковое представление значения <xref:System.TimeSpan>, которое является инвариантным и общим для всех предыдущих версий платформы .NET Framework до выхода .NET Framework 4. c — это строка формата <xref:System.TimeSpan> по умолчанию. Метод <xref:System.TimeSpan.ToString?displayProperty=nameWithType> форматирует значение временного интервала с помощью строки формата c.  
  
> [!NOTE]
> <xref:System.TimeSpan> также поддерживает строки стандартного формата "t" и "T", которые идентичны поведению строки стандартного формата "c".  
  
 В следующем примере создаются два объекта <xref:System.TimeSpan>, которые используются для выполнения арифметических операций, после чего выводится результат. В каждом случае используется составное форматирование для отображения значения <xref:System.TimeSpan> с помощью описателя формата "c".  
  
 [!code-csharp[Conceptual.TimeSpan.Standard#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.standard/cs/standardc1.cs#1)]
 [!code-vb[Conceptual.TimeSpan.Standard#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.standard/vb/standardc1.vb#1)]  

## <a name="the-general-short-g-format-specifier"></a>Описатель общего короткого ("g") формата  
 Описатель формата "g" <xref:System.TimeSpan> возвращает строковое представление значения <xref:System.TimeSpan> в компактной форме, включая только необходимые элементы. Представление имеет следующую форму:  
  
 [-][*d*:]*h*:*mm*:*ss*[.*FFFFFFF*]  
  
 Элементы в квадратных скобках ([и]) являются необязательными. Двоеточие (:) является литеральным символом. В следующей таблице описываются остальные элементы.  
  
|Элемент|ОПИСАНИЕ|  
|-------------|-----------------|  
|*-*|Необязательный знак минуса, который означает отрицательный интервал времени.|  
|*d*|Необязательное число дней без предшествующих нулей.|  
|*h*|Количество часов в диапазоне от "0" до "23" без предшествующих нулей.|  
|*mm*|Количество минут в диапазоне от "00" до "59".|  
|*ss*|Количество секунд в диапазоне от "00" до "59".|  
|*.*|Разделитель долей секунд. Является эквивалентом для свойства <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A> указанного языка и региональных параметров без переопределения пользователем.|  
|*FFFFFFF*|Доли секунд. Отображается как можно меньше цифр.|  
  
 Как и описатель формата "G", описатель формата "g" является локализуемым. Его разделитель долей секунд зависит от текущего языка и региональных параметров или свойства <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A> указанного языка и региональных параметров.  
  
 В следующем примере создаются два объекта <xref:System.TimeSpan>, которые используются для выполнения арифметических операций, после чего выводится результат. В каждом случае используется составное форматирование для отображения значения <xref:System.TimeSpan> с помощью описателя формата "g". Кроме того, он форматирует значение <xref:System.TimeSpan> с использованием соглашений о форматировании текущего системного языка и региональных параметров (в данном случае это английский язык, США или en-US) и французского языка, Франция (fr-FR).  
  
 [!code-csharp[Conceptual.TimeSpan.Standard#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.standard/cs/standardshort1.cs#4)]
 [!code-vb[Conceptual.TimeSpan.Standard#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.standard/vb/standardshort1.vb#4)]  

## <a name="the-general-long-g-format-specifier"></a>Описатель общего длинного ("G") формата  
 Описатель формата "G" <xref:System.TimeSpan> возвращает строковое представление значения <xref:System.TimeSpan> в длинной форме, которая всегда включает и дни, и доли секунд. Строка, которая является результатом описателя стандартного формата "G" имеет следующий вид:  
  
 [-]*d*:*hh*:*mm*:*ss*.*fffffff*  
  
 Элементы в квадратных скобках ([и]) являются необязательными. Двоеточие (:) является литеральным символом. В следующей таблице описываются остальные элементы.  
  
|Элемент|ОПИСАНИЕ|  
|-------------|-----------------|  
|*-*|Необязательный знак минуса, который означает отрицательный интервал времени.|  
|*d*|Число дней без предшествующих нулей.|  
|*hh*|Количество часов в диапазоне от "00" до "23".|  
|*mm*|Количество минут в диапазоне от "00" до "59".|  
|*ss*|Количество секунд в диапазоне от "00" до "59".|  
|*.*|Разделитель долей секунд. Является эквивалентом для свойства <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A> указанного языка и региональных параметров без переопределения пользователем.|  
|*fffffff*|Доли секунд.|  
  
 Как и описатель формата "G", описатель формата "g" является локализуемым. Его разделитель долей секунд зависит от текущего языка и региональных параметров или свойства <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A> указанного языка и региональных параметров.  
  
 В следующем примере создаются два объекта <xref:System.TimeSpan>, которые используются для выполнения арифметических операций, после чего выводится результат. В каждом случае используется составное форматирование для отображения значения <xref:System.TimeSpan> с помощью описателя формата "G". Кроме того, он форматирует значение <xref:System.TimeSpan> с использованием соглашений о форматировании текущего системного языка и региональных параметров (в данном случае это английский язык, США или en-US) и французского языка, Франция (fr-FR).  
  
 [!code-csharp[Conceptual.TimeSpan.Standard#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.standard/cs/standardlong1.cs#5)]
 [!code-vb[Conceptual.TimeSpan.Standard#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.standard/vb/standardlong1.vb#5)]
  
## <a name="see-also"></a>См. также

- [Типы форматирования](../../../docs/standard/base-types/formatting-types.md)
- [Строки настраиваемого формата TimeSpan](../../../docs/standard/base-types/custom-timespan-format-strings.md)
- [Parsing Strings](../../../docs/standard/base-types/parsing-strings.md)
