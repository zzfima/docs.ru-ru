---
title: Производительность связанных запросов (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: b2f1d715-8946-4dc0-8d56-fb3d1bba54a6
ms.openlocfilehash: 6e0b2ec0b73afe10e21c83499c1a3a52c923f591
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43466934"
---
# <a name="performance-of-chained-queries-linq-to-xml-c"></a><span data-ttu-id="78bb0-102">Производительность связанных запросов (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="78bb0-102">Performance of Chained Queries (LINQ to XML) (C#)</span></span>
<span data-ttu-id="78bb0-103">Одним из наиболее важных преимуществ LINQ (и LINQ to XML) является возможность эффективного выполнения цепочек запросов наряду с одиночными большими и более сложными запросами.</span><span class="sxs-lookup"><span data-stu-id="78bb0-103">One of the most important benefits of LINQ (and LINQ to XML) is that chained queries can perform as well as a single larger, more complicated query.</span></span>  
  
 <span data-ttu-id="78bb0-104">Цепочкой запросов называется запрос, использующий в качестве источника другой запрос.</span><span class="sxs-lookup"><span data-stu-id="78bb0-104">A chained query is a query that uses another query as its source.</span></span> <span data-ttu-id="78bb0-105">Например, в следующем простом коде запрос `query2` в качестве источника включает в себя запрос `query1`.</span><span class="sxs-lookup"><span data-stu-id="78bb0-105">For example, in the following simple code, `query2` has `query1` as its source:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    new XElement("Child", 3),  
    new XElement("Child", 4)  
);  
  
var query1 = from x in root.Elements("Child")  
             where (int)x >= 3  
             select x;  
  
var query2 = from e in query1  
             where (int)e % 2 == 0  
             select e;  
  
foreach (var i in query2)  
    Console.WriteLine("{0}", (int)i);  
