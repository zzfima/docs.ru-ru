---
title: "Практическое руководство: количество вхождений слова в строке (LINQ) (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: bc367e46-f7cc-45f9-936f-754e661b7bb9
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5697e52729287a09f1afe993c7b1c1d0c9a6507b
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-count-occurrences-of-a-word-in-a-string-linq-visual-basic"></a><span data-ttu-id="dfe77-102">Практическое руководство: количество вхождений слова в строке (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dfe77-102">How to: Count Occurrences of a Word in a String (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="dfe77-103">В этом примере показано, как использовать LINQ-запрос для подсчета вхождений указанного слова в строке.</span><span class="sxs-lookup"><span data-stu-id="dfe77-103">This example shows how to use a LINQ query to count the occurrences of a specified word in a string.</span></span> <span data-ttu-id="dfe77-104">Обратите внимание, что для выполнения подсчета сначала <xref:System.String.Split%2A>метод вызывается для создания массива слов.</xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="dfe77-104">Note that to perform the count, first the <xref:System.String.Split%2A> method is called to create an array of words.</span></span> <span data-ttu-id="dfe77-105">Чтобы снижается производительность <xref:System.String.Split%2A>метод.</xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="dfe77-105">There is a performance cost to the <xref:System.String.Split%2A> method.</span></span> <span data-ttu-id="dfe77-106">Если подсчет слов является единственной операцией в строке, следует рассмотреть возможность использования <xref:System.Text.RegularExpressions.Regex.Matches%2A>или <xref:System.String.IndexOf%2A>методов вместо.</xref:System.String.IndexOf%2A> </xref:System.Text.RegularExpressions.Regex.Matches%2A></span><span class="sxs-lookup"><span data-stu-id="dfe77-106">If the only operation on the string is to count the words, you should consider using the <xref:System.Text.RegularExpressions.Regex.Matches%2A> or <xref:System.String.IndexOf%2A> methods instead.</span></span> <span data-ttu-id="dfe77-107">Однако если производительность не критична или предложение уже разделено для выполнения других запросов на него, затем имеет смысл использовать LINQ для подсчета слов или фраз.</span><span class="sxs-lookup"><span data-stu-id="dfe77-107">However, if performance is not a critical issue, or you have already split the sentence in order to perform other types of queries over it, then it makes sense to use LINQ to count the words or phrases as well.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfe77-108">Пример</span><span class="sxs-lookup"><span data-stu-id="dfe77-108">Example</span></span>  
  
```vb  
Class CountWords  
  
    Shared Sub Main()  
  
        Dim text As String = "Historically, the world of data and the world of objects" &   
                  " have not been well integrated. Programmers work in C# or Visual Basic" &   
                  " and also in SQL or XQuery. On the one side are concepts such as classes," &   
                  " objects, fields, inheritance, and .NET Framework APIs. On the other side" &   
                  " are tables, columns, rows, nodes, and separate languages for dealing with" &   
                  " them. Data types often require translation between the two worlds; there are" &   
                  " different standard functions. Because the object world has no notion of query, a" &   
                  " query can only be represented as a string without compile-time type checking or" &   
                  " IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to" &   
                  " objects in memory is often tedious and error-prone."  
  
        Dim searchTerm As String = "data"  
  
        ' Convert the string into an array of words.  
        Dim dataSource As String() = text.Split(New Char() {" ", ",", ".", ";", ":"},   
                                                 StringSplitOptions.RemoveEmptyEntries)  
  
        ' Create and execute the query. It executes immediately   
        ' because a singleton value is produced.  
        ' Use ToLower to match "data" and "Data"   
        Dim matchQuery = From word In dataSource   
                      Where word.ToLowerInvariant() = searchTerm.ToLowerInvariant()   
                      Select word  
  
        ' Count the matches.  
        Dim count As Integer = matchQuery.Count()  
        Console.WriteLine(count & " occurrence(s) of the search term """ &   
                          searchTerm & """ were found.")  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
End Class  
' Output:  
' 3 occurrence(s) of the search term "data" were found.  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dfe77-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="dfe77-109">Compiling the Code</span></span>  
 <span data-ttu-id="dfe77-110">Создайте проект, в платформе .NET Framework версии 3.5 или более поздней версии с ссылку на библиотеку System.Core.dll и `Imports` оператор для пространства имен System.Linq.</span><span class="sxs-lookup"><span data-stu-id="dfe77-110">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfe77-111">См. также</span><span class="sxs-lookup"><span data-stu-id="dfe77-111">See Also</span></span>  
 [<span data-ttu-id="dfe77-112">LINQ и строки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dfe77-112">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
