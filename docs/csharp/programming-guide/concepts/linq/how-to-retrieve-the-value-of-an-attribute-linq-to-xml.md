---
title: Практическое руководство. Получение значения атрибута (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 817bbe89-5979-4234-bf0c-46f63692ac8c
ms.openlocfilehash: 224ba9ba47d68afd7c29d0f33fe20d290d0b5ef5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33319131"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-c"></a>Практическое руководство. Получение значения атрибута (LINQ to XML) (C#)
В этом разделе показано получение значений атрибутов. Существует два основных способа. Можно привести <xref:System.Xml.Linq.XAttribute> к требуемому типу, после этого оператор явного преобразования преобразует содержимое элемента или атрибута в указанный тип. Иначе можно использовать свойство <xref:System.Xml.Linq.XAttribute.Value%2A>. Однако приведение, как правило, является лучшим подходом. В частности, становится проще написание кода, обеспечивающего получение значения атрибута, который может существовать или не существовать, после приведения атрибута к типу, допускающему значение NULL. Примеры использования этой технологии см. в разделе [Практическое руководство. Извлечение значений элемента (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).  
  
## <a name="example"></a>Пример  
 Для получения значения атрибута нужно просто привести объект <xref:System.Xml.Linq.XAttribute> к желаемому типу.  
  
```csharp  
XElement root = new XElement("Root",  
                    new XAttribute("Attr", "abcde")  
                );  
Console.WriteLine(root);  
string str = (string)root.Attribute("Attr");  
Console.WriteLine(str);  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как получить значение атрибута, если атрибут находится в пространстве имен. Дополнительные сведения см. в разделе [Работа с пространствами имен XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
                    new XAttribute(aw + "Attr", "abcde")  
                );  
string str = (string)root.Attribute(aw + "Attr");  
Console.WriteLine(str);  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
abcde  
```  
  
## <a name="see-also"></a>См. также  
 [Оси LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
