---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: 58e3752be81609e32eee631e46d10c0a7d704248
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398958"
---
# <a name="activitystatequeries"></a><span data-ttu-id="086d5-101">\<Активитистатекуериес ></span><span class="sxs-lookup"><span data-stu-id="086d5-101">\<activityStateQueries></span></span>
<span data-ttu-id="086d5-102">Представляет коллекцию запросов, которые используются для отслеживания изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="086d5-102">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="086d5-103">Например, вы можете захотеть отследить каждый раз, когда действие "отправить электронное письмо" завершается в рамках экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="086d5-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="086d5-104">Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия.</span><span class="sxs-lookup"><span data-stu-id="086d5-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="086d5-105">Состояния, доступные для подписки, указаны в ActivtyStates.</span><span class="sxs-lookup"><span data-stu-id="086d5-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="086d5-106">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="086d5-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="086d5-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="086d5-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="086d5-108">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="086d5-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="086d5-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="086d5-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="086d5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="086d5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="086d5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="086d5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="086d5-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Активитистатекуериес >**</span><span class="sxs-lookup"><span data-stu-id="086d5-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="086d5-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="086d5-113">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
        <states>
          <state name="String" />
        </states>
        <variables>
         <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="086d5-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="086d5-114">Attributes and Elements</span></span>  
 <span data-ttu-id="086d5-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="086d5-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="086d5-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="086d5-116">Attributes</span></span>  
 <span data-ttu-id="086d5-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="086d5-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="086d5-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="086d5-118">Child Elements</span></span>  
  
|<span data-ttu-id="086d5-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="086d5-119">Element</span></span>|<span data-ttu-id="086d5-120">Описание</span><span class="sxs-lookup"><span data-stu-id="086d5-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="086d5-121">\<Активитистатекуери ></span><span class="sxs-lookup"><span data-stu-id="086d5-121">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="086d5-122">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="086d5-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="086d5-123">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="086d5-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="086d5-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="086d5-124">Parent Elements</span></span>  
  
|<span data-ttu-id="086d5-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="086d5-125">Element</span></span>|<span data-ttu-id="086d5-126">Описание</span><span class="sxs-lookup"><span data-stu-id="086d5-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="086d5-127">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="086d5-127">\<workflow></span></span>](workflow.md)|<span data-ttu-id="086d5-128">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="086d5-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="086d5-129">См. также</span><span class="sxs-lookup"><span data-stu-id="086d5-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="086d5-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="086d5-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="086d5-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="086d5-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
