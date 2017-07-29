---
title: "Практическое руководство. Преобразование строки в число (руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- conversions [C#]
- conversions [C#], string to int
- converting strings to int [C#]
- strings [C#], converting to int
ms.assetid: 467b9979-86ee-4afd-b734-30299cda91e3
caps.latest.revision: 34
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 08d13e40a385ce8e9011b508b04361b2e050f904
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-a-string-to-a-number-c-programming-guide"></a>Практическое руководство. Преобразование строки в число (руководство по программированию в C#)
Вы можете преобразовывать [строку](../../../csharp/language-reference/keywords/string.md) в число с помощью методов в классе <xref:System.Convert> или с помощью метода `TryParse`, который можно найти в различных числовых типах (int, long, float и т. д.).  
  
 Если имеется строка, то немного более эффективно и проще вызвать метод `TryParse` (например, `int.TryParse("11")`).  Использование метода `Convert` более удобно для общих объектов, реализующих <xref:System.IConvertible>.  
  
 Вы можете использовать методы `Parse` или `TryParse` в числовом типе, который предположительно содержит строка, таком как тип <xref:System.Int32?displayProperty=fullName>.  Метод <xref:System.Convert.ToUInt32%2A?displayProperty=fullName> использует <xref:System.Int32.Parse%2A> внутри себя.  Если строка имеет недопустимый формат, `Parse` создает исключение, а `TryParse` возвращает значение [false](../../../csharp/language-reference/keywords/false.md).  
  
## <a name="example"></a>Пример  
 Методы `Parse` и `TryParse` игнорируют пробелы в начале и в конце строки, но все остальные символы должны быть символами, которые образуют соответствующий числовой тип (int, long, ulong, float, decimal и т. д.).  Любые пробелы в символах, образующих число, приводят к ошибке.  Например, можно использовать `decimal.TryParse` для анализа "10", "10.3", "  10  ", но этот метод нельзя использовать для анализа 10 из "10X", "1 0" (обратите внимание на пробел), "10 .3" (обратите внимание на пробел), "10e1" (здесь работает `float.TryParse`) и т. д.  
  
 В приведенных ниже примерах демонстрируются успешные и неуспешные вызовы методов `Parse` и `TryParse`.  
  
 [!code-cs[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]  
[!code-cs[csProgGuideTypes#25](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_2.cs)]  
[!code-cs[csProgGuideTypes#26](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_3.cs)]  
[!code-cs[csProgGuideTypes#27](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_4.cs)]  
[!code-cs[csProgGuideTypes#28](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_5.cs)]  
[!code-cs[csProgGuideTypes#100](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_6.cs)]  
  
## <a name="example"></a>Пример  
 В следующей таблице перечислены некоторые методы класса <xref:System.Convert>, которые можно использовать.  
  
|Числовой тип|Метод|  
|------------------|------------|  
|`decimal`|<xref:System.Convert.ToDecimal%28System.String%29>|  
|`float`|<xref:System.Convert.ToSingle%28System.String%29>|  
|`double`|<xref:System.Convert.ToDouble%28System.String%29>|  
|`short`|<xref:System.Convert.ToInt16%28System.String%29>|  
|`int`|<xref:System.Convert.ToInt32%28System.String%29>|  
|`long`|<xref:System.Convert.ToInt64%28System.String%29>|  
|`ushort`|<xref:System.Convert.ToUInt16%28System.String%29>|  
|`uint`|<xref:System.Convert.ToUInt32%28System.String%29>|  
|`ulong`|<xref:System.Convert.ToUInt64%28System.String%29>|  
  
 В данном примере вызывается метод <xref:System.Convert.ToInt32%28System.String%29?displayProperty=fullName> для преобразования входных данных типа [string](../../../csharp/language-reference/keywords/string.md) в значение типа [int](../../../csharp/language-reference/keywords/int.md). Код перехватывает два наиболее распространенных исключения, которые могут создаваться этим методом, — <xref:System.FormatException> и <xref:System.OverflowException>. Если число может быть увеличено без переполнения места хранения целого числа, программа добавляет к результату 1 и печатает выходные данные.  
  
 [!code-cs[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]  
[!code-cs[csProgGuideTypes#24](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_7.cs)]  
  
## <a name="see-also"></a>См. также  
 [Типы](../../../csharp/programming-guide/types/index.md)   
 [Практическое руководство. Определение представления числового значения в строке](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)   
 [Служебная программа форматирования .NET Framework 4](http://code.msdn.microsoft.com/NET-Framework-4-Formatting-9c4dae8d)

