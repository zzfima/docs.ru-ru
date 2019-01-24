---
title: '&lt;Записи&gt;'
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: 33f98cb4b138307622a14463ce5a3008058b6e31
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587064"
---
# <a name="ltentriesgt"></a><span data-ttu-id="9fc8d-102">&lt;Записи&gt;</span><span class="sxs-lookup"><span data-stu-id="9fc8d-102">&lt;entries&gt;</span></span>
<span data-ttu-id="9fc8d-103">Запись маршрутизации, содержащая сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="9fc8d-103">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="9fc8d-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9fc8d-104">\<system.serviceModel></span></span>  
<span data-ttu-id="9fc8d-105">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="9fc8d-105">\<routing></span></span>  
<span data-ttu-id="9fc8d-106">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="9fc8d-106">\<routingTables></span></span>  
<span data-ttu-id="9fc8d-107">\<Таблица ></span><span class="sxs-lookup"><span data-stu-id="9fc8d-107">\<table></span></span>  
<span data-ttu-id="9fc8d-108">\<записи ></span><span class="sxs-lookup"><span data-stu-id="9fc8d-108">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fc8d-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9fc8d-109">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9fc8d-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9fc8d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9fc8d-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9fc8d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9fc8d-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9fc8d-112">Attributes</span></span>  
 <span data-ttu-id="9fc8d-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9fc8d-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9fc8d-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9fc8d-114">Child Elements</span></span>  
  
|<span data-ttu-id="9fc8d-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="9fc8d-115">Element</span></span>|<span data-ttu-id="9fc8d-116">Описание</span><span class="sxs-lookup"><span data-stu-id="9fc8d-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9fc8d-117">\<Фильтры></span><span class="sxs-lookup"><span data-stu-id="9fc8d-117">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="9fc8d-118">Сопоставляет фильтр с ранее определенной конечной точкой клиента.</span><span class="sxs-lookup"><span data-stu-id="9fc8d-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="9fc8d-119">Сообщения, соответствующие этому фильтру, будут отправлены по данному назначению.</span><span class="sxs-lookup"><span data-stu-id="9fc8d-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9fc8d-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9fc8d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9fc8d-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="9fc8d-121">Element</span></span>|<span data-ttu-id="9fc8d-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="9fc8d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9fc8d-123">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="9fc8d-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="9fc8d-124">Раздел конфигурации, содержащий таблицу маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="9fc8d-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9fc8d-125">См. также</span><span class="sxs-lookup"><span data-stu-id="9fc8d-125">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