```  
  
 <span data-ttu-id="78bb0-106">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="78bb0-106">This example produces the following output:</span></span>  
  
```  
4  
```  
  
 <span data-ttu-id="78bb0-107">Эта цепочка запросов по своим показателям производительности аналогична выполнению итераций по связанному списку.</span><span class="sxs-lookup"><span data-stu-id="78bb0-107">This chained query provides the same performance profile as iterating through a linked list.</span></span>  
  
-   <span data-ttu-id="78bb0-108">Производительность оси <xref:System.Xml.Linq.XContainer.Elements%2A> и выполнения итераций по связанному списку практически одинакова.</span><span class="sxs-lookup"><span data-stu-id="78bb0-108">The <xref:System.Xml.Linq.XContainer.Elements%2A> axis has essentially the same performance as iterating through a linked list.</span></span> <span data-ttu-id="78bb0-109">Ось <xref:System.Xml.Linq.XContainer.Elements%2A> реализована в виде итератора с отложенным выполнением.</span><span class="sxs-lookup"><span data-stu-id="78bb0-109"><xref:System.Xml.Linq.XContainer.Elements%2A> is implemented as an iterator with deferred execution.</span></span> <span data-ttu-id="78bb0-110">Это означает, что помимо итераций по связанному списку выполняется и другая работа, например, выделяется память для объекта итератора и отслеживается состояние выполнения.</span><span class="sxs-lookup"><span data-stu-id="78bb0-110">This means that it does some work in addition to iterating through the linked list, such as allocating the iterator object and keeping track of execution state.</span></span> <span data-ttu-id="78bb0-111">Эта работа делится на две категории: работа, выполняемая при настройке итератора, и работа, выполняемая при каждой итерации.</span><span class="sxs-lookup"><span data-stu-id="78bb0-111">This work can be divided into two categories: the work that is done at the time the iterator is set up, and the work that is done during each iteration.</span></span> <span data-ttu-id="78bb0-112">Настройка требует небольшого фиксированного объема работы, тогда как объем работы, выполняемой при каждой итерации, пропорционален количеству элементов в исходной коллекции.</span><span class="sxs-lookup"><span data-stu-id="78bb0-112">The setup work is a small, fixed amount of work and the work done during each iteration is proportional to the number of items in the source collection.</span></span>  
  
-   <span data-ttu-id="78bb0-113">В запросе `query1` предложение `where` вызывает метод <xref:System.Linq.Enumerable.Where%2A>.</span><span class="sxs-lookup"><span data-stu-id="78bb0-113">In `query1`, the `where` clause causes the query to call the <xref:System.Linq.Enumerable.Where%2A> method.</span></span> <span data-ttu-id="78bb0-114">Этот метод так же реализован в виде итератора.</span><span class="sxs-lookup"><span data-stu-id="78bb0-114">This method is also implemented as an iterator.</span></span> <span data-ttu-id="78bb0-115">Работа по настройке состоит в создании экземпляра выражения-делегата, которое будет ссылаться на лямбда-выражение, и в выполнении обычной настройки итератора.</span><span class="sxs-lookup"><span data-stu-id="78bb0-115">The setup work consists of instantiating the delegate that will reference the lambda expression, plus the normal setup for an iterator.</span></span> <span data-ttu-id="78bb0-116">Выражение-делегат вызывается в каждой итерации для выполнения предиката.</span><span class="sxs-lookup"><span data-stu-id="78bb0-116">With each iteration, the delegate is called to execute the predicate.</span></span> <span data-ttu-id="78bb0-117">Работа по настройке и работа, выполняемая при каждой итерации, аналогична работе, выполняемой при итерациях по оси.</span><span class="sxs-lookup"><span data-stu-id="78bb0-117">The setup work and the work done during each iteration is the similar to the work done while iterating through the axis.</span></span>  
  
-   <span data-ttu-id="78bb0-118">В запросе `query1` предложение select вызывает метод <xref:System.Linq.Enumerable.Select%2A>.</span><span class="sxs-lookup"><span data-stu-id="78bb0-118">In `query1`, the select clause causes the query to call the <xref:System.Linq.Enumerable.Select%2A> method.</span></span> <span data-ttu-id="78bb0-119">Этот метод имеет такие же показатели производительности, что и метод <xref:System.Linq.Enumerable.Where%2A>.</span><span class="sxs-lookup"><span data-stu-id="78bb0-119">This method has the same performance profile as the <xref:System.Linq.Enumerable.Where%2A> method.</span></span>  
  
-   <span data-ttu-id="78bb0-120">В запросе `query2` предложения `where` и `select` имеют такие же показатели производительности, как и в запросе `query1`.</span><span class="sxs-lookup"><span data-stu-id="78bb0-120">In `query2`, both the `where` clause and the `select` clause have the same performance profile as in `query1`.</span></span>  
  
 <span data-ttu-id="78bb0-121">Таким образом, работа итерации по запросу `query2` прямо пропорциональна количеству элементов в источнике первого запроса, то есть имеет линейную зависимость.</span><span class="sxs-lookup"><span data-stu-id="78bb0-121">The iteration through `query2` is therefore directly proportional to the number of items in the source of the first query, in other words, linear time.</span></span> <span data-ttu-id="78bb0-122">Соответствующий пример Visual Basic будет иметь те же показатели производительности.</span><span class="sxs-lookup"><span data-stu-id="78bb0-122">A corresponding Visual Basic example would have the same performance profile.</span></span>  
  
 <span data-ttu-id="78bb0-123">Дополнительные сведения об итерациях см. в разделе [yield](../../../../csharp/language-reference/keywords/yield.md).</span><span class="sxs-lookup"><span data-stu-id="78bb0-123">For more information on iterators, see [yield](../../../../csharp/language-reference/keywords/yield.md).</span></span>  
  
 <span data-ttu-id="78bb0-124">Более подробные сведения об объединении запросов в цепочки см. в разделе [Учебное руководство. Связывание запросов](https://msdn.microsoft.com/library/c08d228a-f07a-4c98-810f-1bf0e8f2257c).</span><span class="sxs-lookup"><span data-stu-id="78bb0-124">For a more detailed tutorial on chaining queries together, see [Tutorial: Chaining Queries Together](https://msdn.microsoft.com/library/c08d228a-f07a-4c98-810f-1bf0e8f2257c).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78bb0-125">См. также</span><span class="sxs-lookup"><span data-stu-id="78bb0-125">See Also</span></span>  
 [<span data-ttu-id="78bb0-126">Производительность (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="78bb0-126">Performance (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/performance-linq-to-xml.md)
