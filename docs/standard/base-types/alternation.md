---
title: "Конструкции изменения в регулярных выражениях"
description: "Конструкции изменения в регулярных выражениях"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 59ffac4d-fc6e-461f-8783-d9f8dc88ce2c
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 2c31622ff97f30e565ed2cd82128518d04d5d1dc

---

# <a name="alternation-constructs-in-regular-expressions"></a>Конструкции изменения в регулярных выражениях

Конструкции изменения модифицируют регулярное выражение, включая сопоставление по принципу «либо/или» или условное сопоставление. Платформа .NET поддерживает три указанные далее конструкции изменения.

* Сопоставление шаблонов с **|**

* Условное сопоставление с **(?(**_expression_**)**_yes_**|**_no_**)**

* Условное сопоставление на основе действительной захватываемой группы.

## <a name="pattern-matching-with-"></a>Сопоставление шаблонов с |

Можно использовать вертикальную черту (|) для сопоставления с любым набором шаблонов, где | отделяет каждый шаблон. 

Как и класс положительных символов, символ | можно использовать для сопоставления с любым количеством отдельных символов. В следующем примере используется класс положительных символов и сопоставление с шаблоном either/or (либо/или) с символом | для обнаружения в строке всех вхождений слов gray или grey. В этом случае символ | создает регулярное выражение, которое является более подробным. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      // Regular expression using character class.
      string pattern1 = @"\bgr[ae]y\b";
      // Regular expression using either/or.
      string pattern2 = @"\bgr(a|e)y\b";

      string input = "The gray wolf blended in among the grey rocks.";
      foreach (Match match in Regex.Matches(input, pattern1))
         Console.WriteLine("'{0}' found at position {1}", 
                           match.Value, match.Index);
      Console.WriteLine();
      foreach (Match match in Regex.Matches(input, pattern2))
         Console.WriteLine("'{0}' found at position {1}", 
                           match.Value, match.Index);
   }
}
// The example displays the following output:
//       'gray' found at position 4
//       'grey' found at position 35
//       
//       'gray' found at position 4
//       'grey' found at position 35           
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      ' Regular expression using character class.
      Dim pattern1 As String = "\bgr[ae]y\b"
      ' Regular expression using either/or.
      Dim pattern2 As String = "\bgr(a|e)y\b"

      Dim input As String = "The gray wolf blended in among the grey rocks."
      For Each match As Match In Regex.Matches(input, pattern1)
         Console.WriteLine("'{0}' found at position {1}", _
                           match.Value, match.Index)
      Next      
      Console.WriteLine()
      For Each match As Match In Regex.Matches(input, pattern2)
         Console.WriteLine("'{0}' found at position {1}", _
                           match.Value, match.Index)
      Next      
   End Sub
End Module
' The example displays the following output:
'       'gray' found at position 4
'       'grey' found at position 35
'       
'       'gray' found at position 4
'       'grey' found at position 35 
```

Возможные интерпретации регулярного выражения, использующего символ | (`\bgr(a|e)y\b,`), показаны в следующей таблице.

Шаблон | Описание
------- | -----------
`\b` | Начало на границе слова.
`gr` | Соответствует символам gr.
(a|e) | Соответствует букве "a" или "e".
`y\b` | Соответствует символу у на границе слова.


Символ | может также использоваться для выполнения сопоставления either/or (или/либо) с несколькими символами или частями выражения, которые могут включать любую комбинацию символьных литералов и элементов языка регулярных выражений. (Класс символов не предоставляет эту функцию). В следующем примере символ | используется для извлечения или номера социального страхования США (SSN), который представляет собой номер из 9 цифр в формате *ddd-dd-dddd*, или номер идентификации работодателя США (EIN), который состоит из 9 цифр в формате *dd-ddddddd*.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b";
      string input = "01-9999999 020-333333 777-88-9999";
      Console.WriteLine("Matches for {0}:", pattern);
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index);
   }
}
// The example displays the following output:
//       Matches for \b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b:
//          01-9999999 at position 0
//          777-88-9999 at position 22
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b"
      Dim input As String = "01-9999999 020-333333 777-88-9999"
      Console.WriteLine("Matches for {0}:", pattern)
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index)
      Next   
   End Sub
End Module
' The example displays the following output:
'       Matches for \b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b:
'          01-9999999 at position 0
'          777-88-9999 at position 22
```

