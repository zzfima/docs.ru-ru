---
title: Извлечение значений элемента (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 4228c007-07c9-4cf2-a45b-e7074c109581
ms.openlocfilehash: 17a7dac464e1ec40db357194000f5745cdf2f3a8
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249211"
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-c"></a>Извлечение значений элемента (LINQ to XML) (C#)
В этом разделе показано получение значений элементов. Это можно сделать двумя основными способами. Первый способ состоит в приведении <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XAttribute> к желаемому типу. Оператор явного преобразования, который преобразует содержимое элемента или атрибута в указанный тип и присваивает полученное значение указанной переменной. Иначе можно использовать свойство <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> или <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>.  
  
 Однако при использовании C# приведение, как правило, является лучшим подходом. В частности, упрощается написание кода, обеспечивающего получение значения элемента или атрибута, который может существовать или не существовать, после приведения элемента (или атрибута) к типу значения, допускающему значение NULL. Это демонстрирует последний пример из данного раздела. Однако нельзя так задать содержимое элемента через приведение, как через свойство <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>.  
  
## <a name="example"></a>Пример  
 Для получения значения элемента нужно просто привести объект <xref:System.Xml.Linq.XElement> к желаемому типу. Всегда можно привести элемент к строке следующим образом:  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (string)e);  
```  
  
 В этом примере выводятся следующие данные:  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a>Пример  
 Также можно приводить элементы к типам, отличным от строковых. Например, если имеется элемент, содержащий целое число, его можно привести к типу `int`, как показано в следующем коде:  
  
```csharp  
XElement e = new XElement("Age", "44");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (int)e);  
```  
  
 В этом примере выводятся следующие данные:  
  
```output  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] предусматривает операторы явного приведения для следующих типов данных: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` и `GUID?`.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]предоставляет аналогичные операторы приведения для объектов <xref:System.Xml.Linq.XAttribute>.  
  
## <a name="example"></a>Пример  
 Свойство <xref:System.Xml.Linq.XElement.Value%2A> может использоваться для получения содержимого элемента.  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + e.Value);  
```  
  
 В этом примере выводятся следующие данные:  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a>Пример  
 Иногда осуществляются попытки получить значение элемента, в отношении которого неизвестно, существует ли он. В этом случае назначение типа значения или ссылочного типа, допускающих значение NULL, для приведенного элемента приводит к тому, что если элемент не существует, то переменной просто присваивается значение `null`. В следующем коде показано, что при отсутствии сведений о том, существует ли элемент, проще использовать приведение типа, чем свойство <xref:System.Xml.Linq.XElement.Value%2A>.  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", "child 1 content"),  
    new XElement("Child2", "2")  
);  
  
// The following assignments show why it is easier to use  
// casting when the element might or might not exist.  
  
string c1 = (string)root.Element("Child1");  
Console.WriteLine("c1:{0}", c1 == null ? "element does not exist" : c1);  
  
int? c2 = (int?)root.Element("Child2");  
Console.WriteLine("c2:{0}", c2 == null ? "element does not exist" : c2.ToString());  
  
string c3 = (string)root.Element("Child3");  
Console.WriteLine("c3:{0}", c3 == null ? "element does not exist" : c3);  
  
int? c4 = (int?)root.Element("Child4");  
Console.WriteLine("c4:{0}", c4 == null ? "element does not exist" : c4.ToString());  
  
Console.WriteLine();  
  
// The following assignments show the required code when using  
// the Value property when the element might or might not exist.  
// Notice that this is more difficult than the casting approach.  
  
XElement e1 = root.Element("Child1");  
string v1;  
if (e1 == null)  
    v1 = null;  
else  
    v1 = e1.Value;  
Console.WriteLine("v1:{0}", v1 == null ? "element does not exist" : v1);  
  
XElement e2 = root.Element("Child2");  
int? v2;  
if (e2 == null)  
    v2 = null;  
else  
    v2 = Int32.Parse(e2.Value);  
Console.WriteLine("v2:{0}", v2 == null ? "element does not exist" : v2.ToString());  
  
XElement e3 = root.Element("Child3");  
string v3;  
if (e3 == null)  
    v3 = null;  
else  
    v3 = e3.Value;  
Console.WriteLine("v3:{0}", v3 == null ? "element does not exist" : v3);  
  
XElement e4 = root.Element("Child4");  
int? v4;  
if (e4 == null)  
    v4 = null;  
else  
    v4 = Int32.Parse(e4.Value);  
Console.WriteLine("v4:{0}", v4 == null ? "element does not exist" : v4.ToString());  
```  
  
 Этот код выводит следующие результаты:  
  
```output  
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

- [Оси LINQ to XML (C#)](./linq-to-xml-axes-overview.md)
