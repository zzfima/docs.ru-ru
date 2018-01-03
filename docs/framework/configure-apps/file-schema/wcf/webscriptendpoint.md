---
title: '&lt;webScriptEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 855a0fc0727bf0559b922317d439f7550f18d9ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltwebscriptendpointgt"></a><span data-ttu-id="66332-102">&lt;webScriptEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="66332-102">&lt;webScriptEndpoint&gt;</span></span>
<span data-ttu-id="66332-103">Этот элемент конфигурации определяет стандартную конечную точку с фиксированным [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) привязки, которая автоматически добавляет [ \<enableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) поведение.</span><span class="sxs-lookup"><span data-stu-id="66332-103">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior.</span></span> <span data-ttu-id="66332-104">Используйте эту конечную точку при написании службы, вызываемой из приложения ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="66332-104">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="66332-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="66332-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="66332-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="66332-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66332-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66332-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String"/>
    </webScriptEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66332-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="66332-108">Attributes and Elements</span></span>  
 <span data-ttu-id="66332-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="66332-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66332-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="66332-110">Attributes</span></span>  
  
|<span data-ttu-id="66332-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="66332-111">Attribute</span></span>|<span data-ttu-id="66332-112">Описание</span><span class="sxs-lookup"><span data-stu-id="66332-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="66332-113">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="66332-113">webEndpointType</span></span>|<span data-ttu-id="66332-114">Строка, указывающая тип конечной точки.</span><span class="sxs-lookup"><span data-stu-id="66332-114">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="66332-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="66332-115">Child Elements</span></span>  
 <span data-ttu-id="66332-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="66332-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="66332-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="66332-117">Parent Elements</span></span>  
  
|<span data-ttu-id="66332-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="66332-118">Element</span></span>|<span data-ttu-id="66332-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="66332-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66332-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="66332-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="66332-121">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="66332-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="66332-122">См. также</span><span class="sxs-lookup"><span data-stu-id="66332-122">See Also</span></span>  
 <xref:System.ServiceModel.Description.WebScriptEndpoint>  
 <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
