---
title: Элемент &lt;system.xml.serialization&gt;
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: b67c1ec1ec737976e4e50b80b42f34e508dc0224
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44133312"
---
# <a name="ltsystemxmlserializationgt-element"></a><span data-ttu-id="bd202-102">Элемент &lt;system.xml.serialization&gt;</span><span class="sxs-lookup"><span data-stu-id="bd202-102">&lt;system.xml.serialization&gt; Element</span></span>
<span data-ttu-id="bd202-103">Элемент верхнего уровня для управления XML-сериализацией.</span><span class="sxs-lookup"><span data-stu-id="bd202-103">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="bd202-104">Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="bd202-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="bd202-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bd202-105">\<configuration></span></span>  
<span data-ttu-id="bd202-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="bd202-106">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd202-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd202-107">Syntax</span></span>  
  
```xml  
<system.xml.serialization>  
</system.xml.serialization>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd202-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bd202-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bd202-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bd202-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd202-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bd202-110">Attributes</span></span>  
 <span data-ttu-id="bd202-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bd202-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bd202-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bd202-112">Child Elements</span></span>  
  
|<span data-ttu-id="bd202-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="bd202-113">Element</span></span>|<span data-ttu-id="bd202-114">Описание</span><span class="sxs-lookup"><span data-stu-id="bd202-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd202-115">Элемент \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="bd202-115">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)|<span data-ttu-id="bd202-116">Определяет режим сериализации объектов <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="bd202-116">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|  
|[<span data-ttu-id="bd202-117">Элемент \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="bd202-117">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)|<span data-ttu-id="bd202-118">Содержит типы, которые использует <xref:System.Xml.Serialization.XmlSchemaImporter> для сопоставления типов XSD с типами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bd202-118">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bd202-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bd202-119">Parent Elements</span></span>  
  
|<span data-ttu-id="bd202-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="bd202-120">Element</span></span>|<span data-ttu-id="bd202-121">Описание</span><span class="sxs-lookup"><span data-stu-id="bd202-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd202-122">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="bd202-122">\<configuration> Element</span></span>](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="bd202-123">Корневой элемент в любом файле конфигурации, который используется средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bd202-123">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bd202-124">Пример</span><span class="sxs-lookup"><span data-stu-id="bd202-124">Example</span></span>  
 <span data-ttu-id="bd202-125">В следующем примере кода показан способ указания режима сериализации объекта <xref:System.DateTime> и добавление типов, используемых <xref:System.Xml.Serialization.XmlSchemaImporter> при сопоставлении типов XSD с типами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bd202-125">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bd202-126">См. также</span><span class="sxs-lookup"><span data-stu-id="bd202-126">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>  
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
- [<span data-ttu-id="bd202-127">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="bd202-127">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="bd202-128">Элемент \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="bd202-128">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)  
- [<span data-ttu-id="bd202-129">Элемент \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="bd202-129">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
- [<span data-ttu-id="bd202-130">\<Добавить > элемент для \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="bd202-130">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
