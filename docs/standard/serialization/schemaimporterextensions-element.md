---
title: Элемент &lt;schemaImporterExtensions&gt;
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: c9f4f6800c2718c3b2c2b9b5b2b6d97e1114dbcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33581333"
---
# <a name="ltschemaimporterextensionsgt-element"></a><span data-ttu-id="c6e28-102">Элемент &lt;schemaImporterExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="c6e28-102">&lt;schemaImporterExtensions&gt; Element</span></span>
<span data-ttu-id="c6e28-103">Содержит типы, которые использует <xref:System.Xml.Serialization.XmlSchemaImporter> для сопоставления типов XSD с типами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c6e28-103">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span> <span data-ttu-id="c6e28-104">Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="c6e28-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6e28-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6e28-105">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</SchemaImporterExtension>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="c6e28-106">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c6e28-106">Child Elements</span></span>  
  
|<span data-ttu-id="c6e28-107">Элемент</span><span class="sxs-lookup"><span data-stu-id="c6e28-107">Element</span></span>|<span data-ttu-id="c6e28-108">Описание</span><span class="sxs-lookup"><span data-stu-id="c6e28-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6e28-109">Элемент \<add> для элемента \<xmlSchemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="c6e28-109">\<add> Element for \<xmlSchemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)|<span data-ttu-id="c6e28-110">Добавляет типы, используемые <xref:System.Xml.Serialization.XmlSchemaImporter> для создания сопоставлений.</span><span class="sxs-lookup"><span data-stu-id="c6e28-110">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="c6e28-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c6e28-111">Parent Elements</span></span>  
  
|<span data-ttu-id="c6e28-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="c6e28-112">Element</span></span>|<span data-ttu-id="c6e28-113">Описание</span><span class="sxs-lookup"><span data-stu-id="c6e28-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6e28-114">Элемент \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="c6e28-114">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="c6e28-115">Элемент верхнего уровня для управления XML-сериализацией.</span><span class="sxs-lookup"><span data-stu-id="c6e28-115">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c6e28-116">Пример</span><span class="sxs-lookup"><span data-stu-id="c6e28-116">Example</span></span>  
 <span data-ttu-id="c6e28-117">В следующем примере кода показано, как добавлять типы, используемые <xref:System.Xml.Serialization.XmlSchemaImporter> при сопоставлении типов XSD с типами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c6e28-117">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
```xml  
<system.xml.serialization>  
    <schemaImporterExtensions>  
        <add name = "MobileCapabilities" type =   
        "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
/system.sxml.serializaiton>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6e28-118">См. также</span><span class="sxs-lookup"><span data-stu-id="c6e28-118">See Also</span></span>  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
 [<span data-ttu-id="c6e28-119">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="c6e28-119">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="c6e28-120">Элемент \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="c6e28-120">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)  
 [<span data-ttu-id="c6e28-121">Элемент \<add> для элемента \<xmlSchemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="c6e28-121">\<add> Element for \<xmlSchemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)  
 [<span data-ttu-id="c6e28-122">Элемент \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="c6e28-122">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
