---
title: Добавление элементов, атрибутов и узлов в дерево XML (Visual Basic)
ms.date: 07/20/2015
ms.assetid: e243e694-c987-43aa-8b22-1e33dace582c
ms.openlocfilehash: 35d3bdb27342dd7a871778ad4749db4d6849bd60
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62021860"
---
# <a name="adding-elements-attributes-and-nodes-to-an-xml-tree-visual-basic"></a>Добавление элементов, атрибутов и узлов в дерево XML (Visual Basic)
Можно добавлять содержимое (элементы, атрибуты, комментарии, инструкции по обработке, текст и CDATA) к существующему XML-дереву.  
  
## <a name="methods-for-adding-content"></a>Методы добавления содержимого  
 Следующие методы позволяют добавить дочернее содержимое к <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument>.  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|Добавляет содержимое в конце дочернего содержимого <xref:System.Xml.Linq.XContainer>.|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|Добавляет содержимое в начале дочернего содержимого <xref:System.Xml.Linq.XContainer>.|  
  
 Следующие методы позволяют добавлять содержимое как одноуровневые узлы для <xref:System.Xml.Linq.XNode>. Самым распространенным узлом, к которому можно добавлять содержимое как одноуровневые узлы, является <xref:System.Xml.Linq.XElement>, хотя можно добавлять содержимое в виде таких узлов и к другим типам узлов, например <xref:System.Xml.Linq.XText> или <xref:System.Xml.Linq.XComment>.  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|Добавляет содержимое после <xref:System.Xml.Linq.XNode>.|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|Добавляет содержимое перед <xref:System.Xml.Linq.XNode>.|  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере создаются два XML-дерева, затем выполняется изменение одного из них.  
  
### <a name="code"></a>Код  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element1>1</Element1>  
        <Element2>2</Element2>  
        <Element3>3</Element3>  
        <Element4>4</Element4>  
        <Element5>5</Element5>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child1>1</Child1>  
        <Child2>2</Child2>  
        <Child3>3</Child3>  
        <Child4>4</Child4>  
        <Child5>5</Child5>  
    </Root>  
  
xmlTree.Add(<NewChild>new content</NewChild>)  
xmlTree.Add( _  
    From el In srcTree.Elements() _  
    Where CInt(el) > 3 _  
    Select el)  
  
' Even though Child9 does not exist in srcTree, the following statement  
' will not throw an exception, and nothing will be added to xmlTree.  
xmlTree.Add(srcTree.Element("Child9"))  
Console.WriteLine(xmlTree)  
```  
  
### <a name="comments"></a>Комментарии  
 Этот код выводит следующие результаты:  
  
```xml  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
  <Child4>4</Child4>  
  <Child5>5</Child5>  
  <NewChild>new content</NewChild>  
  <Element4>4</Element4>  
  <Element5>5</Element5>  
</Root>  
```  
  
## <a name="see-also"></a>См. также

- [Изменение деревьев XML (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
