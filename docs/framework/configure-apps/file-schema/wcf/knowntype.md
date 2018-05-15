---
title: '&lt;knownType&gt;'
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: b2445f12f1eaac03b3f3ab66f3d13a5f465a1133
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltknowntypegt"></a><span data-ttu-id="8657c-102">&lt;knownType&gt;</span><span class="sxs-lookup"><span data-stu-id="8657c-102">&lt;knownType&gt;</span></span>
<span data-ttu-id="8657c-103">Задает тип, используемый <xref:System.Runtime.Serialization.DataContractSerializer> во время десериализации.</span><span class="sxs-lookup"><span data-stu-id="8657c-103">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="8657c-104">Элемент задает «известный тип», возвращаемый полем или свойством «объявленного типа».</span><span class="sxs-lookup"><span data-stu-id="8657c-104">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="8657c-105">Дополнительные сведения см. в разделе [известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="8657c-105">For more information, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="8657c-106">\<System.Runtime.Serialization ></span><span class="sxs-lookup"><span data-stu-id="8657c-106">\<system.runtime.serialization></span></span>  
<span data-ttu-id="8657c-107">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="8657c-107">\<dataContractSerializer></span></span>  
<span data-ttu-id="8657c-108">\<declaredTypes > элемент</span><span class="sxs-lookup"><span data-stu-id="8657c-108">\<declaredTypes> Element</span></span>  
<span data-ttu-id="8657c-109">\<Добавить > из \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="8657c-109">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="8657c-110">\<knownType > элемент</span><span class="sxs-lookup"><span data-stu-id="8657c-110">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8657c-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8657c-111">Syntax</span></span>  
  
```xml  
<knownType type="String">  
     <parameter index="Integer"  
                type="String" />  
</knownType>  
```  
  
## <a name="type"></a><span data-ttu-id="8657c-112">Тип</span><span class="sxs-lookup"><span data-stu-id="8657c-112">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8657c-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8657c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="8657c-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8657c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8657c-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8657c-115">Attributes</span></span>  
  
|<span data-ttu-id="8657c-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8657c-116">Attribute</span></span>|<span data-ttu-id="8657c-117">Описание</span><span class="sxs-lookup"><span data-stu-id="8657c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8657c-118">тип</span><span class="sxs-lookup"><span data-stu-id="8657c-118">type</span></span>|<span data-ttu-id="8657c-119">Задает тип (в том числе пространство имен), имя сборки, версию, язык и региональные параметры и маркер открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="8657c-119">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8657c-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8657c-120">Child Elements</span></span>  
  
|<span data-ttu-id="8657c-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="8657c-121">Element</span></span>|<span data-ttu-id="8657c-122">Описание</span><span class="sxs-lookup"><span data-stu-id="8657c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8657c-123">\<параметр ></span><span class="sxs-lookup"><span data-stu-id="8657c-123">\<parameter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/parameter.md)|<span data-ttu-id="8657c-124">Задает индекс параметра в том случае, если объявленный тип является универсальным типом.</span><span class="sxs-lookup"><span data-stu-id="8657c-124">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8657c-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8657c-125">Parent Elements</span></span>  
  
|<span data-ttu-id="8657c-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="8657c-126">Element</span></span>|<span data-ttu-id="8657c-127">Описание</span><span class="sxs-lookup"><span data-stu-id="8657c-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8657c-128">\<add></span><span class="sxs-lookup"><span data-stu-id="8657c-128">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="8657c-129">Добавляет объявленный тип в коллекцию объявленных типов.</span><span class="sxs-lookup"><span data-stu-id="8657c-129">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8657c-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="8657c-130">Remarks</span></span>  
 <span data-ttu-id="8657c-131">Дополнительные сведения об известных типах см. в разделе [известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8657c-131">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="8657c-132">В разделе [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) пример использования этого элемента.</span><span class="sxs-lookup"><span data-stu-id="8657c-132">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8657c-133">Пример</span><span class="sxs-lookup"><span data-stu-id="8657c-133">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,   
           MyAssembly, Version=2.0.0.0, Culture=neutral,  
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">  
           <knownType type="MyCompany.Library.Circle,   
                      MyAssembly, Version=2.0.0.0, Culture=neutral,  
                      PublicKeyToken=XXXXXX,  
                      processorArchitecture=MSIL"/>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8657c-134">См. также</span><span class="sxs-lookup"><span data-stu-id="8657c-134">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="8657c-135">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="8657c-135">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="8657c-136">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="8657c-136">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="8657c-137">\<add></span><span class="sxs-lookup"><span data-stu-id="8657c-137">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
