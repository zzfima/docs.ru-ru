---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: b0a344aa69085d50087eefc746236bc8ceacadaa
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918860"
---
# <a name="filtertables"></a><span data-ttu-id="3a011-101">\<Филтертаблес ></span><span class="sxs-lookup"><span data-stu-id="3a011-101">\<filterTables></span></span>
<span data-ttu-id="3a011-102">Представляет раздел конфигурации, в котором определены таблицы маршрутизации, содержащие сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при совпадении с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="3a011-102">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="3a011-103">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="3a011-103">\<system.serviceModel></span></span>  
<span data-ttu-id="3a011-104">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="3a011-104">\<routing></span></span>  
<span data-ttu-id="3a011-105">\<Раутингтаблес ></span><span class="sxs-lookup"><span data-stu-id="3a011-105">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a011-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a011-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a011-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3a011-107">Attributes and Elements</span></span>  
 <span data-ttu-id="3a011-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3a011-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a011-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3a011-109">Attributes</span></span>  
 <span data-ttu-id="3a011-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="3a011-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3a011-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3a011-111">Child Elements</span></span>  
  
|<span data-ttu-id="3a011-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="3a011-112">Element</span></span>|<span data-ttu-id="3a011-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3a011-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a011-114">\<Фильтры></span><span class="sxs-lookup"><span data-stu-id="3a011-114">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="3a011-115">Таблица маршрутизации, содержащая сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="3a011-115">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3a011-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3a011-116">Parent Elements</span></span>  
  
|<span data-ttu-id="3a011-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="3a011-117">Element</span></span>|<span data-ttu-id="3a011-118">Описание</span><span class="sxs-lookup"><span data-stu-id="3a011-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a011-119">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="3a011-119">\<routing></span></span>](routing.md)|<span data-ttu-id="3a011-120">Раздел конфигурации, содержащий фильтры и таблицы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="3a011-120">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a011-121">См. также</span><span class="sxs-lookup"><span data-stu-id="3a011-121">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
