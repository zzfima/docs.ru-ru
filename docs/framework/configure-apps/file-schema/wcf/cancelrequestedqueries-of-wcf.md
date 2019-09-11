---
title: <cancelRequestedQueries>WCF
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 63cfc835ac7ce88bde56fd9243a2cf6652cbce6e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850092"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="aa123-102">\<Канцелрекуестедкуериес > WCF</span><span class="sxs-lookup"><span data-stu-id="aa123-102">\<cancelRequestedQueries> of WCF</span></span>
<span data-ttu-id="aa123-103">Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="aa123-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="aa123-104">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="aa123-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="aa123-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="aa123-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="aa123-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aa123-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="aa123-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="aa123-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="aa123-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="aa123-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="aa123-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Профили >** </span><span class="sxs-lookup"><span data-stu-id="aa123-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="aa123-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="aa123-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="aa123-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="aa123-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="aa123-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Канцелрекуестедкуериес >**</span><span class="sxs-lookup"><span data-stu-id="aa123-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa123-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa123-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String" />
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa123-114">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="aa123-114">Attributes and elements</span></span>  

<span data-ttu-id="aa123-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aa123-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa123-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aa123-116">Attributes</span></span>

<span data-ttu-id="aa123-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="aa123-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="aa123-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aa123-118">Child elements</span></span>
  
|<span data-ttu-id="aa123-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="aa123-119">Element</span></span>|<span data-ttu-id="aa123-120">Описание</span><span class="sxs-lookup"><span data-stu-id="aa123-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa123-121">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="aa123-121">\<cancelRequestedQuery></span></span>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="aa123-122">Запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="aa123-122">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aa123-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aa123-123">Parent elements</span></span>  
  
|<span data-ttu-id="aa123-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="aa123-124">Element</span></span>|<span data-ttu-id="aa123-125">Описание</span><span class="sxs-lookup"><span data-stu-id="aa123-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa123-126">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="aa123-126">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="aa123-127">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>.</span><span class="sxs-lookup"><span data-stu-id="aa123-127">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa123-128">См. также</span><span class="sxs-lookup"><span data-stu-id="aa123-128">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="aa123-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="aa123-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="aa123-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="aa123-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
