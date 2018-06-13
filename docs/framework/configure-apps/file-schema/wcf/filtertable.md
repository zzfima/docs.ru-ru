---
title: '&lt;filterTable&gt;'
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 7bdc76ba7a8e2927b93fa0207f48cc569279482f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747415"
---
# <a name="ltfiltertablegt"></a><span data-ttu-id="ee118-102">&lt;filterTable&gt;</span><span class="sxs-lookup"><span data-stu-id="ee118-102">&lt;filterTable&gt;</span></span>
<span data-ttu-id="ee118-103">Представляет таблицу маршрутизации, содержащую список фильтров для оценки сообщения, а конечная точка клиента для перенаправления сообщений, если фильтр имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="ee118-103">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="ee118-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="ee118-104">\<system.serviceModel></span></span>  
<span data-ttu-id="ee118-105">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="ee118-105">\<routing></span></span>  
<span data-ttu-id="ee118-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="ee118-106">\<routingTables></span></span>  
<span data-ttu-id="ee118-107">\<Таблица ></span><span class="sxs-lookup"><span data-stu-id="ee118-107">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee118-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ee118-108">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ee118-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ee118-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ee118-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ee118-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee118-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ee118-111">Attributes</span></span>  
  
|<span data-ttu-id="ee118-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="ee118-112">Element</span></span>|<span data-ttu-id="ee118-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ee118-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ee118-114">имя</span><span class="sxs-lookup"><span data-stu-id="ee118-114">name</span></span>|<span data-ttu-id="ee118-115">Строка, содержащая уникальное имя этого элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ee118-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee118-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ee118-116">Child Elements</span></span>  
  
|<span data-ttu-id="ee118-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="ee118-117">Element</span></span>|<span data-ttu-id="ee118-118">Описание</span><span class="sxs-lookup"><span data-stu-id="ee118-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ee118-119">\<Фильтры ></span><span class="sxs-lookup"><span data-stu-id="ee118-119">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="ee118-120">Сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="ee118-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ee118-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ee118-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ee118-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="ee118-122">Element</span></span>|<span data-ttu-id="ee118-123">Описание</span><span class="sxs-lookup"><span data-stu-id="ee118-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ee118-124">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="ee118-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="ee118-125">Раздел конфигурации, содержащий таблицы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="ee118-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee118-126">См. также</span><span class="sxs-lookup"><span data-stu-id="ee118-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>    
