---
title: Извлечение коллекции элементов (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: b849668c-7976-4974-b8e1-1cd587d34258
ms.openlocfilehash: 89799b17115fb56a93bda5fbc144b21b334a6974
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75345017"
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-c"></a><span data-ttu-id="fbc72-102">Извлечение коллекции элементов (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="fbc72-102">How to retrieve a collection of elements (LINQ to XML) (C#)</span></span>
<span data-ttu-id="fbc72-103">В этом разделе показан метод <xref:System.Xml.Linq.XContainer.Elements%2A>.</span><span class="sxs-lookup"><span data-stu-id="fbc72-103">This topic demonstrates the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span> <span data-ttu-id="fbc72-104">Этот метод получает коллекцию дочерних элементов того или иного элемента.</span><span class="sxs-lookup"><span data-stu-id="fbc72-104">This method retrieves a collection of the child elements of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbc72-105">Пример</span><span class="sxs-lookup"><span data-stu-id="fbc72-105">Example</span></span>  
 <span data-ttu-id="fbc72-106">В этом примере выполняется итерация по дочерним элементам элемента `purchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="fbc72-106">This example iterates through the child elements of the `purchaseOrder` element.</span></span>  
  
 <span data-ttu-id="fbc72-107">В этом примере используется следующий XML-документ: [Пример XML-файла. Стандартный заказ на покупку (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="fbc72-107">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> childElements =  
    from el in po.Elements()  
    select el;  
foreach (XElement el in childElements)  
    Console.WriteLine("Name: " + el.Name);  
```  
  
 <span data-ttu-id="fbc72-108">В этом примере формируются следующие данные:</span><span class="sxs-lookup"><span data-stu-id="fbc72-108">This example produces the following output.</span></span>  
  
```output  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a><span data-ttu-id="fbc72-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fbc72-109">See also</span></span>

- [<span data-ttu-id="fbc72-110">Оси LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="fbc72-110">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
