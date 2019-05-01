---
title: Практическое руководство. Извлечение коллекции элементов (LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 2269f9de-8fb9-4666-b8a1-a4e754fa6a81
ms.openlocfilehash: 53572ac3c80e012b95527d32da28c8685cd8cfd3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62021379"
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-visual-basic"></a><span data-ttu-id="10a13-102">Практическое руководство. Извлечение коллекции элементов (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10a13-102">How to: Retrieve a Collection of Elements (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="10a13-103">В этом разделе показан метод <xref:System.Xml.Linq.XContainer.Elements%2A>.</span><span class="sxs-lookup"><span data-stu-id="10a13-103">This topic demonstrates the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span> <span data-ttu-id="10a13-104">Этот метод получает коллекцию дочерних элементов того или иного элемента.</span><span class="sxs-lookup"><span data-stu-id="10a13-104">This method retrieves a collection of the child elements of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10a13-105">Пример</span><span class="sxs-lookup"><span data-stu-id="10a13-105">Example</span></span>  
 <span data-ttu-id="10a13-106">В этом примере выполняется итерация по дочерним элементам элемента `purchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="10a13-106">This example iterates through the child elements of the `purchaseOrder` element.</span></span>  
  
 <span data-ttu-id="10a13-107">В этом примере используется следующий XML-документ: [Пример XML-файла. Типичный заказ на покупку (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="10a13-107">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim childElements As IEnumerable(Of XElement)  
childElements = _  
    From el In po.Elements() _  
    Select el  
For Each el As XElement In childElements  
    Console.WriteLine("Name: " & el.Name.ToString())  
Next  
```  
  
 <span data-ttu-id="10a13-108">В этом примере формируются следующие данные:</span><span class="sxs-lookup"><span data-stu-id="10a13-108">This example produces the following output.</span></span>  
  
```  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a><span data-ttu-id="10a13-109">См. также</span><span class="sxs-lookup"><span data-stu-id="10a13-109">See also</span></span>

- [<span data-ttu-id="10a13-110">Оси LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10a13-110">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
