---
title: Практическое руководство. Создание запросов со сложной фильтрацией (C#)
ms.date: 07/20/2015
ms.assetid: 4065d901-cf89-4e47-8bf9-abb65acfb003
ms.openlocfilehash: 72c34f8ef8bebb3584e00cf040cfcdc35dfc3701
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-write-queries-with-complex-filtering-c"></a><span data-ttu-id="fb94f-102">Практическое руководство. Создание запросов со сложной фильтрацией (C#)</span><span class="sxs-lookup"><span data-stu-id="fb94f-102">How to: Write Queries with Complex Filtering (C#)</span></span>
<span data-ttu-id="fb94f-103">Иногда возникает необходимость в написании запросов LINQ to XML с комплексной фильтрацией.</span><span class="sxs-lookup"><span data-stu-id="fb94f-103">Sometimes you want to write LINQ to XML queries with complex filters.</span></span> <span data-ttu-id="fb94f-104">Например, может потребоваться найти все элементы, имеющие дочерние элементы с определенным именем и значением.</span><span class="sxs-lookup"><span data-stu-id="fb94f-104">For example, you might have to find all elements that have a child element with a particular name and value.</span></span> <span data-ttu-id="fb94f-105">В этом разделе приводится пример написания запроса с комплексной фильтрацией.</span><span class="sxs-lookup"><span data-stu-id="fb94f-105">This topic gives an example of writing a query with complex filtering.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb94f-106">Пример</span><span class="sxs-lookup"><span data-stu-id="fb94f-106">Example</span></span>  
 <span data-ttu-id="fb94f-107">В этом примере показано, как найти все элементы `PurchaseOrder`, имеющие дочерний элемент `Address` с атрибутом `Type`, равным «Доставка», и дочерним элементом `State`, равным «NY».</span><span class="sxs-lookup"><span data-stu-id="fb94f-107">This example shows how to find all `PurchaseOrder` elements that have a child `Address` element that has a `Type` attribute equal to "Shipping" and a child `State` element equal to "NY".</span></span> <span data-ttu-id="fb94f-108">В нем используется вложенный запрос в предложении `Where`, а оператор `Any` возвращает значение `true`, если коллекция содержит элементы.</span><span class="sxs-lookup"><span data-stu-id="fb94f-108">It uses a nested query in the `Where` clause, and the `Any` operator returns `true` if the collection has any elements in it.</span></span> <span data-ttu-id="fb94f-109">Сведения об использовании синтаксиса запросов на основе методов см. в разделе [Синтаксис запросов и синтаксис методов в LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).</span><span class="sxs-lookup"><span data-stu-id="fb94f-109">For information about using method-based query syntax, see [Query Syntax and Method Syntax in LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
 <span data-ttu-id="fb94f-110">В этом примере используется следующий XML-документ: [Пример XML-файла. Несколько заказов на покупку (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="fb94f-110">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="fb94f-111">Дополнительные сведения об операторе `Any` см. в разделе [Операции, использующие квантификаторы (C#)](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md).</span><span class="sxs-lookup"><span data-stu-id="fb94f-111">For more information about the `Any` operator, see [Quantifier Operations (C#)](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md).</span></span>  
  
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
  
 <span data-ttu-id="fb94f-112">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="fb94f-112">This code produces the following output:</span></span>  
  
```  
99505  
```  
  
## <a name="example"></a><span data-ttu-id="fb94f-113">Пример</span><span class="sxs-lookup"><span data-stu-id="fb94f-113">Example</span></span>  
 <span data-ttu-id="fb94f-114">Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="fb94f-114">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="fb94f-115">Дополнительные сведения см. в разделе [Работа с пространствами имен XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="fb94f-115">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="fb94f-116">В этом примере используется следующий XML-документ: [Пример XML-файла. Несколько заказов на покупку в пространстве имен](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="fb94f-116">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="fb94f-117">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="fb94f-117">This code produces the following output:</span></span>  
  
```  
99505  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb94f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="fb94f-118">See Also</span></span>  
 <xref:System.Xml.Linq.XElement.Attribute%2A>  
 <xref:System.Xml.Linq.XContainer.Elements%2A>  
 [<span data-ttu-id="fb94f-119">Базовые запросы (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="fb94f-119">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
 [<span data-ttu-id="fb94f-120">Операции проекции (C#)</span><span class="sxs-lookup"><span data-stu-id="fb94f-120">Projection Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)  
 [<span data-ttu-id="fb94f-121">Операции, использующие квантификаторы (C#)</span><span class="sxs-lookup"><span data-stu-id="fb94f-121">Quantifier Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md)
