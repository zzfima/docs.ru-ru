---
title: Практическое руководство. Извлечение значений элемента (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 76b9b2a5-b3ba-49da-ba74-82100e1bd21c
ms.openlocfilehash: b1a61091dc59b403c5d967609e8870492c24347f
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80248938"
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-visual-basic"></a>Как: Получить значение элемента (LIN' к XML) (Visual Basic)
В этом разделе показано получение значений элементов. Это можно сделать двумя основными способами. Первый способ состоит в приведении <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XAttribute> к желаемому типу. Оператор явного преобразования, который преобразует содержимое элемента или атрибута в указанный тип и присваивает полученное значение указанной переменной. Иначе можно использовать свойство <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> или <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>.  
  
 При использовании Visual Basic лучшим подходом является использование свойства <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>.  
  
## <a name="example"></a>Пример  
 Для получения значения элемента нужно просто привести объект <xref:System.Xml.Linq.XElement> к желаемому типу. Всегда можно привести элемент к строке следующим образом:  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 В примере получается следующий вывод.  
  
```xml  
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
  
 В примере получается следующий вывод.  
  
```xml  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] предусматривает операторы явного приведения для следующих типов данных: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` и `GUID?`.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]предоставляет аналогичные операторы приведения для объектов <xref:System.Xml.Linq.XAttribute>.  
  
## <a name="example"></a>Пример  
 Свойство <xref:System.Xml.Linq.XElement.Value%2A> может использоваться для получения содержимого элемента.  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 В примере получается следующий вывод.  
  
```xml  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a>Пример  
 Иногда осуществляются попытки получить значение элемента, в отношении которого неизвестно, существует ли он. В этом случае при присвоении отлитого элемента `string` необоснованному типу (или одному из недействительных типов значений в рамке .NET) если элемент не существует, назначенная переменная просто установлена `Nothing`на . В следующем коде показано, что при отсутствии сведений о том, существует ли элемент, проще использовать приведение типа, чем свойство <xref:System.Xml.Linq.XElement.Value%2A>.  
  
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
  
```console  
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

- [Оси LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
