---
title: 'Практическое: поиск дочернего элемента (XPath-LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: adb46c98-a650-42e2-b62d-835920fe8421
ms.openlocfilehash: 122cc269b95a3f35b8eef71e9c7ca1d50af4210b
ms.sourcegitcommit: 869b5832b667915ac4a5dd8c86b1109ed26b6c08
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332617"
---
# <a name="how-to-find-a-child-element-xpath-linq-to-xml-visual-basic"></a>Практическое: поиск дочернего элемента (XPath-LINQ to XML) (Visual Basic)
В этом разделе сравнивается ось дочерних элементов XPath с методом [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<xref:System.Xml.Linq.XContainer.Element%2A>.  
  
 Выражение XPath - `DeliveryNotes`.  
  
## <a name="example"></a>Пример  
 В этом примере производится поиск дочернего элемента `DeliveryNotes`.  
  
 В этом примере используется следующий XML-документ: [Пример XML-файла. Несколько заказов на покупку (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
```vb  
Dim cpo As XDocument = XDocument.Load("PurchaseOrders.xml")  
Dim po As XElement = cpo.Root.<PurchaseOrder>.FirstOrDefault  
  
'LINQ to XML query  
Dim el1 As XElement = po.<DeliveryNotes>.FirstOrDefault  
  
' XPath expression  
Dim el2 As XElement = po.XPathSelectElement("DeliveryNotes")  
' same as "child::DeliveryNotes"  
' same as "./DeliveryNotes"  
  
If el1 Is el2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(el1)  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
Results are identical  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="see-also"></a>См. также  
 [LINQ to XML для пользователей XPath (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
