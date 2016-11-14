---
title: "Конструкции обратных ссылок в регулярных выражениях"
description: "Конструкции обратных ссылок в регулярных выражениях"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: c453ed78-650f-4c3c-9ab4-9d89d250bf88
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: f55ea60d11abcfce4b5fb502e66c513646707bef

---

# <a name="backreference-constructs-in-regular-expressions"></a>Конструкции обратных ссылок в регулярных выражениях

Обратные ссылки предоставляют удобный способ идентификации повторяющегося символа или подстроки в строке. Например, если входная строка содержит несколько экземпляров произвольной подстроки, можно найти первое вхождение с помощью группы записи, а затем использовать обратную ссылку для поиска последующих вхождений подстроки. 

> [!NOTE]
> Для ссылки на именованные и нумерованные захватываемые группы в строках замены используется отдельный синтаксис. Дополнительные сведения см. в статье [Подстановки в регулярных выражениях](substitutions.md).
 
.NET определяет отдельные элементы языка для ссылки на нумерованные и именованные захватываемые группы. Дополнительные сведения о захватываемых группах см. в статье [Конструкции группировки в регулярных выражениях](grouping.md).

## <a name="numbered-backreferences"></a>Нумерованные обратные ссылки

Нумерованная обратная ссылка использует следующий синтаксис:

**\**_число_

где *число* — это порядковое положение захватываемой группы в регулярном выражении. Например, `\4` соответствует содержимому четвертой захватываемой группы. Если *number* не определен в шаблоне регулярного выражения, возникает ошибка синтаксического анализа, и обработчик регулярных выражений создает исключение [ArgumentException](xref:System.ArgumentException). Например, регулярное выражение `\b(\w+)\s\1` является допустимым, поскольку `(\w+)` — это первая и единственная захватываемая группа в выражении. С другой стороны, выражение `\b(\w+)\s\2` недопустимо и создает исключение аргумента, так как захватываемая группа с номером `\2` отсутствует.

Следует отметить неоднозначность такой записи, используемой как в восьмеричных escape-кодах (например, `\16`), так и в обратных ссылках **\**_number_. Эта неопределенность разрешается следующим образом:

* Выражения с `\1` по `\9` всегда интерпретируются как обратные ссылки, а не как восьмеричные коды.

* Если первая цифра многоразрядного выражения — 8 или 9 (например, `\80` или `\91`), выражение интерпретируется как литерал.

* Выражения от `\10` и более считаются обратными ссылками, если имеется обратная ссылка, соответствующая этому номеру. В противном случае они интерпретируются как восьмеричные коды.

* Если регулярное выражение содержит обратную ссылку на неопределенный номер группы, возникает ошибка синтаксического анализа, и обработчик регулярных выражений создает исключение [ArgumentException](xref:System.ArgumentException).

Если неоднозначность представляет проблему, можно использовать представление **\k<**_name_**>**, которое является однозначным, и его невозможно спутать с восьмеричными кодами знаков. Аналогичным образом шестнадцатеричные коды, например `\xdd`, однозначны, и их нельзя спутать с обратными ссылками.

В приведенном ниже примере в строке выделяются двойные словообразующие символы. Здесь определяется регулярное выражение, `(\w)\1,`, которое состоит из следующих элементов.

Элемент | Описание
------- | -----------
`(\w)` | Совпадение со словообразующим символом и его назначение первой захватываемой группе.
`\1` | Совпадение со следующим символом, значение которого совпадает с первой захватываемой группой.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"(\w)\1";
      string input = "trellis llama webbing dresser swagger";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("Found '{0}' at position {1}.", 
                           match.Value, match.Index);
   }
}
// The example displays the following output:
//       Found 'll' at position 3.
//       Found 'll' at position 8.
//       Found 'bb' at position 16.
//       Found 'ss' at position 25.
//       Found 'gg' at position 33.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(\w)\1"
      Dim input As String = "trellis llama webbing dresser swagger"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Found '{0}' at position {1}.", _
                           match.Value, match.Index)
      Next   
   End Sub
