---
title: Практическое руководство. Преобразование строки в число - руководство по программированию на C#
ms.custom: seodec18
ms.date: 02/11/2019
helpviewer_keywords:
- conversions [C#]
- conversions [C#], string to int
- converting strings to int [C#]
- strings [C#], converting to int
ms.assetid: 467b9979-86ee-4afd-b734-30299cda91e3
ms.openlocfilehash: c39602afbece4faaf6599a5c76f5746defffe03a
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73417635"
---
# <a name="how-to-convert-a-string-to-a-number-c-programming-guide"></a>Практическое руководство. Преобразование строки в число (руководство по программированию на C#)

Вы можете преобразовывать [строку](../../language-reference/builtin-types/reference-types.md) в число с помощью вызова метода `Parse` или `TryParse`, который можно найти в различных числовых типах (`int`, `long`, `double` и т. д.), или используя методы в классе <xref:System.Convert?displayProperty=nameWithType>.  
  
 Если имеется строка, то немного эффективнее и проще вызвать метод `TryParse` (например, [`int.TryParse("11", out number)`](xref:System.Int32.TryParse%2A)) или метод `Parse` (например, [`var number = int.Parse("11")`](xref:System.Int32.Parse%2A)).  Использование метода <xref:System.Convert> более удобно для общих объектов, реализующих <xref:System.IConvertible>.  
  
 Вы можете использовать методы `Parse` или `TryParse` в числовом типе, который предположительно содержит строка, таком как тип <xref:System.Int32?displayProperty=nameWithType>.  Метод <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> использует <xref:System.Int32.Parse%2A> внутри себя.  Метод `Parse` возвращает преобразованное число; метод `TryParse` возвращает значение <xref:System.Boolean>, которое указывает, успешно ли выполнено преобразование, и возвращает преобразованное число в [параметр`out`](../../language-reference/keywords/out.md). Если строка имеет недопустимый формат, `Parse` создает исключение, а `TryParse` возвращает значение [false](../../language-reference/keywords/false-literal.md). В случае сбоя операции синтаксического анализа при вызове метода `Parse` вы всегда должны использовать обработку исключений, чтобы перехватить <xref:System.FormatException>.  
  
## <a name="calling-the-parse-and-tryparse-methods"></a>Вызов методов Parse и TryParse

Методы `Parse` и `TryParse` игнорируют пробелы в начале и в конце строки, но все остальные символы должны быть символами, которые образуют соответствующий числовой тип (`int`, `long`, `ulong`, `float`, `decimal` и т. д.).  Любые пробелы в строке, образующие число, приводят к ошибке.  Например, можно использовать `decimal.TryParse` для анализа "10", "10.3" или "  10  ", но этот метод нельзя использовать для анализа 10 из "10X", "1 0" (обратите внимание на внедренный пробел), "10 .3" (обратите внимание на внедренный пробел), "10e1" (здесь работает `float.TryParse`) и т. д. Кроме того, строку со значением `null` или <xref:System.String.Empty?displayProperty=nameWithType> невозможно успешно проанализировать. Вы можете проверить наличие NULL или пустой строки, прежде чем пытаться ее проанализировать, вызвав метод <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType>. 

В указанном ниже примере демонстрируются успешные и неуспешные вызовы методов `Parse` и `TryParse`.  
  
[!code-csharp[Parse and TryParse](~/samples/snippets/csharp/programming-guide/string-to-number/parse-tryparse/program.cs)]  

В следующем примере показан один из подходов к анализу строки, которая, как ожидается, будет включать начальные числовые символы (включая шестнадцатеричные символы) и конечные нечисловые символы. Он назначает допустимые символы в начале новой строки перед вызовом метода <xref:System.Int32.TryParse%2A>. Поскольку анализируемые строки содержат небольшое количество символов, в примере вызывается метод <xref:System.String.Concat%2A?displayProperty=nameWithType> для назначения допустимых символов новой строке. Для большей строки можете использовать класс <xref:System.Text.StringBuilder>. 
  
[!code-csharp[Removing invalid characters](~/samples/snippets/csharp/programming-guide/string-to-number/parse-tryparse2/program.cs)]  

## <a name="calling-the-convert-methods"></a>Вызов методов Convert

В следующей таблице перечислены некоторые методы класса <xref:System.Convert>, которые можно использовать для преобразования строки в число.  
  
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
  
 В данном примере вызывается метод <xref:System.Convert.ToInt32%28System.String%29?displayProperty=nameWithType> для преобразования входных данных string в значение типа [int](../../language-reference/builtin-types/integral-numeric-types.md). Пример перехватывает два наиболее распространенных исключения, которые могут создаваться этим методом, — <xref:System.FormatException> и <xref:System.OverflowException>. Если итоговое число можно увеличить, не превышая <xref:System.Int32.MaxValue?displayProperty=nameWithType>, пример добавляет 1 к результату и отображает вывод.  
  
[!code-csharp[Parsing with Convert methods](~/samples/snippets/csharp/programming-guide/string-to-number/convert/program.cs)]  
  
## <a name="see-also"></a>См. также

- [Типы](./index.md)
- [Практическое руководство. Определение представления числового значения в строке](../strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
- [Пример: служебная программа форматирования .NET Core WinForms (C#)](https://docs.microsoft.com/samples/dotnet/samples/winforms-formatting-utility-cs)
