---
title: '&lt;enableWebScript&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b7e637a744d24ed32be71d0ecf3f5d93144d32aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltenablewebscriptgt"></a><span data-ttu-id="be035-102">&lt;enableWebScript&gt;</span><span class="sxs-lookup"><span data-stu-id="be035-102">&lt;enableWebScript&gt;</span></span>
<span data-ttu-id="be035-103">Этот элемент включает поведение конечной точки, которое позволяет использовать службу с веб-страниц ASP.NET с поддержкой технологии AJAX.</span><span class="sxs-lookup"><span data-stu-id="be035-103">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="be035-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="be035-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="be035-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="be035-105">\<behaviors></span></span>  
<span data-ttu-id="be035-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="be035-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="be035-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="be035-107">\<behavior></span></span>  
<span data-ttu-id="be035-108">\<enableWebScript ></span><span class="sxs-lookup"><span data-stu-id="be035-108">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be035-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be035-109">Syntax</span></span>  
  
```xml  
<enableWebScript />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be035-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="be035-110">Attributes and Elements</span></span>  
 <span data-ttu-id="be035-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="be035-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be035-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="be035-112">Attributes</span></span>  
 <span data-ttu-id="be035-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="be035-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="be035-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="be035-114">Child Elements</span></span>  
 <span data-ttu-id="be035-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="be035-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="be035-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="be035-116">Parent Elements</span></span>  
  
|<span data-ttu-id="be035-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="be035-117">Element</span></span>|<span data-ttu-id="be035-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="be035-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="be035-119">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="be035-119">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="be035-120">Задает набор поведений конечной точки.</span><span class="sxs-lookup"><span data-stu-id="be035-120">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be035-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="be035-121">Remarks</span></span>  
 <span data-ttu-id="be035-122">Это поведение следует использовать только в сочетании с любой [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) стандартной привязки или [ \<webMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) элемента привязки.</span><span class="sxs-lookup"><span data-stu-id="be035-122">This behavior should only be used in conjunction with either the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="be035-123">Дополнительные сведения об этом поведении см. в разделе <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="be035-123">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be035-124">См. также</span><span class="sxs-lookup"><span data-stu-id="be035-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>  
 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>  
 [<span data-ttu-id="be035-125">Интеграция с AJAX и поддержка JSON</span><span class="sxs-lookup"><span data-stu-id="be035-125">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [<span data-ttu-id="be035-126">\<webHttp ></span><span class="sxs-lookup"><span data-stu-id="be035-126">\<webHttp></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
