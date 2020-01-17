---
title: Получение общего числа байтов в наборе папок (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: a01bd1d4-133c-4ca2-aa4e-e93e81d6076c
ms.openlocfilehash: c6bfe6bb6d76e7ce8ea8887eef85cd64f2a025df
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344819"
---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-c"></a>Получение общего числа байтов в наборе папок (LINQ) (C#)
В этом примере показано, как получить общее число байтов, используемое всеми файлами в указанной папке и всех ее вложенных папках.  
  
## <a name="example"></a>Пример  
 Метод <xref:System.Linq.Enumerable.Sum%2A> суммирует значения всех элементов, выбранных в предложении `select`. Этот запрос можно легко изменить, чтобы получить самый большой или маленький файл в заданном дереве каталогов, вызвав метод <xref:System.Linq.Enumerable.Min%2A> или <xref:System.Linq.Enumerable.Max%2A> вместо <xref:System.Linq.Enumerable.Sum%2A>.  
  
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
Создайте проект консольного приложения C# с директивами `using` для пространств имен System.Linq и System.IO.
  
## <a name="see-also"></a>См. также

- [LINQ to Objects (C#)](./linq-to-objects.md)
- [LINQ и каталоги файлов (C#)](./linq-and-file-directories.md)
