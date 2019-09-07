---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: bc0cc5fd027da45994269b149b72496fa03becef
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398732"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="0e2a2-101">\<Фаултпропагатионкуериес ></span><span class="sxs-lookup"><span data-stu-id="0e2a2-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="0e2a2-102">Представляет коллекцию запросов, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="0e2a2-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="0e2a2-103">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="0e2a2-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="0e2a2-104">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="0e2a2-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="0e2a2-105">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="0e2a2-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="0e2a2-106">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0e2a2-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="0e2a2-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0e2a2-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0e2a2-108">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="0e2a2-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="0e2a2-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="0e2a2-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="0e2a2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="0e2a2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="0e2a2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="0e2a2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="0e2a2-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Фаултпропагатионкуериес >**</span><span class="sxs-lookup"><span data-stu-id="0e2a2-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="0e2a2-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e2a2-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e2a2-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0e2a2-114">Attributes and Elements</span></span>  
 <span data-ttu-id="0e2a2-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0e2a2-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e2a2-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0e2a2-116">Attributes</span></span>  
 <span data-ttu-id="0e2a2-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="0e2a2-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0e2a2-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0e2a2-118">Child Elements</span></span>  
  
|<span data-ttu-id="0e2a2-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="0e2a2-119">Element</span></span>|<span data-ttu-id="0e2a2-120">Описание</span><span class="sxs-lookup"><span data-stu-id="0e2a2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e2a2-121">\<Фаултпропагатионкуери ></span><span class="sxs-lookup"><span data-stu-id="0e2a2-121">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="0e2a2-122">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="0e2a2-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="0e2a2-123">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="0e2a2-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0e2a2-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0e2a2-124">Parent Elements</span></span>  
  
|<span data-ttu-id="0e2a2-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="0e2a2-125">Element</span></span>|<span data-ttu-id="0e2a2-126">Описание</span><span class="sxs-lookup"><span data-stu-id="0e2a2-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e2a2-127">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="0e2a2-127">\<workflow></span></span>](workflow.md)|<span data-ttu-id="0e2a2-128">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="0e2a2-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e2a2-129">См. также</span><span class="sxs-lookup"><span data-stu-id="0e2a2-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0e2a2-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="0e2a2-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0e2a2-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="0e2a2-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
