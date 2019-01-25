---
title: '&lt;Узел&gt;'
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 1fb35058d407d0fbae78092bb4ccd45b0aaa40e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702032"
---
# <a name="lthostgt"></a><span data-ttu-id="237bf-102">&lt;Узел&gt;</span><span class="sxs-lookup"><span data-stu-id="237bf-102">&lt;host&gt;</span></span>
<span data-ttu-id="237bf-103">Задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="237bf-103">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="237bf-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="237bf-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="237bf-105">\<Services ></span><span class="sxs-lookup"><span data-stu-id="237bf-105">\<services></span></span>  
<span data-ttu-id="237bf-106">\<службы ></span><span class="sxs-lookup"><span data-stu-id="237bf-106">\<service></span></span>  
<span data-ttu-id="237bf-107">\<узел ></span><span class="sxs-lookup"><span data-stu-id="237bf-107">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="237bf-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="237bf-108">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="237bf-109">Тип</span><span class="sxs-lookup"><span data-stu-id="237bf-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="237bf-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="237bf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="237bf-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="237bf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="237bf-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="237bf-112">Attributes</span></span>  
 <span data-ttu-id="237bf-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="237bf-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="237bf-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="237bf-114">Child Elements</span></span>  
  
|<span data-ttu-id="237bf-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="237bf-115">Element</span></span>|<span data-ttu-id="237bf-116">Описание:</span><span class="sxs-lookup"><span data-stu-id="237bf-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="237bf-117">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="237bf-117">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="237bf-118">Коллекция элементов`baseAddress`, которая задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="237bf-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="237bf-119">\<время ожидания ></span><span class="sxs-lookup"><span data-stu-id="237bf-119">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="237bf-120">Элемент конфигурации, задающий допустимый интервал времени для открытия или закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="237bf-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="237bf-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="237bf-121">Parent Elements</span></span>  
  
|<span data-ttu-id="237bf-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="237bf-122">Element</span></span>|<span data-ttu-id="237bf-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="237bf-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="237bf-124">\<службы ></span><span class="sxs-lookup"><span data-stu-id="237bf-124">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="237bf-125">Задает параметры для службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="237bf-125">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="237bf-126">См. также</span><span class="sxs-lookup"><span data-stu-id="237bf-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="237bf-127">Размещение</span><span class="sxs-lookup"><span data-stu-id="237bf-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
