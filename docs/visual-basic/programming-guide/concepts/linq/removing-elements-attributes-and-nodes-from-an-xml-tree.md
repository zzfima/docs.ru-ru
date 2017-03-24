---
title: "Удаление элементов, атрибутов и узлов из XML-дерева (Visual Basic) | Документы Microsoft"
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
ms.assetid: 5cf21919-4360-4b49-b29d-58ea3164ac72
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: eef13476733f7c883080923614683a41d7cb3b3a
ms.lasthandoff: 03/13/2017


---
# <a name="removing-elements-attributes-and-nodes-from-an-xml-tree-visual-basic"></a>Удаление элементов, атрибутов и узлов из XML-дерева (Visual Basic)
Можно вносить изменения в XML-дерево, удаляя элементы, атрибуты и узлы других типов.  
  
 Удаление одного элемента или атрибута из XML-документа является простой операцией. Но при удалении коллекций элементов или атрибутов необходимо вначале материализовать коллекцию в список, а затем удалить элементы или атрибуты из списка. Лучше всего использовать <xref:System.Xml.Linq.Extensions.Remove%2A>метод расширения, который сделает это за вас.</xref:System.Xml.Linq.Extensions.Remove%2A>  
  
 Основной причиной этого является то, что большинство коллекций, получаемых из XML-дерева, формируется с помощью отложенного выполнения. Если не проводится их предварительная материализация в список или не используются методы расширения, то становится возможным возникновение определенного класса ошибок. Дополнительные сведения см. в разделе [смешанного декларативного и императивного ошибки в коде (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).  
  
 Следующие методы позволяют удалять узлы и атрибуты из XML-дерева.  
  
|Метод|Описание|  
|------------|-----------------|  
|[XAttribute.Remove](https://msdn.microsoft.com/library/system.xml.linq.xattribute.remove\(v=vs.110\).aspx)|Удаляет <xref:System.Xml.Linq.XAttribute>от родительского.</xref:System.Xml.Linq.XAttribute>|  
|[XContainer.RemoveNodes](https://msdn.microsoft.com/library/system.xml.linq.xcontainer.removenodes\(v=vs.110\).aspx)|Удаляет дочерние узлы из <xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName>|Удаляет содержимое и атрибуты из <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName>|Удаляет атрибуты <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName>|Передача `null` в качестве значения приводит к удалению атрибута.|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName>|Передача `null` в качестве значения приводит к удалению дочернего элемента.|  
|<xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=fullName>|Удаляет <xref:System.Xml.Linq.XNode>от родительского.</xref:System.Xml.Linq.XNode>|  
|<xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=fullName></xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=fullName>|Удаляет каждый атрибут или элемент исходной коллекции из своего родительского элемента.|  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В этом примере показано три подхода к удалению элементов. Сначала удаляется одиночный элемент. Во-вторых, он возвращает коллекцию элементов, материализует их с помощью <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>оператор и удаляет коллекцию.</xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> Наконец, он возвращает коллекцию элементов и удаляет их с помощью <xref:System.Xml.Linq.Extensions.Remove%2A>метода расширения.</xref:System.Xml.Linq.Extensions.Remove%2A>  
  
 Дополнительные сведения о <xref:System.Linq.Enumerable.ToList%2A>оператор, в разделе [преобразование типов данных (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).</xref:System.Linq.Enumerable.ToList%2A>  
  
### <a name="code"></a>Код  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>  
            <GrandChild1/>  
            <GrandChild2/>  
            <GrandChild3/>  
        </Child1>  
        <Child2>  
            <GrandChild4/>  
            <GrandChild5/>  
            <GrandChild6/>  
        </Child2>  
        <Child3>  
            <GrandChild7/>  
            <GrandChild8/>  
            <GrandChild9/>  
        </Child3>  
    </Root>  
root.<Child1>.<GrandChild1>.Remove()  
root.<Child2>.Elements().ToList().Remove()  
root.<Child3>.Elements().Remove()  
Console.WriteLine(root)  
  
```  
  
### <a name="comments"></a>Комментарии  
 Этот код выводит следующие результаты:  
  
```xml  
<Root>  
  <Child1>  
    <GrandChild2 />  
    <GrandChild3 />  
  </Child1>  
  <Child2 />  
  <Child3 />  
</Root>  
```  
  
 Обратите внимание, что первый внучатый элемент был удален из `Child1`. Все внучатые элементы были удалены из `Child2` и `Child3`.  
  
## <a name="see-also"></a>См. также  
 [Изменение деревьев XML (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
