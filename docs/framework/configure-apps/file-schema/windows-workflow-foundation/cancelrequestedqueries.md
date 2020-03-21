---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 89297b3a7d64f4300a735d8512230d441836c634
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152311"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="baece-101">\<отменаЗапросы></span><span class="sxs-lookup"><span data-stu-id="baece-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="baece-102">Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="baece-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="baece-103">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="baece-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="baece-104">Для получения дополнительной [информации](../../../windows-workflow-foundation/tracking-profiles.md) о запросах профиля отслеживания см.</span><span class="sxs-lookup"><span data-stu-id="baece-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="baece-105">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="baece-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="baece-106">&nbsp;&nbsp;[**\<Системы. СервисМодель>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="baece-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="baece-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<отслеживание>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="baece-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="baece-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<отслеживаниеПрофильная>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="baece-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="baece-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<рабочий процесс>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="baece-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="baece-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<отменаЗапросы>**</span><span class="sxs-lookup"><span data-stu-id="baece-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baece-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="baece-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String"
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="baece-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="baece-112">Attributes and Elements</span></span>  
 <span data-ttu-id="baece-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="baece-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="baece-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="baece-114">Attributes</span></span>  
 <span data-ttu-id="baece-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="baece-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="baece-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="baece-116">Child Elements</span></span>  
  
|<span data-ttu-id="baece-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="baece-117">Element</span></span>|<span data-ttu-id="baece-118">Описание</span><span class="sxs-lookup"><span data-stu-id="baece-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="baece-119">\<отменаЗапроса></span><span class="sxs-lookup"><span data-stu-id="baece-119">\<cancelRequestedQuery></span></span>](cancelrequestedquery.md)|<span data-ttu-id="baece-120">Запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="baece-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="baece-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="baece-121">Parent Elements</span></span>  
  
|<span data-ttu-id="baece-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="baece-122">Element</span></span>|<span data-ttu-id="baece-123">Описание</span><span class="sxs-lookup"><span data-stu-id="baece-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="baece-124">\<рабочий процесс></span><span class="sxs-lookup"><span data-stu-id="baece-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="baece-125">Элемент конфигурации, содержащий все запросы для конкретного рабочего процесса, идентифицированного свойством **activityDefinitionId.**</span><span class="sxs-lookup"><span data-stu-id="baece-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="baece-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="baece-126">See also</span></span>

- [<span data-ttu-id="baece-127">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="baece-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="baece-128">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="baece-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
