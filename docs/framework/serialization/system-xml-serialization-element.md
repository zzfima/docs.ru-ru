---
title: "Элемент &lt;system.xml.serialization&gt; | Microsoft Docs"
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
  - "<system.xml.serialization>, элемент"
  - "элемент system.xml.serialization"
  - "XML-сериализация, конфигурация"
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Элемент &lt;system.xml.serialization&gt;
Элемент верхнего уровня для управления XML\-сериализацией.  Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md).  
  
## Синтаксис  
  
```  
  
<system.xml.serialization>  
</system.xml.serialization>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Отсутствует.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[Элемент \<dateTimeSerialization\>](../../../docs/framework/serialization/datetimeserialization-element.md)|Определяет режим сериализации объектов <xref:System.DateTime>.|  
|[Элемент \<schemaImporterExtensions\>](../../../docs/framework/serialization/schemaimporterextensions-element.md)|Содержит типы, которые использует <xref:System.Xml.Serialization.XmlSchemaImporter> для сопоставления типов XSD с типами .NET Framework.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[Элемент \<configuration\>](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Корневой элемент в любом файле конфигурации, который используется средой CLR и приложениями .NET Framework.|  
  
## Пример  
 В следующем примере кода показан способ указания режима сериализации объекта <xref:System.DateTime> и добавление типов, используемых <xref:System.Xml.Serialization.XmlSchemaImporter> при сопоставлении типов XSD с типами .NET Framework.  
  
```  
<system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
    <dateTimeSerialization mode = "Local" />  
    <schemaImporterExtensions>  
        <add   
        name = "MobileCapabilities"   
        type = "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neuutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.sxml.serialization>  
```  
  
## См. также  
 <xref:System.Xml.Serialization.XmlSchemaImporter>   
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>   
 [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md)   
 [Элемент \<dateTimeSerialization\>](../../../docs/framework/serialization/datetimeserialization-element.md)   
 [Элемент \<schemaImporterExtensions\>](../../../docs/framework/serialization/schemaimporterextensions-element.md)   
 [Элемент \<add\> для элемента \<xmlSchemaImporterExtensions\>](../../../docs/framework/serialization/add-element-for-xmlschemaimporterextensions.md)