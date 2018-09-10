---
title: Связывание стандартных операторов запросов (C#)
ms.date: 07/20/2015
ms.assetid: 66f2b0a9-2c23-4735-988e-bbc9dfb55c7b
ms.openlocfilehash: 07cc6769646f8f3f924b488e30ce2415c587ebe0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43520872"
---
# <a name="chaining-standard-query-operators-together-c"></a><span data-ttu-id="33959-102">Связывание стандартных операторов запросов (C#)</span><span class="sxs-lookup"><span data-stu-id="33959-102">Chaining Standard Query Operators Together (C#)</span></span>
<span data-ttu-id="33959-103">Это последний раздел учебника [Объединение запросов в цепочки (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md).</span><span class="sxs-lookup"><span data-stu-id="33959-103">This is the final topic in the [Tutorial: Chaining Queries Together (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md) tutorial.</span></span>  
  
 <span data-ttu-id="33959-104">Стандартные операторы запросов также можно объединять в цепочки.</span><span class="sxs-lookup"><span data-stu-id="33959-104">The standard query operators can also be chained together.</span></span> <span data-ttu-id="33959-105">Например, можно вставить оператор <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType>, который также будет действовать как отложенный.</span><span class="sxs-lookup"><span data-stu-id="33959-105">For example, you can interject the <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> operator, and it also operates in a lazy fashion.</span></span> <span data-ttu-id="33959-106">Этот оператор не материализует промежуточные результаты.</span><span class="sxs-lookup"><span data-stu-id="33959-106">No intermediate results are materialized by it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33959-107">Пример</span><span class="sxs-lookup"><span data-stu-id="33959-107">Example</span></span>  
 <span data-ttu-id="33959-108">В данном примере метод <xref:System.Linq.Enumerable.Where%2A> вызывается до вызова метода `ConvertCollectionToUpperCase`.</span><span class="sxs-lookup"><span data-stu-id="33959-108">In this example, the <xref:System.Linq.Enumerable.Where%2A> method is called before calling `ConvertCollectionToUpperCase`.</span></span> <span data-ttu-id="33959-109">Метод <xref:System.Linq.Enumerable.Where%2A> действует практически так же, как отложенные методы, использовавшиеся в предыдущих примерах, приведенных в этом учебнике, `ConvertCollectionToUpperCase` и `AppendString`.</span><span class="sxs-lookup"><span data-stu-id="33959-109">The <xref:System.Linq.Enumerable.Where%2A> method operates in almost exactly the same way as the lazy methods used in previous examples in this tutorial, `ConvertCollectionToUpperCase` and `AppendString`.</span></span>  
  
 <span data-ttu-id="33959-110">Отличие заключается в том, что в этом случае метод <xref:System.Linq.Enumerable.Where%2A> просматривает свою исходную коллекцию, определяет, что первый элемент не передает предикат, а затем переходит к следующему элементу, который предикат передает.</span><span class="sxs-lookup"><span data-stu-id="33959-110">One difference is that in this case, the <xref:System.Linq.Enumerable.Where%2A> method iterates through its source collection, determines that the first item does not pass the predicate, and then gets the next item, which does pass.</span></span> <span data-ttu-id="33959-111">После этого метод выдает второй элемент.</span><span class="sxs-lookup"><span data-stu-id="33959-111">It then yields the second item.</span></span>  
  
 <span data-ttu-id="33959-112">Однако базовый принцип остался прежним: промежуточные коллекции материализуются только в случае необходимости.</span><span class="sxs-lookup"><span data-stu-id="33959-112">However, the basic idea is the same: Intermediate collections are not materialized unless they have to be.</span></span>  
  
 <span data-ttu-id="33959-113">При использовании выражений запросов они преобразуются в вызовы стандартных операторов запросов, а затем применяется тот же принцип.</span><span class="sxs-lookup"><span data-stu-id="33959-113">When query expressions are used, they are converted to calls to the standard query operators, and the same principles apply.</span></span>  
  
 <span data-ttu-id="33959-114">Во всех примерах, приведенных в этом разделе, в которых запрашиваются документы Office Open XML, используется один и тот же принцип.</span><span class="sxs-lookup"><span data-stu-id="33959-114">All of the examples in this section that are querying Office Open XML documents use the same principle.</span></span> <span data-ttu-id="33959-115">Отложенное выполнение и отложенное вычисление - это основополагающие принципы, которые необходимо понимать, чтобы эффективно использовать LINQ (и LINQ to XML).</span><span class="sxs-lookup"><span data-stu-id="33959-115">Deferred execution and lazy evaluation are some of the fundamental concepts that you must understand  to use LINQ (and LINQ to XML) effectively.</span></span>  
  
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
            where s.CompareTo("D") >= 0  
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
  
 <span data-ttu-id="33959-116">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="33959-116">This example produces the following output:</span></span>  
  
```  
ToUpper: source >abc<  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
## <a name="see-also"></a><span data-ttu-id="33959-117">См. также</span><span class="sxs-lookup"><span data-stu-id="33959-117">See Also</span></span>

- [<span data-ttu-id="33959-118">Учебник. Объединение запросов в цепочки (C#)</span><span class="sxs-lookup"><span data-stu-id="33959-118">Tutorial: Chaining Queries Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)
