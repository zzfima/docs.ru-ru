---
title: '&lt; add&gt; элемента &lt;declaredTypes&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: dd5972c2bb25367f2566bcf77e53e7a3341d89b4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519467"
---
# <a name="ltaddgt-of-ltdeclaredtypesgt-element"></a><span data-ttu-id="f6adc-102">&lt; add&gt; элемента &lt;declaredTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="f6adc-102">&lt;add&gt; of &lt;declaredTypes&gt; Element</span></span>
<span data-ttu-id="f6adc-103">Добавляет тип, используемый <xref:System.Runtime.Serialization.DataContractSerializer> во время десериализации.</span><span class="sxs-lookup"><span data-stu-id="f6adc-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="f6adc-104">В каждый объявленный тип включены известные типы, которые будут возвращены как поле или свойство объявленного типа.</span><span class="sxs-lookup"><span data-stu-id="f6adc-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
 <span data-ttu-id="f6adc-105">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="f6adc-105">system.runtime.serialization</span></span>  
<span data-ttu-id="f6adc-106">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="f6adc-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="f6adc-107">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="f6adc-107">\<declaredTypes></span></span>  
<span data-ttu-id="f6adc-108">\<Добавить > из \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="f6adc-108">\<add> of \<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6adc-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6adc-109">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6adc-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f6adc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f6adc-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f6adc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6adc-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f6adc-112">Attributes</span></span>  
  
|<span data-ttu-id="f6adc-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f6adc-113">Attribute</span></span>|<span data-ttu-id="f6adc-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f6adc-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f6adc-115">тип</span><span class="sxs-lookup"><span data-stu-id="f6adc-115">type</span></span>|<span data-ttu-id="f6adc-116">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="f6adc-116">Required string attribute.</span></span><br /><br /> <span data-ttu-id="f6adc-117">Задает имя типа (в том числе пространство имен), имя сборки, номер версии, язык и региональные параметры и маркер открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="f6adc-117">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f6adc-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f6adc-118">Child Elements</span></span>  
  
|<span data-ttu-id="f6adc-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="f6adc-119">Element</span></span>|<span data-ttu-id="f6adc-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="f6adc-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f6adc-121">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="f6adc-121">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="f6adc-122">Задает известный тип для добавляемого объявленного типа.</span><span class="sxs-lookup"><span data-stu-id="f6adc-122">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="f6adc-123">Если объявленный тип является универсальным типом, необходимо также добавить элемент параметра к элементу `<knownType>`, чтобы указать, какой универсальный параметр будет использоваться для возвращения известного типа.</span><span class="sxs-lookup"><span data-stu-id="f6adc-123">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f6adc-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f6adc-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f6adc-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="f6adc-125">Element</span></span>|<span data-ttu-id="f6adc-126">Описание</span><span class="sxs-lookup"><span data-stu-id="f6adc-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f6adc-127">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="f6adc-127">\<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|<span data-ttu-id="f6adc-128">Содержит типы, для которых необходимы известные типы во время десериализации с помощью <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="f6adc-128">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6adc-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="f6adc-129">Remarks</span></span>  
 <span data-ttu-id="f6adc-130">Дополнительные сведения об известных типах см. в разделе [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="f6adc-130">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="f6adc-131">См. в разделе [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) пример использования этого элемента.</span><span class="sxs-lookup"><span data-stu-id="f6adc-131">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6adc-132">При добавлении типа <xref:System.Object> как `<declaredType>` возникает <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="f6adc-132">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="f6adc-133">Это обусловлено тем, что тип <xref:System.Object> нельзя использовать как объявленный тип в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f6adc-133">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6adc-134">Пример</span><span class="sxs-lookup"><span data-stu-id="f6adc-134">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL" />
</add>
```  
  
## <a name="see-also"></a><span data-ttu-id="f6adc-135">См. также</span><span class="sxs-lookup"><span data-stu-id="f6adc-135">See also</span></span>
- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="f6adc-136">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="f6adc-136">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="f6adc-137">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="f6adc-137">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="f6adc-138">\<Добавить > из \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="f6adc-138">\<add> of \<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
