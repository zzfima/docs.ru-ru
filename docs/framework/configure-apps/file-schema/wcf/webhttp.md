---
title: '&lt;webHttp&gt;'
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 9ba54dc1744751efe4efad04f829cccce1244e0d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145683"
---
# <a name="ltwebhttpgt"></a><span data-ttu-id="31b3c-102">&lt;webHttp&gt;</span><span class="sxs-lookup"><span data-stu-id="31b3c-102">&lt;webHttp&gt;</span></span>
<span data-ttu-id="31b3c-103">Данный элемент задает <xref:System.ServiceModel.Description.WebHttpBehavior> на конечной точке в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="31b3c-103">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="31b3c-104">Это поведение, при использовании в сочетании с [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) стандартной привязки включает модель веб-программирования для службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="31b3c-104">This behavior, when used in conjunction with the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="31b3c-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="31b3c-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="31b3c-106">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="31b3c-106">\<behaviors></span></span>  
<span data-ttu-id="31b3c-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="31b3c-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="31b3c-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="31b3c-108">\<behavior></span></span>  
<span data-ttu-id="31b3c-109">\<webHttp ></span><span class="sxs-lookup"><span data-stu-id="31b3c-109">\<webHttp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31b3c-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="31b3c-110">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31b3c-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="31b3c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="31b3c-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="31b3c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31b3c-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="31b3c-113">Attributes</span></span>  
  
|<span data-ttu-id="31b3c-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="31b3c-114">Attribute</span></span>|<span data-ttu-id="31b3c-115">Описание</span><span class="sxs-lookup"><span data-stu-id="31b3c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="31b3c-116">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="31b3c-116">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="31b3c-117">Если это свойство имеет значение `true`, то инфраструктура WCF определяет лучший формат для использования.</span><span class="sxs-lookup"><span data-stu-id="31b3c-117">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="31b3c-118">Автоматический выбор формата отключен по умолчанию в целях обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="31b3c-118">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="31b3c-119">Автоматический выбор формата можно включить программно или через конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="31b3c-119">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="31b3c-120">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="31b3c-120">defaultBodyStyle</span></span>|<span data-ttu-id="31b3c-121">Задает стиль по умолчанию для текста возвращаемых сообщений.</span><span class="sxs-lookup"><span data-stu-id="31b3c-121">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="31b3c-122">Дополнительные сведения см. в разделе <xref:System.ServiceModel.Web.WebMessageBodyStyle> и [WCF Web HTTP форматирование](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="31b3c-122">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="31b3c-123">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="31b3c-123">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="31b3c-124">Определяет формат ответа по умолчанию для исходящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="31b3c-124">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="31b3c-125">Дополнительные сведения см. в разделе [WCF Web HTTP форматирование](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="31b3c-125">For more information, see [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="31b3c-126">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="31b3c-126">faultExceptionEnabled</span></span>|<span data-ttu-id="31b3c-127">Получает или задает флаг, указывающий, будет ли создаваться исключение FaultException при возникновении внутренней ошибки сервера (код состояния HTTP: 500).</span><span class="sxs-lookup"><span data-stu-id="31b3c-127">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="31b3c-128">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="31b3c-128">helpEnabled</span></span>|<span data-ttu-id="31b3c-129">Возвращает или задает значение, определяющее, будет ли включена страница справки.</span><span class="sxs-lookup"><span data-stu-id="31b3c-129">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="31b3c-130">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="31b3c-130">Child Elements</span></span>  
 <span data-ttu-id="31b3c-131">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="31b3c-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="31b3c-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="31b3c-132">Parent Elements</span></span>  
  
|<span data-ttu-id="31b3c-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="31b3c-133">Element</span></span>|<span data-ttu-id="31b3c-134">Описание</span><span class="sxs-lookup"><span data-stu-id="31b3c-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31b3c-135">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="31b3c-135">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="31b3c-136">Задает набор поведений конечной точки.</span><span class="sxs-lookup"><span data-stu-id="31b3c-136">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="31b3c-137">См. также</span><span class="sxs-lookup"><span data-stu-id="31b3c-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebHttpElement>  
 <xref:System.ServiceModel.Description.WebHttpBehavior>  
 [<span data-ttu-id="31b3c-138">Интеграция с AJAX и поддержка JSON</span><span class="sxs-lookup"><span data-stu-id="31b3c-138">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [<span data-ttu-id="31b3c-139">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="31b3c-139">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)
