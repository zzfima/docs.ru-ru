---
title: '&lt;filterTable&gt;'
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: f790e294b832f43a595d0636c60a8a67da5ad56a
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147893"
---
# <a name="ltfiltertablegt"></a><span data-ttu-id="8c5d8-102">&lt;filterTable&gt;</span><span class="sxs-lookup"><span data-stu-id="8c5d8-102">&lt;filterTable&gt;</span></span>
<span data-ttu-id="8c5d8-103">Представляет таблицу маршрутизации, которая содержит список фильтров для оценки сообщения, а конечная точка клиента для перенаправления сообщений, если фильтр возвращает значение true.</span><span class="sxs-lookup"><span data-stu-id="8c5d8-103">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="8c5d8-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8c5d8-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8c5d8-105">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="8c5d8-105">\<routing></span></span>  
<span data-ttu-id="8c5d8-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="8c5d8-106">\<routingTables></span></span>  
<span data-ttu-id="8c5d8-107">\<Таблица ></span><span class="sxs-lookup"><span data-stu-id="8c5d8-107">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c5d8-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c5d8-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c5d8-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8c5d8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8c5d8-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8c5d8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c5d8-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8c5d8-111">Attributes</span></span>  
  
|<span data-ttu-id="8c5d8-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="8c5d8-112">Element</span></span>|<span data-ttu-id="8c5d8-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8c5d8-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8c5d8-114">имя</span><span class="sxs-lookup"><span data-stu-id="8c5d8-114">name</span></span>|<span data-ttu-id="8c5d8-115">Строка, содержащая уникальное имя этого элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8c5d8-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c5d8-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8c5d8-116">Child Elements</span></span>  
  
|<span data-ttu-id="8c5d8-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="8c5d8-117">Element</span></span>|<span data-ttu-id="8c5d8-118">Описание</span><span class="sxs-lookup"><span data-stu-id="8c5d8-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c5d8-119">\<Фильтры></span><span class="sxs-lookup"><span data-stu-id="8c5d8-119">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="8c5d8-120">Сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="8c5d8-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c5d8-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8c5d8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8c5d8-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="8c5d8-122">Element</span></span>|<span data-ttu-id="8c5d8-123">Описание</span><span class="sxs-lookup"><span data-stu-id="8c5d8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c5d8-124">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="8c5d8-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="8c5d8-125">Раздел конфигурации, содержащий таблицы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="8c5d8-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8c5d8-126">См. также</span><span class="sxs-lookup"><span data-stu-id="8c5d8-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>    
