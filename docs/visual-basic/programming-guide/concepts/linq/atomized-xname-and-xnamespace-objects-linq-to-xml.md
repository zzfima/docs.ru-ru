---
title: Атомарные объекты XName и XNamespace (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 21ee7585-7df9-40b4-8c76-a12bb5f29bb3
ms.openlocfilehash: 0ffed5d00364f6614b439480607ed521f52754ec
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345731"
---
# <a name="atomized-xname-and-xnamespace-objects-linq-to-xml-visual-basic"></a>Atomized XName and XNamespace Objects (LINQ to XML) (Visual Basic)

Объекты <xref:System.Xml.Linq.XName> и <xref:System.Xml.Linq.XNamespace> являются *атомарными*; иными словами, если они имеют идентичное полное имя, они ссылаются на один и тот же объект. Это способствует повышению производительности при выполнении запросов: при сравнении двух атомарных имен для проверки их равенства соответствующий промежуточный язык должен определить, ссылаются ли они на один и тот же объект. Эта операция используется в промежуточном коде вместо более длительной операции сравнения строк.

## <a name="atomization-semantics"></a>Семантика атомизации

Атомизация означает, что два объекта <xref:System.Xml.Linq.XName> имеющие идентичное локальное имя и находящиеся в одном пространстве имен, совместно используют один и тот же экземпляр. Аналогично, если два объекта <xref:System.Xml.Linq.XNamespace> имеют идентичный идентификатор URI пространства имен, то они совместно используют один и тот же экземпляр.

Чтобы разрешить создание атомарных объектов класса, необходимо, чтобы конструктор класса был закрытым, а не открытым. Это требование основано на том, что если бы конструктор был открытым, можно было бы создавать неатомарные объекты. Классы <xref:System.Xml.Linq.XName> и <xref:System.Xml.Linq.XNamespace> реализуют неявный оператор преобразования строки в объект <xref:System.Xml.Linq.XName> или <xref:System.Xml.Linq.XNamespace>. Экземпляры этих объектов могут быть получены только таким способом. Создание экземпляров с помощью конструктора невозможно, так как конструктор недоступен.

Классы <xref:System.Xml.Linq.XName> и<xref:System.Xml.Linq.XNamespace> также реализуют операторы для проверки равенства и неравенства, определяющие, ссылаются ли два сравниваемых объекта на один и тот же экземпляр.

## <a name="example"></a>Пример

Следующий код создает объекты <xref:System.Xml.Linq.XElement> и демонстрирует, что идентичные имена совместно используют один и тот же экземпляр.

```vb
Dim r1 As New XElement("Root", "data1")
Dim r2 As XElement = XElement.Parse("<Root>data2</Root>")

If DirectCast(r1.Name, Object) = DirectCast(r2.Name, Object) Then
    Console.WriteLine("r1 and r2 have names that refer to the same instance.")
Else
    Console.WriteLine("Different")
End If

Dim n As XName = "Root"

If DirectCast(n, Object) = DirectCast(r1.Name, Object) Then
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.")
Else
    Console.WriteLine("Different")
End If
```

В этом примере выводятся следующие данные:

```console
r1 and r2 have names that refer to the same instance.
The name of r1 and the name in 'n' refer to the same instance.
```

Как отмечалось выше, преимущество атомарных объектов заключается в том, что при использовании одного из методов оси, принимающих в качестве параметра <xref:System.Xml.Linq.XName>, этому методу оси для выбора необходимых элементов достаточно определить, что два имени совместно используют один и тот же экземпляр.

В следующем примере объект <xref:System.Xml.Linq.XName> передается при вызове метода <xref:System.Xml.Linq.XContainer.Descendants%2A>, производительность которого выше за счет использования атомизации.

```vb
Dim root As New XElement("Root", New XElement("C1", 1), New XElement("Z1", New XElement("C1", 2), New XElement("C1", 1)))

Dim query = From e In root.Descendants("C1") Where CInt(e) = 1e

For Each z As var In query
    Console.WriteLine(z)
Next
```

В этом примере выводятся следующие данные:

```xml
<C1>1</C1>
<C1>1</C1>
```

## <a name="see-also"></a>См. также

- [Performance (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)
