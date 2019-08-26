---
title: Практическое руководство. Фильтрация по атрибуту (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 208d6256-1bd7-4237-b2c9-909f26dfd0e2
ms.openlocfilehash: 96c6d26c035d70fb50e0b5dc022bd28fd0242edd
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69593826"
---
# <a name="how-to-filter-on-an-attribute-xpath-linq-to-xml-c"></a><span data-ttu-id="207bd-102">Практическое руководство. Фильтрация по атрибуту (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="207bd-102">How to: Filter on an Attribute (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="207bd-103">В этом разделе показано, как получать элементы-потомки с указанным именем и атрибут с заданным значением.</span><span class="sxs-lookup"><span data-stu-id="207bd-103">This topic shows how to get the descendant elements with a specified name, and with an attribute with a specified value.</span></span>  
  
 <span data-ttu-id="207bd-104">Выражение XPath:</span><span class="sxs-lookup"><span data-stu-id="207bd-104">The XPath expression is:</span></span>  
  
 `.//Address[@Type='Shipping']`  
  
## <a name="example"></a><span data-ttu-id="207bd-105">Пример</span><span class="sxs-lookup"><span data-stu-id="207bd-105">Example</span></span>  
 <span data-ttu-id="207bd-106">В этом примере обнаруживаются все элементы-потомки с именем `Address` и с атрибутом `Type`, имеющим значение «Доставка».</span><span class="sxs-lookup"><span data-stu-id="207bd-106">This example finds all descendants elements with the name of `Address`, and with a `Type` attribute with a value of "Shipping".</span></span>  
  
 <span data-ttu-id="207bd-107">В этом примере используется следующий XML-документ: [Пример XML-файла. Несколько заказов на покупку (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="207bd-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    from el in po.Descendants("Address")  
    where (string)el.Attribute("Type") == "Shipping"  
    select el;  
  
// XPath expression  
IEnumerable<XElement> list2 = po.XPathSelectElements(".//Address[@Type='Shipping']");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="207bd-108">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="207bd-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Address Type="Shipping">  
  <Name>Ellen Adams</Name>  
  <Street>123 Maple Street</Street>  
  <City>Mill Valley</City>  
  <State>CA</State>  
  <Zip>10999</Zip>  
  <Country>USA</Country>  
</Address>  
<Address Type="Shipping">  
  <Name>Cristian Osorio</Name>  
  <Street>456 Main Street</Street>  
  <City>Buffalo</City>  
  <State>NY</State>  
  <Zip>98112</Zip>  
  <Country>USA</Country>  
</Address>  
<Address Type="Shipping">  
  <Name>Jessica Arnold</Name>  
  <Street>4055 Madison Ave</Street>  
  <City>Seattle</City>  
  <State>WA</State>  
  <Zip>98112</Zip>  
  <Country>USA</Country>  
</Address>  
```  
