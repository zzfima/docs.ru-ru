---
title: "Элемент &lt;add&gt; для элемента &lt;xmlSchemaImporterExtensions&gt; | Microsoft Docs"
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
  - "элемент <add> для элемента <xmlSchemaImporterExtensions>"
  - "XML-сериализация, конфигурация"
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Элемент &lt;add&gt; для элемента &lt;xmlSchemaImporterExtensions&gt;
Добавляет типы, используемые <xref:System.Xml.Serialization.XmlSchemaImporter>, для сопоставления типов XSD с типами платформы .NET Framework.  Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md).  
  
 \<XmlSchemaImporterExtensions\>  
\<add\>  
  
## Синтаксис  
  
```  
  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|**name**|Простое имя, используемое для поиска экземпляра.|  
|**type**|Обязательный.  Задает добавляемый класс расширения схемы.  Значение атрибута **type** должно располагаться на одной строке и содержать полное имя типа.  Когда сборка помещается в глобальный кэш сборок \(GAC\), она должна также содержать версию, язык и региональные параметры и маркер открытого ключа подписанной сборки.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|\<xmlSchemaImporterExtensions\>|Содержит типы, используемые классом<xref:System.Xml.Serialization.XmlSchemaImporter>.|  
  
## Пример  
 В приведенном ниже примере кода добавляется тип расширения, который XmlSchemaImporter может использовать при сопоставлении типов.  
  
```  
<configuration>  
  <system.xml.serialization>  
    <xmlSchemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,   
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,   
       PublicKeyToken=b03f5f7f11d50a3a" />   
    </xmlSchemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## См. также  
 <xref:System.Xml.Serialization.XmlSchemaImporter>   
 [Элемент \<system.xml.serialization\>](../../../docs/framework/serialization/system-xml-serialization-element.md)   
 [Элемент \<schemaImporterExtensions\>](../../../docs/framework/serialization/schemaimporterextensions-element.md)