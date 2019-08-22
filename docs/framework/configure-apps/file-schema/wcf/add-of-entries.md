---
title: <add> из <entries>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 3052a7570d1d93836603454817be921b37d26060
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658828"
---
# <a name="add-of-entries"></a><span data-ttu-id="22e41-102">\<Добавление > \<записей ></span><span class="sxs-lookup"><span data-stu-id="22e41-102">\<add> of \<entries></span></span>
<span data-ttu-id="22e41-103">Представляет запись маршрутизации, которая сопоставляет фильтр с ранее определенной конечной точкой клиента.</span><span class="sxs-lookup"><span data-stu-id="22e41-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="22e41-104">Сообщения, соответствующие этому фильтру, будут отправлены по данному назначению.</span><span class="sxs-lookup"><span data-stu-id="22e41-104">Messages matching this filter will be sent to this destination.</span></span>  
  
 <span data-ttu-id="22e41-105">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="22e41-105">\<system.serviceModel></span></span>  
<span data-ttu-id="22e41-106">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="22e41-106">\<routing></span></span>  
<span data-ttu-id="22e41-107">\<Филтертаблес ></span><span class="sxs-lookup"><span data-stu-id="22e41-107">\<filterTables></span></span>  
<span data-ttu-id="22e41-108">\<Филтертабле ></span><span class="sxs-lookup"><span data-stu-id="22e41-108">\<filterTable></span></span>  
<span data-ttu-id="22e41-109">\<> записей</span><span class="sxs-lookup"><span data-stu-id="22e41-109">\<entries></span></span>  
<span data-ttu-id="22e41-110">\<add></span><span class="sxs-lookup"><span data-stu-id="22e41-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22e41-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22e41-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22e41-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="22e41-112">Attributes and Elements</span></span>  
 <span data-ttu-id="22e41-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="22e41-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22e41-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="22e41-114">Attributes</span></span>  
  
|<span data-ttu-id="22e41-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="22e41-115">Attribute</span></span>|<span data-ttu-id="22e41-116">Описание</span><span class="sxs-lookup"><span data-stu-id="22e41-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="22e41-117">backupList</span><span class="sxs-lookup"><span data-stu-id="22e41-117">backupList</span></span>|<span data-ttu-id="22e41-118">Строка, указывающая ссылку на резервный список конечных точек.</span><span class="sxs-lookup"><span data-stu-id="22e41-118">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="22e41-119">конечная точка</span><span class="sxs-lookup"><span data-stu-id="22e41-119">endpoint</span></span>|<span data-ttu-id="22e41-120">Строка, в которой указана ссылка на конечную точку клиента, получающую сообщения, которые соответствуют критериям фильтра, указанного в атрибуте `filterName`.</span><span class="sxs-lookup"><span data-stu-id="22e41-120">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="22e41-121">filterName</span><span class="sxs-lookup"><span data-stu-id="22e41-121">filterName</span></span>|<span data-ttu-id="22e41-122">Строка, в которой указана ссылка на элемент фильтра.</span><span class="sxs-lookup"><span data-stu-id="22e41-122">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="22e41-123">priority</span><span class="sxs-lookup"><span data-stu-id="22e41-123">priority</span></span>|<span data-ttu-id="22e41-124">Целое число, задающее приоритет этой записи.</span><span class="sxs-lookup"><span data-stu-id="22e41-124">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="22e41-125">Записи в таблице маршрутизации обрабатываются исходя из приоритета, причем 0 является самым низким приоритетом.</span><span class="sxs-lookup"><span data-stu-id="22e41-125">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="22e41-126">Все записи определенного приоритета обрабатываются одновременно, и, если для текущего приоритета не находится совпадающая запись, вычисляется следующий уровень приоритета.</span><span class="sxs-lookup"><span data-stu-id="22e41-126">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="22e41-127">Это значение является необязательным.</span><span class="sxs-lookup"><span data-stu-id="22e41-127">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22e41-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="22e41-128">Child Elements</span></span>  
 <span data-ttu-id="22e41-129">Нет.</span><span class="sxs-lookup"><span data-stu-id="22e41-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22e41-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="22e41-130">Parent Elements</span></span>  
  
|<span data-ttu-id="22e41-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="22e41-131">Element</span></span>|<span data-ttu-id="22e41-132">Описание</span><span class="sxs-lookup"><span data-stu-id="22e41-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22e41-133">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="22e41-133">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="22e41-134">Раздел конфигурации, в котором содержатся записи сопоставления маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="22e41-134">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="22e41-135">См. также</span><span class="sxs-lookup"><span data-stu-id="22e41-135">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
