---
title: '&lt;useRequestHeadersForMetadataAddress&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c538939a97e43239048853b5d6c32251d557d7e2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltuserequestheadersformetadataaddressgt"></a><span data-ttu-id="dcffe-102">&lt;useRequestHeadersForMetadataAddress&gt;</span><span class="sxs-lookup"><span data-stu-id="dcffe-102">&lt;useRequestHeadersForMetadataAddress&gt;</span></span>
<span data-ttu-id="dcffe-103">Включает получение сведений об адресе метаданных из заголовков сообщений запросов.</span><span class="sxs-lookup"><span data-stu-id="dcffe-103">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="dcffe-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="dcffe-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dcffe-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="dcffe-105">\<behaviors></span></span>  
<span data-ttu-id="dcffe-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="dcffe-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="dcffe-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="dcffe-107">\<behavior></span></span>  
<span data-ttu-id="dcffe-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="dcffe-108">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcffe-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dcffe-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dcffe-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dcffe-110">Attributes and Elements</span></span>  
 <span data-ttu-id="dcffe-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dcffe-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dcffe-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dcffe-112">Attributes</span></span>  
 <span data-ttu-id="dcffe-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="dcffe-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dcffe-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dcffe-114">Child Elements</span></span>  
  
|<span data-ttu-id="dcffe-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="dcffe-115">Element</span></span>|<span data-ttu-id="dcffe-116">Описание</span><span class="sxs-lookup"><span data-stu-id="dcffe-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dcffe-117">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="dcffe-117">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="dcffe-118">Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="dcffe-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dcffe-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dcffe-119">Parent Elements</span></span>  
  
|<span data-ttu-id="dcffe-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="dcffe-120">Element</span></span>|<span data-ttu-id="dcffe-121">Описание</span><span class="sxs-lookup"><span data-stu-id="dcffe-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dcffe-122">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="dcffe-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="dcffe-123">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="dcffe-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dcffe-124">См. также</span><span class="sxs-lookup"><span data-stu-id="dcffe-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
