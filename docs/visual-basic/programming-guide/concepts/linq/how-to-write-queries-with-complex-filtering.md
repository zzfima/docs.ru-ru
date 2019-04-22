---
title: Практическое руководство. Создание запросов со сложной фильтрацией (Visual Basic)
ms.date: 07/20/2015
ms.assetid: bf286ffc-7990-4b00-a4eb-ee3d70129950
ms.openlocfilehash: ac58394619b83e2b862e87926f0b6a722fdc3c7e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58820923"
---
# <a name="how-to-write-queries-with-complex-filtering-visual-basic"></a><span data-ttu-id="b67d3-102">Практическое руководство. Создание запросов со сложной фильтрацией (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b67d3-102">How to: Write Queries with Complex Filtering (Visual Basic)</span></span>
<span data-ttu-id="b67d3-103">Иногда возникает необходимость в написании запросов LINQ to XML с комплексной фильтрацией.</span><span class="sxs-lookup"><span data-stu-id="b67d3-103">Sometimes you want to write LINQ to XML queries with complex filters.</span></span> <span data-ttu-id="b67d3-104">Например, может потребоваться найти все элементы, имеющие дочерние элементы с определенным именем и значением.</span><span class="sxs-lookup"><span data-stu-id="b67d3-104">For example, you might have to find all elements that have a child element with a particular name and value.</span></span> <span data-ttu-id="b67d3-105">В этом разделе приводится пример написания запроса с комплексной фильтрацией.</span><span class="sxs-lookup"><span data-stu-id="b67d3-105">This topic gives an example of writing a query with complex filtering.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b67d3-106">Пример</span><span class="sxs-lookup"><span data-stu-id="b67d3-106">Example</span></span>  
 <span data-ttu-id="b67d3-107">В этом примере показано, как найти все элементы `PurchaseOrder`, имеющие дочерний элемент `Address` с атрибутом `Type`, равным «Доставка», и дочерним элементом `State`, равным «NY».</span><span class="sxs-lookup"><span data-stu-id="b67d3-107">This example shows how to find all `PurchaseOrder` elements that have a child `Address` element that has a `Type` attribute equal to "Shipping" and a child `State` element equal to "NY".</span></span> <span data-ttu-id="b67d3-108">В нем используется вложенный запрос в предложении `Where`, а оператор `Any` возвращает значение `True`, если коллекция содержит элементы.</span><span class="sxs-lookup"><span data-stu-id="b67d3-108">It uses a nested query in the `Where` clause, and the `Any` operator returns `True` if the collection has any elements in it.</span></span>  
  
 <span data-ttu-id="b67d3-109">В этом примере используется следующий XML-документ: [Пример XML-файла. Несколько заказов на покупку (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b67d3-109">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="b67d3-110">Дополнительные сведения о `Any` оператора, см. в разделе [операции, использующие квантификаторы (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md).</span><span class="sxs-lookup"><span data-stu-id="b67d3-110">For more information about the `Any` operator, see [Quantifier Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md).</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("PurchaseOrders.xml")  
Dim purchaseOrders As IEnumerable(Of XElement) = _  
    From el In root.<PurchaseOrder> _  
    Where _  
        (From add In el.<Address> _  
        Where _  
             add.@Type = "Shipping" And _  
             add.<State>.Value = "NY" _  
        Select add) _  
    .Any() _  
    Select el  
For Each el As XElement In purchaseOrders  
    Console.WriteLine(el.@PurchaseOrderNumber)  
Next  
```  
  
 <span data-ttu-id="b67d3-111">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="b67d3-111">This code produces the following output:</span></span>  
  
```  
99505  
```  
  
## <a name="example"></a><span data-ttu-id="b67d3-112">Пример</span><span class="sxs-lookup"><span data-stu-id="b67d3-112">Example</span></span>  
 <span data-ttu-id="b67d3-113">Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="b67d3-113">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="b67d3-114">Дополнительные сведения см. в разделе [работа с пространствами имен XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="b67d3-114">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="b67d3-115">В этом примере используется следующий XML-документ: [Пример XML-файла. Несколько заказов на покупку в пространстве имен](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="b67d3-115">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns:aw='http://www.adventure-works.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("PurchaseOrdersInNamespace.xml")  
        Dim purchaseOrders As IEnumerable(Of XElement) = _  
            From el In root.<aw:PurchaseOrder> _  
            Where _  
                (From add In el.<aw:Address> _  
                Where _  
                     add.@aw:Type = "Shipping" And _  
                     add.<aw:State>.Value = "NY" _  
                Select add) _  
            .Any() _  
            Select el  
        For Each el As XElement In purchaseOrders  
            Console.WriteLine(el.@aw:PurchaseOrderNumber)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="b67d3-116">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="b67d3-116">This code produces the following output:</span></span>  
  
```  
99505  
```  
  
## <a name="see-also"></a><span data-ttu-id="b67d3-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b67d3-117">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="b67d3-118">Базовые запросы (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b67d3-118">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
- [<span data-ttu-id="b67d3-119">Свойство дочерней оси XML</span><span class="sxs-lookup"><span data-stu-id="b67d3-119">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="b67d3-120">Свойство оси атрибута XML</span><span class="sxs-lookup"><span data-stu-id="b67d3-120">XML Attribute Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
- [<span data-ttu-id="b67d3-121">Свойство значения XML</span><span class="sxs-lookup"><span data-stu-id="b67d3-121">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="b67d3-122">Операции проекции (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b67d3-122">Projection Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
- [<span data-ttu-id="b67d3-123">Операции, использующие квантификаторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b67d3-123">Quantifier Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)
