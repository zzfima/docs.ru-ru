---
title: '&lt;cancelRequestedQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 457cc3aaa921016e553eb40bcee72af5de3c7179
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltcancelrequestedqueriesgt"></a><span data-ttu-id="1c882-102">&lt;cancelRequestedQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="1c882-102">&lt;cancelRequestedQueries&gt;</span></span>
<span data-ttu-id="1c882-103">Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="1c882-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="1c882-104">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="1c882-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="1c882-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="1c882-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="1c882-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="1c882-106">\<system.serviceModel></span></span>  
<span data-ttu-id="1c882-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="1c882-107">\<tracking></span></span>  
<span data-ttu-id="1c882-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="1c882-108">\<trackingProfile></span></span>  
<span data-ttu-id="1c882-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="1c882-109">\<workflow></span></span>  
<span data-ttu-id="1c882-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="1c882-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c882-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c882-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c882-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1c882-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1c882-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1c882-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c882-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1c882-114">Attributes</span></span>  
 <span data-ttu-id="1c882-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1c882-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1c882-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1c882-116">Child Elements</span></span>  
  
|<span data-ttu-id="1c882-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="1c882-117">Element</span></span>|<span data-ttu-id="1c882-118">Описание</span><span class="sxs-lookup"><span data-stu-id="1c882-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c882-119">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="1c882-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="1c882-120">Запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="1c882-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1c882-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1c882-121">Parent Elements</span></span>  
  
|<span data-ttu-id="1c882-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="1c882-122">Element</span></span>|<span data-ttu-id="1c882-123">Описание</span><span class="sxs-lookup"><span data-stu-id="1c882-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c882-124">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="1c882-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="1c882-125">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="1c882-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1c882-126">См. также</span><span class="sxs-lookup"><span data-stu-id="1c882-126">See Also</span></span>  
 [<span data-ttu-id="1c882-127">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="1c882-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="1c882-128">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="1c882-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
