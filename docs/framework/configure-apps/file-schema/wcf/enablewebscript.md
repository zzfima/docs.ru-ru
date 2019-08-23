---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 123f58ee3d77bf605db21fa0d9537b3196d56468
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919116"
---
# <a name="enablewebscript"></a><span data-ttu-id="a4577-101">\<Енаблевебскрипт ></span><span class="sxs-lookup"><span data-stu-id="a4577-101">\<enableWebScript></span></span>
<span data-ttu-id="a4577-102">Этот элемент включает поведение конечной точки, которое позволяет использовать службу с веб-страниц ASP.NET с поддержкой технологии AJAX.</span><span class="sxs-lookup"><span data-stu-id="a4577-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="a4577-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a4577-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a4577-104">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="a4577-104">\<behaviors></span></span>  
<span data-ttu-id="a4577-105">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a4577-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="a4577-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="a4577-106">\<behavior></span></span>  
<span data-ttu-id="a4577-107">\<Енаблевебскрипт ></span><span class="sxs-lookup"><span data-stu-id="a4577-107">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4577-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a4577-108">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4577-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a4577-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a4577-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a4577-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4577-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a4577-111">Attributes</span></span>  
 <span data-ttu-id="a4577-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="a4577-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a4577-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a4577-113">Child Elements</span></span>  
 <span data-ttu-id="a4577-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="a4577-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a4577-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a4577-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a4577-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="a4577-116">Element</span></span>|<span data-ttu-id="a4577-117">Описание</span><span class="sxs-lookup"><span data-stu-id="a4577-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4577-118">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="a4577-118">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="a4577-119">Задает набор поведений конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a4577-119">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4577-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="a4577-120">Remarks</span></span>  
 <span data-ttu-id="a4577-121">Это поведение следует использовать только в сочетании с [ \<привязкой WebHttpBinding >](webhttpbinding.md) Standard или с [ \<элементом привязки вебмессажеенкодинг >](webmessageencoding.md) .</span><span class="sxs-lookup"><span data-stu-id="a4577-121">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="a4577-122">Дополнительные сведения об этом поведении см. в разделе <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="a4577-122">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4577-123">См. также</span><span class="sxs-lookup"><span data-stu-id="a4577-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="a4577-124">Интеграция с AJAX и поддержка JSON</span><span class="sxs-lookup"><span data-stu-id="a4577-124">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="a4577-125">\<> http</span><span class="sxs-lookup"><span data-stu-id="a4577-125">\<webHttp></span></span>](webhttp.md)
