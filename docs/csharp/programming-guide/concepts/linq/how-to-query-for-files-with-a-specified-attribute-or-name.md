---
title: "Практическое руководство. Запрос файлов с указанными атрибутами или именем (C#)"
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
ms.assetid: 560e3879-b0b3-4549-ad02-0a53aff2f83c
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2bfb7e19dcb6562dfc9b9efd24bec93774dfbee9
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-query-for-files-with-a-specified-attribute-or-name-c"></a><span data-ttu-id="9a652-102">Практическое руководство. Запрос файлов с указанными атрибутами или именем (C#)</span><span class="sxs-lookup"><span data-stu-id="9a652-102">How to: Query for Files with a Specified Attribute or Name (C#)</span></span>
<span data-ttu-id="9a652-103">В этом примере показано, как обнаружить все файлы с указанным расширением (например, TXT) в заданном дереве каталогов.</span><span class="sxs-lookup"><span data-stu-id="9a652-103">This example shows how to find all files that have a specified file name extension (for example ".txt") in a specified directory tree.</span></span> <span data-ttu-id="9a652-104">Кроме того, он показывает, как обнаружить самый новый или самый старый файл в дереве, используя время создания.</span><span class="sxs-lookup"><span data-stu-id="9a652-104">It also shows how to return either the newest or oldest file in the tree based on the creation time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a652-105">Пример</span><span class="sxs-lookup"><span data-stu-id="9a652-105">Example</span></span>  
  
```csharp  
class FindFileByExtension  
{  
    // This query will produce the full path for all .txt files  
    // under the specified folder including subfolders.  
    // It orders the list according to the file name.  
    static void Main()  
    {  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        //Create the query  
        IEnumerable<System.IO.FileInfo> fileQuery =  
            from file in fileList  
            where file.Extension == ".txt"  
            orderby file.Name  
            select file;  
  
        //Execute the query. This might write out a lot of files!  
        foreach (System.IO.FileInfo fi in fileQuery)  
        {  
            Console.WriteLine(fi.FullName);  
        }  
  
        // Create and execute a new query by using the previous   
        // query as a starting point. fileQuery is not   
        // executed again until the call to Last()  
        var newestFile =  
            (from file in fileQuery  
             orderby file.CreationTime  
             select new { file.FullName, file.CreationTime })  
            .Last();  
  
        Console.WriteLine("\r\nThe newest .txt file is {0}. Creation time: {1}",  
            newestFile.FullName, newestFile.CreationTime);  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9a652-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="9a652-106">Compiling the Code</span></span>  
 <span data-ttu-id="9a652-107">Создайте проект, предназначенный для .NET Framework 3.5 или более поздней версии, со ссылкой на библиотеку System.Core.dll и директивы `using` для пространств имен System.Linq и System.IO.</span><span class="sxs-lookup"><span data-stu-id="9a652-107">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to   System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a652-108">См. также</span><span class="sxs-lookup"><span data-stu-id="9a652-108">See Also</span></span>  
 <span data-ttu-id="9a652-109">[LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md) </span><span class="sxs-lookup"><span data-stu-id="9a652-109">[LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md) </span></span>  
 [<span data-ttu-id="9a652-110">LINQ и каталоги файлов (C#)</span><span class="sxs-lookup"><span data-stu-id="9a652-110">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)

