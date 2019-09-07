---
title: <add> элемента <declaredTypes>
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: a001e8743b2c24f68b1b23cbccf3e5ac162c4e71
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400659"
---
# <a name="add-of-declaredtypes-element"></a><span data-ttu-id="9d550-102">\<Добавление > \<элемента > declaredTypes</span><span class="sxs-lookup"><span data-stu-id="9d550-102">\<add> of \<declaredTypes> Element</span></span>
<span data-ttu-id="9d550-103">Добавляет тип, используемый <xref:System.Runtime.Serialization.DataContractSerializer> во время десериализации.</span><span class="sxs-lookup"><span data-stu-id="9d550-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="9d550-104">В каждый объявленный тип включены известные типы, которые будут возвращены как поле или свойство объявленного типа.</span><span class="sxs-lookup"><span data-stu-id="9d550-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
<span data-ttu-id="9d550-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9d550-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9d550-106">&nbsp;&nbsp;[ **\<System. Runtime. Serialization >** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="9d550-106">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="9d550-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dataContractSerializer >** ](datacontractserializer.md)</span><span class="sxs-lookup"><span data-stu-id="9d550-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)</span></span>\
<span data-ttu-id="9d550-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<declaredTypes >** ](declaredtypes.md)</span><span class="sxs-lookup"><span data-stu-id="9d550-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)</span></span>\
<span data-ttu-id="9d550-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="9d550-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d550-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d550-110">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d550-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9d550-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9d550-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9d550-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d550-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9d550-113">Attributes</span></span>  
  
|<span data-ttu-id="9d550-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9d550-114">Attribute</span></span>|<span data-ttu-id="9d550-115">Описание</span><span class="sxs-lookup"><span data-stu-id="9d550-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9d550-116">type</span><span class="sxs-lookup"><span data-stu-id="9d550-116">type</span></span>|<span data-ttu-id="9d550-117">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="9d550-117">Required string attribute.</span></span><br /><br /> <span data-ttu-id="9d550-118">Задает имя типа (в том числе пространство имен), имя сборки, номер версии, язык и региональные параметры и маркер открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="9d550-118">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d550-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9d550-119">Child Elements</span></span>  
  
|<span data-ttu-id="9d550-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="9d550-120">Element</span></span>|<span data-ttu-id="9d550-121">Описание</span><span class="sxs-lookup"><span data-stu-id="9d550-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d550-122">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="9d550-122">\<knownType></span></span>](knowntype.md)|<span data-ttu-id="9d550-123">Задает известный тип для добавляемого объявленного типа.</span><span class="sxs-lookup"><span data-stu-id="9d550-123">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="9d550-124">Если объявленный тип является универсальным типом, необходимо также добавить элемент параметра к элементу `<knownType>`, чтобы указать, какой универсальный параметр будет использоваться для возвращения известного типа.</span><span class="sxs-lookup"><span data-stu-id="9d550-124">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9d550-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9d550-125">Parent Elements</span></span>  
  
|<span data-ttu-id="9d550-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="9d550-126">Element</span></span>|<span data-ttu-id="9d550-127">Описание</span><span class="sxs-lookup"><span data-stu-id="9d550-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d550-128">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="9d550-128">\<declaredTypes></span></span>](declaredtypes.md)|<span data-ttu-id="9d550-129">Содержит типы, для которых необходимы известные типы во время десериализации с помощью <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="9d550-129">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d550-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="9d550-130">Remarks</span></span>  
 <span data-ttu-id="9d550-131">Дополнительные сведения об известных типах см. в статье о [известных типах контрактов данных](../../../wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="9d550-131">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="9d550-132">Пример использования этого элемента см. в [ \<> dataContractSerializer](datacontractserializer-element.md) .</span><span class="sxs-lookup"><span data-stu-id="9d550-132">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d550-133">При добавлении типа <xref:System.Object> как `<declaredType>` возникает <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="9d550-133">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="9d550-134">Это обусловлено тем, что тип <xref:System.Object> нельзя использовать как объявленный тип в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9d550-134">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d550-135">Пример</span><span class="sxs-lookup"><span data-stu-id="9d550-135">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9d550-136">См. также</span><span class="sxs-lookup"><span data-stu-id="9d550-136">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="9d550-137">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="9d550-137">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="9d550-138">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="9d550-138">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="9d550-139">\<Добавление > \<> declaredTypes</span><span class="sxs-lookup"><span data-stu-id="9d550-139">\<add> of \<declaredTypes></span></span>](add-of-declaredtypes-element.md)
