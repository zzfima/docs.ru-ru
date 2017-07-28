---
title: "Атрибуты управления SOAP-сериализацией с кодировкой | Microsoft Docs"
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
  - "сериализация, атрибуты"
  - "SOAP, XML-сериализация"
  - "XML-сериализация, атрибуты"
  - "XML-сериализация, SOAP"
ms.assetid: 93ee258c-9c0f-4a08-897c-c10db7a00f91
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Атрибуты управления SOAP-сериализацией с кодировкой
В документе «Simple Object Access Protocol \(SOAP\) 1.1» консорциума World Wide Web Consortium \(www.w3.org\) содержится дополнительный раздел \(раздел 5\), в котором описаны способы кодирования параметров SOAP.Для соответствия разделу 5 спецификации следует использовать специальный набор атрибутов, расположенный в пространстве имен [System.Xml.Serialization](frlrfSystemXmlSerialization).Примените эти атрибуты для соответствующих классов и членов классов, а затем используйте [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx) для сериализации экземпляров класса или классов.  
  
 В следующей таблице показаны атрибуты, место их применения и выполняемые ими действия.Дополнительные сведения об использовании этих атрибутов для управления XML\-сериализацией см. в разделах [Как сериализовать объект как поток XML с кодировкой SOAP](../../../docs/framework/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) и [Как переопределить XML\-сериализацию с кодировкой SOAP](../../../docs/framework/serialization/how-to-override-encoded-soap-xml-serialization.md).  
  
 Дополнительные сведения об атрибутах см. в разделе [Атрибуты](../../../docs/standard/attributes/index.md).  
  
|Атрибут|Применимость|Что определяет|  
|-------------|------------------|--------------------|  
|[SoapAttributeAttribute](frlrfSystemXmlSerializationSoapAttributeAttributeClassTopic)|Открытое поле, свойство, параметр или возвращаемое значение.|Член класса должен быть сериализован как атрибут XML.|  
|[SoapElementAttribute](frlrfSystemXmlSerializationSoapElementAttributeClassTopic)|Открытое поле, свойство, параметр или возвращаемое значение.|Класс должен быть сериализован как элемент XML.|  
|[SoapEnumAttribute](frlrfSystemXmlSerializationSoapEnumAttributeClassTopic)|Открытое поле, являющееся идентификатором перечисления.|Имя элемента члена перечисления.|  
|[SoapIgnoreAttribute](frlrfSystemXmlSerializationSoapIgnoreAttributeClassTopic)|Открытые свойства и поля.|Свойство или поле должно игнорироваться при сериализации содержащего его класса.|  
|[SoapIncludeAttribute](frlrfSystemXmlSerializationSoapIncludeAttributeClassTopic)|Объявления открытых производных классов и открытые методы для документов WSDL.|При создании схем должен быть включен тип \(чтобы его можно было распознать во время сериализации\).|  
|[SoapTypeAttribute](frlrfSystemXmlSerializationSoapTypeAttributeClassTopic)|Объявления открытых классов.|Класс должен быть сериализован как тип XML.|  
  
## См. также  
 [XML\- и SOAP\-сериализация](../../../docs/framework/serialization/xml-and-soap-serialization.md)   
 [Как сериализовать объект как поток XML с кодировкой SOAP](../../../docs/framework/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)   
 [Как переопределить XML\-сериализацию с кодировкой SOAP](../../../docs/framework/serialization/how-to-override-encoded-soap-xml-serialization.md)   
 [Атрибуты](../../../docs/standard/attributes/index.md)   
 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)   
 [Как сериализовать объект](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [Как десериализовать объект](../../../docs/framework/serialization/how-to-deserialize-an-object.md)