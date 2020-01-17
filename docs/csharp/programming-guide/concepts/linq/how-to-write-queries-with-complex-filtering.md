---
title: Создание запросов со сложной фильтрацией (C#)
ms.date: 07/20/2015
ms.assetid: 4065d901-cf89-4e47-8bf9-abb65acfb003
ms.openlocfilehash: a4918631fed21967b402c5c56cfb8a211d44c139
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337359"
---
# <a name="how-to-write-queries-with-complex-filtering-c"></a><span data-ttu-id="f3e7a-102">Создание запросов со сложной фильтрацией (C#)</span><span class="sxs-lookup"><span data-stu-id="f3e7a-102">How to write queries with complex filtering (C#)</span></span>
<span data-ttu-id="f3e7a-103">Иногда возникает необходимость в написании запросов LINQ to XML с комплексной фильтрацией.</span><span class="sxs-lookup"><span data-stu-id="f3e7a-103">Sometimes you want to write LINQ to XML queries with complex filters.</span></span> <span data-ttu-id="f3e7a-104">Например, может потребоваться найти все элементы, имеющие дочерние элементы с определенным именем и значением.</span><span class="sxs-lookup"><span data-stu-id="f3e7a-104">For example, you might have to find all elements that have a child element with a particular name and value.</span></span> <span data-ttu-id="f3e7a-105">В этом разделе приводится пример написания запроса с комплексной фильтрацией.</span><span class="sxs-lookup"><span data-stu-id="f3e7a-105">This topic gives an example of writing a query with complex filtering.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3e7a-106">Пример</span><span class="sxs-lookup"><span data-stu-id="f3e7a-106">Example</span></span>  
 <span data-ttu-id="f3e7a-107">В этом примере показано, как найти все элементы `PurchaseOrder`, имеющие дочерний элемент `Address` с атрибутом `Type`, равным «Доставка», и дочерним элементом `State`, равным «NY».</span><span class="sxs-lookup"><span data-stu-id="f3e7a-107">This example shows how to find all `PurchaseOrder` elements that have a child `Address` element that has a `Type` attribute equal to "Shipping" and a child `State` element equal to "NY".</span></span> <span data-ttu-id="f3e7a-108">В нем используется вложенный запрос в предложении `Where`, а оператор `Any` возвращает значение `true`, если коллекция содержит элементы.</span><span class="sxs-lookup"><span data-stu-id="f3e7a-108">It uses a nested query in the `Where` clause, and the `Any` operator returns `true` if the collection has any elements in it.</span></span> <span data-ttu-id="f3e7a-109">Сведения об использовании синтаксиса запросов на основе методов см. в разделе [Синтаксис запросов и синтаксис методов в LINQ](./query-syntax-and-method-syntax-in-linq.md).</span><span class="sxs-lookup"><span data-stu-id="f3e7a-109">For information about using method-based query syntax, see [Query Syntax and Method Syntax in LINQ](./query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
 <span data-ttu-id="f3e7a-110">В этом примере используется следующий XML-документ: [Пример XML-файла. Несколько заказов на покупку (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f3e7a-110">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="f3e7a-111">Дополнительные сведения об операторе `Any` см. в разделе [Операции, использующие квантификаторы (C#)](./quantifier-operations.md).</span><span class="sxs-lookup"><span data-stu-id="f3e7a-111">For more information about the `Any` operator, see [Quantifier Operations (C#)](./quantifier-operations.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrders.xml");  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements("PurchaseOrder")  
    where   
        (from add in el.Elements("Address")  
        where  
            (string)add.Attribute("Type") == "Shipping" &&  
            (string)add.Element("State") == "NY"  
        select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute("PurchaseOrderNumber"));  
```  
  
 <span data-ttu-id="f3e7a-112">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="f3e7a-112">This code produces the following output:</span></span>  
  
```output  
99505  
```  
  
## <a name="example"></a><span data-ttu-id="f3e7a-113">Пример</span><span class="sxs-lookup"><span data-stu-id="f3e7a-113">Example</span></span>  
 <span data-ttu-id="f3e7a-114">Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="f3e7a-114">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="f3e7a-115">Дополнительные сведения см. в статье [Обзор пространств имен DFS (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f3e7a-115">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="f3e7a-116">В этом примере используется следующий XML-документ: [Пример XML-файла. Несколько заказов на покупку в пространстве имен](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="f3e7a-116">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrdersInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements(aw + "PurchaseOrder")  
    where  
        (from add in el.Elements(aw + "Address")  
         where  
             (string)add.Attribute(aw + "Type") == "Shipping" &&  
             (string)add.Element(aw + "State") == "NY"  
         select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute(aw + "PurchaseOrderNumber"));  
```  
  
 <span data-ttu-id="f3e7a-117">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="f3e7a-117">This code produces the following output:</span></span>  
  
```output  
99505  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3e7a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f3e7a-118">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="f3e7a-119">Операции проекции (C#)</span><span class="sxs-lookup"><span data-stu-id="f3e7a-119">Projection Operations (C#)</span></span>](./projection-operations.md)
- [<span data-ttu-id="f3e7a-120">Операции, использующие квантификаторы (C#)</span><span class="sxs-lookup"><span data-stu-id="f3e7a-120">Quantifier Operations (C#)</span></span>](./quantifier-operations.md)
