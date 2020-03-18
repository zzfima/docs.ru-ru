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
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-c"></a>Извлечение коллекции элементов (LINQ to XML) (C#)
В этом разделе показан метод <xref:System.Xml.Linq.XContainer.Elements%2A>. Этот метод получает коллекцию дочерних элементов того или иного элемента.  
  
## <a name="example"></a>Пример  
 В этом примере выполняется итерация по дочерним элементам элемента `purchaseOrder`.  
  
 В этом примере используется следующий XML-документ: [Пример XML-файла. Стандартный заказ на покупку (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> childElements =  
    from el in po.Elements()  
    select el;  
foreach (XElement el in childElements)  
    Console.WriteLine("Name: " + el.Name);  
```  
  
 В этом примере формируются следующие данные:  
  
```output  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a>См. также раздел

- [Оси LINQ to XML (C#)](./linq-to-xml-axes-overview.md)
