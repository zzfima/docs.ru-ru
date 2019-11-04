---
title: Элемент <dateTimeSerialization>
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: 180a4942dd4b701b56fe4788d5f8cd8607faaedd
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459259"
---
# <a name="datetimeserialization-element"></a><span data-ttu-id="8c30b-102">\<элемент datetimeserialization > элемент</span><span class="sxs-lookup"><span data-stu-id="8c30b-102">\<dateTimeSerialization> Element</span></span>
<span data-ttu-id="8c30b-103">Определяет режим сериализации объектов <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="8c30b-103">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 <span data-ttu-id="8c30b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8c30b-104">\<configuration></span></span>  
<span data-ttu-id="8c30b-105">\<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="8c30b-105">\<dateTimeSerialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c30b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c30b-106">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c30b-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8c30b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="8c30b-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8c30b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c30b-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8c30b-109">Attributes</span></span>  
  
|<span data-ttu-id="8c30b-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8c30b-110">Attributes</span></span>|<span data-ttu-id="8c30b-111">Описание</span><span class="sxs-lookup"><span data-stu-id="8c30b-111">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="8c30b-112">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="8c30b-112">Optional.</span></span> <span data-ttu-id="8c30b-113">Задает режим сериализации.</span><span class="sxs-lookup"><span data-stu-id="8c30b-113">Specifies the serialization mode.</span></span> <span data-ttu-id="8c30b-114">Задайте одно из значений <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>.</span><span class="sxs-lookup"><span data-stu-id="8c30b-114">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="8c30b-115">Значение по умолчанию: **RoundTrip**.</span><span class="sxs-lookup"><span data-stu-id="8c30b-115">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c30b-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8c30b-116">Child Elements</span></span>  
 <span data-ttu-id="8c30b-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8c30b-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8c30b-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8c30b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="8c30b-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="8c30b-119">Element</span></span>|<span data-ttu-id="8c30b-120">Описание</span><span class="sxs-lookup"><span data-stu-id="8c30b-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8c30b-121">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="8c30b-121">system.xml.serialization</span></span>|<span data-ttu-id="8c30b-122">Элемент верхнего уровня для управления XML-сериализацией.</span><span class="sxs-lookup"><span data-stu-id="8c30b-122">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c30b-123">Заметки</span><span class="sxs-lookup"><span data-stu-id="8c30b-123">Remarks</span></span>  
 <span data-ttu-id="8c30b-124">На платформе .NET Framework версий 1.0, 1.1 и 2.0 и более поздних при присвоении этому свойству значения **Local** объекты <xref:System.DateTime> всегда форматируются как местное время.</span><span class="sxs-lookup"><span data-stu-id="8c30b-124">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="8c30b-125">Это значит, что в сериализованные данные всегда включается информация о местном часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="8c30b-125">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="8c30b-126">Присвоение этому свойству значения **Local** обеспечивает совместимость с предыдущими версиями платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8c30b-126">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="8c30b-127">На платформе .NET Framework версии 2.0 и более поздних, в которых для этого свойства задано значение **Roundtrip**, объекты <xref:System.DateTime> анализируются с целью выяснить, указан ли в них местный часовой пояс, время UTC или часовой пояс не указан.</span><span class="sxs-lookup"><span data-stu-id="8c30b-127">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="8c30b-128">После этого объекты <xref:System.DateTime> сериализуются способом, обеспечивающим сохранение этой информации.</span><span class="sxs-lookup"><span data-stu-id="8c30b-128">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="8c30b-129">Это является поведением по умолчанию, рекомендуемым для всех новых приложений, не взаимодействующих со старыми версиями платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8c30b-129">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c30b-130">См. также</span><span class="sxs-lookup"><span data-stu-id="8c30b-130">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="8c30b-131">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="8c30b-131">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="8c30b-132">Элемент \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="8c30b-132">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [<span data-ttu-id="8c30b-133">\<добавить элемент > для \<элемент schemaimporterextensions ></span><span class="sxs-lookup"><span data-stu-id="8c30b-133">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="8c30b-134">Элемент \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="8c30b-134">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
