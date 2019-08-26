---
title: Практическое руководство. Фильтрация по именам элементов (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 1849fb03-f075-421f-863c-e8fb32773cdf
ms.openlocfilehash: 9febe3b834261326bab3e82d87c476f99d4e6b1f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69593804"
---
# <a name="how-to-filter-on-element-names-linq-to-xml-c"></a><span data-ttu-id="3bd21-102">Практическое руководство. Фильтрация по именам элементов (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="3bd21-102">How to: Filter on Element Names (LINQ to XML) (C#)</span></span>
<span data-ttu-id="3bd21-103">При вызове одного из методов, возвращающих коллекцию <xref:System.Collections.Generic.IEnumerable%601> элементов <xref:System.Xml.Linq.XElement>, можно осуществить фильтрацию по именам элементов.</span><span class="sxs-lookup"><span data-stu-id="3bd21-103">When you call one of the methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, you can filter on the element name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bd21-104">Пример</span><span class="sxs-lookup"><span data-stu-id="3bd21-104">Example</span></span>  
 <span data-ttu-id="3bd21-105">В этом примере показано получение отфильтрованной коллекции потомков, в которой содержатся только потомки с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="3bd21-105">This example retrieves a collection of descendants that is filtered to contain only descendants with the specified name.</span></span>  
  
 <span data-ttu-id="3bd21-106">В этом примере используется следующий XML-документ: [Пример XML-файла. Типичный заказ на покупку (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="3bd21-106">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> items =  
    from el in po.Descendants("ProductName")  
    select el;  
foreach(XElement prdName in items)  
    Console.WriteLine(prdName.Name + ":" + (string) prdName);  
```  
  
 <span data-ttu-id="3bd21-107">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="3bd21-107">This code produces the following output:</span></span>  
  
```  
ProductName:Lawnmower  
ProductName:Baby Monitor  
```  
  
 <span data-ttu-id="3bd21-108">В других методах, возвращающих коллекции <xref:System.Collections.Generic.IEnumerable%601> элементов <xref:System.Xml.Linq.XElement>, заложен тот же принцип.</span><span class="sxs-lookup"><span data-stu-id="3bd21-108">The other methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> collections follow the same pattern.</span></span> <span data-ttu-id="3bd21-109">Их сигнатуры подобны <xref:System.Xml.Linq.XContainer.Elements%2A> и <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span><span class="sxs-lookup"><span data-stu-id="3bd21-109">Their signatures are similar to <xref:System.Xml.Linq.XContainer.Elements%2A> and <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span></span> <span data-ttu-id="3bd21-110">Ниже следует полный список методов, имеющих аналогичные сигнатурам методов:</span><span class="sxs-lookup"><span data-stu-id="3bd21-110">The following is the complete list of methods that have similar method signatures:</span></span>  
  
- <xref:System.Xml.Linq.XNode.Ancestors%2A>  
  
- <xref:System.Xml.Linq.XContainer.Descendants%2A>  
  
- <xref:System.Xml.Linq.XContainer.Elements%2A>  
  
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>  
  
- <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>  
  
- <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>  
  
- <xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A>  
  
## <a name="example"></a><span data-ttu-id="3bd21-111">Пример</span><span class="sxs-lookup"><span data-stu-id="3bd21-111">Example</span></span>  
 <span data-ttu-id="3bd21-112">Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="3bd21-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="3bd21-113">Дополнительные сведения см. в статье [Обзор пространств имен DFS (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="3bd21-113">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="3bd21-114">В этом примере используется следующий XML-документ: [Пример XML-файла. Типичный заказ на покупку в пространстве имен](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="3bd21-114">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement po = XElement.Load("PurchaseOrderInNamespace.xml");  
IEnumerable<XElement> items =  
    from el in po.Descendants(aw + "ProductName")  
    select el;  
foreach (XElement prdName in items)  
    Console.WriteLine(prdName.Name + ":" + (string)prdName);  
```  
  
 <span data-ttu-id="3bd21-115">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="3bd21-115">This code produces the following output:</span></span>  
  
```  
{http://www.adventure-works.com}ProductName:Lawnmower  
{http://www.adventure-works.com}ProductName:Baby Monitor  
```  
  
## <a name="see-also"></a><span data-ttu-id="3bd21-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3bd21-116">See also</span></span>

- [<span data-ttu-id="3bd21-117">Оси LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="3bd21-117">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
