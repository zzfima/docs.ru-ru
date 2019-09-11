---
title: <customTrackingQueries>WCF
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 2c4bd74ae346c536e8bc0ae454e638b7c76a40fc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855433"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="2cc33-102">\<Кустомтраккингкуериес > WCF</span><span class="sxs-lookup"><span data-stu-id="2cc33-102">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="2cc33-103">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="2cc33-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="2cc33-104">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="2cc33-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
<span data-ttu-id="2cc33-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="2cc33-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="2cc33-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2cc33-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2cc33-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2cc33-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2cc33-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="2cc33-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="2cc33-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Профили >** </span><span class="sxs-lookup"><span data-stu-id="2cc33-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="2cc33-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="2cc33-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="2cc33-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="2cc33-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="2cc33-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Кустомтраккингкуериес >**</span><span class="sxs-lookup"><span data-stu-id="2cc33-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="2cc33-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2cc33-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2cc33-114">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="2cc33-114">Attributes and elements</span></span>

<span data-ttu-id="2cc33-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2cc33-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2cc33-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2cc33-116">Attributes</span></span>

<span data-ttu-id="2cc33-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="2cc33-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="2cc33-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2cc33-118">Child elements</span></span>
  
|<span data-ttu-id="2cc33-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="2cc33-119">Element</span></span>|<span data-ttu-id="2cc33-120">Описание</span><span class="sxs-lookup"><span data-stu-id="2cc33-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2cc33-121">\<Кустомтраккингкуери ></span><span class="sxs-lookup"><span data-stu-id="2cc33-121">\<customTrackingQuery></span></span>](customtrackingquery-of-wcf.md)|<span data-ttu-id="2cc33-122">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="2cc33-122">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2cc33-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2cc33-123">Parent elements</span></span>  
  
|<span data-ttu-id="2cc33-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="2cc33-124">Element</span></span>|<span data-ttu-id="2cc33-125">Описание</span><span class="sxs-lookup"><span data-stu-id="2cc33-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2cc33-126">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="2cc33-126">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="2cc33-127">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="2cc33-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2cc33-128">См. также</span><span class="sxs-lookup"><span data-stu-id="2cc33-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2cc33-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="2cc33-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2cc33-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="2cc33-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
