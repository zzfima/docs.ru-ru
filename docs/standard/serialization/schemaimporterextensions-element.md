---
title: Элемент <schemaImporterExtensions>
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: 43f8439708c73e8e5241a923360caf549bf09d8b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55265312"
---
# <a name="schemaimporterextensions-element"></a><span data-ttu-id="fec4e-102">\<schemaImporterExtensions > элемент</span><span class="sxs-lookup"><span data-stu-id="fec4e-102">\<schemaImporterExtensions> Element</span></span>
<span data-ttu-id="fec4e-103">Содержит типы, которые использует <xref:System.Xml.Serialization.XmlSchemaImporter> для сопоставления типов XSD с типами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fec4e-103">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span> <span data-ttu-id="fec4e-104">Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="fec4e-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fec4e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fec4e-105">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="fec4e-106">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fec4e-106">Child Elements</span></span>  
  
|<span data-ttu-id="fec4e-107">Элемент</span><span class="sxs-lookup"><span data-stu-id="fec4e-107">Element</span></span>|<span data-ttu-id="fec4e-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="fec4e-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fec4e-109">\<Добавить > элемент для \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="fec4e-109">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)|<span data-ttu-id="fec4e-110">Добавляет типы, используемые <xref:System.Xml.Serialization.XmlSchemaImporter> для создания сопоставлений.</span><span class="sxs-lookup"><span data-stu-id="fec4e-110">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="fec4e-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fec4e-111">Parent Elements</span></span>  
  
|<span data-ttu-id="fec4e-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="fec4e-112">Element</span></span>|<span data-ttu-id="fec4e-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="fec4e-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fec4e-114">Элемент \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="fec4e-114">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="fec4e-115">Элемент верхнего уровня для управления XML-сериализацией.</span><span class="sxs-lookup"><span data-stu-id="fec4e-115">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fec4e-116">Пример</span><span class="sxs-lookup"><span data-stu-id="fec4e-116">Example</span></span>  
 <span data-ttu-id="fec4e-117">В следующем примере кода показано, как добавлять типы, используемые <xref:System.Xml.Serialization.XmlSchemaImporter> при сопоставлении типов XSD с типами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fec4e-117">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fec4e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="fec4e-118">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="fec4e-119">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="fec4e-119">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="fec4e-120">Элемент \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="fec4e-120">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)
- [<span data-ttu-id="fec4e-121">\<Добавить > элемент для \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="fec4e-121">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="fec4e-122">Элемент \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="fec4e-122">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
