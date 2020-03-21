---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 6901244009956a499458858bf73f8fd83ec52e13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152265"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="ef129-101">\<customTrackingЗапросы></span><span class="sxs-lookup"><span data-stu-id="ef129-101">\<customTrackingQueries></span></span>
<span data-ttu-id="ef129-102">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="ef129-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="ef129-103">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="ef129-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="ef129-104">Для получения дополнительной [информации](../../../windows-workflow-foundation/tracking-profiles.md) о запросах профиля отслеживания см.</span><span class="sxs-lookup"><span data-stu-id="ef129-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="ef129-105">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ef129-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ef129-106">&nbsp;&nbsp;[**\<Системы. СервисМодель>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ef129-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="ef129-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<отслеживание>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="ef129-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="ef129-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<отслеживаниеПрофильная>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="ef129-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="ef129-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<рабочий процесс>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ef129-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="ef129-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingЗапросы>**</span><span class="sxs-lookup"><span data-stu-id="ef129-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef129-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ef129-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String"
                             name="String" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef129-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ef129-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ef129-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ef129-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef129-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ef129-114">Attributes</span></span>  
 <span data-ttu-id="ef129-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="ef129-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ef129-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ef129-116">Child Elements</span></span>  
  
|<span data-ttu-id="ef129-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="ef129-117">Element</span></span>|<span data-ttu-id="ef129-118">Описание</span><span class="sxs-lookup"><span data-stu-id="ef129-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef129-119">\<пользовательскиеTrackingКуири></span><span class="sxs-lookup"><span data-stu-id="ef129-119">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="ef129-120">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="ef129-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ef129-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ef129-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ef129-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="ef129-122">Element</span></span>|<span data-ttu-id="ef129-123">Описание</span><span class="sxs-lookup"><span data-stu-id="ef129-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef129-124">\<рабочий процесс></span><span class="sxs-lookup"><span data-stu-id="ef129-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="ef129-125">Элемент конфигурации, содержащий все запросы для конкретного рабочего процесса, идентифицированного свойством **activityDefinitionId.**</span><span class="sxs-lookup"><span data-stu-id="ef129-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef129-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ef129-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ef129-127">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="ef129-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ef129-128">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="ef129-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
