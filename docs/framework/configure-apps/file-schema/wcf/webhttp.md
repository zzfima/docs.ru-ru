---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 366def5d0f4cc82b0ff0a5127701b0b5a6adb6a0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940500"
---
# <a name="webhttp"></a><span data-ttu-id="c9cdd-101">\<> http</span><span class="sxs-lookup"><span data-stu-id="c9cdd-101">\<webHttp></span></span>
<span data-ttu-id="c9cdd-102">Данный элемент задает <xref:System.ServiceModel.Description.WebHttpBehavior> на конечной точке в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c9cdd-102">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="c9cdd-103">Это поведение при использовании в сочетании с [ \<привязкой WebHttpBinding >](webhttpbinding.md) Standard включает модель веб-программирования для службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="c9cdd-103">This behavior, when used in conjunction with the [\<webHttpBinding>](webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="c9cdd-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c9cdd-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c9cdd-105">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="c9cdd-105">\<behaviors></span></span>  
<span data-ttu-id="c9cdd-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c9cdd-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="c9cdd-107">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="c9cdd-107">\<behavior></span></span>  
<span data-ttu-id="c9cdd-108">\<> http</span><span class="sxs-lookup"><span data-stu-id="c9cdd-108">\<webHttp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9cdd-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9cdd-109">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9cdd-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c9cdd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c9cdd-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c9cdd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9cdd-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c9cdd-112">Attributes</span></span>  
  
|<span data-ttu-id="c9cdd-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c9cdd-113">Attribute</span></span>|<span data-ttu-id="c9cdd-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c9cdd-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c9cdd-115">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="c9cdd-115">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="c9cdd-116">Если это свойство имеет значение `true`, то инфраструктура WCF определяет лучший формат для использования.</span><span class="sxs-lookup"><span data-stu-id="c9cdd-116">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="c9cdd-117">Автоматический выбор формата отключен по умолчанию в целях обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="c9cdd-117">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="c9cdd-118">Автоматический выбор формата можно включить программно или через конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="c9cdd-118">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="c9cdd-119">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="c9cdd-119">defaultBodyStyle</span></span>|<span data-ttu-id="c9cdd-120">Задает стиль по умолчанию для текста возвращаемых сообщений.</span><span class="sxs-lookup"><span data-stu-id="c9cdd-120">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="c9cdd-121">Дополнительные сведения см. в <xref:System.ServiceModel.Web.WebMessageBodyStyle> разделе и [веб-форматирование WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="c9cdd-121">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="c9cdd-122">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="c9cdd-122">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="c9cdd-123">Определяет формат ответа по умолчанию для исходящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="c9cdd-123">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="c9cdd-124">Дополнительные сведения см. в разделе [веб-форматирование WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="c9cdd-124">For more information, see [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="c9cdd-125">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="c9cdd-125">faultExceptionEnabled</span></span>|<span data-ttu-id="c9cdd-126">Получает или задает флаг, указывающий, будет ли создаваться исключение FaultException при возникновении внутренней ошибки сервера (код состояния HTTP: 500).</span><span class="sxs-lookup"><span data-stu-id="c9cdd-126">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="c9cdd-127">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="c9cdd-127">helpEnabled</span></span>|<span data-ttu-id="c9cdd-128">Возвращает или задает значение, определяющее, будет ли включена страница справки.</span><span class="sxs-lookup"><span data-stu-id="c9cdd-128">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c9cdd-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c9cdd-129">Child Elements</span></span>  
 <span data-ttu-id="c9cdd-130">Нет.</span><span class="sxs-lookup"><span data-stu-id="c9cdd-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c9cdd-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c9cdd-131">Parent Elements</span></span>  
  
|<span data-ttu-id="c9cdd-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="c9cdd-132">Element</span></span>|<span data-ttu-id="c9cdd-133">Описание</span><span class="sxs-lookup"><span data-stu-id="c9cdd-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9cdd-134">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="c9cdd-134">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="c9cdd-135">Задает набор поведений конечной точки.</span><span class="sxs-lookup"><span data-stu-id="c9cdd-135">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c9cdd-136">См. также</span><span class="sxs-lookup"><span data-stu-id="c9cdd-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="c9cdd-137">Интеграция с AJAX и поддержка JSON</span><span class="sxs-lookup"><span data-stu-id="c9cdd-137">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="c9cdd-138">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="c9cdd-138">\<webHttpBinding></span></span>](webhttpbinding.md)
