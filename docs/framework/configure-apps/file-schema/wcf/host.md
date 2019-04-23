---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 3d1f7774f61060880a5c3b0327bdd6c2cc4dd74e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103003"
---
# <a name="host"></a><span data-ttu-id="1c05f-101">\<узел ></span><span class="sxs-lookup"><span data-stu-id="1c05f-101">\<host></span></span>
<span data-ttu-id="1c05f-102">Задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="1c05f-102">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="1c05f-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1c05f-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="1c05f-104">\<Services ></span><span class="sxs-lookup"><span data-stu-id="1c05f-104">\<services></span></span>  
<span data-ttu-id="1c05f-105">\<службы ></span><span class="sxs-lookup"><span data-stu-id="1c05f-105">\<service></span></span>  
<span data-ttu-id="1c05f-106">\<узел ></span><span class="sxs-lookup"><span data-stu-id="1c05f-106">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c05f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c05f-107">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="1c05f-108">Тип</span><span class="sxs-lookup"><span data-stu-id="1c05f-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c05f-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1c05f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1c05f-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1c05f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c05f-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1c05f-111">Attributes</span></span>  
 <span data-ttu-id="1c05f-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1c05f-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1c05f-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1c05f-113">Child Elements</span></span>  
  
|<span data-ttu-id="1c05f-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="1c05f-114">Element</span></span>|<span data-ttu-id="1c05f-115">Описание</span><span class="sxs-lookup"><span data-stu-id="1c05f-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c05f-116">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="1c05f-116">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="1c05f-117">Коллекция элементов`baseAddress`, которая задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="1c05f-117">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="1c05f-118">\<время ожидания ></span><span class="sxs-lookup"><span data-stu-id="1c05f-118">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="1c05f-119">Элемент конфигурации, задающий допустимый интервал времени для открытия или закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="1c05f-119">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1c05f-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1c05f-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1c05f-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="1c05f-121">Element</span></span>|<span data-ttu-id="1c05f-122">Описание</span><span class="sxs-lookup"><span data-stu-id="1c05f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c05f-123">\<службы ></span><span class="sxs-lookup"><span data-stu-id="1c05f-123">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="1c05f-124">Задает параметры для службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1c05f-124">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1c05f-125">См. также</span><span class="sxs-lookup"><span data-stu-id="1c05f-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="1c05f-126">Размещение</span><span class="sxs-lookup"><span data-stu-id="1c05f-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
