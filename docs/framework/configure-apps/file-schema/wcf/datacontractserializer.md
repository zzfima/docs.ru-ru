---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: e6524c18780c062c3b5b7dfc2509449cb208e270
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400435"
---
# <a name="datacontractserializer"></a><span data-ttu-id="87712-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="87712-102">dataContractSerializer</span></span>
<span data-ttu-id="87712-103">Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="87712-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
<span data-ttu-id="87712-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="87712-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="87712-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="87712-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="87712-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="87712-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="87712-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="87712-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="87712-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="87712-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="87712-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<dataContractSerializer >**</span><span class="sxs-lookup"><span data-stu-id="87712-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87712-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87712-110">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87712-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="87712-111">Attributes and Elements</span></span>  
 <span data-ttu-id="87712-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="87712-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87712-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="87712-113">Attributes</span></span>  
  
|<span data-ttu-id="87712-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="87712-114">Element</span></span>|<span data-ttu-id="87712-115">Описание</span><span class="sxs-lookup"><span data-stu-id="87712-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87712-116">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="87712-116">ignoreExtensionDataObject</span></span>|<span data-ttu-id="87712-117">Логическое значение, указывающее, должны ли пропускаться данные, предоставляемые конечной точкой, при их сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="87712-117">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="87712-118">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="87712-118">maxItemsInObjectGraph</span></span>|<span data-ttu-id="87712-119">Целое число, указывающее максимальное количество элементов для сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="87712-119">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87712-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="87712-120">Child Elements</span></span>  
 <span data-ttu-id="87712-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="87712-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="87712-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="87712-122">Parent Elements</span></span>  
  
|<span data-ttu-id="87712-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="87712-123">Element</span></span>|<span data-ttu-id="87712-124">Описание</span><span class="sxs-lookup"><span data-stu-id="87712-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87712-125">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="87712-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="87712-126">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="87712-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87712-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="87712-127">Remarks</span></span>  
 <span data-ttu-id="87712-128">Дополнительные сведения об известных типах см. в документации по <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="87712-128">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="87712-129">Элемент поведения `<dataContractSerializer>` (если он присутствует) должен всегда находиться в файле конфигурации перед элементом поведения `<enableWebScript>`.</span><span class="sxs-lookup"><span data-stu-id="87712-129">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="87712-130">В противном случае результирующее поведение является неопределенным.</span><span class="sxs-lookup"><span data-stu-id="87712-130">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87712-131">См. также</span><span class="sxs-lookup"><span data-stu-id="87712-131">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="87712-132">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="87712-132">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="87712-133">Передача данных и сериализация</span><span class="sxs-lookup"><span data-stu-id="87712-133">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
