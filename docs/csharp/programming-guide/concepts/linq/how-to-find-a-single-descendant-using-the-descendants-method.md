---
title: Практическое руководство. Поиск одного потомка с помощью метода потомков (C#)
ms.date: 07/20/2015
ms.assetid: 6f735be9-0293-4680-8007-ca9d96bfebed
ms.openlocfilehash: e08e07e0d32146a14b90b9d6463e6e58a233a923
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33316963"
---
# <a name="how-to-find-a-single-descendant-using-the-descendants-method-c"></a>Практическое руководство. Поиск одного потомка с помощью метода потомков (C#)
Метод оси <xref:System.Xml.Linq.XContainer.Descendants%2A> можно использовать для быстрого написания кода с целью поиска одного уникально именованного элемента. Этот способ особенно полезен, если нужно найти конкретного потомка с заданным именем. Можно написать собственный код для перехода к нужному элементу, но часто быстрей и легче написать такой код с помощью оси <xref:System.Xml.Linq.XContainer.Descendants%2A>.  
  
## <a name="example"></a>Пример  
 В этом примере используется стандартный оператор запроса <xref:System.Linq.Enumerable.First%2A>.  
  
```csharp  
XElement root = XElement.Parse(@"<Root>  
  <Child1>  
    <GrandChild1>GC1 Value</GrandChild1>  
  </Child1>  
  <Child2>  
    <GrandChild2>GC2 Value</GrandChild2>  
  </Child2>  
  <Child3>  
    <GrandChild3>GC3 Value</GrandChild3>  
  </Child3>  
  <Child4>  
    <GrandChild4>GC4 Value</GrandChild4>  
  </Child4>  
</Root>");  
string grandChild3 = (string)  
    (from el in root.Descendants("GrandChild3")  
    select el).First();  
Console.WriteLine(grandChild3);  
```  
  
 Этот код выводит следующие результаты:  
  
```  
GC3 Value  
```  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен. Дополнительные сведения см. в разделе [Работа с пространствами имен XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
```csharp  
XElement root = XElement.Parse(@"<aw:Root xmlns:aw='http://www.adventure-works.com'>  
  <aw:Child1>  
    <aw:GrandChild1>GC1 Value</aw:GrandChild1>  
  </aw:Child1>  
  <aw:Child2>  
    <aw:GrandChild2>GC2 Value</aw:GrandChild2>  
  </aw:Child2>  
  <aw:Child3>  
    <aw:GrandChild3>GC3 Value</aw:GrandChild3>  
  </aw:Child3>  
  <aw:Child4>  
    <aw:GrandChild4>GC4 Value</aw:GrandChild4>  
  </aw:Child4>  
</aw:Root>");  
XNamespace aw = "http://www.adventure-works.com";  
string grandChild3 = (string)  
    (from el in root.Descendants(aw + "GrandChild3")  
     select el).First();  
Console.WriteLine(grandChild3);  
```  
  
 Этот код выводит следующие результаты:  
  
```  
GC3 Value  
```  
  
## <a name="see-also"></a>См. также  
 [Базовые запросы (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
