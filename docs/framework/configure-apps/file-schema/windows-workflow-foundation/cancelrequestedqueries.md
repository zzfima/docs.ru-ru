---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 0d08612ce5d74f4f7f505c538187ddecea610132
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398829"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="c1b7a-101">\<Канцелрекуестедкуериес ></span><span class="sxs-lookup"><span data-stu-id="c1b7a-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="c1b7a-102">Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="c1b7a-103">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="c1b7a-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="c1b7a-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="c1b7a-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c1b7a-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c1b7a-106">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="c1b7a-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="c1b7a-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="c1b7a-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="c1b7a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="c1b7a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="c1b7a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="c1b7a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="c1b7a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Канцелрекуестедкуериес >**</span><span class="sxs-lookup"><span data-stu-id="c1b7a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1b7a-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1b7a-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1b7a-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c1b7a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c1b7a-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1b7a-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c1b7a-114">Attributes</span></span>  
 <span data-ttu-id="c1b7a-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c1b7a-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c1b7a-116">Child Elements</span></span>  
  
|<span data-ttu-id="c1b7a-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="c1b7a-117">Element</span></span>|<span data-ttu-id="c1b7a-118">Описание</span><span class="sxs-lookup"><span data-stu-id="c1b7a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1b7a-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="c1b7a-119">\<cancelRequestedQuery></span></span>](cancelrequestedquery.md)|<span data-ttu-id="c1b7a-120">Запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="c1b7a-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c1b7a-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c1b7a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c1b7a-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="c1b7a-122">Element</span></span>|<span data-ttu-id="c1b7a-123">Описание</span><span class="sxs-lookup"><span data-stu-id="c1b7a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1b7a-124">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="c1b7a-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="c1b7a-125">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="c1b7a-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1b7a-126">См. также</span><span class="sxs-lookup"><span data-stu-id="c1b7a-126">See also</span></span>

- [<span data-ttu-id="c1b7a-127">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="c1b7a-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c1b7a-128">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="c1b7a-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
