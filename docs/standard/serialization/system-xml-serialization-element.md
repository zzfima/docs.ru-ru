---
title: Элемент <system.xml.serialization>
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: f41e3811fc6bab8a354f75f46b0ac79c0ce42f99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62018090"
---
# <a name="systemxmlserialization-element"></a><span data-ttu-id="ff032-102">\<System.XML.Serialization > элемент</span><span class="sxs-lookup"><span data-stu-id="ff032-102">\<system.xml.serialization> Element</span></span>
<span data-ttu-id="ff032-103">Элемент верхнего уровня для управления XML-сериализацией.</span><span class="sxs-lookup"><span data-stu-id="ff032-103">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="ff032-104">Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="ff032-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="ff032-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ff032-105">\<configuration></span></span>  
<span data-ttu-id="ff032-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="ff032-106">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff032-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff032-107">Syntax</span></span>  
  
```xml  
<system.xml.serialization>  
</system.xml.serialization>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff032-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ff032-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ff032-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ff032-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff032-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ff032-110">Attributes</span></span>  
 <span data-ttu-id="ff032-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ff032-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ff032-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ff032-112">Child Elements</span></span>  
  
|<span data-ttu-id="ff032-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="ff032-113">Element</span></span>|<span data-ttu-id="ff032-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ff032-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff032-115">Элемент \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="ff032-115">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)|<span data-ttu-id="ff032-116">Определяет режим сериализации объектов <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="ff032-116">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|  
|[<span data-ttu-id="ff032-117">Элемент \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="ff032-117">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)|<span data-ttu-id="ff032-118">Содержит типы, которые использует <xref:System.Xml.Serialization.XmlSchemaImporter> для сопоставления типов XSD с типами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ff032-118">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ff032-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ff032-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ff032-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="ff032-120">Element</span></span>|<span data-ttu-id="ff032-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="ff032-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff032-122">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="ff032-122">\<configuration> Element</span></span>](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="ff032-123">Корневой элемент в любом файле конфигурации, который используется средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ff032-123">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ff032-124">Пример</span><span class="sxs-lookup"><span data-stu-id="ff032-124">Example</span></span>  
 <span data-ttu-id="ff032-125">В следующем примере кода показан способ указания режима сериализации объекта <xref:System.DateTime> и добавление типов, используемых <xref:System.Xml.Serialization.XmlSchemaImporter> при сопоставлении типов XSD с типами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ff032-125">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ff032-126">См. также</span><span class="sxs-lookup"><span data-stu-id="ff032-126">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="ff032-127">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="ff032-127">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="ff032-128">Элемент \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="ff032-128">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)
- [<span data-ttu-id="ff032-129">Элемент \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="ff032-129">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [<span data-ttu-id="ff032-130">\<Добавить > элемент для \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="ff032-130">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
