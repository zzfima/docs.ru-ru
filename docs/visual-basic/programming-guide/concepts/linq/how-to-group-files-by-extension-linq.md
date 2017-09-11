---
title: "Практическое руководство: группировка файлов по расширению (LINQ) (Visual Basic) | Документы Microsoft"
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
ms.assetid: 904dc6d7-7162-4655-a7f4-5785d669bc5a
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
ms.openlocfilehash: 8b78cbaf8b0f20c6b7ab14640dffd61e9657dc9b
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-group-files-by-extension-linq-visual-basic"></a><span data-ttu-id="56e66-102">Практическое руководство: группировка файлов по расширению (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56e66-102">How to: Group Files by Extension (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="56e66-103">В этом примере показано, как можно использовать LINQ для выполнения расширенной группировки и сортировки списков файлов или папок.</span><span class="sxs-lookup"><span data-stu-id="56e66-103">This example shows how LINQ can be used to perform advanced grouping and sorting operations on lists of files or folders.</span></span> <span data-ttu-id="56e66-104">Также показано, как на страницы выходные данные в окне консоли с помощью <xref:System.Linq.Enumerable.Skip%2A>и <xref:System.Linq.Enumerable.Take%2A>методы.</xref:System.Linq.Enumerable.Take%2A> </xref:System.Linq.Enumerable.Skip%2A></span><span class="sxs-lookup"><span data-stu-id="56e66-104">It also shows how to page output in the console window by using the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56e66-105">Пример</span><span class="sxs-lookup"><span data-stu-id="56e66-105">Example</span></span>  
 <span data-ttu-id="56e66-106">Следующий запрос демонстрирует Группировка содержимого указанном дереве каталогов по расширению имени файла.</span><span class="sxs-lookup"><span data-stu-id="56e66-106">The following query shows how to group the contents of a specified directory tree by the file name extension.</span></span>  
  
```vb  
Module GroupByExtension  
    Public Sub Main()  
  
        ' Root folder to query, along with all subfolders.  
        Dim startFolder As String = "C:\program files\Microsoft Visual Studio 9.0\VB\"  
  
        ' Used in WriteLine() to skip over startfolder in output lines.  
        Dim rootLength As Integer = startFolder.Length  
  
        'Take a snapshot of the folder contents  
        Dim dir As New System.IO.DirectoryInfo(startFolder)  
        Dim fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
  
        ' Create the query.  
        Dim queryGroupByExt = From file In fileList _  
                          Group By file.Extension.ToLower() Into fileGroup = Group _  
                          Order By ToLower _  
                          Select fileGroup  
  
        ' Execute the query. By storing the result we can  
        ' page the display with good performance.  
        Dim groupByExtList = queryGroupByExt.ToList()  
  
        ' Display one group at a time. If the number of   
        ' entries is greater than the number of lines  
        ' in the console window, then page the output.  
        Dim trimLength = startFolder.Length  
        PageOutput(groupByExtList, trimLength)  
  
    End Sub  
  
    ' Pages console diplay for large query results. No more than one group per page.  
    ' This sub specifically works with group queries of FileInfo objects  
    ' but can be modified for any type.  
    Sub PageOutput(ByVal groupQuery, ByVal charsToSkip)  
  
        ' "3" = 1 line for extension key + 1 for "Press any key" + 1 for input cursor.  
        Dim numLines As Integer = Console.WindowHeight - 3  
        ' Flag to indicate whether there are more results to diplay  
        Dim goAgain As Boolean = True  
  
        For Each fg As IEnumerable(Of System.IO.FileInfo) In groupQuery  
            ' Start a new extension at the top of a page.  
            Dim currentLine As Integer = 0  
  
            Do While (currentLine < fg.Count())  
                Console.Clear()  
                Console.WriteLine(fg(0).Extension)  
  
                ' Get the next page of results  
                ' No more than one filename per page  
                Dim resultPage = From file In fg _  
                                Skip currentLine Take numLines  
  
                ' Execute the query. Trim the display output.  
                For Each line In resultPage  
                    Console.WriteLine(vbTab & line.FullName.Substring(charsToSkip))  
                Next  
  
                ' Advance the current position  
                currentLine = numLines + currentLine  
  
                ' Give the user a chance to break out of the loop  
                Console.WriteLine("Press any key for next page or the 'End' key to exit.")  
                Dim key As ConsoleKey = Console.ReadKey().Key  
                If key = ConsoleKey.End Then  
                    goAgain = False  
                    Exit For  
                End If  
            Loop  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="56e66-107">Выходные данные этой программы могут быть длинными в зависимости от сведений о локальной файловой системы и что `startFolder` имеет значение.</span><span class="sxs-lookup"><span data-stu-id="56e66-107">The output from this program can be long, depending on the details of the local file system and what the `startFolder` is set to.</span></span> <span data-ttu-id="56e66-108">Для просмотра всех результатов, в этом примере показано, как просматривать результаты постранично.</span><span class="sxs-lookup"><span data-stu-id="56e66-108">To enable viewing of all results, this example shows how to page through results.</span></span> <span data-ttu-id="56e66-109">Те же методы могут применяться для Windows и веб-приложений.</span><span class="sxs-lookup"><span data-stu-id="56e66-109">The same techniques can be applied to Windows and Web applications.</span></span> <span data-ttu-id="56e66-110">Обратите внимание, что поскольку код страницы элементов в группе, требуется вложенный `For Each` цикла является обязательным.</span><span class="sxs-lookup"><span data-stu-id="56e66-110">Notice that because the code pages the items in a group, a nested `For Each` loop is required.</span></span> <span data-ttu-id="56e66-111">Также существует некоторая дополнительная логика для вычисления текущей позиции в списке и предоставления пользователю возможности остановить разбиение по страницам и выйти из программы.</span><span class="sxs-lookup"><span data-stu-id="56e66-111">There is also some additional logic to compute the current position in the list, and to enable the user to stop paging and exit the program.</span></span> <span data-ttu-id="56e66-112">В данном конкретном случае запрос разбиения на страницы выполняется к кэшированным результатам из исходного запроса.</span><span class="sxs-lookup"><span data-stu-id="56e66-112">In this particular case, the paging query is run against the cached results from the original query.</span></span> <span data-ttu-id="56e66-113">В других контекстах, например LINQ to SQL подобное кэширование не требуется.</span><span class="sxs-lookup"><span data-stu-id="56e66-113">In other contexts, such as LINQ to SQL, such caching is not required.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="56e66-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="56e66-114">Compiling the Code</span></span>  
 <span data-ttu-id="56e66-115">Создайте проект, в платформе .NET Framework версии 3.5 или более поздней версии с ссылку на библиотеку System.Core.dll и `Imports` оператор для пространства имен System.Linq.</span><span class="sxs-lookup"><span data-stu-id="56e66-115">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a   `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56e66-116">См. также</span><span class="sxs-lookup"><span data-stu-id="56e66-116">See Also</span></span>  
 <span data-ttu-id="56e66-117">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span><span class="sxs-lookup"><span data-stu-id="56e66-117">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span></span>  
<span data-ttu-id="56e66-118"> [LINQ и каталоги файлов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span><span class="sxs-lookup"><span data-stu-id="56e66-118"> [LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span></span>
