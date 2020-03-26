---
title: Практическое руководство. Извлечение значения атрибута (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 5f4b3790-c83f-4eb3-a889-e3587edf3ca1
ms.openlocfilehash: 6593639dcdc234ddda808cfdb5e85ebe1a771b62
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80248951"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-visual-basic"></a>Как: Получить значение атрибута (LIN' к XML) (Visual Basic)
В этом разделе показано получение значений атрибутов. Существует два основных способа. Можно привести <xref:System.Xml.Linq.XAttribute> к требуемому типу, после этого оператор явного преобразования преобразует содержимое элемента или атрибута в указанный тип. Иначе можно использовать свойство <xref:System.Xml.Linq.XAttribute.Value%2A>. Однако приведение, как правило, является лучшим подходом. Если вы отбрасываете атрибут в необоснованное значение типа, код проще писать при получении значения атрибута, который может или не может существовать. Для примеров этого метода см. [Как: Получить значение элемента (LIN' к XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).  
  
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
 В следующем примере показано, как получить значение атрибута, если атрибут находится в пространстве имен. Для получения дополнительной информации см. Обзор [имен (LIN' к XML) (Visual Basic).](namespaces-overview-linq-to-xml.md)  
  
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
  
 В примере получается следующий вывод.  
  
```console  
abcde  
```  
  
## <a name="see-also"></a>См. также

- [Оси LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
