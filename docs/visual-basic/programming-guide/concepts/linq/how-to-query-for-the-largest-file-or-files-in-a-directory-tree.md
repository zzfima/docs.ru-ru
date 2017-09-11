---
title: "Практическое руководство: запрос самого большого файла или файлов в дереве каталогов (LINQ) (Visual Basic) | Документы Microsoft"
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
ms.assetid: 8c1c9f0c-95dd-4222-9be2-9ec026a13e81
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
ms.openlocfilehash: 95c5197b2cb66745201ceac89b78fe67b95ecb75
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq-visual-basic"></a><span data-ttu-id="b490a-102">Практическое руководство. Запрос самого большого файла или файлов в дереве папок (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b490a-102">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="b490a-103">Этот пример показывает пять запросов, связанных с размером файла в байтах.</span><span class="sxs-lookup"><span data-stu-id="b490a-103">This example shows five queries related to file size in bytes:</span></span>  
  
-   <span data-ttu-id="b490a-104">Как получить размер в байтах самого большого файла.</span><span class="sxs-lookup"><span data-stu-id="b490a-104">How to retrieve the size in bytes of the largest file.</span></span>  
  
-   <span data-ttu-id="b490a-105">Как получить размер в байтах наименьшего файла.</span><span class="sxs-lookup"><span data-stu-id="b490a-105">How to retrieve the size in bytes of the smallest file.</span></span>  
  
-   <span data-ttu-id="b490a-106">Как получить <xref:System.IO.FileInfo>объекта наибольшего или наименьшего файла из одной или нескольких папок в указанной корневой папке.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="b490a-106">How to retrieve the <xref:System.IO.FileInfo> object largest or smallest file from one or more folders under a specified root folder.</span></span>  
  
-   <span data-ttu-id="b490a-107">Как получить последовательности, например 10 наибольших файлов.</span><span class="sxs-lookup"><span data-stu-id="b490a-107">How to retrieve a sequence such as the 10 largest files.</span></span>  
  
-   <span data-ttu-id="b490a-108">Как упорядочение файлов в группы на основании их размера в байтах, игнорируя файлы меньше заданного размера.</span><span class="sxs-lookup"><span data-stu-id="b490a-108">How to order files into groups based on their file size in bytes, ignoring files that are less than a specified size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b490a-109">Пример</span><span class="sxs-lookup"><span data-stu-id="b490a-109">Example</span></span>  
 <span data-ttu-id="b490a-110">Следующий пример содержит пять отдельных запросов, которые показывают, как запрашивать и группировать файлы на основании их размера в байтах.</span><span class="sxs-lookup"><span data-stu-id="b490a-110">The following example contains five separate queries that show how to query and group files, depending on their file size in bytes.</span></span> <span data-ttu-id="b490a-111">Эти примеры, чтобы создать запрос на основании других свойств объекта можно легко изменить <xref:System.IO.FileInfo>объекта.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="b490a-111">You can easily modify these examples to base the query on some other property of the <xref:System.IO.FileInfo> object.</span></span>  
  
