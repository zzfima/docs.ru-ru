---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: ba65d3858cdbdf6b49c50e60f4e3cc9624fef136
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254409"
---
# <a name="filtertable"></a><span data-ttu-id="84001-101">\<filterTable ></span><span class="sxs-lookup"><span data-stu-id="84001-101">\<filterTable></span></span>
<span data-ttu-id="84001-102">Представляет таблицу маршрутизации, которая содержит список фильтров для оценки сообщения, а конечная точка клиента для перенаправления сообщений, если фильтр возвращает значение true.</span><span class="sxs-lookup"><span data-stu-id="84001-102">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="84001-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="84001-103">\<system.serviceModel></span></span>  
<span data-ttu-id="84001-104">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="84001-104">\<routing></span></span>  
<span data-ttu-id="84001-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="84001-105">\<routingTables></span></span>  
<span data-ttu-id="84001-106">\<Таблица ></span><span class="sxs-lookup"><span data-stu-id="84001-106">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84001-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84001-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84001-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="84001-108">Attributes and Elements</span></span>  
 <span data-ttu-id="84001-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="84001-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84001-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="84001-110">Attributes</span></span>  
  
|<span data-ttu-id="84001-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="84001-111">Element</span></span>|<span data-ttu-id="84001-112">Описание</span><span class="sxs-lookup"><span data-stu-id="84001-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="84001-113">имя</span><span class="sxs-lookup"><span data-stu-id="84001-113">name</span></span>|<span data-ttu-id="84001-114">Строка, содержащая уникальное имя этого элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="84001-114">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="84001-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="84001-115">Child Elements</span></span>  
  
|<span data-ttu-id="84001-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="84001-116">Element</span></span>|<span data-ttu-id="84001-117">Описание</span><span class="sxs-lookup"><span data-stu-id="84001-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="84001-118">\<Фильтры></span><span class="sxs-lookup"><span data-stu-id="84001-118">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="84001-119">Сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="84001-119">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="84001-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="84001-120">Parent Elements</span></span>  
  
|<span data-ttu-id="84001-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="84001-121">Element</span></span>|<span data-ttu-id="84001-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="84001-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="84001-123">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="84001-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="84001-124">Раздел конфигурации, содержащий таблицы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="84001-124">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="84001-125">См. также</span><span class="sxs-lookup"><span data-stu-id="84001-125">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
