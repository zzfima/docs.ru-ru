---
title: 'Как: извлечение значений атрибута (LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 5f4b3790-c83f-4eb3-a889-e3587edf3ca1
ms.openlocfilehash: 96d5e5a0c7ee294b140385c93b13ee56f3f92491
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-visual-basic"></a>Как: извлечение значений атрибута (LINQ to XML) (Visual Basic)
В этом разделе показано получение значений атрибутов. Существует два основных способа. Можно привести <xref:System.Xml.Linq.XAttribute> к требуемому типу, после этого оператор явного преобразования преобразует содержимое элемента или атрибута в указанный тип. Иначе можно использовать свойство <xref:System.Xml.Linq.XAttribute.Value%2A>. Однако приведение, как правило, является лучшим подходом. В частности, становится проще написание кода, обеспечивающего получение значения атрибута, который может существовать или не существовать, после приведения атрибута к типу, допускающему значение NULL. Примеры этой методики см. в разделе [как: извлечение значения элемента (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).  
  
## <a name="example"></a>Пример  
 В Visual Basic для получения значения атрибута можно использовать встроенное свойство атрибута.  
  
```vb  
Dim root As XElement = <Root Attr="abcde"/>  
Console.WriteLine(root)  
Dim str As String = root.@Attr  
Console.WriteLine(str)  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a>Пример  
 В Visual Basic для установки значения атрибута можно использовать встроенное свойство атрибута. Далее в случае использования встроенного свойства атрибута для установки значения несуществующего атрибута этот атрибут будет создан.  
  
```vb  
Dim root As XElement = <Root Att1="content"/>  
root.@Att1 = "new content"  
root.@Att2 = "new attribute"  
Console.WriteLine(root)  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<Root Att1="new content" Att2="new attribute" />  
```  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как получить значение атрибута, если атрибут находится в пространстве имен. Дополнительные сведения см. в разделе [работа с пространствами имен XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root aw:Attr="abcde"/>  
        Dim str As String = root.@aw:Attr  
        Console.WriteLine(str)  
    End Sub  
End Module  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
abcde  
```  
  
## <a name="see-also"></a>См. также  
 [Оси LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
