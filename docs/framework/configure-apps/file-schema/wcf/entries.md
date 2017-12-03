---
title: "&lt;записи&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ef9c58a9b4ecd6db8b4efe116f6fafba01c3f6f5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltentriesgt"></a><span data-ttu-id="ec6b1-102">&lt;записи&gt;</span><span class="sxs-lookup"><span data-stu-id="ec6b1-102">&lt;entries&gt;</span></span>
<span data-ttu-id="ec6b1-103">Запись маршрутизации, содержащая сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="ec6b1-103">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="ec6b1-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="ec6b1-104">\<system.serviceModel></span></span>  
<span data-ttu-id="ec6b1-105">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="ec6b1-105">\<routing></span></span>  
<span data-ttu-id="ec6b1-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="ec6b1-106">\<routingTables></span></span>  
<span data-ttu-id="ec6b1-107">\<Таблица ></span><span class="sxs-lookup"><span data-stu-id="ec6b1-107">\<table></span></span>  
<span data-ttu-id="ec6b1-108">\<записи ></span><span class="sxs-lookup"><span data-stu-id="ec6b1-108">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec6b1-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec6b1-109">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ec6b1-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ec6b1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ec6b1-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec6b1-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ec6b1-112">Attributes</span></span>  
 <span data-ttu-id="ec6b1-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ec6b1-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ec6b1-114">Child Elements</span></span>  
  
|<span data-ttu-id="ec6b1-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="ec6b1-115">Element</span></span>|<span data-ttu-id="ec6b1-116">Описание</span><span class="sxs-lookup"><span data-stu-id="ec6b1-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec6b1-117">\<Фильтры ></span><span class="sxs-lookup"><span data-stu-id="ec6b1-117">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="ec6b1-118">Сопоставляет фильтр с ранее определенной конечной точкой клиента.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="ec6b1-119">Сообщения, соответствующие этому фильтру, будут отправлены по данному назначению.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ec6b1-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ec6b1-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ec6b1-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="ec6b1-121">Element</span></span>|<span data-ttu-id="ec6b1-122">Описание</span><span class="sxs-lookup"><span data-stu-id="ec6b1-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec6b1-123">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="ec6b1-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="ec6b1-124">Раздел конфигурации, содержащий таблицу маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec6b1-125">См. также</span><span class="sxs-lookup"><span data-stu-id="ec6b1-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>    
