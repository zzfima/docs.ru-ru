---
title: "&lt;параметр&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cdbb47fcb65273d03d226e13730849170d4345c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltparametergt"></a><span data-ttu-id="f22c7-102">&lt;параметр&gt;</span><span class="sxs-lookup"><span data-stu-id="f22c7-102">&lt;parameter&gt;</span></span>
<span data-ttu-id="f22c7-103">Указывает общий параметр, если объявленный тип является общим типом.</span><span class="sxs-lookup"><span data-stu-id="f22c7-103">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
 <span data-ttu-id="f22c7-104">\<System.Runtime.Serialization ></span><span class="sxs-lookup"><span data-stu-id="f22c7-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="f22c7-105">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="f22c7-105">\<dataContractSerializer></span></span>  
<span data-ttu-id="f22c7-106">\<declaredTypes > элемент</span><span class="sxs-lookup"><span data-stu-id="f22c7-106">\<declaredTypes> Element</span></span>  
<span data-ttu-id="f22c7-107">\<Добавить > элемент для \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="f22c7-107">\<add> element for \<declaredTypes></span></span>  
<span data-ttu-id="f22c7-108">\<knownType > элемент</span><span class="sxs-lookup"><span data-stu-id="f22c7-108">\<knownType> Element</span></span>  
<span data-ttu-id="f22c7-109">\<параметр > элемент</span><span class="sxs-lookup"><span data-stu-id="f22c7-109">\<parameter> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f22c7-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f22c7-110">Syntax</span></span>  
  
```xml  
<parameter index="integer"  
                      type=String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f22c7-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f22c7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f22c7-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f22c7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f22c7-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f22c7-113">Attributes</span></span>  
  
|<span data-ttu-id="f22c7-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f22c7-114">Attribute</span></span>|<span data-ttu-id="f22c7-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f22c7-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f22c7-116">индекс</span><span class="sxs-lookup"><span data-stu-id="f22c7-116">index</span></span>|<span data-ttu-id="f22c7-117">Если объявленный тип является общим типом, указывает общий параметр, который возвращает известный тип.</span><span class="sxs-lookup"><span data-stu-id="f22c7-117">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="f22c7-118">тип</span><span class="sxs-lookup"><span data-stu-id="f22c7-118">type</span></span>|<span data-ttu-id="f22c7-119">Строка, которая описывает известный тип, используемый для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="f22c7-119">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="f22c7-120">Атрибут index</span><span class="sxs-lookup"><span data-stu-id="f22c7-120">index Attribute</span></span>  
  
|<span data-ttu-id="f22c7-121">Значение</span><span class="sxs-lookup"><span data-stu-id="f22c7-121">Value</span></span>|<span data-ttu-id="f22c7-122">Описание</span><span class="sxs-lookup"><span data-stu-id="f22c7-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f22c7-123">"0"</span><span class="sxs-lookup"><span data-stu-id="f22c7-123">"0"</span></span>|<span data-ttu-id="f22c7-124">Первый параметр в общем типе.</span><span class="sxs-lookup"><span data-stu-id="f22c7-124">The first parameter in the generic type.</span></span> <span data-ttu-id="f22c7-125">Например, у <xref:System.Collections.Generic.List%601> есть только один параметр.</span><span class="sxs-lookup"><span data-stu-id="f22c7-125">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="f22c7-126">Если он используется как объявленный тип, индексу присваивается значение 0.</span><span class="sxs-lookup"><span data-stu-id="f22c7-126">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="f22c7-127">"1"</span><span class="sxs-lookup"><span data-stu-id="f22c7-127">"1"</span></span>|<span data-ttu-id="f22c7-128">Второй параметр в общем типе.</span><span class="sxs-lookup"><span data-stu-id="f22c7-128">The second parameter in a generic type.</span></span> <span data-ttu-id="f22c7-129">Например, у <xref:System.Collections.Generic.Dictionary%602> есть два параметра.</span><span class="sxs-lookup"><span data-stu-id="f22c7-129">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="f22c7-130">Если известный тип возвращается вторым параметром, атрибуту index присваивается значение 1.</span><span class="sxs-lookup"><span data-stu-id="f22c7-130">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f22c7-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f22c7-131">Child Elements</span></span>  
 <span data-ttu-id="f22c7-132">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f22c7-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f22c7-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f22c7-133">Parent Elements</span></span>  
  
|<span data-ttu-id="f22c7-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="f22c7-134">Element</span></span>|<span data-ttu-id="f22c7-135">Описание:</span><span class="sxs-lookup"><span data-stu-id="f22c7-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f22c7-136">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="f22c7-136">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="f22c7-137">Указывает известный тип, который может возвращаться полем или свойством объявленного типа.</span><span class="sxs-lookup"><span data-stu-id="f22c7-137">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f22c7-138">Примечания</span><span class="sxs-lookup"><span data-stu-id="f22c7-138">Remarks</span></span>  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]<span data-ttu-id="f22c7-139">известных типах см. в разделе [известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="f22c7-139"> known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="f22c7-140">В разделе [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) пример использования этого элемента.</span><span class="sxs-lookup"><span data-stu-id="f22c7-140">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="f22c7-141">У данного элемента конфигурации не может одновременно быть оба атрибута.</span><span class="sxs-lookup"><span data-stu-id="f22c7-141">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="f22c7-142">Если заданы оба атрибута, возникает исключение <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="f22c7-142">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f22c7-143">См. также</span><span class="sxs-lookup"><span data-stu-id="f22c7-143">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="f22c7-144">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="f22c7-144">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="f22c7-145">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="f22c7-145">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="f22c7-146">\<add></span><span class="sxs-lookup"><span data-stu-id="f22c7-146">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
