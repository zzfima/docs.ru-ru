---
title: Запрос содержимого файлов в папке (LINQ)
ms.date: 07/20/2015
ms.assetid: edacbcd3-f3e4-4429-a8be-28a58dc0dd70
ms.openlocfilehash: 02ffa398c495ca5af77685d62299c59cfc3b9d9c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347615"
---
# <a name="how-to-query-the-contents-of-files-in-a-folder-linq-visual-basic"></a>Запрос содержимого файлов в папке (LINQ) (Visual Basic)

В этом примере показано, как запросить все файлы в указанном дереве каталогов, открыть каждый файл и проверить его содержимое. Этот способ позволяет создать индексы для содержимого дерева каталогов или обратить их порядок. В этом примере выполняется простой поиск строки. Более сложные типы сопоставления шаблонов можно выполнять с помощью регулярных выражений. Дополнительные сведения см. [в разделе Практические руководства. Объединение запросов LINQ с помощью регулярных выражений (Visual Basic)](how-to-combine-linq-queries-with-regular-expressions.md).  
  
## <a name="example"></a>Пример  
  
```vb
Imports System.IO

Module Module1  
    'QueryContents  
    Public Sub Main()  
  
        ' Modify this path as necessary.  
        Dim startFolder = "C:\Program Files (x86)\Microsoft Visual Studio 14.0"  

        ' Take a snapshot of the folder contents.
        Dim dir As New DirectoryInfo(startFolder)
        Dim fileList = dir.GetFiles("*.*", SearchOption.AllDirectories)

        Dim searchTerm = "Welcome"

        ' Search the contents of each file.
        ' A regular expression created with the RegEx class
        ' could be used instead of the Contains method.
        Dim queryMatchingFiles = From file In fileList _
                                 Where file.Extension = ".html" _
                                 Let fileText = GetFileText(file.FullName) _
                                 Where fileText.Contains(searchTerm) _
                                 Select file.FullName

        Console.WriteLine("The term " & searchTerm & " was found in:")

        ' Execute the query.
        For Each filename In queryMatchingFiles
            Console.WriteLine(filename)
        Next

        ' Keep the console window open in debug mode.
        Console.WriteLine("Press any key to exit")
        Console.ReadKey()

    End Sub

    ' Read the contents of the file. This is done in a separate
    ' function in order to handle potential file system errors.
    Function GetFileText(name As String) As String

        ' If the file has been deleted, the right thing
        ' to do in this case is return an empty string.
        Dim fileContents = String.Empty

        ' If the file has been deleted since we took
        ' the snapshot, ignore it and return the empty string.
        If File.Exists(name) Then
            fileContents = File.ReadAllText(name)
        End If

        Return fileContents

    End Function
End Module
```

## <a name="compiling-the-code"></a>Компиляция кода

Создайте проект консольного приложения VB.NET, скопируйте и вставьте пример кода и измените значение объекта Startup в свойствах проекта.

## <a name="see-also"></a>См. также

- [LINQ to Objects (Visual Basic)](linq-to-objects.md)
- [LINQ и каталоги файлов (Visual Basic)](linq-and-file-directories.md)
