---
title: "Практическое руководство. Изменение порядка полей файла с разделителями (LINQ) (C#)"
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
ms.assetid: 4e62d82c-61b7-4f18-b9a1-86723746d7d2
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
ms.openlocfilehash: 83cc16d6f80b68d530b5daea67443e2e2b7dcf74
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-reorder-the-fields-of-a-delimited-file-linq-c"></a><span data-ttu-id="1237e-102">Практическое руководство. Изменение порядка полей файла с разделителями (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="1237e-102">How to: Reorder the Fields of a Delimited File (LINQ) (C#)</span></span>
<span data-ttu-id="1237e-103">CSV-файл — это текстовый файл, который часто используется для хранения данных электронных таблиц или других табличных данных, представленных строками и столбцами.</span><span class="sxs-lookup"><span data-stu-id="1237e-103">A comma-separated value (CSV) file is a text file that is often used to store spreadsheet data or other tabular data that is represented by rows and columns.</span></span> <span data-ttu-id="1237e-104">Использование метода <xref:System.String.Split%2A> для разделения полей упрощает создание запросов к CSV-файлам и управление ими с помощью LINQ.</span><span class="sxs-lookup"><span data-stu-id="1237e-104">By using the <xref:System.String.Split%2A> method to separate the fields, it is very easy to query and manipulate CSV files by using LINQ.</span></span> <span data-ttu-id="1237e-105">Фактически та же технология может использоваться для изменения порядка частей любой структурированной строки текста, а не только CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="1237e-105">In fact, the same technique can be used to reorder the parts of any structured line of text; it is not limited to CSV files.</span></span>  
  
 <span data-ttu-id="1237e-106">В следующем примере предполагается, что три столбца представляют "фамилию", "имя" и "идентификатор" учащихся.</span><span class="sxs-lookup"><span data-stu-id="1237e-106">In the following example, assume that the three columns represent students' "last name," "first name", and "ID."</span></span> <span data-ttu-id="1237e-107">Поля группируются в алфавитном порядке по фамилии учащихся.</span><span class="sxs-lookup"><span data-stu-id="1237e-107">The fields are in alphabetical order based on the students' last names.</span></span> <span data-ttu-id="1237e-108">Запрос создает новую последовательность, в которой столбец идентификатора отображается первым, за ним следует второй столбец, который объединяет имя и фамилию учащегося.</span><span class="sxs-lookup"><span data-stu-id="1237e-108">The query produces a new sequence in which the ID column appears first, followed by a second column that combines the student's first name and last name.</span></span> <span data-ttu-id="1237e-109">Порядок строк изменен в соответствии с полем идентификатора.</span><span class="sxs-lookup"><span data-stu-id="1237e-109">The lines are reordered according to the ID field.</span></span> <span data-ttu-id="1237e-110">Результаты сохраняются в новый файл, и исходные данные не изменяются.</span><span class="sxs-lookup"><span data-stu-id="1237e-110">The results are saved into a new file and the original data is not modified.</span></span>  
  
### <a name="to-create-the-data-file"></a><span data-ttu-id="1237e-111">Создание файла данных</span><span class="sxs-lookup"><span data-stu-id="1237e-111">To create the data file</span></span>  
  
1.  <span data-ttu-id="1237e-112">Скопируйте следующие строки в обычный текстовый файл с именем spreadsheet1.csv.</span><span class="sxs-lookup"><span data-stu-id="1237e-112">Copy the following lines into a plain text file that is named spreadsheet1.csv.</span></span> <span data-ttu-id="1237e-113">Сохраните файл в папке проекта.</span><span class="sxs-lookup"><span data-stu-id="1237e-113">Save the file in your project folder.</span></span>  
  
    ```  
    Adams,Terry,120  
    Fakhouri,Fadi,116  
    Feng,Hanying,117  
    Garcia,Cesar,114  
    Garcia,Debra,115  
    Garcia,Hugo,118  
    Mortensen,Sven,113  
    O'Donnell,Claire,112  
    Omelchenko,Svetlana,111  
    Tucker,Lance,119  
    Tucker,Michael,122  
    Zabokritski,Eugene,121  
    ```  
  
## <a name="example"></a><span data-ttu-id="1237e-114">Пример</span><span class="sxs-lookup"><span data-stu-id="1237e-114">Example</span></span>  
  
```csharp  
class CSVFiles  
{  
    static void Main(string[] args)  
    {  
        // Create the IEnumerable data source  
        string[] lines = System.IO.File.ReadAllLines(@"../../../spreadsheet1.csv");  
  
        // Create the query. Put field 2 first, then  
        // reverse and combine fields 0 and 1 from the old field  
        IEnumerable<string> query =  
            from line in lines  
            let x = line.Split(',')  
            orderby x[2]  
            select x[2] + ", " + (x[1] + " " + x[0]);  
  
        // Execute the query and write out the new file. Note that WriteAllLines  
        // takes a string[], so ToArray is called on the query.  
        System.IO.File.WriteAllLines(@"../../../spreadsheet2.csv", query.ToArray());  
  
        Console.WriteLine("Spreadsheet2.csv written to disk. Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output to spreadsheet2.csv:  
111, Svetlana Omelchenko  
112, Claire O'Donnell  
113, Sven Mortensen  
114, Cesar Garcia  
115, Debra Garcia  
116, Fadi Fakhouri  
117, Hanying Feng  
118, Hugo Garcia  
119, Lance Tucker  
120, Terry Adams  
121, Eugene Zabokritski  
122, Michael Tucker  
 */  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1237e-115">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="1237e-115">Compiling the Code</span></span>  
 <span data-ttu-id="1237e-116">Создайте проект, предназначенный для .NET Framework 3.5 или более поздней версии, со ссылкой на библиотеку System.Core.dll и директивы `using` для пространств имен System.Linq и System.IO.</span><span class="sxs-lookup"><span data-stu-id="1237e-116">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1237e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="1237e-117">See Also</span></span>  
 <span data-ttu-id="1237e-118">[LINQ и строки (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md) </span><span class="sxs-lookup"><span data-stu-id="1237e-118">[LINQ and Strings (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md) </span></span>  
 <span data-ttu-id="1237e-119">[LINQ и каталоги файлов (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md) </span><span class="sxs-lookup"><span data-stu-id="1237e-119">[LINQ and File Directories (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md) </span></span>  
 [<span data-ttu-id="1237e-120">Практическое руководство. Создание кода XML из CSV-файлов</span><span class="sxs-lookup"><span data-stu-id="1237e-120">How to: Generate XML from CSV Files</span></span>](http://msdn.microsoft.com/library/dd7bab8c-96fa-4343-94d0-9739dd6a74fd)

