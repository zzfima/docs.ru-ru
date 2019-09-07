---
title: <declaredTypes>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- declaredTypes element
- DataContractSerializer
- KnownTypes
- <declaredTypes> element
ms.assetid: f35184e4-9d9e-4d37-8fb4-d5b58220eb3e
ms.openlocfilehash: c45a4e67d0a2d98c0e9c1a91e07f25b81370244c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398052"
---
# <a name="declaredtypes"></a><span data-ttu-id="0bd72-101">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="0bd72-101">\<declaredTypes></span></span>
<span data-ttu-id="0bd72-102">Содержит известные типы, которые <xref:System.Runtime.Serialization.DataContractSerializer> использует при десериализации.</span><span class="sxs-lookup"><span data-stu-id="0bd72-102">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span>  
  
 <span data-ttu-id="0bd72-103">Дополнительные сведения о контрактах данных и известных типах см. в статье о [известных типах контрактов данных](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="0bd72-103">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
<span data-ttu-id="0bd72-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0bd72-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0bd72-105">&nbsp;&nbsp;[ **\<System. Runtime. Serialization >** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="0bd72-105">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="0bd72-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dataContractSerializer >** ](datacontractserializer.md)</span><span class="sxs-lookup"><span data-stu-id="0bd72-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)</span></span>\
<span data-ttu-id="0bd72-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<declaredTypes >**</span><span class="sxs-lookup"><span data-stu-id="0bd72-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<declaredTypes>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bd72-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0bd72-108">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="String ">
          <knownType type="String">
            <parameter index="Integer"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0bd72-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0bd72-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0bd72-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0bd72-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0bd72-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0bd72-111">Attributes</span></span>  
 <span data-ttu-id="0bd72-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="0bd72-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0bd72-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0bd72-113">Child Elements</span></span>  
  
|<span data-ttu-id="0bd72-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="0bd72-114">Element</span></span>|<span data-ttu-id="0bd72-115">Описание</span><span class="sxs-lookup"><span data-stu-id="0bd72-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0bd72-116">\<add></span><span class="sxs-lookup"><span data-stu-id="0bd72-116">\<add></span></span>](add-of-declaredtypes-element.md)|<span data-ttu-id="0bd72-117">Добавляет типы, для которых необходимы известные типы.</span><span class="sxs-lookup"><span data-stu-id="0bd72-117">Adds types that require known types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0bd72-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0bd72-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0bd72-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="0bd72-119">Element</span></span>|<span data-ttu-id="0bd72-120">Описание</span><span class="sxs-lookup"><span data-stu-id="0bd72-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0bd72-121">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="0bd72-121">\<dataContractSerializer></span></span>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="0bd72-122">Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="0bd72-122">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0bd72-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="0bd72-123">Remarks</span></span>  
 <span data-ttu-id="0bd72-124">Дополнительные сведения об известных типах см. в статье о [известных типах контрактов данных](../../../wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="0bd72-124">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bd72-125">Пример</span><span class="sxs-lookup"><span data-stu-id="0bd72-125">Example</span></span>  
 <span data-ttu-id="0bd72-126">В следующем коде XML показаны объявленные типы и известные типы, добавленные в `DataContractSerializer` элемент.</span><span class="sxs-lookup"><span data-stu-id="0bd72-126">The following XML code shows declared types and known types added to a `DataContractSerializer` element.</span></span> <span data-ttu-id="0bd72-127">В этом примере показаны три добавляемых типа.</span><span class="sxs-lookup"><span data-stu-id="0bd72-127">The example shows three types being added.</span></span> <span data-ttu-id="0bd72-128">Первый тип - это пользовательский тип с именем «Orders», использующий известный тип с именем «Item».</span><span class="sxs-lookup"><span data-stu-id="0bd72-128">The first is a custom type named "Orders" that uses a known type named "Item".</span></span> <span data-ttu-id="0bd72-129">Второй объявленный тип - это <xref:System.Collections.Generic.List%601>, использующий `Item` в качестве известного типа.</span><span class="sxs-lookup"><span data-stu-id="0bd72-129">The second declared type is a <xref:System.Collections.Generic.List%601> that uses `Item` as a known type.</span></span> <span data-ttu-id="0bd72-130">Наконец, третий объявленный тип - это <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="0bd72-130">Finally the third declared type is a <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="0bd72-131">Тип класса <xref:System.Collections.Generic.Dictionary%602> является универсальным типом с двумя параметрами типов.</span><span class="sxs-lookup"><span data-stu-id="0bd72-131">The <xref:System.Collections.Generic.Dictionary%602> class type is a generic type, with two type parameters.</span></span> <span data-ttu-id="0bd72-132">Первый представляет ключ, а второй представляет значение.</span><span class="sxs-lookup"><span data-stu-id="0bd72-132">The first represents the key and the second represents the value.</span></span> <span data-ttu-id="0bd72-133">В следующем примере параметр второго типа <xref:System.Collections.Generic.List%601> (значение) добавляется к списку известных типов.</span><span class="sxs-lookup"><span data-stu-id="0bd72-133">The following example adds a <xref:System.Collections.Generic.List%601> of the second type (the value) to the list of known types.</span></span> <span data-ttu-id="0bd72-134">Чтобы задать параметр типа для использования в известном типе, необходимо использовать атрибут `index`.</span><span class="sxs-lookup"><span data-stu-id="0bd72-134">You must use the `index` attribute to specify which type parameter to use in the known type.</span></span> <span data-ttu-id="0bd72-135">В данном примере тип значения указан атрибутом индекса, для которого задано значение 1 (коллекция начинается с нуля).</span><span class="sxs-lookup"><span data-stu-id="0bd72-135">In this case, the value type is indicated by the index attribute set to "1" (the collection is zero-based).</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="Examples.Types.Orders, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.Dictionary`2, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
            <parameter index="1"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="0bd72-136">См. также</span><span class="sxs-lookup"><span data-stu-id="0bd72-136">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="0bd72-137">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="0bd72-137">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="0bd72-138">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="0bd72-138">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="0bd72-139">\<add></span><span class="sxs-lookup"><span data-stu-id="0bd72-139">\<add></span></span>](add-of-declaredtypes-element.md)
