---
title: '&lt;filterTables&gt;'
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: 966556a1a8bde72e33640dcc6fd37ae7a044ceef
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753418"
---
# <a name="ltfiltertablesgt"></a><span data-ttu-id="481bb-102">&lt;filterTables&gt;</span><span class="sxs-lookup"><span data-stu-id="481bb-102">&lt;filterTables&gt;</span></span>
<span data-ttu-id="481bb-103">Представляет раздел конфигурации, в котором определены таблицы маршрутизации, содержащие сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при совпадении с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="481bb-103">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="481bb-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="481bb-104">\<system.serviceModel></span></span>  
<span data-ttu-id="481bb-105">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="481bb-105">\<routing></span></span>  
<span data-ttu-id="481bb-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="481bb-106">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="481bb-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="481bb-107">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="481bb-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="481bb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="481bb-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="481bb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="481bb-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="481bb-110">Attributes</span></span>  
 <span data-ttu-id="481bb-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="481bb-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="481bb-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="481bb-112">Child Elements</span></span>  
  
|<span data-ttu-id="481bb-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="481bb-113">Element</span></span>|<span data-ttu-id="481bb-114">Описание</span><span class="sxs-lookup"><span data-stu-id="481bb-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="481bb-115">\<Фильтры ></span><span class="sxs-lookup"><span data-stu-id="481bb-115">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="481bb-116">Таблица маршрутизации, содержащая сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="481bb-116">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="481bb-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="481bb-117">Parent Elements</span></span>  
  
|<span data-ttu-id="481bb-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="481bb-118">Element</span></span>|<span data-ttu-id="481bb-119">Описание</span><span class="sxs-lookup"><span data-stu-id="481bb-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="481bb-120">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="481bb-120">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="481bb-121">Раздел конфигурации, содержащий фильтры и таблицы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="481bb-121">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="481bb-122">См. также</span><span class="sxs-lookup"><span data-stu-id="481bb-122">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>    
