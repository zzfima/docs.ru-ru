---
title: 'Как: заполнение коллекций объектов из нескольких источников (LINQ) (Visual Basic)'
ms.date: 06/22/2018
ms.assetid: 63062a22-e6a9-42c0-b357-c7c965f58f33
ms.openlocfilehash: 6560f853874f9b9a9aeb53bd0678540004fdfcc1
ms.sourcegitcommit: 9e18e4a18284ae9e54c515e30d019c0bbff9cd37
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2018
ms.locfileid: "37070867"
---
# <a name="how-to-populate-object-collections-from-multiple-sources-linq-visual-basic"></a>Как: заполнение коллекций объектов из нескольких источников (LINQ) (Visual Basic)

В этом примере показано, как объединить данные из разных источников в последовательность новых типов.

> [!NOTE]
> Не пытайтесь соединения в памяти или данных в файловой системе с данными, которые все еще находится в базе данных. Такие междоменные соединения могут повлечь за собой непредвиденные результаты из-за разных способов, с помощью которых операции соединения могут определяться для запросов к базам данных и другим типам источников. Кроме того, существует риск, что такая операция может вызвать исключение нехватки памяти, если объем данных в базе данных достаточно большой. Чтобы объединить данные из базы данных с данными в памяти, сначала вызовите `ToList` или `ToArray` для запроса к базе данных, а затем выполните присоединение для возвращенной коллекции.

## <a name="to-create-the-data-file"></a>Создание файла данных

- Скопируйте файлы names.csv и scores.csv в папке проекта, как описано в [как: присоединение содержимого из различных файлов (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md).

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
                               .FirstName = splitName(0), .LastName = splitName(1), .ID = splitName(2),
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
' The average score of Omelchenko Svetlana is 82.5
' The average score of O'Donnell Claire is 72.25
' The average score of Mortensen Sven is 84.5
' The average score of Garcia Cesar is 88.25
' The average score of Garcia Debra is 67
' The average score of Fakhouri Fadi is 92.25
' The average score of Feng Hanying is 88
' The average score of Garcia Hugo is 85.75
' The average score of Tucker Lance is 81.75
' The average score of Adams Terry is 85.25
' The average score of Zabokritski Eugene is 83
' The average score of Tucker Michael is 92
```

В [предложение Select](../../../../visual-basic/language-reference/queries/select-clause.md) предложение, инициализатор объектов используется для создания каждого нового `Student` объекта, используя данные из двух источников.

Если не нужно сохранять результаты запроса, анонимные типы могут быть более удобным, чем именованные типы. Именованные типы необходимы, если результаты запроса передаются за пределы метода, в котором выполняется запрос. Следующий пример кода выполняет ту же задачу, что и в предыдущем примере, но использует анонимные типы вместо именованных типов:

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

## <a name="compiling-the-code"></a>Компиляция кода

Создание и компиляция проекте, ориентированном на один из следующих вариантов:

- .NET framework версии 3.5 и ссылки на библиотеку System.Core.dll.
- .NET framework 4.0 или более поздней версии.
- .NET core версии 1.0 или более поздней версии.

## <a name="see-also"></a>См. также

[LINQ и строки (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
