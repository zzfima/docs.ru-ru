---
title: "Допустимое содержимое XElement и XDocument Objects2 | Документы Microsoft"
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
ms.assetid: 400bb692-478a-40b6-ac1b-4ccbb4cbbd02
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f752ae346167709b95e758d15c1785ba7b6fcc5f
ms.lasthandoff: 03/13/2017

---
# <a name="valid-content-of-xelement-and-xdocument-objects"></a>Допустимое содержимое объектов XElement и XDocument
В этом разделе описываются допустимые аргументы, которые можно передавать конструкторам, а также методы, которые можно использовать для добавления содержимого в элементы и документы.  
  
## <a name="valid-content"></a>Допустимое содержимое  
 Запросы часто иметь <xref:System.Collections.Generic.IEnumerable%601>или <xref:System.Xml.Linq.XElement> <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Можно передавать коллекции объектов <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XAttribute>объектов <xref:System.Xml.Linq.XElement>конструктор.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> Таким образом, передавать результаты запроса методам и конструкторам, используемым для заполнения XML-деревьев, удобно в виде содержимого.  
  
 При добавлении простого содержимого этому методу могут передаваться различные типы. Допустимые типы:  
  
-   <xref:System.String></xref:System.String>  
  
-   <xref:System.Double></xref:System.Double>  
  
-   <xref:System.Single></xref:System.Single>  
  
-   <xref:System.Decimal></xref:System.Decimal>  
  
-   <xref:System.Boolean></xref:System.Boolean>  
  
-   <xref:System.DateTime></xref:System.DateTime>  
  
-   <xref:System.TimeSpan></xref:System.TimeSpan>  
  
-   <xref:System.DateTimeOffset></xref:System.DateTimeOffset>  
  
-   Любой тип, реализующий `Object.ToString`.  
  
-   Любой тип, реализующий <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601>  
  
 При добавлении сложного содержимого этому методу могут передаваться различные типы:  
  
-   <xref:System.Xml.Linq.XObject></xref:System.Xml.Linq.XObject>  
  
-   <xref:System.Xml.Linq.XNode></xref:System.Xml.Linq.XNode>  
  
-   <xref:System.Xml.Linq.XAttribute>  
  
-   Любой тип, реализующий<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>  
  
 Если объект реализует интерфейс <xref:System.Collections.Generic.IEnumerable%601>, коллекция в этом объекте перечисляется и добавляются все элементы в коллекции.</xref:System.Collections.Generic.IEnumerable%601> Если коллекция содержит <xref:System.Xml.Linq.XNode>или <xref:System.Xml.Linq.XAttribute>объектов, каждый элемент в коллекцию добавляется отдельно.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XNode> Если коллекция содержит текст (или объекты, преобразованные в текст), текст в коллекции объединяется и добавляется в виде единого текстового узла.  
  
 Если содержимое имеет значение `null`, ничего не добавляется. При передаче коллекции ее элементы могут иметь значение `null`. Элементы коллекции со значением `null` не влияют на дерево.  
  
 Добавленный атрибут должен иметь уникальное имя внутри содержащего его элемента.  
  
 При добавлении <xref:System.Xml.Linq.XNode>или <xref:System.Xml.Linq.XAttribute>объектов, если новое содержимое не имеет родителя, то объекты просто добавляются к XML-дереву.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XNode> Если же новое содержимое уже имеет родителя и является частью другого XML-дерева, тогда это содержимое клонируется, а вновь созданный клон присоединяется к XML-дереву.  
  
## <a name="valid-content-for-documents"></a>Допустимое содержимое для документов  
 Атрибуты и простое содержимое не могут быть добавлены к документу.  
  
 Не существует множество сценариев, которые требуют создания <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument> Вместо этого обычно имеется возможность создавать XML-деревья с <xref:System.Xml.Linq.XElement>корневого узла.</xref:System.Xml.Linq.XElement> Если отсутствуют конкретные требования для создания документа (например, если необходимо создать инструкции по обработке и комментарии на верхнем уровне или необходимостью поддержки типов документов), часто бывает удобно использовать <xref:System.Xml.Linq.XElement>в качестве корневого узла.</xref:System.Xml.Linq.XElement>  
  
 К допустимому содержимому для документа относится следующее:  
  
-   Ноль или один <xref:System.Xml.Linq.XDocumentType>объектов.</xref:System.Xml.Linq.XDocumentType> Типы документов должны указываться до элемента.  
  
-   Ноль или один элемент.  
  
-   Ноль или более комментариев.  
  
-   Ноль или более инструкций по обработке.  
  
-   Ноль или более текстовых узлов, содержащих только пробел.  
  
## <a name="constructors-and-functions-that-allow-adding-content"></a>Конструкторы и функции, допускающие добавление содержимого  
 Следующие методы позволяют добавлять дочернее содержимое <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XDocument>:</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement>  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.%23ctor%2A></xref:System.Xml.Linq.XElement.%23ctor%2A>|Создает <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement>|  
|<xref:System.Xml.Linq.XDocument.%23ctor%2A></xref:System.Xml.Linq.XDocument.%23ctor%2A>|Создает <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument>|  
|<xref:System.Xml.Linq.XContainer.Add%2A></xref:System.Xml.Linq.XContainer.Add%2A>|Добавляет к концу дочернего содержимого <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement>|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A></xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|Добавляет содержимое после <xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode>|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|Добавляет содержимое перед <xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode>|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A></xref:System.Xml.Linq.XContainer.AddFirst%2A>|Добавляет содержимое в начале дочернего содержимого <xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A></xref:System.Xml.Linq.XElement.ReplaceAll%2A>|Заменяет все содержимое (дочерние узлы и атрибуты) <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A></xref:System.Xml.Linq.XElement.ReplaceAttributes%2A>|Заменяет атрибуты <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement>|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A></xref:System.Xml.Linq.XContainer.ReplaceNodes%2A>|Заменяет дочерние узлы новым содержимым.|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A></xref:System.Xml.Linq.XNode.ReplaceWith%2A>|Заменяет узел новым содержимым.|  
  
## <a name="see-also"></a>См. также  
 [Создание деревьев XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
