---
title: Клонирование и присоединение
ms.date: 07/20/2015
ms.assetid: 3c3bd105-c9d3-49bd-875b-27ab4e8bc7a3
ms.openlocfilehash: 22e86ee78d5c3fa0a7b80ae559c39f424fc9d61a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345695"
---
# <a name="cloning-vs-attaching-visual-basic"></a>Клонирование и присоединение (Visual Basic)
При добавлении объекта <xref:System.Xml.Linq.XNode> (включая <xref:System.Xml.Linq.XElement>) или объекта <xref:System.Xml.Linq.XAttribute> в новое дерево, если новое содержимое не имеет родителя, объекты просто добавляются к XML-дереву. Если у нового содержимого уже есть родитель и оно является частью другого XML-дерева, то новое содержимое клонируется. Затем клонированное содержимое присоединяется к XML-дереву.  
  
## <a name="example"></a>Пример  
 Следующий код демонстрирует поведение при добавлении к дереву элемента с родителем и при добавлении к дереву элемента без родителей.  
  
```vb  
' Create a tree with a child element.  
Dim xmlTree1 As XElement = _  
    <Root>  
        <Child1>1</Child1>  
    </Root>  
  
' Create an element that is not parented.  
Dim child2 As XElement = <Child2>2</Child2>  
  
' Create a tree and add Child1 and Child2 to it.  
Dim xmlTree2 As XElement = _  
    <Root>  
        <%= xmlTree1.<Child1>(0) %>  
        <%= child2 %>  
    </Root>  
  
' Compare Child1 identity.  
Console.WriteLine("Child1 was {0}", _  
    IIf(xmlTree1.Element("Child1") Is xmlTree2.Element("Child1"), _  
    "attached", "cloned"))  
  
' Compare Child2 identity.  
Console.WriteLine("Child2 was {0}", _  
    IIf(child2 Is xmlTree2.Element("Child2"), _  
    "attached", "cloned"))  
```  
  
 В этом примере выводятся следующие данные:  
  
```console  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a>См. также

- [Создание деревьев XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
