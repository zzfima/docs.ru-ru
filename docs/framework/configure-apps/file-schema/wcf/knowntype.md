---
title: '&lt;knownType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ccb7152197a021821936e178e0de77b9dfabce45
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltknowntypegt"></a><span data-ttu-id="65768-102">&lt;knownType&gt;</span><span class="sxs-lookup"><span data-stu-id="65768-102">&lt;knownType&gt;</span></span>
<span data-ttu-id="65768-103">Задает тип, используемый <xref:System.Runtime.Serialization.DataContractSerializer> во время десериализации.</span><span class="sxs-lookup"><span data-stu-id="65768-103">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="65768-104">Элемент задает «известный тип», возвращаемый полем или свойством «объявленного типа».</span><span class="sxs-lookup"><span data-stu-id="65768-104">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="65768-105">Дополнительные сведения см. в разделе [известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="65768-105">For more information, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="65768-106">\<System.Runtime.Serialization ></span><span class="sxs-lookup"><span data-stu-id="65768-106">\<system.runtime.serialization></span></span>  
<span data-ttu-id="65768-107">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="65768-107">\<dataContractSerializer></span></span>  
<span data-ttu-id="65768-108">\<declaredTypes > элемент</span><span class="sxs-lookup"><span data-stu-id="65768-108">\<declaredTypes> Element</span></span>  
<span data-ttu-id="65768-109">\<Добавить > из \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="65768-109">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="65768-110">\<knownType > элемент</span><span class="sxs-lookup"><span data-stu-id="65768-110">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65768-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65768-111">Syntax</span></span>  
  
```xml  
<knownType type="String">  
     <parameter index="Integer"  
                type="String" />  
</knownType>  
```  
  
## <a name="type"></a><span data-ttu-id="65768-112">Тип</span><span class="sxs-lookup"><span data-stu-id="65768-112">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65768-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="65768-113">Attributes and Elements</span></span>  
 <span data-ttu-id="65768-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="65768-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65768-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="65768-115">Attributes</span></span>  
  
|<span data-ttu-id="65768-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="65768-116">Attribute</span></span>|<span data-ttu-id="65768-117">Описание</span><span class="sxs-lookup"><span data-stu-id="65768-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="65768-118">тип</span><span class="sxs-lookup"><span data-stu-id="65768-118">type</span></span>|<span data-ttu-id="65768-119">Задает тип (в том числе пространство имен), имя сборки, версию, язык и региональные параметры и маркер открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="65768-119">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="65768-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="65768-120">Child Elements</span></span>  
  
|<span data-ttu-id="65768-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="65768-121">Element</span></span>|<span data-ttu-id="65768-122">Описание</span><span class="sxs-lookup"><span data-stu-id="65768-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65768-123">\<параметр ></span><span class="sxs-lookup"><span data-stu-id="65768-123">\<parameter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/parameter.md)|<span data-ttu-id="65768-124">Задает индекс параметра в том случае, если объявленный тип является универсальным типом.</span><span class="sxs-lookup"><span data-stu-id="65768-124">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="65768-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="65768-125">Parent Elements</span></span>  
  
|<span data-ttu-id="65768-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="65768-126">Element</span></span>|<span data-ttu-id="65768-127">Описание</span><span class="sxs-lookup"><span data-stu-id="65768-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65768-128">\<add></span><span class="sxs-lookup"><span data-stu-id="65768-128">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="65768-129">Добавляет объявленный тип в коллекцию объявленных типов.</span><span class="sxs-lookup"><span data-stu-id="65768-129">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65768-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="65768-130">Remarks</span></span>  
 <span data-ttu-id="65768-131">Дополнительные сведения об известных типах см. в разделе [известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="65768-131">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="65768-132">В разделе [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) пример использования этого элемента.</span><span class="sxs-lookup"><span data-stu-id="65768-132">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65768-133">Пример</span><span class="sxs-lookup"><span data-stu-id="65768-133">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="65768-134">См. также</span><span class="sxs-lookup"><span data-stu-id="65768-134">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="65768-135">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="65768-135">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="65768-136">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="65768-136">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="65768-137">\<add></span><span class="sxs-lookup"><span data-stu-id="65768-137">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
