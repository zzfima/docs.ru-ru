---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 00644d248e6fb85d7cf712620e6ac74405e6b0c3
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399166"
---
# <a name="webhttp"></a><span data-ttu-id="93040-101">\<> http</span><span class="sxs-lookup"><span data-stu-id="93040-101">\<webHttp></span></span>
<span data-ttu-id="93040-102">Данный элемент задает <xref:System.ServiceModel.Description.WebHttpBehavior> на конечной точке в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="93040-102">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="93040-103">Это поведение при использовании в сочетании с [ \<привязкой WebHttpBinding >](webhttpbinding.md) Standard включает модель веб-программирования для службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="93040-103">This behavior, when used in conjunction with the [\<webHttpBinding>](webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
<span data-ttu-id="93040-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="93040-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="93040-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="93040-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="93040-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="93040-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="93040-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="93040-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="93040-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="93040-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="93040-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> http**</span><span class="sxs-lookup"><span data-stu-id="93040-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttp>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93040-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93040-110">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93040-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="93040-111">Attributes and Elements</span></span>  
 <span data-ttu-id="93040-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="93040-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93040-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="93040-113">Attributes</span></span>  
  
|<span data-ttu-id="93040-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="93040-114">Attribute</span></span>|<span data-ttu-id="93040-115">Описание</span><span class="sxs-lookup"><span data-stu-id="93040-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="93040-116">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="93040-116">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="93040-117">Если это свойство имеет значение `true`, то инфраструктура WCF определяет лучший формат для использования.</span><span class="sxs-lookup"><span data-stu-id="93040-117">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="93040-118">Автоматический выбор формата отключен по умолчанию в целях обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="93040-118">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="93040-119">Автоматический выбор формата можно включить программно или через конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="93040-119">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="93040-120">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="93040-120">defaultBodyStyle</span></span>|<span data-ttu-id="93040-121">Задает стиль по умолчанию для текста возвращаемых сообщений.</span><span class="sxs-lookup"><span data-stu-id="93040-121">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="93040-122">Дополнительные сведения см. в <xref:System.ServiceModel.Web.WebMessageBodyStyle> разделе и [веб-форматирование WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="93040-122">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="93040-123">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="93040-123">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="93040-124">Определяет формат ответа по умолчанию для исходящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="93040-124">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="93040-125">Дополнительные сведения см. в разделе [веб-форматирование WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="93040-125">For more information, see [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="93040-126">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="93040-126">faultExceptionEnabled</span></span>|<span data-ttu-id="93040-127">Получает или задает флаг, указывающий, будет ли создаваться исключение FaultException при возникновении внутренней ошибки сервера (код состояния HTTP: 500).</span><span class="sxs-lookup"><span data-stu-id="93040-127">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="93040-128">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="93040-128">helpEnabled</span></span>|<span data-ttu-id="93040-129">Возвращает или задает значение, определяющее, будет ли включена страница справки.</span><span class="sxs-lookup"><span data-stu-id="93040-129">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93040-130">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="93040-130">Child Elements</span></span>  
 <span data-ttu-id="93040-131">Нет.</span><span class="sxs-lookup"><span data-stu-id="93040-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93040-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="93040-132">Parent Elements</span></span>  
  
|<span data-ttu-id="93040-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="93040-133">Element</span></span>|<span data-ttu-id="93040-134">Описание</span><span class="sxs-lookup"><span data-stu-id="93040-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93040-135">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="93040-135">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="93040-136">Задает набор поведений конечной точки.</span><span class="sxs-lookup"><span data-stu-id="93040-136">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="93040-137">См. также</span><span class="sxs-lookup"><span data-stu-id="93040-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="93040-138">Интеграция с AJAX и поддержка JSON</span><span class="sxs-lookup"><span data-stu-id="93040-138">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="93040-139">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="93040-139">\<webHttpBinding></span></span>](webhttpbinding.md)
