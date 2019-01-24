---
title: Элемент &lt;schemaImporterExtensions&gt;
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: dbe85ea817a597db84ddad530d67b1c2b7953f75
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535376"
---
# <a name="ltschemaimporterextensionsgt-element"></a>Элемент &lt;schemaImporterExtensions&gt;
Содержит типы, которые использует <xref:System.Xml.Serialization.XmlSchemaImporter> для сопоставления типов XSD с типами .NET Framework. Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Добавить > элемент для \<schemaImporterExtensions >](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)|Добавляет типы, используемые <xref:System.Xml.Serialization.XmlSchemaImporter> для создания сопоставлений.|  
  
## <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[Элемент \<system.xml.serialization>](../../../docs/standard/serialization/system-xml-serialization-element.md)|Элемент верхнего уровня для управления XML-сериализацией.|  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как добавлять типы, используемые <xref:System.Xml.Serialization.XmlSchemaImporter> при сопоставлении типов XSD с типами .NET Framework.  
  
```xml  
<system.xml.serialization>  
    <schemaImporterExtensions>  
        <add name = "MobileCapabilities" type =   
        "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.xml.serialization>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md)
- [Элемент \<dateTimeSerialization>](../../../docs/standard/serialization/datetimeserialization-element.md)
- [\<Добавить > элемент для \<schemaImporterExtensions >](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [Элемент \<system.xml.serialization>](../../../docs/standard/serialization/system-xml-serialization-element.md)
