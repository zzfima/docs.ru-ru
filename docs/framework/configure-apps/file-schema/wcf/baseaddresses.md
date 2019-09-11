---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 9b3ed6b39f1743249925d5b6d9a47845c87983bc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850209"
---
# <a name="baseaddresses"></a><span data-ttu-id="32209-101">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="32209-101">\<baseAddresses></span></span>
<span data-ttu-id="32209-102">Представляет коллекцию элементов `baseAddress`, которые являются базовыми адресам для узла службы в резидентной среде.</span><span class="sxs-lookup"><span data-stu-id="32209-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="32209-103">Если указан базовый адрес, конечные точки можно настроить, используя относительные (по отношению к базовому адресу) адреса.</span><span class="sxs-lookup"><span data-stu-id="32209-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
<span data-ttu-id="32209-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="32209-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="32209-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="32209-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="32209-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<службы >** ](services.md)</span><span class="sxs-lookup"><span data-stu-id="32209-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="32209-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> службы**](service.md)</span><span class="sxs-lookup"><span data-stu-id="32209-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="32209-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> узла**](host.md)</span><span class="sxs-lookup"><span data-stu-id="32209-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)</span></span>\
<span data-ttu-id="32209-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<baseAddresses >**</span><span class="sxs-lookup"><span data-stu-id="32209-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddresses>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32209-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32209-110">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="32209-111">Тип</span><span class="sxs-lookup"><span data-stu-id="32209-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32209-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="32209-112">Attributes and Elements</span></span>  
 <span data-ttu-id="32209-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="32209-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32209-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="32209-114">Attributes</span></span>  
 <span data-ttu-id="32209-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="32209-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="32209-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="32209-116">Child Elements</span></span>  
  
|<span data-ttu-id="32209-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="32209-117">Element</span></span>|<span data-ttu-id="32209-118">Описание</span><span class="sxs-lookup"><span data-stu-id="32209-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32209-119">\<add></span><span class="sxs-lookup"><span data-stu-id="32209-119">\<add></span></span>](add-of-baseaddresses.md)|<span data-ttu-id="32209-120">Элемент конфигурации, который задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="32209-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="32209-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="32209-121">Parent Elements</span></span>  
  
|<span data-ttu-id="32209-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="32209-122">Element</span></span>|<span data-ttu-id="32209-123">Описание</span><span class="sxs-lookup"><span data-stu-id="32209-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32209-124">\<> узла</span><span class="sxs-lookup"><span data-stu-id="32209-124">\<host></span></span>](host.md)|<span data-ttu-id="32209-125">Элемент конфигурации, который задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="32209-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="32209-126">См. также</span><span class="sxs-lookup"><span data-stu-id="32209-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="32209-127">Размещение</span><span class="sxs-lookup"><span data-stu-id="32209-127">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
