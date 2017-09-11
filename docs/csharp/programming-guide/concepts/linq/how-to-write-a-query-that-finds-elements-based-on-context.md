---
title: "Практическое руководство. Написание запроса, ищущего элементы на основании контекста (C#)"
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
ms.assetid: 3ff79ef0-fc8b-42fe-8cc0-10dc32b06b4e
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3c0592dee4da6d8b8b18ad4c3dc349398bd87a77
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-a-query-that-finds-elements-based-on-context-c"></a><span data-ttu-id="0496e-102">Практическое руководство. Написание запроса, ищущего элементы на основании контекста (C#)</span><span class="sxs-lookup"><span data-stu-id="0496e-102">How to: Write a Query that Finds Elements Based on Context (C#)</span></span>
<span data-ttu-id="0496e-103">Иногда требуется написать запрос, который выбирает элементы, исходя из их контекста.</span><span class="sxs-lookup"><span data-stu-id="0496e-103">Sometimes you might have to write a query that selects elements based on their context.</span></span> <span data-ttu-id="0496e-104">Может потребоваться использовать фильтрацию с учетом предыдущих или следующих одноуровневых элементов.</span><span class="sxs-lookup"><span data-stu-id="0496e-104">You might want to filter based on preceding or following sibling elements.</span></span> <span data-ttu-id="0496e-105">Может потребоваться использовать фильтрацию с учетом дочерних или родительских элементов.</span><span class="sxs-lookup"><span data-stu-id="0496e-105">You might want to filter based on child or ancestor elements.</span></span>  
  
 <span data-ttu-id="0496e-106">Это можно сделать, написав запрос и используя результаты запроса в предложении `where`.</span><span class="sxs-lookup"><span data-stu-id="0496e-106">You can do this by writing a query and using the results of the query in the `where` clause.</span></span> <span data-ttu-id="0496e-107">Если требуется сначала провести проверку на наличие значения null, а затем проверить само значение, более удобным будет выполнить запрос в предложении `let`, а затем использовать результаты в предложении `where`.</span><span class="sxs-lookup"><span data-stu-id="0496e-107">If you have to first test against null, and then test the value, it is more convenient to do the query in a `let` clause, and then use the results in the `where` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0496e-108">Пример</span><span class="sxs-lookup"><span data-stu-id="0496e-108">Example</span></span>  
 <span data-ttu-id="0496e-109">В следующем примере выбираются все элементы `p`, сразу за которыми следует элемент `ul`.</span><span class="sxs-lookup"><span data-stu-id="0496e-109">The following example selects all `p` elements that are immediately followed by a `ul` element.</span></span>  
  
```csharp  
XElement doc = XElement.Parse(@"<Root>  
    <p id=""1""/>  
    <ul>abc</ul>  
    <Child>  
        <p id=""2""/>  
        <notul/>  
        <p id=""3""/>  
        <ul>def</ul>  
        <p id=""4""/>  
    </Child>  
    <Child>  
        <p id=""5""/>  
        <notul/>  
        <p id=""6""/>  
        <ul>abc</ul>  
        <p id=""7""/>  
    </Child>  
</Root>");  
  
IEnumerable<XElement> items =  
    from e in doc.Descendants("p")  
    let z = e.ElementsAfterSelf().FirstOrDefault()  
    where z != null && z.Name.LocalName == "ul"  
    select e;  
  
foreach (XElement e in items)  
    Console.WriteLine("id = {0}", (string)e.Attribute("id"));  
```  
  
 <span data-ttu-id="0496e-110">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="0496e-110">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="example"></a><span data-ttu-id="0496e-111">Пример</span><span class="sxs-lookup"><span data-stu-id="0496e-111">Example</span></span>  
 <span data-ttu-id="0496e-112">Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="0496e-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="0496e-113">Дополнительные сведения см. в разделе [Работа с пространствами имен XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="0496e-113">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```csharp  
XElement doc = XElement.Parse(@"<Root xmlns='http://www.adatum.com'>  
    <p id=""1""/>  
    <ul>abc</ul>  
    <Child>  
        <p id=""2""/>  
        <notul/>  
        <p id=""3""/>  
        <ul>def</ul>  
        <p id=""4""/>  
    </Child>  
    <Child>  
        <p id=""5""/>  
        <notul/>  
        <p id=""6""/>  
        <ul>abc</ul>  
        <p id=""7""/>  
    </Child>  
</Root>");  
  
XNamespace ad = "http://www.adatum.com";  
  
IEnumerable<XElement> items =  
    from e in doc.Descendants(ad + "p")  
    let z = e.ElementsAfterSelf().FirstOrDefault()  
    where z != null && z.Name == ad.GetName("ul")  
    select e;  
  
foreach (XElement e in items)  
    Console.WriteLine("id = {0}", (string)e.Attribute("id"));  
```  
  
 <span data-ttu-id="0496e-114">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="0496e-114">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="see-also"></a><span data-ttu-id="0496e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0496e-115">See Also</span></span>  
 <span data-ttu-id="0496e-116"><xref:System.Xml.Linq.XElement.Parse%2A></span><span class="sxs-lookup"><span data-stu-id="0496e-116"><xref:System.Xml.Linq.XElement.Parse%2A></span></span>   
 <span data-ttu-id="0496e-117"><xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="0496e-117"><xref:System.Xml.Linq.XContainer.Descendants%2A></span></span>   
 <span data-ttu-id="0496e-118"><xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A></span><span class="sxs-lookup"><span data-stu-id="0496e-118"><xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A></span></span>   
 <span data-ttu-id="0496e-119"><xref:System.Linq.Enumerable.FirstOrDefault%2A></span><span class="sxs-lookup"><span data-stu-id="0496e-119"><xref:System.Linq.Enumerable.FirstOrDefault%2A></span></span>   
 [<span data-ttu-id="0496e-120">Базовые запросы (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="0496e-120">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)

