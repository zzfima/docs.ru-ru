---
title: Пример отложенного выполнения (C#)
ms.date: 07/20/2015
ms.assetid: 50f4fbac-81fe-4f26-aedf-506e21419b19
ms.openlocfilehash: 8613f2335e5b3cb2a012f5309307e081b9400709
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33335930"
---
# <a name="deferred-execution-example-c"></a><span data-ttu-id="198b0-102">Пример отложенного выполнения (C#)</span><span class="sxs-lookup"><span data-stu-id="198b0-102">Deferred Execution Example (C#)</span></span>
<span data-ttu-id="198b0-103">В данном разделе показано влияние отложенного выполнения и отложенного вычисления на запросы LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="198b0-103">This topic shows how deferred execution and lazy evaluation affect the execution of your LINQ to XML queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="198b0-104">Пример</span><span class="sxs-lookup"><span data-stu-id="198b0-104">Example</span></span>  
 <span data-ttu-id="198b0-105">В следующем примере демонстрируется порядок выполнения при использовании метода расширения, в котором применяется отложенное выполнение.</span><span class="sxs-lookup"><span data-stu-id="198b0-105">The following example shows the order of execution when using an extension method that uses deferred execution.</span></span> <span data-ttu-id="198b0-106">В этом примере объявляется массив из трех строк.</span><span class="sxs-lookup"><span data-stu-id="198b0-106">The example declares an array of three strings.</span></span> <span data-ttu-id="198b0-107">Затем в нем производится итерация по коллекции, возвращенной `ConvertCollectionToUpperCase`.</span><span class="sxs-lookup"><span data-stu-id="198b0-107">It then iterates through the collection returned by `ConvertCollectionToUpperCase`.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source {0}", str);  
            yield return str.ToUpper();  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        var q = from str in stringArray.ConvertCollectionToUpperCase()  
                select str;  
  
        foreach (string str in q)  
            Console.WriteLine("Main: str {0}", str);  
    }  
}  
```  
  
 <span data-ttu-id="198b0-108">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="198b0-108">This example produces the following output:</span></span>  
  
```  
ToUpper: source abc  
Main: str ABC  
ToUpper: source def  
Main: str DEF  
ToUpper: source ghi  
Main: str GHI  
```  
  
 <span data-ttu-id="198b0-109">Обратите внимание, что во время итерации по коллекции, возвращенной `ConvertCollectionToUpperCase`, происходит получение каждого элемента из исходного массива строк и преобразование символов в верхний регистр до получения следующего элемента из исходного массива строк.</span><span class="sxs-lookup"><span data-stu-id="198b0-109">Notice that when iterating through the collection returned by `ConvertCollectionToUpperCase`, each item is retrieved from the source string array and converted to uppercase before the next item is retrieved from the source string array.</span></span>  
  
 <span data-ttu-id="198b0-110">Видно, что весь массив строк не преобразуется в символы верхнего регистра, пока каждый элемент возвращенной коллекции не будет обработан циклом `foreach` в `Main`.</span><span class="sxs-lookup"><span data-stu-id="198b0-110">You can see that the entire array of strings is not converted to uppercase before each item in the returned collection is processed in the `foreach` loop in `Main`.</span></span>  
  
 <span data-ttu-id="198b0-111">Следующий раздел учебника иллюстрирует объединение запросов в цепочки:</span><span class="sxs-lookup"><span data-stu-id="198b0-111">The next topic in this tutorial illustrates chaining queries together:</span></span>  
  
-   [<span data-ttu-id="198b0-112">Пример связывания запросов (C#)</span><span class="sxs-lookup"><span data-stu-id="198b0-112">Chaining Queries Example (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/chaining-queries-example.md)  
  
## <a name="see-also"></a><span data-ttu-id="198b0-113">См. также</span><span class="sxs-lookup"><span data-stu-id="198b0-113">See Also</span></span>  
 [<span data-ttu-id="198b0-114">Учебник. Объединение запросов в цепочки (C#)</span><span class="sxs-lookup"><span data-stu-id="198b0-114">Tutorial: Chaining Queries Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)
