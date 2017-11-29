---
title: '&lt;filterTable&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 04780d51cfd1d1d0049fc608cf7bd304be382b9b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltfiltertablegt"></a><span data-ttu-id="e1637-102">&lt;filterTable&gt;</span><span class="sxs-lookup"><span data-stu-id="e1637-102">&lt;filterTable&gt;</span></span>
<span data-ttu-id="e1637-103">Представляет таблицу маршрутизации, содержащую список фильтров для оценки сообщения, а конечная точка клиента для перенаправления сообщений, если фильтр имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="e1637-103">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="e1637-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="e1637-104">\<system.serviceModel></span></span>  
<span data-ttu-id="e1637-105">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="e1637-105">\<routing></span></span>  
<span data-ttu-id="e1637-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="e1637-106">\<routingTables></span></span>  
<span data-ttu-id="e1637-107">\<Таблица ></span><span class="sxs-lookup"><span data-stu-id="e1637-107">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1637-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1637-108">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e1637-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e1637-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e1637-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e1637-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1637-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e1637-111">Attributes</span></span>  
  
|<span data-ttu-id="e1637-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="e1637-112">Element</span></span>|<span data-ttu-id="e1637-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e1637-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e1637-114">имя</span><span class="sxs-lookup"><span data-stu-id="e1637-114">name</span></span>|<span data-ttu-id="e1637-115">Строка, содержащая уникальное имя этого элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e1637-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1637-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e1637-116">Child Elements</span></span>  
  
|<span data-ttu-id="e1637-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="e1637-117">Element</span></span>|<span data-ttu-id="e1637-118">Описание</span><span class="sxs-lookup"><span data-stu-id="e1637-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1637-119">\<Фильтры ></span><span class="sxs-lookup"><span data-stu-id="e1637-119">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="e1637-120">Сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="e1637-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e1637-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e1637-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e1637-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="e1637-122">Element</span></span>|<span data-ttu-id="e1637-123">Описание</span><span class="sxs-lookup"><span data-stu-id="e1637-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1637-124">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="e1637-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="e1637-125">Раздел конфигурации, содержащий таблицы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="e1637-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e1637-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e1637-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>    
