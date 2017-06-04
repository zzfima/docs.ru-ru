---
title: "Обработка XML-данных в памяти | Microsoft Docs"
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
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
caps.latest.revision: 2
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 2
---
# Обработка XML-данных в памяти
Платформа Microsoft .NET Framework предусматривает три модели обработки XML\-данных: класс <xref:System.Xml.XmlDocument>, класс <xref:System.Xml.XPath.XPathDocument> и [LINQ to XML](../../../../ocs/visual-basic/programming-guide/concepts/linq/linq-to-xml.md).  
  
 Класс <xref:System.Xml.XmlDocument> реализует базовую модель DOM W3C 1\-го уровня и базовые рекомендации объекта DOM 2\-го уровня.  DOM \- древовидное представление XML\-документа в памяти \(кэш\).  С помощью <xref:System.Xml.XmlDocument> и связанных классов можно конструировать XML\-документы, загружать данные и обращаться к ним, изменять данные и сохранять изменения.  
  
 Класс <xref:System.Xml.XPath.XPathDocument> \- доступное только для чтения хранилище данных в памяти, на базе модели данных XPath.  В классе <xref:System.Xml.XPath.XPathNavigator> предусмотрено несколько вариантов редактирования и способов навигации с помощью модели курсора для XML\-документов в доступном только для чтения классе <xref:System.Xml.XPath.XPathDocument>, а также в классе <xref:System.Xml.XmlDocument>.  
  
 [LINQ to XML](../../../../ocs/visual-basic/programming-guide/concepts/linq/linq-to-xml.md) \- новая модель в платформе .NET Framework версии 3.5 для обработки XML\-данных.  Это размещаемая в памяти модель, использующая [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md).  LINQ расширяет синтаксис C\# и Visual Basic, обеспечивая новые возможности запросов.  
  
## В этом подразделе  
 [Обработка XML\-данных с использованием модели DOM](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 Описывает использование класса <xref:System.Xml.XmlDocument> и связанных с ним классов для обработки XML\-данных.  
  
 [Обработка XML\-данных с использованием модели данных XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 Описывает использование классов <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument> и <xref:System.Xml.XPath.XPathNavigator> для обработки XML\-данных.  
  
 [Обработка XML\-данных с помощью LINQ to XML](../../../../docs/standard/data/xml/process-xml-data-using-linq-to-xml.md)  
 Содержит краткие общие сведения о LINQ to XML и ссылки на документацию LINQ to XML.  
  
## Связанные подразделы  
 [XML\-документы и данные](../../../../docs/standard/data/xml/index.md)