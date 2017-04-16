---
title: "Параметры обработки XML | Microsoft Docs"
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
ms.assetid: 33ced8ee-1745-4e71-8dee-ebe70ec067c7
caps.latest.revision: 5
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 5
---
# Параметры обработки XML
В следующих таблицах приведен список технологий Microsoft, с помощью которых можно обрабатывать XML\-данные.  
  
## Параметры платформы .NET Framework  
  
|**Параметр**|**Тип обработки**|**Описание**|  
|------------------|-----------------------|------------------|  
|[LINQ to XML](../../../../ocs/visual-basic/programming-guide/concepts/linq/linq-to-xml.md) <br /> \(пространство имен <xref:System.Xml.Linq>\)|In\-memory|-   На основе технологии LINQ платформы .NET Framework.<br />-   Позволяет работать с запросами к объектам, реляционным данным и XML\-данным как в SQL.<br />-   Предоставляет наглядные возможности по созданию и преобразованию документов.<br />-   Используйте этот вариант при написании нового кода.|  
|<xref:System.Xml.XmlReader?displayProperty=fullName>|На основе потоков|-   Предоставляет быстрый односторонний доступ к XML\-данным без кэширования.<br />-   Можно создать объекты с помощью метода <xref:System.Xml.XmlReader.Create%2A?displayProperty=fullName> и указать набор компонентов, которые будут включены для объекта, посредством класса <xref:System.Xml.XmlReaderSettings>.|  
|<xref:System.Xml.XmlWriter?displayProperty=fullName>|На основе потоков|-   Предоставляет быстрый способ однонаправленного формирования XML\-данных без кэширования.<br />-   Можно создать объекты с помощью метода <xref:System.Xml.XmlWriter.Create%2A?displayProperty=fullName> и указать набор компонентов, которые будут включены для объекта, посредством класса <xref:System.Xml.XmlWriterSettings>.|  
|<xref:System.Xml.XmlDocument?displayProperty=fullName>|In\-memory|-   Реализует рекомендации по [ядру модели DOM уровня 1 W3C](http://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html) и [ядру модели DOM уровня 2](http://www.w3.org/TR/DOM-Level-2-Core/).<br />-   Узлы можно создавать, вставлять, удалять и изменять с помощью методов и свойств, основанных на знакомой модели DOM.<br />-   Используйте этот вариант при изменении существующего кода, в котором используется W3C DOM.|  
|<xref:System.Xml.XPath.XPathNavigator?displayProperty=fullName>|In\-memory|-   Предлагает несколько параметров изменения и возможностей перемещения с помощью модели курсора.<br />-   XML\-документы могут содержаться в объекте <xref:System.Xml.XPath.XPathDocument> или объекте <xref:System.Xml.XmlDocument>.<br />-   Обеспечивает превосходную производительность при обработке XML только для чтения.<br />-   Используйте этот вариант при изменении существующего кода с помощью запросов XPath или преобразований XSLT.|  
|<xref:System.Xml.Xsl.XslCompiledTransform>|In\-memory|-   Предоставляет параметры для преобразования XML\-данных с помощью преобразований XSL.<br />-   [XSLT\-компилятор \(xsltc.exe\)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md) позволяет задавать ссылки на готовые преобразования в приложении.|  
  
## Win32 и параметры, основанные на технологии COM  
  
|**Параметр**|**Описание**|  
|------------------|------------------|  
|[XmlLite](http://go.microsoft.com/fwlink/?LinkId=93723)|-   Это быстрое безопасное однопроходное средство синтаксического анализа XML, которое позволяет создавать высокопроизводительные XML\-приложения.<br />-   Работает с любым языком, который может использовать динамически загружаемые библиотеки \(DLL\); рекомендуется C\+\+.|  
|[MSXML](http://go.microsoft.com/fwlink/?LinkId=93722)|-   Это основанная на модели COM технология обработки XML, включенная в операционную систему Windows.<br />-   Обеспечивает собственную реализацию DOM с поддержкой XPath и XSLT.<br />-   Содержит основанное на событиях средство синтаксического анализа SAX2.|  
  
## См. также  
 [Обработка XML\-данных с использованием модели DOM](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)   
 [Обработка XML\-данных с использованием модели данных XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)   
 [XSLT\-компилятор \(xsltc.exe\)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)