Возможные интерпретации регулярного выражения `\b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` показаны в следующей таблице.

Шаблон | Описание
------- | -----------
`\b` | Начало на границе слова.
(\d{2}-\d{7}|;\d{3}-\d{2}-\d{4}) | Сопоставьте любые из следующих значений: два десятичных знака, за которыми следует дефис и еще семь десятичных знаков; или последовательность из трех десятичных знаков, дефиса, двух десятичных знаков, еще одного дефиса и четырех десятичных знаков. 
`\d` | Совпадение должно заканчиваться на границе слова.
                                         
## <a name="conditional-matching-with-an-expression"></a>Условное сопоставление с выражением

Этот элемент языка пытается сопоставить один из двух шаблонов в зависимости от того, может ли он сопоставить первоначальный шаблон. Он имеет следующий синтаксис:

**(?(**_expression_**)**_yes_**|**_no_**)**

где *expression* — первый сопоставляемый шаблон, *yes* — шаблон, который необходимо сопоставить, если сопоставлен шаблон expression, а *no* — это дополнительный шаблон, который необходимо сопоставить, если *expression* не сопоставлен. Обработчик регулярных выражений рассматривает *expression* как утверждение нулевой ширины, то есть обработчик регулярных выражений не перемещается в потоке входных значений после оценки *expression*. Следовательно, эта конструкция эквивалентна следующему.

**(?(?**=_expression_**)**_yes_**|**_no_**)**

где **(?**=_expression_**)** — это конструкция утверждения нулевой ширины. (Дополнительные сведения см. в статье [Конструкции группировки в регулярных выражениях](grouping.md).) Так как обработчик регулярных выражений интерпретирует *expression* как привязку (утверждение нулевой ширины), *expression* должно представлять собой утверждение нулевой ширины (дополнительные сведения см. в статье [Привязки в регулярных выражениях](anchors.md)) или как часть выражения, которая также содержится в шаблоне *yes*. В противном случае шаблон *yes* сопоставить невозможно. 

> [!NOTE]
> Если *expression* является именованной или нумерованной захватываемой группой, конструкция изменения интерпретируется как проверка захвата. Дополнительные сведения см. далее в разделе [Условное сопоставление на основе действительной захватываемой группы](#conditional-matching-based-on-a-valid-captured-group). Другими словами, обработчик регулярных выражений не пытается сопоставить захваченную часть строки, а вместо этого выполняет проверку на наличие или отсутствие группы.
 

Следующий пример является вариантом примера, который отображается в предыдущем подразделе. Условное сопоставление используется, чтобы определить, являются ли первые три символа после границы слова двумя цифрами и дефисом. Если да, предпринимается попытка сопоставить Идентификационный номер работодателя США (EIN). Если нет, предпринимается попытка сопоставить Номер социального страхования США (SSN).

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b";
      string input = "01-9999999 020-333333 777-88-9999";
      Console.WriteLine("Matches for {0}:", pattern);
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index);
   }
}
// The example displays the following output:
//       Matches for \b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b:
//          01-9999999 at position 0
//          777-88-9999 at position 22
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b"
      Dim input As String = "01-9999999 020-333333 777-88-9999"
      Console.WriteLine("Matches for {0}:", pattern)
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index)
      Next   
   End Sub
