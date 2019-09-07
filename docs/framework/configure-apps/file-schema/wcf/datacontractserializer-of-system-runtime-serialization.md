---
title: <dataContractSerializer>< System. Runtime. Serialization >
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: eb556f533af1f99049382e9a2e34465f88d563db
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398083"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="6af8d-102">\<dataContractSerializer > \<System. Runtime. Serialization ></span><span class="sxs-lookup"><span data-stu-id="6af8d-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>
<span data-ttu-id="6af8d-103">Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="6af8d-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
<span data-ttu-id="6af8d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6af8d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6af8d-105">&nbsp;&nbsp;[ **\<System. Runtime. Serialization >** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="6af8d-105">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="6af8d-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<dataContractSerializer >**</span><span class="sxs-lookup"><span data-stu-id="6af8d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6af8d-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6af8d-107">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer"
                       type="String" />
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6af8d-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6af8d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6af8d-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6af8d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6af8d-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6af8d-110">Attributes</span></span>  
  
|<span data-ttu-id="6af8d-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="6af8d-111">Element</span></span>|<span data-ttu-id="6af8d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="6af8d-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6af8d-113">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="6af8d-113">ignoreExtensionDataObject</span></span>|<span data-ttu-id="6af8d-114">Логическое значение, указывающее, пропускать ли данные, предоставленные конечной точкой при ее сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="6af8d-114">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="6af8d-115">Этот атрибут можно задать только в `<dataContractSerializer>` в элементе `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="6af8d-115">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="6af8d-116">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="6af8d-116">maxItemsInObjectGraph</span></span>|<span data-ttu-id="6af8d-117">Целое число, указывающее максимальное количество элементов для сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="6af8d-117">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="6af8d-118">Этот атрибут имеет значение 65 536.</span><span class="sxs-lookup"><span data-stu-id="6af8d-118">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6af8d-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6af8d-119">Child Elements</span></span>  
  
|<span data-ttu-id="6af8d-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="6af8d-120">Element</span></span>|<span data-ttu-id="6af8d-121">Описание</span><span class="sxs-lookup"><span data-stu-id="6af8d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6af8d-122">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="6af8d-122">\<declaredTypes></span></span>](declaredtypes.md)|<span data-ttu-id="6af8d-123">Содержит известные типы, которые <xref:System.Runtime.Serialization.DataContractSerializer> использует при десериализации.</span><span class="sxs-lookup"><span data-stu-id="6af8d-123">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="6af8d-124">Дополнительные сведения о контрактах данных и известных типах см. в статье о [известных типах контрактов данных](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="6af8d-124">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6af8d-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6af8d-125">Parent Elements</span></span>  
  
|<span data-ttu-id="6af8d-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="6af8d-126">Element</span></span>|<span data-ttu-id="6af8d-127">Описание</span><span class="sxs-lookup"><span data-stu-id="6af8d-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6af8d-128">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="6af8d-128">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)|<span data-ttu-id="6af8d-129">Представляет корневой элемент для раздела пространства имен <xref:System.Runtime.Serialization> и содержит элементы для установки параметров <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="6af8d-129">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6af8d-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="6af8d-130">Remarks</span></span>  
 <span data-ttu-id="6af8d-131">Дополнительные сведения об известных типах см. в <xref:System.Runtime.Serialization.DataContractSerializer> разделе и [известные типы контракта данных](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="6af8d-131">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6af8d-132">См. также</span><span class="sxs-lookup"><span data-stu-id="6af8d-132">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="6af8d-133">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="6af8d-133">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
