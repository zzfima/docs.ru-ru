---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 20c0057c80b668df97379d0168bb7c005d9927ce
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400386"
---
# <a name="enablewebscript"></a><span data-ttu-id="1892d-101">\<Енаблевебскрипт ></span><span class="sxs-lookup"><span data-stu-id="1892d-101">\<enableWebScript></span></span>
<span data-ttu-id="1892d-102">Этот элемент включает поведение конечной точки, которое позволяет использовать службу с веб-страниц ASP.NET с поддержкой технологии AJAX.</span><span class="sxs-lookup"><span data-stu-id="1892d-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
<span data-ttu-id="1892d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1892d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1892d-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1892d-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1892d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1892d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="1892d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1892d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="1892d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1892d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="1892d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Енаблевебскрипт >**</span><span class="sxs-lookup"><span data-stu-id="1892d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<enableWebScript>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1892d-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1892d-109">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1892d-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1892d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1892d-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1892d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1892d-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1892d-112">Attributes</span></span>  
 <span data-ttu-id="1892d-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="1892d-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1892d-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1892d-114">Child Elements</span></span>  
 <span data-ttu-id="1892d-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="1892d-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1892d-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1892d-116">Parent Elements</span></span>  
  
|<span data-ttu-id="1892d-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="1892d-117">Element</span></span>|<span data-ttu-id="1892d-118">Описание</span><span class="sxs-lookup"><span data-stu-id="1892d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1892d-119">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="1892d-119">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="1892d-120">Задает набор поведений конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1892d-120">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1892d-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="1892d-121">Remarks</span></span>  
 <span data-ttu-id="1892d-122">Это поведение следует использовать только в сочетании с [ \<привязкой WebHttpBinding >](webhttpbinding.md) Standard или с [ \<элементом привязки вебмессажеенкодинг >](webmessageencoding.md) .</span><span class="sxs-lookup"><span data-stu-id="1892d-122">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="1892d-123">Дополнительные сведения об этом поведении см. в разделе <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="1892d-123">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1892d-124">См. также</span><span class="sxs-lookup"><span data-stu-id="1892d-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="1892d-125">Интеграция с AJAX и поддержка JSON</span><span class="sxs-lookup"><span data-stu-id="1892d-125">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="1892d-126">\<> http</span><span class="sxs-lookup"><span data-stu-id="1892d-126">\<webHttp></span></span>](webhttp.md)
