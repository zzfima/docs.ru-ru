---
title: "Параметры обработки XML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33ced8ee-1745-4e71-8dee-ebe70ec067c7
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 18f8f9c76a1842517340eaa3f74b4778f869403e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xml-processing-options"></a>Параметры обработки XML
В следующих таблицах приведен список технологий Microsoft, с помощью которых можно обрабатывать XML-данные.  
  
## <a name="net-framework-options"></a>Параметры платформы .NET Framework  
  
|**Параметр**|**Тип обработки**|**Описание**|  
|----------------|-------------------------|---------------------|  
|[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) <br />(пространство имен <xref:System.Xml.Linq>)|In-memory|-Основаны на технологии технологии запросов (LINQ).<br />-Обеспечивает функционирование запросов, которая похожа на SQL для объектов, реляционных данных и XML-данных.<br />-Предоставляет наглядные возможности по созданию и преобразованию документа.<br />-Используйте этот вариант при написании нового кода.|  
|<xref:System.Xml.XmlReader?displayProperty=nameWithType>|На основе потоков|-Обеспечивает быстрое, без кэширования, прямой способ доступа к данным XML.<br />— Можно создать объекты с помощью <xref:System.Xml.XmlReader.Create%2A?displayProperty=nameWithType> метода и указать набор функций, которые включены для объекта с помощью <xref:System.Xml.XmlReaderSettings> класса.|  
|<xref:System.Xml.XmlWriter?displayProperty=nameWithType>|На основе потоков|-Обеспечивает быстрое, без кэширования, прямой способ создания XML-данных.<br />— Можно создать объекты с помощью <xref:System.Xml.XmlWriter.Create%2A?displayProperty=nameWithType> метода и указать набор функций, которые включены для объекта с помощью <xref:System.Xml.XmlWriterSettings> класса.|  
|<xref:System.Xml.XmlDocument?displayProperty=nameWithType>|In-memory|-Реализует [базового уровня 1 W3C объекта модели (DOM)](http://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html) и [DOM Level 2 Core](http://www.w3.org/TR/DOM-Level-2-Core/) рекомендации.<br />— Можно создать, вставки, удаления и изменения узлов с помощью методов и свойств, основанных на знакомой модели DOM..<br />— Используйте этот вариант при изменении существующего кода, в котором используется W3C DOM.|  
|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|In-memory|-Обеспечивает несколько вариантов редактирования и возможностей перемещения с помощью модели курсора.<br />-XML документы могут содержаться в <xref:System.Xml.XPath.XPathDocument> или <xref:System.Xml.XmlDocument> объекта.<br />-Обеспечивает превосходную производительность для обработки только для чтения XML.<br />-Используйте этот параметр, при изменении существующего кода с помощью запросов XPath или преобразований XSLT.|  
|<xref:System.Xml.Xsl.XslCompiledTransform>|In-memory|-Предоставляет параметры для преобразования XML-данных с помощью преобразований XSL.<br />- [XSLT-компилятор (xsltc.exe)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md) ссылке позволяет предварительно компилируется преобразований в вашем приложении.|  
  
## <a name="win32-and-com-based-options"></a>Win32 и параметры, основанные на технологии COM  
  
|**Параметр**|**Описание**|  
|----------------|---------------------|  
|[XmlLite](http://go.microsoft.com/fwlink/?LinkId=93723)|-Быстрый и надежный, без кэширования, только вперед синтаксического анализа XML, которая помогает создавать высокопроизводительные приложения XML.<br />-Работает с любым языком, можно использовать библиотеки динамической компоновки (DLL); Мы рекомендуем использовать C++.|  
|[MSXML](http://go.microsoft.com/fwlink/?LinkId=93722)|-Основанной на COM технология обработки XML, который входит в состав операционной системы Windows.<br />-Обеспечивает собственную реализацию DOM с поддержкой XPath и XSLT.<br />-Содержит средство синтаксического анализа SAX2 на основе событий.|  
  
## <a name="see-also"></a>См. также  
 [Обработка XML-данных с помощью модели DOM](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 [Обработка XML-данных с использованием модели данных XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [XSLT-компилятор (xsltc.exe)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)