End Module
' The example displays the following output:
'       Found 'll' at position 3.
'       Found 'll' at position 8.
'       Found 'bb' at position 16.
'       Found 'ss' at position 25.
'       Found 'gg' at position 33.
```

## <a name="named-backreferences"></a>Именованные обратные ссылки

Именованная обратная ссылка задается с помощью следующего синтаксиса:

**\k<**_name_**>**

или

**\k'**_name_**'**

где *name*— это имя захватываемой группы, определенное в шаблоне регулярного выражения. Если значение *name* не определено в шаблоне регулярного выражения, возникает ошибка синтаксического анализа, и обработчик регулярных выражений создает исключение [ArgumentException](xref:System.ArgumentException).

В приведенном ниже примере в строке выделяются двойные словообразующие символы. Здесь определяется регулярное выражение, `(?<char>\w)\k<char>`, которое состоит из следующих элементов.

Элемент | Описание
------- | -----------
`(?<char>\w)` | Совпадение со словообразующим символом и его назначение захватываемой группе с именем char.
`\k<char>` | Совпадение со следующим символом, значение которого совпадает с первой захватываемой группой char.
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"(?<char>\w)\k<char>";
      string input = "trellis llama webbing dresser swagger";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("Found '{0}' at position {1}.", 
                           match.Value, match.Index);
   }
}
// The example displays the following output:
//       Found 'll' at position 3.
//       Found 'll' at position 8.
//       Found 'bb' at position 16.
//       Found 'ss' at position 25.
//       Found 'gg' at position 33.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(?<char>\w)\k<char>"
      Dim input As String = "trellis llama webbing dresser swagger"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Found '{0}' at position {1}.", _
                           match.Value, match.Index)
      Next   
   End Sub
End Module
' The example displays the following output:
'       Found 'll' at position 3.
'       Found 'll' at position 8.
'       Found 'bb' at position 16.
'       Found 'ss' at position 25.
'       Found 'gg' at position 33.
```

Обратите внимание, что *name* также может быть строковым представлением числа. Например, далее используется регулярное выражение `(?<2>\w)\k<2>` для поиска в строке двойных словообразующих символов.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"(?<2>\w)\k<2>";
      string input = "trellis llama webbing dresser swagger";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("Found '{0}' at position {1}.", 
                           match.Value, match.Index);
   }
}
// The example displays the following output:
//       Found 'll' at position 3.
//       Found 'll' at position 8.
//       Found 'bb' at position 16.
//       Found 'ss' at position 25.
//       Found 'gg' at position 33.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(?<2>\w)\k<2>"
      Dim input As String = "trellis llama webbing dresser swagger"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Found '{0}' at position {1}.", _
                           match.Value, match.Index)
      Next   
   End Sub
End Module
' The example displays the following output:
'       Found 'll' at position 3.
'       Found 'll' at position 8.
'       Found 'bb' at position 16.
'       Found 'ss' at position 25.
'       Found 'gg' at position 33.
```

## <a name="what-backreferences-match"></a>С чем сопоставляются обратные ссылки

Обратная ссылка относится к самому недавнему определению группы (самому ближнему слева определению при обработке слева направо). Если из группы создается несколько шаблонов для поиска, обратная ссылка относится к самому последнему шаблону. 

В примере ниже показан шаблон регулярного выражения `(?<1>a)(?<1>\1b)*`, который переопределяет именованную группу \1. В следующей таблице описывается каждый шаблон регулярного выражения. 

Шаблон | Описание
------- | -----------
`(?<1>a)` | Совпадение с символом "a" и назначение результата захватываемой группе с именем 1.
`(?<1>\1b)*` |Совпадение с нулевым или единичным вхождением группы с именем 1 вместе с "b" и назначение результата захватываемой группе с именем 1. 
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"(?<1>a)(?<1>\1b)*";
      string input = "aababb";
      foreach (Match match in Regex.Matches(input, pattern))
      {
         Console.WriteLine("Match: " + match.Value);
         foreach (Group group in match.Groups)
            Console.WriteLine("   Group: " + group.Value);
      }
   }
}
// The example displays the following output:
//          Group: aababb
//          Group: abb
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(?<1>a)(?<1>\1b)*"
      Dim input As String = "aababb"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Match: " + match.Value)
         For Each group As Group In match.Groups
            Console.WriteLIne("   Group: " + group.Value)
         Next
      Next
   End Sub
End Module
' The example display the following output:
'          Group: aababb
'          Group: abb
```

