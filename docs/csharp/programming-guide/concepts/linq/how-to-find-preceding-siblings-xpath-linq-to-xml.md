---
title: "Практическое руководство. Поиск предшествующих элементов того же уровня (XPath-LINQ to XML) (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: b281ff99-d08a-43d0-bea1-eff831b2f8ae
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c49dd8998b0ad1e2a579b44f07462fb1111f3094
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-preceding-siblings-xpath-linq-to-xml-c"></a><span data-ttu-id="79dc8-102">Практическое руководство. Поиск предшествующих элементов того же уровня (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="79dc8-102">How to: Find Preceding Siblings (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="79dc8-103">В этом разделе сравнивается ось XPath `preceding-sibling` с дочерней для [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] осью <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="79dc8-103">This topic compares the XPath `preceding-sibling` axis to the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] child <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName> axis.</span></span>  
  
 <span data-ttu-id="79dc8-104">Выражение XPath:</span><span class="sxs-lookup"><span data-stu-id="79dc8-104">The XPath expression is:</span></span>  
  
 `preceding-sibling::*`  
  
 <span data-ttu-id="79dc8-105">Обратите внимание, что результаты как <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A>, так и <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName> соответствуют структуре документа.</span><span class="sxs-lookup"><span data-stu-id="79dc8-105">Note that the results of both <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> and <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName> are in document order.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79dc8-106">Пример</span><span class="sxs-lookup"><span data-stu-id="79dc8-106">Example</span></span>  
 <span data-ttu-id="79dc8-107">В следующем примере находится элемент `FullAddress`, после чего при помощи оси `preceding-sibling` получаются предыдущие элементы.</span><span class="sxs-lookup"><span data-stu-id="79dc8-107">The following example finds the `FullAddress` element, and then retrieves the previous elements using the `preceding-sibling` axis.</span></span>  
  
 <span data-ttu-id="79dc8-108">В этом примере используется следующий XML-документ: [Пример XML-файла. Клиенты и заказы (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="79dc8-108">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
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
  
 <span data-ttu-id="79dc8-109">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="79dc8-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
<CompanyName>Great Lakes Food Market</CompanyName>  
<ContactName>Howard Snyder</ContactName>  
<ContactTitle>Marketing Manager</ContactTitle>  
<Phone>(503) 555-7555</Phone>  
```  
  
## <a name="see-also"></a><span data-ttu-id="79dc8-110">См. также</span><span class="sxs-lookup"><span data-stu-id="79dc8-110">See Also</span></span>  
 [<span data-ttu-id="79dc8-111">LINQ to XML для пользователей XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="79dc8-111">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

