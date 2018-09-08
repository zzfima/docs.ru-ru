---
title: Атрибуты управления сериализацией с кодировкой SOAP
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- XML serialization, attributes
- attributes [.NET Framework], XML serialization
- serialization, attributes
ms.assetid: 93ee258c-9c0f-4a08-897c-c10db7a00f91
ms.openlocfilehash: 7b5a48003ff9bfb398c05c8d70a9076d49ad83d6
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44222309"
---
# <a name="attributes-that-control-encoded-soap-serialization"></a>Атрибуты управления сериализацией с кодировкой SOAP

Документ World Wide Web Consortium (W3C), с именем [Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/) содержится дополнительный раздел (раздел 5), описывающее способы кодирования параметров SOAP. Для соответствия разделу 5 спецификации следует использовать специальный набор атрибутов, расположенный в пространстве имен <xref:System.Xml.Serialization>. Примените эти атрибуты для соответствующих классов и членов классов, а затем используйте <xref:System.Xml.Serialization.XmlSerializer> для сериализации экземпляров класса или классов.

В следующей таблице показаны атрибуты, место их применения и выполняемые ими действия. Дополнительные сведения об использовании этих атрибутов для управления XML-сериализации см. в разделах [Практическое руководство. Сериализация объекта как потока XML с кодировкой SOAP](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) и [Практическое руководство. Переопределение сериализации XML с кодировкой SOAP](how-to-override-encoded-soap-xml-serialization.md).

Дополнительные сведения об атрибутах см. в разделе [Атрибуты](../../../docs/standard/attributes/index.md).

|Атрибут|Применение|Что определяет|
|---------------|----------------|---------------|
|<xref:System.Xml.Serialization.SoapAttributeAttribute>|Открытое поле, свойство, параметр или возвращаемое значение.|Член класса должен быть сериализован как атрибут XML.|
|<xref:System.Xml.Serialization.SoapElementAttribute>|Открытое поле, свойство, параметр или возвращаемое значение.|Класс должен быть сериализован как элемент XML.|
|<xref:System.Xml.Serialization.SoapEnumAttribute>|Открытое поле, являющееся идентификатором перечисления.|Имя элемента члена перечисления.|
|<xref:System.Xml.Serialization.SoapIgnoreAttribute>|Открытые свойства и поля.|Свойство или поле должно игнорироваться при сериализации содержащего его класса.|
|<xref:System.Xml.Serialization.SoapIncludeAttribute>|Объявления открытых производных классов и открытые методы для документов WSDL.|При создании схем должен быть включен тип (чтобы его можно было распознать во время сериализации).|
|<xref:System.Xml.Serialization.SoapTypeAttribute>|Объявления открытых классов.|Класс должен быть сериализован как тип XML.|

## <a name="see-also"></a>См. также

- [Сериализация XML и SOAP](xml-and-soap-serialization.md)  
- [Практическое руководство. Сериализация объекта как потока XML с кодировкой SOAP](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
- [Практическое руководство. Переопределение сериализации XML с кодировкой SOAP](how-to-override-encoded-soap-xml-serialization.md)  
- [Атрибуты](../../../docs/standard/attributes/index.md)  
- <xref:System.Xml.Serialization.XmlSerializer>  
- [Практическое руководство. Сериализация объекта](how-to-serialize-an-object.md)  
- [Практическое руководство. Десериализация объекта](how-to-deserialize-an-object.md)
