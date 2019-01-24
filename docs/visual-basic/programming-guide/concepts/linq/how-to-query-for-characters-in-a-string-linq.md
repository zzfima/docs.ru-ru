---
title: Как выполнить Запрос символов в строке (LINQ) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 499ebbe0-746c-4235-9dba-ce722c12b50e
ms.openlocfilehash: 3a4f3bbca313747e0b16170719b9028e5dc9174f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559753"
---
# <a name="how-to-query-for-characters-in-a-string-linq-visual-basic"></a><span data-ttu-id="17629-102">Как выполнить Запрос символов в строке (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17629-102">How to: Query for Characters in a String (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="17629-103">Поскольку класс <xref:System.String> реализует универсальный интерфейс <xref:System.Collections.Generic.IEnumerable%601>, любая строка может запрашиваться как последовательность символов.</span><span class="sxs-lookup"><span data-stu-id="17629-103">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="17629-104">Однако это не слишком распространенный пример использования LINQ.</span><span class="sxs-lookup"><span data-stu-id="17629-104">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="17629-105">Для сложных операций сопоставления шаблонов используйте класс <xref:System.Text.RegularExpressions.Regex>.</span><span class="sxs-lookup"><span data-stu-id="17629-105">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17629-106">Пример</span><span class="sxs-lookup"><span data-stu-id="17629-106">Example</span></span>  
 <span data-ttu-id="17629-107">В следующем примере запрашивается строка, чтобы определить количество содержащихся в ней цифр.</span><span class="sxs-lookup"><span data-stu-id="17629-107">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="17629-108">Обратите внимание, что запрос "используется повторно" после первоначального выполнения.</span><span class="sxs-lookup"><span data-stu-id="17629-108">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="17629-109">Это становится возможным, поскольку сам запрос не хранит фактические результаты.</span><span class="sxs-lookup"><span data-stu-id="17629-109">This is possible because the query itself does not store any actual results.</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="17629-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="17629-110">Compiling the Code</span></span>  
 <span data-ttu-id="17629-111">Создайте проект, предназначенный для .NET Framework 3.5 или более поздней версии, со ссылкой на библиотеку System.Core.dll и директивой `Imports` для пространства имен System.Linq.</span><span class="sxs-lookup"><span data-stu-id="17629-111">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17629-112">См. также</span><span class="sxs-lookup"><span data-stu-id="17629-112">See also</span></span>
- [<span data-ttu-id="17629-113">LINQ и строки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17629-113">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
- [<span data-ttu-id="17629-114">Практическое руководство. Объединение запросов LINQ с помощью регулярных выражений (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17629-114">How to: Combine LINQ Queries with Regular Expressions (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)
