---
title: Элемент &lt;dateTimeSerialization&gt;
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: cd275cdbc51c86b1d774058db839c38349b319a6
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "45515461"
---
# <a name="ltdatetimeserializationgt-element"></a><span data-ttu-id="318d5-102">Элемент &lt;dateTimeSerialization&gt;</span><span class="sxs-lookup"><span data-stu-id="318d5-102">&lt;dateTimeSerialization&gt; Element</span></span>
<span data-ttu-id="318d5-103">Определяет режим сериализации объектов <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="318d5-103">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 <span data-ttu-id="318d5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="318d5-104">\<configuration></span></span>  
<span data-ttu-id="318d5-105">\<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="318d5-105">\<dateTimeSerialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="318d5-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="318d5-106">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip" | "Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="318d5-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="318d5-107">Attributes and Elements</span></span>  
 <span data-ttu-id="318d5-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="318d5-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="318d5-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="318d5-109">Attributes</span></span>  
  
|<span data-ttu-id="318d5-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="318d5-110">Attributes</span></span>|<span data-ttu-id="318d5-111">Описание</span><span class="sxs-lookup"><span data-stu-id="318d5-111">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="318d5-112">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="318d5-112">Optional.</span></span> <span data-ttu-id="318d5-113">Задает режим сериализации.</span><span class="sxs-lookup"><span data-stu-id="318d5-113">Specifies the serialization mode.</span></span> <span data-ttu-id="318d5-114">Задайте одно из значений <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>.</span><span class="sxs-lookup"><span data-stu-id="318d5-114">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="318d5-115">Значение по умолчанию: **RoundTrip**.</span><span class="sxs-lookup"><span data-stu-id="318d5-115">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="318d5-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="318d5-116">Child Elements</span></span>  
 <span data-ttu-id="318d5-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="318d5-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="318d5-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="318d5-118">Parent Elements</span></span>  
  
|<span data-ttu-id="318d5-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="318d5-119">Element</span></span>|<span data-ttu-id="318d5-120">Описание</span><span class="sxs-lookup"><span data-stu-id="318d5-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="318d5-121">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="318d5-121">system.xml.serialization</span></span>|<span data-ttu-id="318d5-122">Элемент верхнего уровня для управления XML-сериализацией.</span><span class="sxs-lookup"><span data-stu-id="318d5-122">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="318d5-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="318d5-123">Remarks</span></span>  
 <span data-ttu-id="318d5-124">На платформе .NET Framework версий 1.0, 1.1 и 2.0 и более поздних при присвоении этому свойству значения **Local** объекты <xref:System.DateTime> всегда форматируются как местное время.</span><span class="sxs-lookup"><span data-stu-id="318d5-124">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="318d5-125">Это значит, что в сериализованные данные всегда включается информация о местном часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="318d5-125">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="318d5-126">Присвоение этому свойству значения **Local** обеспечивает совместимость с предыдущими версиями платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="318d5-126">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="318d5-127">На платформе .NET Framework версии 2.0 и более поздних, в которых для этого свойства задано значение **Roundtrip**, объекты <xref:System.DateTime> анализируются с целью выяснить, указан ли в них местный часовой пояс, время UTC или часовой пояс не указан.</span><span class="sxs-lookup"><span data-stu-id="318d5-127">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="318d5-128">После этого объекты <xref:System.DateTime> сериализуются способом, обеспечивающим сохранение этой информации.</span><span class="sxs-lookup"><span data-stu-id="318d5-128">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="318d5-129">Это является поведением по умолчанию, рекомендуемым для всех новых приложений, не взаимодействующих со старыми версиями платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="318d5-129">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="318d5-130">См. также</span><span class="sxs-lookup"><span data-stu-id="318d5-130">See also</span></span>

- <xref:System.DateTime>  
- <xref:System.Xml.Serialization.XmlSchemaImporter>  
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
- [<span data-ttu-id="318d5-131">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="318d5-131">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="318d5-132">Элемент \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="318d5-132">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
- [<span data-ttu-id="318d5-133">\<Добавить > элемент для \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="318d5-133">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)  
- [<span data-ttu-id="318d5-134">Элемент \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="318d5-134">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
