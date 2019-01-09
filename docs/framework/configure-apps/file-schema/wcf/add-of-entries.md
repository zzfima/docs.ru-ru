---
title: '&lt;add&gt; для &lt;entries&gt;'
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 5a61aefd92390eefb95d1f3e39236e53fa264990
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151509"
---
# <a name="ltaddgt-of-ltentriesgt"></a><span data-ttu-id="cca15-102">&lt;add&gt; для &lt;entries&gt;</span><span class="sxs-lookup"><span data-stu-id="cca15-102">&lt;add&gt; of &lt;entries&gt;</span></span>
<span data-ttu-id="cca15-103">Представляет запись маршрутизации, которая сопоставляет фильтр с ранее определенной конечной точкой клиента.</span><span class="sxs-lookup"><span data-stu-id="cca15-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="cca15-104">Сообщения, соответствующие этому фильтру, будут отправлены по данному назначению.</span><span class="sxs-lookup"><span data-stu-id="cca15-104">Messages matching this filter will be sent to this destination.</span></span>  
  
 <span data-ttu-id="cca15-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="cca15-105">\<system.serviceModel></span></span>  
<span data-ttu-id="cca15-106">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="cca15-106">\<routing></span></span>  
<span data-ttu-id="cca15-107">\<filterTables ></span><span class="sxs-lookup"><span data-stu-id="cca15-107">\<filterTables></span></span>  
<span data-ttu-id="cca15-108">\<filterTable ></span><span class="sxs-lookup"><span data-stu-id="cca15-108">\<filterTable></span></span>  
<span data-ttu-id="cca15-109">\<записи ></span><span class="sxs-lookup"><span data-stu-id="cca15-109">\<entries></span></span>  
<span data-ttu-id="cca15-110">\<add></span><span class="sxs-lookup"><span data-stu-id="cca15-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cca15-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cca15-111">Syntax</span></span>  
  
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
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cca15-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cca15-112">Attributes and Elements</span></span>  
 <span data-ttu-id="cca15-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cca15-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cca15-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cca15-114">Attributes</span></span>  
  
|<span data-ttu-id="cca15-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cca15-115">Attribute</span></span>|<span data-ttu-id="cca15-116">Описание</span><span class="sxs-lookup"><span data-stu-id="cca15-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cca15-117">backupList</span><span class="sxs-lookup"><span data-stu-id="cca15-117">backupList</span></span>|<span data-ttu-id="cca15-118">Строка, указывающая ссылку на резервный список конечных точек.</span><span class="sxs-lookup"><span data-stu-id="cca15-118">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="cca15-119">конечная точка</span><span class="sxs-lookup"><span data-stu-id="cca15-119">endpoint</span></span>|<span data-ttu-id="cca15-120">Строка, в которой указана ссылка на конечную точку клиента, получающую сообщения, которые соответствуют критериям фильтра, указанного в атрибуте `filterName`.</span><span class="sxs-lookup"><span data-stu-id="cca15-120">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="cca15-121">filterName</span><span class="sxs-lookup"><span data-stu-id="cca15-121">filterName</span></span>|<span data-ttu-id="cca15-122">Строка, в которой указана ссылка на элемент фильтра.</span><span class="sxs-lookup"><span data-stu-id="cca15-122">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="cca15-123">priority</span><span class="sxs-lookup"><span data-stu-id="cca15-123">priority</span></span>|<span data-ttu-id="cca15-124">Целое число, задающее приоритет этой записи.</span><span class="sxs-lookup"><span data-stu-id="cca15-124">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="cca15-125">Записи в таблице маршрутизации обрабатываются исходя из приоритета, причем 0 является самым низким приоритетом.</span><span class="sxs-lookup"><span data-stu-id="cca15-125">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="cca15-126">Все записи определенного приоритета обрабатываются одновременно, и, если для текущего приоритета не находится совпадающая запись, вычисляется следующий уровень приоритета.</span><span class="sxs-lookup"><span data-stu-id="cca15-126">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="cca15-127">Это значение является необязательным.</span><span class="sxs-lookup"><span data-stu-id="cca15-127">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cca15-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cca15-128">Child Elements</span></span>  
 <span data-ttu-id="cca15-129">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cca15-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cca15-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cca15-130">Parent Elements</span></span>  
  
|<span data-ttu-id="cca15-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="cca15-131">Element</span></span>|<span data-ttu-id="cca15-132">Описание</span><span class="sxs-lookup"><span data-stu-id="cca15-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cca15-133">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="cca15-133">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="cca15-134">Раздел конфигурации, в котором содержатся записи сопоставления маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="cca15-134">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cca15-135">См. также</span><span class="sxs-lookup"><span data-stu-id="cca15-135">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType> 
