---
title: "Практическое руководство: преобразование формы дерева XML (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 84b60854-48b2-452c-87f2-77d53e1d653a
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9c71f4af829a395204bc17161547aa5fdd06cbb1
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-transform-the-shape-of-an-xml-tree-visual-basic"></a>Практическое руководство: преобразование формы дерева XML (Visual Basic)
*Фигуры* XML-документу обозначает совокупность имен элементов, именами атрибутов и характеристик его иерархии.  
  
 Иногда может потребоваться изменить форму XML-документа. Например, может потребоваться передать существующий XML-документ в другую систему, которая использует другие названия элементов и атрибутов. Можно пройти по документу, удаляя и переименовывая элементы согласно требованиям, однако использование результатов функциональных построений дает более читаемый код и просто код для обработки. Дополнительные сведения о функциональном построении см. в разделе [функциональное построение (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).  
  
 В первом примере выполнится изменение организации всего XML-документа. Происходит перемещение сложных элементов из одного места дерева в другое.  
  
 Во втором примере, приведенном в этом разделе, создается XML-документ, форма которого отлична от формы исходного документа. Выполняется изменение тегов имен элементов, переименование некоторых элементов и опущение некоторых элементов, присутствующих в исходном дереве.  
  
## <a name="example"></a>Пример  
 Следующий код позволяет изменить форму XML-файла при помощи внедренного выражения запроса.  
  
 Исходный XML-документ в этом примере содержит `Customers` элемент `Root`, в котором содержится список всех клиентов. Он также содержит элемент `Orders` под элементом `Root`, который содержит все заказы. В этом примере создается новое XML-дерево, в котором заказы каждого клиента содержатся в элементе `Orders`, который является дочерним по отношению к элементу `Customer`. Оригинальный документ также содержит элемент `CustomerID` внутри элемента `Order`. Этот элемент будет удален из преобразованного документа.  
  
 В этом примере используется следующий XML-документ: [пример XML-файла: Customers и Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).  
  
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
  
 Этот код выводит следующие результаты:  
  
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
  
## <a name="example"></a>Пример  
 В этом примере выполняется переименование некоторых элементов и преобразование некоторых атрибутов в элементы.  
  
 Этот код вызывает `ConvertAddress`, который возвращает список <xref:System.Xml.Linq.XElement>объектов.</xref:System.Xml.Linq.XElement> По отношению к методу аргументом является запрос, который определяет сложный элемент `Address`, в котором атрибут `Type` обладает значением `"Shipping"`.  
  
 В этом примере используется следующий XML-документ: [пример XML-файла: типичный заказ на покупку (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).  
  
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
  
 Этот код выводит следующие результаты:  
  
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
  
## <a name="see-also"></a>См. также  
 [Проекции и преобразования (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
