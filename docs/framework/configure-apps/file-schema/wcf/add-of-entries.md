---
title: "&lt;add&gt; для &lt;entries&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1583ec3cab3ed43556dc066c1e4753ddf9845ef5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltentriesgt"></a><span data-ttu-id="b2b1e-102">&lt;add&gt; для &lt;entries&gt;</span><span class="sxs-lookup"><span data-stu-id="b2b1e-102">&lt;add&gt; of &lt;entries&gt;</span></span>
<span data-ttu-id="b2b1e-103">Представляет запись маршрутизации, которая сопоставляет фильтр с ранее определенной конечной точкой клиента.</span><span class="sxs-lookup"><span data-stu-id="b2b1e-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="b2b1e-104">Сообщения, соответствующие этому фильтру, будут отправлены по данному назначению.</span><span class="sxs-lookup"><span data-stu-id="b2b1e-104">Messages matching this filter will be sent to this destination.</span></span>  
  
 <span data-ttu-id="b2b1e-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="b2b1e-105">\<system.serviceModel></span></span>  
<span data-ttu-id="b2b1e-106">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="b2b1e-106">\<routing></span></span>  
<span data-ttu-id="b2b1e-107">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="b2b1e-107">\<routingTables></span></span>  
<span data-ttu-id="b2b1e-108">\<Таблица ></span><span class="sxs-lookup"><span data-stu-id="b2b1e-108">\<table></span></span>  
<span data-ttu-id="b2b1e-109">\<записи ></span><span class="sxs-lookup"><span data-stu-id="b2b1e-109">\<entries></span></span>  
<span data-ttu-id="b2b1e-110">\<add></span><span class="sxs-lookup"><span data-stu-id="b2b1e-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2b1e-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2b1e-111">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2b1e-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b2b1e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b2b1e-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b2b1e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2b1e-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b2b1e-114">Attributes</span></span>  
  
|<span data-ttu-id="b2b1e-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b2b1e-115">Attribute</span></span>|<span data-ttu-id="b2b1e-116">Описание</span><span class="sxs-lookup"><span data-stu-id="b2b1e-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b2b1e-117">backupList</span><span class="sxs-lookup"><span data-stu-id="b2b1e-117">backupList</span></span>|<span data-ttu-id="b2b1e-118">Строка, указывающая ссылку на резервный список конечных точек.</span><span class="sxs-lookup"><span data-stu-id="b2b1e-118">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="b2b1e-119">конечная точка</span><span class="sxs-lookup"><span data-stu-id="b2b1e-119">endpoint</span></span>|<span data-ttu-id="b2b1e-120">Строка, в которой указана ссылка на конечную точку клиента, получающую сообщения, которые соответствуют критериям фильтра, указанного в атрибуте `filterName`.</span><span class="sxs-lookup"><span data-stu-id="b2b1e-120">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="b2b1e-121">filterName</span><span class="sxs-lookup"><span data-stu-id="b2b1e-121">filterName</span></span>|<span data-ttu-id="b2b1e-122">Строка, в которой указана ссылка на элемент фильтра.</span><span class="sxs-lookup"><span data-stu-id="b2b1e-122">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="b2b1e-123">priority</span><span class="sxs-lookup"><span data-stu-id="b2b1e-123">priority</span></span>|<span data-ttu-id="b2b1e-124">Целое число, задающее приоритет этой записи.</span><span class="sxs-lookup"><span data-stu-id="b2b1e-124">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="b2b1e-125">Записи в таблице маршрутизации обрабатываются исходя из приоритета, причем 0 является самым низким приоритетом.</span><span class="sxs-lookup"><span data-stu-id="b2b1e-125">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="b2b1e-126">Все записи определенного приоритета обрабатываются одновременно, и, если для текущего приоритета не находится совпадающая запись, вычисляется следующий уровень приоритета.</span><span class="sxs-lookup"><span data-stu-id="b2b1e-126">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="b2b1e-127">Это значение является необязательным.</span><span class="sxs-lookup"><span data-stu-id="b2b1e-127">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2b1e-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b2b1e-128">Child Elements</span></span>  
 <span data-ttu-id="b2b1e-129">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b2b1e-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b2b1e-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b2b1e-130">Parent Elements</span></span>  
  
|<span data-ttu-id="b2b1e-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="b2b1e-131">Element</span></span>|<span data-ttu-id="b2b1e-132">Описание:</span><span class="sxs-lookup"><span data-stu-id="b2b1e-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2b1e-133">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="b2b1e-133">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="b2b1e-134">Раздел конфигурации, в котором содержатся записи сопоставления маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="b2b1e-134">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b2b1e-135">См. также</span><span class="sxs-lookup"><span data-stu-id="b2b1e-135">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType> 
