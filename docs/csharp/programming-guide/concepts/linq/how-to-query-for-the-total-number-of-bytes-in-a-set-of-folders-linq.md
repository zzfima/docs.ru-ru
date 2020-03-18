---
title: Получение общего числа байтов в наборе папок (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: a01bd1d4-133c-4ca2-aa4e-e93e81d6076c
ms.openlocfilehash: c6bfe6bb6d76e7ce8ea8887eef85cd64f2a025df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75344819"
---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-c"></a><span data-ttu-id="5d087-102">Получение общего числа байтов в наборе папок (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="5d087-102">How to query for the total number of bytes in a set of folders (LINQ) (C#)</span></span>
<span data-ttu-id="5d087-103">В этом примере показано, как получить общее число байтов, используемое всеми файлами в указанной папке и всех ее вложенных папках.</span><span class="sxs-lookup"><span data-stu-id="5d087-103">This example shows how to retrieve the total number of bytes used by all the files in a specified folder and all its subfolders.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d087-104">Пример</span><span class="sxs-lookup"><span data-stu-id="5d087-104">Example</span></span>  
 <span data-ttu-id="5d087-105">Метод <xref:System.Linq.Enumerable.Sum%2A> суммирует значения всех элементов, выбранных в предложении `select`.</span><span class="sxs-lookup"><span data-stu-id="5d087-105">The <xref:System.Linq.Enumerable.Sum%2A> method adds the values of all the items selected in the `select` clause.</span></span> <span data-ttu-id="5d087-106">Этот запрос можно легко изменить, чтобы получить самый большой или маленький файл в заданном дереве каталогов, вызвав метод <xref:System.Linq.Enumerable.Min%2A> или <xref:System.Linq.Enumerable.Max%2A> вместо <xref:System.Linq.Enumerable.Sum%2A>.</span><span class="sxs-lookup"><span data-stu-id="5d087-106">You can easily modify this query to retrieve the biggest or smallest file in the specified directory tree by calling the <xref:System.Linq.Enumerable.Min%2A> or <xref:System.Linq.Enumerable.Max%2A> method instead of <xref:System.Linq.Enumerable.Sum%2A>.</span></span>  
  
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
  
 <span data-ttu-id="5d087-107">Если требуется только подсчитать число байтов в указанном дереве каталогов, можно сделать это более эффективно без создания запроса LINQ, который вносит дополнительные издержки, связанные с созданием коллекции списков в качестве источника данных.</span><span class="sxs-lookup"><span data-stu-id="5d087-107">If you only have to count the number of bytes in a specified directory tree, you can do this more efficiently without creating a LINQ query, which incurs the overhead of creating the list collection as a data source.</span></span> <span data-ttu-id="5d087-108">Практичность подхода LINQ увеличивается по мере усложнения запроса или при необходимости выполнения нескольких запросов к одному источнику данных.</span><span class="sxs-lookup"><span data-stu-id="5d087-108">The usefulness of the LINQ approach increases as the query becomes more complex, or when you have to run multiple queries against the same data source.</span></span>  
  
 <span data-ttu-id="5d087-109">Для получения длины файла запрос вызывает отдельный метод.</span><span class="sxs-lookup"><span data-stu-id="5d087-109">The query calls out to a separate method to obtain the file length.</span></span> <span data-ttu-id="5d087-110">Это необходимо для обработки возможных исключений, которые могут возникнуть из-за удаления файла в другом потоке после создания объекта <xref:System.IO.FileInfo> вызовом `GetFiles`.</span><span class="sxs-lookup"><span data-stu-id="5d087-110">It does this in order to consume the possible exception that will be raised if the file was deleted on another thread after the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="5d087-111">Даже если объект <xref:System.IO.FileInfo> уже создан, может возникнуть исключение, так как объект <xref:System.IO.FileInfo> будет пытаться обновить свойство <xref:System.IO.FileInfo.Length%2A>, используя самую последнюю длину при первом обращении к свойству.</span><span class="sxs-lookup"><span data-stu-id="5d087-111">Even though the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property with the most current length the first time the property is accessed.</span></span> <span data-ttu-id="5d087-112">При помещении этой операции в блок try-catch вне запроса будет выполнено правило исключения использования в запросах операций, которые могут вызвать побочные эффекты.</span><span class="sxs-lookup"><span data-stu-id="5d087-112">By putting this operation in a try-catch block outside the query, the code follows the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="5d087-113">В целом необходимо соблюдать осторожность при перехвате исключений, чтобы убедиться, что приложение не остается в неизвестном состоянии.</span><span class="sxs-lookup"><span data-stu-id="5d087-113">In general, great care must be taken when you consume exceptions to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5d087-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="5d087-114">Compiling the Code</span></span>  
<span data-ttu-id="5d087-115">Создайте проект консольного приложения C# с директивами `using` для пространств имен System.Linq и System.IO.</span><span class="sxs-lookup"><span data-stu-id="5d087-115">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5d087-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5d087-116">See also</span></span>

- [<span data-ttu-id="5d087-117">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="5d087-117">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
- [<span data-ttu-id="5d087-118">LINQ и каталоги файлов (C#)</span><span class="sxs-lookup"><span data-stu-id="5d087-118">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
