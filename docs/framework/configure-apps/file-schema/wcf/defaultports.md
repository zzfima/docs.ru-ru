---
title: '&lt;defaultPorts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd4fba4d7d5bcb0adc5a1a638598af2746ad4cf4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltdefaultportsgt"></a><span data-ttu-id="73b1f-102">&lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="73b1f-102">&lt;defaultPorts&gt;</span></span>
<span data-ttu-id="73b1f-103">Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="73b1f-103">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="73b1f-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="73b1f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="73b1f-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="73b1f-105">\<behaviors></span></span>  
<span data-ttu-id="73b1f-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="73b1f-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="73b1f-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="73b1f-107">\<behavior></span></span>  
<span data-ttu-id="73b1f-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="73b1f-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="73b1f-109">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="73b1f-109">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73b1f-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73b1f-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73b1f-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="73b1f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="73b1f-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="73b1f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73b1f-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="73b1f-113">Attributes</span></span>  
 <span data-ttu-id="73b1f-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="73b1f-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="73b1f-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="73b1f-115">Child Elements</span></span>  
  
|<span data-ttu-id="73b1f-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="73b1f-116">Element</span></span>|<span data-ttu-id="73b1f-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="73b1f-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73b1f-118">\<Добавить > из \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="73b1f-118">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="73b1f-119">Конечная точка связи по умолчанию, которую прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="73b1f-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="73b1f-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="73b1f-120">Parent Elements</span></span>  
  
|<span data-ttu-id="73b1f-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="73b1f-121">Element</span></span>|<span data-ttu-id="73b1f-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="73b1f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73b1f-123">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="73b1f-123">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="73b1f-124">Список портов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="73b1f-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="73b1f-125">См. также</span><span class="sxs-lookup"><span data-stu-id="73b1f-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
