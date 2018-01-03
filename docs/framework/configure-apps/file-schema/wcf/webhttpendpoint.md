---
title: '&lt;webHttpEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc45511e0e7b4644704a834f0bc08d64ff3367f3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltwebhttpendpointgt"></a><span data-ttu-id="0482e-102">&lt;webHttpEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="0482e-102">&lt;webHttpEndpoint&gt;</span></span>
<span data-ttu-id="0482e-103">Этот элемент конфигурации определяет стандартную конечную точку с фиксированным [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) привязки, которая автоматически добавляет [ \<webHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) поведение.</span><span class="sxs-lookup"><span data-stu-id="0482e-103">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<webHttp>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) behavior.</span></span> <span data-ttu-id="0482e-104">Используйте эту конечную точку при написании службы REST.</span><span class="sxs-lookup"><span data-stu-id="0482e-104">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="0482e-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0482e-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="0482e-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="0482e-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0482e-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0482e-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint automaticFormatSelectionEnabled="String" 
                        defaultOutgoingResponseFormat="Xml/Json" 
                        helpEnabled="Boolean" 
                        webEndpointType="String"/>
    </webHttpEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0482e-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0482e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0482e-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0482e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0482e-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0482e-110">Attributes</span></span>  
  
|<span data-ttu-id="0482e-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0482e-111">Attribute</span></span>|<span data-ttu-id="0482e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0482e-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0482e-113">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="0482e-113">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="0482e-114">Логическое значение, указывающее, включен ли автоматический выбор формата.</span><span class="sxs-lookup"><span data-stu-id="0482e-114">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="0482e-115">Если автоматический выбор формата включен, инфраструктура выполняет синтаксический анализ заголовка `Accept` сообщения запроса и определяет наиболее подходящий формат ответа.</span><span class="sxs-lookup"><span data-stu-id="0482e-115">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="0482e-116">Если в заголовке `Accept` не указан подходящий формат ответа, инфраструктура использует тип `Content-Type` сообщения запроса или формат ответа, заданный для этой операции по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0482e-116">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="0482e-117">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="0482e-117">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="0482e-118">Атрибут, определяющий формат исходящего ответа по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0482e-118">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="0482e-119">Это атрибут типа <xref:System.ServiceModel.Web.WebMessageFormat>.</span><span class="sxs-lookup"><span data-stu-id="0482e-119">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="0482e-120">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="0482e-120">helpEnabled</span></span>|<span data-ttu-id="0482e-121">Логическое значение, указывающее, включена ли страница справки HTTP для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="0482e-121">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="0482e-122">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="0482e-122">webEndpointType</span></span>|<span data-ttu-id="0482e-123">Строка, указывающая тип конечной точки.</span><span class="sxs-lookup"><span data-stu-id="0482e-123">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0482e-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0482e-124">Child Elements</span></span>  
 <span data-ttu-id="0482e-125">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0482e-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0482e-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0482e-126">Parent Elements</span></span>  
  
|<span data-ttu-id="0482e-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="0482e-127">Element</span></span>|<span data-ttu-id="0482e-128">Описание:</span><span class="sxs-lookup"><span data-stu-id="0482e-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0482e-129">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="0482e-129">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="0482e-130">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="0482e-130">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0482e-131">См. также</span><span class="sxs-lookup"><span data-stu-id="0482e-131">See Also</span></span>  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>  
 <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
