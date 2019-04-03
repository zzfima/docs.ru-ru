---
title: Практическое руководство. Поиск предшествующих элементов того же уровня (XPath-LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 59055718-d0a7-4db3-8901-18dd33587703
ms.openlocfilehash: 4584a84df0e25b451a440c33e17c14cd78fc78bf
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58833014"
---
# <a name="how-to-find-preceding-siblings-xpath-linq-to-xml-visual-basic"></a>Практическое руководство. Поиск предшествующих элементов того же уровня (XPath-LINQ to XML) (Visual Basic)
В этом разделе сравнивается ось XPath `preceding-sibling` с дочерней для [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] осью <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType>.  
  
 Выражение XPath:  
  
 `preceding-sibling::*`  
  
 Обратите внимание, что результаты как <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A>, так и <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> соответствуют структуре документа.  
  
## <a name="example"></a>Пример  
 В следующем примере находится элемент `FullAddress`, после чего при помощи оси `preceding-sibling` получаются предыдущие элементы.  
  
 В этом примере используется следующий XML-документ: [Пример XML-файла. Заказчики и заказы (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).  
  
```vb  
Dim co As XElement = XElement.Load("CustomersOrders.xml")  
Dim add As XElement = co.<Customers>.<Customer>. _  
        <FullAddress>.FirstOrDefault  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = add.ElementsBeforeSelf()  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = add.XPathSelectElements("preceding-sibling::*")  
  
If list1.Count() = list2.Count() And _  
        list1.Intersect(list2).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list2  
    Console.WriteLine(el)  
Next  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
Results are identical  
<CompanyName>Great Lakes Food Market</CompanyName>  
<ContactName>Howard Snyder</ContactName>  
<ContactTitle>Marketing Manager</ContactTitle>  
<Phone>(503) 555-7555</Phone>  
```  
  
## <a name="see-also"></a>См. также

- [LINQ to XML для пользователей XPath (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
