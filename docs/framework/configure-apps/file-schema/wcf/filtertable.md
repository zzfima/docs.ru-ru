---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 918a365004efea82f4ef4c8868f6821d4bb6da18
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855192"
---
# <a name="filtertable"></a><span data-ttu-id="376a7-101">\<Филтертабле ></span><span class="sxs-lookup"><span data-stu-id="376a7-101">\<filterTable></span></span>
<span data-ttu-id="376a7-102">Представляет таблицу маршрутизации, содержащую список фильтров для вычисления сообщений и конечную точку клиента для маршрутизации сообщений, если фильтр имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="376a7-102">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
<span data-ttu-id="376a7-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="376a7-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="376a7-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="376a7-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="376a7-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> маршрутизации**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="376a7-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="376a7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Филтертаблес >** ](filtertables.md)</span><span class="sxs-lookup"><span data-stu-id="376a7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)</span></span>\
<span data-ttu-id="376a7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Филтертабле >**</span><span class="sxs-lookup"><span data-stu-id="376a7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTable>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="376a7-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="376a7-108">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
     name="String">
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="376a7-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="376a7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="376a7-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="376a7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="376a7-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="376a7-111">Attributes</span></span>  
  
|<span data-ttu-id="376a7-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="376a7-112">Element</span></span>|<span data-ttu-id="376a7-113">Описание</span><span class="sxs-lookup"><span data-stu-id="376a7-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="376a7-114">имя</span><span class="sxs-lookup"><span data-stu-id="376a7-114">name</span></span>|<span data-ttu-id="376a7-115">Строка, содержащая уникальное имя этого элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="376a7-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="376a7-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="376a7-116">Child Elements</span></span>  
  
|<span data-ttu-id="376a7-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="376a7-117">Element</span></span>|<span data-ttu-id="376a7-118">Описание</span><span class="sxs-lookup"><span data-stu-id="376a7-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="376a7-119">\<Фильтры></span><span class="sxs-lookup"><span data-stu-id="376a7-119">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="376a7-120">Сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="376a7-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="376a7-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="376a7-121">Parent Elements</span></span>  
  
|<span data-ttu-id="376a7-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="376a7-122">Element</span></span>|<span data-ttu-id="376a7-123">Описание</span><span class="sxs-lookup"><span data-stu-id="376a7-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="376a7-124">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="376a7-124">\<routing></span></span>](routing.md)|<span data-ttu-id="376a7-125">Раздел конфигурации, содержащий таблицы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="376a7-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="376a7-126">См. также</span><span class="sxs-lookup"><span data-stu-id="376a7-126">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
