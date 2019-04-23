---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 22ef3c3c6d23d6c68c27d6b5d1ed35b7c9910d48
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59230802"
---
# <a name="parameter"></a><span data-ttu-id="3851b-101">\<Параметр ></span><span class="sxs-lookup"><span data-stu-id="3851b-101">\<parameter></span></span>
<span data-ttu-id="3851b-102">Указывает общий параметр, если объявленный тип является общим типом.</span><span class="sxs-lookup"><span data-stu-id="3851b-102">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
 <span data-ttu-id="3851b-103">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="3851b-103">\<system.runtime.serialization></span></span>  
<span data-ttu-id="3851b-104">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="3851b-104">\<dataContractSerializer></span></span>  
<span data-ttu-id="3851b-105">\<declaredTypes > элемент</span><span class="sxs-lookup"><span data-stu-id="3851b-105">\<declaredTypes> Element</span></span>  
<span data-ttu-id="3851b-106">\<Добавить > элемент для \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="3851b-106">\<add> element for \<declaredTypes></span></span>  
<span data-ttu-id="3851b-107">\<knownType > элемент</span><span class="sxs-lookup"><span data-stu-id="3851b-107">\<knownType> Element</span></span>  
<span data-ttu-id="3851b-108">\<параметр > элемент</span><span class="sxs-lookup"><span data-stu-id="3851b-108">\<parameter> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3851b-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3851b-109">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3851b-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3851b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3851b-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3851b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3851b-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3851b-112">Attributes</span></span>  
  
|<span data-ttu-id="3851b-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3851b-113">Attribute</span></span>|<span data-ttu-id="3851b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3851b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3851b-115">индекс</span><span class="sxs-lookup"><span data-stu-id="3851b-115">index</span></span>|<span data-ttu-id="3851b-116">Если объявленный тип является общим типом, указывает общий параметр, который возвращает известный тип.</span><span class="sxs-lookup"><span data-stu-id="3851b-116">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="3851b-117">type</span><span class="sxs-lookup"><span data-stu-id="3851b-117">type</span></span>|<span data-ttu-id="3851b-118">Строка, которая описывает известный тип, используемый для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="3851b-118">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="3851b-119">Атрибут index</span><span class="sxs-lookup"><span data-stu-id="3851b-119">index Attribute</span></span>  
  
|<span data-ttu-id="3851b-120">Значение</span><span class="sxs-lookup"><span data-stu-id="3851b-120">Value</span></span>|<span data-ttu-id="3851b-121">Описание</span><span class="sxs-lookup"><span data-stu-id="3851b-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3851b-122">"0"</span><span class="sxs-lookup"><span data-stu-id="3851b-122">"0"</span></span>|<span data-ttu-id="3851b-123">Первый параметр в общем типе.</span><span class="sxs-lookup"><span data-stu-id="3851b-123">The first parameter in the generic type.</span></span> <span data-ttu-id="3851b-124">Например, у <xref:System.Collections.Generic.List%601> есть только один параметр.</span><span class="sxs-lookup"><span data-stu-id="3851b-124">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="3851b-125">Если он используется как объявленный тип, индексу присваивается значение 0.</span><span class="sxs-lookup"><span data-stu-id="3851b-125">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="3851b-126">"1"</span><span class="sxs-lookup"><span data-stu-id="3851b-126">"1"</span></span>|<span data-ttu-id="3851b-127">Второй параметр в общем типе.</span><span class="sxs-lookup"><span data-stu-id="3851b-127">The second parameter in a generic type.</span></span> <span data-ttu-id="3851b-128">Например, у <xref:System.Collections.Generic.Dictionary%602> есть два параметра.</span><span class="sxs-lookup"><span data-stu-id="3851b-128">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="3851b-129">Если известный тип возвращается вторым параметром, атрибуту index присваивается значение 1.</span><span class="sxs-lookup"><span data-stu-id="3851b-129">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3851b-130">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3851b-130">Child Elements</span></span>  
 <span data-ttu-id="3851b-131">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3851b-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3851b-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3851b-132">Parent Elements</span></span>  
  
|<span data-ttu-id="3851b-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="3851b-133">Element</span></span>|<span data-ttu-id="3851b-134">Описание</span><span class="sxs-lookup"><span data-stu-id="3851b-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3851b-135">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="3851b-135">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="3851b-136">Указывает известный тип, который может возвращаться полем или свойством объявленного типа.</span><span class="sxs-lookup"><span data-stu-id="3851b-136">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3851b-137">Примечания</span><span class="sxs-lookup"><span data-stu-id="3851b-137">Remarks</span></span>  
 <span data-ttu-id="3851b-138">Дополнительные сведения об известных типах см. в разделе [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="3851b-138">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="3851b-139">См. в разделе [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) пример использования этого элемента.</span><span class="sxs-lookup"><span data-stu-id="3851b-139">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="3851b-140">У данного элемента конфигурации не может одновременно быть оба атрибута.</span><span class="sxs-lookup"><span data-stu-id="3851b-140">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="3851b-141">Если заданы оба атрибута, возникает исключение <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="3851b-141">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3851b-142">См. также</span><span class="sxs-lookup"><span data-stu-id="3851b-142">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="3851b-143">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="3851b-143">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="3851b-144">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="3851b-144">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="3851b-145">\<add></span><span class="sxs-lookup"><span data-stu-id="3851b-145">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
