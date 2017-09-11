---
title: "Пример связывания запросов (C#)"
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
ms.assetid: abbca162-d95e-43af-b92c-e46e6aa2540e
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 70179c93c48f56614bd7c8b648f73e86ebe26ff4
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="chaining-queries-example-c"></a><span data-ttu-id="8b59a-102">Пример связывания запросов (C#)</span><span class="sxs-lookup"><span data-stu-id="8b59a-102">Chaining Queries Example (C#)</span></span>
<span data-ttu-id="8b59a-103">Этот пример основан на предыдущем примере и показывает, что происходит при соединении в цепочку двух запросов, использующих отложенное выполнение и отложенное вычисление.</span><span class="sxs-lookup"><span data-stu-id="8b59a-103">This example builds on the previous example and shows what happens when you chain together two queries that both use deferred execution and lazy evaluation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b59a-104">Пример</span><span class="sxs-lookup"><span data-stu-id="8b59a-104">Example</span></span>  
 <span data-ttu-id="8b59a-105">В этом примере представлен другой метод расширения, `AppendString`, который добавляет указанную строку в каждую строку исходной коллекции, а затем выдает новые строки.</span><span class="sxs-lookup"><span data-stu-id="8b59a-105">In this example, another extension method is introduced, `AppendString`, which appends a specified string onto every string in the source collection, and then yields the new strings.</span></span>  
  
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
  
 <span data-ttu-id="8b59a-106">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="8b59a-106">This example produces the following output:</span></span>  
  
```  
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
  
 <span data-ttu-id="8b59a-107">В этом примере видно, что каждый метод расширения работает поочередно с каждым элементом исходной коллекции.</span><span class="sxs-lookup"><span data-stu-id="8b59a-107">In this example, you can see that each extension method operates one at a time for each item in the source collection.</span></span>  
  
 <span data-ttu-id="8b59a-108">Этот пример показывает, что даже при соединении в цепочку двух запросов, формирующих коллекции, промежуточные коллекции не материализуются.</span><span class="sxs-lookup"><span data-stu-id="8b59a-108">What should be clear from this example is that even though we have chained together queries that yield collections, no intermediate collections are materialized.</span></span> <span data-ttu-id="8b59a-109">Вместо этого каждый элемент передается от одного отложенного метода к другому.</span><span class="sxs-lookup"><span data-stu-id="8b59a-109">Instead, each item is passed from one lazy method to the next.</span></span> <span data-ttu-id="8b59a-110">Это приводит к использованию намного меньшего объема памяти, чем при подходе, который сначала принимает один массив строк, затем создает второй массив строк, преобразованных в символы верхнего регистра, и наконец создает третий массив строк, где каждая строка имеет добавленные к ней восклицательные знаки.</span><span class="sxs-lookup"><span data-stu-id="8b59a-110">This results in a much smaller memory footprint than an approach that would first take one array of strings, then create a second array of strings that have been converted to uppercase, and finally create a third array of strings where each string has the exclamation points appended to it.</span></span>  
  
 <span data-ttu-id="8b59a-111">Следующий раздел учебника иллюстрирует промежуточную материализацию:</span><span class="sxs-lookup"><span data-stu-id="8b59a-111">The next topic in this tutorial illustrates intermediate materialization:</span></span>  
  
-   [<span data-ttu-id="8b59a-112">Промежуточная материализация (C#)</span><span class="sxs-lookup"><span data-stu-id="8b59a-112">Intermediate Materialization (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/intermediate-materialization.md)  
  
## <a name="see-also"></a><span data-ttu-id="8b59a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="8b59a-113">See Also</span></span>  
 [<span data-ttu-id="8b59a-114">Учебник. Объединение запросов в цепочки (C#)</span><span class="sxs-lookup"><span data-stu-id="8b59a-114">Tutorial: Chaining Queries Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)

