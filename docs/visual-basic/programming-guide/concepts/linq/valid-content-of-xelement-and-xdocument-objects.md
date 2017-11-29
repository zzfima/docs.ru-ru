---
title: "Допустимое содержимое XElement и XDocument Objects2"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 400bb692-478a-40b6-ac1b-4ccbb4cbbd02
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5093ef1c2974bcb980d97d4839af35bb69044a90
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="valid-content-of-xelement-and-xdocument-objects"></a>Допустимое содержимое объектов XElement и XDocument
В этом разделе описываются допустимые аргументы, которые можно передавать конструкторам, а также методы, которые можно использовать для добавления содержимого в элементы и документы.  
  
## <a name="valid-content"></a>Допустимое содержимое  
 Возвращаемые запросами данные часто выражаются с помощью коллекций <xref:System.Collections.Generic.IEnumerable%601> элементов <xref:System.Xml.Linq.XElement> или с помощью коллекций <xref:System.Collections.Generic.IEnumerable%601> атрибутов <xref:System.Xml.Linq.XAttribute>. Можно передавать коллекции объектов <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XAttribute> в конструктор <xref:System.Xml.Linq.XElement>. Таким образом, передавать результаты запроса методам и конструкторам, используемым для заполнения XML-деревьев, удобно в виде содержимого.  
  
 При добавлении простого содержимого этому методу могут передаваться различные типы. Допустимые типы:  
  
-   <xref:System.String>  
  
-   <xref:System.Double>  
  
-   <xref:System.Single>  
  
-   <xref:System.Decimal>  
  
-   <xref:System.Boolean>  
  
-   <xref:System.DateTime>  
  
-   <xref:System.TimeSpan>  
  
-   <xref:System.DateTimeOffset>  
  
-   Любой тип, реализующий `Object.ToString`.  
  
-   Любой тип, реализующий <xref:System.Collections.Generic.IEnumerable%601>.  
  
 При добавлении сложного содержимого этому методу могут передаваться различные типы:  
  
-   <xref:System.Xml.Linq.XObject>  
  
-   <xref:System.Xml.Linq.XNode>  
  
-   <xref:System.Xml.Linq.XAttribute>  
  
-   Любой тип, реализующий <xref:System.Collections.Generic.IEnumerable%601>  
  
 Если объект реализует интерфейс <xref:System.Collections.Generic.IEnumerable%601>, коллекция в этом объекте перечисляется и добавляются все элементы коллекции. Если коллекция содержит объекты <xref:System.Xml.Linq.XNode> или <xref:System.Xml.Linq.XAttribute>, каждый ее элемент добавляется отдельно. Если коллекция содержит текст (или объекты, преобразованные в текст), текст в коллекции объединяется и добавляется в виде единого текстового узла.  
  
 Если содержимое имеет значение `null`, ничего не добавляется. При передаче коллекции ее элементы могут иметь значение `null`. Элементы коллекции со значением `null` не влияют на дерево.  
  
 Добавленный атрибут должен иметь уникальное имя внутри содержащего его элемента.  
  
 Если при добавлении объектов <xref:System.Xml.Linq.XNode> или <xref:System.Xml.Linq.XAttribute> новое содержимое не имеет родителя, то эти объекты просто добавляются к XML-дереву. Если же новое содержимое уже имеет родителя и является частью другого XML-дерева, тогда это содержимое клонируется, а вновь созданный клон присоединяется к XML-дереву.  
  
## <a name="valid-content-for-documents"></a>Допустимое содержимое для документов  
 Атрибуты и простое содержимое не могут быть добавлены к документу.  
  
 Ситуации, когда необходимо создавать документ <xref:System.Xml.Linq.XDocument>, встречаются нечасто. Вместо этого обычно имеется возможность создавать XML-деревья с корневым узлом <xref:System.Xml.Linq.XElement>. Если отсутствуют конкретные требования по созданию документа (вызванные, например, необходимостью создания инструкций по обработке и комментариев на верхнем уровне или необходимостью поддержки типов документов), часто бывает удобнее всего в качестве корневого узла использовать <xref:System.Xml.Linq.XElement>.  
  
 К допустимому содержимому для документа относится следующее:  
  
-   Ноль или один объект <xref:System.Xml.Linq.XDocumentType>. Типы документов должны указываться до элемента.  
  
-   Ноль или один элемент.  
  
-   Ноль или более комментариев.  
  
-   Ноль или более инструкций по обработке.  
  
-   Ноль или более текстовых узлов, содержащих только пробел.  
  
## <a name="constructors-and-functions-that-allow-adding-content"></a>Конструкторы и функции, допускающие добавление содержимого  
 Следующие методы позволяют добавлять дочернее содержимое к элементу <xref:System.Xml.Linq.XElement> или к документу <xref:System.Xml.Linq.XDocument>.  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.%23ctor%2A>|Создает элемент <xref:System.Xml.Linq.XElement>.|  
|<xref:System.Xml.Linq.XDocument.%23ctor%2A>|Создает документ <xref:System.Xml.Linq.XDocument>.|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|Добавляет к концу дочернего содержимого элемента <xref:System.Xml.Linq.XElement> или документа <xref:System.Xml.Linq.XDocument>.|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|Добавляет содержимое после <xref:System.Xml.Linq.XNode>.|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|Добавляет содержимое перед <xref:System.Xml.Linq.XNode>.|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|Добавляет содержимое в начале дочернего содержимого <xref:System.Xml.Linq.XContainer>.|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A>|Заменяет все содержимое (дочерние узлы и атрибуты) элемента <xref:System.Xml.Linq.XElement>.|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A>|Заменяет атрибуты элемента <xref:System.Xml.Linq.XElement>.|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A>|Заменяет дочерние узлы новым содержимым.|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A>|Заменяет узел новым содержимым.|  
  
## <a name="see-also"></a>См. также  
 [Создание деревьев XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
