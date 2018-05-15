---
title: '&lt;defaultPorts&gt;'
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 2f7de066a1b91e9fa22fbe0213e221c6f4bbe617
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltdefaultportsgt"></a><span data-ttu-id="d1c52-102">&lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="d1c52-102">&lt;defaultPorts&gt;</span></span>
<span data-ttu-id="d1c52-103">Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="d1c52-103">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="d1c52-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d1c52-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d1c52-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="d1c52-105">\<behaviors></span></span>  
<span data-ttu-id="d1c52-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d1c52-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="d1c52-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="d1c52-107">\<behavior></span></span>  
<span data-ttu-id="d1c52-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="d1c52-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="d1c52-109">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="d1c52-109">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1c52-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d1c52-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1c52-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d1c52-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d1c52-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d1c52-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1c52-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d1c52-113">Attributes</span></span>  
 <span data-ttu-id="d1c52-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d1c52-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d1c52-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d1c52-115">Child Elements</span></span>  
  
|<span data-ttu-id="d1c52-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="d1c52-116">Element</span></span>|<span data-ttu-id="d1c52-117">Описание</span><span class="sxs-lookup"><span data-stu-id="d1c52-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1c52-118">\<Добавить > из \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="d1c52-118">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="d1c52-119">Конечная точка связи по умолчанию, которую прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="d1c52-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d1c52-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d1c52-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d1c52-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="d1c52-121">Element</span></span>|<span data-ttu-id="d1c52-122">Описание</span><span class="sxs-lookup"><span data-stu-id="d1c52-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1c52-123">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="d1c52-123">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="d1c52-124">Список портов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d1c52-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d1c52-125">См. также</span><span class="sxs-lookup"><span data-stu-id="d1c52-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
