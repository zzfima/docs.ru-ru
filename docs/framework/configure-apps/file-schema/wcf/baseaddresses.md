---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 7d0afd638e9a311b69ff47b6789d5fde093945ba
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212106"
---
# <a name="baseaddresses"></a><span data-ttu-id="322fc-101">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="322fc-101">\<baseAddresses></span></span>
<span data-ttu-id="322fc-102">Представляет коллекцию элементов `baseAddress`, которые являются базовыми адресам для узла службы в резидентной среде.</span><span class="sxs-lookup"><span data-stu-id="322fc-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="322fc-103">Если указан базовый адрес, конечные точки можно настроить, используя относительные (по отношению к базовому адресу) адреса.</span><span class="sxs-lookup"><span data-stu-id="322fc-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="322fc-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="322fc-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="322fc-105">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="322fc-105">\<client></span></span>  
<span data-ttu-id="322fc-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="322fc-106">\<endpoint></span></span>  
<span data-ttu-id="322fc-107">\<узел ></span><span class="sxs-lookup"><span data-stu-id="322fc-107">\<host></span></span>  
<span data-ttu-id="322fc-108">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="322fc-108">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="322fc-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="322fc-109">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="322fc-110">Тип</span><span class="sxs-lookup"><span data-stu-id="322fc-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="322fc-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="322fc-111">Attributes and Elements</span></span>  
 <span data-ttu-id="322fc-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="322fc-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="322fc-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="322fc-113">Attributes</span></span>  
 <span data-ttu-id="322fc-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="322fc-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="322fc-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="322fc-115">Child Elements</span></span>  
  
|<span data-ttu-id="322fc-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="322fc-116">Element</span></span>|<span data-ttu-id="322fc-117">Описание</span><span class="sxs-lookup"><span data-stu-id="322fc-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="322fc-118">\<add></span><span class="sxs-lookup"><span data-stu-id="322fc-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="322fc-119">Элемент конфигурации, который задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="322fc-119">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="322fc-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="322fc-120">Parent Elements</span></span>  
  
|<span data-ttu-id="322fc-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="322fc-121">Element</span></span>|<span data-ttu-id="322fc-122">Описание</span><span class="sxs-lookup"><span data-stu-id="322fc-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="322fc-123">\<узел ></span><span class="sxs-lookup"><span data-stu-id="322fc-123">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="322fc-124">Элемент конфигурации, который задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="322fc-124">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="322fc-125">См. также</span><span class="sxs-lookup"><span data-stu-id="322fc-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="322fc-126">Размещение</span><span class="sxs-lookup"><span data-stu-id="322fc-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
