---
title: '&lt;Среди базовых адресов&gt;'
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 34d400e74b24e9eb4140d1b43597b0217b23d80c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730130"
---
# <a name="ltbaseaddressesgt"></a><span data-ttu-id="e3803-102">&lt;Среди базовых адресов&gt;</span><span class="sxs-lookup"><span data-stu-id="e3803-102">&lt;baseAddresses&gt;</span></span>
<span data-ttu-id="e3803-103">Представляет коллекцию элементов `baseAddress`, которые являются базовыми адресам для узла службы в резидентной среде.</span><span class="sxs-lookup"><span data-stu-id="e3803-103">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="e3803-104">Если указан базовый адрес, конечные точки можно настроить, используя относительные (по отношению к базовому адресу) адреса.</span><span class="sxs-lookup"><span data-stu-id="e3803-104">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="e3803-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e3803-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e3803-106">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="e3803-106">\<client></span></span>  
<span data-ttu-id="e3803-107">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="e3803-107">\<endpoint></span></span>  
<span data-ttu-id="e3803-108">\<узел ></span><span class="sxs-lookup"><span data-stu-id="e3803-108">\<host></span></span>  
<span data-ttu-id="e3803-109">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="e3803-109">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3803-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3803-110">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="e3803-111">Тип</span><span class="sxs-lookup"><span data-stu-id="e3803-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3803-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e3803-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e3803-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e3803-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3803-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e3803-114">Attributes</span></span>  
 <span data-ttu-id="e3803-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e3803-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e3803-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e3803-116">Child Elements</span></span>  
  
|<span data-ttu-id="e3803-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="e3803-117">Element</span></span>|<span data-ttu-id="e3803-118">Описание</span><span class="sxs-lookup"><span data-stu-id="e3803-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3803-119">\<add></span><span class="sxs-lookup"><span data-stu-id="e3803-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="e3803-120">Элемент конфигурации, который задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="e3803-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e3803-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e3803-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e3803-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="e3803-122">Element</span></span>|<span data-ttu-id="e3803-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="e3803-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3803-124">\<узел ></span><span class="sxs-lookup"><span data-stu-id="e3803-124">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="e3803-125">Элемент конфигурации, который задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="e3803-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3803-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e3803-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="e3803-127">Размещение</span><span class="sxs-lookup"><span data-stu-id="e3803-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
