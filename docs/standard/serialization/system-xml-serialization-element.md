---
title: "Элемент &lt;system.xml.serialization&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cfc2b38eba68a8c7f9ddab4a6ee941f6faee7c02
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltsystemxmlserializationgt-element"></a><span data-ttu-id="6d6c2-102">Элемент &lt;system.xml.serialization&gt;</span><span class="sxs-lookup"><span data-stu-id="6d6c2-102">&lt;system.xml.serialization&gt; Element</span></span>
<span data-ttu-id="6d6c2-103">Элемент верхнего уровня для управления XML-сериализацией.</span><span class="sxs-lookup"><span data-stu-id="6d6c2-103">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="6d6c2-104">Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="6d6c2-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="6d6c2-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6d6c2-105">\<configuration></span></span>  
<span data-ttu-id="6d6c2-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="6d6c2-106">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d6c2-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d6c2-107">Syntax</span></span>  
  
```xml  
<system.xml.serialization>  
</system.xml.serialization>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6d6c2-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6d6c2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6d6c2-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6d6c2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6d6c2-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6d6c2-110">Attributes</span></span>  
 <span data-ttu-id="6d6c2-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6d6c2-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6d6c2-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6d6c2-112">Child Elements</span></span>  
  
|<span data-ttu-id="6d6c2-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="6d6c2-113">Element</span></span>|<span data-ttu-id="6d6c2-114">Описание</span><span class="sxs-lookup"><span data-stu-id="6d6c2-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6d6c2-115">Элемент \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="6d6c2-115">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)|<span data-ttu-id="6d6c2-116">Определяет режим сериализации объектов <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="6d6c2-116">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|  
|[<span data-ttu-id="6d6c2-117">Элемент \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="6d6c2-117">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)|<span data-ttu-id="6d6c2-118">Содержит типы, которые использует <xref:System.Xml.Serialization.XmlSchemaImporter> для сопоставления типов XSD с типами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6d6c2-118">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6d6c2-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6d6c2-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6d6c2-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="6d6c2-120">Element</span></span>|<span data-ttu-id="6d6c2-121">Описание</span><span class="sxs-lookup"><span data-stu-id="6d6c2-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6d6c2-122">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="6d6c2-122">\<configuration> Element</span></span>](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="6d6c2-123">Корневой элемент в любом файле конфигурации, который используется средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6d6c2-123">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6d6c2-124">Пример</span><span class="sxs-lookup"><span data-stu-id="6d6c2-124">Example</span></span>  
 <span data-ttu-id="6d6c2-125">В следующем примере кода показан способ указания режима сериализации объекта <xref:System.DateTime> и добавление типов, используемых <xref:System.Xml.Serialization.XmlSchemaImporter> при сопоставлении типов XSD с типами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6d6c2-125">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
```xml  
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
  
## <a name="see-also"></a><span data-ttu-id="6d6c2-126">См. также</span><span class="sxs-lookup"><span data-stu-id="6d6c2-126">See Also</span></span>  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
 [<span data-ttu-id="6d6c2-127">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="6d6c2-127">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="6d6c2-128">Элемент \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="6d6c2-128">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)  
 [<span data-ttu-id="6d6c2-129">Элемент \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="6d6c2-129">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
 [<span data-ttu-id="6d6c2-130">Элемент \<add> для элемента \<xmlSchemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="6d6c2-130">\<add> Element for \<xmlSchemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)
