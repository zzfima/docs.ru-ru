---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: 610ba29ec98f4b1f2a9b1db3542bcb3aefb46457
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925653"
---
# <a name="entries"></a><span data-ttu-id="a98a2-101">\<> записей</span><span class="sxs-lookup"><span data-stu-id="a98a2-101">\<entries></span></span>
<span data-ttu-id="a98a2-102">Запись маршрутизации, содержащая сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="a98a2-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="a98a2-103">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="a98a2-103">\<system.serviceModel></span></span>  
<span data-ttu-id="a98a2-104">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="a98a2-104">\<routing></span></span>  
<span data-ttu-id="a98a2-105">\<Раутингтаблес ></span><span class="sxs-lookup"><span data-stu-id="a98a2-105">\<routingTables></span></span>  
<span data-ttu-id="a98a2-106">\<Таблица ></span><span class="sxs-lookup"><span data-stu-id="a98a2-106">\<table></span></span>  
<span data-ttu-id="a98a2-107">\<> записей</span><span class="sxs-lookup"><span data-stu-id="a98a2-107">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a98a2-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a98a2-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a98a2-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a98a2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a98a2-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a98a2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a98a2-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a98a2-111">Attributes</span></span>  
 <span data-ttu-id="a98a2-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="a98a2-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a98a2-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a98a2-113">Child Elements</span></span>  
  
|<span data-ttu-id="a98a2-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="a98a2-114">Element</span></span>|<span data-ttu-id="a98a2-115">Описание</span><span class="sxs-lookup"><span data-stu-id="a98a2-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a98a2-116">\<Фильтры></span><span class="sxs-lookup"><span data-stu-id="a98a2-116">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="a98a2-117">Сопоставляет фильтр с ранее определенной конечной точкой клиента.</span><span class="sxs-lookup"><span data-stu-id="a98a2-117">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="a98a2-118">Сообщения, соответствующие этому фильтру, будут отправлены по данному назначению.</span><span class="sxs-lookup"><span data-stu-id="a98a2-118">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a98a2-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a98a2-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a98a2-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="a98a2-120">Element</span></span>|<span data-ttu-id="a98a2-121">Описание</span><span class="sxs-lookup"><span data-stu-id="a98a2-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a98a2-122">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="a98a2-122">\<routing></span></span>](routing.md)|<span data-ttu-id="a98a2-123">Раздел конфигурации, содержащий таблицу маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="a98a2-123">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a98a2-124">См. также</span><span class="sxs-lookup"><span data-stu-id="a98a2-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
