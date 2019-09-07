---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: e24dae47171f741af064ca2eaa822928690acf6e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400454"
---
# <a name="datacontractserializer"></a><span data-ttu-id="52f0f-101">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="52f0f-101">\<dataContractSerializer></span></span>
<span data-ttu-id="52f0f-102">Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="52f0f-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="52f0f-103">Этот элемент присутствует в двух разных иерархиях.</span><span class="sxs-lookup"><span data-stu-id="52f0f-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="52f0f-104">Одна из них указана в следующем разделе «Иерархия схемы», а другая - в разделе «Примечания».</span><span class="sxs-lookup"><span data-stu-id="52f0f-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
<span data-ttu-id="52f0f-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="52f0f-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="52f0f-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="52f0f-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="52f0f-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="52f0f-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="52f0f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="52f0f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="52f0f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="52f0f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="52f0f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<dataContractSerializer >**</span><span class="sxs-lookup"><span data-stu-id="52f0f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52f0f-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52f0f-111">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52f0f-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="52f0f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="52f0f-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="52f0f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52f0f-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="52f0f-114">Attributes</span></span>  
  
|<span data-ttu-id="52f0f-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="52f0f-115">Element</span></span>|<span data-ttu-id="52f0f-116">Описание</span><span class="sxs-lookup"><span data-stu-id="52f0f-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="52f0f-117">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="52f0f-117">ignoreExtensionDataObject</span></span>|<span data-ttu-id="52f0f-118">Логическое значение, указывающее, пропускать ли данные, предоставленные конечной точкой при ее сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="52f0f-118">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="52f0f-119">Этот атрибут можно задать только в `<dataContractSerializer>` в элементе `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="52f0f-119">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="52f0f-120">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="52f0f-120">maxItemsInObjectGraph</span></span>|<span data-ttu-id="52f0f-121">Целое число, указывающее максимальное количество элементов для сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="52f0f-121">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="52f0f-122">Этот атрибут имеет значение 65 536.</span><span class="sxs-lookup"><span data-stu-id="52f0f-122">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="52f0f-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="52f0f-123">Child Elements</span></span>  
 <span data-ttu-id="52f0f-124">Нет.</span><span class="sxs-lookup"><span data-stu-id="52f0f-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="52f0f-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="52f0f-125">Parent Elements</span></span>  
  
|<span data-ttu-id="52f0f-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="52f0f-126">Element</span></span>|<span data-ttu-id="52f0f-127">Описание</span><span class="sxs-lookup"><span data-stu-id="52f0f-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52f0f-128">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="52f0f-128">\<behavior></span></span>](behavior-of-servicebehaviors.md)|<span data-ttu-id="52f0f-129">Коллекция параметров для поведения службы.</span><span class="sxs-lookup"><span data-stu-id="52f0f-129">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="52f0f-130">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="52f0f-130">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)|<span data-ttu-id="52f0f-131">Представляет корневой элемент для раздела пространства имен <xref:System.Runtime.Serialization> и содержит элементы для установки параметров <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="52f0f-131">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52f0f-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="52f0f-132">Remarks</span></span>  
 <span data-ttu-id="52f0f-133">Как указано в этом разделе, это вторая иерархия, в которой \<происходит элемент > X509Extension.</span><span class="sxs-lookup"><span data-stu-id="52f0f-133">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="52f0f-134">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="52f0f-134">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)  
  
 [<span data-ttu-id="52f0f-135">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="52f0f-135">\<dataContractSerializer></span></span>](datacontractserializer-element.md)  
  
 <span data-ttu-id="52f0f-136">Дополнительные сведения об известных типах см. в разделе <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="52f0f-136">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52f0f-137">См. также</span><span class="sxs-lookup"><span data-stu-id="52f0f-137">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="52f0f-138">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="52f0f-138">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="52f0f-139">Передача данных и сериализация</span><span class="sxs-lookup"><span data-stu-id="52f0f-139">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
