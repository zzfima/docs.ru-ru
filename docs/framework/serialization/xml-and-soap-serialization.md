---
title: "XML- и SOAP-сериализация | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "сериализация"
  - "сериализация, о сериализации"
  - "сериализация, SOAP"
  - "SOAP, XML-сериализация"
  - "XML-сериализация"
  - "XML-сериализация, SOAP"
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# XML- и SOAP-сериализация
При XML\-сериализации открытые поля и свойства объекта или параметры и возвращаемые значения методов преобразуются \(сериализуются\) в поток XML в соответствии со специальным документом, составленном на языке XSD \(язык определения схемы XML\).XML\-сериализация приводит к образованию строго типизированных классов с открытыми свойствами и полями, которые преобразуются в серийный формат \(в данном случае — XML\) для хранения и передачи.  
  
 Поскольку стандарт XML является открытым, поток XML может обработать любое необходимое приложение независимо от платформы.Например, XML\-веб\-службы, созданные с помощью ASP.NET, используют класс <xref:System.Xml.Serialization.XmlSerializer>, чтобы создавать потоки XML, которые передают данные между приложениями веб\-службы XML через Интернет или интрасети.И наоборот, при десериализации используется такой поток и воссоздается объект.  
  
 XML\-сериализация может также использоваться для сериализации объектов в потоки XML, которые соответствуют спецификации SOAP.SOAP — это протокол, основанный на XML и созданный специально для передачи вызовов процедур с использованием XML.  
  
 Чтобы сериализовать и десериализовать объекты, используйте класс <xref:System.Xml.Serialization.XmlSerializer>.Чтобы создать классы для их последующей сериализации, используйте инструмент определения схемы XML.  
  
## В этом подразделе  
 [Введение в XML\-сериализацию](../../../docs/framework/serialization/introducing-xml-serialization.md)  
 Содержит общее определение сериализации, в особенности XML\-сериализации.  
  
 [Как сериализовать объект](../../../docs/framework/serialization/how-to-serialize-an-object.md)  
 Содержит пошаговые инструкции по сериализации объекта.  
  
 [Как десериализовать объект](../../../docs/framework/serialization/how-to-deserialize-an-object.md)  
 Содержит пошаговые инструкции по десериализации объекта.  
  
 [Примеры XML\-сериализации](../../../docs/framework/serialization/examples-of-xml-serialization.md)  
 Содержит примеры, демонстрирующие основные возможности XML\-сериализации .  
  
 [Инструмент определения схемы XML и сериализация XML](../../../docs/framework/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)  
 Содержит описание правил использования инструмента определения схемы XML для создания классов, которые соответствуют определенной схеме языка определения схемы XML \(XSD\), или создания схемы XML из файла DLL.  
  
 [Управление XML\-сериализацией с использованием атрибутов](../../../docs/framework/serialization/controlling-xml-serialization-using-attributes.md)  
 Содержит описание, как управлять сериализацией с помощью атрибутов.  
  
 [Атрибуты управления XML\-сериализацией](../../../docs/framework/serialization/attributes-that-control-xml-serialization.md)  
 Содержит список атрибутов, используемых для управления XML\-сериализацией.  
  
 [Как указать имя альтернативного элемента для потока XML](../../../docs/framework/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)  
 Содержит сложный сценарий, в котором описывается, как создавать несколько потоков XML путем переопределения сериализации.  
  
 [Как управлять сериализацией производных классов](../../../docs/framework/serialization/how-to-control-serialization-of-derived-classes.md)  
 Содержит пример, в котором показан способ управления сериализацией производных классов.  
  
 [Как квалифицировать элемент XML и имена атрибутов XML](../../../docs/framework/serialization/how-to-qualify-xml-element-and-xml-attribute-names.md)  
 Содержит описание, как определять и управлять способом, с помощью которого в потоке XML используются пространства имен XML.  
  
 [XML\-сериализация с использованием XML\-веб\-служб](../../../docs/framework/serialization/xml-serialization-with-xml-web-services.md)  
 Содержит объяснение способов использования XML\-сериализации в веб\-службах XML.  
  
 [Как сериализовать объект как поток XML с кодировкой SOAP](../../../docs/framework/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
 Содержит описание, как использовать класс <xref:System.Xml.Serialization.XmlSerializer> для создания потоков XML с кодировкой SOAP, соответствующих разделу 5 документа "Simple Object Access Protocol \(SOAP\) 1.1" консорциума World Wide Web Consortium \(www.w3.org\).  
  
 [Как переопределить XML\-сериализацию с кодировкой SOAP](../../../docs/framework/serialization/how-to-override-encoded-soap-xml-serialization.md)  
 Содержит описание процесса переопределения XML\-сериализации объектов как сообщений SOAP.  
  
 [Атрибуты управления SOAP\-сериализацией с кодировкой](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md)  
 Содержит список атрибутов, используемых для управления сериализацией с кодировкой SOAP.  
  
 [Элемент \<system.xml.serialization\>](../../../docs/framework/serialization/system-xml-serialization-element.md)  
 Элемент конфигурации верхнего уровня для управления XML\-сериализацией.  
  
 [Элемент \<dateTimeSerialization\>](../../../docs/framework/serialization/datetimeserialization-element.md)  
 Содержит информацию об управлении режимом сериализации объектов <xref:System.DateTime>.  
  
 [Элемент \<schemaImporterExtensions\>](../../../docs/framework/serialization/schemaimporterextensions-element.md)  
 Содержит типы, используемые классом <xref:System.Xml.Serialization.XmlSchemaImporter>.  
  
 [Элемент \<add\> для элемента \<xmlSchemaImporterExtensions\>](../../../docs/framework/serialization/add-element-for-xmlschemaimporterextensions.md)  
 Содержит информацию о добавленных типах, использующих класс <xref:System.Xml.Serialization.XmlSchemaImporter>.  
  
## Связанные подразделы  
 [Advanced Development Technologies](http://msdn.microsoft.com/ru-ru/c4a7e341-f0c6-4df4-a74f-223387ac6e4e)  
 Содержит ссылки на дополнительные сведения о сложных задачах и методиках разработки приложений в платформе .NET Framework.  
  
 [XML Web Services Created Using ASP.NET and XML Web Service Clients](http://msdn.microsoft.com/ru-ru/1e64af78-d705-4384-b08d-591a45f4379c)  
 Содержит разделы с описаниями и объяснением программирования XML\-веб\-служб с помощью ASP.NET.  
  
## См. также  
 [Двоичная сериализация](../../../docs/framework/serialization/binary-serialization.md)