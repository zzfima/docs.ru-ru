---
title: dataContractSerializer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 66c8686ae4397b9d4bf18fbf7a79aa2408db101d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="datacontractserializer"></a><span data-ttu-id="756cf-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="756cf-102">dataContractSerializer</span></span>
<span data-ttu-id="756cf-103">Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="756cf-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="756cf-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="756cf-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="756cf-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="756cf-105">\<behaviors></span></span>  
<span data-ttu-id="756cf-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="756cf-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="756cf-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="756cf-107">\<behavior></span></span>  
<span data-ttu-id="756cf-108">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="756cf-108">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="756cf-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="756cf-109">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
      maxItemsInObjectGraph="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="756cf-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="756cf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="756cf-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="756cf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="756cf-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="756cf-112">Attributes</span></span>  
  
|<span data-ttu-id="756cf-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="756cf-113">Element</span></span>|<span data-ttu-id="756cf-114">Описание</span><span class="sxs-lookup"><span data-stu-id="756cf-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="756cf-115">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="756cf-115">ignoreExtensionDataObject</span></span>|<span data-ttu-id="756cf-116">Логическое значение, указывающее, должны ли пропускаться данные, предоставляемые конечной точкой, при их сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="756cf-116">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="756cf-117">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="756cf-117">maxItemsInObjectGraph</span></span>|<span data-ttu-id="756cf-118">Целое число, указывающее максимальное количество элементов для сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="756cf-118">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="756cf-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="756cf-119">Child Elements</span></span>  
 <span data-ttu-id="756cf-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="756cf-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="756cf-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="756cf-121">Parent Elements</span></span>  
  
|<span data-ttu-id="756cf-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="756cf-122">Element</span></span>|<span data-ttu-id="756cf-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="756cf-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="756cf-124">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="756cf-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="756cf-125">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="756cf-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="756cf-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="756cf-126">Remarks</span></span>  
 <span data-ttu-id="756cf-127">Дополнительные сведения об известных типах см. в документации по <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="756cf-127">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="756cf-128">Элемент поведения `<dataContractSerializer>` (если он присутствует) должен всегда находиться в файле конфигурации перед элементом поведения `<enableWebScript>`.</span><span class="sxs-lookup"><span data-stu-id="756cf-128">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="756cf-129">В противном случае результирующее поведение является неопределенным.</span><span class="sxs-lookup"><span data-stu-id="756cf-129">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="756cf-130">См. также</span><span class="sxs-lookup"><span data-stu-id="756cf-130">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [<span data-ttu-id="756cf-131">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="756cf-131">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="756cf-132">Передача данных и сериализация</span><span class="sxs-lookup"><span data-stu-id="756cf-132">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
