---
title: Практическое руководство. Извлечение коллекции атрибутов (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: a49ee7a3-b2c2-4d49-9b5c-b7c6c41f4f13
ms.openlocfilehash: d561c3bbebbf57c88ccc9043449540bca06e33fb
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486351"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-c"></a><span data-ttu-id="cc38a-102">Практическое руководство. Извлечение коллекции атрибутов (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="cc38a-102">How to: Retrieve a Collection of Attributes (LINQ to XML) (C#)</span></span>
<span data-ttu-id="cc38a-103">В этом разделе представлен метод <xref:System.Xml.Linq.XElement.Attributes%2A>.</span><span class="sxs-lookup"><span data-stu-id="cc38a-103">This topic introduces the <xref:System.Xml.Linq.XElement.Attributes%2A> method.</span></span> <span data-ttu-id="cc38a-104">Этот метод извлекает атрибуты того или иного элемента.</span><span class="sxs-lookup"><span data-stu-id="cc38a-104">This method retrieves the attributes of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc38a-105">Пример</span><span class="sxs-lookup"><span data-stu-id="cc38a-105">Example</span></span>  
 <span data-ttu-id="cc38a-106">В следующем примере показано, как просматривать коллекцию атрибутов элемента.</span><span class="sxs-lookup"><span data-stu-id="cc38a-106">The following example shows how to iterate through the collection of attributes of an element.</span></span>  
  
```csharp  
XElement val = new XElement("Value",  
    new XAttribute("ID", "1243"),  
    new XAttribute("Type", "int"),  
    new XAttribute("ConvertableTo", "double"),  
    "100");  
IEnumerable<XAttribute> listOfAttributes =  
    from att in val.Attributes()  
    select att;  
foreach (XAttribute a in listOfAttributes)  
    Console.WriteLine(a);  
```  
  
 <span data-ttu-id="cc38a-107">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="cc38a-107">This code produces the following output:</span></span>  
  
```  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a><span data-ttu-id="cc38a-108">См. также</span><span class="sxs-lookup"><span data-stu-id="cc38a-108">See also</span></span>

- [<span data-ttu-id="cc38a-109">Оси LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="cc38a-109">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes-overview.md)
