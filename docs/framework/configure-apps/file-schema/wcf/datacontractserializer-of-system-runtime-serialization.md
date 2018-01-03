---
title: "&lt;dataContractSerializer&gt; для &lt;system.runtime.serialization&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 836d00cb0c3de36e8fd918babb605cf629239357
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltdatacontractserializergt-of-ltsystemruntimeserializationgt"></a><span data-ttu-id="b4148-102">&lt;dataContractSerializer&gt; для &lt;system.runtime.serialization&gt;</span><span class="sxs-lookup"><span data-stu-id="b4148-102">&lt;dataContractSerializer&gt; of &lt;system.runtime.serialization&gt;</span></span>
<span data-ttu-id="b4148-103">Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b4148-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="b4148-104">\<System.Runtime.Serialization ></span><span class="sxs-lookup"><span data-stu-id="b4148-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="b4148-105">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="b4148-105">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4148-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4148-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4148-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b4148-107">Attributes and Elements</span></span>  
 <span data-ttu-id="b4148-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b4148-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4148-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b4148-109">Attributes</span></span>  
  
|<span data-ttu-id="b4148-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="b4148-110">Element</span></span>|<span data-ttu-id="b4148-111">Описание</span><span class="sxs-lookup"><span data-stu-id="b4148-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b4148-112">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="b4148-112">ignoreExtensionDataObject</span></span>|<span data-ttu-id="b4148-113">Логическое значение, указывающее, пропускать ли данные, предоставленные конечной точкой при ее сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="b4148-113">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="b4148-114">Этот атрибут можно задать только в `<dataContractSerializer>` в элементе `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="b4148-114">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="b4148-115">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="b4148-115">maxItemsInObjectGraph</span></span>|<span data-ttu-id="b4148-116">Целое число, указывающее максимальное количество элементов для сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="b4148-116">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="b4148-117">Этот атрибут имеет значение 65 536.</span><span class="sxs-lookup"><span data-stu-id="b4148-117">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4148-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b4148-118">Child Elements</span></span>  
  
|<span data-ttu-id="b4148-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="b4148-119">Element</span></span>|<span data-ttu-id="b4148-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="b4148-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4148-121">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="b4148-121">\<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|<span data-ttu-id="b4148-122">Содержит известные типы, которые <xref:System.Runtime.Serialization.DataContractSerializer> использует при десериализации.</span><span class="sxs-lookup"><span data-stu-id="b4148-122">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="b4148-123">Дополнительные сведения о контрактах данных и известных типах см. в разделе [известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="b4148-123">For more information about data contracts and known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b4148-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b4148-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b4148-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="b4148-125">Element</span></span>|<span data-ttu-id="b4148-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="b4148-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4148-127">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="b4148-127">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="b4148-128">Представляет корневой элемент для раздела пространства имен <xref:System.Runtime.Serialization> и содержит элементы для установки параметров <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b4148-128">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4148-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="b4148-129">Remarks</span></span>  
 <span data-ttu-id="b4148-130">Дополнительные сведения об известных типах см. в разделе <xref:System.Runtime.Serialization.DataContractSerializer> и [известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="b4148-130">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4148-131">См. также</span><span class="sxs-lookup"><span data-stu-id="b4148-131">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 [<span data-ttu-id="b4148-132">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="b4148-132">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
