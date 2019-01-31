---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 8a8f9db96281d8d775ff5c2923018228b3a9c1e5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269033"
---
# <a name="host"></a><span data-ttu-id="96a4f-101">\<узел ></span><span class="sxs-lookup"><span data-stu-id="96a4f-101">\<host></span></span>
<span data-ttu-id="96a4f-102">Задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="96a4f-102">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="96a4f-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="96a4f-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="96a4f-104">\<Services ></span><span class="sxs-lookup"><span data-stu-id="96a4f-104">\<services></span></span>  
<span data-ttu-id="96a4f-105">\<службы ></span><span class="sxs-lookup"><span data-stu-id="96a4f-105">\<service></span></span>  
<span data-ttu-id="96a4f-106">\<узел ></span><span class="sxs-lookup"><span data-stu-id="96a4f-106">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96a4f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="96a4f-107">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="96a4f-108">Тип</span><span class="sxs-lookup"><span data-stu-id="96a4f-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96a4f-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="96a4f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="96a4f-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="96a4f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96a4f-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="96a4f-111">Attributes</span></span>  
 <span data-ttu-id="96a4f-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="96a4f-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="96a4f-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="96a4f-113">Child Elements</span></span>  
  
|<span data-ttu-id="96a4f-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="96a4f-114">Element</span></span>|<span data-ttu-id="96a4f-115">Описание</span><span class="sxs-lookup"><span data-stu-id="96a4f-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96a4f-116">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="96a4f-116">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="96a4f-117">Коллекция элементов`baseAddress`, которая задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="96a4f-117">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="96a4f-118">\<время ожидания ></span><span class="sxs-lookup"><span data-stu-id="96a4f-118">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="96a4f-119">Элемент конфигурации, задающий допустимый интервал времени для открытия или закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="96a4f-119">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="96a4f-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="96a4f-120">Parent Elements</span></span>  
  
|<span data-ttu-id="96a4f-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="96a4f-121">Element</span></span>|<span data-ttu-id="96a4f-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="96a4f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96a4f-123">\<службы ></span><span class="sxs-lookup"><span data-stu-id="96a4f-123">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="96a4f-124">Задает параметры для службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="96a4f-124">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="96a4f-125">См. также</span><span class="sxs-lookup"><span data-stu-id="96a4f-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="96a4f-126">Размещение</span><span class="sxs-lookup"><span data-stu-id="96a4f-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
