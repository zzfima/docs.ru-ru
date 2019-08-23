---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: 7e440810fee1dddb7025d1385b1edb4838d98a39
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925911"
---
# <a name="datacontractserializer"></a><span data-ttu-id="c60c2-101">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="c60c2-101">\<dataContractSerializer></span></span>
<span data-ttu-id="c60c2-102">Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="c60c2-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="c60c2-103">Этот элемент присутствует в двух разных иерархиях.</span><span class="sxs-lookup"><span data-stu-id="c60c2-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="c60c2-104">Одна из них указана в следующем разделе «Иерархия схемы», а другая - в разделе «Примечания».</span><span class="sxs-lookup"><span data-stu-id="c60c2-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="c60c2-105">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c60c2-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="c60c2-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="c60c2-106">\<behaviors></span></span>  
<span data-ttu-id="c60c2-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c60c2-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="c60c2-108">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="c60c2-108">\<behavior></span></span>  
<span data-ttu-id="c60c2-109">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="c60c2-109">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c60c2-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c60c2-110">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c60c2-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c60c2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c60c2-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c60c2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c60c2-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c60c2-113">Attributes</span></span>  
  
|<span data-ttu-id="c60c2-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="c60c2-114">Element</span></span>|<span data-ttu-id="c60c2-115">Описание</span><span class="sxs-lookup"><span data-stu-id="c60c2-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c60c2-116">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="c60c2-116">ignoreExtensionDataObject</span></span>|<span data-ttu-id="c60c2-117">Логическое значение, указывающее, пропускать ли данные, предоставленные конечной точкой при ее сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="c60c2-117">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="c60c2-118">Этот атрибут можно задать только в `<dataContractSerializer>` в элементе `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="c60c2-118">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="c60c2-119">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="c60c2-119">maxItemsInObjectGraph</span></span>|<span data-ttu-id="c60c2-120">Целое число, указывающее максимальное количество элементов для сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="c60c2-120">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="c60c2-121">Этот атрибут имеет значение 65 536.</span><span class="sxs-lookup"><span data-stu-id="c60c2-121">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c60c2-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c60c2-122">Child Elements</span></span>  
 <span data-ttu-id="c60c2-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="c60c2-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c60c2-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c60c2-124">Parent Elements</span></span>  
  
|<span data-ttu-id="c60c2-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="c60c2-125">Element</span></span>|<span data-ttu-id="c60c2-126">Описание</span><span class="sxs-lookup"><span data-stu-id="c60c2-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c60c2-127">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="c60c2-127">\<behavior></span></span>](behavior-of-servicebehaviors.md)|<span data-ttu-id="c60c2-128">Коллекция параметров для поведения службы.</span><span class="sxs-lookup"><span data-stu-id="c60c2-128">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="c60c2-129">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="c60c2-129">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)|<span data-ttu-id="c60c2-130">Представляет корневой элемент для раздела пространства имен <xref:System.Runtime.Serialization> и содержит элементы для установки параметров <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="c60c2-130">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c60c2-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="c60c2-131">Remarks</span></span>  
 <span data-ttu-id="c60c2-132">Как указано в этом разделе, это вторая иерархия, в которой \<происходит элемент > X509Extension.</span><span class="sxs-lookup"><span data-stu-id="c60c2-132">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="c60c2-133">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="c60c2-133">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)  
  
 [<span data-ttu-id="c60c2-134">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="c60c2-134">\<dataContractSerializer></span></span>](datacontractserializer-element.md)  
  
 <span data-ttu-id="c60c2-135">Дополнительные сведения об известных типах см. в разделе <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="c60c2-135">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c60c2-136">См. также</span><span class="sxs-lookup"><span data-stu-id="c60c2-136">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="c60c2-137">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="c60c2-137">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="c60c2-138">Передача данных и сериализация</span><span class="sxs-lookup"><span data-stu-id="c60c2-138">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
