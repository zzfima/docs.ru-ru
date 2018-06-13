---
title: Практическое руководство. Извлечение коллекции элементов (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: b849668c-7976-4974-b8e1-1cd587d34258
ms.openlocfilehash: 8d2aab59a6c2a72d796bfaf40755bdf280c81b6a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33320421"
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-c"></a><span data-ttu-id="5e398-102">Практическое руководство. Извлечение коллекции элементов (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="5e398-102">How to: Retrieve a Collection of Elements (LINQ to XML) (C#)</span></span>
<span data-ttu-id="5e398-103">В этом разделе показан метод <xref:System.Xml.Linq.XContainer.Elements%2A>.</span><span class="sxs-lookup"><span data-stu-id="5e398-103">This topic demonstrates the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span> <span data-ttu-id="5e398-104">Этот метод получает коллекцию дочерних элементов того или иного элемента.</span><span class="sxs-lookup"><span data-stu-id="5e398-104">This method retrieves a collection of the child elements of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e398-105">Пример</span><span class="sxs-lookup"><span data-stu-id="5e398-105">Example</span></span>  
 <span data-ttu-id="5e398-106">В этом примере выполняется итерация по дочерним элементам элемента `purchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="5e398-106">This example iterates through the child elements of the `purchaseOrder` element.</span></span>  
  
 <span data-ttu-id="5e398-107">В этом примере используется следующий XML-документ: [Пример XML-файла. Стандартный заказ на покупку (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="5e398-107">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> childElements =  
    from el in po.Elements()  
    select el;  
foreach (XElement el in childElements)  
    Console.WriteLine("Name: " + el.Name);  
```  
  
 <span data-ttu-id="5e398-108">В этом примере формируются следующие данные:</span><span class="sxs-lookup"><span data-stu-id="5e398-108">This example produces the following output.</span></span>  
  
```  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a><span data-ttu-id="5e398-109">См. также</span><span class="sxs-lookup"><span data-stu-id="5e398-109">See Also</span></span>  
 [<span data-ttu-id="5e398-110">Оси LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="5e398-110">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
