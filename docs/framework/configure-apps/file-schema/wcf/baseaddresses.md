---
title: "&lt;среди базовых адресов&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4bf698b64b528b0ea109223a2d94e6725c8ce6b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltbaseaddressesgt"></a><span data-ttu-id="a4b6a-102">&lt;среди базовых адресов&gt;</span><span class="sxs-lookup"><span data-stu-id="a4b6a-102">&lt;baseAddresses&gt;</span></span>
<span data-ttu-id="a4b6a-103">Представляет коллекцию элементов `baseAddress`, которые являются базовыми адресам для узла службы в резидентной среде.</span><span class="sxs-lookup"><span data-stu-id="a4b6a-103">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="a4b6a-104">Если указан базовый адрес, конечные точки можно настроить, используя относительные (по отношению к базовому адресу) адреса.</span><span class="sxs-lookup"><span data-stu-id="a4b6a-104">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="a4b6a-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a4b6a-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="a4b6a-106">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="a4b6a-106">\<client></span></span>  
<span data-ttu-id="a4b6a-107">\<Конечная точка ></span><span class="sxs-lookup"><span data-stu-id="a4b6a-107">\<endpoint></span></span>  
<span data-ttu-id="a4b6a-108">\<узел ></span><span class="sxs-lookup"><span data-stu-id="a4b6a-108">\<host></span></span>  
<span data-ttu-id="a4b6a-109">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="a4b6a-109">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4b6a-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a4b6a-110">Syntax</span></span>  
  
```xml  
<baseAddresses>  
   <add baseAddress="string" />  
</baseAddresses>  
```  
  
## <a name="type"></a><span data-ttu-id="a4b6a-111">Тип</span><span class="sxs-lookup"><span data-stu-id="a4b6a-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4b6a-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a4b6a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a4b6a-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a4b6a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4b6a-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a4b6a-114">Attributes</span></span>  
 <span data-ttu-id="a4b6a-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a4b6a-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a4b6a-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a4b6a-116">Child Elements</span></span>  
  
|<span data-ttu-id="a4b6a-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="a4b6a-117">Element</span></span>|<span data-ttu-id="a4b6a-118">Описание</span><span class="sxs-lookup"><span data-stu-id="a4b6a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4b6a-119">\<add></span><span class="sxs-lookup"><span data-stu-id="a4b6a-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="a4b6a-120">Элемент конфигурации, который задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="a4b6a-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a4b6a-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a4b6a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a4b6a-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="a4b6a-122">Element</span></span>|<span data-ttu-id="a4b6a-123">Описание</span><span class="sxs-lookup"><span data-stu-id="a4b6a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4b6a-124">\<узел ></span><span class="sxs-lookup"><span data-stu-id="a4b6a-124">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="a4b6a-125">Элемент конфигурации, который задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="a4b6a-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a4b6a-126">См. также</span><span class="sxs-lookup"><span data-stu-id="a4b6a-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="a4b6a-127">Размещение</span><span class="sxs-lookup"><span data-stu-id="a4b6a-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
