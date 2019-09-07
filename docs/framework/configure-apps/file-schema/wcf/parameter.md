---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 07fa410109a7bd2fa315132c4737301698bb3a93
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400114"
---
# <a name="parameter"></a><span data-ttu-id="1e336-101">\<> параметра</span><span class="sxs-lookup"><span data-stu-id="1e336-101">\<parameter></span></span>
<span data-ttu-id="1e336-102">Указывает общий параметр, если объявленный тип является общим типом.</span><span class="sxs-lookup"><span data-stu-id="1e336-102">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
<span data-ttu-id="1e336-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1e336-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1e336-104">&nbsp;&nbsp;[ **\<System. Runtime. Serialization >** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="1e336-104">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="1e336-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dataContractSerializer >** ](datacontractserializer.md)</span><span class="sxs-lookup"><span data-stu-id="1e336-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)</span></span>\
<span data-ttu-id="1e336-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<declaredTypes >** ](declaredtypes.md)</span><span class="sxs-lookup"><span data-stu-id="1e336-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)</span></span>\
<span data-ttu-id="1e336-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Добавить >** ](add-of-declaredtypes-element.md)</span><span class="sxs-lookup"><span data-stu-id="1e336-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)</span></span>\
<span data-ttu-id="1e336-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<knownType >** ](knowntype.md)</span><span class="sxs-lookup"><span data-stu-id="1e336-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownType>**](knowntype.md)</span></span>\
<span data-ttu-id="1e336-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> параметра**</span><span class="sxs-lookup"><span data-stu-id="1e336-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<parameter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e336-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e336-110">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e336-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1e336-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1e336-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1e336-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e336-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1e336-113">Attributes</span></span>  
  
|<span data-ttu-id="1e336-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1e336-114">Attribute</span></span>|<span data-ttu-id="1e336-115">Описание</span><span class="sxs-lookup"><span data-stu-id="1e336-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1e336-116">индекс</span><span class="sxs-lookup"><span data-stu-id="1e336-116">index</span></span>|<span data-ttu-id="1e336-117">Если объявленный тип является общим типом, указывает общий параметр, который возвращает известный тип.</span><span class="sxs-lookup"><span data-stu-id="1e336-117">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="1e336-118">type</span><span class="sxs-lookup"><span data-stu-id="1e336-118">type</span></span>|<span data-ttu-id="1e336-119">Строка, которая описывает известный тип, используемый для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="1e336-119">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="1e336-120">Атрибут index</span><span class="sxs-lookup"><span data-stu-id="1e336-120">index Attribute</span></span>  
  
|<span data-ttu-id="1e336-121">Значение</span><span class="sxs-lookup"><span data-stu-id="1e336-121">Value</span></span>|<span data-ttu-id="1e336-122">Описание</span><span class="sxs-lookup"><span data-stu-id="1e336-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1e336-123">"0"</span><span class="sxs-lookup"><span data-stu-id="1e336-123">"0"</span></span>|<span data-ttu-id="1e336-124">Первый параметр в общем типе.</span><span class="sxs-lookup"><span data-stu-id="1e336-124">The first parameter in the generic type.</span></span> <span data-ttu-id="1e336-125">Например, у <xref:System.Collections.Generic.List%601> есть только один параметр.</span><span class="sxs-lookup"><span data-stu-id="1e336-125">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="1e336-126">Если он используется как объявленный тип, индексу присваивается значение 0.</span><span class="sxs-lookup"><span data-stu-id="1e336-126">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="1e336-127">"1"</span><span class="sxs-lookup"><span data-stu-id="1e336-127">"1"</span></span>|<span data-ttu-id="1e336-128">Второй параметр в общем типе.</span><span class="sxs-lookup"><span data-stu-id="1e336-128">The second parameter in a generic type.</span></span> <span data-ttu-id="1e336-129">Например, у <xref:System.Collections.Generic.Dictionary%602> есть два параметра.</span><span class="sxs-lookup"><span data-stu-id="1e336-129">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="1e336-130">Если известный тип возвращается вторым параметром, атрибуту index присваивается значение 1.</span><span class="sxs-lookup"><span data-stu-id="1e336-130">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e336-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1e336-131">Child Elements</span></span>  
 <span data-ttu-id="1e336-132">Нет.</span><span class="sxs-lookup"><span data-stu-id="1e336-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1e336-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1e336-133">Parent Elements</span></span>  
  
|<span data-ttu-id="1e336-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="1e336-134">Element</span></span>|<span data-ttu-id="1e336-135">Описание</span><span class="sxs-lookup"><span data-stu-id="1e336-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e336-136">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="1e336-136">\<knownType></span></span>](knowntype.md)|<span data-ttu-id="1e336-137">Указывает известный тип, который может возвращаться полем или свойством объявленного типа.</span><span class="sxs-lookup"><span data-stu-id="1e336-137">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e336-138">Примечания</span><span class="sxs-lookup"><span data-stu-id="1e336-138">Remarks</span></span>  
 <span data-ttu-id="1e336-139">Дополнительные сведения об известных типах см. в статье о [известных типах контрактов данных](../../../wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="1e336-139">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="1e336-140">Пример использования этого элемента см. в [ \<> dataContractSerializer](datacontractserializer-element.md) .</span><span class="sxs-lookup"><span data-stu-id="1e336-140">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="1e336-141">У данного элемента конфигурации не может одновременно быть оба атрибута.</span><span class="sxs-lookup"><span data-stu-id="1e336-141">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="1e336-142">Если заданы оба атрибута, возникает исключение <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="1e336-142">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e336-143">См. также</span><span class="sxs-lookup"><span data-stu-id="1e336-143">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="1e336-144">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="1e336-144">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="1e336-145">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="1e336-145">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="1e336-146">\<add></span><span class="sxs-lookup"><span data-stu-id="1e336-146">\<add></span></span>](add-of-declaredtypes-element.md)
