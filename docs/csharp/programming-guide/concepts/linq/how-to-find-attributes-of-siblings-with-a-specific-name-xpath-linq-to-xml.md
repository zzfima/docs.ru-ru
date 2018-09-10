---
title: Практическое руководство. Поиск атрибутов элементов того же уровня с определенным именем (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: c3133d64-523f-422d-8838-73d36b945ca0
ms.openlocfilehash: 60b6529f310ccbb02160ff96e1db7870bcc71058
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863125"
---
# <a name="how-to-find-attributes-of-siblings-with-a-specific-name-xpath-linq-to-xml-c"></a>Практическое руководство. Поиск атрибутов элементов того же уровня с определенным именем (XPath-LINQ to XML) (C#)
В этом разделе показано, как найти все атрибуты одноуровневых элементов контекстного узла. В коллекции возвращаются только атрибуты с заданным именем.  
  
 Выражение XPath:  
  
 `../Book/@id`  
  
## <a name="example"></a>Пример  
 В этом примере вначале происходит поиск элемента `Book`, затем всех одноуровневых элементов с именем `Book`, а после этого всех атрибутов с именем `id`. Результатом становится коллекция атрибутов.  
  
 В этом примере используется следующий XML-документ: [Пример XML-файла. Книги (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).  
  
```csharp  
XDocument books = XDocument.Load("Books.xml");  
  
XElement book =   
    books  
    .Root  
    .Element("Book");  
  
// LINQ to XML query  
IEnumerable<XAttribute> list1 =  
    from el in book.Parent.Elements("Book")  
    select el.Attribute("id");  
  
// XPath expression  
IEnumerable<XAttribute> list2 =  
  ((IEnumerable)book.XPathEvaluate("../Book/@id")).Cast<XAttribute>();  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XAttribute el in list1)  
    Console.WriteLine(el);  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
Results are identical  
id="bk101"  
id="bk102"  
```  
  
## <a name="see-also"></a>См. также

- [LINQ to XML для пользователей XPath (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
