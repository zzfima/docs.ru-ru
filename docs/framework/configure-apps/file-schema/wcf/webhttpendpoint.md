---
title: '&lt;webHttpEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 46691a36b62898583132b5668b06de5659926d66
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltwebhttpendpointgt"></a><span data-ttu-id="5b7d8-102">&lt;webHttpEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="5b7d8-102">&lt;webHttpEndpoint&gt;</span></span>
<span data-ttu-id="5b7d8-103">Этот элемент конфигурации определяет стандартную конечную точку с фиксированным [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) привязки, которая автоматически добавляет [ \<webHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) поведение.</span><span class="sxs-lookup"><span data-stu-id="5b7d8-103">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<webHttp>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) behavior.</span></span> <span data-ttu-id="5b7d8-104">Используйте эту конечную точку при написании службы REST.</span><span class="sxs-lookup"><span data-stu-id="5b7d8-104">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="5b7d8-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5b7d8-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="5b7d8-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="5b7d8-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b7d8-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5b7d8-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b7d8-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5b7d8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5b7d8-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5b7d8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b7d8-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5b7d8-110">Attributes</span></span>  
  
|<span data-ttu-id="5b7d8-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5b7d8-111">Attribute</span></span>|<span data-ttu-id="5b7d8-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5b7d8-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5b7d8-113">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="5b7d8-113">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="5b7d8-114">Логическое значение, указывающее, включен ли автоматический выбор формата.</span><span class="sxs-lookup"><span data-stu-id="5b7d8-114">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="5b7d8-115">Если автоматический выбор формата включен, инфраструктура выполняет синтаксический анализ заголовка `Accept` сообщения запроса и определяет наиболее подходящий формат ответа.</span><span class="sxs-lookup"><span data-stu-id="5b7d8-115">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="5b7d8-116">Если в заголовке `Accept` не указан подходящий формат ответа, инфраструктура использует тип `Content-Type` сообщения запроса или формат ответа, заданный для этой операции по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5b7d8-116">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="5b7d8-117">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="5b7d8-117">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="5b7d8-118">Атрибут, определяющий формат исходящего ответа по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5b7d8-118">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="5b7d8-119">Это атрибут типа <xref:System.ServiceModel.Web.WebMessageFormat>.</span><span class="sxs-lookup"><span data-stu-id="5b7d8-119">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="5b7d8-120">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="5b7d8-120">helpEnabled</span></span>|<span data-ttu-id="5b7d8-121">Логическое значение, указывающее, включена ли страница справки HTTP для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5b7d8-121">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="5b7d8-122">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="5b7d8-122">webEndpointType</span></span>|<span data-ttu-id="5b7d8-123">Строка, указывающая тип конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5b7d8-123">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5b7d8-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5b7d8-124">Child Elements</span></span>  
 <span data-ttu-id="5b7d8-125">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5b7d8-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5b7d8-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5b7d8-126">Parent Elements</span></span>  
  
|<span data-ttu-id="5b7d8-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="5b7d8-127">Element</span></span>|<span data-ttu-id="5b7d8-128">Описание</span><span class="sxs-lookup"><span data-stu-id="5b7d8-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b7d8-129">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="5b7d8-129">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="5b7d8-130">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="5b7d8-130">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5b7d8-131">См. также</span><span class="sxs-lookup"><span data-stu-id="5b7d8-131">See Also</span></span>  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>  
 <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
