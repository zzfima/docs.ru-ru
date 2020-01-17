---
title: Как запросить самый большой файл или файлы в дереве папок (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: 20c8a917-0552-4514-b489-0b8b6a4c3b4c
ms.openlocfilehash: dee501dc8d0cabd718307b45c99ca049ae4250aa
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344554"
---
# <a name="how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq-c"></a>Как запросить самый большой файл или файлы в дереве папок (LINQ) (C#)
В этом примере показано пять запросов, связанных с размером файла в байтах.  
  
- Извлечение размера в байтах наибольшего файла.  
  
- Извлечение размера в байтах наименьшего файла.  
  
- Извлечение объекта <xref:System.IO.FileInfo> наибольшего или наименьшего файла из одной или нескольких папок в указанной корневой папке.  
  
- Извлечение последовательности, например 10 наибольших файлов.  
  
- Упорядочение файлов в группы на основании их размера в байтах, игнорируя файлы меньше заданного размера.  
  
## <a name="example"></a>Пример  
 Следующий пример содержит пять отдельных запросов, которые показывают, как запрашивать и группировать файлы на основании их размера в байтах. Эти примеры можно легко изменить, чтобы создать запрос на основании других свойств объекта <xref:System.IO.FileInfo>.  
  
```csharp  
class QueryBySize  
{  
    static void Main(string[] args)  
    {  
        QueryFilesBySize();  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    private static void QueryFilesBySize()  
    {  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        //Return the size of the largest file  
        long maxSize =  
            (from file in fileList  
             let len = GetFileLength(file)  
             select len)  
             .Max();  
  
        Console.WriteLine("The length of the largest file under {0} is {1}",  
            startFolder, maxSize);  
  
        // Return the FileInfo object for the largest file  
        // by sorting and selecting from beginning of list  
        System.IO.FileInfo longestFile =  
            (from file in fileList  
             let len = GetFileLength(file)  
             where len > 0  
             orderby len descending  
             select file)  
            .First();  
  
        Console.WriteLine("The largest file under {0} is {1} with a length of {2} bytes",  
                            startFolder, longestFile.FullName, longestFile.Length);  
  
        //Return the FileInfo of the smallest file  
        System.IO.FileInfo smallestFile =  
            (from file in fileList  
             let len = GetFileLength(file)  
             where len > 0  
             orderby len ascending  
             select file).First();  
  
        Console.WriteLine("The smallest file under {0} is {1} with a length of {2} bytes",  
                            startFolder, smallestFile.FullName, smallestFile.Length);  
  
        //Return the FileInfos for the 10 largest files  
        // queryTenLargest is an IEnumerable<System.IO.FileInfo>  
        var queryTenLargest =  
            (from file in fileList  
             let len = GetFileLength(file)  
             orderby len descending  
             select file).Take(10);  
  
        Console.WriteLine("The 10 largest files under {0} are:", startFolder);  
  
        foreach (var v in queryTenLargest)  
        {  
            Console.WriteLine("{0}: {1} bytes", v.FullName, v.Length);  
        }  
  
        // Group the files according to their size, leaving out  
        // files that are less than 200000 bytes.   
        var querySizeGroups =  
            from file in fileList  
            let len = GetFileLength(file)  
            where len > 0  
            group file by (len / 100000) into fileGroup  
            where fileGroup.Key >= 2  
            orderby fileGroup.Key descending  
            select fileGroup;  
  
        foreach (var filegroup in querySizeGroups)  
        {  
            Console.WriteLine(filegroup.Key.ToString() + "00000");  
            foreach (var item in filegroup)  
            {  
                Console.WriteLine("\t{0}: {1}", item.Name, item.Length);  
            }  
        }  
    }  
  
    // This method is used to swallow the possible exception  
    // that can be raised when accessing the FileInfo.Length property.  
    // In this particular case, it is safe to swallow the exception.  
    static long GetFileLength(System.IO.FileInfo fi)  
    {  
        long retval;  
        try  
        {  
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
  
 Чтобы вернуть один или несколько полных объектов <xref:System.IO.FileInfo>, запрос должен сначала проверить каждый из них в источнике данных, а затем отсортировать их по значению свойства Length. Затем он может вернуть один объект или последовательность объектов с максимальной длиной. <xref:System.Linq.Enumerable.First%2A> возвращает первый элемент в списке. <xref:System.Linq.Enumerable.Take%2A> возвращает первые n элементов. Укажите порядок сортировки по убыванию для размещения наименьших элементов в начале списка.  
  
 Запрос вызывает отдельный метод, чтобы получить размер файла в байтах для обработки возможных исключений, которые будут вызваны при удалении файла в другом потоке за период времени с момента создания объекта <xref:System.IO.FileInfo> в вызове `GetFiles`. Даже если объект <xref:System.IO.FileInfo> уже создан, может возникнуть исключение, так как объект <xref:System.IO.FileInfo> будет пытаться обновить свойство <xref:System.IO.FileInfo.Length%2A>, используя самый последний размер в байтах при первом обращении к свойству. Поместив эту операцию в блок try-catch вне запроса, будет выполнено правило исключения использования операций в запросах, которые могут вызвать побочные эффекты. В целом, необходимо соблюдать осторожность при перехвате исключений, чтобы убедиться, что приложение не остается в неизвестном состоянии.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
Создайте проект консольного приложения C# с директивами `using` для пространств имен System.Linq и System.IO.
 
## <a name="see-also"></a>См. также

- [LINQ to Objects (C#)](./linq-to-objects.md)
- [LINQ и каталоги файлов (C#)](./linq-and-file-directories.md)
