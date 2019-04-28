---
title: <add> из <entries>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 1324803d7c0f127cfee9eadebff2672955780eda
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673645"
---
# <a name="add-of-entries"></a><span data-ttu-id="67183-102">\<Добавить > из \<записи ></span><span class="sxs-lookup"><span data-stu-id="67183-102">\<add> of \<entries></span></span>
<span data-ttu-id="67183-103">Представляет запись маршрутизации, которая сопоставляет фильтр с ранее определенной конечной точкой клиента.</span><span class="sxs-lookup"><span data-stu-id="67183-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="67183-104">Сообщения, соответствующие этому фильтру, будут отправлены по данному назначению.</span><span class="sxs-lookup"><span data-stu-id="67183-104">Messages matching this filter will be sent to this destination.</span></span>  
  
 <span data-ttu-id="67183-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="67183-105">\<system.serviceModel></span></span>  
<span data-ttu-id="67183-106">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="67183-106">\<routing></span></span>  
<span data-ttu-id="67183-107">\<filterTables ></span><span class="sxs-lookup"><span data-stu-id="67183-107">\<filterTables></span></span>  
<span data-ttu-id="67183-108">\<filterTable ></span><span class="sxs-lookup"><span data-stu-id="67183-108">\<filterTable></span></span>  
<span data-ttu-id="67183-109">\<записи ></span><span class="sxs-lookup"><span data-stu-id="67183-109">\<entries></span></span>  
<span data-ttu-id="67183-110">\<add></span><span class="sxs-lookup"><span data-stu-id="67183-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67183-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67183-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67183-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="67183-112">Attributes and Elements</span></span>  
 <span data-ttu-id="67183-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="67183-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67183-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="67183-114">Attributes</span></span>  
  
|<span data-ttu-id="67183-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="67183-115">Attribute</span></span>|<span data-ttu-id="67183-116">Описание</span><span class="sxs-lookup"><span data-stu-id="67183-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="67183-117">backupList</span><span class="sxs-lookup"><span data-stu-id="67183-117">backupList</span></span>|<span data-ttu-id="67183-118">Строка, указывающая ссылку на резервный список конечных точек.</span><span class="sxs-lookup"><span data-stu-id="67183-118">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="67183-119">конечная точка</span><span class="sxs-lookup"><span data-stu-id="67183-119">endpoint</span></span>|<span data-ttu-id="67183-120">Строка, в которой указана ссылка на конечную точку клиента, получающую сообщения, которые соответствуют критериям фильтра, указанного в атрибуте `filterName`.</span><span class="sxs-lookup"><span data-stu-id="67183-120">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="67183-121">filterName</span><span class="sxs-lookup"><span data-stu-id="67183-121">filterName</span></span>|<span data-ttu-id="67183-122">Строка, в которой указана ссылка на элемент фильтра.</span><span class="sxs-lookup"><span data-stu-id="67183-122">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="67183-123">priority</span><span class="sxs-lookup"><span data-stu-id="67183-123">priority</span></span>|<span data-ttu-id="67183-124">Целое число, задающее приоритет этой записи.</span><span class="sxs-lookup"><span data-stu-id="67183-124">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="67183-125">Записи в таблице маршрутизации обрабатываются исходя из приоритета, причем 0 является самым низким приоритетом.</span><span class="sxs-lookup"><span data-stu-id="67183-125">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="67183-126">Все записи определенного приоритета обрабатываются одновременно, и, если для текущего приоритета не находится совпадающая запись, вычисляется следующий уровень приоритета.</span><span class="sxs-lookup"><span data-stu-id="67183-126">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="67183-127">Это значение является необязательным.</span><span class="sxs-lookup"><span data-stu-id="67183-127">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="67183-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="67183-128">Child Elements</span></span>  
 <span data-ttu-id="67183-129">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="67183-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="67183-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="67183-130">Parent Elements</span></span>  
  
|<span data-ttu-id="67183-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="67183-131">Element</span></span>|<span data-ttu-id="67183-132">Описание</span><span class="sxs-lookup"><span data-stu-id="67183-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67183-133">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="67183-133">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="67183-134">Раздел конфигурации, в котором содержатся записи сопоставления маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="67183-134">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="67183-135">См. также</span><span class="sxs-lookup"><span data-stu-id="67183-135">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
