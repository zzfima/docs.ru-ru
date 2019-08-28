---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 7952e6cc4d2fe7eaa77e297a650f7ffbd7aec785
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040933"
---
# <a name="datacontractserializer"></a><span data-ttu-id="3d433-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="3d433-102">dataContractSerializer</span></span>
<span data-ttu-id="3d433-103">Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="3d433-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="3d433-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3d433-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3d433-105">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="3d433-105">\<behaviors></span></span>  
<span data-ttu-id="3d433-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3d433-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="3d433-107">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="3d433-107">\<behavior></span></span>  
<span data-ttu-id="3d433-108">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="3d433-108">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d433-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d433-109">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d433-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3d433-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3d433-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3d433-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d433-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3d433-112">Attributes</span></span>  
  
|<span data-ttu-id="3d433-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="3d433-113">Element</span></span>|<span data-ttu-id="3d433-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3d433-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3d433-115">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="3d433-115">ignoreExtensionDataObject</span></span>|<span data-ttu-id="3d433-116">Логическое значение, указывающее, должны ли пропускаться данные, предоставляемые конечной точкой, при их сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="3d433-116">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="3d433-117">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="3d433-117">maxItemsInObjectGraph</span></span>|<span data-ttu-id="3d433-118">Целое число, указывающее максимальное количество элементов для сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="3d433-118">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3d433-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3d433-119">Child Elements</span></span>  
 <span data-ttu-id="3d433-120">Нет.</span><span class="sxs-lookup"><span data-stu-id="3d433-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3d433-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3d433-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3d433-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="3d433-122">Element</span></span>|<span data-ttu-id="3d433-123">Описание</span><span class="sxs-lookup"><span data-stu-id="3d433-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d433-124">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="3d433-124">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="3d433-125">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3d433-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d433-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="3d433-126">Remarks</span></span>  
 <span data-ttu-id="3d433-127">Дополнительные сведения об известных типах см. в документации по <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="3d433-127">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="3d433-128">Элемент поведения `<dataContractSerializer>` (если он присутствует) должен всегда находиться в файле конфигурации перед элементом поведения `<enableWebScript>`.</span><span class="sxs-lookup"><span data-stu-id="3d433-128">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="3d433-129">В противном случае результирующее поведение является неопределенным.</span><span class="sxs-lookup"><span data-stu-id="3d433-129">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d433-130">См. также</span><span class="sxs-lookup"><span data-stu-id="3d433-130">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="3d433-131">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="3d433-131">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="3d433-132">Передача данных и сериализация</span><span class="sxs-lookup"><span data-stu-id="3d433-132">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
