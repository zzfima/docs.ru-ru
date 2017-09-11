---
title: "Практическое руководство: цепочку вызовы для методов осей (LINQ to XML) (Visual Basic) | Документы Microsoft"
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
ms.assetid: e4e22942-39bd-460f-b3c0-9f09e53d3aa9
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: 4997f7e91f968f080c22ca9d3a204c748758f832
ms.contentlocale: ru-ru
ms.lasthandoff: 06/01/2017


---
# <a name="how-to-chain-axis-method-calls-linq-to-xml-visual-basic"></a><span data-ttu-id="95253-102">Практическое руководство: цепочку вызовы для методов осей (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95253-102">How to: Chain Axis Method Calls (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="95253-103">Обычно при написании кода вы будете придерживаться схемы, по которой вызывается метод оси, после чего вызывается одна из осей метода расширений.</span><span class="sxs-lookup"><span data-stu-id="95253-103">A common pattern that you will use in your code is to call an axis method, then call one of the extension method axes.</span></span>  
  
 <span data-ttu-id="95253-104">Существуют две оси с именем `Elements` , которые возвращают коллекцию элементов: <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>метод и <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName>метод.</xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> </xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="95253-104">There are two axes with the name of `Elements` that return a collection of elements: the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> method and the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="95253-105">Можно сочетать эти две оси таким образом, чтобы найти все элементы с указанным именем на заданной глубине дерева.</span><span class="sxs-lookup"><span data-stu-id="95253-105">You can combine these two axes to find all elements of a specified name at a given depth in the tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95253-106">Пример</span><span class="sxs-lookup"><span data-stu-id="95253-106">Example</span></span>  
 <span data-ttu-id="95253-107">В этом примере используется <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>и <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName>для поиска всех `Name` элементы во всех `Address` элементы во всех `PurchaseOrder` элементы.</xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> </xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="95253-107">This example uses <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> and <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> to find all `Name` elements in all `Address` elements in all `PurchaseOrder` elements.</span></span>  
  
 <span data-ttu-id="95253-108">В этом примере используется следующий XML-документ: [пример XML-файла: несколько заказов на покупку (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="95253-108">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim purchaseOrders As XElement = XElement.Load("PurchaseOrders.xml")  
Dim names As IEnumerable(Of XElement) = _  
    From el In purchaseOrders.<PurchaseOrder>.<Address>.<Name> _  
    Select el  
For Each e As XElement In names  
    Console.WriteLine(e)  
Next  
```  
  
 <span data-ttu-id="95253-109">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="95253-109">This example produces the following output:</span></span>  
  
```xml  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
 <span data-ttu-id="95253-110">Это работает, поскольку один из реализаций `Elements` ось — как метод расширения <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="95253-110">This works because one of the implementations of the `Elements` axis is as an extension method on <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="95253-111"><xref:System.Xml.Linq.XElement>является производным от <xref:System.Xml.Linq.XContainer>, чтобы можно было вызвать <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName>результаты вызова метода <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>метод.</xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> </xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> </xref:System.Xml.Linq.XContainer></xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="95253-111"><xref:System.Xml.Linq.XElement> derives from <xref:System.Xml.Linq.XContainer>, so you can call the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> method on the results of a call to the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95253-112">Пример</span><span class="sxs-lookup"><span data-stu-id="95253-112">Example</span></span>  
 <span data-ttu-id="95253-113">Иногда может потребоваться получить все элементы с определенной глубины структуры элементов при условии, что неизвестно, имеются промежуточные предки или нет.</span><span class="sxs-lookup"><span data-stu-id="95253-113">Sometimes you want to retrieve all elements at a particular element depth when there might or might not be intervening ancestors.</span></span> <span data-ttu-id="95253-114">Например, в следующем документе может потребоваться получение всех элементов `ConfigParameter`, которые являются дочерними по отношению к элементу `Customer`, кроме `ConfigParameter`, которые являются дочерними по отношению к элементу `Root`.</span><span class="sxs-lookup"><span data-stu-id="95253-114">For example, in the following document, you might want to retrieve all the `ConfigParameter` elements that are children of the `Customer` element, but not the `ConfigParameter` that is a child of the `Root` element.</span></span>  
  
```xml  
<Root>  
  <ConfigParameter>RootConfigParameter</ConfigParameter>  
  <Customer>  
    <Name>Frank</Name>  
    <Config>  
      <ConfigParameter>FirstConfigParameter</ConfigParameter>  
    </Config>  
  </Customer>  
  <Customer>  
    <Name>Bob</Name>  
    <!--This customer doesn't have a Config element-->  
  </Customer>  
  <Customer>  
    <Name>Bill</Name>  
    <Config>  
      <ConfigParameter>SecondConfigParameter</ConfigParameter>  
    </Config>  
  </Customer>  
</Root>  
```  
  
 <span data-ttu-id="95253-115">Чтобы сделать это, можно использовать <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName>оси, следующим образом:</xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="95253-115">To do this, you can use the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> axis, as follows:</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("Irregular.xml")  
Dim configParameters As IEnumerable(Of XElement) = _  
    root.<Customer>.<Config>.<ConfigParameter>  
For Each cp As XElement In configParameters  
    Console.WriteLine(cp)  
Next  
```  
  
 <span data-ttu-id="95253-116">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="95253-116">This example produces the following output:</span></span>  
  
```xml  
<ConfigParameter>FirstConfigParameter</ConfigParameter>  
<ConfigParameter>SecondConfigParameter</ConfigParameter>  
```  
  
## <a name="example"></a><span data-ttu-id="95253-117">Пример</span><span class="sxs-lookup"><span data-stu-id="95253-117">Example</span></span>  
 <span data-ttu-id="95253-118">Следующий пример демонстрирует тот же способ обработки XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="95253-118">The following example shows the same technique for XML that is in a namespace.</span></span> <span data-ttu-id="95253-119">Дополнительные сведения см. в разделе [работа с пространствами имен XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="95253-119">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="95253-120">В этом примере используется следующий XML-документ: [пример XML-файла: несколько заказов на покупку в пространстве имен](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="95253-120">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim purchaseOrders As XElement = XElement.Load("PurchaseOrdersInNamespace.xml")  
        Dim names As IEnumerable(Of XElement) = _  
            From el In purchaseOrders.<aw:PurchaseOrder>.<aw:Address>.<aw:Name> _  
            Select el  
        For Each e As XElement In names  
            Console.WriteLine(e)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="95253-121">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="95253-121">This example produces the following output:</span></span>  
  
```xml  
<aw:Name xmlns:aw="http://www.adventure-works.com">Ellen Adams</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Tai Yee</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
```  
  
## <a name="see-also"></a><span data-ttu-id="95253-122">См. также</span><span class="sxs-lookup"><span data-stu-id="95253-122">See Also</span></span>  
 [<span data-ttu-id="95253-123">Оси LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95253-123">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
