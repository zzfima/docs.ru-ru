---
title: "Пример регулярного выражения. Поиск ссылок HREF"
description: "Пример регулярного выражения. Поиск ссылок HREF"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: d6484880-bdac-47cd-b5e5-9419c9ed14cd
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 494ceeb2cc3bbf77098d2b6145690e7229ed3b9f

---

# <a name="regular-expression-example-scanning-for-hrefs"></a>Пример регулярного выражения. Поиск ссылок HREF

В следующем примере показаны поиск и вывод всех значений href="...", а также их позиций в строке. 

## <a name="the-regex-object"></a>Объект Regex

Поскольку метод `DumpHRefs` может быть вызван из пользовательского кода несколько раз, используется метод `static` [Regex.Match(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions)). Это позволяет обработчику регулярных выражений кэшировать регулярное выражение и избежать дополнительной нагрузки, связанной с созданием объекта [Regex](xref:System.Text.RegularExpressions.Regex) при каждом вызове метода. Затем объект [Match](xref:System.Text.RegularExpressions.Match) используется для итерации по всем совпадениям в строке. 

```csharp
private static void DumpHRefs(string inputString) 
{
   Match m;
   string HRefPattern = "href\\s*=\\s*(?:[\"'](?<1>[^\"']*)[\"']|(?<1>\\S+))";

   try {
      m = Regex.Match(inputString, HRefPattern, 
                      RegexOptions.IgnoreCase | RegexOptions.Compiled, 
                      TimeSpan.FromSeconds(1));
      while (m.Success)
      {
         Console.WriteLine("Found href " + m.Groups[1] + " at " 
            + m.Groups[1].Index);
         m = m.NextMatch();
      }   
   }
   catch (RegexMatchTimeoutException) {
      Console.WriteLine("The matching operation timed out.");
   }
}
```

```vb
Private Sub DumpHRefs(inputString As String) 
   Dim m As Match
   Dim HRefPattern As String = "href\s*=\s*(?:[""'](?<1>[^""']*)[""']|(?<1>\S+))"

   Try
      m = Regex.Match(inputString, HRefPattern, _ 
                      RegexOptions.IgnoreCase Or RegexOptions.Compiled,
                      TimeSpan.FromSeconds(1))
      Do While m.Success
         Console.WriteLine("Found href {0} at {1}.", _
                           m.Groups(1), m.Groups(1).Index)
         m = m.NextMatch()
      Loop   
   Catch e As RegexMatchTimeoutException
      Console.WriteLine("The matching operation timed out.")
   End Try
End Sub
```

В следующем примере показан вызов метода `DumpHRefs`.

```csharp
public static void Main()
{
   string inputString = "My favorite web sites include:</P>" +
                        "<A HREF=\"http://msdn2.microsoft.com\">" +
                        "MSDN Home Page</A></P>" +
                        "<A HREF=\"http://www.microsoft.com\">" +
                        "Microsoft Corporation Home Page</A></P>" +
                        "<A HREF=\"http://blogs.msdn.com/bclteam\">" +
                        ".NET Base Class Library blog</A></P>";
   DumpHRefs(inputString);                     

}
// The example displays the following output:
//       Found href http://msdn2.microsoft.com at 43
//       Found href http://www.microsoft.com at 102
//       Found href http://blogs.msdn.com/bclteam at 176
```

```vb
Public Sub Main()
   Dim inputString As String = "My favorite web sites include:</P>" & _
                               "<A HREF=""http://msdn2.microsoft.com"">" & _
                               "MSDN Home Page</A></P>" & _
                               "<A HREF=""http://www.microsoft.com"">" & _
                               "Microsoft Corporation Home Page</A></P>" & _
                               "<A HREF=""http://blogs.msdn.com/bclteam"">" & _
                               ".NET Base Class Library blog</A></P>"
   DumpHRefs(inputString)                     
End Sub
' The example displays the following output:
'       Found href http://msdn2.microsoft.com at 43
'       Found href http://www.microsoft.com at 102
'       Found href http://blogs.msdn.com/bclteam/) at 176
```

Возможные интерпретации шаблона регулярного выражения `href\s*=\s*(?:["']&#40;?<1>[^"']*)["']|(?<1>\S+))` показаны в следующей таблице.

Шаблон | Описание
------- | ----------- 
`href` | Совпадение с литеральной строкой "href". Сопоставление не учитывает регистр.
`\s*` | Соответствует нулю или нескольким символам пробела.
`=` |Соответствует знаку равенства.
`\s*` | Соответствует нулю или нескольким символам пробела.
`(?:["']&#40;?<1>[^"']*)"&#124;(?<1>\S+))` | Соответствует одному из следующих знаков без назначения результата захваченной группе: одиночные кавычки или апостроф, за которыми следует ноль или несколько вхождений любого символа, отличного от одиночных кавычек или апострофа, за которыми следуют кавычки или апостроф. В этот шаблон включена группа с именем `1`. Один или более символов, которые не являются пробелами. В этот шаблон включена группа с именем `1`.
`(?<1>[^"']*)` | Присвоить ноль или несколько любых символов, кроме кавычки или апострофа, группе записи `1`.
`"(?<1>\S+)` | Присвоить один или несколько символов, отличных от пробела, захваченной группе с именем `1`.
 
## <a name="match-result-class"></a>Класс результата поиска

Результаты поиска сохраняются в классе [Match](xref:System.Text.RegularExpressions.Match), который предоставляет доступ ко всем подстрокам, извлеченным в ходе поиска. Также запоминается искомая строка и используемое регулярное выражение, поэтому можно вызвать метод [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch) для выполнения другого поиска, начиная с того места, где закончился предыдущий.

## <a name="explicitly-named-captures"></a>Явно именованные шаблоны

В обычных регулярных выражениях круглые скобки, обозначающие отдельные шаблоны, автоматически последовательно нумеруются. В связи с этим возникают две проблемы. Во-первых, если регулярное выражение изменяется из-за вставки или удаления пары круглых скобок, все части кода, которые ссылаются на нумерованные шаблоны, необходимо переписать, чтобы отразить новую нумерацию. Во-вторых, вследствие того, что различные пары круглых скобок часто используются для определения двух альтернативных выражений для поиска, трудно определить, какое из двух выражений в действительности вернуло результат.

Для решения этих проблем класс [Regex](xref:System.Text.RegularExpressions.Regex) поддерживает синтаксис `(?<name>…)`, с помощью которого найденное совпадение можно сохранить в указанной ячейке (которой можно присвоить строковое имя или целочисленное обозначение; целые числа при этом работают быстрее). Таким образом, если совпадение будет найдено повторно, оно попадет в ту же ячейку. В случае конфликта успешным является то совпадение, которое было помещено в ячейку последним. (Однако доступен и полный список совпадений для одной ячейки. Дополнительные сведения см. в коллекции [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures).)

## <a name="see-also"></a>См. также

[Регулярные выражения .NET](regular-expressions.md)

[Примеры регулярных выражений](regex-examples.md)




<!--HONumber=Nov16_HO3-->


