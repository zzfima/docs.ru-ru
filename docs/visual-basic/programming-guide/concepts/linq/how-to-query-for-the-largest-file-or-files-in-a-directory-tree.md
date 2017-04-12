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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 055cbdd5a5903417ab382d390e1215f0319c0b5a
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq-visual-basic"></a>Практическое руководство. Запрос самого большого файла или файлов в дереве папок (LINQ) (Visual Basic)
Этот пример показывает пять запросов, связанных с размером файла в байтах.  
  
-   Как получить размер в байтах самого большого файла.  
  
-   Как получить размер в байтах наименьшего файла.  
  
-   Как получить <xref:System.IO.FileInfo>объекта наибольшего или наименьшего файла из одной или нескольких папок в указанной корневой папке.</xref:System.IO.FileInfo>  
  
-   Как получить последовательности, например 10 наибольших файлов.  
  
-   Как упорядочение файлов в группы на основании их размера в байтах, игнорируя файлы меньше заданного размера.  
  
## <a name="example"></a>Пример  
 Следующий пример содержит пять отдельных запросов, которые показывают, как запрашивать и группировать файлы на основании их размера в байтах. Эти примеры, чтобы создать запрос на основании других свойств объекта можно легко изменить <xref:System.IO.FileInfo>объекта.</xref:System.IO.FileInfo>  
  
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
  
 Чтобы вернуть один или несколько полных <xref:System.IO.FileInfo>объектов, запрос должен сначала проверить каждый из них в данных источника, а затем отсортировать их по значению свойства Length.</xref:System.IO.FileInfo> Затем он может вернуть один объект или последовательность объектов с максимальной длиной. Используйте <xref:System.Linq.Enumerable.First%2A>для возвращения первого элемента в списке.</xref:System.Linq.Enumerable.First%2A> Используйте <xref:System.Linq.Enumerable.Take%2A>для возврата n количество первых элементов.</xref:System.Linq.Enumerable.Take%2A> Укажите порядок сортировки по убыванию для размещения наименьших элементов в начале списка.  
  
 Запрос вызывает отдельный метод, чтобы получить размер файла в байтах для обработки возможных исключений, которые могут возникнуть в случае, когда файл был удален в другом потоке за период времени с момента <xref:System.IO.FileInfo>объект был создан в вызове `GetFiles`.</xref:System.IO.FileInfo> Вплоть до <xref:System.IO.FileInfo>объект уже создан, исключение может возникнуть из-за <xref:System.IO.FileInfo>будет пытаться обновить его <xref:System.IO.FileInfo.Length%2A>используя самый последний размер в байтах при первом обращении к свойству.</xref:System.IO.FileInfo.Length%2A> </xref:System.IO.FileInfo> </xref:System.IO.FileInfo> Поместив эту операцию в блок try-catch вне запроса, будет выполнено правило исключения использования операций в запросах, которые могут вызвать побочные эффекты. В общем случае отлично необходимо соблюдать осторожность при перехвате исключений, чтобы убедиться в том, что приложение не остается в неизвестном состоянии.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Создайте проект, в платформе .NET Framework версии 3.5 или более поздней версии с ссылку на библиотеку System.Core.dll и `Imports` оператор для пространства имен System.Linq.  
  
## <a name="see-also"></a>См. также  
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)   
 [LINQ и каталоги файлов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
