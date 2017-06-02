---
title: "Таблица форматирования числовых результатов (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
- Console.Write method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: a3e5d2eef3f0a76fc8e3faa52feca827070a9cab
ms.contentlocale: ru-ru
ms.lasthandoff: 05/10/2017

---
# <a name="formatting-numeric-results-table-c-reference"></a>Таблица форматирования числовых результатов (Справочник по C#)
Для форматирования результатов можно воспользоваться методом <xref:System.String.Format%2A?displayProperty=fullName>, а также методом <xref:System.Console.Write%2A?displayProperty=fullName> или <xref:System.Console.WriteLine%2A?displayProperty=fullName>, вызывающим метод `String.Format`. Формат задается с помощью строк формата. В следующей таблице приведены поддерживаемые строки стандартных форматов. Строка формата принимает следующую форму: `Axx`, где `A` — описатель формата, а `xx` — описатель точности. Описатель формата управляет типом форматирования, применяемым к числовому значению, а описатель точности управляет количеством значащих цифр или десятичных знаков форматированного результата. Значение описателя точности находится в диапазоне от 0 до 99.  
  
 Дополнительные сведения о строках стандартных и пользовательских форматов см. в разделе [Типы форматирования](../../../standard/base-types/formatting-types.md). Дополнительные сведения о методе `String.Format` см. в разделе <xref:System.String.Format%2A?displayProperty=fullName>.  
  
|Описатель формата|Описание|Примеры|Вывод|  
|----------------------|-----------------|--------------|------------|  
|C или c|Валюта|Console.Write("{0:C}", 2.5);<br /><br /> Console.Write("{0:C}", -2.5);|$2.50<br /><br /> ($2.50)|  
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
