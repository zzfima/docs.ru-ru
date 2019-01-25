---
title: Атрибуты управления сериализацией XML
ms.date: 03/30/2017
helpviewer_keywords:
- classes, serializing
- XmlSerializer class, serializing
- XML serialization, attributes
- attributes [.NET Framework], XML serialization
- serialization, attributes
- XML Schema, serializing
ms.assetid: 414b820f-a696-4206-b576-2711d85490c7
ms.openlocfilehash: 0d1aee4650ea29083348af482e445011289e9581
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580685"
---
# <a name="attributes-that-control-xml-serialization"></a>Атрибуты управления сериализацией XML
Для управления способом, с помощью которого <xref:System.Xml.Serialization.XmlSerializer> сериализует или десериализует экземпляр класса, к классам и членам класса можно применять атрибуты, указанные в следующей таблице. Сведения о том, как эти атрибуты управляют XML-сериализацией, см. в разделе [Управление сериализацией XML с использованием атрибутов](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md).  
  
 Эти атрибуты можно также использовать для управления литеральным стилем сообщений SOAP, генерируемых XML-веб-службой. Дополнительные сведения о применении этих атрибутов для существующего метода XML-веб-служб см. в разделе [Сериализация XML с использованием XML-веб-служб](../../../docs/standard/serialization/xml-serialization-with-xml-web-services.md).  
  
 Дополнительные сведения об атрибутах см. в разделе [Атрибуты](../../../docs/standard/attributes/index.md).  
  
|Атрибут|Применение|Что определяет|  
|---------------|----------------|---------------|  
|<xref:System.Xml.Serialization.XmlAnyAttributeAttribute>|Открытое поле, свойство, параметр или возвращаемое значение, которое возвращает массив объектов <xref:System.Xml.XmlAttribute>.|Во время десериализации массив будет заполняться объектами <xref:System.Xml.XmlAttribute>, представляющими все атрибуты XML, не известные для схемы.|  
|<xref:System.Xml.Serialization.XmlAnyElementAttribute>|Открытое поле, свойство, параметр или возвращаемое значение, которое возвращает массив объектов <xref:System.Xml.XmlElement>.|Во время десериализации массив заполняется объектами <xref:System.Xml.XmlElement>, представляющими все элементы XML, не известные для схемы.|  
|<xref:System.Xml.Serialization.XmlArrayAttribute>|Открытое поле, свойство, параметр или возвращаемое значение, которое возвращает массив сложных объектов.|Члены массива создаются как члены массива XML.|  
|<xref:System.Xml.Serialization.XmlArrayItemAttribute>|Открытое поле, свойство, параметр или возвращаемое значение, которое возвращает массив сложных объектов.|Производные типы, которые могут быть размещены в массиве. Обычно используется совместно с <xref:System.Xml.Serialization.XmlArrayAttribute>.|  
|<xref:System.Xml.Serialization.XmlAttributeAttribute>|Открытое поле, свойство, параметр или возвращаемое значение.|Член должен быть сериализован как атрибут XML.|  
|<xref:System.Xml.Serialization.XmlChoiceIdentifierAttribute>|Открытое поле, свойство, параметр или возвращаемое значение.|Член может быть однозначно определен перечислением.|  
|<xref:System.Xml.Serialization.XmlElementAttribute>|Открытое поле, свойство, параметр или возвращаемое значение.|Поле или свойство сериализуется как элемент XML.|  
|<xref:System.Xml.Serialization.XmlEnumAttribute>|Открытое поле, являющееся идентификатором перечисления.|Имя элемента члена перечисления.|  
|<xref:System.Xml.Serialization.XmlIgnoreAttribute>|Открытые свойства и поля.|Свойство или поле должно игнорироваться при сериализации содержащего его класса.|  
|<xref:System.Xml.Serialization.XmlIncludeAttribute>|Объявления открытых производных классов и возвращаемые значения открытых методов для документов WSDL.|При создании схем класс должен быть включен (чтобы его можно было распознать во время сериализации).|  
|<xref:System.Xml.Serialization.XmlRootAttribute>|Объявления открытых классов.|Управляет XML-сериализацией конечного объекта атрибута как корневого XML-элемента. Используйте атрибут, чтобы подробнее указать пространство имен и имя элемента.|  
|<xref:System.Xml.Serialization.XmlTextAttribute>|Открытые свойства и поля.|Свойство или поле сериализуется как текст XML.|  
|<xref:System.Xml.Serialization.XmlTypeAttribute>|Объявления открытых классов.|Имя и пространство имен типа XML.|  
  
 Кроме этих атрибутов, которые располагаются в пространстве имен <xref:System.Xml.Serialization>, к полю можно применять атрибут <xref:System.ComponentModel.DefaultValueAttribute>. Атрибут **DefaultValueAttribute** задает значение, которое автоматически назначается члену, если значение не указано.  
  
 Дополнительные сведения см. в разделе [Атрибуты управления сериализацией с кодировкой SOAP](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).  
  
## <a name="see-also"></a>См. также

- [Сериализация XML и SOAP](../../../docs/standard/serialization/xml-and-soap-serialization.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Управление сериализацией XML с использованием атрибутов](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)
- [Практическое руководство. Указание имени альтернативного элемента для XML Stream](../../../docs/standard/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
- [Практическое руководство. Сериализация объекта](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [Практическое руководство. Десериализация объекта](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
