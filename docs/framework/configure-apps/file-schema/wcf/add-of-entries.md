---
title: <add> из <entries>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 23b0a825ea593f85ade870d5b93367571eaa3ec0
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850509"
---
# <a name="add-of-entries"></a><span data-ttu-id="820f4-102">\<Добавление > \<записей ></span><span class="sxs-lookup"><span data-stu-id="820f4-102">\<add> of \<entries></span></span>
<span data-ttu-id="820f4-103">Представляет запись маршрутизации, которая сопоставляет фильтр с ранее определенной конечной точкой клиента.</span><span class="sxs-lookup"><span data-stu-id="820f4-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="820f4-104">Сообщения, соответствующие этому фильтру, будут отправлены по данному назначению.</span><span class="sxs-lookup"><span data-stu-id="820f4-104">Messages matching this filter will be sent to this destination.</span></span>  
  
<span data-ttu-id="820f4-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="820f4-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="820f4-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="820f4-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="820f4-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> маршрутизации**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="820f4-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="820f4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Филтертаблес >** ](filtertables.md)</span><span class="sxs-lookup"><span data-stu-id="820f4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)</span></span>\
<span data-ttu-id="820f4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Филтертабле >** ](filtertable.md)</span><span class="sxs-lookup"><span data-stu-id="820f4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)</span></span>\
<span data-ttu-id="820f4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> записей**](entries.md)</span><span class="sxs-lookup"><span data-stu-id="820f4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<entries>**](entries.md)</span></span>\
<span data-ttu-id="820f4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="820f4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="820f4-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="820f4-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="820f4-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="820f4-113">Attributes and Elements</span></span>  
 <span data-ttu-id="820f4-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="820f4-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="820f4-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="820f4-115">Attributes</span></span>  
  
|<span data-ttu-id="820f4-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="820f4-116">Attribute</span></span>|<span data-ttu-id="820f4-117">Описание</span><span class="sxs-lookup"><span data-stu-id="820f4-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="820f4-118">backupList</span><span class="sxs-lookup"><span data-stu-id="820f4-118">backupList</span></span>|<span data-ttu-id="820f4-119">Строка, указывающая ссылку на резервный список конечных точек.</span><span class="sxs-lookup"><span data-stu-id="820f4-119">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="820f4-120">конечная точка</span><span class="sxs-lookup"><span data-stu-id="820f4-120">endpoint</span></span>|<span data-ttu-id="820f4-121">Строка, в которой указана ссылка на конечную точку клиента, получающую сообщения, которые соответствуют критериям фильтра, указанного в атрибуте `filterName`.</span><span class="sxs-lookup"><span data-stu-id="820f4-121">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="820f4-122">filterName</span><span class="sxs-lookup"><span data-stu-id="820f4-122">filterName</span></span>|<span data-ttu-id="820f4-123">Строка, в которой указана ссылка на элемент фильтра.</span><span class="sxs-lookup"><span data-stu-id="820f4-123">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="820f4-124">priority</span><span class="sxs-lookup"><span data-stu-id="820f4-124">priority</span></span>|<span data-ttu-id="820f4-125">Целое число, задающее приоритет этой записи.</span><span class="sxs-lookup"><span data-stu-id="820f4-125">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="820f4-126">Записи в таблице маршрутизации обрабатываются исходя из приоритета, причем 0 является самым низким приоритетом.</span><span class="sxs-lookup"><span data-stu-id="820f4-126">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="820f4-127">Все записи определенного приоритета обрабатываются одновременно, и, если для текущего приоритета не находится совпадающая запись, вычисляется следующий уровень приоритета.</span><span class="sxs-lookup"><span data-stu-id="820f4-127">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="820f4-128">Это значение является необязательным.</span><span class="sxs-lookup"><span data-stu-id="820f4-128">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="820f4-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="820f4-129">Child Elements</span></span>  
 <span data-ttu-id="820f4-130">Нет.</span><span class="sxs-lookup"><span data-stu-id="820f4-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="820f4-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="820f4-131">Parent Elements</span></span>  
  
|<span data-ttu-id="820f4-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="820f4-132">Element</span></span>|<span data-ttu-id="820f4-133">Описание</span><span class="sxs-lookup"><span data-stu-id="820f4-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="820f4-134">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="820f4-134">\<routing></span></span>](routing.md)|<span data-ttu-id="820f4-135">Раздел конфигурации, в котором содержатся записи сопоставления маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="820f4-135">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="820f4-136">См. также</span><span class="sxs-lookup"><span data-stu-id="820f4-136">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
