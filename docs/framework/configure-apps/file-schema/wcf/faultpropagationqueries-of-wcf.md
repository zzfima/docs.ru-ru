---
title: <faultPropagationQueries>WCF
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 709c2c6907b4d0d28118f9de12edb047aa16d741
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855265"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="55662-102">\<Фаултпропагатионкуериес > WCF</span><span class="sxs-lookup"><span data-stu-id="55662-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="55662-103">Представляет коллекцию запросов, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="55662-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="55662-104">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="55662-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="55662-105">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="55662-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="55662-106">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="55662-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="55662-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="55662-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="55662-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="55662-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="55662-109">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="55662-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="55662-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="55662-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="55662-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Профили >** </span><span class="sxs-lookup"><span data-stu-id="55662-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="55662-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="55662-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="55662-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="55662-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="55662-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Фаултпропагатионкуериес >**</span><span class="sxs-lookup"><span data-stu-id="55662-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55662-115">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55662-115">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String"/>
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55662-116">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="55662-116">Attributes and elements</span></span>

<span data-ttu-id="55662-117">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="55662-117">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="55662-118">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="55662-118">Attributes</span></span>

<span data-ttu-id="55662-119">Нет.</span><span class="sxs-lookup"><span data-stu-id="55662-119">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="55662-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="55662-120">Child elements</span></span>

|<span data-ttu-id="55662-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="55662-121">Element</span></span>|<span data-ttu-id="55662-122">Описание</span><span class="sxs-lookup"><span data-stu-id="55662-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="55662-123">\<Фаултпропагатионкуери ></span><span class="sxs-lookup"><span data-stu-id="55662-123">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="55662-124">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="55662-124">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="55662-125">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="55662-125">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="55662-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="55662-126">Parent elements</span></span>  
  
|<span data-ttu-id="55662-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="55662-127">Element</span></span>|<span data-ttu-id="55662-128">Описание</span><span class="sxs-lookup"><span data-stu-id="55662-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="55662-129">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="55662-129">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="55662-130">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="55662-130">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="55662-131">См. также</span><span class="sxs-lookup"><span data-stu-id="55662-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="55662-132">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="55662-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="55662-133">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="55662-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
