---
title: "Практическое руководство: извлечение значений элемента (LINQ to XML) (Visual Basic) | Документы Microsoft"
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
ms.assetid: 76b9b2a5-b3ba-49da-ba74-82100e1bd21c
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d38928df51006a8db9417d34ccbe6cd03091db66
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-visual-basic"></a>Практическое руководство: извлечение значений элемента (LINQ to XML) (Visual Basic)
В этом разделе показано получение значений элементов. Это можно сделать двумя основными способами. Один способ состоит в приведении <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XAttribute>в требуемый тип.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> Оператор явного преобразования, который преобразует содержимое элемента или атрибута в указанный тип и присваивает полученное значение указанной переменной. Кроме того, можно использовать <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>свойства или <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>свойство.</xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>  
  
 С помощью Visual Basic лучшим подходом является использование <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>свойство.</xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>  
  
## <a name="example"></a>Пример  
 Чтобы получить значение элемента, нужно просто привести <xref:System.Xml.Linq.XElement>объекта к желаемому типу.</xref:System.Xml.Linq.XElement> Всегда можно привести элемент к строке следующим образом:  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a>Пример  
 Также можно приводить элементы к типам, отличным от строковых. Например, если имеется элемент, содержащий целое число, его можно привести к типу `int`, как показано в следующем коде:  
  
```vb  
Dim e As XElement = <Age>44</Age>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & CInt(e))  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]предоставляет аналогичные операторы приведения для <xref:System.Xml.Linq.XAttribute>объектов.</xref:System.Xml.Linq.XAttribute>  
  
## <a name="example"></a>Пример  
 Можно использовать <xref:System.Xml.Linq.XElement.Value%2A>свойство для извлечения содержимого элемента:</xref:System.Xml.Linq.XElement.Value%2A>  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a>Пример  
 Иногда осуществляются попытки получить значение элемента, в отношении которого неизвестно, существует ли он. В этом случае при назначении элемент привести тип nullable (либо `string` или одного из таких типов в [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]), если элемент не существует, то переменной просто присваивается значение `Nothing`. В следующем коде показано, что если элемент может существовать или не существовать, проще использовать приведение типа, а не использовать <xref:System.Xml.Linq.XElement.Value%2A>свойство.</xref:System.Xml.Linq.XElement.Value%2A>  
  
```vb  
Dim root As XElement = <Root>  
                           <Child1>child 1 content</Child1>  
                           <Child2>2</Child2>  
                       </Root>  
  
' The following assignments show why it is easier to use  
' casting when the element might or might not exist.  
  
Dim c1 As String = CStr(root.Element("Child1"))  
Console.WriteLine("c1:{0}", IIf(c1 Is Nothing, "element does not exist", c1))  
  
Dim c2 As Nullable(Of Integer) = CType(root.Element("Child2"), Nullable(Of Integer))  
Console.WriteLine("c2:{0}", IIf(Not (c2.HasValue), "element does not exist", c2.ToString()))  
  
Dim c3 As String = CStr(root.Element("Child3"))  
Console.WriteLine("c3:{0}", IIf(c3 Is Nothing, "element does not exist", c3))  
  
Dim c4 As Nullable(Of Integer) = CType(root.Element("Child4"), Nullable(Of Integer))  
Console.WriteLine("c4:{0}", IIf(Not (c4.HasValue), "element does not exist", c4.ToString()))  
  
Console.WriteLine()  
  
' The following assignments show the required code when using  
' the Value property when the attribute might or might not exist.  
' Notice that this is more difficult than the casting approach.  
  
Dim e1 As XElement = root.Element("Child1")  
Dim v1 As String  
If (e1 Is Nothing) Then  
    v1 = Nothing  
Else  
    v1 = e1.Value  
End If  
Console.WriteLine("v1:{0}", IIf(v1 Is Nothing, "element does not exist", v1))  
  
Dim e2 As XElement = root.Element("Child2")  
Dim v2 As Nullable(Of Integer)  
If (e2 Is Nothing) Then  
    v2 = Nothing  
Else  
    v2 = e2.Value  
End If  
Console.WriteLine("v2:{0}", IIf(Not (v2.HasValue), "element does not exist", v2))  
  
Dim e3 As XElement = root.Element("Child3")  
Dim v3 As String  
If (e3 Is Nothing) Then  
    v3 = Nothing  
Else  
    v3 = e3.Value  
End If  
Console.WriteLine("v3:{0}", IIf(v3 Is Nothing, "element does not exist", v3))  
  
Dim e4 As XElement = root.Element("Child4")  
Dim v4 As Nullable(Of Integer)  
If (e4 Is Nothing) Then  
    v4 = Nothing  
Else  
    v4 = e4.Value  
End If  
Console.WriteLine("v4:{0}", IIf(Not (v4.HasValue), "element does not exist", v4))  
```  
  
 Этот код выводит следующие результаты:  
  
```  
c1:child 1 content  
c2:2  
c3:element does not exist  
c4:element does not exist  
  
v1:child 1 content  
v2:2  
v3:element does not exist  
v4:element does not exist  
```  
  
 Как правило, использование приведения для получения содержимого элементов и атрибутов позволяет создавать более простой код.  
  
## <a name="see-also"></a>См. также  
 [Оси LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
