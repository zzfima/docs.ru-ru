---
title: "Элемент &lt;schemaImporterExtensions&gt; | Microsoft Docs"
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
  - "<schemaImporterExtensions>, элемент"
  - "элемент schemaImporterExtensions"
  - "XML-сериализация, конфигурация"
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Элемент &lt;schemaImporterExtensions&gt;
Содержит типы, которые использует <xref:System.Xml.Serialization.XmlSchemaImporter> для сопоставления типов XSD с типами .NET Framework.  Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md).  
  
## Синтаксис  
  
```  
  
<schemaImporterExtensions>  
    <!-- Add types -->  
</SchemaImporterExtension>  
```  
  
## Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[Элемент \<add\> для элемента \<xmlSchemaImporterExtensions\>](../../../docs/framework/serialization/add-element-for-xmlschemaimporterextensions.md)|Добавляет типы, используемые <xref:System.Xml.Serialization.XmlSchemaImporter> для создания сопоставлений.|  
  
## Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[Элемент \<system.xml.serialization\>](../../../docs/framework/serialization/system-xml-serialization-element.md)|Элемент верхнего уровня для управления XML\-сериализацией.|  
  
## Пример  
 В следующем примере кода показано, как добавлять типы, используемые <xref:System.Xml.Serialization.XmlSchemaImporter> при сопоставлении типов XSD с типами .NET Framework.  
  
```  
<system.xml.serialization>  
    <schemaImporterExtensions>  
        <add name = "MobileCapabilities" type =   
        "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
/system.sxml.serializaiton>  
```  
  
## См. также  
 <xref:System.Xml.Serialization.XmlSchemaImporter>   
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>   
 [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md)   
 [Элемент \<dateTimeSerialization\>](../../../docs/framework/serialization/datetimeserialization-element.md)   
 [Элемент \<add\> для элемента \<xmlSchemaImporterExtensions\>](../../../docs/framework/serialization/add-element-for-xmlschemaimporterextensions.md)   
 [Элемент \<system.xml.serialization\>](../../../docs/framework/serialization/system-xml-serialization-element.md)