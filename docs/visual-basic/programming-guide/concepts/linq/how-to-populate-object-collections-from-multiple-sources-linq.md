---
title: Практическое руководство. Заполнение коллекций объектов из нескольких источников (LINQ)
ms.date: 06/22/2018
ms.assetid: 63062a22-e6a9-42c0-b357-c7c965f58f33
ms.openlocfilehash: 74a2a0f71e575136f1758f72f9a8db72549a9489
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346976"
---
# <a name="how-to-populate-object-collections-from-multiple-sources-linq-visual-basic"></a>Как заполнить коллекции объектов из нескольких источников (LINQ) (Visual Basic)

В этом примере показано, как объединить данные из разных источников в последовательность новых типов.

> [!NOTE]
> Не пытайтесь объединить данные в памяти или данные в файловой системе с данными, которые остаются в базе данных. Такие междоменные соединения могут повлечь за собой непредвиденные результаты из-за разных способов, с помощью которых операции соединения могут определяться для запросов к базам данных и другим типам источников. Кроме того, существует риск, что такая операция может вызвать исключение нехватки памяти, если объем данных в базе данных достаточно большой. Чтобы объединить данные из базы данных с данными в памяти, сначала вызовите `ToList` или `ToArray` для запроса к базе данных, а затем выполните присоединение для возвращенной коллекции.

## <a name="to-create-the-data-file"></a>Создание файла данных

- Скопируйте файлы Names. csv и scores. csv в папку проекта, как описано в разделе [как присоединиться к содержимому из разнородных файлов (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md).

## <a name="example"></a>Пример

Следующий пример демонстрирует использование именованного типа `Student` для хранения объединенных данных из двух коллекций строк в памяти, которые имитируют данные электронной таблицы в формате CSV. Первая коллекция строк представляет имена и идентификаторы учащихся, а вторая коллекция — идентификатор учащегося (в первом столбце) и результаты четырех экзаменов. Идентификатор используется в качестве внешнего ключа.

```vb
Imports System.Collections.Generic
Imports System.Linq

Class Student
    Public FirstName As String
    Public LastName As String
    Public ID As Integer
    Public ExamScores As List(Of Integer)
End Class

Class PopulateCollection

    Shared Sub Main()

        ' Merge content from spreadsheets into a list of Student objects.

        ' These data files are defined in How to: Join Content from
        ' Dissimilar Files (LINQ).

        ' Each line of names.csv consists of a last name, a first name, and an
        ' ID number, separated by commas. For example, Omelchenko,Svetlana,111
        Dim names As String() = System.IO.File.ReadAllLines("../../../names.csv")

        ' Each line of scores.csv consists of an ID number and four test
        ' scores, separated by commas. For example, 111, 97, 92, 81, 60
        Dim scores As String() = System.IO.File.ReadAllLines("../../../scores.csv")

        ' The following query merges the content of two dissimilar spreadsheets
        ' based on common ID values.
        ' Multiple From clauses are used instead of a Join clause
        ' in order to store the results of scoreLine.Split.
        ' Note the dynamic creation of a list of integers for the
        ' ExamScores member. The first item is skipped in the split string
        ' because it is the student ID, not an exam score.
        Dim queryNamesScores = From nameLine In names
                          Let splitName = nameLine.Split(New Char() {","})
                          From scoreLine In scores
                          Let splitScoreLine = scoreLine.Split(New Char() {","})
                          Where Convert.ToInt32(splitName(2)) = Convert.ToInt32(splitScoreLine(0))
                          Select New Student() With {
                               .FirstName = splitName(1), .LastName = splitName(0), .ID = splitName(2),
                               .ExamScores = (From scoreAsText In splitScoreLine Skip 1
                                             Select Convert.ToInt32(scoreAsText)).ToList()}

        ' Optional. Store the query results for faster access in future
        ' queries. This could be useful with very large data files.
        Dim students As List(Of Student) = queryNamesScores.ToList()

        ' Display each student's name and exam score average.
        For Each s In students
            Console.WriteLine("The average score of " & s.FirstName & " " &
                              s.LastName & " is " & s.ExamScores.Average())
        Next

        ' Keep console window open in debug mode.
        Console.WriteLine("Press any key to exit.")
        Console.ReadKey()
    End Sub
End Class

' Output:
' The average score of Svetlana Omelchenko is 82.5
' The average score of Claire O'Donnell is 72.25
' The average score of Sven Mortensen is 84.5
' The average score of Cesar Garcia is 88.25
' The average score of Debra Garcia is 67
' The average score of Fadi Fakhouri is 92.25
' The average score of Hanying Feng is 88
' The average score of Hugo Garcia is 85.75
' The average score of Lance Tucker is 81.75
' The average score of Terry Adams is 85.25
' The average score of Eugene Zabokritski is 83
' The average score of Michael Tucker is 92
```

В предложении [предложения SELECT](../../../../visual-basic/language-reference/queries/select-clause.md) инициализатор объекта используется для создания экземпляра каждого нового `Student` объекта с помощью данных из двух источников.

Если не требуется хранить результаты запроса, анонимные типы могут быть более удобными, чем именованные типы. Именованные типы необходимы, если результаты запроса передаются за пределы метода, в котором выполняется запрос. Следующий пример кода выполняет ту же задачу, что и в предыдущем примере, но использует анонимные типы вместо именованных типов:

```vb
' Merge the data by using an anonymous type.
' Note the dynamic creation of a list of integers for the
' ExamScores member. We skip 1 because the first string
' in the array is the student ID, not an exam score.
Dim queryNamesScores2 =
    From nameLine In names
    Let splitName = nameLine.Split(New Char() {","})
    From scoreLine In scores
    Let splitScoreLine = scoreLine.Split(New Char() {","})
    Where Convert.ToInt32(splitName(2)) = Convert.ToInt32(splitScoreLine(0))
    Select New With
           {.Last = splitName(0),
            .First = splitName(1),
            .ExamScores = (From scoreAsText In splitScoreLine Skip 1
                           Select Convert.ToInt32(scoreAsText)).ToList()}

' Display each student's name and exam score average.
For Each s In queryNamesScores2
    Console.WriteLine("The average score of " & s.First & " " &
                      s.Last & " is " & s.ExamScores.Average())
Next
```

## <a name="see-also"></a>См. также:

- [LINQ и строки (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
