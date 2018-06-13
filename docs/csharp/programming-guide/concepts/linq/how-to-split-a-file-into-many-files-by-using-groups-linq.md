---
title: Практическое руководство. Разделение файла на несколько файлов с помощью групп (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: 8179b91c-d778-4e57-884f-77fe5a8e4e40
ms.openlocfilehash: 8cce9176c303efe0da4b546afabe2bf6d491e167
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33326977"
---
# <a name="how-to-split-a-file-into-many-files-by-using-groups-linq-c"></a><span data-ttu-id="a1f97-102">Практическое руководство. Разделение файла на несколько файлов с помощью групп (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="a1f97-102">How to: Split a File Into Many Files by Using Groups (LINQ) (C#)</span></span>
<span data-ttu-id="a1f97-103">В этом примере показан один из способов объединения содержимого двух файлов и последующего создания набора новых файлов, данные в котором будут организованы иначе.</span><span class="sxs-lookup"><span data-stu-id="a1f97-103">This example shows one way to merge the contents of two files and then create a set of new files that organize the data in a new way.</span></span>  
  
### <a name="to-create-the-data-files"></a><span data-ttu-id="a1f97-104">Создание файлов данных</span><span class="sxs-lookup"><span data-stu-id="a1f97-104">To create the data files</span></span>  
  
1.  <span data-ttu-id="a1f97-105">Скопируйте эти имена в текстовый файл с именем names1.txt и сохраните его в папке проекта:</span><span class="sxs-lookup"><span data-stu-id="a1f97-105">Copy these names into a text file that is named names1.txt and save it in your project folder:</span></span>  
  
    ```  
    Bankov, Peter  
    Holm, Michael  
    Garcia, Hugo  
    Potra, Cristina  
    Noriega, Fabricio  
    Aw, Kam Foo  
    Beebe, Ann  
    Toyoshima, Tim  
    Guy, Wey Yuan  
    Garcia, Debra  
    ```  
  
2.  <span data-ttu-id="a1f97-106">Скопируйте эти имена в текстовый файл с именем names2.txt и сохраните его в папке проекта. Обратите внимание на то, что имена этих двух файлов похожи.</span><span class="sxs-lookup"><span data-stu-id="a1f97-106">Copy these names into a text file that is named names2.txt and save it in your project folder: Note that the two files have some names in common.</span></span>  
  
    ```  
    Liu, Jinghao  
    Bankov, Peter  
    Holm, Michael  
    Garcia, Hugo  
    Beebe, Ann  
    Gilchrist, Beth  
    Myrcha, Jacek  
    Giakoumakis, Leo  
    McLin, Nkenge  
    El Yassir, Mehdi  
    ```  
  
## <a name="example"></a><span data-ttu-id="a1f97-107">Пример</span><span class="sxs-lookup"><span data-stu-id="a1f97-107">Example</span></span>  
  
```csharp  
class SplitWithGroups  
{  
    static void Main()  
    {  
        string[] fileA = System.IO.File.ReadAllLines(@"../../../names1.txt");  
        string[] fileB = System.IO.File.ReadAllLines(@"../../../names2.txt");  
  
        // Concatenate and remove duplicate names based on  
        // default string comparer  
        var mergeQuery = fileA.Union(fileB);  
  
        // Group the names by the first letter in the last name.  
        var groupQuery = from name in mergeQuery  
                         let n = name.Split(',')  
                         group name by n[0][0] into g  
                         orderby g.Key  
                         select g;  
  
        // Create a new file for each group that was created  
        // Note that nested foreach loops are required to access  
        // individual items with each group.  
        foreach (var g in groupQuery)  
        {  
            // Create the new file name.  
            string fileName = @"../../../testFile_" + g.Key + ".txt";  
  
            // Output to display.  
            Console.WriteLine(g.Key);  
  
            // Write file.  
            using (System.IO.StreamWriter sw = new System.IO.StreamWriter(fileName))  
            {  
                foreach (var item in g)  
                {  
                    sw.WriteLine(item);  
                    // Output to console for example purposes.  
                    Console.WriteLine("   {0}", item);  
                }  
            }  
        }  
        // Keep console window open in debug mode.  
        Console.WriteLine("Files have been written. Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:   
    A  
       Aw, Kam Foo  
    B  
       Bankov, Peter  
       Beebe, Ann  
    E  
       El Yassir, Mehdi  
    G  
       Garcia, Hugo  
       Guy, Wey Yuan  
       Garcia, Debra  
       Gilchrist, Beth  
       Giakoumakis, Leo  
    H  
       Holm, Michael  
    L  
       Liu, Jinghao  
    M  
       Myrcha, Jacek  
       McLin, Nkenge  
    N  
       Noriega, Fabricio  
    P  
       Potra, Cristina  
    T  
       Toyoshima, Tim  
 */  
```  
  
 <span data-ttu-id="a1f97-108">Программа записывает отдельный файл для каждой группы в ту же папку, где находятся файлы данных.</span><span class="sxs-lookup"><span data-stu-id="a1f97-108">The program writes a separate file for each group in the same folder as the data files.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a1f97-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a1f97-109">Compiling the Code</span></span>  
 <span data-ttu-id="a1f97-110">Создайте проект, предназначенный для .NET Framework 3.5 или более поздней версии, со ссылкой на библиотеку System.Core.dll и директивы `using` для пространств имен System.Linq и System.IO.</span><span class="sxs-lookup"><span data-stu-id="a1f97-110">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1f97-111">См. также</span><span class="sxs-lookup"><span data-stu-id="a1f97-111">See Also</span></span>  
 [<span data-ttu-id="a1f97-112">LINQ и строки (C#)</span><span class="sxs-lookup"><span data-stu-id="a1f97-112">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)  
 [<span data-ttu-id="a1f97-113">LINQ и каталоги файлов (C#)</span><span class="sxs-lookup"><span data-stu-id="a1f97-113">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
