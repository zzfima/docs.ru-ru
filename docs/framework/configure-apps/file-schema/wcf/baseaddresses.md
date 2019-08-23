---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 059ea4e637ab906d1fde9807a73ac8341f81c574
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926426"
---
# <a name="baseaddresses"></a><span data-ttu-id="a0b3b-101">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="a0b3b-101">\<baseAddresses></span></span>
<span data-ttu-id="a0b3b-102">Представляет коллекцию элементов `baseAddress`, которые являются базовыми адресам для узла службы в резидентной среде.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="a0b3b-103">Если указан базовый адрес, конечные точки можно настроить, используя относительные (по отношению к базовому адресу) адреса.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="a0b3b-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a0b3b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a0b3b-105">\<> клиента</span><span class="sxs-lookup"><span data-stu-id="a0b3b-105">\<client></span></span>  
<span data-ttu-id="a0b3b-106">\<> конечной точки</span><span class="sxs-lookup"><span data-stu-id="a0b3b-106">\<endpoint></span></span>  
<span data-ttu-id="a0b3b-107">\<> узла</span><span class="sxs-lookup"><span data-stu-id="a0b3b-107">\<host></span></span>  
<span data-ttu-id="a0b3b-108">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="a0b3b-108">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0b3b-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0b3b-109">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="a0b3b-110">Тип</span><span class="sxs-lookup"><span data-stu-id="a0b3b-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0b3b-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a0b3b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a0b3b-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0b3b-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a0b3b-113">Attributes</span></span>  
 <span data-ttu-id="a0b3b-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a0b3b-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a0b3b-115">Child Elements</span></span>  
  
|<span data-ttu-id="a0b3b-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="a0b3b-116">Element</span></span>|<span data-ttu-id="a0b3b-117">Описание</span><span class="sxs-lookup"><span data-stu-id="a0b3b-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0b3b-118">\<add></span><span class="sxs-lookup"><span data-stu-id="a0b3b-118">\<add></span></span>](add-of-baseaddresses.md)|<span data-ttu-id="a0b3b-119">Элемент конфигурации, который задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-119">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a0b3b-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a0b3b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a0b3b-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="a0b3b-121">Element</span></span>|<span data-ttu-id="a0b3b-122">Описание</span><span class="sxs-lookup"><span data-stu-id="a0b3b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0b3b-123">\<> узла</span><span class="sxs-lookup"><span data-stu-id="a0b3b-123">\<host></span></span>](host.md)|<span data-ttu-id="a0b3b-124">Элемент конфигурации, который задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-124">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a0b3b-125">См. также</span><span class="sxs-lookup"><span data-stu-id="a0b3b-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="a0b3b-126">Размещение</span><span class="sxs-lookup"><span data-stu-id="a0b3b-126">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
