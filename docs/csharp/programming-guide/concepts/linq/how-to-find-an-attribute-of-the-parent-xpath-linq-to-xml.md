---
title: Практическое руководство. Поиск атрибута родительского элемента (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: 6f796bfb8f8b0051af4e31f6e82a503dbfbbc334
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a>Практическое руководство. Поиск атрибута родительского элемента (XPath-LINQ to XML) (C#)
Данный раздел показывает способ перехода к родительскому элементу и нахождения его атрибута.  
  
 Выражение XPath:  
  
 `../@id`  
  
## <a name="example"></a>Пример  
 Сначала в данном примере осуществляется поиск элемента `Author`. Затем в нем осуществляется поиск атрибута `id` родительского элемента.  
  
 В этом примере используется следующий XML-документ: [Пример XML-файла. Книги (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).  
  
```csharp  
XDocument books = XDocument.Load("Books.xml");  
  
XElement author =   
    books  
    .Root  
    .Element("Book")  
    .Element("Author");  
  
// LINQ to XML query  
XAttribute att1 =  
    author  
    .Parent  
    .Attribute("id");  
  
// XPath expression  
XAttribute att2 = ((IEnumerable)author.XPathEvaluate("../@id")).Cast<XAttribute>().First();  
  
if (att1 == att2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(att1);  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
Results are identical  
id="bk101"  
```  
  
## <a name="see-also"></a>См. также  
 [LINQ to XML для пользователей XPath (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
