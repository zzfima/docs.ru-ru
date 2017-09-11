---
title: "Практическое руководство: объединение и сравнение коллекций строк (LINQ) (Visual Basic) | Документы Microsoft"
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
ms.assetid: 243cfafc-9eaa-4354-a9df-d329f1d39913
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c2b512695052485e6c19f44d3e53cd14b04d0f07
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-combine-and-compare-string-collections-linq-visual-basic"></a><span data-ttu-id="3bc42-102">Практическое руководство: объединение и сравнение коллекций строк (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3bc42-102">How to: Combine and Compare String Collections (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="3bc42-103">В этом примере показано, как выполнить слияние файлов, содержащих строки текста, а затем отсортировать результаты.</span><span class="sxs-lookup"><span data-stu-id="3bc42-103">This example shows how to merge files that contain lines of text and then sort the results.</span></span> <span data-ttu-id="3bc42-104">В частности показано выполнение простого соединения, объединения и пересечения в двух наборах строк текста.</span><span class="sxs-lookup"><span data-stu-id="3bc42-104">Specifically, it shows how to perform a simple concatenation, a union, and an intersection on the two sets of text lines.</span></span>  
  
### <a name="to-set-up-the-project-and-the-text-files"></a><span data-ttu-id="3bc42-105">Настройка проекта и текстовых файлов</span><span class="sxs-lookup"><span data-stu-id="3bc42-105">To set up the project and the text files</span></span>  
  
1.  <span data-ttu-id="3bc42-106">Скопируйте эти имена в текстовый файл с именем names1.txt и сохраните его в папке проекта:</span><span class="sxs-lookup"><span data-stu-id="3bc42-106">Copy these names into a text file that is named names1.txt and save it in your project folder:</span></span>  
  
    ```  
    Bankov, Peter  
    Holm, Michael  
    Garcia, Hugo  
    Potra, Cristina  
    Noriega, Fabricio  
    Aw, Kam Foo  
    Beebe, Ann  
    Toyoshima, Tim  
    Guy, Wey Yuan  
    Garcia, Debra  
    ```  
  
2.  <span data-ttu-id="3bc42-107">Скопируйте эти имена в текстовый файл с именем names2.txt и сохраните его в папке проекта.</span><span class="sxs-lookup"><span data-stu-id="3bc42-107">Copy these names into a text file that is named names2.txt and save it in your project folder.</span></span> <span data-ttu-id="3bc42-108">Обратите внимание, что два файла некоторые имена общих.</span><span class="sxs-lookup"><span data-stu-id="3bc42-108">Note that the two files have some names in common.</span></span>  
  
    ```  
    Liu, Jinghao  
    Bankov, Peter  
    Holm, Michael  
    Garcia, Hugo  
    Beebe, Ann  
    Gilchrist, Beth  
    Myrcha, Jacek  
    Giakoumakis, Leo  
    McLin, Nkenge  
    El Yassir, Mehdi  
    ```  
  
## <a name="example"></a><span data-ttu-id="3bc42-109">Пример</span><span class="sxs-lookup"><span data-stu-id="3bc42-109">Example</span></span>  
  
```vb  
Class ConcatenateStrings  
    Shared Sub Main()  
  
        ' Create the IEnumerable data sources.  
        Dim fileA As String() = System.IO.File.ReadAllLines("../../../names1.txt")  
        Dim fileB As String() = System.IO.File.ReadAllLines("../../../names2.txt")  
  
        ' Simple concatenation and sort.  
        Dim concatQuery = fileA.Concat(fileB).OrderBy(Function(name) name)  
  
        ' Pass the query variable to another function for execution  
        OutputQueryResults(concatQuery, "Simple concatenation and sort. Duplicates are preserved:")  
  
        ' New query. Concatenate files and remove duplicates  
        Dim uniqueNamesQuery = fileA.Union(fileB).OrderBy(Function(name) name)  
        OutputQueryResults(uniqueNamesQuery, "Union removes duplicate names:")  
  
        ' New query. Find the names that occur in both files.  
        Dim commonNamesQuery = fileA.Intersect(fileB)  
        OutputQueryResults(commonNamesQuery, "Merge based on intersect: ")  
  
        ' New query in three steps for better readability   
        ' First filter each list separately  
  
        Dim nameToSearch As String = "Garcia"  
        Dim mergeQueryA As IEnumerable(Of String) = From name In fileA   
                          Let n = name.Split(New Char() {","})   
                          Where n(0) = nameToSearch   
                          Select name  
  
        Dim mergeQueryB = From name In fileB   
                          Let n = name.Split(New Char() {","})   
                          Where n(0) = nameToSearch   
                          Select name  
  
        ' Create a new query to concatenate and sort results. Duplicates are removed in Union.  
        ' Note that none of the queries actually executed until the call to OutputQueryResults.  
        Dim mergeSortQuery = mergeQueryA.Union(mergeQueryB).OrderBy(Function(str) str)  
  
        ' Now execute mergeSortQuery  
        OutputQueryResults(mergeSortQuery, "Concat based on partial name match """ & nameToSearch & """ from each list:")  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
  
    End Sub  
  
    Shared Sub OutputQueryResults(ByVal query As IEnumerable(Of String), ByVal message As String)  
  
        Console.WriteLine(System.Environment.NewLine & message)  
        For Each item As String In query  
            Console.WriteLine(item)  
        Next  
        Console.WriteLine(query.Count & " total names in list")  
  
    End Sub  
End Class  
' Output:  
  
' Simple concatenation and sort. Duplicates are preserved:  
' Aw, Kam Foo  
' Bankov, Peter  
' Bankov, Peter  
' Beebe, Ann  
' Beebe, Ann  
' El Yassir, Mehdi  
' Garcia, Debra  
' Garcia, Hugo  
' Garcia, Hugo  
' Giakoumakis, Leo  
' Gilchrist, Beth  
' Guy, Wey Yuan  
' Holm, Michael  
' Holm, Michael  
' Liu, Jinghao  
' McLin, Nkenge  
' Myrcha, Jacek  
' Noriega, Fabricio  
' Potra, Cristina  
' Toyoshima, Tim  
' 20 total names in list  
  
' Union removes duplicate names:  
' Aw, Kam Foo  
' Bankov, Peter  
' Beebe, Ann  
' El Yassir, Mehdi  
' Garcia, Debra  
' Garcia, Hugo  
' Giakoumakis, Leo  
' Gilchrist, Beth  
' Guy, Wey Yuan  
' Holm, Michael  
' Liu, Jinghao  
' McLin, Nkenge  
' Myrcha, Jacek  
' Noriega, Fabricio  
' Potra, Cristina  
' Toyoshima, Tim  
' 16 total names in list  
  
' Merge based on intersect:  
' Bankov, Peter  
' Holm, Michael  
' Garcia, Hugo  
' Beebe, Ann  
' 4 total names in list  
  
' Concat based on partial name match "Garcia" from each list:  
' Garcia, Debra  
' Garcia, Hugo  
' 2 total names in list  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3bc42-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="3bc42-110">Compiling the Code</span></span>  
 <span data-ttu-id="3bc42-111">Создайте проект, в платформе .NET Framework версии 3.5 или более поздней версии с ссылку на библиотеку System.Core.dll и `Imports` оператор для пространства имен System.Linq.</span><span class="sxs-lookup"><span data-stu-id="3bc42-111">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bc42-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3bc42-112">See Also</span></span>  
 <span data-ttu-id="3bc42-113">[LINQ и строки (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md) </span><span class="sxs-lookup"><span data-stu-id="3bc42-113">[LINQ and Strings (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md) </span></span>  
<span data-ttu-id="3bc42-114"> [LINQ и каталоги файлов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span><span class="sxs-lookup"><span data-stu-id="3bc42-114"> [LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span></span>
