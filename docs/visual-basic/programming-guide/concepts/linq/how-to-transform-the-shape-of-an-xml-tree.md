---
title: Практическое руководство. Преобразование формы дерева XML
ms.date: 07/20/2015
ms.assetid: 84b60854-48b2-452c-87f2-77d53e1d653a
ms.openlocfilehash: 67ffd5f50572c0deba75c664ffd0e12ecfabf730
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332423"
---
# <a name="how-to-transform-the-shape-of-an-xml-tree-visual-basic"></a><span data-ttu-id="b0049-102">Как преобразовать форму XML-дерева (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b0049-102">How to: Transform the Shape of an XML Tree (Visual Basic)</span></span>
<span data-ttu-id="b0049-103">Понятие *форма* применительно к XML-документу обозначает совокупность имен элементов, атрибутов и характеристик его иерархии.</span><span class="sxs-lookup"><span data-stu-id="b0049-103">The *shape* of an XML document refers to its element names, attribute names, and the characteristics of its hierarchy.</span></span>  
  
 <span data-ttu-id="b0049-104">Иногда может потребоваться изменить форму XML-документа.</span><span class="sxs-lookup"><span data-stu-id="b0049-104">Sometimes you will have to change the shape of an XML document.</span></span> <span data-ttu-id="b0049-105">Например, может потребоваться передать существующий XML-документ в другую систему, которая использует другие названия элементов и атрибутов.</span><span class="sxs-lookup"><span data-stu-id="b0049-105">For example, you might have to send an existing XML document to another system that requires different element and attribute names.</span></span> <span data-ttu-id="b0049-106">Можно пройти по документу, удаляя и переименовывая элементы согласно требованиям, однако использование результатов функциональных построений дает более читаемый код и просто код для обработки.</span><span class="sxs-lookup"><span data-stu-id="b0049-106">You could go through the document, deleting and renaming elements as required, but using functional construction results in more readable and maintainable code.</span></span> <span data-ttu-id="b0049-107">Дополнительные сведения о функциональном построении см. в разделе [функциональное построение (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b0049-107">For more information about functional construction, see [Functional Construction (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="b0049-108">В первом примере выполнится изменение организации всего XML-документа.</span><span class="sxs-lookup"><span data-stu-id="b0049-108">The first example changes the organization of the XML document.</span></span> <span data-ttu-id="b0049-109">Происходит перемещение сложных элементов из одного места дерева в другое.</span><span class="sxs-lookup"><span data-stu-id="b0049-109">It moves complex elements from one location in the tree to another.</span></span>  
  
 <span data-ttu-id="b0049-110">Во втором примере, приведенном в этом разделе, создается XML-документ, форма которого отлична от формы исходного документа.</span><span class="sxs-lookup"><span data-stu-id="b0049-110">The second example in this topic creates an XML document with a different shape than the source document.</span></span> <span data-ttu-id="b0049-111">Выполняется изменение тегов имен элементов, переименование некоторых элементов и опущение некоторых элементов, присутствующих в исходном дереве.</span><span class="sxs-lookup"><span data-stu-id="b0049-111">It changes the casing of the element names, renames some elements, and leaves some elements from the source tree out of the transformed tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0049-112">Пример</span><span class="sxs-lookup"><span data-stu-id="b0049-112">Example</span></span>  
 <span data-ttu-id="b0049-113">Следующий код позволяет изменить форму XML-файла при помощи внедренного выражения запроса.</span><span class="sxs-lookup"><span data-stu-id="b0049-113">The following code changes the shape of an XML file using embedded query expressions.</span></span>  
  
 <span data-ttu-id="b0049-114">Исходный XML-документ в этом примере содержит `Customers` элемент `Root`, в котором содержится список всех клиентов.</span><span class="sxs-lookup"><span data-stu-id="b0049-114">The source XML document in this example contains a `Customers` element under the `Root` element that contains all customers.</span></span> <span data-ttu-id="b0049-115">Он также содержит элемент `Orders` под элементом `Root`, который содержит все заказы.</span><span class="sxs-lookup"><span data-stu-id="b0049-115">It also contains an `Orders` element under the `Root` element that contains all orders.</span></span> <span data-ttu-id="b0049-116">В этом примере создается новое XML-дерево, в котором заказы каждого клиента содержатся в элементе `Orders`, который является дочерним по отношению к элементу `Customer`.</span><span class="sxs-lookup"><span data-stu-id="b0049-116">This example creates a new XML tree in which the orders for each customer are contained in an `Orders` element within the `Customer` element.</span></span> <span data-ttu-id="b0049-117">Оригинальный документ также содержит элемент `CustomerID` внутри элемента `Order`. Этот элемент будет удален из преобразованного документа.</span><span class="sxs-lookup"><span data-stu-id="b0049-117">The original document also contains a `CustomerID` element in the `Order` element; this element will be removed from the re-shaped document.</span></span>  
  
 <span data-ttu-id="b0049-118">В этом примере используется следующий XML-документ: [Пример XML-файла. Клиенты и заказы (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b0049-118">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim co As XElement = XElement.Load("CustomersOrders.xml")  
Dim newCustOrd = _  
    <Root>  
        <%= From cust In co.<Customers>.<Customer> _  
            Select _  
            <Customer>  
                <%= cust.Attributes() %>  
                <%= cust.Elements() %>  
                <Orders>  
                    <%= From ord In co.<Orders>.<Order> _  
                        Where ord.<CustomerID>.Value = cust.@CustomerID _  
                        Select _  
                        <Order>  
                            <%= ord.Attributes() %>  
                            <%= ord.<EmployeeID> %>  
                            <%= ord.<OrderDate> %>  
                            <%= ord.<RequiredDate> %>  
                            <%= ord.<ShipInfo> %>  
                        </Order> _  
                    %>  
                </Orders>  
            </Customer> _  
        %>  
    </Root>  
Console.WriteLine(newCustOrd)  
```  
  
 <span data-ttu-id="b0049-119">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="b0049-119">This code produces the following output:</span></span>  
  
```xml  
        <Root>  
<Customer CustomerID="GREAL">  
  <CompanyName>Great Lakes Food Market</CompanyName>  
  <ContactName>Howard Snyder</ContactName>  
  <ContactTitle>Marketing Manager</ContactTitle>  
  <Phone>(503) 555-7555</Phone>  
  <FullAddress>  
    <Address>2732 Baker Blvd.</Address>  
    <City>Eugene</City>  
    <Region>OR</Region>  
    <PostalCode>97403</PostalCode>  
    <Country>USA</Country>  
  </FullAddress>  
  <Orders />  
</Customer>  
<Customer CustomerID="HUNGC">  
  <CompanyName>Hungry Coyote Import Store</CompanyName>  
  <ContactName>Yoshi Latimer</ContactName>  
  <ContactTitle>Sales Representative</ContactTitle>  
  <Phone>(503) 555-6874</Phone>  
  <Fax>(503) 555-2376</Fax>  
  <FullAddress>  
    <Address>City Center Plaza 516 Main St.</Address>  
    <City>Elgin</City>  
    <Region>OR</Region>  
    <PostalCode>97827</PostalCode>  
    <Country>USA</Country>  
  </FullAddress>  
  <Orders />  
</Customer>  
. . .  
```  
  
## <a name="example"></a><span data-ttu-id="b0049-120">Пример</span><span class="sxs-lookup"><span data-stu-id="b0049-120">Example</span></span>  
 <span data-ttu-id="b0049-121">В этом примере выполняется переименование некоторых элементов и преобразование некоторых атрибутов в элементы.</span><span class="sxs-lookup"><span data-stu-id="b0049-121">This example renames some elements and converts some attributes to elements.</span></span>  
  
 <span data-ttu-id="b0049-122">Код вызывает `ConvertAddress`, который возвращает объекты <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="b0049-122">The code calls `ConvertAddress`, which returns a list of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="b0049-123">По отношению к методу аргументом является запрос, который определяет сложный элемент `Address`, в котором атрибут `Type` обладает значением `"Shipping"`.</span><span class="sxs-lookup"><span data-stu-id="b0049-123">The argument to the method is a query that determines the `Address` complex element where the `Type` attribute has a value of `"Shipping"`.</span></span>  
  
 <span data-ttu-id="b0049-124">В этом примере используется следующий XML-документ: [Пример XML-файла. Стандартный заказ на покупку (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b0049-124">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Function ConvertAddress(ByVal add As XElement) As IEnumerable(Of XElement)  
    Dim fragment = New List(Of XElement)  
    fragment.Add(<NAME><%= add.<Name>.Value %></NAME>)  
    fragment.Add(<STREET><%= add.<Street>.Value %></STREET>)  
    fragment.Add(<CITY><%= add.<City>.Value %></CITY>)  
    fragment.Add(<ST><%= add.<State>.Value %></ST>)  
    fragment.Add(<POSTALCODE><%= add.<Zip>.Value %></POSTALCODE>)  
    fragment.Add(<COUNTRY><%= add.<Country>.Value %></COUNTRY>)  
    Return fragment  
End Function  
  
Sub Main()  
    Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
    Dim newPo As XElement = _  
        <PO>  
            <ID><%= po.@PurchaseOrderNumber %></ID>  
            <DATE><%= CDate(po.@OrderDate) %></DATE>  
            <%= _  
                ConvertAddress( _  
                (From el In po.<Address> _  
                Where el.@Type = "Shipping" _  
                Select el) _  
                .First() _  
                ) _  
            %>  
        </PO>  
    Console.WriteLine(newPo)  
End Sub  
```  
  
 <span data-ttu-id="b0049-125">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="b0049-125">This code produces the following output:</span></span>  
  
```xml  
<PO>  
  <ID>99503</ID>  
  <DATE>1999-10-20T00:00:00</DATE>  
  <NAME>Ellen Adams</NAME>  
  <STREET>123 Maple Street</STREET>  
  <CITY>Mill Valley</CITY>  
  <ST>CA</ST>  
  <POSTALCODE>10999</POSTALCODE>  
  <COUNTRY>USA</COUNTRY>  
</PO>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b0049-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b0049-126">See also</span></span>

- [<span data-ttu-id="b0049-127">Проекции и преобразования (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b0049-127">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
