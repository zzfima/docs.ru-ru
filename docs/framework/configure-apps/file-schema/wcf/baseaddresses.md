---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: dc4b31e729f9037da101bdf3e6cde28e91b1a070
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277021"
---
# <a name="baseaddresses"></a><span data-ttu-id="aa9e6-101">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="aa9e6-101">\<baseAddresses></span></span>
<span data-ttu-id="aa9e6-102">Представляет коллекцию элементов `baseAddress`, которые являются базовыми адресам для узла службы в резидентной среде.</span><span class="sxs-lookup"><span data-stu-id="aa9e6-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="aa9e6-103">Если указан базовый адрес, конечные точки можно настроить, используя относительные (по отношению к базовому адресу) адреса.</span><span class="sxs-lookup"><span data-stu-id="aa9e6-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="aa9e6-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="aa9e6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="aa9e6-105">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="aa9e6-105">\<client></span></span>  
<span data-ttu-id="aa9e6-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="aa9e6-106">\<endpoint></span></span>  
<span data-ttu-id="aa9e6-107">\<узел ></span><span class="sxs-lookup"><span data-stu-id="aa9e6-107">\<host></span></span>  
<span data-ttu-id="aa9e6-108">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="aa9e6-108">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa9e6-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa9e6-109">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="aa9e6-110">Тип</span><span class="sxs-lookup"><span data-stu-id="aa9e6-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa9e6-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aa9e6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="aa9e6-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aa9e6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa9e6-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aa9e6-113">Attributes</span></span>  
 <span data-ttu-id="aa9e6-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="aa9e6-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aa9e6-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aa9e6-115">Child Elements</span></span>  
  
|<span data-ttu-id="aa9e6-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="aa9e6-116">Element</span></span>|<span data-ttu-id="aa9e6-117">Описание</span><span class="sxs-lookup"><span data-stu-id="aa9e6-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa9e6-118">\<add></span><span class="sxs-lookup"><span data-stu-id="aa9e6-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="aa9e6-119">Элемент конфигурации, который задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="aa9e6-119">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aa9e6-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aa9e6-120">Parent Elements</span></span>  
  
|<span data-ttu-id="aa9e6-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="aa9e6-121">Element</span></span>|<span data-ttu-id="aa9e6-122">Описание</span><span class="sxs-lookup"><span data-stu-id="aa9e6-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa9e6-123">\<узел ></span><span class="sxs-lookup"><span data-stu-id="aa9e6-123">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="aa9e6-124">Элемент конфигурации, который задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="aa9e6-124">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa9e6-125">См. также</span><span class="sxs-lookup"><span data-stu-id="aa9e6-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="aa9e6-126">Размещение</span><span class="sxs-lookup"><span data-stu-id="aa9e6-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
