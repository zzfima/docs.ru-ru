---
title: Элемент <schemaImporterExtensions>
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: 5ed80ac370e34d6b62bb2b601cb7bd978228a302
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159823"
---
# <a name="schemaimporterextensions-element"></a><span data-ttu-id="7e0ab-102">\<элемент schemaimporterextensions > элемент</span><span class="sxs-lookup"><span data-stu-id="7e0ab-102">\<schemaImporterExtensions> Element</span></span>
<span data-ttu-id="7e0ab-103">Содержит типы, которые использует <xref:System.Xml.Serialization.XmlSchemaImporter> для сопоставления типов XSD с типами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7e0ab-103">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span> <span data-ttu-id="7e0ab-104">Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="7e0ab-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e0ab-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e0ab-105">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="7e0ab-106">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7e0ab-106">Child Elements</span></span>  
  
|<span data-ttu-id="7e0ab-107">Элемент</span><span class="sxs-lookup"><span data-stu-id="7e0ab-107">Element</span></span>|<span data-ttu-id="7e0ab-108">Description</span><span class="sxs-lookup"><span data-stu-id="7e0ab-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e0ab-109">\<добавить элемент > для \<элемент schemaimporterextensions ></span><span class="sxs-lookup"><span data-stu-id="7e0ab-109">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)|<span data-ttu-id="7e0ab-110">Добавляет типы, используемые <xref:System.Xml.Serialization.XmlSchemaImporter> для создания сопоставлений.</span><span class="sxs-lookup"><span data-stu-id="7e0ab-110">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="7e0ab-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7e0ab-111">Parent Elements</span></span>  
  
|<span data-ttu-id="7e0ab-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="7e0ab-112">Element</span></span>|<span data-ttu-id="7e0ab-113">Description</span><span class="sxs-lookup"><span data-stu-id="7e0ab-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e0ab-114">Элемент \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="7e0ab-114">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="7e0ab-115">Элемент верхнего уровня для управления XML-сериализацией.</span><span class="sxs-lookup"><span data-stu-id="7e0ab-115">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7e0ab-116">Пример</span><span class="sxs-lookup"><span data-stu-id="7e0ab-116">Example</span></span>  
 <span data-ttu-id="7e0ab-117">В следующем примере кода показано, как добавлять типы, используемые <xref:System.Xml.Serialization.XmlSchemaImporter> при сопоставлении типов XSD с типами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7e0ab-117">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7e0ab-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7e0ab-118">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="7e0ab-119">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="7e0ab-119">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="7e0ab-120">Элемент \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="7e0ab-120">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)
- [<span data-ttu-id="7e0ab-121">\<добавить элемент > для \<элемент schemaimporterextensions ></span><span class="sxs-lookup"><span data-stu-id="7e0ab-121">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="7e0ab-122">Элемент \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="7e0ab-122">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
