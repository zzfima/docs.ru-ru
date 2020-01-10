---
title: Типы узлов, распознаваемые запросами XPath
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1d33e22d-18e5-43f8-a466-2e3d0a8dd094
ms.openlocfilehash: cc1aa668ccf6fc7f210f48a28cf76b364459c784
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710548"
---
# <a name="node-types-recognized-with-xpath-queries"></a>Типы узлов, распознаваемые запросами XPath
Типы узлов, распознаваемые в запросе XPath, отличаются от типов узлов в модели DOM XML-документа.  
  
## <a name="w3c-xpath-node-types"></a>Типы узлов W3C XPath  
 Типы узлов, распознаваемые в запросе XPath, отличаются от типов узлов в модели DOM XML-документа. Ниже приведены типы узлов XPath, представленные перечислением <xref:System.Xml.XPath.XPathNodeType>.  
  
- <xref:System.Xml.XPath.XPathNodeType.All>  
  
- <xref:System.Xml.XPath.XPathNodeType.Attribute>  
  
- <xref:System.Xml.XPath.XPathNodeType.Comment>  
  
- <xref:System.Xml.XPath.XPathNodeType.Element>  
  
- <xref:System.Xml.XPath.XPathNodeType.Namespace>  
  
- <xref:System.Xml.XPath.XPathNodeType.ProcessingInstruction>  
  
- <xref:System.Xml.XPath.XPathNodeType.Root>  
  
- <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace>  
  
- <xref:System.Xml.XPath.XPathNodeType.Text>  
  
- <xref:System.Xml.XPath.XPathNodeType.Whitespace>  
  
 Эти типы узлов основаны на модели данных XPath, где узлы являются производными от набора данных XML. Типы узлов <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace> и <xref:System.Xml.XPath.XPathNodeType.Whitespace> - расширения платформы Microsoft .NET Framework для базовых типов узлов, описанных в модели данных XPath.  
  
 Тип узла атрибута используется в модели данных XPath иначе, нежели в DOM. В модели данных XPath узел элемента имеет набор связанных с ним узлов атрибута, и узел элемента является родителем каждого узла атрибута. Однако в DOM узел элемента является владельцем, но не родителем. В обеих моделях узлы атрибута и пространства имен не считаются дочерними узлами узла элемента.  
  
 Тип узла пространства имен - дополнение к модели данных XPath и не является распознаваемым типом узла DOM.  
  
 См. дополнительные сведения о навигации в руководствах по [навигации по наборам улов](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md) и [улов атрибутов и пространств имен](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md) с помощью XPathNavigator.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Обработка XML-данных с использованием модели данных XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Выборка XML-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)
- [Вычисление выражения XPath с помощью класса XPathNavigator](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)
- [Соответствие узлов с помощью XPathNavigator](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)
- [Запросы XPath и пространства имен](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)
- [Скомпилированные выражения XPath](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
