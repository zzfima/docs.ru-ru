---
title: Элемент &lt;schemaImporterExtensions&gt;
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: b5696c593fdeaabab66ea7c286c6e1309e6e8e38
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44204803"
---
# <a name="ltschemaimporterextensionsgt-element"></a><span data-ttu-id="07945-102">Элемент &lt;schemaImporterExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="07945-102">&lt;schemaImporterExtensions&gt; Element</span></span>
<span data-ttu-id="07945-103">Содержит типы, которые использует <xref:System.Xml.Serialization.XmlSchemaImporter> для сопоставления типов XSD с типами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="07945-103">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span> <span data-ttu-id="07945-104">Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="07945-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07945-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="07945-105">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="07945-106">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="07945-106">Child Elements</span></span>  
  
|<span data-ttu-id="07945-107">Элемент</span><span class="sxs-lookup"><span data-stu-id="07945-107">Element</span></span>|<span data-ttu-id="07945-108">Описание</span><span class="sxs-lookup"><span data-stu-id="07945-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07945-109">\<Добавить > элемент для \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="07945-109">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)|<span data-ttu-id="07945-110">Добавляет типы, используемые <xref:System.Xml.Serialization.XmlSchemaImporter> для создания сопоставлений.</span><span class="sxs-lookup"><span data-stu-id="07945-110">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="07945-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="07945-111">Parent Elements</span></span>  
  
|<span data-ttu-id="07945-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="07945-112">Element</span></span>|<span data-ttu-id="07945-113">Описание</span><span class="sxs-lookup"><span data-stu-id="07945-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07945-114">Элемент \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="07945-114">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="07945-115">Элемент верхнего уровня для управления XML-сериализацией.</span><span class="sxs-lookup"><span data-stu-id="07945-115">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="07945-116">Пример</span><span class="sxs-lookup"><span data-stu-id="07945-116">Example</span></span>  
 <span data-ttu-id="07945-117">В следующем примере кода показано, как добавлять типы, используемые <xref:System.Xml.Serialization.XmlSchemaImporter> при сопоставлении типов XSD с типами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="07945-117">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="07945-118">См. также</span><span class="sxs-lookup"><span data-stu-id="07945-118">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>  
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
- [<span data-ttu-id="07945-119">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="07945-119">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="07945-120">Элемент \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="07945-120">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)  
- [<span data-ttu-id="07945-121">\<Добавить > элемент для \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="07945-121">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)  
- [<span data-ttu-id="07945-122">Элемент \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="07945-122">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
