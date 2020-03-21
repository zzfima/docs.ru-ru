---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: a02d71811709b2c285ab7081b89ee3082ec5b43d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152213"
---
# <a name="customtrackingquery"></a><span data-ttu-id="f7aa5-101">\<пользовательскиеTrackingКуи></span><span class="sxs-lookup"><span data-stu-id="f7aa5-101">\<customTrackingQuery></span></span>
<span data-ttu-id="f7aa5-102">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="f7aa5-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="f7aa5-103">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f7aa5-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="f7aa5-104">Для получения дополнительной [информации](../../../windows-workflow-foundation/tracking-profiles.md) о запросах профиля отслеживания см.</span><span class="sxs-lookup"><span data-stu-id="f7aa5-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="f7aa5-105">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f7aa5-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f7aa5-106">&nbsp;&nbsp;[**\<Системы. СервисМодель>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="f7aa5-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="f7aa5-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<отслеживание>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="f7aa5-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="f7aa5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<отслеживаниеПрофильная>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="f7aa5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="f7aa5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<рабочий процесс>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="f7aa5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="f7aa5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingЗапросы>**](customtrackingqueries.md)</span><span class="sxs-lookup"><span data-stu-id="f7aa5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)</span></span>\
<span data-ttu-id="f7aa5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<пользовательскиеTrackingКуири>**</span><span class="sxs-lookup"><span data-stu-id="f7aa5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7aa5-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7aa5-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7aa5-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f7aa5-113">Attributes and Elements</span></span>  
 <span data-ttu-id="f7aa5-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f7aa5-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7aa5-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f7aa5-115">Attributes</span></span>  
  
|<span data-ttu-id="f7aa5-116">attribute</span><span class="sxs-lookup"><span data-stu-id="f7aa5-116">Attribute</span></span>|<span data-ttu-id="f7aa5-117">Описание</span><span class="sxs-lookup"><span data-stu-id="f7aa5-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f7aa5-118">activityName</span><span class="sxs-lookup"><span data-stu-id="f7aa5-118">activityName</span></span>|<span data-ttu-id="f7aa5-119">Строка, задающая имя действия, сформировавшего запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f7aa5-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="f7aa5-120">name</span><span class="sxs-lookup"><span data-stu-id="f7aa5-120">name</span></span>|<span data-ttu-id="f7aa5-121">Строка, задающая имя выдаваемой пользовательской записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f7aa5-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7aa5-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f7aa5-122">Child Elements</span></span>  
 <span data-ttu-id="f7aa5-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="f7aa5-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7aa5-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f7aa5-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f7aa5-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="f7aa5-125">Element</span></span>|<span data-ttu-id="f7aa5-126">Описание</span><span class="sxs-lookup"><span data-stu-id="f7aa5-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7aa5-127">\<пользовательскиеTrackingКуири></span><span class="sxs-lookup"><span data-stu-id="f7aa5-127">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="f7aa5-128">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="f7aa5-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f7aa5-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f7aa5-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f7aa5-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="f7aa5-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f7aa5-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="f7aa5-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
