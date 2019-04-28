---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: 5561cf61cef2258ec61bd32770538add1c69f5c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704210"
---
# <a name="entries"></a><span data-ttu-id="e3318-101">\<записи ></span><span class="sxs-lookup"><span data-stu-id="e3318-101">\<entries></span></span>
<span data-ttu-id="e3318-102">Запись маршрутизации, содержащая сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="e3318-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="e3318-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e3318-103">\<system.serviceModel></span></span>  
<span data-ttu-id="e3318-104">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="e3318-104">\<routing></span></span>  
<span data-ttu-id="e3318-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="e3318-105">\<routingTables></span></span>  
<span data-ttu-id="e3318-106">\<Таблица ></span><span class="sxs-lookup"><span data-stu-id="e3318-106">\<table></span></span>  
<span data-ttu-id="e3318-107">\<записи ></span><span class="sxs-lookup"><span data-stu-id="e3318-107">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3318-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3318-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3318-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e3318-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e3318-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e3318-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3318-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e3318-111">Attributes</span></span>  
 <span data-ttu-id="e3318-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e3318-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e3318-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e3318-113">Child Elements</span></span>  
  
|<span data-ttu-id="e3318-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="e3318-114">Element</span></span>|<span data-ttu-id="e3318-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e3318-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3318-116">\<Фильтры></span><span class="sxs-lookup"><span data-stu-id="e3318-116">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="e3318-117">Сопоставляет фильтр с ранее определенной конечной точкой клиента.</span><span class="sxs-lookup"><span data-stu-id="e3318-117">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="e3318-118">Сообщения, соответствующие этому фильтру, будут отправлены по данному назначению.</span><span class="sxs-lookup"><span data-stu-id="e3318-118">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e3318-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e3318-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e3318-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="e3318-120">Element</span></span>|<span data-ttu-id="e3318-121">Описание</span><span class="sxs-lookup"><span data-stu-id="e3318-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3318-122">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="e3318-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="e3318-123">Раздел конфигурации, содержащий таблицу маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="e3318-123">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3318-124">См. также</span><span class="sxs-lookup"><span data-stu-id="e3318-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
