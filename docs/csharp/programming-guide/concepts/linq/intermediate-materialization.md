---
title: Промежуточная материализация (C#)
ms.date: 07/20/2015
ms.assetid: 7922d38f-5044-41cf-8e17-7173d6553a5e
ms.openlocfilehash: af1eb7df7da02d8e72fc102cda4ee5f329dc7974
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70253161"
---
# <a name="intermediate-materialization-c"></a><span data-ttu-id="35ec7-102">Промежуточная материализация (C#)</span><span class="sxs-lookup"><span data-stu-id="35ec7-102">Intermediate Materialization (C#)</span></span>
<span data-ttu-id="35ec7-103">Если не соблюдать осторожность, то в некоторых ситуациях может происходить преждевременная материализация коллекций в запросах, что приводит к радикальному изменению характера использования памяти и снижению производительности приложения.</span><span class="sxs-lookup"><span data-stu-id="35ec7-103">If you are not careful, in some situations you can drastically alter the memory and performance profile of your application by causing premature materialization of collections in your queries.</span></span> <span data-ttu-id="35ec7-104">Некоторые стандартные операторы запросов материализуют свою исходную коллекцию еще до получения хотя бы одного элемента.</span><span class="sxs-lookup"><span data-stu-id="35ec7-104">Some standard query operators cause materialization of their source collection before yielding a single element.</span></span> <span data-ttu-id="35ec7-105">Например, при выполнении оператора <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType> вначале происходит итерация по всей исходной коллекции, затем сортировка всех элементов и лишь после этого осуществляется возврат первого элемента.</span><span class="sxs-lookup"><span data-stu-id="35ec7-105">For example, <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType> first iterates through its entire source collection, then sorts all items, and then finally yields the first item.</span></span> <span data-ttu-id="35ec7-106">Это означает, что самой дорогостоящей операцией является получение первого элемента упорядоченной коллекции, после чего затраты ресурсов на каждый последующий элемент становятся меньше.</span><span class="sxs-lookup"><span data-stu-id="35ec7-106">This means that it is expensive to get the first item of an ordered collection; each item thereafter is not expensive.</span></span> <span data-ttu-id="35ec7-107">Это имеет смысл: сделать иначе оператор запроса не мог бы.</span><span class="sxs-lookup"><span data-stu-id="35ec7-107">This makes sense: It would be impossible for that query operator to do otherwise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35ec7-108">Пример</span><span class="sxs-lookup"><span data-stu-id="35ec7-108">Example</span></span>  
 <span data-ttu-id="35ec7-109">В этом примере внесены изменения по сравнению с предыдущим примером.</span><span class="sxs-lookup"><span data-stu-id="35ec7-109">This example alters the previous example.</span></span> <span data-ttu-id="35ec7-110">В методе `AppendString` осуществляется вызов <xref:System.Linq.Enumerable.ToList%2A> до начала итераций по данным источника.</span><span class="sxs-lookup"><span data-stu-id="35ec7-110">The `AppendString` method calls <xref:System.Linq.Enumerable.ToList%2A> before iterating through the source.</span></span> <span data-ttu-id="35ec7-111">Это становится причиной материализации.</span><span class="sxs-lookup"><span data-stu-id="35ec7-111">This causes materialization.</span></span>  
  
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
        // the following statement materializes the source collection in a List<T>  
        // before iterating through it  
        foreach (string str in source.ToList())  
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
  
 <span data-ttu-id="35ec7-112">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="35ec7-112">This example produces the following output:</span></span>  
  
```output  
ToUpper: source >abc<  
ToUpper: source >def<  
ToUpper: source >ghi<  
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 <span data-ttu-id="35ec7-113">В этом примере можно видеть, что применение вызова <xref:System.Linq.Enumerable.ToList%2A> вынуждает метод `AppendString` сформировать перечисление по всему источнику, прежде чем возвратить первый элемент.</span><span class="sxs-lookup"><span data-stu-id="35ec7-113">In this example, you can see that the call to <xref:System.Linq.Enumerable.ToList%2A> causes `AppendString` to enumerate its entire source before yielding the first item.</span></span> <span data-ttu-id="35ec7-114">Если источник представляет собой большой массив, то в результате характер использования памяти приложением существенно изменится.</span><span class="sxs-lookup"><span data-stu-id="35ec7-114">If the source were a large array, this would significantly alter the memory profile of the application.</span></span>  
  
 <span data-ttu-id="35ec7-115">Стандартные операторы запроса можно также соединять в виде цепочки.</span><span class="sxs-lookup"><span data-stu-id="35ec7-115">Standard query operators can also be chained together.</span></span> <span data-ttu-id="35ec7-116">Это показано в последнем разделе учебника.</span><span class="sxs-lookup"><span data-stu-id="35ec7-116">The final topic in this tutorial illustrates this.</span></span>  
  
- [<span data-ttu-id="35ec7-117">Связывание стандартных операторов запросов (C#)</span><span class="sxs-lookup"><span data-stu-id="35ec7-117">Chaining Standard Query Operators Together (C#)</span></span>](./chaining-standard-query-operators-together.md)  
  
## <a name="see-also"></a><span data-ttu-id="35ec7-118">См. также</span><span class="sxs-lookup"><span data-stu-id="35ec7-118">See also</span></span>

- [<span data-ttu-id="35ec7-119">Учебник. Объединение запросов в цепочки (C#)</span><span class="sxs-lookup"><span data-stu-id="35ec7-119">Tutorial: Chaining Queries Together (C#)</span></span>](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
