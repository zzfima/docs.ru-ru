---
title: "Практическое руководство: поиск объединения двух путей расположения (XPath-LINQ to XML) (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: c82c09b4-cb0a-47ec-8cc3-a124144c2788
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 90fe1bd9a7992c5e3f4c57f5596a88e5be506917
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-find-a-union-of-two-location-paths-xpath-linq-to-xml-visual-basic"></a>Практическое руководство: поиск объединения двух путей расположения (XPath-LINQ to XML) (Visual Basic)
XPath позволяет найти объединение результатов определения двух путей доступа XPath.  
  
 Выражение XPath:  
  
 `//Category|//Price`  
  
 Те же результаты можно получить с помощью <xref:System.Linq.Enumerable.Concat%2A>стандартного оператора запроса.</xref:System.Linq.Enumerable.Concat%2A>  
  
## <a name="example"></a>Пример  
 В этом примере осуществляется поиск всех элементов `Category` и всех элементов `Price` и объединение их в одну коллекцию. Обратите внимание, что [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] запрос вызывает <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A>для упорядочения результатов.</xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> Эти результаты вычисления выражения XPath также представлены в той же последовательности, что и в документе.  
  
 В этом примере используется следующий XML-документ: [пример XML-файла: числовые данные (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).  
  
```vb  
Dim data As XDocument = XDocument.Load("Data.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = _  
    data...<Category>.Concat(data...<Price>).InDocumentOrder()  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = _  
    data.XPathSelectElements("//Category|//Price")  
  
If list1.Count() = list2.Count() And _  
        list1.Intersect(list2).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
Results are identical  
<Category>A</Category>  
<Price>24.50</Price>  
<Category>B</Category>  
<Price>89.99</Price>  
<Category>A</Category>  
<Price>4.95</Price>  
<Category>A</Category>  
<Price>66.00</Price>  
<Category>B</Category>  
<Price>.99</Price>  
<Category>A</Category>  
<Price>29.00</Price>  
<Category>B</Category>  
<Price>6.99</Price>  
```  
  
## <a name="see-also"></a>См. также  
 [LINQ to XML для пользователей XPath (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

