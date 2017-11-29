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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9b6d8d1c3797d60b26443e07cc527ea8b86f526e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltentriesgt"></a><span data-ttu-id="78eaa-102">&lt;записи&gt;</span><span class="sxs-lookup"><span data-stu-id="78eaa-102">&lt;entries&gt;</span></span>
<span data-ttu-id="78eaa-103">Запись маршрутизации, содержащая сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="78eaa-103">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="78eaa-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="78eaa-104">\<system.serviceModel></span></span>  
<span data-ttu-id="78eaa-105">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="78eaa-105">\<routing></span></span>  
<span data-ttu-id="78eaa-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="78eaa-106">\<routingTables></span></span>  
<span data-ttu-id="78eaa-107">\<Таблица ></span><span class="sxs-lookup"><span data-stu-id="78eaa-107">\<table></span></span>  
<span data-ttu-id="78eaa-108">\<записи ></span><span class="sxs-lookup"><span data-stu-id="78eaa-108">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78eaa-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78eaa-109">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="78eaa-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="78eaa-110">Attributes and Elements</span></span>  
 <span data-ttu-id="78eaa-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="78eaa-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78eaa-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="78eaa-112">Attributes</span></span>  
 <span data-ttu-id="78eaa-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="78eaa-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="78eaa-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="78eaa-114">Child Elements</span></span>  
  
|<span data-ttu-id="78eaa-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="78eaa-115">Element</span></span>|<span data-ttu-id="78eaa-116">Описание</span><span class="sxs-lookup"><span data-stu-id="78eaa-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78eaa-117">\<Фильтры ></span><span class="sxs-lookup"><span data-stu-id="78eaa-117">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="78eaa-118">Сопоставляет фильтр с ранее определенной конечной точкой клиента.</span><span class="sxs-lookup"><span data-stu-id="78eaa-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="78eaa-119">Сообщения, соответствующие этому фильтру, будут отправлены по данному назначению.</span><span class="sxs-lookup"><span data-stu-id="78eaa-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="78eaa-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="78eaa-120">Parent Elements</span></span>  
  
|<span data-ttu-id="78eaa-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="78eaa-121">Element</span></span>|<span data-ttu-id="78eaa-122">Описание</span><span class="sxs-lookup"><span data-stu-id="78eaa-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78eaa-123">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="78eaa-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="78eaa-124">Раздел конфигурации, содержащий таблицу маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="78eaa-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78eaa-125">См. также</span><span class="sxs-lookup"><span data-stu-id="78eaa-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>    