При сравнении регулярного выражения с входной строкой ("aababb") обработчик регулярных выражений выполняет указанные далее операции.

1. Начинается с первого символа и успешно сопоставляет "a" с выражением `(?<1>a)`. Теперь значение группы 1 будет равно "a".

2. Перемещается ко второму символу и успешно сопоставляет строку "ab" с выражением `\1b` или "ab". Затем результат "ab" присваивается `\1`.

3. Переходит к четвертому символу. Выражение `(?<1>\1b)` должно выдать ноль или больше совпадений, поэтому он успешно сопоставляет строку "abb" с выражением `\1b`. Затем результат "abb" присваивается `\1`.

В этом примере \* является циклическим квантификатором — он вычисляется многократно до тех пор, пока обработчик регулярных выражений не сможет обнаружить соответствие заданному им шаблону. Квантификаторы циклов не удаляют определения групп.

Если для группы не было найдено ни одной подстроки, то обратная ссылка на эту группу не определена и не работает. Это продемонстрировано в шаблоне регулярного выражения `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b,`, который определяется следующим образом:

Шаблон | Описание
------- | -----------
`\b` | Сопоставление начинается на границе слова.
`(\p{Lu}{2})` | Совпадение с двумя прописными буквами. Это первая группа записи.
`(\d{2})?` | Совпадение с нулевым или единичным вхождением двух десятичных цифр. Это вторая группа записи.
`(\p{Lu}{2})` | Совпадение с двумя прописными буквами. Это третья группа записи.
`\b` | Сопоставление заканчивается на границе слова.

Входная строка может соответствовать этому регулярному выражению, даже если отсутствуют две десятичные цифры, которые заданы второй захватываемой группой. В следующем примере показано, что даже несмотря на то, что сопоставление является успешным, между двумя группами успешной записи найдена пустая группа.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b";
      string[] inputs = { "AA22ZZ", "AABB" };
      foreach (string input in inputs)
      {
         Match match = Regex.Match(input, pattern);
         if (match.Success)
         {
            Console.WriteLine("Match in {0}: {1}", input, match.Value);
            if (match.Groups.Count > 1)
            {
               for (int ctr = 1; ctr <= match.Groups.Count - 1; ctr++)
               {
                  if (match.Groups[ctr].Success)
                     Console.WriteLine("Group {0}: {1}", 
                                       ctr, match.Groups[ctr].Value);
                  else
                     Console.WriteLine("Group {0}: <no match>", ctr);
               }
            }
         }
         Console.WriteLine();
      }      
   }
}
// The example displays the following output:
//       Match in AA22ZZ: AA22ZZ
//       Group 1: AA
//       Group 2: 22
//       Group 3: ZZ
//       
//       Match in AABB: AABB
//       Group 1: AA
//       Group 2: <no match>
//       Group 3: BB
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b"
      Dim inputs() As String = { "AA22ZZ", "AABB" }
      For Each input As String In inputs
         Dim match As Match = Regex.Match(input, pattern)
         If match.Success Then
            Console.WriteLine("Match in {0}: {1}", input, match.Value)
            If match.Groups.Count > 1 Then
               For ctr As Integer = 1 To match.Groups.Count - 1
                  If match.Groups(ctr).Success Then
                     Console.WriteLine("Group {0}: {1}", _
                                       ctr, match.Groups(ctr).Value)
                  Else
                     Console.WriteLine("Group {0}: <no match>", ctr)
                  End If      
               Next
            End If
         End If
         Console.WriteLine()
      Next      
   End Sub
End Module
' The example displays the following output:
'       Match in AA22ZZ: AA22ZZ
'       Group 1: AA
'       Group 2: 22
'       Group 3: ZZ
'       
'       Match in AABB: AABB
'       Group 1: AA
'       Group 2: <no match>
'       Group 3: BB
```

## <a name="see-also"></a>См. также

[Элементы языка регулярных выражений — краткий справочник](quick-ref.md)




<!--HONumber=Nov16_HO1-->


