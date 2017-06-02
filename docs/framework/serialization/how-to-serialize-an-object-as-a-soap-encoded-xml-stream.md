---
title: "Как сериализовать объект как поток XML с кодировкой SOAP | Microsoft Docs"
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
  - "сериализация, SOAP"
  - "SOAP, XML-сериализация"
  - "XML-сериализация, SOAP"
ms.assetid: af406e0a-fa3a-46dd-a7ba-c80731eba3a0
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Как сериализовать объект как поток XML с кодировкой SOAP
[Пример кода](#cpconxmlserializationusingsoapprotocolanchor1)  
  
 Поскольку сообщение SOAP построено с использованием XML, [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx) можно использовать для сериализации классов и созданию сообщений с кодировкой SOAP.Полученный в результате XML соответствует разделу 5 документа "Simple Object Access Protocol \(SOAP\) 1.1", разработанного консорциумом World Wide Web \(www.w3.org\).При создании XML\-веб\-службы, которая осуществляет связь посредством сообщений SOAP, можно настроить поток XML, применив к классам и членам классов набор специальных атрибутов SOAP.Список атрибутов см. в разделе [Атрибуты управления SOAP\-сериализацией с кодировкой](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md).  
  
### Чтобы сериализовать объект как поток XML с кодировкой SOAP  
  
1.  Создайте класс с помощью [Инструмент определения схемы XML \(Xsd.exe\)](../../../docs/framework/serialization/xml-schema-definition-tool-xsd-exe.md).  
  
2.  Примените один или несколько специальных атрибутов из **System.Xml.Serialization**.Список атрибутов см. в разделе "Атрибуты управления сериализацией с кодировкой SOAP".  
  
3.  Создайте **XmlTypeMapping** путем создания нового **SoapReflectionImporter** и вызова метода **ImportTypeMapping** с типом сериализуемого класса.  
  
     В следующем примере кода вызывается метод **ImportTypeMapping**класса **SoapReflectionImporter** для создания **XmlTypeMapping**.  
  
    ```vb  
    ' Serializes a class named Group as a SOAP message.  
    Dim myTypeMapping As XmlTypeMapping = (New SoapReflectionImporter(). _  
    ImportTypeMapping(GetType(Group))  
  
    ```  
  
    ```csharp  
    // Serializes a class named Group as a SOAP message.  
    XmlTypeMapping myTypeMapping = (new SoapReflectionImporter().  
    ImportTypeMapping(typeof(Group));  
    ```  
  
4.  Создайте экземпляр класса **XmlSerializer**, передав **XmlTypeMapping** конструктору <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29>.  
  
    ```vb  
    Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
  
    ```  
  
    ```csharp  
    XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
    ```  
  
5.  Вызовите метод **Serialize** или **Deserialize**.  
  
## Пример  
  
```vb  
' Serializes a class named Group as a SOAP message.  
Dim myTypeMapping As XmlTypeMapping = (New SoapReflectionImporter(). _  
ImportTypeMapping(GetType(Group))  
Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
  
```  
  
```csharp  
// Serializes a class named Group as a SOAP message.  
XmlTypeMapping myTypeMapping = (new SoapReflectionImporter().ImportTypeMapping(typeof(Group));  
XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
```  
  
## См. также  
 [XML\- и SOAP\-сериализация](../../../docs/framework/serialization/xml-and-soap-serialization.md)   
 [Атрибуты управления SOAP\-сериализацией с кодировкой](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md)   
 [XML\-сериализация с использованием XML\-веб\-служб](../../../docs/framework/serialization/xml-serialization-with-xml-web-services.md)   
 [Как сериализовать объект](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [Как десериализовать объект](../../../docs/framework/serialization/how-to-deserialize-an-object.md)   
 [Как переопределить XML\-сериализацию с кодировкой SOAP](../../../docs/framework/serialization/how-to-override-encoded-soap-xml-serialization.md)