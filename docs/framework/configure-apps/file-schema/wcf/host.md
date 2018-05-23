---
title: '&lt;Узел&gt;'
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: ec53568e9d1df9ebb04bc299f491e80674950c63
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="lthostgt"></a><span data-ttu-id="be880-102">&lt;Узел&gt;</span><span class="sxs-lookup"><span data-stu-id="be880-102">&lt;host&gt;</span></span>
<span data-ttu-id="be880-103">Задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="be880-103">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="be880-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="be880-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="be880-105">\<службы ></span><span class="sxs-lookup"><span data-stu-id="be880-105">\<services></span></span>  
<span data-ttu-id="be880-106">\<Служба ></span><span class="sxs-lookup"><span data-stu-id="be880-106">\<service></span></span>  
<span data-ttu-id="be880-107">\<узел ></span><span class="sxs-lookup"><span data-stu-id="be880-107">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be880-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be880-108">Syntax</span></span>  
  
```xml  
<host>
    <baseAddresses>  
        <add baseAddress="string" />  
    </baseAddresses>  
    <timeOuts closeTimeout="TimeSpan" openTimeout="TimeSpan">  
</host>  
```  
  
## <a name="type"></a><span data-ttu-id="be880-109">Тип</span><span class="sxs-lookup"><span data-stu-id="be880-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be880-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="be880-110">Attributes and Elements</span></span>  
 <span data-ttu-id="be880-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="be880-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be880-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="be880-112">Attributes</span></span>  
 <span data-ttu-id="be880-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="be880-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="be880-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="be880-114">Child Elements</span></span>  
  
|<span data-ttu-id="be880-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="be880-115">Element</span></span>|<span data-ttu-id="be880-116">Описание</span><span class="sxs-lookup"><span data-stu-id="be880-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="be880-117">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="be880-117">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="be880-118">Коллекция элементов`baseAddress`, которая задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="be880-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="be880-119">\<время ожидания ></span><span class="sxs-lookup"><span data-stu-id="be880-119">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="be880-120">Элемент конфигурации, задающий допустимый интервал времени для открытия или закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="be880-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="be880-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="be880-121">Parent Elements</span></span>  
  
|<span data-ttu-id="be880-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="be880-122">Element</span></span>|<span data-ttu-id="be880-123">Описание</span><span class="sxs-lookup"><span data-stu-id="be880-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="be880-124">\<Служба ></span><span class="sxs-lookup"><span data-stu-id="be880-124">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="be880-125">Задает параметры для службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="be880-125">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="be880-126">См. также</span><span class="sxs-lookup"><span data-stu-id="be880-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="be880-127">Размещение</span><span class="sxs-lookup"><span data-stu-id="be880-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
