---
title: Предварительная атомизация объектов XName (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 06ea104b-f44c-4bb2-9c34-889ae025c80d
ms.openlocfilehash: c0e75afa797d2b20f32fc55e6c19d0c1593d174c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740792"
---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-visual-basic"></a>Предварительное разъединение объектов XName (LINQ to XML) (Visual Basic)

Одним из способов повышения производительности в LINQ to XML является предварительная атомизация объектов <xref:System.Xml.Linq.XName>. Перед созданием XML-дерева с помощью конструкторов классов <xref:System.Xml.Linq.XElement> и <xref:System.Xml.Linq.XAttribute> необходимо назначить строку объекту <xref:System.Xml.Linq.XName>. Затем, вместо того чтобы передавать строку в конструктор, где будет выполнено ее неявное преобразование в объект <xref:System.Xml.Linq.XName>, можно передать инициализированный объект <xref:System.Xml.Linq.XName>.

Таким способом можно повысить производительность при создании большого XML-дерева с рядом повторяющихся имен. Для этого перед построением XML-дерева необходимо объявить и инициализировать объекты <xref:System.Xml.Linq.XName>, а затем в качестве имен элементов и атрибутов указать эти объекты <xref:System.Xml.Linq.XName> вместо строк. Эта техника может дать существенный рост производительности, когда создается большое количество элементов (или атрибутов) с одним и тем же именем.

Чтобы принять решение об использовании предварительной атомизации, протестируйте этот прием в вашем конкретном случае.

## <a name="example"></a>Пример

Следующий пример демонстрирует это:

```vb
Dim root1 As XName = "Root"
Dim data As XName = "Data"
Dim id As XName = "ID"

Dim root2 As New XElement(root1, New XElement(data, New XAttribute(id, "1"), "4,100,000"),
                          New XElement(data, New XAttribute(id, "2"), "3,700,000"),
                          New XElement(data, New XAttribute(id, "3"), "1,150,000"))

Console.WriteLine(root2)
```

В примере получается следующий вывод.

```xml
<Root>
  <Data ID="1">4,100,000</Data>
  <Data ID="2">3,700,000</Data>
  <Data ID="3">1,150,000</Data>
</Root>
```

Следующий пример демонстрирует ту же технику, когда XML-документ находится в пространстве имен.

```vb
Dim aw As XNamespace = "http://www.adventure-works.com"
Dim root1 As XName = aw + "Root"
Dim data As XName = aw + "Data"
Dim id As XName = "ID"

Dim root2 As New XElement(root1, New XAttribute(XNamespace.Xmlns + "aw", aw),
                          New XElement(data, New XAttribute(id, "1"), "4,100,000"),
                          New XElement(data, New XAttribute(id, "2"), "3,700,000"),
                          New XElement(data, New XAttribute(id, "3"), "1,150,000"))

Console.WriteLine(root2)
```

В примере получается следующий вывод.

```xml
<aw:Root xmlns:aw="http://www.adventure-works.com">
  <aw:Data ID="1">4,100,000</aw:Data>
  <aw:Data ID="2">3,700,000</aw:Data>
  <aw:Data ID="3">1,150,000</aw:Data>
</aw:Root>
```

Следующий пример наиболее приближен к реальной ситуации. В этом примере содержимое элементов предоставляется запросом.

```vb
Dim root1 As XName = "Root"
Dim data As XName = "Data"
Dim id As XName = "ID"
  
Dim sw As Stopwatch = Stopwatch.StartNew()
Dim root2 As New XElement(root1, From i In Enumerable.Range(1, 100000)
                                 Select New XElement(data, New XAttribute(ID, i), i * 5))
sw.Stop()
Console.WriteLine($"Time to construct: {sw.ElapsedMilliseconds} milliseconds")
```  

Производительность кода в предыдущем примере выше, чем в следующем, где не выполняется предварительная атомизация имен.

```vb
Dim sw As Stopwatch = Stopwatch.StartNew()
Dim root As New XElement("Root", From i In Enumerable.Range(1, 100000)
                                 Select New XElement("Data", New XAttribute("ID", i), i * 5))
sw.Stop()
Console.WriteLine($"Time to construct: {sw.ElapsedMilliseconds} milliseconds")
```

## <a name="see-also"></a>См. также раздел

- [Производительность (LINQ to XML) (Visual Basic)](performance-linq-to-xml.md)
- [Атомарные объекты XName и XNamespace (LINQ to XML) (Visual Basic)](atomized-xname-and-xnamespace-objects-linq-to-xml.md)
