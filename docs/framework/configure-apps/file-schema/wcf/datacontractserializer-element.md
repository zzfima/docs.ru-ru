---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: 1b4fd959d5e522150751d2e9b8be8c5b2252bf27
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254955"
---
# <a name="datacontractserializer"></a><span data-ttu-id="8f4c3-101">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="8f4c3-101">\<dataContractSerializer></span></span>
<span data-ttu-id="8f4c3-102">Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8f4c3-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="8f4c3-103">Этот элемент присутствует в двух разных иерархиях.</span><span class="sxs-lookup"><span data-stu-id="8f4c3-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="8f4c3-104">Одна из них указана в следующем разделе «Иерархия схемы», а другая - в разделе «Примечания».</span><span class="sxs-lookup"><span data-stu-id="8f4c3-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="8f4c3-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8f4c3-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="8f4c3-106">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="8f4c3-106">\<behaviors></span></span>  
<span data-ttu-id="8f4c3-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="8f4c3-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="8f4c3-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="8f4c3-108">\<behavior></span></span>  
<span data-ttu-id="8f4c3-109">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="8f4c3-109">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f4c3-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f4c3-110">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f4c3-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8f4c3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8f4c3-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8f4c3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f4c3-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8f4c3-113">Attributes</span></span>  
  
|<span data-ttu-id="8f4c3-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="8f4c3-114">Element</span></span>|<span data-ttu-id="8f4c3-115">Описание</span><span class="sxs-lookup"><span data-stu-id="8f4c3-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8f4c3-116">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="8f4c3-116">ignoreExtensionDataObject</span></span>|<span data-ttu-id="8f4c3-117">Логическое значение, указывающее, пропускать ли данные, предоставленные конечной точкой при ее сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="8f4c3-117">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="8f4c3-118">Этот атрибут можно задать только в `<dataContractSerializer>` в элементе `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="8f4c3-118">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="8f4c3-119">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="8f4c3-119">maxItemsInObjectGraph</span></span>|<span data-ttu-id="8f4c3-120">Целое число, указывающее максимальное количество элементов для сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="8f4c3-120">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="8f4c3-121">Этот атрибут имеет значение 65 536.</span><span class="sxs-lookup"><span data-stu-id="8f4c3-121">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8f4c3-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8f4c3-122">Child Elements</span></span>  
 <span data-ttu-id="8f4c3-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8f4c3-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8f4c3-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8f4c3-124">Parent Elements</span></span>  
  
|<span data-ttu-id="8f4c3-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="8f4c3-125">Element</span></span>|<span data-ttu-id="8f4c3-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="8f4c3-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f4c3-127">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="8f4c3-127">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|<span data-ttu-id="8f4c3-128">Коллекция параметров для поведения службы.</span><span class="sxs-lookup"><span data-stu-id="8f4c3-128">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="8f4c3-129">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="8f4c3-129">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="8f4c3-130">Представляет корневой элемент для раздела пространства имен <xref:System.Runtime.Serialization> и содержит элементы для установки параметров <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8f4c3-130">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f4c3-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="8f4c3-131">Remarks</span></span>  
 <span data-ttu-id="8f4c3-132">Как уже говорилось в начале этого раздела, это вторая иерархия, в которой \<X509Extension > происходит элемент.</span><span class="sxs-lookup"><span data-stu-id="8f4c3-132">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="8f4c3-133">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="8f4c3-133">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [<span data-ttu-id="8f4c3-134">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="8f4c3-134">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 <span data-ttu-id="8f4c3-135">Дополнительные сведения об известных типах см. в разделе <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8f4c3-135">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f4c3-136">См. также</span><span class="sxs-lookup"><span data-stu-id="8f4c3-136">See also</span></span>
- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="8f4c3-137">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="8f4c3-137">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="8f4c3-138">Передача данных и сериализация</span><span class="sxs-lookup"><span data-stu-id="8f4c3-138">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
