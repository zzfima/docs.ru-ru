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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 668a8a4d89f7b81c3aef9b4e1a46ad749c4a8341
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-visual-basic"></a>Практическое руководство: запрос общее количество байтов в наборе папок (LINQ) (Visual Basic)
В этом примере показано, как получить общее число байтов, используемых все файлы в указанной папке и всех ее подпапках.  
  
## <a name="example"></a>Пример  
 <xref:System.Linq.Enumerable.Sum%2A>Метод складывает значения всех элементов, выбранных в `select` предложение.</xref:System.Linq.Enumerable.Sum%2A> Вы легко можете изменить этот запрос для получения наибольшего или наименьшего файла в дереве каталогов путем вызова <xref:System.Linq.Enumerable.Min%2A>или <xref:System.Linq.Enumerable.Max%2A>вместо <xref:System.Linq.Enumerable.Sum%2A>.</xref:System.Linq.Enumerable.Sum%2A> </xref:System.Linq.Enumerable.Max%2A> </xref:System.Linq.Enumerable.Min%2A>  
  
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
  
 При наличии только число байтов в указанном дереве каталогов, можно сделать это более эффективно без создания запроса LINQ, который вносит дополнительную нагрузку, связанную с созданием коллекции списков в качестве источника данных. Полезность этого подхода LINQ увеличивается по мере более сложный запрос или при необходимости выполнения нескольких запросов к одному источнику данных.  
  
 Запрос вызывает отдельный метод для получения длины файла. Это делается для обработки возможных исключений, которые могут возникнуть, если файл был удален в другом потоке после <xref:System.IO.FileInfo>объект был создан в вызове `GetFiles`.</xref:System.IO.FileInfo> Несмотря на то что <xref:System.IO.FileInfo>объект уже создан, исключение может возникнуть из-за <xref:System.IO.FileInfo>будет пытаться обновить его <xref:System.IO.FileInfo.Length%2A>свойство с самую последнюю длину при первом обращении к свойству.</xref:System.IO.FileInfo.Length%2A> </xref:System.IO.FileInfo> </xref:System.IO.FileInfo> Поместив эту операцию в блок try-catch вне запроса, код следует правилу избежать операции в запросах, которые могут вызвать побочные эффекты. В общем случае отлично необходимо соблюдать осторожность при перехвате исключений, чтобы убедиться в том, что приложение не остается в неизвестном состоянии.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Создайте проект, в платформе .NET Framework версии 3.5 или более поздней версии с ссылку на библиотеку System.Core.dll и `Imports` оператор для пространства имен System.Linq.  
  
## <a name="see-also"></a>См. также  
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)   
 [LINQ и каталоги файлов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
