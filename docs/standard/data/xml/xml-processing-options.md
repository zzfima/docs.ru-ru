---
title: Параметры обработки XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 33ced8ee-1745-4e71-8dee-ebe70ec067c7
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3fc7def48bff71935fce7c6ed914ad20c66e5182
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425178"
---
# <a name="xml-processing-options"></a>Параметры обработки XML
В следующих таблицах приведен список технологий Microsoft, с помощью которых можно обрабатывать XML-данные.  
  
## <a name="net-framework-options"></a>Параметры платформы .NET Framework  
  
|**Параметр**|**Тип обработки**|**Описание**|  
|----------------|-------------------------|---------------------|  
|[LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) <br/> [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md) <br />(пространство имен <xref:System.Xml.Linq>)|In-memory|— На основе технологии LINQ платформы .NET Framework.<br />— Позволяет создавать запросы в стиле SQL для обращения к объектам, реляционным данным и XML-данным.<br />— Предоставляет удобные возможности для создания и преобразования документов.<br />— Используйте этот вариант, если вы создаете новый код.|  
|<xref:System.Xml.XmlReader?displayProperty=nameWithType>|На основе потоков|— Предоставляет быстрый последовательный доступ к XML-данным без кэширования.<br />— Вы можете создавать объекты с помощью метода <xref:System.Xml.XmlReader.Create%2A?displayProperty=nameWithType>, указывая набор поддерживаемых объектом компонентов с помощью класса <xref:System.Xml.XmlReaderSettings>.|  
|<xref:System.Xml.XmlWriter?displayProperty=nameWithType>|На основе потоков|— Предоставляет быстрый способ последовательного формирования XML-данных без кэширования.<br />— Вы можете создавать объекты с помощью метода <xref:System.Xml.XmlWriter.Create%2A?displayProperty=nameWithType>, указывая набор поддерживаемых объектом компонентов с помощью класса <xref:System.Xml.XmlWriterSettings>.|  
|<xref:System.Xml.XmlDocument?displayProperty=nameWithType>|In-memory|— Реализует рекомендации модели W3C [DOM базового уровня 1](https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html) и [DOM базового уровня 2](https://www.w3.org/TR/DOM-Level-2-Core/).<br />— Узлы можно создавать, вставлять, удалять и изменять с помощью методов и свойств, основанных на знакомой модели DOM.<br />— Используйте этот вариант, если вы дорабатываете существующий код, в котором используется W3C DOM.|  
|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|In-memory|— Предлагает несколько вариантов для редактирования и навигации на основе модели курсора.<br />— XML-документы могут содержаться в объекте <xref:System.Xml.XPath.XPathDocument> или <xref:System.Xml.XmlDocument>.<br />— Обеспечивает превосходную производительность при обработке XML в режиме чтения.<br />— Используйте этот вариант, если вы редактируете существующий код, в котором применяются запросы XPath или преобразования XSLT.|  
|<xref:System.Xml.Xsl.XslCompiledTransform>|In-memory|— Предоставляет возможности для преобразования XML-данных с помощью преобразований XSL.<br />— [Компилятор XSLT (xsltc.exe)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md) позволяет задавать в приложении ссылки на готовые преобразования.|  
  
## <a name="win32-and-com-based-options"></a>Win32 и параметры, основанные на технологии COM  
  
|**Параметр**|**Описание**|  
|----------------|---------------------|  
|[XmlLite](https://docs.microsoft.com/previous-versions/windows/desktop/ms752872(v=vs.85))|— Быстрое и безопасное средство последовательного синтаксического анализа XML, которое позволяет создавать высокопроизводительные XML-приложения.<br />— Работает с любым языком, который поддерживает динамически загружаемые библиотеки (DLL); мы рекомендуем использовать C++.|  
|[MSXML](https://docs.microsoft.com/previous-versions/windows/desktop/ms763742(v=vs.85))|— Основанная на модели COM технология обработки XML, включенная в операционную систему Windows.<br />— Обеспечивает собственную реализацию DOM с поддержкой XPath и XSLT.<br />— Содержит основанное на событиях средство синтаксического анализа SAX2.|  
  
## <a name="see-also"></a>См. также

- [Обработка XML-данных с использованием модели DOM](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)
- [Обработка XML-данных с использованием модели данных XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Компилятор XSLT (xsltc.exe)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)
