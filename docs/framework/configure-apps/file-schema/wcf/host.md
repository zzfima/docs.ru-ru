---
title: "&lt;узел&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bded8d718259bf4fc84bfe790db069a77fc2a703
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="lthostgt"></a><span data-ttu-id="8b1d2-102">&lt;узел&gt;</span><span class="sxs-lookup"><span data-stu-id="8b1d2-102">&lt;host&gt;</span></span>
<span data-ttu-id="8b1d2-103">Задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-103">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="8b1d2-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8b1d2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8b1d2-105">\<службы ></span><span class="sxs-lookup"><span data-stu-id="8b1d2-105">\<services></span></span>  
<span data-ttu-id="8b1d2-106">\<Служба ></span><span class="sxs-lookup"><span data-stu-id="8b1d2-106">\<service></span></span>  
<span data-ttu-id="8b1d2-107">\<узел ></span><span class="sxs-lookup"><span data-stu-id="8b1d2-107">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b1d2-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b1d2-108">Syntax</span></span>  
  
```xml  
<host>  
      <baseAddresses>  
         <baseAddress baseAddress="string" />  
      </baseAddresses>  
      <timeOuts closeTimeout="TimeSpan"  
         openTimeout="TimeSpan" >  
</host>  
```  
  
## <a name="type"></a><span data-ttu-id="8b1d2-109">Тип</span><span class="sxs-lookup"><span data-stu-id="8b1d2-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b1d2-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8b1d2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8b1d2-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b1d2-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8b1d2-112">Attributes</span></span>  
 <span data-ttu-id="8b1d2-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8b1d2-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8b1d2-114">Child Elements</span></span>  
  
|<span data-ttu-id="8b1d2-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="8b1d2-115">Element</span></span>|<span data-ttu-id="8b1d2-116">Описание</span><span class="sxs-lookup"><span data-stu-id="8b1d2-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b1d2-117">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="8b1d2-117">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="8b1d2-118">Коллекция элементов`baseAddress`, которая задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="8b1d2-119">\<время ожидания ></span><span class="sxs-lookup"><span data-stu-id="8b1d2-119">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="8b1d2-120">Элемент конфигурации, задающий допустимый интервал времени для открытия или закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8b1d2-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8b1d2-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8b1d2-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="8b1d2-122">Element</span></span>|<span data-ttu-id="8b1d2-123">Описание</span><span class="sxs-lookup"><span data-stu-id="8b1d2-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b1d2-124">\<Служба ></span><span class="sxs-lookup"><span data-stu-id="8b1d2-124">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="8b1d2-125">Задает параметры службы [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b1d2-125">Specifies the settings for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8b1d2-126">См. также</span><span class="sxs-lookup"><span data-stu-id="8b1d2-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="8b1d2-127">Размещение</span><span class="sxs-lookup"><span data-stu-id="8b1d2-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
