---
title: "Практическое руководство. Запрос содержимого текстовых файлов в папке (LINQ) (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: f5b4dce7-1a34-4eb4-9bf1-60d5bdda264c
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1aa2ef581dcba5814657681daebd07be70e498b1
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-query-the-contents-of-text-files-in-a-folder-linq-c"></a>Практическое руководство. Запрос содержимого текстовых файлов в папке (LINQ) (C#)
В этом примере показано, как запросить все файлы в указанном дереве каталогов, открыть каждый файл и проверить его содержимое. Этот способ позволяет создать индексы для содержимого дерева каталогов или обратить их порядок. В этом примере выполняется простой поиск строки. Более сложные типы сопоставления шаблонов можно выполнять с помощью регулярных выражений. Дополнительные сведения см. в разделе [Практическое руководство. Объединение запросов LINQ с помощью регулярных выражений (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md).  
  
## <a name="example"></a>Пример  
  
```csharp  
class QueryContents  
{  
    public static void Main()  
    {  
        // Modify this path as necessary.  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        string searchTerm = @"Visual Studio";  
  
        // Search the contents of each file.  
        // A regular expression created with the RegEx class  
        // could be used instead of the Contains method.  
        // queryMatchingFiles is an IEnumerable<string>.  
        var queryMatchingFiles =  
            from file in fileList  
            where file.Extension == ".htm"  
            let fileText = GetFileText(file.FullName)  
            where fileText.Contains(searchTerm)  
            select file.FullName;  
  
        // Execute the query.  
        Console.WriteLine("The term \"{0}\" was found in:", searchTerm);  
        foreach (string filename in queryMatchingFiles)  
        {  
            Console.WriteLine(filename);  
        }  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    // Read the contents of the file.  
    static string GetFileText(string name)  
    {  
        string fileContents = String.Empty;  
  
        // If the file has been deleted since we took   
        // the snapshot, ignore it and return the empty string.  
        if (System.IO.File.Exists(name))  
        {  
            fileContents = System.IO.File.ReadAllText(name);  
        }  
        return fileContents;  
    }  
}  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Создайте проект, предназначенный для .NET Framework 3.5 или более поздней версии, со ссылкой на библиотеку System.Core.dll и директивы `using` для пространств имен System.Linq и System.IO.  
  
## <a name="see-also"></a>См. также  
 [LINQ и каталоги файлов (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)   
 [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)

