---
title: "Ввод XmlDataDocument в XslTransform | Microsoft Docs"
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
ms.assetid: a0b536b6-cdb3-4a44-86c2-3b2ebc7bd4c9
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 4
---
# Ввод XmlDataDocument в XslTransform
> [!NOTE]
>  Класс <xref:System.Xml.Xsl.XslTransform> в версии [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] устарел. Можно выполнять XSLT\-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>. Дополнительные сведения см. в разделах [Использование класса XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) и [Миграция с класса XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).  
  
 Платформа Microsoft [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] реализует модель DOM, чтобы предоставить доступ к данным в XML\-документах и дополнительным классам для чтения, записи и перемещения в XML\-документах. Класс <xref:System.Xml.XmlDataDocument> в пространстве имен <xref:System.Xml> обеспечивает реляционный доступ к данным с возможностью синхронизации с реляционными данными в объекте <xref:System.Data.DataSet>. Можно одновременно просматривать и управлять структурированными XML\-документами через реляционное представление <xref:System.Data.DataSet> или управлять полуструктурированными XML\-документами через представление модели DOM класса <xref:System.Xml.XmlDataDocument>. Поэтому класс <xref:System.Xml.XmlDataDocument> пересекает границы реляционной и XML\-областей.  
  
 Если данные хранятся в реляционной структуре и нужно использовать их в качестве входных данных для XSLT\-преобразования, можно загрузить реляционные данные в объект <xref:System.Data.DataSet> и связать их с объектом <xref:System.Xml.XmlDataDocument>. Объект <xref:System.Xml.XPath.XPathNavigator>, входной параметр для объекта <xref:System.Xml.Xsl.XslTransform>, реализован в классе <xref:System.Xml.XmlDataDocument> через интерфейс <xref:System.Xml.XPath.IXPathNavigable>. Принимая реляционные данные, загружая их в объект <xref:System.Data.DataSet> и используя синхронизацию в классе <xref:System.Xml.XmlDataDocument>, можно выполнить XSLT\-преобразование реляционных данных.  
  
 Дополнительные сведения о применении преобразования реляционных данных см. в разделе [Применение XSLT\-преобразования к набору данных](../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md).  
  
## См. также  
 <xref:System.Xml.XmlDataDocument>   
 [Синхронизация DataSet и XmlDataDocument](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)   
 [XSLT\-преобразования с помощью класса XslTransform](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)   
 [Реализация классом XslTransform XSLT\-процессора](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)   
 [XPathNavigator в преобразованиях](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)   
 [XPathNodeIterator в преобразованиях](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)   
 [Ввод XPathDocument в XslTransform](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)   
 [Ввод XmlDocument в XslTransform](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)