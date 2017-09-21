---
title: "Практическое руководство. Сериализация объекта как потока XML с кодировкой SOAP"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
ms.assetid: af406e0a-fa3a-46dd-a7ba-c80731eba3a0
caps.latest.revision: 6
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: 84bdce1e7a877425a38a980ba306d38573add227
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-serialize-an-object-as-a-soap-encoded-xml-stream"></a>Практическое руководство. Сериализация объекта как потока XML с кодировкой SOAP
  
 Поскольку сообщение SOAP сформировано с использованием XML, можно использовать <xref:System.Xml.Serialization.XmlSerializer> для сериализации классов и генерации сообщений с кодировкой SOAP. Полученный в результате код XML соответствует [разделу 5 документа "Simple Object Access Protocol (SOAP) 1.1", разработанного консорциумом W3С](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512). При создании XML-веб-службы, которая осуществляет связь посредством сообщений SOAP, можно настроить поток XML, применив к классам и членам классов набор специальных атрибутов SOAP. Список атрибутов см. в разделе [Атрибуты, которые управляют сериализацией с кодировкой SOAP](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).  
  
### <a name="to-serialize-an-object-as-a-soap-encoded-xml-stream"></a>Чтобы сериализовать объект как поток XML с кодировкой SOAP  
  
1.  Создайте класс с помощью [средства определения схемы XML (xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).  
  
2.  Примените один или несколько специальных атрибутов из `System.Xml.Serialization`. Список атрибутов см. в разделе "Атрибуты управления сериализацией с кодировкой SOAP".  
  
3.  Создайте `XmlTypeMapping` путем создания нового `SoapReflectionImporter` и вызова метода `ImportTypeMapping` с типом сериализуемого класса.  
  
     В следующем примере кода вызывается метод `ImportTypeMapping` класса `SoapReflectionImporter` для создания `XmlTypeMapping`.  
  
    ```vb  
    ' Serializes a class named Group as a SOAP message.  
    Dim myTypeMapping As XmlTypeMapping =
        New SoapReflectionImporter().ImportTypeMapping(GetType(Group))  
    ```  
  
    ```csharp  
    // Serializes a class named Group as a SOAP message.  
    XmlTypeMapping myTypeMapping =
        new SoapReflectionImporter().ImportTypeMapping(typeof(Group));
    ```  
  
4.  Создайте экземпляр класса `XmlSerializer`, передав `XmlTypeMapping` конструктору <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29>.  
  
    ```vb  
    Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
    ```  
  
    ```csharp  
    XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
    ```  
  
5.  Вызовите метод `Serialize` или `Deserialize`.  
  
## <a name="example"></a>Пример  
  
```vb  
' Serializes a class named Group as a SOAP message.  
Dim myTypeMapping As XmlTypeMapping =
    New SoapReflectionImporter().ImportTypeMapping(GetType(Group))
Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
```  
  
```csharp  
// Serializes a class named Group as a SOAP message.  
XmlTypeMapping myTypeMapping =
    new SoapReflectionImporter().ImportTypeMapping(typeof(Group));
XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
```  
  
## <a name="see-also"></a>См. также  
 [Сериализация XML и SOAP](../../../docs/standard/serialization/xml-and-soap-serialization.md)   
 [Атрибуты управления сериализацией с кодировкой SOAP](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)   
 [Сериализация XML с использованием XML-веб-служб](../../../docs/standard/serialization/xml-serialization-with-xml-web-services.md)   
 [Практическое руководство. Сериализация объекта](../../../docs/standard/serialization/how-to-serialize-an-object.md)   
 [Практическое руководство. Десериализация объекта](../../../docs/standard/serialization/how-to-deserialize-an-object.md)   
 [Практическое руководство. Переопределение сериализации XML с кодировкой SOAP](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md)

