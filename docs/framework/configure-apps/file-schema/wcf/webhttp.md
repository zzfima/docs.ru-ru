---
title: '&lt;webHttp&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6b488d4e4884f92b107b2b6be71827a2f8b4cdbf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltwebhttpgt"></a><span data-ttu-id="6f1b6-102">&lt;webHttp&gt;</span><span class="sxs-lookup"><span data-stu-id="6f1b6-102">&lt;webHttp&gt;</span></span>
<span data-ttu-id="6f1b6-103">Данный элемент задает <xref:System.ServiceModel.Description.WebHttpBehavior> на конечной точке в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6f1b6-103">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="6f1b6-104">Такое поведение, при использовании в сочетании с [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) Стандартная привязка включает модель веб-программирования для [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] службы.</span><span class="sxs-lookup"><span data-stu-id="6f1b6-104">This behavior, when used in conjunction with the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, enables the Web programming model for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service.</span></span>  
  
 <span data-ttu-id="6f1b6-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6f1b6-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="6f1b6-106">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="6f1b6-106">\<behaviors></span></span>  
<span data-ttu-id="6f1b6-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="6f1b6-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="6f1b6-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="6f1b6-108">\<behavior></span></span>  
<span data-ttu-id="6f1b6-109">\<webHttp ></span><span class="sxs-lookup"><span data-stu-id="6f1b6-109">\<webHttp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f1b6-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f1b6-110">Syntax</span></span>  
  
```xml  
<webHttp />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f1b6-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6f1b6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6f1b6-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6f1b6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f1b6-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6f1b6-113">Attributes</span></span>  
  
|<span data-ttu-id="6f1b6-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6f1b6-114">Attribute</span></span>|<span data-ttu-id="6f1b6-115">Описание</span><span class="sxs-lookup"><span data-stu-id="6f1b6-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6f1b6-116">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="6f1b6-116">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="6f1b6-117">Если это свойство имеет значение `true`, то инфраструктура WCF определяет лучший формат для использования.</span><span class="sxs-lookup"><span data-stu-id="6f1b6-117">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="6f1b6-118">Автоматический выбор формата отключен по умолчанию в целях обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="6f1b6-118">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="6f1b6-119">Автоматический выбор формата можно включить программно или через конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="6f1b6-119">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="6f1b6-120">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="6f1b6-120">defaultBodyStyle</span></span>|<span data-ttu-id="6f1b6-121">Задает стиль по умолчанию для текста возвращаемых сообщений.</span><span class="sxs-lookup"><span data-stu-id="6f1b6-121">Specifies the default body style of returned messages.</span></span> [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)]<span data-ttu-id="6f1b6-122"><xref:System.ServiceModel.Web.WebMessageBodyStyle> и [WCF Web HTTP форматирование](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="6f1b6-122"> <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="6f1b6-123">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="6f1b6-123">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="6f1b6-124">Определяет формат ответа по умолчанию для исходящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="6f1b6-124">Specifies the default outgoing response format for messages.</span></span> [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)]<span data-ttu-id="6f1b6-125">[WCF Web HTTP форматирование](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="6f1b6-125"> [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="6f1b6-126">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="6f1b6-126">faultExceptionEnabled</span></span>|<span data-ttu-id="6f1b6-127">Возвращает или задает флаг, указывающий, будет ли создаваться исключение FaultException при возникновении внутренней ошибки сервера (код состояния HTTP: 500).</span><span class="sxs-lookup"><span data-stu-id="6f1b6-127">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="6f1b6-128">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="6f1b6-128">helpEnabled</span></span>|<span data-ttu-id="6f1b6-129">Возвращает или задает значение, определяющее, будет ли включена страница справки.</span><span class="sxs-lookup"><span data-stu-id="6f1b6-129">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f1b6-130">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6f1b6-130">Child Elements</span></span>  
 <span data-ttu-id="6f1b6-131">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6f1b6-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6f1b6-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6f1b6-132">Parent Elements</span></span>  
  
|<span data-ttu-id="6f1b6-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="6f1b6-133">Element</span></span>|<span data-ttu-id="6f1b6-134">Описание:</span><span class="sxs-lookup"><span data-stu-id="6f1b6-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6f1b6-135">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="6f1b6-135">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="6f1b6-136">Задает набор поведений конечной точки.</span><span class="sxs-lookup"><span data-stu-id="6f1b6-136">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6f1b6-137">См. также</span><span class="sxs-lookup"><span data-stu-id="6f1b6-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebHttpElement>  
 <xref:System.ServiceModel.Description.WebHttpBehavior>  
 [<span data-ttu-id="6f1b6-138">Интеграция с AJAX и поддержка JSON</span><span class="sxs-lookup"><span data-stu-id="6f1b6-138">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [<span data-ttu-id="6f1b6-139">\<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="6f1b6-139">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)
