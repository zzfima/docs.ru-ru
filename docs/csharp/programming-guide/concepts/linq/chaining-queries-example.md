---
title: Пример связывания запросов (C#)
ms.date: 07/20/2015
ms.assetid: abbca162-d95e-43af-b92c-e46e6aa2540e
ms.openlocfilehash: 45e3a4f341ca8eb06ff0f553e0f933956e6c6546
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "70205412"
---
# <a name="chaining-queries-example-c"></a><span data-ttu-id="8e35e-102">Пример связывания запросов (C#)</span><span class="sxs-lookup"><span data-stu-id="8e35e-102">Chaining Queries Example (C#)</span></span>
<span data-ttu-id="8e35e-103">Этот пример основан на предыдущем примере и показывает, что происходит при соединении в цепочку двух запросов, использующих отложенное выполнение и отложенное вычисление.</span><span class="sxs-lookup"><span data-stu-id="8e35e-103">This example builds on the previous example and shows what happens when you chain together two queries that both use deferred execution and lazy evaluation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e35e-104">Пример</span><span class="sxs-lookup"><span data-stu-id="8e35e-104">Example</span></span>  
 <span data-ttu-id="8e35e-105">В этом примере представлен другой метод расширения, `AppendString`, который добавляет указанную строку в каждую строку исходной коллекции, а затем выдает новые строки.</span><span class="sxs-lookup"><span data-stu-id="8e35e-105">In this example, another extension method is introduced, `AppendString`, which appends a specified string onto every string in the source collection, and then yields the new strings.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source >{0}<", str);  
            yield return str.ToUpper();  
        }  
    }  
  
    public static IEnumerable<string>  
      AppendString(this IEnumerable<string> source, string stringToAppend)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("AppendString: source >{0}<", str);  
            yield return str + stringToAppend;  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        IEnumerable<string> q1 =  
            from s in stringArray.ConvertCollectionToUpperCase()  
            select s;  
  
        IEnumerable<string> q2 =  
            from s in q1.AppendString("!!!")  
            select s;  
  
        foreach (string str in q2)  
        {  
            Console.WriteLine("Main: str >{0}<", str);  
            Console.WriteLine();  
        }  
    }  
}  
```  
  
 <span data-ttu-id="8e35e-106">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="8e35e-106">This example produces the following output:</span></span>  
  
```output  
ToUpper: source >abc<  
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 <span data-ttu-id="8e35e-107">В этом примере видно, что каждый метод расширения работает поочередно с каждым элементом исходной коллекции.</span><span class="sxs-lookup"><span data-stu-id="8e35e-107">In this example, you can see that each extension method operates one at a time for each item in the source collection.</span></span>  
  
 <span data-ttu-id="8e35e-108">Этот пример показывает, что даже при соединении в цепочку двух запросов, формирующих коллекции, промежуточные коллекции не материализуются.</span><span class="sxs-lookup"><span data-stu-id="8e35e-108">What should be clear from this example is that even though we have chained together queries that yield collections, no intermediate collections are materialized.</span></span> <span data-ttu-id="8e35e-109">Вместо этого каждый элемент передается от одного отложенного метода к другому.</span><span class="sxs-lookup"><span data-stu-id="8e35e-109">Instead, each item is passed from one lazy method to the next.</span></span> <span data-ttu-id="8e35e-110">Это приводит к использованию намного меньшего объема памяти, чем при подходе, который сначала принимает один массив строк, затем создает второй массив строк, преобразованных в символы верхнего регистра, и наконец создает третий массив строк, где каждая строка имеет добавленные к ней восклицательные знаки.</span><span class="sxs-lookup"><span data-stu-id="8e35e-110">This results in a much smaller memory footprint than an approach that would first take one array of strings, then create a second array of strings that have been converted to uppercase, and finally create a third array of strings where each string has the exclamation points appended to it.</span></span>  
  
 <span data-ttu-id="8e35e-111">Следующий раздел учебника иллюстрирует промежуточную материализацию:</span><span class="sxs-lookup"><span data-stu-id="8e35e-111">The next topic in this tutorial illustrates intermediate materialization:</span></span>  
  
- [<span data-ttu-id="8e35e-112">Промежуточная материализация (C#)</span><span class="sxs-lookup"><span data-stu-id="8e35e-112">Intermediate Materialization (C#)</span></span>](./intermediate-materialization.md)  
  
## <a name="see-also"></a><span data-ttu-id="8e35e-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8e35e-113">See also</span></span>

- [<span data-ttu-id="8e35e-114">Учебник. Объединение запросов в цепочки (C#)</span><span class="sxs-lookup"><span data-stu-id="8e35e-114">Tutorial: Chaining Queries Together (C#)</span></span>](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
