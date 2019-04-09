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
ms.openlocfilehash: 8919ee717012f8badcf7015bf8d850ed431c5943
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090281"
---
# <a name="declaredtypes"></a><span data-ttu-id="dc707-101">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="dc707-101">\<declaredTypes></span></span>
<span data-ttu-id="dc707-102">Содержит известные типы, которые <xref:System.Runtime.Serialization.DataContractSerializer> использует при десериализации.</span><span class="sxs-lookup"><span data-stu-id="dc707-102">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span>  
  
 <span data-ttu-id="dc707-103">Дополнительные сведения о контрактах данных и известных типов, см. в разделе [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="dc707-103">For more information about data contracts and known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="dc707-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="dc707-104">system.runtime.serialization</span></span>  
<span data-ttu-id="dc707-105">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="dc707-105">\<dataContractSerializer></span></span>  
<span data-ttu-id="dc707-106">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="dc707-106">\<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc707-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc707-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc707-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dc707-108">Attributes and Elements</span></span>  
 <span data-ttu-id="dc707-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dc707-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc707-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dc707-110">Attributes</span></span>  
 <span data-ttu-id="dc707-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="dc707-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dc707-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dc707-112">Child Elements</span></span>  
  
|<span data-ttu-id="dc707-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="dc707-113">Element</span></span>|<span data-ttu-id="dc707-114">Описание</span><span class="sxs-lookup"><span data-stu-id="dc707-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc707-115">\<add></span><span class="sxs-lookup"><span data-stu-id="dc707-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="dc707-116">Добавляет типы, для которых необходимы известные типы.</span><span class="sxs-lookup"><span data-stu-id="dc707-116">Adds types that require known types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dc707-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dc707-117">Parent Elements</span></span>  
  
|<span data-ttu-id="dc707-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="dc707-118">Element</span></span>|<span data-ttu-id="dc707-119">Описание</span><span class="sxs-lookup"><span data-stu-id="dc707-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc707-120">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="dc707-120">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="dc707-121">Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="dc707-121">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc707-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="dc707-122">Remarks</span></span>  
 <span data-ttu-id="dc707-123">Дополнительные сведения об известных типах см. в разделе [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="dc707-123">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc707-124">Пример</span><span class="sxs-lookup"><span data-stu-id="dc707-124">Example</span></span>  
 <span data-ttu-id="dc707-125">Приведенный ниже код XML показывает объявленные типы и известных типов, добавленных к `DataContractSerializer` элемент.</span><span class="sxs-lookup"><span data-stu-id="dc707-125">The following XML code shows declared types and known types added to a `DataContractSerializer` element.</span></span> <span data-ttu-id="dc707-126">В этом примере показаны три добавляемых типа.</span><span class="sxs-lookup"><span data-stu-id="dc707-126">The example shows three types being added.</span></span> <span data-ttu-id="dc707-127">Первый тип - это пользовательский тип с именем «Orders», использующий известный тип с именем «Item».</span><span class="sxs-lookup"><span data-stu-id="dc707-127">The first is a custom type named "Orders" that uses a known type named "Item".</span></span> <span data-ttu-id="dc707-128">Второй объявленный тип - это <xref:System.Collections.Generic.List%601>, использующий `Item` в качестве известного типа.</span><span class="sxs-lookup"><span data-stu-id="dc707-128">The second declared type is a <xref:System.Collections.Generic.List%601> that uses `Item` as a known type.</span></span> <span data-ttu-id="dc707-129">Наконец, третий объявленный тип - это <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="dc707-129">Finally the third declared type is a <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="dc707-130">Тип класса <xref:System.Collections.Generic.Dictionary%602> является универсальным типом с двумя параметрами типов.</span><span class="sxs-lookup"><span data-stu-id="dc707-130">The <xref:System.Collections.Generic.Dictionary%602> class type is a generic type, with two type parameters.</span></span> <span data-ttu-id="dc707-131">Первый представляет ключ, а второй представляет значение.</span><span class="sxs-lookup"><span data-stu-id="dc707-131">The first represents the key and the second represents the value.</span></span> <span data-ttu-id="dc707-132">В следующем примере параметр второго типа <xref:System.Collections.Generic.List%601> (значение) добавляется к списку известных типов.</span><span class="sxs-lookup"><span data-stu-id="dc707-132">The following example adds a <xref:System.Collections.Generic.List%601> of the second type (the value) to the list of known types.</span></span> <span data-ttu-id="dc707-133">Чтобы задать параметр типа для использования в известном типе, необходимо использовать атрибут `index`.</span><span class="sxs-lookup"><span data-stu-id="dc707-133">You must use the `index` attribute to specify which type parameter to use in the known type.</span></span> <span data-ttu-id="dc707-134">В данном примере тип значения указан атрибутом индекса, для которого задано значение 1 (коллекция начинается с нуля).</span><span class="sxs-lookup"><span data-stu-id="dc707-134">In this case, the value type is indicated by the index attribute set to "1" (the collection is zero-based).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dc707-135">См. также</span><span class="sxs-lookup"><span data-stu-id="dc707-135">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="dc707-136">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="dc707-136">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="dc707-137">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="dc707-137">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="dc707-138">\<add></span><span class="sxs-lookup"><span data-stu-id="dc707-138">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
