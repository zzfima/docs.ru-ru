---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 9c9bbb9ccc7879510ae3e2bee2fabd604fd52f65
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266654"
---
# <a name="enablewebscript"></a><span data-ttu-id="430f0-101">\<enableWebScript ></span><span class="sxs-lookup"><span data-stu-id="430f0-101">\<enableWebScript></span></span>
<span data-ttu-id="430f0-102">Этот элемент включает поведение конечной точки, которое позволяет использовать службу с веб-страниц ASP.NET с поддержкой технологии AJAX.</span><span class="sxs-lookup"><span data-stu-id="430f0-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="430f0-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="430f0-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="430f0-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="430f0-104">\<behaviors></span></span>  
<span data-ttu-id="430f0-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="430f0-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="430f0-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="430f0-106">\<behavior></span></span>  
<span data-ttu-id="430f0-107">\<enableWebScript ></span><span class="sxs-lookup"><span data-stu-id="430f0-107">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="430f0-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="430f0-108">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="430f0-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="430f0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="430f0-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="430f0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="430f0-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="430f0-111">Attributes</span></span>  
 <span data-ttu-id="430f0-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="430f0-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="430f0-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="430f0-113">Child Elements</span></span>  
 <span data-ttu-id="430f0-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="430f0-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="430f0-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="430f0-115">Parent Elements</span></span>  
  
|<span data-ttu-id="430f0-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="430f0-116">Element</span></span>|<span data-ttu-id="430f0-117">Описание</span><span class="sxs-lookup"><span data-stu-id="430f0-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="430f0-118">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="430f0-118">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="430f0-119">Задает набор поведений конечной точки.</span><span class="sxs-lookup"><span data-stu-id="430f0-119">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="430f0-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="430f0-120">Remarks</span></span>  
 <span data-ttu-id="430f0-121">Это поведение можно использовать только в сочетании со [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) стандартной привязки или [ \<webMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) элемента привязки.</span><span class="sxs-lookup"><span data-stu-id="430f0-121">This behavior should only be used in conjunction with either the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="430f0-122">Дополнительные сведения об этом поведении см. в разделе <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="430f0-122">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="430f0-123">См. также</span><span class="sxs-lookup"><span data-stu-id="430f0-123">See also</span></span>
- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="430f0-124">Интеграция с AJAX и поддержка JSON</span><span class="sxs-lookup"><span data-stu-id="430f0-124">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="430f0-125">\<webHttp ></span><span class="sxs-lookup"><span data-stu-id="430f0-125">\<webHttp></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
