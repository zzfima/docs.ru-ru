---
title: '&lt;Добавить&gt; элемент для &lt;schemaImporterExtensions&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: 3d3c72fd64042032d44c49ebde867d111ce03b94
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42936590"
---
# <a name="ltaddgt-element-for-ltschemaimporterextensionsgt"></a><span data-ttu-id="7c735-102">&lt;Добавить&gt; элемент для &lt;schemaImporterExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="7c735-102">&lt;add&gt; Element for &lt;schemaImporterExtensions&gt;</span></span>
<span data-ttu-id="7c735-103">Добавляет типы, используемые <xref:System.Xml.Serialization.XmlSchemaImporter>, для сопоставления типов XSD с типами платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7c735-103">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET Framework types.</span></span> <span data-ttu-id="7c735-104">Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="7c735-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="7c735-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7c735-105">\<configuration></span></span>  
<span data-ttu-id="7c735-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="7c735-106">\<system.xml.serialization></span></span>  
<span data-ttu-id="7c735-107">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="7c735-107">\<schemaImporterExtensions></span></span>  
<span data-ttu-id="7c735-108">\<add></span><span class="sxs-lookup"><span data-stu-id="7c735-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c735-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c735-109">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c735-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7c735-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7c735-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7c735-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c735-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7c735-112">Attributes</span></span>  
  
|<span data-ttu-id="7c735-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7c735-113">Attribute</span></span>|<span data-ttu-id="7c735-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="7c735-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7c735-115">**name**</span><span class="sxs-lookup"><span data-stu-id="7c735-115">**name**</span></span>|<span data-ttu-id="7c735-116">Простое имя, используемое для поиска экземпляра.</span><span class="sxs-lookup"><span data-stu-id="7c735-116">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="7c735-117">**type**</span><span class="sxs-lookup"><span data-stu-id="7c735-117">**type**</span></span>|<span data-ttu-id="7c735-118">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="7c735-118">Required.</span></span> <span data-ttu-id="7c735-119">Задает добавляемый класс расширения схемы.</span><span class="sxs-lookup"><span data-stu-id="7c735-119">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="7c735-120">Значение атрибута **type** должно располагаться на одной строке и содержать полное имя типа.</span><span class="sxs-lookup"><span data-stu-id="7c735-120">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="7c735-121">Когда сборка помещается в глобальный кэш сборок (GAC), она должна также содержать версию, язык и региональные параметры и маркер открытого ключа подписанной сборки.</span><span class="sxs-lookup"><span data-stu-id="7c735-121">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7c735-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7c735-122">Child Elements</span></span>  
 <span data-ttu-id="7c735-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7c735-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7c735-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7c735-124">Parent Elements</span></span>  
  
|<span data-ttu-id="7c735-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="7c735-125">Element</span></span>|<span data-ttu-id="7c735-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="7c735-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c735-127">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="7c735-127">\<schemaImporterExtensions></span></span>|<span data-ttu-id="7c735-128">Содержит типы, используемые классом<xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="7c735-128">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7c735-129">Пример</span><span class="sxs-lookup"><span data-stu-id="7c735-129">Example</span></span>  
 <span data-ttu-id="7c735-130">В приведенном ниже примере кода добавляется тип расширения, который XmlSchemaImporter может использовать при сопоставлении типов.</span><span class="sxs-lookup"><span data-stu-id="7c735-130">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <schemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,   
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,   
       PublicKeyToken=b03f5f7f11d50a3a" />   
    </schemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7c735-131">См. также</span><span class="sxs-lookup"><span data-stu-id="7c735-131">See Also</span></span>  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 [<span data-ttu-id="7c735-132">Элемент \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="7c735-132">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)  
 [<span data-ttu-id="7c735-133">Элемент \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="7c735-133">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
