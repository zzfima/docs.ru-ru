---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 8814a48df8933cf08db78e397c24d42f2da26026
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919236"
---
# <a name="datacontractserializer"></a><span data-ttu-id="3cf4e-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="3cf4e-102">dataContractSerializer</span></span>
<span data-ttu-id="3cf4e-103">Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="3cf4e-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="3cf4e-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3cf4e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3cf4e-105">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="3cf4e-105">\<behaviors></span></span>  
<span data-ttu-id="3cf4e-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3cf4e-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="3cf4e-107">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="3cf4e-107">\<behavior></span></span>  
<span data-ttu-id="3cf4e-108">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="3cf4e-108">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cf4e-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3cf4e-109">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cf4e-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3cf4e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3cf4e-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3cf4e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cf4e-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3cf4e-112">Attributes</span></span>  
  
|<span data-ttu-id="3cf4e-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="3cf4e-113">Element</span></span>|<span data-ttu-id="3cf4e-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3cf4e-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3cf4e-115">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="3cf4e-115">ignoreExtensionDataObject</span></span>|<span data-ttu-id="3cf4e-116">Логическое значение, указывающее, должны ли пропускаться данные, предоставляемые конечной точкой, при их сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="3cf4e-116">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="3cf4e-117">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="3cf4e-117">maxItemsInObjectGraph</span></span>|<span data-ttu-id="3cf4e-118">Целое число, указывающее максимальное количество элементов для сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="3cf4e-118">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3cf4e-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3cf4e-119">Child Elements</span></span>  
 <span data-ttu-id="3cf4e-120">Нет.</span><span class="sxs-lookup"><span data-stu-id="3cf4e-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3cf4e-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3cf4e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3cf4e-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="3cf4e-122">Element</span></span>|<span data-ttu-id="3cf4e-123">Описание</span><span class="sxs-lookup"><span data-stu-id="3cf4e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3cf4e-124">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="3cf4e-124">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="3cf4e-125">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3cf4e-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cf4e-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="3cf4e-126">Remarks</span></span>  
 <span data-ttu-id="3cf4e-127">Дополнительные сведения об известных типах см. в документации по <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="3cf4e-127">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="3cf4e-128">Элемент поведения `<dataContractSerializer>` (если он присутствует) должен всегда находиться в файле конфигурации перед элементом поведения `<enableWebScript>`.</span><span class="sxs-lookup"><span data-stu-id="3cf4e-128">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="3cf4e-129">В противном случае результирующее поведение является неопределенным.</span><span class="sxs-lookup"><span data-stu-id="3cf4e-129">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cf4e-130">См. также</span><span class="sxs-lookup"><span data-stu-id="3cf4e-130">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="3cf4e-131">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="3cf4e-131">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="3cf4e-132">Передача данных и сериализация</span><span class="sxs-lookup"><span data-stu-id="3cf4e-132">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
