---
title: "Практическое руководство: получение одного дочернего элемента (LINQ to XML) (Visual Basic) | Документы Microsoft"
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
ms.assetid: 0033e258-d9c4-4569-86f6-79b7c06d1204
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 006a6afbb07ceea64b8fcc6cdab1d4fd31ae3c87
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017


---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-visual-basic"></a><span data-ttu-id="edcfc-102">Практическое руководство: получение одного дочернего элемента (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="edcfc-102">How to: Retrieve a Single Child Element (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="edcfc-103">В этом разделе объясняется, как обеспечить получение отдельных дочерних элементов, когда известно имя этого дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="edcfc-103">This topic explains how to retrieve a single child element, given the name of the child element.</span></span> <span data-ttu-id="edcfc-104">Если известно имя дочернего элемента, а также то, что есть только один элемент с таким именем, удобнее получить один элемент, а не целую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="edcfc-104">When you know the name of the child element and that there is only one element that has this name, it can be convenient to retrieve just one element, instead of a collection.</span></span>  
  
 <span data-ttu-id="edcfc-105"><xref:System.Xml.Linq.XContainer.Element%2A>Метод возвращает первый дочерний <xref:System.Xml.Linq.XElement>с указанным <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XContainer.Element%2A></span><span class="sxs-lookup"><span data-stu-id="edcfc-105">The <xref:System.Xml.Linq.XContainer.Element%2A> method returns the first child <xref:System.Xml.Linq.XElement> with the specified <xref:System.Xml.Linq.XName>.</span></span>  
  
 <span data-ttu-id="edcfc-106">Если требуется получить отдельный дочерний элемент в Visual Basic, обычно используется XML-свойство, а затем происходит получение первого элемента при помощи обозначения индексатора массива.</span><span class="sxs-lookup"><span data-stu-id="edcfc-106">If you want to retrieve a single child element in Visual Basic, a common approach is to use the XML property, and then retrieve the first element using array indexer notation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="edcfc-107">Пример</span><span class="sxs-lookup"><span data-stu-id="edcfc-107">Example</span></span>  
 <span data-ttu-id="edcfc-108">В следующем примере показано использование <xref:System.Xml.Linq.XContainer.Element%2A>метода.</xref:System.Xml.Linq.XContainer.Element%2A></span><span class="sxs-lookup"><span data-stu-id="edcfc-108">The following example demonstrates the use of the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span> <span data-ttu-id="edcfc-109">В этом примере берется XML-дерево `po` и осуществляется поиск первого элемента с именем `Comment`.</span><span class="sxs-lookup"><span data-stu-id="edcfc-109">This example takes the XML tree named `po` and finds the first element named `Comment`.</span></span>  
  
 <span data-ttu-id="edcfc-110">В примере по Visual Basic демонстрируется использование обозначения индексатора массива для получения отдельного элемента.</span><span class="sxs-lookup"><span data-stu-id="edcfc-110">The Visual Basic example shows using array indexer notation to retrieve a single element.</span></span>  
  
 <span data-ttu-id="edcfc-111">В этом примере используется следующий XML-документ: [пример XML-файла: типичный заказ на покупку (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="edcfc-111">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim e As XElement = po.<DeliveryNotes>(0)  
Console.WriteLine(e)  
```  
  
 <span data-ttu-id="edcfc-112">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="edcfc-112">This example produces the following output:</span></span>  
  
```xml  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="example"></a><span data-ttu-id="edcfc-113">Пример</span><span class="sxs-lookup"><span data-stu-id="edcfc-113">Example</span></span>  
 <span data-ttu-id="edcfc-114">В следующем примере демонстрируется тот же код XML-документа, который находится в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="edcfc-114">The following example shows the same code for XML that is in a namespace.</span></span> <span data-ttu-id="edcfc-115">Дополнительные сведения см. в разделе [работа с пространствами имен XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="edcfc-115">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="edcfc-116">В этом примере используется следующий XML-документ: [пример XML-файла: типичный заказ на покупку в пространстве имен](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="edcfc-116">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrderInNamespace.xml")  
        Dim e As XElement = po.<aw:DeliveryNotes>(0)  
        Console.WriteLine(e)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="edcfc-117">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="edcfc-117">This example produces the following output:</span></span>  
  
```xml  
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>  
```  
  
## <a name="see-also"></a><span data-ttu-id="edcfc-118">См. также</span><span class="sxs-lookup"><span data-stu-id="edcfc-118">See Also</span></span>  
 [<span data-ttu-id="edcfc-119">Оси LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="edcfc-119">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)

