---
title: '&lt;Параметр&gt;'
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 82a2f5c46c698508695fe5f13f67059860a50713
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148296"
---
# <a name="ltparametergt"></a><span data-ttu-id="9ca07-102">&lt;Параметр&gt;</span><span class="sxs-lookup"><span data-stu-id="9ca07-102">&lt;parameter&gt;</span></span>
<span data-ttu-id="9ca07-103">Указывает общий параметр, если объявленный тип является общим типом.</span><span class="sxs-lookup"><span data-stu-id="9ca07-103">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
 <span data-ttu-id="9ca07-104">\<System.Runtime.Serialization ></span><span class="sxs-lookup"><span data-stu-id="9ca07-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="9ca07-105">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="9ca07-105">\<dataContractSerializer></span></span>  
<span data-ttu-id="9ca07-106">\<declaredTypes > элемент</span><span class="sxs-lookup"><span data-stu-id="9ca07-106">\<declaredTypes> Element</span></span>  
<span data-ttu-id="9ca07-107">\<Добавить > элемент для \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="9ca07-107">\<add> element for \<declaredTypes></span></span>  
<span data-ttu-id="9ca07-108">\<knownType > элемент</span><span class="sxs-lookup"><span data-stu-id="9ca07-108">\<knownType> Element</span></span>  
<span data-ttu-id="9ca07-109">\<параметр > элемент</span><span class="sxs-lookup"><span data-stu-id="9ca07-109">\<parameter> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ca07-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ca07-110">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ca07-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9ca07-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9ca07-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9ca07-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ca07-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9ca07-113">Attributes</span></span>  
  
|<span data-ttu-id="9ca07-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9ca07-114">Attribute</span></span>|<span data-ttu-id="9ca07-115">Описание</span><span class="sxs-lookup"><span data-stu-id="9ca07-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9ca07-116">индекс</span><span class="sxs-lookup"><span data-stu-id="9ca07-116">index</span></span>|<span data-ttu-id="9ca07-117">Если объявленный тип является общим типом, указывает общий параметр, который возвращает известный тип.</span><span class="sxs-lookup"><span data-stu-id="9ca07-117">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="9ca07-118">тип</span><span class="sxs-lookup"><span data-stu-id="9ca07-118">type</span></span>|<span data-ttu-id="9ca07-119">Строка, которая описывает известный тип, используемый для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="9ca07-119">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="9ca07-120">Атрибут index</span><span class="sxs-lookup"><span data-stu-id="9ca07-120">index Attribute</span></span>  
  
|<span data-ttu-id="9ca07-121">Значение</span><span class="sxs-lookup"><span data-stu-id="9ca07-121">Value</span></span>|<span data-ttu-id="9ca07-122">Описание</span><span class="sxs-lookup"><span data-stu-id="9ca07-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9ca07-123">"0"</span><span class="sxs-lookup"><span data-stu-id="9ca07-123">"0"</span></span>|<span data-ttu-id="9ca07-124">Первый параметр в общем типе.</span><span class="sxs-lookup"><span data-stu-id="9ca07-124">The first parameter in the generic type.</span></span> <span data-ttu-id="9ca07-125">Например, у <xref:System.Collections.Generic.List%601> есть только один параметр.</span><span class="sxs-lookup"><span data-stu-id="9ca07-125">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="9ca07-126">Если он используется как объявленный тип, индексу присваивается значение 0.</span><span class="sxs-lookup"><span data-stu-id="9ca07-126">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="9ca07-127">"1"</span><span class="sxs-lookup"><span data-stu-id="9ca07-127">"1"</span></span>|<span data-ttu-id="9ca07-128">Второй параметр в общем типе.</span><span class="sxs-lookup"><span data-stu-id="9ca07-128">The second parameter in a generic type.</span></span> <span data-ttu-id="9ca07-129">Например, у <xref:System.Collections.Generic.Dictionary%602> есть два параметра.</span><span class="sxs-lookup"><span data-stu-id="9ca07-129">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="9ca07-130">Если известный тип возвращается вторым параметром, атрибуту index присваивается значение 1.</span><span class="sxs-lookup"><span data-stu-id="9ca07-130">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ca07-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9ca07-131">Child Elements</span></span>  
 <span data-ttu-id="9ca07-132">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9ca07-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9ca07-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9ca07-133">Parent Elements</span></span>  
  
|<span data-ttu-id="9ca07-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="9ca07-134">Element</span></span>|<span data-ttu-id="9ca07-135">Описание</span><span class="sxs-lookup"><span data-stu-id="9ca07-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ca07-136">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="9ca07-136">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="9ca07-137">Указывает известный тип, который может возвращаться полем или свойством объявленного типа.</span><span class="sxs-lookup"><span data-stu-id="9ca07-137">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ca07-138">Примечания</span><span class="sxs-lookup"><span data-stu-id="9ca07-138">Remarks</span></span>  
 <span data-ttu-id="9ca07-139">Дополнительные сведения об известных типах см. в разделе [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="9ca07-139">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="9ca07-140">См. в разделе [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) пример использования этого элемента.</span><span class="sxs-lookup"><span data-stu-id="9ca07-140">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="9ca07-141">У данного элемента конфигурации не может одновременно быть оба атрибута.</span><span class="sxs-lookup"><span data-stu-id="9ca07-141">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="9ca07-142">Если заданы оба атрибута, возникает исключение <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="9ca07-142">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ca07-143">См. также</span><span class="sxs-lookup"><span data-stu-id="9ca07-143">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="9ca07-144">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="9ca07-144">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="9ca07-145">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="9ca07-145">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="9ca07-146">\<add></span><span class="sxs-lookup"><span data-stu-id="9ca07-146">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
