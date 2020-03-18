---
title: Как запросить самый большой файл или файлы в дереве папок (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: 20c8a917-0552-4514-b489-0b8b6a4c3b4c
ms.openlocfilehash: ed7d610bd292be4062db89f3c94af280e851141f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79168769"
---
# <a name="how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq-c"></a><span data-ttu-id="fbdec-102">Как запросить самый большой файл или файлы в дереве папок (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="fbdec-102">How to query for the largest file or files in a directory tree (LINQ) (C#)</span></span>
<span data-ttu-id="fbdec-103">В этом примере показано пять запросов, связанных с размером файла в байтах.</span><span class="sxs-lookup"><span data-stu-id="fbdec-103">This example shows five queries related to file size in bytes:</span></span>  
  
- <span data-ttu-id="fbdec-104">Извлечение размера в байтах наибольшего файла.</span><span class="sxs-lookup"><span data-stu-id="fbdec-104">How to retrieve the size in bytes of the largest file.</span></span>  
  
- <span data-ttu-id="fbdec-105">Извлечение размера в байтах наименьшего файла.</span><span class="sxs-lookup"><span data-stu-id="fbdec-105">How to retrieve the size in bytes of the smallest file.</span></span>  
  
- <span data-ttu-id="fbdec-106">Извлечение объекта <xref:System.IO.FileInfo> наибольшего или наименьшего файла из одной или нескольких папок в указанной корневой папке.</span><span class="sxs-lookup"><span data-stu-id="fbdec-106">How to retrieve the <xref:System.IO.FileInfo> object largest or smallest file from one or more folders under a specified root folder.</span></span>  
  
- <span data-ttu-id="fbdec-107">Извлечение последовательности, например 10 наибольших файлов.</span><span class="sxs-lookup"><span data-stu-id="fbdec-107">How to retrieve a sequence such as the 10 largest files.</span></span>  
  
- <span data-ttu-id="fbdec-108">Упорядочение файлов в группы на основании их размера в байтах, игнорируя файлы меньше заданного размера.</span><span class="sxs-lookup"><span data-stu-id="fbdec-108">How to order files into groups based on their file size in bytes, ignoring files that are less than a specified size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbdec-109">Пример</span><span class="sxs-lookup"><span data-stu-id="fbdec-109">Example</span></span>  
 <span data-ttu-id="fbdec-110">Следующий пример содержит пять отдельных запросов, которые показывают, как запрашивать и группировать файлы на основании их размера в байтах.</span><span class="sxs-lookup"><span data-stu-id="fbdec-110">The following example contains five separate queries that show how to query and group files, depending on their file size in bytes.</span></span> <span data-ttu-id="fbdec-111">Эти примеры можно легко изменить, чтобы создать запрос на основании других свойств объекта <xref:System.IO.FileInfo>.</span><span class="sxs-lookup"><span data-stu-id="fbdec-111">You can easily modify these examples to base the query on some other property of the <xref:System.IO.FileInfo> object.</span></span>  
  
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
  
 <span data-ttu-id="fbdec-112">Чтобы вернуть один или несколько полных объектов <xref:System.IO.FileInfo>, запрос должен сначала проверить каждый из них в источнике данных, а затем отсортировать их по значению свойства Length.</span><span class="sxs-lookup"><span data-stu-id="fbdec-112">To return one or more complete <xref:System.IO.FileInfo> objects, the query first must examine each one in the data source, and then sort them by the value of their Length property.</span></span> <span data-ttu-id="fbdec-113">Затем он может вернуть один объект или последовательность объектов с максимальной длиной.</span><span class="sxs-lookup"><span data-stu-id="fbdec-113">Then it can return the single one or the sequence with the greatest lengths.</span></span> <span data-ttu-id="fbdec-114"><xref:System.Linq.Enumerable.First%2A> возвращает первый элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="fbdec-114">Use <xref:System.Linq.Enumerable.First%2A> to return the first element in a list.</span></span> <span data-ttu-id="fbdec-115"><xref:System.Linq.Enumerable.Take%2A> возвращает первые n элементов.</span><span class="sxs-lookup"><span data-stu-id="fbdec-115">Use <xref:System.Linq.Enumerable.Take%2A> to return the first n number of elements.</span></span> <span data-ttu-id="fbdec-116">Укажите порядок сортировки по убыванию для размещения наименьших элементов в начале списка.</span><span class="sxs-lookup"><span data-stu-id="fbdec-116">Specify a descending sort order to put the smallest elements at the start of the list.</span></span>  
  
 <span data-ttu-id="fbdec-117">Запрос вызывает отдельный метод, чтобы получить размер файла в байтах для обработки возможных исключений, которые будут вызваны при удалении файла в другом потоке за период времени с момента создания объекта <xref:System.IO.FileInfo> в вызове `GetFiles`.</span><span class="sxs-lookup"><span data-stu-id="fbdec-117">The query calls out to a separate method to obtain the file size in bytes in order to consume the possible exception that will be raised in the case where a file was deleted on another thread in the time period since the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="fbdec-118">Даже если объект <xref:System.IO.FileInfo> уже создан, может возникнуть исключение, так как объект <xref:System.IO.FileInfo> будет пытаться обновить свойство <xref:System.IO.FileInfo.Length%2A>, используя самый последний размер в байтах при первом обращении к свойству.</span><span class="sxs-lookup"><span data-stu-id="fbdec-118">Even through the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property by using the most current size in bytes the first time the property is accessed.</span></span> <span data-ttu-id="fbdec-119">Поместив эту операцию в блок try-catch вне запроса, будет выполнено правило исключения использования операций в запросах, которые могут вызвать побочные эффекты.</span><span class="sxs-lookup"><span data-stu-id="fbdec-119">By putting this operation in a try-catch block outside the query, we follow the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="fbdec-120">В целом, необходимо соблюдать осторожность при перехвате исключений, чтобы убедиться, что приложение не остается в неизвестном состоянии.</span><span class="sxs-lookup"><span data-stu-id="fbdec-120">In general, great care must be taken when consuming exceptions, to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fbdec-121">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="fbdec-121">Compiling the Code</span></span>  
<span data-ttu-id="fbdec-122">Создайте проект консольного приложения C# с директивами `using` для пространств имен System.Linq и System.IO.</span><span class="sxs-lookup"><span data-stu-id="fbdec-122">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbdec-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fbdec-123">See also</span></span>

- [<span data-ttu-id="fbdec-124">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="fbdec-124">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
- [<span data-ttu-id="fbdec-125">LINQ и каталоги файлов (C#)</span><span class="sxs-lookup"><span data-stu-id="fbdec-125">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
