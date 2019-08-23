---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: f9e64e667befb70d617574b2a03c3e6bebb2a143
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925605"
---
# <a name="filtertable"></a><span data-ttu-id="6a026-101">\<Филтертабле ></span><span class="sxs-lookup"><span data-stu-id="6a026-101">\<filterTable></span></span>
<span data-ttu-id="6a026-102">Представляет таблицу маршрутизации, содержащую список фильтров для вычисления сообщений и конечную точку клиента для маршрутизации сообщений, если фильтр имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="6a026-102">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="6a026-103">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="6a026-103">\<system.serviceModel></span></span>  
<span data-ttu-id="6a026-104">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="6a026-104">\<routing></span></span>  
<span data-ttu-id="6a026-105">\<Раутингтаблес ></span><span class="sxs-lookup"><span data-stu-id="6a026-105">\<routingTables></span></span>  
<span data-ttu-id="6a026-106">\<Таблица ></span><span class="sxs-lookup"><span data-stu-id="6a026-106">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a026-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a026-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a026-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6a026-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6a026-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6a026-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a026-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6a026-110">Attributes</span></span>  
  
|<span data-ttu-id="6a026-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="6a026-111">Element</span></span>|<span data-ttu-id="6a026-112">Описание</span><span class="sxs-lookup"><span data-stu-id="6a026-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6a026-113">имя</span><span class="sxs-lookup"><span data-stu-id="6a026-113">name</span></span>|<span data-ttu-id="6a026-114">Строка, содержащая уникальное имя этого элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6a026-114">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6a026-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6a026-115">Child Elements</span></span>  
  
|<span data-ttu-id="6a026-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="6a026-116">Element</span></span>|<span data-ttu-id="6a026-117">Описание</span><span class="sxs-lookup"><span data-stu-id="6a026-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a026-118">\<Фильтры></span><span class="sxs-lookup"><span data-stu-id="6a026-118">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="6a026-119">Сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="6a026-119">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6a026-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6a026-120">Parent Elements</span></span>  
  
|<span data-ttu-id="6a026-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="6a026-121">Element</span></span>|<span data-ttu-id="6a026-122">Описание</span><span class="sxs-lookup"><span data-stu-id="6a026-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a026-123">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="6a026-123">\<routing></span></span>](routing.md)|<span data-ttu-id="6a026-124">Раздел конфигурации, содержащий таблицы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="6a026-124">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6a026-125">См. также</span><span class="sxs-lookup"><span data-stu-id="6a026-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
