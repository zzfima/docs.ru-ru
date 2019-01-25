---
title: Элемент &lt;system.xml.serialization&gt;
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: 8b85eef0f2c3bbb2d0d4a5548f5cbb4a66b0431d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54609568"
---
# <a name="ltsystemxmlserializationgt-element"></a><span data-ttu-id="21489-102">Элемент &lt;system.xml.serialization&gt;</span><span class="sxs-lookup"><span data-stu-id="21489-102">&lt;system.xml.serialization&gt; Element</span></span>
<span data-ttu-id="21489-103">Элемент верхнего уровня для управления XML-сериализацией.</span><span class="sxs-lookup"><span data-stu-id="21489-103">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="21489-104">Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="21489-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="21489-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="21489-105">\<configuration></span></span>  
<span data-ttu-id="21489-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="21489-106">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21489-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21489-107">Syntax</span></span>  
  
```xml  
<system.xml.serialization>  
</system.xml.serialization>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21489-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="21489-108">Attributes and Elements</span></span>  
 <span data-ttu-id="21489-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="21489-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21489-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="21489-110">Attributes</span></span>  
 <span data-ttu-id="21489-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="21489-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="21489-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="21489-112">Child Elements</span></span>  
  
|<span data-ttu-id="21489-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="21489-113">Element</span></span>|<span data-ttu-id="21489-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="21489-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21489-115">Элемент \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="21489-115">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)|<span data-ttu-id="21489-116">Определяет режим сериализации объектов <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="21489-116">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|  
|[<span data-ttu-id="21489-117">Элемент \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="21489-117">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)|<span data-ttu-id="21489-118">Содержит типы, которые использует <xref:System.Xml.Serialization.XmlSchemaImporter> для сопоставления типов XSD с типами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="21489-118">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="21489-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="21489-119">Parent Elements</span></span>  
  
|<span data-ttu-id="21489-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="21489-120">Element</span></span>|<span data-ttu-id="21489-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="21489-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21489-122">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="21489-122">\<configuration> Element</span></span>](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="21489-123">Корневой элемент в любом файле конфигурации, который используется средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="21489-123">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="21489-124">Пример</span><span class="sxs-lookup"><span data-stu-id="21489-124">Example</span></span>  
 <span data-ttu-id="21489-125">В следующем примере кода показан способ указания режима сериализации объекта <xref:System.DateTime> и добавление типов, используемых <xref:System.Xml.Serialization.XmlSchemaImporter> при сопоставлении типов XSD с типами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="21489-125">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="21489-126">См. также</span><span class="sxs-lookup"><span data-stu-id="21489-126">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="21489-127">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="21489-127">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="21489-128">Элемент \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="21489-128">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)
- [<span data-ttu-id="21489-129">Элемент \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="21489-129">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [<span data-ttu-id="21489-130">\<Добавить > элемент для \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="21489-130">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
