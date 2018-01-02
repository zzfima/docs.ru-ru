---
title: '&lt;dataContractSerializer&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 27b80c831fdc66bd3b022645c3de9c0c31ee575a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltdatacontractserializergt"></a><span data-ttu-id="112b7-102">&lt;dataContractSerializer&gt;</span><span class="sxs-lookup"><span data-stu-id="112b7-102">&lt;dataContractSerializer&gt;</span></span>
<span data-ttu-id="112b7-103">Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="112b7-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="112b7-104">Этот элемент присутствует в двух разных иерархиях.</span><span class="sxs-lookup"><span data-stu-id="112b7-104">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="112b7-105">Одна из них указана в следующем разделе «Иерархия схемы», а другая - в разделе «Примечания».</span><span class="sxs-lookup"><span data-stu-id="112b7-105">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="112b7-106">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="112b7-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="112b7-107">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="112b7-107">\<behaviors></span></span>  
<span data-ttu-id="112b7-108">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="112b7-108">\<serviceBehaviors></span></span>  
<span data-ttu-id="112b7-109">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="112b7-109">\<behavior></span></span>  
<span data-ttu-id="112b7-110">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="112b7-110">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="112b7-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="112b7-111">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
   maxItemsInObjectGraph="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="112b7-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="112b7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="112b7-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="112b7-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="112b7-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="112b7-114">Attributes</span></span>  
  
|<span data-ttu-id="112b7-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="112b7-115">Element</span></span>|<span data-ttu-id="112b7-116">Описание</span><span class="sxs-lookup"><span data-stu-id="112b7-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="112b7-117">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="112b7-117">ignoreExtensionDataObject</span></span>|<span data-ttu-id="112b7-118">Логическое значение, указывающее, пропускать ли данные, предоставленные конечной точкой при ее сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="112b7-118">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="112b7-119">Этот атрибут можно задать только в `<dataContractSerializer>` в элементе `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="112b7-119">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="112b7-120">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="112b7-120">maxItemsInObjectGraph</span></span>|<span data-ttu-id="112b7-121">Целое число, указывающее максимальное количество элементов для сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="112b7-121">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="112b7-122">Этот атрибут имеет значение 65 536.</span><span class="sxs-lookup"><span data-stu-id="112b7-122">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="112b7-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="112b7-123">Child Elements</span></span>  
 <span data-ttu-id="112b7-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="112b7-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="112b7-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="112b7-125">Parent Elements</span></span>  
  
|<span data-ttu-id="112b7-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="112b7-126">Element</span></span>|<span data-ttu-id="112b7-127">Описание:</span><span class="sxs-lookup"><span data-stu-id="112b7-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="112b7-128">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="112b7-128">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|<span data-ttu-id="112b7-129">Коллекция параметров для поведения службы.</span><span class="sxs-lookup"><span data-stu-id="112b7-129">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="112b7-130">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="112b7-130">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="112b7-131">Представляет корневой элемент для раздела пространства имен <xref:System.Runtime.Serialization> и содержит элементы для установки параметров <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="112b7-131">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="112b7-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="112b7-132">Remarks</span></span>  
 <span data-ttu-id="112b7-133">Как уже говорилось в введение к этому разделу, это вторая иерархия, в которой \<X509Extension > элемент присутствует.</span><span class="sxs-lookup"><span data-stu-id="112b7-133">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="112b7-134">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="112b7-134">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [<span data-ttu-id="112b7-135">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="112b7-135">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 <span data-ttu-id="112b7-136">Дополнительные сведения об известных типах см. в разделе <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="112b7-136">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="112b7-137">См. также</span><span class="sxs-lookup"><span data-stu-id="112b7-137">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [<span data-ttu-id="112b7-138">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="112b7-138">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="112b7-139">Передача данных и сериализация</span><span class="sxs-lookup"><span data-stu-id="112b7-139">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
