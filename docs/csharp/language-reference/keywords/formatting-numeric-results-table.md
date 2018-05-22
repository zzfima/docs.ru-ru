---
title: Таблица форматирования числовых результатов (Справочник по C#)
ms.date: 07/20/2015
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
- Console.Write method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
ms.openlocfilehash: cc215971d63a0ee61eb25ac45834a81fbbc50b96
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="formatting-numeric-results-table-c-reference"></a>Таблица форматирования числовых результатов (Справочник по C#)
Для форматирования результатов можно воспользоваться методом <xref:System.String.Format%2A?displayProperty=nameWithType>, методами <xref:System.Console.Write%2A?displayProperty=nameWithType> или <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, вызывающими `String.Format`, или [интерполяцией строк](../tokens/interpolated.md). Формат задается с помощью строк формата. В следующей таблице приведены поддерживаемые строки стандартных форматов. Строка формата принимает следующую форму: `Axx`, где `A` — описатель формата, а `xx` — описатель точности. Описатель формата управляет типом форматирования, применяемым к числовому значению, а описатель точности управляет количеством значащих цифр или десятичных знаков форматированного результата. Значение описателя точности находится в диапазоне от 0 до 99.  
  
 Дополнительные сведения о строках стандартных и пользовательских форматов см. в разделе [Типы форматирования](../../../standard/base-types/formatting-types.md).
  
|Описатель формата|Описание:|Примеры|Вывод|  
|----------------------|-----------------|--------------|------------|  
|C или c|Валюта|Console.Write("{0:C}", 2.5);<br /><br /> Console.Write("{0:C}", −2.5);|$2.50<br /><br /> ($2.50)|  
|D или d|Десятичное число|Console.Write("{0:D5}", 25);|00025|  
|E или e|Экспоненциальный|Console.Write("{0:E}", 250000);|2.500000E+005|  
|F или f|С фиксированной запятой|Console.Write("{0:F2}", 25);<br /><br /> Console.Write("{0:F0}", 25);|25.00<br /><br /> 25|  
|G или g|Общие|Console.Write("{0:G}", 2.5);|2.5|  
|N или n|Число|Console.Write("{0:N}", 2500000);|2,500,000.00|  
|X или x|Шестнадцатеричный|Console.Write("{0:X}", 250);<br /><br /> Console.Write("{0:X}", 0xffff);|FA<br /><br /> FFFF|  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Строки стандартных числовых форматов](../../../standard/base-types/standard-numeric-format-strings.md)  
 [Справочные таблицы по типам](../../../csharp/language-reference/keywords/reference-tables-for-types.md)  
 [string](../../../csharp/language-reference/keywords/string.md)
