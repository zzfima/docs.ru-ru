---
title: "Практическое руководство. Создание иерархии с помощью группировки (C#)"
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
ms.assetid: 0213d59e-5f76-438c-9cab-4bf11f7b971d
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 94b46f48698061368bba47bd7aa248610c0e8f30
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-hierarchy-using-grouping-c"></a><span data-ttu-id="9ddfe-102">Практическое руководство. Создание иерархии с помощью группировки (C#)</span><span class="sxs-lookup"><span data-stu-id="9ddfe-102">How to: Create Hierarchy Using Grouping (C#)</span></span>
<span data-ttu-id="9ddfe-103">Этот пример показывает, как группировать данные и затем создавать код XML на основе группирования.</span><span class="sxs-lookup"><span data-stu-id="9ddfe-103">This example shows how to group data, and then generate XML based on the grouping.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ddfe-104">Пример</span><span class="sxs-lookup"><span data-stu-id="9ddfe-104">Example</span></span>  
 <span data-ttu-id="9ddfe-105">В этом примере сначала данные группируются по категориям, а затем создается новый XML-файл, в котором XML-иерархия отражает группирование.</span><span class="sxs-lookup"><span data-stu-id="9ddfe-105">This example first groups data by a category, then generates a new XML file in which the XML hierarchy reflects the grouping.</span></span>  
  
 <span data-ttu-id="9ddfe-106">В этом примере используется следующий XML-документ: [Пример XML-файла. Числовые данные (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9ddfe-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XElement doc = XElement.Load("Data.xml");  
var newData =  
    new XElement("Root",  
        from data in doc.Elements("Data")  
        group data by (string)data.Element("Category") into groupedData  
        select new XElement("Group",  
            new XAttribute("ID", groupedData.Key),  
            from g in groupedData  
            select new XElement("Data",  
                g.Element("Quantity"),  
                g.Element("Price")  
            )  
        )  
    );  
Console.WriteLine(newData);  
```  
  
 <span data-ttu-id="9ddfe-107">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="9ddfe-107">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Group ID="A">  
    <Data>  
      <Quantity>3</Quantity>  
      <Price>24.50</Price>  
    </Data>  
    <Data>  
      <Quantity>5</Quantity>  
      <Price>4.95</Price>  
    </Data>  
    <Data>  
      <Quantity>3</Quantity>  
      <Price>66.00</Price>  
    </Data>  
    <Data>  
      <Quantity>15</Quantity>  
      <Price>29.00</Price>  
    </Data>  
  </Group>  
  <Group ID="B">  
    <Data>  
      <Quantity>1</Quantity>  
      <Price>89.99</Price>  
    </Data>  
    <Data>  
      <Quantity>10</Quantity>  
      <Price>.99</Price>  
    </Data>  
    <Data>  
      <Quantity>8</Quantity>  
      <Price>6.99</Price>  
    </Data>  
  </Group>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9ddfe-108">См. также</span><span class="sxs-lookup"><span data-stu-id="9ddfe-108">See Also</span></span>  
 [<span data-ttu-id="9ddfe-109">Дополнительные способы создания запросов (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="9ddfe-109">Advanced Query Techniques (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)

