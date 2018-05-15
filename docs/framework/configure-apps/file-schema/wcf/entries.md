---
title: '&lt;Записи&gt;'
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: b9cc7f7736ffefaca68a0f197bd064a99c4dca9a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltentriesgt"></a><span data-ttu-id="726fa-102">&lt;Записи&gt;</span><span class="sxs-lookup"><span data-stu-id="726fa-102">&lt;entries&gt;</span></span>
<span data-ttu-id="726fa-103">Запись маршрутизации, содержащая сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="726fa-103">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="726fa-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="726fa-104">\<system.serviceModel></span></span>  
<span data-ttu-id="726fa-105">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="726fa-105">\<routing></span></span>  
<span data-ttu-id="726fa-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="726fa-106">\<routingTables></span></span>  
<span data-ttu-id="726fa-107">\<Таблица ></span><span class="sxs-lookup"><span data-stu-id="726fa-107">\<table></span></span>  
<span data-ttu-id="726fa-108">\<записи ></span><span class="sxs-lookup"><span data-stu-id="726fa-108">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="726fa-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="726fa-109">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="726fa-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="726fa-110">Attributes and Elements</span></span>  
 <span data-ttu-id="726fa-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="726fa-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="726fa-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="726fa-112">Attributes</span></span>  
 <span data-ttu-id="726fa-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="726fa-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="726fa-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="726fa-114">Child Elements</span></span>  
  
|<span data-ttu-id="726fa-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="726fa-115">Element</span></span>|<span data-ttu-id="726fa-116">Описание</span><span class="sxs-lookup"><span data-stu-id="726fa-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="726fa-117">\<Фильтры ></span><span class="sxs-lookup"><span data-stu-id="726fa-117">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="726fa-118">Сопоставляет фильтр с ранее определенной конечной точкой клиента.</span><span class="sxs-lookup"><span data-stu-id="726fa-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="726fa-119">Сообщения, соответствующие этому фильтру, будут отправлены по данному назначению.</span><span class="sxs-lookup"><span data-stu-id="726fa-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="726fa-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="726fa-120">Parent Elements</span></span>  
  
|<span data-ttu-id="726fa-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="726fa-121">Element</span></span>|<span data-ttu-id="726fa-122">Описание</span><span class="sxs-lookup"><span data-stu-id="726fa-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="726fa-123">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="726fa-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="726fa-124">Раздел конфигурации, содержащий таблицу маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="726fa-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="726fa-125">См. также</span><span class="sxs-lookup"><span data-stu-id="726fa-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>    
