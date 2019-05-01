---
title: Сериализация XML и SOAP
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
- serialization, about serialization
- XML serialization
- serialization
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
ms.openlocfilehash: d9dc68d8e7eced031af404aaec20784573c9930a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62028243"
---
# <a name="xml-and-soap-serialization"></a>Сериализация XML и SOAP

При сериализации XML открытые поля и свойства объекта или параметры и возвращаемые значения методов преобразуются (сериализуются) в поток XML в соответствии со специальным документом, составленном на языке XSD (язык определения схемы XML). XML-сериализация приводит к образованию строго типизированных классов с открытыми свойствами и полями, которые преобразуются в серийный формат (в данном случае - XML) для хранения и передачи.

Поскольку стандарт XML является открытым, поток XML может обработать любое необходимое приложение независимо от платформы. Например, XML-веб-службы, созданные с помощью ASP.NET, используют класс <xref:System.Xml.Serialization.XmlSerializer>, чтобы создавать потоки XML, которые передают данные между приложениями веб-службы XML через Интернет или интрасети. И наоборот, при десериализации используется такой поток и воссоздается объект.

XML-сериализация может также использоваться для сериализации объектов в потоки XML, которые соответствуют спецификации SOAP. SOAP - это протокол, основанный на XML и созданный специально для передачи вызовов процедур с использованием XML.

Чтобы сериализовать и десериализовать объекты, используйте класс <xref:System.Xml.Serialization.XmlSerializer>. Чтобы создать классы для их последующей сериализации, используйте инструмент определения схемы XML.

## <a name="in-this-section"></a>В этом разделе

[Введение в сериализацию XML](introducing-xml-serialization.md)  
Содержит общее определение сериализации, в особенности, XML-сериализации.

[Практическое руководство. Сериализация объекта](how-to-serialize-an-object.md)  
Содержит пошаговые инструкции по сериализации объекта.

[Практическое руководство. Десериализация объекта](how-to-deserialize-an-object.md)  
Содержит пошаговые инструкции по десериализации объекта.

[Примеры сериализации XML](examples-of-xml-serialization.md)  
Содержит примеры, демонстрирующие основные возможности XML-сериализации .

[Инструмент определения схемы XML и сериализация XML](the-xml-schema-definition-tool-and-xml-serialization.md)  
Содержит описание правил использования инструмента определения схемы XML для создания классов, которые соответствуют определенной схеме языка определения схемы XML (XSD), или создания схемы XML из файла DLL.

[Управление сериализацией XML с использованием атрибутов](controlling-xml-serialization-using-attributes.md)  
Содержит описание, как управлять сериализацией с помощью атрибутов.

[Атрибуты управления сериализацией XML](attributes-that-control-xml-serialization.md)  
Содержит список атрибутов, используемых для управления XML-сериализацией.

[Практическое руководство. Указание имени альтернативного элемента для XML Stream](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)  
Содержит сложный сценарий, в котором описывается, как создавать несколько потоков XML путем переопределения сериализации.

[Практическое руководство. Управление сериализацией производных классов](how-to-control-serialization-of-derived-classes.md)  
Содержит пример, в котором показан способ управления сериализацией производных классов.

[Практическое руководство. Квалификация элемента XML и имен атрибутов XML](how-to-qualify-xml-element-and-xml-attribute-names.md)  
Содержит описание, как определять и управлять способом, с помощью которого в потоке XML используются пространства имен XML.

[Сериализация XML с использованием XML-веб-служб](xml-serialization-with-xml-web-services.md)  
Содержит объяснение способов использования XML-сериализации в веб-службах XML.

[Практическое руководство. Сериализация объекта как Stream XML с кодировкой SOAP](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
Описывает использование <xref:System.Xml.Serialization.XmlSerializer> класс, чтобы создать закодированный SOAP XML потоки, которые соответствуют раздела 5 документа консорциума World Wide Web (W3C) [Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/).

[Практическое руководство. Переопределение сериализации XML с кодировкой SOAP](how-to-override-encoded-soap-xml-serialization.md)  
Содержит описание процесса переопределения XML-сериализации объектов как сообщений SOAP.

[Атрибуты управления сериализацией с кодировкой SOAP](attributes-that-control-encoded-soap-serialization.md)  
Содержит список атрибутов, используемых для управления сериализацией с кодировкой SOAP.

[Элемент \<system.xml.serialization>](system-xml-serialization-element.md)  
Элемент конфигурации верхнего уровня для управления XML-сериализацией.

[Элемент \<dateTimeSerialization>](datetimeserialization-element.md)  
Содержит информацию об управлении режимом сериализации объектов <xref:System.DateTime>.

[Элемент \<schemaImporterExtensions>](schemaimporterextensions-element.md)  
Содержит типы, используемые классом <xref:System.Xml.Serialization.XmlSchemaImporter>.

[\<Добавить > элемент для \<schemaImporterExtensions >](add-element-for-schemaimporterextensions.md)  
Добавляет типы, используемые классом <xref:System.Xml.Serialization.XmlSchemaImporter>.

## <a name="related-sections"></a>Связанные разделы

[Веб-службы XML, созданные с помощью ASP.NET, и клиенты веб-служб с поддержкой XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))  
Содержит разделы с описаниями и объяснением программирования XML-веб-служб с помощью ASP.NET.

## <a name="see-also"></a>См. также

- [Двоичная сериализация](binary-serialization.md)
