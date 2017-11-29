---
title: "Как: запрос общее число байтов в наборе папок (LINQ) (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bfe85ed2-44dc-4ef1-aac7-241622b80a69
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b200581f4876400727c63e86e3ccf4a44c67914b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-visual-basic"></a>Как: запрос общее число байтов в наборе папок (LINQ) (Visual Basic)
В этом примере показано, как получить общее число байтов, используемое всеми файлами в указанной папке и всех ее вложенных папках.  
  
## <a name="example"></a>Пример  
 Метод <xref:System.Linq.Enumerable.Sum%2A> суммирует значения всех элементов, выбранных в предложении `select`. Этот запрос можно легко изменить, чтобы получить самый большой или маленький файл в заданном дереве каталогов, вызвав метод <xref:System.Linq.Enumerable.Min%2A> или <xref:System.Linq.Enumerable.Max%2A> вместо <xref:System.Linq.Enumerable.Sum%2A>.  
  
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
  
 Если требуется только подсчитать число байтов в указанном дереве каталогов, можно сделать это более эффективно без создания запроса LINQ, который вносит дополнительные издержки, связанные с созданием коллекции списков в качестве источника данных. Практичность подхода LINQ увеличивается по мере усложнения запроса или при необходимости выполнения нескольких запросов к одному источнику данных.  
  
 Для получения длины файла запрос вызывает отдельный метод. Это необходимо для обработки возможных исключений, которые могут возникнуть из-за удаления файла в другом потоке после создания объекта <xref:System.IO.FileInfo> вызовом `GetFiles`. Даже если объект <xref:System.IO.FileInfo> уже создан, может возникнуть исключение, так как объект <xref:System.IO.FileInfo> будет пытаться обновить свойство <xref:System.IO.FileInfo.Length%2A>, используя самую последнюю длину при первом обращении к свойству. При помещении этой операции в блок try-catch вне запроса будет выполнено правило исключения использования в запросах операций, которые могут вызвать побочные эффекты. В целом необходимо соблюдать осторожность при перехвате исключений, чтобы убедиться, что приложение не остается в неизвестном состоянии.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Создайте в проекте, ориентированном на .NET Framework версии 3.5 или более поздней версии с ссылку на библиотеку System.Core.dll и `Imports` оператор для пространства имен System.Linq.  
  
## <a name="see-also"></a>См. также  
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
 [LINQ и каталоги файлов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
