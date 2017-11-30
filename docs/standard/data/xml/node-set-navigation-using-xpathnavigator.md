---
title: "Навигация в наборе узлов с помощью XPathNavigator"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a954b41-7173-40bc-8544-d430f209b1e5
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9ac0135227599d6a72813bcf57b209705545da66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="node-set-navigation-using-xpathnavigator"></a>Навигация в наборе узлов с помощью XPathNavigator
Навигацию по узлам в объекте <xref:System.Xml.XPath.XPathDocument> или <xref:System.Xml.XmlDocument> обеспечивают методы просмотра набора узлов класса <xref:System.Xml.XPath.XPathNavigator>. Возможен просмотр всех узлов или набора выбранных узлов, возвращаемого одним из методов выбора класса <xref:System.Xml.XPath.XPathNavigator>.  
  
## <a name="element-node-set-navigation"></a>Навигация в наборе узлов элементов  
 В классе <xref:System.Xml.XPath.XPathNavigator> предусмотрено несколько методов, используемых для навигации по узлам элементов. В следующей таблице показаны доступные методы навигации и описания способов перемещения. В таблицу не включены методы, применяемые для навигации по узлам атрибутов и пространств имен.  
  
 Дополнительные сведения о выборе узлов в <xref:System.Xml.XPath.XPathNavigator> см. в разделе [выбор, вычисление и отбор XML-данных с помощью класса XPathNavigator](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md). Дополнительные сведения о навигации по узлам атрибутов и пространств имен см. в разделе [атрибутов и пространство имен узла навигации с помощью XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md).  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>|Перемещает объект <xref:System.Xml.XPath.XPathNavigator> в положение указанного объекта <xref:System.Xml.XPath.XPathNavigator>.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>|Перемещает объект <xref:System.Xml.XPath.XPathNavigator> в дочерний узел текущего узла.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>|Перемещает объект <xref:System.Xml.XPath.XPathNavigator> в первый узел одного уровня с текущим узлом.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>|Перемещает объект <xref:System.Xml.XPath.XPathNavigator> в первый дочерний узел текущего узла.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFollowing%2A>|Перемещает объект <xref:System.Xml.XPath.XPathNavigator> в указанный элемент в порядке следования документов.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>|Перемещает объект <xref:System.Xml.XPath.XPathNavigator> в узел, имеющий атрибут типа `ID` со значением, которое совпадает с данным значением <xref:System.String>.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A>|Перемещает объект <xref:System.Xml.XPath.XPathNavigator> в следующий узел одного уровня с текущим узлом.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A>|Перемещает объект <xref:System.Xml.XPath.XPathNavigator> в родительский узел текущего узла.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A>|Перемещает объект <xref:System.Xml.XPath.XPathNavigator> в предыдущий узел одного уровня с текущим узлом.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToRoot%2A>|Перемещает объект <xref:System.Xml.XPath.XPathNavigator> в корневой узел XML-документа.|  
  
## <a name="comments-and-processing-instruction-node-navigation"></a>Навигация по узлам комментариев и инструкций по обработке  
 Следующие методы класса <xref:System.Xml.XPath.XPathNavigator> допустимы для перемещения комментариев и инструкций по обработке из других узлов в XML-документ.  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [Обработка XML-данных с использованием модели данных XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [Атрибут и навигации узла пространства имен с помощью XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)  
 [Извлечение XML-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/extract-xml-data-using-xpathnavigator.md)  
 [Доступ к строго типизированным XML-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
