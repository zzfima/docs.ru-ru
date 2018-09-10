---
title: Практическое руководство. Поиск предшествующих элементов того же уровня (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: b281ff99-d08a-43d0-bea1-eff831b2f8ae
ms.openlocfilehash: d2bd34db7bd839e50ec3e77819230f5f6410b73e
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43787126"
---
# <a name="how-to-find-preceding-siblings-xpath-linq-to-xml-c"></a>Практическое руководство. Поиск предшествующих элементов того же уровня (XPath-LINQ to XML) (C#)
В этом разделе сравнивается ось XPath `preceding-sibling` с дочерней для [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] осью <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType>.  
  
 Выражение XPath:  
  
 `preceding-sibling::*`  
  
 Обратите внимание, что результаты как <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A>, так и <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> соответствуют структуре документа.  
  
## <a name="example"></a>Пример  
 В следующем примере находится элемент `FullAddress`, после чего при помощи оси `preceding-sibling` получаются предыдущие элементы.  
  
 В этом примере используется следующий XML-документ: [Пример XML-файла. Клиенты и заказы (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).  
  
```csharp  
XElement co = XElement.Load("CustomersOrders.xml");  
  
XElement add = co.Element("Customers").Element("Customer").Element("FullAddress");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = add.ElementsBeforeSelf();  
  
// XPath expression  
IEnumerable<XElement> list2 = add.XPathSelectElements("preceding-sibling::*");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list2)  
    Console.WriteLine(el);  
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

- [LINQ to XML для пользователей XPath (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