End Module
' The example displays the following output:
'       Matches for \b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b:
'          01-9999999 at position 0
'          777-88-9999 at position 22
```

Возможные интерпретации шаблона регулярного выражения `\b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` показаны в следующей таблице.

Шаблон | Описание
------- | -----------
`\b` | Начало на границе слова.
`(?(\d{2}-)` | Определите, состоят ли следующие три символа из двух цифр, за которыми следуют дефис.
`\d{2}-\d{7}` | Если предыдущий шаблон сопоставлен, сопоставьте две цифры с дефисом, за которыми следуют еще семь цифр.
`\d{3}-\d{2}-\d{4}` | Если предыдущий шаблон не сопоставлен, сопоставьте три цифры, дефис, две цифры, еще один дефис и еще четыре цифры. 
`\b` | Соответствует границе слова.
 
## <a name="conditional-matching-based-on-a-valid-captured-group"></a>Условное сопоставление на основе действительной захватываемой группы.

Этот элемент языка пытается сопоставить один из двух шаблонов, в зависимости от того, соответствует ли он указанной группе записи. Он имеет следующий синтаксис:

**(?(**_name_**)**_yes_**|**_no_**)**

или

**(?(**_number_**)**_yes_**|**_no_**)**

где *name* — имя, а *number* — номер захватываемой группы, *yes* — сопоставляемое выражение, если для name или number имеется соответствие, а *no* — это дополнительное выражение для сопоставления при отсутствии соответствия.

Если *name* не соответствует имени захватываемой группы, которая используется в шаблоне регулярного выражения, конструкция изменения интерпретируется как проверка выражения, как было описано в предыдущем разделе. Как правило, это означает, что expression имеет значение `false`. Если `number` не соответствует нумерованной захватываемой группе, используемой в шаблоне регулярного выражения, обработчик регулярных выражений создает исключение [ArgumentException](xref:System.ArgumentException).

Следующий пример является вариантом примера, который отображается в предыдущем подразделе. В нем используется захватываемая группа с именем `n2`, которая состоит из двух цифр и дефиса. Конструкция изменения проверяет, сопоставлена ли эта группа захвата в строке ввода. Если да, конструкция изменения пытается сопоставить последние семь цифр девятизначного Идентификационный номер работодателя США (EIN). В противном случае она пытается сопоставить девятизначный Номер социального страхования США (SSN).

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(?<n2>\d{2}-)*(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b";
      string input = "01-9999999 020-333333 777-88-9999";
      Console.WriteLine("Matches for {0}:", pattern);
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index);
   }
}
// The example displays the following output:
//       Matches for \b(?<n2>\d{2}-)*(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b:
//          01-9999999 at position 0
//          777-88-9999 at position 22
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(?<n2>\d{2}-)*(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b"
      Dim input As String = "01-9999999 020-333333 777-88-9999"
      Console.WriteLine("Matches for {0}:", pattern)
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index)
      Next   
   End Sub
End Module
```

Возможные интерпретации шаблона регулярного выражения `\b(?<n2>\d{2}-)*(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b` показаны в следующей таблице.

Шаблон | Описание
------- | -----------
`\b` | Начало на границе слова.
`(?<n2>\d{2}-)*` | Сопоставьте нулевое или единичное вхождение двух цифр с дефисом. Установка для группы имени `n2`.
`(?(n2)` | Проверка наличия сопоставления `n2` во входной строке. 
`)\d{7}` | Если есть сопоставление `n2`, сопоставляются семь десятичных цифр.
`|;\d{3}-\d{2}-\d{4} | Если сопоставления нет `n2`, сопоставляются три десятичных цифры, дефис, две десятичных цифры, еще один дефис и четыре десятичных цифры. 
`\b` | Соответствует границе слова.
 
В следующем примере показана вариация этого примера, в котором вместо именованной группы используется нумерованная. Шаблон регулярного выражения выглядит следующим образом: `\b(\d{2}-)*(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b`

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\d{2}-)*(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b";
      string input = "01-9999999 020-333333 777-88-9999";
      Console.WriteLine("Matches for {0}:", pattern);
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index);
   }
}
// The example display the following output:
//       Matches for \b(\d{2}-)*(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b:
//          01-9999999 at position 0
//          777-88-9999 at position 22
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\d{2}-)*(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b"
      Dim input As String = "01-9999999 020-333333 777-88-9999"
      Console.WriteLine("Matches for {0}:", pattern)
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index)
      Next   
   End Sub
End Module
' The example displays the following output:
'       Matches for \b(\d{2}-)*(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b:
'          01-9999999 at position 0
'          777-88-9999 at position 22
```

См. также

[Элементы языка регулярных выражений — краткий справочник](quick-ref.md)




<!--HONumber=Nov16_HO3-->


