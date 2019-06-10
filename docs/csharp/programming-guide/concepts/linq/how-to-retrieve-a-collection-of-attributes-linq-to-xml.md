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
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-c"></a>Практическое руководство. Извлечение коллекции атрибутов (LINQ to XML) (C#)
В этом разделе представлен метод <xref:System.Xml.Linq.XElement.Attributes%2A>. Этот метод извлекает атрибуты того или иного элемента.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как просматривать коллекцию атрибутов элемента.  
  
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
  
 Этот код выводит следующие результаты:  
  
```  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a>См. также

- [Оси LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes-overview.md)
