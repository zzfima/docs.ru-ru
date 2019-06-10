---
title: Практическое руководство. Извлечение коллекции элементов (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: b849668c-7976-4974-b8e1-1cd587d34258
ms.openlocfilehash: 42d1eaeb5e0ce43d27cd4675f634ab3dfca80a53
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66485092"
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-c"></a><span data-ttu-id="a20e9-102">Практическое руководство. Извлечение коллекции элементов (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="a20e9-102">How to: Retrieve a Collection of Elements (LINQ to XML) (C#)</span></span>
<span data-ttu-id="a20e9-103">В этом разделе показан метод <xref:System.Xml.Linq.XContainer.Elements%2A>.</span><span class="sxs-lookup"><span data-stu-id="a20e9-103">This topic demonstrates the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span> <span data-ttu-id="a20e9-104">Этот метод получает коллекцию дочерних элементов того или иного элемента.</span><span class="sxs-lookup"><span data-stu-id="a20e9-104">This method retrieves a collection of the child elements of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a20e9-105">Пример</span><span class="sxs-lookup"><span data-stu-id="a20e9-105">Example</span></span>  
 <span data-ttu-id="a20e9-106">В этом примере выполняется итерация по дочерним элементам элемента `purchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="a20e9-106">This example iterates through the child elements of the `purchaseOrder` element.</span></span>  
  
 <span data-ttu-id="a20e9-107">В этом примере используется следующий XML-документ: [Пример XML-файла. Типичный заказ на покупку (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="a20e9-107">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> childElements =  
    from el in po.Elements()  
    select el;  
foreach (XElement el in childElements)  
    Console.WriteLine("Name: " + el.Name);  
```  
  
 <span data-ttu-id="a20e9-108">В этом примере формируются следующие данные:</span><span class="sxs-lookup"><span data-stu-id="a20e9-108">This example produces the following output.</span></span>  
  
```  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a><span data-ttu-id="a20e9-109">См. также</span><span class="sxs-lookup"><span data-stu-id="a20e9-109">See also</span></span>

- [<span data-ttu-id="a20e9-110">Оси LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="a20e9-110">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes-overview.md)
