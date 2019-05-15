---
title: Практическое руководство. Нахождение разности множеств между двумя списками (LINQ) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: b5b25474-10a8-4df6-aab5-75621bb6b68e
ms.openlocfilehash: a5c08e270059cd4ab127051d091deff221091fbc
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593461"
---
# <a name="how-to-find-the-set-difference-between-two-lists-linq-visual-basic"></a>Практическое руководство. Нахождение разности множеств между двумя списками (LINQ) (Visual Basic)
В этом примере показано, как использовать LINQ для сравнения двух списков строк и вывода тех строк, которые содержатся в файле names1.txt, но не в файле names2.txt.  
  
### <a name="to-create-the-data-files"></a>Создание файлов данных  
  
1. Скопируйте файлы names1.txt и names2.txt в папку решения, как показано в разделе [Практическое руководство. Объединение и сравнение коллекций строк (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md).  
  
## <a name="example"></a>Пример  
  
```vb  
Class CompareLists  
  
    Shared Sub Main()  
  
        ' Create the IEnumerable data sources.  
        Dim names1 As String() = System.IO.File.ReadAllLines("../../../names1.txt")  
        Dim names2 As String() = System.IO.File.ReadAllLines("../../../names2.txt")  
  
        ' Create the query. Note that method syntax must be used here.  
        Dim differenceQuery = names1.Except(names2)  
        Console.WriteLine("The following lines are in names1.txt but not names2.txt")  
  
        ' Execute the query.  
        For Each name As String In differenceQuery  
            Console.WriteLine(name)  
        Next  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
End Class  
' Output:  
' The following lines are in names1.txt but not names2.txt  
' Potra, Cristina  
' Noriega, Fabricio  
' Aw, Kam Foo  
' Toyoshima, Tim  
' Guy, Wey Yuan  
' Garcia, Debra  
```  
  
 Некоторые типы операторов запроса в Visual Basic, такие как <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A>, и <xref:System.Linq.Enumerable.Concat%2A>, могут быть выражены только в синтаксисе на основе методов.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
Создайте проект консольного приложения VB.NET, с помощью `Imports` оператор для пространства имен System.Linq.
  
## <a name="see-also"></a>См. также

- [LINQ и строки (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
