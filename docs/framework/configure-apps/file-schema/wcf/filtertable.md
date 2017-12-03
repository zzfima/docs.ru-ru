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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 96425604fab8f70456ea1e0d97efb2c3bf843224
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltfiltertablegt"></a><span data-ttu-id="878de-102">&lt;filterTable&gt;</span><span class="sxs-lookup"><span data-stu-id="878de-102">&lt;filterTable&gt;</span></span>
<span data-ttu-id="878de-103">Представляет таблицу маршрутизации, содержащую список фильтров для оценки сообщения, а конечная точка клиента для перенаправления сообщений, если фильтр имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="878de-103">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="878de-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="878de-104">\<system.serviceModel></span></span>  
<span data-ttu-id="878de-105">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="878de-105">\<routing></span></span>  
<span data-ttu-id="878de-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="878de-106">\<routingTables></span></span>  
<span data-ttu-id="878de-107">\<Таблица ></span><span class="sxs-lookup"><span data-stu-id="878de-107">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="878de-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="878de-108">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="878de-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="878de-109">Attributes and Elements</span></span>  
 <span data-ttu-id="878de-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="878de-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="878de-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="878de-111">Attributes</span></span>  
  
|<span data-ttu-id="878de-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="878de-112">Element</span></span>|<span data-ttu-id="878de-113">Описание</span><span class="sxs-lookup"><span data-stu-id="878de-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="878de-114">имя</span><span class="sxs-lookup"><span data-stu-id="878de-114">name</span></span>|<span data-ttu-id="878de-115">Строка, содержащая уникальное имя этого элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="878de-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="878de-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="878de-116">Child Elements</span></span>  
  
|<span data-ttu-id="878de-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="878de-117">Element</span></span>|<span data-ttu-id="878de-118">Описание</span><span class="sxs-lookup"><span data-stu-id="878de-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="878de-119">\<Фильтры ></span><span class="sxs-lookup"><span data-stu-id="878de-119">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="878de-120">Сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="878de-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="878de-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="878de-121">Parent Elements</span></span>  
  
|<span data-ttu-id="878de-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="878de-122">Element</span></span>|<span data-ttu-id="878de-123">Описание</span><span class="sxs-lookup"><span data-stu-id="878de-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="878de-124">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="878de-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="878de-125">Раздел конфигурации, содержащий таблицы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="878de-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="878de-126">См. также</span><span class="sxs-lookup"><span data-stu-id="878de-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>    
