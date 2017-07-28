---
title: "Элемент &lt;dateTimeSerialization&gt; | Microsoft Docs"
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
  - "<dateTimeSerialization>, элемент"
  - "элемент dateTimeSerialization"
  - "XML-сериализация, конфигурация"
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Элемент &lt;dateTimeSerialization&gt;
Определяет режим сериализации объектов <xref:System.DateTime>.  
  
## Синтаксис  
  
```  
  
<dateTimeSerialization  
    mode = "Roundtrip" | "Local"  
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибуты|Описание|  
|--------------|--------------|  
|`mode`|Необязательно.  Задает режим сериализации.  Задайте одно из значений <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>.  Значение по умолчанию — **RoundTrip**.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|system.xml.serialization|Элемент верхнего уровня для управления XML\-сериализацией.|  
  
## Заметки  
 В платформе .NET Framework версий 1.0, 1.1 и 2.0 и более поздних при задании для этого свойства значения **Local** объекты <xref:System.DateTime> всегда форматируются как местное время.  Это значит, что в сериализованные данные всегда включается информация о местном часовом поясе.  Присвоение этому свойству значения **Local** обеспечивает совместимость с предыдущими версиями платформы .NET Framework.  
  
 В платформе .NET Framework версии 2.0 и более поздних, в которых для этого свойства задано значение **Roundtrip**, объекты <xref:System.DateTime> анализируются с целью выяснить, указан ли в них местный часовой пояс, время UTC, или часовой пояс не указан.  После этого объекты <xref:System.DateTime> сериализуются способом, обеспечивающим сохранение этой информации.  Это является поведением по умолчанию, рекомендуемым для всех новых приложений, не взаимодействующих со старыми версиями платформы .NET Framework.  
  
## См. также  
 <xref:System.DateTime>   
 <xref:System.Xml.Serialization.XmlSchemaImporter>   
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>   
 [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md)   
 [Элемент \<schemaImporterExtensions\>](../../../docs/framework/serialization/schemaimporterextensions-element.md)   
 [Элемент \<add\> для элемента \<xmlSchemaImporterExtensions\>](../../../docs/framework/serialization/add-element-for-xmlschemaimporterextensions.md)   
 [Элемент \<system.xml.serialization\>](../../../docs/framework/serialization/system-xml-serialization-element.md)