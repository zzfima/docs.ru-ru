---
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 6fb31fca6ac38f6cb92ef087cc277a4d5066521c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182459"
---
# <a name="webhttpendpoint"></a><span data-ttu-id="ada38-101">\<webHttpEndpoint></span><span class="sxs-lookup"><span data-stu-id="ada38-101">\<webHttpEndpoint></span></span>
<span data-ttu-id="ada38-102">Этот элемент конфигурации определяет стандартную конечную точку с фиксированным [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) привязка, которая автоматически добавляет [ \<webHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) поведение.</span><span class="sxs-lookup"><span data-stu-id="ada38-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<webHttp>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) behavior.</span></span> <span data-ttu-id="ada38-103">Используйте эту конечную точку при написании службы REST.</span><span class="sxs-lookup"><span data-stu-id="ada38-103">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="ada38-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ada38-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ada38-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="ada38-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ada38-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ada38-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint automaticFormatSelectionEnabled="String"
                        defaultOutgoingResponseFormat="Xml/Json"
                        helpEnabled="Boolean"
                        webEndpointType="String" />
    </webHttpEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ada38-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ada38-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ada38-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ada38-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ada38-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ada38-109">Attributes</span></span>  
  
|<span data-ttu-id="ada38-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ada38-110">Attribute</span></span>|<span data-ttu-id="ada38-111">Описание</span><span class="sxs-lookup"><span data-stu-id="ada38-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ada38-112">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="ada38-112">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="ada38-113">Логическое значение, указывающее, включен ли автоматический выбор формата.</span><span class="sxs-lookup"><span data-stu-id="ada38-113">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="ada38-114">Если автоматический выбор формата включен, инфраструктура выполняет синтаксический анализ заголовка `Accept` сообщения запроса и определяет наиболее подходящий формат ответа.</span><span class="sxs-lookup"><span data-stu-id="ada38-114">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="ada38-115">Если в заголовке `Accept` не указан подходящий формат ответа, инфраструктура использует тип `Content-Type` сообщения запроса или формат ответа, заданный для этой операции по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ada38-115">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="ada38-116">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="ada38-116">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="ada38-117">Атрибут, определяющий формат исходящего ответа по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ada38-117">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="ada38-118">Это атрибут типа <xref:System.ServiceModel.Web.WebMessageFormat>.</span><span class="sxs-lookup"><span data-stu-id="ada38-118">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="ada38-119">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="ada38-119">helpEnabled</span></span>|<span data-ttu-id="ada38-120">Логическое значение, указывающее, включена ли страница справки HTTP для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ada38-120">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="ada38-121">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="ada38-121">webEndpointType</span></span>|<span data-ttu-id="ada38-122">Строка, указывающая тип конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ada38-122">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ada38-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ada38-123">Child Elements</span></span>  
 <span data-ttu-id="ada38-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ada38-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ada38-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ada38-125">Parent Elements</span></span>  
  
|<span data-ttu-id="ada38-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="ada38-126">Element</span></span>|<span data-ttu-id="ada38-127">Описание</span><span class="sxs-lookup"><span data-stu-id="ada38-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ada38-128">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="ada38-128">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="ada38-129">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="ada38-129">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ada38-130">См. также</span><span class="sxs-lookup"><span data-stu-id="ada38-130">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
