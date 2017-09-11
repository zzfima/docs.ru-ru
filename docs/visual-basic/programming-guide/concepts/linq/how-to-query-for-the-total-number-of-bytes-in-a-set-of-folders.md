---
title: "Практическое руководство: запрос общее количество байтов в наборе папок (LINQ) (Visual Basic) | Документы Microsoft"
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
ms.assetid: bfe85ed2-44dc-4ef1-aac7-241622b80a69
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
ms.openlocfilehash: bda25acd3065898eeb61dce83d46d7526e825add
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-visual-basic"></a><span data-ttu-id="e30b6-102">Практическое руководство: запрос общее количество байтов в наборе папок (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e30b6-102">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="e30b6-103">В этом примере показано, как получить общее число байтов, используемых все файлы в указанной папке и всех ее подпапках.</span><span class="sxs-lookup"><span data-stu-id="e30b6-103">This example shows how to retrieve the total number of bytes used by all the files in a specified folder and all its subfolders.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e30b6-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e30b6-104">Example</span></span>  
 <span data-ttu-id="e30b6-105"><xref:System.Linq.Enumerable.Sum%2A>Метод складывает значения всех элементов, выбранных в `select` предложение.</xref:System.Linq.Enumerable.Sum%2A></span><span class="sxs-lookup"><span data-stu-id="e30b6-105">The <xref:System.Linq.Enumerable.Sum%2A> method adds the values of all the items selected in the `select` clause.</span></span> <span data-ttu-id="e30b6-106">Вы легко можете изменить этот запрос для получения наибольшего или наименьшего файла в дереве каталогов путем вызова <xref:System.Linq.Enumerable.Min%2A>или <xref:System.Linq.Enumerable.Max%2A>вместо <xref:System.Linq.Enumerable.Sum%2A>.</xref:System.Linq.Enumerable.Sum%2A> </xref:System.Linq.Enumerable.Max%2A> </xref:System.Linq.Enumerable.Min%2A></span><span class="sxs-lookup"><span data-stu-id="e30b6-106">You can easily modify this query to retrieve the biggest or smallest file in the specified directory tree by calling the <xref:System.Linq.Enumerable.Min%2A> or <xref:System.Linq.Enumerable.Max%2A> method instead of <xref:System.Linq.Enumerable.Sum%2A>.</span></span>  
  
```vb  
Module QueryTotalBytes  
    Sub Main()  
  
        ' Change the drive\path if necessary.  
        Dim root As String = "C:\Program Files\Microsoft Visual Studio 9.0\VB"  
  
        'Take a snapshot of the folder contents.  
        ' This method assumes that the application has discovery permissions  
        ' for all folders under the specified path.  
        Dim fileList = My.Computer.FileSystem.GetFiles _  
                  (root, FileIO.SearchOption.SearchAllSubDirectories, "*.*")  
  
        Dim fileQuery = From file In fileList _  
                        Select GetFileLength(file)  
  
        ' Force execution and cache the results to avoid multiple trips to the file system.  
        Dim fileLengths = fileQuery.ToArray()  
  
        ' Find the largest file  
        Dim maxSize = Aggregate aFile In fileLengths Into Max()  
  
        ' Find the total number of bytes  
        Dim totalBytes = Aggregate aFile In fileLengths Into Sum()  
  
        Console.WriteLine("The largest file is " & maxSize & " bytes")  
        Console.WriteLine("There are " & totalBytes & " total bytes in " & _  
                          fileList.Count & " files under " & root)  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
  
    ' This method is used to catch the possible exception  
    ' that can be raised when accessing the FileInfo.Length property.  
    Function GetFileLength(ByVal filename As String) As Long  
        Dim retval As Long  
        Try  
            Dim fi As New System.IO.FileInfo(filename)  
            retval = fi.Length  
        Catch ex As System.IO.FileNotFoundException  
            ' If a file is no longer present,  
            ' just return zero bytes.   
            retval = 0  
        End Try  
  
        Return retval  
    End Function  
End Module  
```  
  
 <span data-ttu-id="e30b6-107">При наличии только число байтов в указанном дереве каталогов, можно сделать это более эффективно без создания запроса LINQ, который вносит дополнительную нагрузку, связанную с созданием коллекции списков в качестве источника данных.</span><span class="sxs-lookup"><span data-stu-id="e30b6-107">If you only have to count the number of bytes in a specified directory tree, you can do this more efficiently without creating a LINQ query, which incurs the overhead of creating the list collection as a data source.</span></span> <span data-ttu-id="e30b6-108">Полезность этого подхода LINQ увеличивается по мере более сложный запрос или при необходимости выполнения нескольких запросов к одному источнику данных.</span><span class="sxs-lookup"><span data-stu-id="e30b6-108">The usefulness of the LINQ approach increases as the query becomes more complex, or when you have to run multiple queries against the same data source.</span></span>  
  
 <span data-ttu-id="e30b6-109">Запрос вызывает отдельный метод для получения длины файла.</span><span class="sxs-lookup"><span data-stu-id="e30b6-109">The query calls out to a separate method to obtain the file length.</span></span> <span data-ttu-id="e30b6-110">Это делается для обработки возможных исключений, которые могут возникнуть, если файл был удален в другом потоке после <xref:System.IO.FileInfo>объект был создан в вызове `GetFiles`.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="e30b6-110">It does this in order to consume the possible exception that will be raised if the file was deleted on another thread after the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="e30b6-111">Несмотря на то что <xref:System.IO.FileInfo>объект уже создан, исключение может возникнуть из-за <xref:System.IO.FileInfo>будет пытаться обновить его <xref:System.IO.FileInfo.Length%2A>свойство с самую последнюю длину при первом обращении к свойству.</xref:System.IO.FileInfo.Length%2A> </xref:System.IO.FileInfo> </xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="e30b6-111">Even though the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property with the most current length the first time the property is accessed.</span></span> <span data-ttu-id="e30b6-112">Поместив эту операцию в блок try-catch вне запроса, код следует правилу избежать операции в запросах, которые могут вызвать побочные эффекты.</span><span class="sxs-lookup"><span data-stu-id="e30b6-112">By putting this operation in a try-catch block outside the query, the code follows the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="e30b6-113">В общем случае отлично необходимо соблюдать осторожность при перехвате исключений, чтобы убедиться в том, что приложение не остается в неизвестном состоянии.</span><span class="sxs-lookup"><span data-stu-id="e30b6-113">In general, great care must be taken when you consume exceptions to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e30b6-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="e30b6-114">Compiling the Code</span></span>  
 <span data-ttu-id="e30b6-115">Создайте проект, в платформе .NET Framework версии 3.5 или более поздней версии с ссылку на библиотеку System.Core.dll и `Imports` оператор для пространства имен System.Linq.</span><span class="sxs-lookup"><span data-stu-id="e30b6-115">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a   `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e30b6-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e30b6-116">See Also</span></span>  
 <span data-ttu-id="e30b6-117">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span><span class="sxs-lookup"><span data-stu-id="e30b6-117">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span></span>  
<span data-ttu-id="e30b6-118"> [LINQ и каталоги файлов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span><span class="sxs-lookup"><span data-stu-id="e30b6-118"> [LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span></span>
