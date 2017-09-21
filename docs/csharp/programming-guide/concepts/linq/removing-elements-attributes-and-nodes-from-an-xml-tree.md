---
title: "Удаление элементов, атрибутов и узлов из дерева XML (C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 07dd06d6-1117-4077-bf98-9120cf51176e
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 75642ff3beb4462faa9068db76c89f3cb5f75ab8
ms.openlocfilehash: 40be8959c731746df9392e3cbf29c88fce222b0b
ms.contentlocale: ru-ru
ms.lasthandoff: 08/10/2017

---
# <a name="removing-elements-attributes-and-nodes-from-an-xml-tree-c"></a>Удаление элементов, атрибутов и узлов из дерева XML (C#)
Можно вносить изменения в XML-дерево, удаляя элементы, атрибуты и узлы других типов.  
  
 Удаление одного элемента или атрибута из XML-документа является простой операцией. Но при удалении коллекций элементов или атрибутов необходимо вначале материализовать коллекцию в список, а затем удалить элементы или атрибуты из списка. Наилучшим подходом является использование метода расширения <xref:System.Xml.Linq.Extensions.Remove%2A>, позволяющего выполнить эту задачу.  
  
 Основной причиной этого является то, что большинство коллекций, получаемых из XML-дерева, формируется с помощью отложенного выполнения. Если не проводится их предварительная материализация в список или не используются методы расширения, то становится возможным возникновение определенного класса ошибок. Дополнительные сведения см. в разделе [Ошибки смешанного декларативного и императивного кода (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).  
  
 Следующие методы позволяют удалять узлы и атрибуты из XML-дерева.  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Remove%2A?displayProperty=fullName>|Удаляет <xref:System.Xml.Linq.XAttribute> из его родительского элемента.|  
|<xref:System.Xml.Linq.XContainer.RemoveNodes%2A?displayProperty=fullName>|Удаляет дочерние узлы из <xref:System.Xml.Linq.XContainer>.|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName>|Удаляет содержимое и атрибуты из <xref:System.Xml.Linq.XElement>.|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName>|Удаляет атрибуты <xref:System.Xml.Linq.XElement>.|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName>|Передача `null` в качестве значения приводит к удалению атрибута.|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName>|Передача `null` в качестве значения приводит к удалению дочернего элемента.|  
|<xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=fullName>|Удаляет <xref:System.Xml.Linq.XNode> из его родительского элемента.|  
|<xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=fullName>|Удаляет каждый атрибут или элемент исходной коллекции из своего родительского элемента.|  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В этом примере показано три подхода к удалению элементов. Сначала удаляется одиночный элемент. Затем он возвращает коллекцию элементов, материализует их с помощью оператора <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> и удаляет коллекцию. Наконец, он получает коллекцию элементов и удаляет их с помощью метода расширения <xref:System.Xml.Linq.Extensions.Remove%2A>.  
  
 Дополнительные сведения об операторе <xref:System.Linq.Enumerable.ToList%2A> см. в разделе [Преобразование типов данных (C#)](../../../../csharp/programming-guide/concepts/linq/converting-data-types.md).  
  
### <a name="code"></a>Код  
  
```csharp  
XElement root = XElement.Parse(@"<Root>  
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
</Root>");  
root.Element("Child1").Element("GrandChild1").Remove();  
root.Element("Child2").Elements().ToList().Remove();  
root.Element("Child3").Elements().Remove();  
Console.WriteLine(root);  
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
 [Изменение деревьев XML (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)

