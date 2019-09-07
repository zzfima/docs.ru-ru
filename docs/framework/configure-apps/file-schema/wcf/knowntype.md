---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 61f51b2ecd572ba254317a01e0f514503c7cc9e4
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397869"
---
# <a name="knowntype"></a><span data-ttu-id="0a3ab-101">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="0a3ab-101">\<knownType></span></span>
<span data-ttu-id="0a3ab-102">Задает тип, используемый <xref:System.Runtime.Serialization.DataContractSerializer> во время десериализации.</span><span class="sxs-lookup"><span data-stu-id="0a3ab-102">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="0a3ab-103">Элемент задает «известный тип», возвращаемый полем или свойством «объявленного типа».</span><span class="sxs-lookup"><span data-stu-id="0a3ab-103">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="0a3ab-104">Дополнительные сведения см. в статье о [известных типах контрактов данных](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="0a3ab-104">For more information, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
<span data-ttu-id="0a3ab-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0a3ab-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0a3ab-106">&nbsp;&nbsp;[ **\<System. Runtime. Serialization >** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="0a3ab-106">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="0a3ab-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dataContractSerializer >** ](datacontractserializer.md)</span><span class="sxs-lookup"><span data-stu-id="0a3ab-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)</span></span>\
<span data-ttu-id="0a3ab-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<declaredTypes >** ](declaredtypes.md)</span><span class="sxs-lookup"><span data-stu-id="0a3ab-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)</span></span>\
<span data-ttu-id="0a3ab-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Добавить >** ](add-of-declaredtypes-element.md)</span><span class="sxs-lookup"><span data-stu-id="0a3ab-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)</span></span>\
<span data-ttu-id="0a3ab-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<knownType >**</span><span class="sxs-lookup"><span data-stu-id="0a3ab-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a3ab-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a3ab-111">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="0a3ab-112">Тип</span><span class="sxs-lookup"><span data-stu-id="0a3ab-112">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a3ab-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0a3ab-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0a3ab-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0a3ab-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a3ab-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0a3ab-115">Attributes</span></span>  
  
|<span data-ttu-id="0a3ab-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0a3ab-116">Attribute</span></span>|<span data-ttu-id="0a3ab-117">Описание</span><span class="sxs-lookup"><span data-stu-id="0a3ab-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0a3ab-118">type</span><span class="sxs-lookup"><span data-stu-id="0a3ab-118">type</span></span>|<span data-ttu-id="0a3ab-119">Задает тип (в том числе пространство имен), имя сборки, версию, язык и региональные параметры и маркер открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="0a3ab-119">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0a3ab-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0a3ab-120">Child Elements</span></span>  
  
|<span data-ttu-id="0a3ab-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="0a3ab-121">Element</span></span>|<span data-ttu-id="0a3ab-122">Описание</span><span class="sxs-lookup"><span data-stu-id="0a3ab-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a3ab-123">\<> параметра</span><span class="sxs-lookup"><span data-stu-id="0a3ab-123">\<parameter></span></span>](parameter.md)|<span data-ttu-id="0a3ab-124">Задает индекс параметра в том случае, если объявленный тип является универсальным типом.</span><span class="sxs-lookup"><span data-stu-id="0a3ab-124">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0a3ab-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0a3ab-125">Parent Elements</span></span>  
  
|<span data-ttu-id="0a3ab-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="0a3ab-126">Element</span></span>|<span data-ttu-id="0a3ab-127">Описание</span><span class="sxs-lookup"><span data-stu-id="0a3ab-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a3ab-128">\<add></span><span class="sxs-lookup"><span data-stu-id="0a3ab-128">\<add></span></span>](add-of-declaredtypes-element.md)|<span data-ttu-id="0a3ab-129">Добавляет объявленный тип в коллекцию объявленных типов.</span><span class="sxs-lookup"><span data-stu-id="0a3ab-129">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a3ab-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="0a3ab-130">Remarks</span></span>  
 <span data-ttu-id="0a3ab-131">Дополнительные сведения об известных типах см. в статье о [известных типах контрактов данных](../../../wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="0a3ab-131">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="0a3ab-132">Пример использования этого элемента см. в [ \<> dataContractSerializer](datacontractserializer-element.md) .</span><span class="sxs-lookup"><span data-stu-id="0a3ab-132">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a3ab-133">Пример</span><span class="sxs-lookup"><span data-stu-id="0a3ab-133">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0a3ab-134">См. также</span><span class="sxs-lookup"><span data-stu-id="0a3ab-134">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="0a3ab-135">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="0a3ab-135">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="0a3ab-136">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="0a3ab-136">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="0a3ab-137">\<add></span><span class="sxs-lookup"><span data-stu-id="0a3ab-137">\<add></span></span>](add-of-declaredtypes-element.md)
