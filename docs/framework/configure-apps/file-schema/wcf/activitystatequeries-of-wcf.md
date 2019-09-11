---
title: <activityStateQueries>WCF
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 249ac3d91f6251a943dd856e4122b8b54f691702
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850570"
---
# <a name="activitystatequeries-of-wcf"></a><span data-ttu-id="2ce13-102">\<Активитистатекуериес > WCF</span><span class="sxs-lookup"><span data-stu-id="2ce13-102">\<activityStateQueries> of WCF</span></span>

<span data-ttu-id="2ce13-103">Представляет коллекцию запросов, которые используются для отслеживания изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="2ce13-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="2ce13-104">Например, вы можете захотеть отследить каждый раз, когда действие "отправить электронное письмо" завершается в рамках экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="2ce13-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="2ce13-105">Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия.</span><span class="sxs-lookup"><span data-stu-id="2ce13-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="2ce13-106">Состояния, доступные для подписки, указаны в ActivtyStates.</span><span class="sxs-lookup"><span data-stu-id="2ce13-106">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="2ce13-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="2ce13-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="2ce13-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2ce13-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2ce13-109">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2ce13-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2ce13-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="2ce13-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="2ce13-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Профили >** </span><span class="sxs-lookup"><span data-stu-id="2ce13-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="2ce13-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="2ce13-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="2ce13-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="2ce13-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="2ce13-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Активитистатекуериес >**</span><span class="sxs-lookup"><span data-stu-id="2ce13-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ce13-115">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ce13-115">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String" />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQuery>
        </activityStateQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  

## <a name="attributes-and-elements"></a><span data-ttu-id="2ce13-116">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="2ce13-116">Attributes and elements</span></span>

<span data-ttu-id="2ce13-117">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2ce13-117">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="2ce13-118">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2ce13-118">Attributes</span></span>  

<span data-ttu-id="2ce13-119">Нет.</span><span class="sxs-lookup"><span data-stu-id="2ce13-119">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="2ce13-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2ce13-120">Child elements</span></span>

|<span data-ttu-id="2ce13-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="2ce13-121">Element</span></span>|<span data-ttu-id="2ce13-122">Описание</span><span class="sxs-lookup"><span data-stu-id="2ce13-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2ce13-123">\<Активитистатекуери ></span><span class="sxs-lookup"><span data-stu-id="2ce13-123">\<activityStateQuery></span></span>](activitystatequery-of-wcf.md)|<span data-ttu-id="2ce13-124">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="2ce13-124">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="2ce13-125">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="2ce13-125">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2ce13-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2ce13-126">Parent elements</span></span>

|<span data-ttu-id="2ce13-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="2ce13-127">Element</span></span>|<span data-ttu-id="2ce13-128">Описание</span><span class="sxs-lookup"><span data-stu-id="2ce13-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2ce13-129">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="2ce13-129">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="2ce13-130">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="2ce13-130">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="2ce13-131">См. также</span><span class="sxs-lookup"><span data-stu-id="2ce13-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="2ce13-132">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="2ce13-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2ce13-133">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="2ce13-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
