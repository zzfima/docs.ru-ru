---
title: Практическое руководство. Вычисление промежуточных значений (C#)
ms.date: 07/20/2015
ms.assetid: 7fd3001f-f8f9-4bce-879f-d4c7af8a04fe
ms.openlocfilehash: 47b84e7186cf579d9229dc82b12ed621e1f58e2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-calculate-intermediate-values-c"></a>Практическое руководство. Вычисление промежуточных значений (C#)
В этом примере показано, как вычислять промежуточные значения, которые используются в сортировке, фильтрации и выборке.  
  
## <a name="example"></a>Пример  
 В следующем примере используется предложение `Let`.  
  
 В этом примере используется следующий XML-документ: [Пример XML-файла. Числовые данные (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
IEnumerable<decimal> extensions =  
    from el in root.Elements("Data")  
    let extension = (decimal)el.Element("Quantity") * (decimal)el.Element("Price")  
    where extension >= 25  
    orderby extension  
    select extension;  
foreach (decimal ex in extensions)  
    Console.WriteLine(ex);  
```  
  
 Этот код выводит следующие результаты:  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен. Дополнительные сведения см. в разделе [Работа с пространствами имен XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
 В этом примере используется следующий XML-документ: [Пример XML-файла. Числовые данные пространства имен](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).  
  
```csharp  
XElement root = XElement.Load("DataInNamespace.xml");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<decimal> extensions =  
    from el in root.Elements(ad + "Data")  
    let extension = (decimal)el.Element(ad + "Quantity") * (decimal)el.Element(ad + "Price")  
    where extension >= 25  
    orderby extension  
    select extension;  
foreach (decimal ex in extensions)  
    Console.WriteLine(ex);  
```  
  
 Этот код выводит следующие результаты:  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="see-also"></a>См. также  
 [Базовые запросы (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
