---
title: "Инструмент определения схемы XML и сериализация XML | Microsoft Docs"
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
  - "Xsd.exe"
  - "сериализация XML, инструмент определения схемы XML"
  - "инструмент определения схемы XML"
  - "сериализация, инструмент определения схемы XML"
ms.assetid: 3c03f855-f931-47ff-bbc6-50c0367a16e4
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Инструмент определения схемы XML и сериализация XML
Инструмент определения схемы XML \([Инструмент определения схемы XML \(Xsd.exe\)](../../../docs/framework/serialization/xml-schema-definition-tool-xsd-exe.md)\) устанавливается вместе со средствами .NET Framework в составе пакета средств разработки Windows® \(SDK\). Этот инструмент служит, главным образом, двум следующим целям.  
  
-   Создание файлов классов C\# или Visual Basic, соответствующих конкретной схеме языка определения схемы XML \(XSD\). Инструмент принимает схему XML как аргумент и выдает файл с числом классов, которые при сериализации с использованием [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx) соответствуют схеме. Дополнительные сведения об использовании этого инструмента для создания классов, которые соответствуют определенной схеме, см. в разделе [Как использовать инструмент определения схемы XML для создания классов и документов схемы XML](../../../docs/framework/serialization/xml-schema-def-tool-gen.md).  
  
-   Создание документа схемы XML из DLL\-файла или EXE\-файла. Чтобы просмотреть схему набора файлов, которая была создана или изменена с помощью атрибутов, передайте в инструмент файл DLL или EXE как аргумент для создания схемы XML. Сведения об использовании этого инструмента для создания документа схемы XML из набора классов см. в разделе [Как использовать инструмент определения схемы XML для создания классов и документов схемы XML](../../../docs/framework/serialization/xml-schema-def-tool-gen.md).  
  
 Дополнительные сведения об этом и других инструментах см. в разделе [Tools](../../../docs/framework/tools/index.md). Сведения о параметрах этого инструмента см. в разделе [Инструмент определения схемы XML \(Xsd.exe\)](../../../docs/framework/serialization/xml-schema-definition-tool-xsd-exe.md).  
  
## См. также  
 [Введение в XML\-сериализацию](../../../docs/framework/serialization/introducing-xml-serialization.md)   
 [DataSet](frlrfSystemDataDataSetClassTopic)   
 [Инструмент определения схемы XML \(Xsd.exe\)](../../../docs/framework/serialization/xml-schema-definition-tool-xsd-exe.md)   
 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)   
 [Как сериализовать объект](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [Как десериализовать объект](../../../docs/framework/serialization/how-to-deserialize-an-object.md)   
 [Как использовать инструмент определения схемы XML для создания классов и документов схемы XML](../../../docs/framework/serialization/xml-schema-def-tool-gen.md)   
 [Поддержка привязки схемы XML в .NET Framework](http://msdn.microsoft.com/ru-ru/8f0619dd-f1fc-4895-ae21-6d45d0382cc1)