```vb  
Module QueryBySize  
    Sub Main()  
  
        ' Change the drive\path if necessary  
        Dim root As String = "C:\Program Files\Microsoft Visual Studio 9.0"  
  
        'Take a snapshot of the folder contents  
        Dim dir As New System.IO.DirectoryInfo(root)  
        Dim fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
  
        ' Return the size of the largest file  
        Dim maxSize = Aggregate aFile In fileList Into Max(GetFileLength(aFile))  
  
        'Dim maxSize = fileLengths.Max  
        Console.WriteLine("The length of the largest file under {0} is {1}", _  
                          root, maxSize)  
  
        ' Return the FileInfo object of the largest file  
        ' by sorting and selecting from the beginning of the list  
        Dim filesByLengDesc = From file In fileList _  
                              Let filelength = GetFileLength(file) _  
                              Where filelength > 0 _  
                              Order By filelength Descending _  
                              Select file  
  
        Dim longestFile = filesByLengDesc.First  
  
        Console.WriteLine("The largest file under {0} is {1} with a length of {2} bytes", _  
                          root, longestFile.FullName, longestFile.Length)  
  
        Dim smallestFile = filesByLengDesc.Last  
  
        Console.WriteLine("The smallest file under {0} is {1} with a length of {2} bytes", _  
                                root, smallestFile.FullName, smallestFile.Length)  
  
        ' Return the FileInfos for the 10 largest files  
        ' Based on a previous query, but nothing is executed  
        ' until the For Each statement below.  
        Dim tenLargest = From file In filesByLengDesc Take 10  
  
        Console.WriteLine("The 10 largest files under {0} are:", root)  
  
        For Each fi As System.IO.FileInfo In tenLargest  
            Console.WriteLine("{0}: {1} bytes", fi.FullName, fi.Length)  
        Next  
  
        ' Group files according to their size,  
        ' leaving out the ones under 200K  
        Dim sizeGroups = From file As System.IO.FileInfo In fileList _  
                         Where file.Length > 0 _  
                         Let groupLength = file.Length / 100000 _  
                         Group file By groupLength Into fileGroup = Group _  
                         Where groupLength >= 2 _  
                         Order By groupLength Descending  
  
        For Each group In sizeGroups  
            Console.WriteLine(group.groupLength + "00000")  
  
            For Each item As System.IO.FileInfo In group.fileGroup  
                Console.WriteLine("   {0}: {1}", item.Name, item.Length)  
            Next  
        Next  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
  
    End Sub  
  
    ' This method is used to catch the possible exception  
    ' that can be raised when accessing the FileInfo.Length property.  
    ' In this particular case, it is safe to ignore the exception.  
    Function GetFileLength(ByVal fi As System.IO.FileInfo) As Long  
        Dim retval As Long  
        Try  
            retval = fi.Length  
        Catch ex As FileNotFoundException  
            ' If a file is no longer present,  
            ' just return zero bytes.   
            retval = 0  
        End Try  
  
        Return retval  
    End Function  
End Module  
```  
  
 <span data-ttu-id="b490a-112">Чтобы вернуть один или несколько полных <xref:System.IO.FileInfo>объектов, запрос должен сначала проверить каждый из них в данных источника, а затем отсортировать их по значению свойства Length.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="b490a-112">To return one or more complete <xref:System.IO.FileInfo> objects, the query first must examine each one in the data source, and then sort them by the value of their Length property.</span></span> <span data-ttu-id="b490a-113">Затем он может вернуть один объект или последовательность объектов с максимальной длиной.</span><span class="sxs-lookup"><span data-stu-id="b490a-113">Then it can return the single one or the sequence with the greatest lengths.</span></span> <span data-ttu-id="b490a-114">Используйте <xref:System.Linq.Enumerable.First%2A>для возвращения первого элемента в списке.</xref:System.Linq.Enumerable.First%2A></span><span class="sxs-lookup"><span data-stu-id="b490a-114">Use <xref:System.Linq.Enumerable.First%2A> to return the first element in a list.</span></span> <span data-ttu-id="b490a-115">Используйте <xref:System.Linq.Enumerable.Take%2A>для возврата n количество первых элементов.</xref:System.Linq.Enumerable.Take%2A></span><span class="sxs-lookup"><span data-stu-id="b490a-115">Use <xref:System.Linq.Enumerable.Take%2A> to return the first n number of elements.</span></span> <span data-ttu-id="b490a-116">Укажите порядок сортировки по убыванию для размещения наименьших элементов в начале списка.</span><span class="sxs-lookup"><span data-stu-id="b490a-116">Specify a descending sort order to put the smallest elements at the start of the list.</span></span>  
  
 <span data-ttu-id="b490a-117">Запрос вызывает отдельный метод, чтобы получить размер файла в байтах для обработки возможных исключений, которые могут возникнуть в случае, когда файл был удален в другом потоке за период времени с момента <xref:System.IO.FileInfo>объект был создан в вызове `GetFiles`.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="b490a-117">The query calls out to a separate method to obtain the file size in bytes in order to consume the possible exception that will be raised in the case where a file was deleted on another thread in the time period since the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="b490a-118">Вплоть до <xref:System.IO.FileInfo>объект уже создан, исключение может возникнуть из-за <xref:System.IO.FileInfo>будет пытаться обновить его <xref:System.IO.FileInfo.Length%2A>используя самый последний размер в байтах при первом обращении к свойству.</xref:System.IO.FileInfo.Length%2A> </xref:System.IO.FileInfo> </xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="b490a-118">Even through the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property by using the most current size in bytes the first time the property is accessed.</span></span> <span data-ttu-id="b490a-119">Поместив эту операцию в блок try-catch вне запроса, будет выполнено правило исключения использования операций в запросах, которые могут вызвать побочные эффекты.</span><span class="sxs-lookup"><span data-stu-id="b490a-119">By putting this operation in a try-catch block outside the query, we follow the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="b490a-120">В общем случае отлично необходимо соблюдать осторожность при перехвате исключений, чтобы убедиться в том, что приложение не остается в неизвестном состоянии.</span><span class="sxs-lookup"><span data-stu-id="b490a-120">In general, great care must be taken when consuming exceptions, to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b490a-121">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="b490a-121">Compiling the Code</span></span>  
 <span data-ttu-id="b490a-122">Создайте проект, в платформе .NET Framework версии 3.5 или более поздней версии с ссылку на библиотеку System.Core.dll и `Imports` оператор для пространства имен System.Linq.</span><span class="sxs-lookup"><span data-stu-id="b490a-122">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b490a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="b490a-123">See Also</span></span>  
 <span data-ttu-id="b490a-124">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span><span class="sxs-lookup"><span data-stu-id="b490a-124">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span></span>  
<span data-ttu-id="b490a-125"> [LINQ и каталоги файлов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span><span class="sxs-lookup"><span data-stu-id="b490a-125"> [LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span></span>
