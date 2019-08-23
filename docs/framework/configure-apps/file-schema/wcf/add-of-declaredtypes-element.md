---
title: <add> элемента <declaredTypes>
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: 1ea008dcc72d555b00e9648ace95bb9522ffc2c8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920176"
---
# <a name="add-of-declaredtypes-element"></a><span data-ttu-id="228e2-102">\<Добавление > \<элемента > declaredTypes</span><span class="sxs-lookup"><span data-stu-id="228e2-102">\<add> of \<declaredTypes> Element</span></span>
<span data-ttu-id="228e2-103">Добавляет тип, используемый <xref:System.Runtime.Serialization.DataContractSerializer> во время десериализации.</span><span class="sxs-lookup"><span data-stu-id="228e2-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="228e2-104">В каждый объявленный тип включены известные типы, которые будут возвращены как поле или свойство объявленного типа.</span><span class="sxs-lookup"><span data-stu-id="228e2-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
 <span data-ttu-id="228e2-105">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="228e2-105">system.runtime.serialization</span></span>  
<span data-ttu-id="228e2-106">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="228e2-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="228e2-107">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="228e2-107">\<declaredTypes></span></span>  
<span data-ttu-id="228e2-108">\<Добавление > \<> declaredTypes</span><span class="sxs-lookup"><span data-stu-id="228e2-108">\<add> of \<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="228e2-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="228e2-109">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="228e2-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="228e2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="228e2-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="228e2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="228e2-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="228e2-112">Attributes</span></span>  
  
|<span data-ttu-id="228e2-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="228e2-113">Attribute</span></span>|<span data-ttu-id="228e2-114">Описание</span><span class="sxs-lookup"><span data-stu-id="228e2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="228e2-115">type</span><span class="sxs-lookup"><span data-stu-id="228e2-115">type</span></span>|<span data-ttu-id="228e2-116">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="228e2-116">Required string attribute.</span></span><br /><br /> <span data-ttu-id="228e2-117">Задает имя типа (в том числе пространство имен), имя сборки, номер версии, язык и региональные параметры и маркер открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="228e2-117">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="228e2-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="228e2-118">Child Elements</span></span>  
  
|<span data-ttu-id="228e2-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="228e2-119">Element</span></span>|<span data-ttu-id="228e2-120">Описание</span><span class="sxs-lookup"><span data-stu-id="228e2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="228e2-121">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="228e2-121">\<knownType></span></span>](knowntype.md)|<span data-ttu-id="228e2-122">Задает известный тип для добавляемого объявленного типа.</span><span class="sxs-lookup"><span data-stu-id="228e2-122">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="228e2-123">Если объявленный тип является универсальным типом, необходимо также добавить элемент параметра к элементу `<knownType>`, чтобы указать, какой универсальный параметр будет использоваться для возвращения известного типа.</span><span class="sxs-lookup"><span data-stu-id="228e2-123">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="228e2-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="228e2-124">Parent Elements</span></span>  
  
|<span data-ttu-id="228e2-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="228e2-125">Element</span></span>|<span data-ttu-id="228e2-126">Описание</span><span class="sxs-lookup"><span data-stu-id="228e2-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="228e2-127">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="228e2-127">\<declaredTypes></span></span>](declaredtypes.md)|<span data-ttu-id="228e2-128">Содержит типы, для которых необходимы известные типы во время десериализации с помощью <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="228e2-128">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="228e2-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="228e2-129">Remarks</span></span>  
 <span data-ttu-id="228e2-130">Дополнительные сведения об известных типах см. в статье о [известных типах контрактов данных](../../../wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="228e2-130">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="228e2-131">Пример использования этого элемента см. в [ \<> dataContractSerializer](datacontractserializer-element.md) .</span><span class="sxs-lookup"><span data-stu-id="228e2-131">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="228e2-132">При добавлении типа <xref:System.Object> как `<declaredType>` возникает <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="228e2-132">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="228e2-133">Это обусловлено тем, что тип <xref:System.Object> нельзя использовать как объявленный тип в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="228e2-133">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="228e2-134">Пример</span><span class="sxs-lookup"><span data-stu-id="228e2-134">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="228e2-135">См. также</span><span class="sxs-lookup"><span data-stu-id="228e2-135">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="228e2-136">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="228e2-136">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="228e2-137">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="228e2-137">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="228e2-138">\<Добавление > \<> declaredTypes</span><span class="sxs-lookup"><span data-stu-id="228e2-138">\<add> of \<declaredTypes></span></span>](add-of-declaredtypes-element.md)
