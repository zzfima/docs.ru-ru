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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7177c62af8501258ad8709bff88cb85488b56727
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="lthostgt"></a><span data-ttu-id="bb027-102">&lt;узел&gt;</span><span class="sxs-lookup"><span data-stu-id="bb027-102">&lt;host&gt;</span></span>
<span data-ttu-id="bb027-103">Задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="bb027-103">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="bb027-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bb027-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bb027-105">\<службы ></span><span class="sxs-lookup"><span data-stu-id="bb027-105">\<services></span></span>  
<span data-ttu-id="bb027-106">\<Служба ></span><span class="sxs-lookup"><span data-stu-id="bb027-106">\<service></span></span>  
<span data-ttu-id="bb027-107">\<узел ></span><span class="sxs-lookup"><span data-stu-id="bb027-107">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb027-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb027-108">Syntax</span></span>  
  
```xml  
<host>  
      <baseAddresses>  
         <baseAddress baseAddress="string" />  
      </baseAddresses>  
      <timeOuts closeTimeout="TimeSpan"  
         openTimeout="TimeSpan" >  
</host>  
```  
  
## <a name="type"></a><span data-ttu-id="bb027-109">Тип</span><span class="sxs-lookup"><span data-stu-id="bb027-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb027-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bb027-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bb027-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bb027-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb027-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bb027-112">Attributes</span></span>  
 <span data-ttu-id="bb027-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bb027-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bb027-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bb027-114">Child Elements</span></span>  
  
|<span data-ttu-id="bb027-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="bb027-115">Element</span></span>|<span data-ttu-id="bb027-116">Описание:</span><span class="sxs-lookup"><span data-stu-id="bb027-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bb027-117">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="bb027-117">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="bb027-118">Коллекция элементов`baseAddress`, которая задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="bb027-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="bb027-119">\<время ожидания ></span><span class="sxs-lookup"><span data-stu-id="bb027-119">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="bb027-120">Элемент конфигурации, задающий допустимый интервал времени для открытия или закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="bb027-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bb027-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bb027-121">Parent Elements</span></span>  
  
|<span data-ttu-id="bb027-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="bb027-122">Element</span></span>|<span data-ttu-id="bb027-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="bb027-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bb027-124">\<Служба ></span><span class="sxs-lookup"><span data-stu-id="bb027-124">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="bb027-125">Задает параметры службы [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb027-125">Specifies the settings for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bb027-126">См. также</span><span class="sxs-lookup"><span data-stu-id="bb027-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="bb027-127">Размещение</span><span class="sxs-lookup"><span data-stu-id="bb027-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
