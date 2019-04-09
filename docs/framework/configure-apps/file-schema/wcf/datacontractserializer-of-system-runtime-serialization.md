---
title: <dataContractSerializer> of <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: c81fdb040f2e0d6c9a3728d8ed3b917443ecb42e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115366"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="2d989-102">\<dataContractSerializer> of \<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="2d989-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>
<span data-ttu-id="2d989-103">Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="2d989-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="2d989-104">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="2d989-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="2d989-105">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="2d989-105">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d989-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2d989-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d989-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2d989-107">Attributes and Elements</span></span>  
 <span data-ttu-id="2d989-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2d989-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d989-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2d989-109">Attributes</span></span>  
  
|<span data-ttu-id="2d989-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="2d989-110">Element</span></span>|<span data-ttu-id="2d989-111">Описание</span><span class="sxs-lookup"><span data-stu-id="2d989-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2d989-112">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="2d989-112">ignoreExtensionDataObject</span></span>|<span data-ttu-id="2d989-113">Логическое значение, указывающее, пропускать ли данные, предоставленные конечной точкой при ее сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="2d989-113">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="2d989-114">Этот атрибут можно задать только в `<dataContractSerializer>` в элементе `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="2d989-114">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="2d989-115">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="2d989-115">maxItemsInObjectGraph</span></span>|<span data-ttu-id="2d989-116">Целое число, указывающее максимальное количество элементов для сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="2d989-116">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="2d989-117">Этот атрибут имеет значение 65 536.</span><span class="sxs-lookup"><span data-stu-id="2d989-117">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d989-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2d989-118">Child Elements</span></span>  
  
|<span data-ttu-id="2d989-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="2d989-119">Element</span></span>|<span data-ttu-id="2d989-120">Описание</span><span class="sxs-lookup"><span data-stu-id="2d989-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d989-121">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="2d989-121">\<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|<span data-ttu-id="2d989-122">Содержит известные типы, которые <xref:System.Runtime.Serialization.DataContractSerializer> использует при десериализации.</span><span class="sxs-lookup"><span data-stu-id="2d989-122">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="2d989-123">Дополнительные сведения о контрактах данных и известных типов, см. в разделе [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="2d989-123">For more information about data contracts and known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2d989-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2d989-124">Parent Elements</span></span>  
  
|<span data-ttu-id="2d989-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="2d989-125">Element</span></span>|<span data-ttu-id="2d989-126">Описание</span><span class="sxs-lookup"><span data-stu-id="2d989-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d989-127">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="2d989-127">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="2d989-128">Представляет корневой элемент для раздела пространства имен <xref:System.Runtime.Serialization> и содержит элементы для установки параметров <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="2d989-128">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d989-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="2d989-129">Remarks</span></span>  
 <span data-ttu-id="2d989-130">Дополнительные сведения об известных типах см. в разделе <xref:System.Runtime.Serialization.DataContractSerializer> и [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="2d989-130">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d989-131">См. также</span><span class="sxs-lookup"><span data-stu-id="2d989-131">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="2d989-132">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="2d989-132">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
