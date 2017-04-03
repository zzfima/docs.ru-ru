---
title: "Практическое руководство. Запрос общего числа байтов в наборе папок (LINQ) (C#) | Документы Майкрософт"
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
ms.assetid: a01bd1d4-133c-4ca2-aa4e-e93e81d6076c
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: dd78f36792ab65f31075a7a83660261f096953ae
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-c"></a>Практическое руководство. Запрос общего числа байтов в наборе папок (LINQ) (C#)
В этом примере показано, как получить общее число байтов, используемое всеми файлами в указанной папке и всех ее вложенных папках.  
  
## <a name="example"></a>Пример  
 Метод <xref:System.Linq.Enumerable.Sum%2A> суммирует значения всех элементов, выбранных в предложении `select`. Этот запрос можно легко изменить для извлечения наибольшего или наименьшего файла в дереве каталогов путем вызова метода <xref:System.Linq.Enumerable.Min%2A> или <xref:System.Linq.Enumerable.Max%2A> вместо <xref:System.Linq.Enumerable.Sum%2A>.  
  
```csharp  
class QuerySize  
{  
    public static void Main()  
    {  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\VC#";  
  
        // Take a snapshot of the file system.  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<string> fileList = System.IO.Directory.GetFiles(startFolder, "*.*", System.IO.SearchOption.AllDirectories);  
  
        var fileQuery = from file in fileList  
                        select GetFileLength(file);  
  
        // Cache the results to avoid multiple trips to the file system.  
        long[] fileLengths = fileQuery.ToArray();  
  
        // Return the size of the largest file  
        long largestFile = fileLengths.Max();  
  
        // Return the total number of bytes in all the files under the specified folder.  
        long totalBytes = fileLengths.Sum();  
  
        Console.WriteLine("There are {0} bytes in {1} files under {2}",  
            totalBytes, fileList.Count(), startFolder);  
        Console.WriteLine("The largest files is {0} bytes.", largestFile);  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit.");  
        Console.ReadKey();  
    }  
  
    // This method is used to swallow the possible exception  
    // that can be raised when accessing the System.IO.FileInfo.Length property.  
    static long GetFileLength(string filename)  
    {  
        long retval;  
        try  
        {  
            System.IO.FileInfo fi = new System.IO.FileInfo(filename);  
            retval = fi.Length;  
        }  
        catch (System.IO.FileNotFoundException)  
        {  
            // If a file is no longer present,  
            // just add zero bytes to the total.  
            retval = 0;  
        }  
        return retval;  
    }  
}  
```  
  
 Если требуется только подсчитать число байтов в указанном дереве каталогов, можно сделать это более эффективно без создания запроса LINQ, который вносит дополнительные издержки, связанные с созданием коллекции списков в качестве источника данных. Практичность подхода LINQ увеличивается по мере усложнения запроса или при необходимости выполнения нескольких запросов к одному источнику данных.  
  
 Для получения длины файла запрос вызывает отдельный метод. Это необходимо для обработки возможных исключений, которые могут возникнуть из-за удаления файла в другом потоке после создания объекта <xref:System.IO.FileInfo> вызовом `GetFiles`. Даже если объект <xref:System.IO.FileInfo> уже создан, может возникнуть исключение, так как объект <xref:System.IO.FileInfo> будет пытаться обновить свойство <xref:System.IO.FileInfo.Length%2A>, используя самую последнюю длину при первом обращении к свойству. При помещении этой операции в блок try-catch вне запроса будет выполнено правило исключения использования в запросах операций, которые могут вызвать побочные эффекты. В целом необходимо соблюдать осторожность при перехвате исключений, чтобы убедиться, что приложение не остается в неизвестном состоянии.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Создайте проект, предназначенный для .NET Framework 3.5 или более поздней версии, со ссылкой на библиотеку System.Core.dll и директивы `using` для пространств имен System.Linq и System.IO.  
  
## <a name="see-also"></a>См. также  
 [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)   
 [LINQ и каталоги файлов (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
