---
title: Написание запроса для поиска элементов на основе контекста (C#)
ms.date: 07/20/2015
ms.assetid: 3ff79ef0-fc8b-42fe-8cc0-10dc32b06b4e
ms.openlocfilehash: 3fc131fdeb8dbf8871bfa455bc54eab0eeca7022
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348368"
---
# <a name="how-to-write-a-query-that-finds-elements-based-on-context-c"></a><span data-ttu-id="5d9b9-102">Написание запроса для поиска элементов на основе контекста (C#)</span><span class="sxs-lookup"><span data-stu-id="5d9b9-102">How to write a query that finds elements based on context (C#)</span></span>
<span data-ttu-id="5d9b9-103">Иногда требуется написать запрос, который выбирает элементы, исходя из их контекста.</span><span class="sxs-lookup"><span data-stu-id="5d9b9-103">Sometimes you might have to write a query that selects elements based on their context.</span></span> <span data-ttu-id="5d9b9-104">Может потребоваться использовать фильтрацию с учетом предыдущих или следующих одноуровневых элементов.</span><span class="sxs-lookup"><span data-stu-id="5d9b9-104">You might want to filter based on preceding or following sibling elements.</span></span> <span data-ttu-id="5d9b9-105">Может потребоваться использовать фильтрацию с учетом дочерних или родительских элементов.</span><span class="sxs-lookup"><span data-stu-id="5d9b9-105">You might want to filter based on child or ancestor elements.</span></span>  
  
 <span data-ttu-id="5d9b9-106">Это можно сделать, написав запрос и используя результаты запроса в предложении `where`.</span><span class="sxs-lookup"><span data-stu-id="5d9b9-106">You can do this by writing a query and using the results of the query in the `where` clause.</span></span> <span data-ttu-id="5d9b9-107">Если требуется сначала провести проверку на наличие значения null, а затем проверить само значение, более удобным будет выполнить запрос в предложении `let`, а затем использовать результаты в предложении `where`.</span><span class="sxs-lookup"><span data-stu-id="5d9b9-107">If you have to first test against null, and then test the value, it is more convenient to do the query in a `let` clause, and then use the results in the `where` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d9b9-108">Пример</span><span class="sxs-lookup"><span data-stu-id="5d9b9-108">Example</span></span>  
 <span data-ttu-id="5d9b9-109">В следующем примере выбираются все элементы `p`, сразу за которыми следует элемент `ul`.</span><span class="sxs-lookup"><span data-stu-id="5d9b9-109">The following example selects all `p` elements that are immediately followed by a `ul` element.</span></span>  
  
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
  
 <span data-ttu-id="5d9b9-110">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="5d9b9-110">This code produces the following output:</span></span>  
  
```output  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="example"></a><span data-ttu-id="5d9b9-111">Пример</span><span class="sxs-lookup"><span data-stu-id="5d9b9-111">Example</span></span>  
 <span data-ttu-id="5d9b9-112">Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="5d9b9-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="5d9b9-113">Дополнительные сведения см. в статье [Обзор пространств имен DFS (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="5d9b9-113">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="5d9b9-114">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="5d9b9-114">This code produces the following output:</span></span>  
  
```output  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="see-also"></a><span data-ttu-id="5d9b9-115">См. также</span><span class="sxs-lookup"><span data-stu-id="5d9b9-115">See also</span></span>

- <xref:System.Xml.Linq.XElement.Parse%2A>
- <xref:System.Xml.Linq.XContainer.Descendants%2A>
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>
- <xref:System.Linq.Enumerable.FirstOrDefault%2A>
