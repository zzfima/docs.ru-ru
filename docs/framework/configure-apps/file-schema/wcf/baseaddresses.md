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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bfe66b499eb50a058ed8b6a46769893f6dc5fd6e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltbaseaddressesgt"></a><span data-ttu-id="7e2ed-102">&lt;среди базовых адресов&gt;</span><span class="sxs-lookup"><span data-stu-id="7e2ed-102">&lt;baseAddresses&gt;</span></span>
<span data-ttu-id="7e2ed-103">Представляет коллекцию элементов `baseAddress`, которые являются базовыми адресам для узла службы в резидентной среде.</span><span class="sxs-lookup"><span data-stu-id="7e2ed-103">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="7e2ed-104">Если указан базовый адрес, конечные точки можно настроить, используя относительные (по отношению к базовому адресу) адреса.</span><span class="sxs-lookup"><span data-stu-id="7e2ed-104">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="7e2ed-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7e2ed-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="7e2ed-106">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="7e2ed-106">\<client></span></span>  
<span data-ttu-id="7e2ed-107">\<Конечная точка ></span><span class="sxs-lookup"><span data-stu-id="7e2ed-107">\<endpoint></span></span>  
<span data-ttu-id="7e2ed-108">\<узел ></span><span class="sxs-lookup"><span data-stu-id="7e2ed-108">\<host></span></span>  
<span data-ttu-id="7e2ed-109">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="7e2ed-109">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e2ed-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e2ed-110">Syntax</span></span>  
  
```xml  
<baseAddresses>  
   <add baseAddress="string" />  
</baseAddresses>  
```  
  
## <a name="type"></a><span data-ttu-id="7e2ed-111">Тип</span><span class="sxs-lookup"><span data-stu-id="7e2ed-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e2ed-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7e2ed-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7e2ed-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7e2ed-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e2ed-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7e2ed-114">Attributes</span></span>  
 <span data-ttu-id="7e2ed-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7e2ed-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7e2ed-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7e2ed-116">Child Elements</span></span>  
  
|<span data-ttu-id="7e2ed-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="7e2ed-117">Element</span></span>|<span data-ttu-id="7e2ed-118">Описание</span><span class="sxs-lookup"><span data-stu-id="7e2ed-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e2ed-119">\<add></span><span class="sxs-lookup"><span data-stu-id="7e2ed-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="7e2ed-120">Элемент конфигурации, который задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="7e2ed-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7e2ed-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7e2ed-121">Parent Elements</span></span>  
  
|<span data-ttu-id="7e2ed-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="7e2ed-122">Element</span></span>|<span data-ttu-id="7e2ed-123">Описание</span><span class="sxs-lookup"><span data-stu-id="7e2ed-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e2ed-124">\<узел ></span><span class="sxs-lookup"><span data-stu-id="7e2ed-124">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="7e2ed-125">Элемент конфигурации, который задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="7e2ed-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e2ed-126">См. также</span><span class="sxs-lookup"><span data-stu-id="7e2ed-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="7e2ed-127">Размещение</span><span class="sxs-lookup"><span data-stu-id="7e2ed-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
