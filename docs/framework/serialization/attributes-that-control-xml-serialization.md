---
title: "Атрибуты управления XML-сериализацией | Microsoft Docs"
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
  - "атрибуты [платформа .NET Framework], XML-сериализация"
  - "классы, сериализация"
  - "сериализация, атрибуты"
  - "схема XML, сериализация"
  - "XML-сериализация, атрибуты"
  - "класс XmlSerializer, сериализация"
ms.assetid: 414b820f-a696-4206-b576-2711d85490c7
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Атрибуты управления XML-сериализацией
Для управления способом, с помощью которого [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx) сериализует или десериализует экземпляр класса, к классам и членам класса можно применять атрибуты, указанные в следующей таблице.Дополнительные сведения о том, как эти атрибуты управляют сериализацией XML, см. в разделе [Управление XML\-сериализацией с использованием атрибутов](../../../docs/framework/serialization/controlling-xml-serialization-using-attributes.md).  
  
 Эти атрибуты можно также использовать для управления литеральным стилем сообщений SOAP, генерируемых XML\-веб\-службой.Дополнительные сведения о применении этих атрибутов для существующего метода XML\-веб\-служб см. в разделе [XML\-сериализация с использованием XML\-веб\-служб](../../../docs/framework/serialization/xml-serialization-with-xml-web-services.md).  
  
 Дополнительные сведения об атрибутах см. в разделе [Атрибуты](../../../docs/standard/attributes/index.md).  
  
|Атрибут|Применимость|Что определяет|  
|-------------|------------------|--------------------|  
|[XmlAnyAttributeAttribute](frlrfSystemXmlSerializationXmlAnyAttributeAttributeClassTopic)|Открытое поле, свойство, параметр или возвращаемое значение, которое возвращает массив объектов [XmlAttribute](frlrfSystemXmlXmlAttributeClassTopic).|Во время десериализации массив будет заполняться объектами [XmlAttribute](frlrfSystemXmlXmlAttributeClassTopic), представляющими все атрибуты XML, не известные для схемы.|  
|[XmlAnyElementAttribute](frlrfSystemXmlSerializationXmlAnyElementAttributeClassTopic)|Открытое поле, свойство, параметр или возвращаемое значение, которое возвращает массив объектов [XmlElement](frlrfSystemXmlXmlElementClassTopic).|Во время десериализации массив заполняется объектами [XmlElement](frlrfSystemXmlXmlElementClassTopic), представляющими все элементы XML, не известные для схемы.|  
|[XmlArrayAttribute](frlrfSystemXmlSerializationXmlArrayAttributeClassTopic)|Открытое поле, свойство, параметр или возвращаемое значение, которое возвращает массив сложных объектов.|Члены массива создаются как члены массива XML.|  
|[XmlArrayItemAttribute](frlrfSystemXmlSerializationXmlArrayItemAttributeClassTopic)|Открытое поле, свойство, параметр или возвращаемое значение, которое возвращает массив сложных объектов.|Производные типы, которые могут быть размещены в массиве.Обычно используется совместно с [XmlArrayAttribute](frlrfSystemXmlSerializationXmlArrayAttributeClassTopic).|  
|[XmlAttributeAttribute](frlrfSystemXmlSerializationXmlAttributeAttributeClassTopic)|Открытое поле, свойство, параметр или возвращаемое значение.|Член должен быть сериализован как атрибут XML.|  
|[XmlChoiceIdentifierAttribute](frlrfSystemXmlSerializationXmlChoiceIdentifierAttributeClassTopic)|Открытое поле, свойство, параметр или возвращаемое значение.|Член может быть однозначно определен перечислением.|  
|[XmlElementAttribute](frlrfSystemXmlSerializationXmlElementAttributeClassTopic)|Открытое поле, свойство, параметр или возвращаемое значение.|Поле или свойство сериализуется как элемент XML.|  
|[XmlEnumAttribute](frlrfSystemXmlSerializationXmlEnumAttributeClassTopic)|Открытое поле, идентификатор перечисления.|Имя элемента члена перечисления.|  
|[XmlIgnoreAttribute](frlrfSystemXmlSerializationXmlIgnoreAttributeClassTopic)|Открытые свойства и поля.|При сериализации содержащего класса свойство или поле должно игнорироваться.|  
|[XmlIncludeAttribute](frlrfSystemXmlSerializationXmlIncludeAttributeClassTopic)|Объявления открытых производных классов и возвращаемые значения открытых методов для документов WSDL.|При создании схем класс должен быть включен \(чтобы его можно было распознать во время сериализации\).|  
|[XmlRootAttribute](frlrfSystemXmlSerializationXmlRootAttributeClassTopic)|Объявления открытых классов.|Управляет XML\-сериализацией конечного объекта атрибута как корневого XML\-элемента.Используйте атрибут, чтобы подробнее указать пространство имен и имя элемента.|  
|[XmlTextAttribute](frlrfSystemXmlSerializationXmlTextAttributeClassTopic)|Открытые свойства и поля.|Свойство или поле сериализуется как текст XML.|  
|[XmlTypeAttribute](frlrfSystemXmlSerializationXmlTypeAttributeClassTopic)|Объявления открытых классов.|Имя и пространство имен типа XML.|  
  
 Кроме этих атрибутов, которые располагаются в пространстве имен [System.Xml.Serialization](frlrfSystemxmlserialization), к полю можно применять атрибут [System.ComponentModel.DefaultValueAttribute](frlrfSystemComponentModelDefaultValueAttributeClassTopic).**DefaultValueAttribute** задает значение, которое автоматически назначается члену, если значение не указано.  
  
 Описание управления сериализацией кодированных элементов SOAP XML см. в разделе [Атрибуты управления SOAP\-сериализацией с кодировкой](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md).  
  
## См. также  
 [XML\- и SOAP\-сериализация](../../../docs/framework/serialization/xml-and-soap-serialization.md)   
 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)   
 [Управление XML\-сериализацией с использованием атрибутов](../../../docs/framework/serialization/controlling-xml-serialization-using-attributes.md)   
 [Как указать имя альтернативного элемента для потока XML](../../../docs/framework/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)   
 [Как сериализовать объект](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [Как десериализовать объект](../../../docs/framework/serialization/how-to-deserialize-an-object.md)