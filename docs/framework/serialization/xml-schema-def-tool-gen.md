---
title: "Как использовать инструмент определения схемы XML для создания классов и документов схемы XML | Microsoft Docs"
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
  - "создание классов XML с использованием инструмента определения схемы XML"
  - "создание документа схемы XML с использованием инструмента определения схемы XML"
  - "инструмент определения схемы XML, использование для создания классов, соответствующих определенной схеме"
  - "инструмент определения схемы XML, использование для создания документа схемы XML"
ms.assetid: 51f0edc3-993d-4051-b7f2-77753694d3d1
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Как использовать инструмент определения схемы XML для создания классов и документов схемы XML
С помощью инструмента определения схемы XML \(Xsd.exe\) можно создать схему XML, которая описывает класс, или создать класс, определенный схемой XML.В процедурах ниже показана методика выполнения таких операций.  
  
### Создание классов, соответствующих определенной схеме  
  
1.  Откройте окно командной строки.  
  
2.  Передайте схему XML как аргумент в инструмент определения схемы XML, который создаст набор классов, точно соответствующих схеме XML, например:  
  
    ```  
    xsd mySchema.xsd  
    ```  
  
     Средство может обрабатывать только схемы, которые ссылаются на спецификацию XML консорциума W3C от 16 марта 2001 г.Иными словами, пространство имен схемы XML должно иметь вид «http:\/\/www.w3.org\/2001\/XMLSchema», как показано в следующем примере.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <xs:schema attributeFormDefault="qualified" elementFormDefault="qualified" targetNamespace="" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    ```  
  
3.  При необходимости измените классы с методами, свойствами или полями.Дополнительные сведения об изменении класса с атрибутами см. в разделах [Управление XML\-сериализацией с использованием атрибутов](../../../docs/framework/serialization/controlling-xml-serialization-using-attributes.md) и [Атрибуты управления SOAP\-сериализацией с кодировкой](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md).  
  
 Часто бывает полезным изучить схему потока XML, которая генерируется при сериализации экземпляров класса \(или классов\).Например, можно опубликовать схему для совместного использования или сравнить ее со схемой, в которой предпринимается попытка обеспечения соответствия.  
  
#### Создание документа схемы XML из набора классов  
  
1.  Скомпилируйте класс или классы в библиотеку DLL.  
  
2.  Откройте окно командной строки.  
  
3.  Передайте библиотеку DLL как аргумент в Xsd.exe, например:  
  
    ```  
    xsd MyFile.dll  
    ```  
  
     В результате записывается схема \(или схемы\), которая начинается с имени "schema0.xsd".  
  
## См. также  
 [Инструмент определения схемы XML и сериализация XML](../../../docs/framework/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)   
 [Введение в XML\-сериализацию](../../../docs/framework/serialization/introducing-xml-serialization.md)   
 [DataSet](frlrfSystemDataDataSetClassTopic)   
 [Инструмент определения схемы XML \(Xsd.exe\)](../../../docs/framework/serialization/xml-schema-definition-tool-xsd-exe.md)   
 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)   
 [Как сериализовать объект](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [Как десериализовать объект](../../../docs/framework/serialization/how-to-deserialize-an-object.md)