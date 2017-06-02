---
title: "Типы узлов, распознаваемые запросами XPath | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 1d33e22d-18e5-43f8-a466-2e3d0a8dd094
caps.latest.revision: 2
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 2
---
# Типы узлов, распознаваемые запросами XPath
Типы узлов, распознаваемые в запросе XPath, отличаются от типов узлов в модели DOM XML\-документа.  
  
## Типы узлов W3C XPath  
 Типы узлов, распознаваемые в запросе XPath, отличаются от типов узлов в модели DOM XML\-документа.  Ниже приведены типы узлов XPath, представленные перечислением <xref:System.Xml.XPath.XPathNodeType>.  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
 Эти типы узлов основаны на модели данных XPath, где узлы являются производными от набора данных XML.  Типы узлов <xref:System.Xml.XPath.XPathNodeType> и <xref:System.Xml.XPath.XPathNodeType> \- расширения платформы Microsoft .NET Framework для базовых типов узлов, описанных в модели данных XPath.  
  
 Тип узла атрибута используется в модели данных XPath иначе, нежели в DOM.  В модели данных XPath узел элемента имеет набор связанных с ним узлов атрибута, и узел элемента является родителем каждого узла атрибута.  Однако в DOM узел элемента является владельцем, но не родителем.  В обеих моделях узлы атрибута и пространства имен не считаются дочерними узлами узла элемента.  
  
 Тип узла пространства имен \- дополнение к модели данных XPath и не является распознаваемым типом узла DOM.  
  
 Дополнительные сведения о навигации по узлам элементов, атрибутов и пространств имен см. в разделах [Навигация в наборе узлов с помощью XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md) и [Навигация по узлам атрибутов и пространств имен с помощью XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md).  
  
## См. также  
 <xref:System.Xml.XmlDocument>   
 <xref:System.Xml.XPath.XPathDocument>   
 <xref:System.Xml.XPath.XPathNavigator>   
 [Обработка XML\-данных с использованием модели данных XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)   
 [Выборка XML\-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)   
 [Вычисление выражения XPath с помощью класса XPathNavigator](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)   
 [Соответствие узлов с помощью XPathNavigator](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)   
 [Запросы XPath и пространства имен](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)   
 [Скомпилированные выражения XPath](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)