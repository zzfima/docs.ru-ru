---
title: Как запросить символы в строке (LINQ) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 499ebbe0-746c-4235-9dba-ce722c12b50e
ms.openlocfilehash: f2102a8cb149fa9c7886826e509bf254fad5eb95
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582724"
---
# <a name="how-to-query-for-characters-in-a-string-linq-visual-basic"></a>Как запросить символы в строке (LINQ) (Visual Basic)

Поскольку класс <xref:System.String> реализует универсальный интерфейс <xref:System.Collections.Generic.IEnumerable%601>, любая строка может запрашиваться как последовательность символов. Однако это не слишком распространенный пример использования LINQ. Для сложных операций сопоставления шаблонов используйте класс <xref:System.Text.RegularExpressions.Regex>.

## <a name="example"></a>Пример

В следующем примере запрашивается строка, чтобы определить количество содержащихся в ней цифр. Обратите внимание, что запрос "используется повторно" после первоначального выполнения. Это становится возможным, поскольку сам запрос не хранит фактические результаты.

```vb
Class QueryAString

    Shared Sub Main()

        ' A string is an IEnumerable data source.
        Dim aString As String = "ABCDE99F-J74-12-89A"

        ' Select only those characters that are numbers
        Dim stringQuery = From ch In aString
                          Where Char.IsDigit(ch)
                          Select ch
        ' Execute the query
        For Each c As Char In stringQuery
            Console.Write(c & " ")
        Next

        ' Call the Count method on the existing query.
        Dim count As Integer = stringQuery.Count()
        Console.WriteLine(System.Environment.NewLine & "Count = " & count)

        ' Select all characters before the first '-'
        Dim stringQuery2 = aString.TakeWhile(Function(c) c <> "-")

        ' Execute the second query
        For Each ch In stringQuery2
            Console.Write(ch)
        Next

        Console.WriteLine(System.Environment.NewLine & "Press any key to exit")
        Console.ReadKey()
    End Sub
End Class
' Output:
' 9 9 7 4 1 2 8 9
' Count = 8
' ABCDE99F
```

## <a name="compiling-the-code"></a>Компиляция кода

Создайте проект консольного приложения VB.NET с помощью инструкции `Imports` для пространства имен System. LINQ.

## <a name="see-also"></a>См. также

- [LINQ и строки (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
- [Практические руководства. Объединение запросов LINQ с помощью регулярных выражений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)
