---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 3d6d03638ec5806448a16cc32b37e630d6198624
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152135"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="dee83-101">\<faultPropagationЗапросы></span><span class="sxs-lookup"><span data-stu-id="dee83-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="dee83-102">Представляет коллекцию запросов, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="dee83-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="dee83-103">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="dee83-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="dee83-104">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="dee83-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="dee83-105">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="dee83-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="dee83-106">Для получения дополнительной [информации](../../../windows-workflow-foundation/tracking-profiles.md)о запросах профиля отслеживания см.</span><span class="sxs-lookup"><span data-stu-id="dee83-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="dee83-107">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dee83-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dee83-108">&nbsp;&nbsp;[**\<Системы. СервисМодель>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="dee83-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="dee83-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<отслеживание>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="dee83-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="dee83-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<отслеживаниеПрофильная>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="dee83-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="dee83-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<рабочий процесс>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="dee83-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="dee83-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationЗапросы>**</span><span class="sxs-lookup"><span data-stu-id="dee83-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="dee83-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dee83-113">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String"
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dee83-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dee83-114">Attributes and Elements</span></span>  
 <span data-ttu-id="dee83-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dee83-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dee83-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dee83-116">Attributes</span></span>  
 <span data-ttu-id="dee83-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="dee83-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dee83-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dee83-118">Child Elements</span></span>  
  
|<span data-ttu-id="dee83-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="dee83-119">Element</span></span>|<span data-ttu-id="dee83-120">Описание</span><span class="sxs-lookup"><span data-stu-id="dee83-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dee83-121">\<faultPropagationКевир></span><span class="sxs-lookup"><span data-stu-id="dee83-121">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="dee83-122">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="dee83-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="dee83-123">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="dee83-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dee83-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dee83-124">Parent Elements</span></span>  
  
|<span data-ttu-id="dee83-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="dee83-125">Element</span></span>|<span data-ttu-id="dee83-126">Описание</span><span class="sxs-lookup"><span data-stu-id="dee83-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dee83-127">\<рабочий процесс></span><span class="sxs-lookup"><span data-stu-id="dee83-127">\<workflow></span></span>](workflow.md)|<span data-ttu-id="dee83-128">Элемент конфигурации, содержащий все запросы для конкретного рабочего процесса, идентифицированного свойством **activityDefinitionId.**</span><span class="sxs-lookup"><span data-stu-id="dee83-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dee83-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dee83-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="dee83-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="dee83-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="dee83-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="dee83-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
