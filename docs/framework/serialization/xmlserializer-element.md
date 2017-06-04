---
title: "Элемент &lt;xmlSerializer&gt; | Microsoft Docs"
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
  - "<xmlSerializer>, элемент"
  - "XML-сериализация, конфигурация"
  - "xmlSerializer, элемент"
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Элемент &lt;xmlSerializer&gt;
Указывает, выполнена ли дополнительная проверка хода выполнения <xref:System.Xml.Serialization.XmlSerializer>.  
  
## Синтаксис  
  
```  
  
<xmlSerializer checkDeserializerAdvance = "true"|"false" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|**checkDeserializeAdvances**|Указывает, выполнена ли проверка хода выполнения <xref:System.Xml.Serialization.XmlSerializer>.  Присвойте атрибуту значение "true" или "false".  Значение по умолчанию \- "true".|  
|**useLegacySerializationGeneration**|Укажите, следует ли объекту <xref:System.Xml.Serialization.XmlSerializer> использовать установленную сериализацию прежней версии, которая создает сборки путем написания кода на C\# в файле и компиляции его в сборку.  Значение по умолчанию — **false**.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[Элемент \<system.xml.serialization\>](../../../docs/framework/serialization/system-xml-serialization-element.md)|Содержит параметры конфигурации для классов <xref:System.Xml.Serialization.XmlSerializer> и <xref:System.Xml.Serialization.XmlSchemaImporter>.|  
  
## Заметки  
 По умолчанию <xref:System.Xml.Serialization.XmlSerializer> обеспечивает дополнительный уровень безопасности в отношении возможных атак типа "отказ в обслуживании" во время десериализации ненадежных данных.  Такие атаки отслеживаются путем определения бесконечных циклов во время десериализации.  Если обнаруживается такое состояние, выводится исключение со следующим сообщением: “Internal error: deserialization failed to advance over underlying stream” \(Внутренняя ошибка: ошибка продолжения десериализации по основному потоку\).  
  
 Такое сообщение еще не означает, что система подвергается атаке типа "отказ в обслуживании".  В редких случаях механизм определения бесконечного цикла сообщает о ложном положительном результате, и выдается исключение для допустимых входящих сообщений.  Если обнаружится, что некоторые допустимые сообщения определенных приложений отклоняются из\-за использования такого дополнительного уровня защиты, задайте атрибут **checkDeserializeAdvances** как "false".  
  
## Пример  
 В следующем примере кода атрибут **checkDeserializeAdvances** задан как "false".  
  
```  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## См. также  
 <xref:System.Xml.Serialization.XmlSerializer>   
 [Элемент \<system.xml.serialization\>](../../../docs/framework/serialization/system-xml-serialization-element.md)   
 [XML\- и SOAP\-сериализация](../../../docs/framework/serialization/xml-and-soap-serialization.md)