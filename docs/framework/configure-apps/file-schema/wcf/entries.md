---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: ffe2538fa2c3cb680285cfaa68c975c0f9d4b1bd
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855276"
---
# <a name="entries"></a><span data-ttu-id="12706-101">\<> записей</span><span class="sxs-lookup"><span data-stu-id="12706-101">\<entries></span></span>
<span data-ttu-id="12706-102">Запись маршрутизации, содержащая сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="12706-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
<span data-ttu-id="12706-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="12706-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="12706-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="12706-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="12706-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> маршрутизации**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="12706-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="12706-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Филтертаблес >** ](filtertables.md)</span><span class="sxs-lookup"><span data-stu-id="12706-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)</span></span>\
<span data-ttu-id="12706-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Филтертабле >** ](filtertable.md)</span><span class="sxs-lookup"><span data-stu-id="12706-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)</span></span>\
<span data-ttu-id="12706-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> записей**</span><span class="sxs-lookup"><span data-stu-id="12706-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<entries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12706-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12706-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12706-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="12706-110">Attributes and Elements</span></span>  
 <span data-ttu-id="12706-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="12706-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12706-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="12706-112">Attributes</span></span>  
 <span data-ttu-id="12706-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="12706-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="12706-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="12706-114">Child Elements</span></span>  
  
|<span data-ttu-id="12706-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="12706-115">Element</span></span>|<span data-ttu-id="12706-116">Описание</span><span class="sxs-lookup"><span data-stu-id="12706-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12706-117">\<Фильтры></span><span class="sxs-lookup"><span data-stu-id="12706-117">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="12706-118">Сопоставляет фильтр с ранее определенной конечной точкой клиента.</span><span class="sxs-lookup"><span data-stu-id="12706-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="12706-119">Сообщения, соответствующие этому фильтру, будут отправлены по данному назначению.</span><span class="sxs-lookup"><span data-stu-id="12706-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="12706-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="12706-120">Parent Elements</span></span>  
  
|<span data-ttu-id="12706-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="12706-121">Element</span></span>|<span data-ttu-id="12706-122">Описание</span><span class="sxs-lookup"><span data-stu-id="12706-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12706-123">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="12706-123">\<routing></span></span>](routing.md)|<span data-ttu-id="12706-124">Раздел конфигурации, содержащий таблицу маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="12706-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="12706-125">См. также</span><span class="sxs-lookup"><span data-stu-id="12706-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
