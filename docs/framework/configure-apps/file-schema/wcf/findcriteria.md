---
title: "&lt;Критерии_поиска&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b428d1a95ec6f1f493c831f66223f52e4723990c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltfindcriteriagt"></a><span data-ttu-id="a4e90-102">&lt;Критерии_поиска&gt;</span><span class="sxs-lookup"><span data-stu-id="a4e90-102">&lt;findCriteria&gt;</span></span>
<span data-ttu-id="a4e90-103">Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="a4e90-103">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="a4e90-104">Критерии могут быть сгруппированы в критерии поиска (с указанием искомых служб, которые вы ищете) и критерии прекращения поиска (как долго поиска должно длиться).</span><span class="sxs-lookup"><span data-stu-id="a4e90-104">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>  
  
 <span data-ttu-id="a4e90-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a4e90-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="a4e90-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="a4e90-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4e90-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a4e90-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan" maxResults="Integer" scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String" namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      </standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4e90-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a4e90-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a4e90-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a4e90-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4e90-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a4e90-110">Attributes</span></span>  
  
|<span data-ttu-id="a4e90-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a4e90-111">Attribute</span></span>|<span data-ttu-id="a4e90-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a4e90-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a4e90-113">duration</span><span class="sxs-lookup"><span data-stu-id="a4e90-113">duration</span></span>|<span data-ttu-id="a4e90-114">Значение Timespan, указывающее максимальное время ожидания ответа от служб в сети.</span><span class="sxs-lookup"><span data-stu-id="a4e90-114">A Timespan value that specifies the maximum time to wait for replies from services on the network.</span></span> <span data-ttu-id="a4e90-115">Значение по умолчанию - 20 секунд.</span><span class="sxs-lookup"><span data-stu-id="a4e90-115">The default duration is 20 seconds..</span></span>|  
|<span data-ttu-id="a4e90-116">maxResults</span><span class="sxs-lookup"><span data-stu-id="a4e90-116">maxResults</span></span>|<span data-ttu-id="a4e90-117">Целочисленное значение, указывающее максимальное количество ответов, ожидаемых от служб по сети или через Интернет.</span><span class="sxs-lookup"><span data-stu-id="a4e90-117">An integer that specifies the maximum number of replies to wait for, from services on a network or the Internet.</span></span> <span data-ttu-id="a4e90-118">Операция поиска завершается, если максимальное число ответов достигнуто до истечения срока, указанного в атрибуте `duration`.</span><span class="sxs-lookup"><span data-stu-id="a4e90-118">If maximum replies are received before the value specified in the `duration` attribute has elapsed, the find operation ends.</span></span>|  
|<span data-ttu-id="a4e90-119">scopeMatchBy</span><span class="sxs-lookup"><span data-stu-id="a4e90-119">scopeMatchBy</span></span>|<span data-ttu-id="a4e90-120">URI, указывающий алгоритм сопоставления, который используется для сопоставления областей из сообщения зонда с областями из конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a4e90-120">A URI that specify the matching algorithm to use while matching the scopes in the Probe message with that of the endpoint.</span></span><br /><br /> <span data-ttu-id="a4e90-121">Поддерживаются пять правил сопоставления областей.</span><span class="sxs-lookup"><span data-stu-id="a4e90-121">There are five supported scope-matching rules.</span></span> <span data-ttu-id="a4e90-122">Если правило сопоставления областей не указано, используется `ScopeMatchByPrefix`.</span><span class="sxs-lookup"><span data-stu-id="a4e90-122">If you do not specify a scope-matching rule, `ScopeMatchByPrefix` is used.</span></span> <span data-ttu-id="a4e90-123">Дополнительные сведения см. в разделе <xref:System.ServiceModel.Discovery.FindCriteria>.</span><span class="sxs-lookup"><span data-stu-id="a4e90-123">For more information on this, see <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4e90-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a4e90-124">Child Elements</span></span>  
  
|<span data-ttu-id="a4e90-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="a4e90-125">Element</span></span>|<span data-ttu-id="a4e90-126">Описание</span><span class="sxs-lookup"><span data-stu-id="a4e90-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4e90-127">\<contractTypeNames ></span><span class="sxs-lookup"><span data-stu-id="a4e90-127">\<contractTypeNames></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="a4e90-128">Коллекция элементов конфигурации, которые содержат имена типов контрактов службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a4e90-128">A collection of configuration elements that contain the names of workflow service contract types..</span></span>|  
|<span data-ttu-id="a4e90-129">\<расширения > из \<Критерии_поиска ></span><span class="sxs-lookup"><span data-stu-id="a4e90-129">\<extensions> of \<findCriteria></span></span>|<span data-ttu-id="a4e90-130">Коллекция объектов элементов XML, предоставляющих расширения.</span><span class="sxs-lookup"><span data-stu-id="a4e90-130">A collection of XML element objects that provide extensions.</span></span>|  
|[<span data-ttu-id="a4e90-131">\<области ></span><span class="sxs-lookup"><span data-stu-id="a4e90-131">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="a4e90-132">Коллекция объектов, содержащих абсолютные URI, по которым определяется расположение отдельных служб в ходе операции поиска.</span><span class="sxs-lookup"><span data-stu-id="a4e90-132">A collection of objects that contain absolute URIs that are used during a find operation to locate a specific service or services.</span></span><br /><br /> <span data-ttu-id="a4e90-133">Если найдена определенная служба, URI службы и URI области были успешно сопоставлены, иногда с помощью правил области, предназначенных для преодоления сложностей совпадения.</span><span class="sxs-lookup"><span data-stu-id="a4e90-133">If the specific service is found, a successful match has been made between the service URI and the Scope URI, sometimes with the help of scope rules that handle complications of matching.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a4e90-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a4e90-134">Parent Elements</span></span>  
  
|<span data-ttu-id="a4e90-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="a4e90-135">Element</span></span>|<span data-ttu-id="a4e90-136">Описание</span><span class="sxs-lookup"><span data-stu-id="a4e90-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4e90-137">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="a4e90-137">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="a4e90-138">Содержит параметры, необходимые приложению для участия в процессе обнаружения служб в качестве клиента.</span><span class="sxs-lookup"><span data-stu-id="a4e90-138">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a4e90-139">См. также</span><span class="sxs-lookup"><span data-stu-id="a4e90-139">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
