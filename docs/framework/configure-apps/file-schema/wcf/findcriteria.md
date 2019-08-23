---
title: <findCriteria>
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: eb8ff3905f7696f4c71a79e31db1b8f82c9f0d3b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925584"
---
# <a name="findcriteria"></a><span data-ttu-id="dc951-101">\<findCriteria ></span><span class="sxs-lookup"><span data-stu-id="dc951-101">\<findCriteria></span></span>
<span data-ttu-id="dc951-102">Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="dc951-102">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="dc951-103">Критерии можно сгруппировать в критерии поиска (указав интересующие вас службы) и найти критерии завершения (срок поиска в прошлом).</span><span class="sxs-lookup"><span data-stu-id="dc951-103">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>  
  
 <span data-ttu-id="dc951-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dc951-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dc951-105">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="dc951-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc951-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc951-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String"
                   namespace="String" />
            </contractTypeNames>
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc951-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dc951-107">Attributes and Elements</span></span>  
 <span data-ttu-id="dc951-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dc951-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc951-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dc951-109">Attributes</span></span>  
  
|<span data-ttu-id="dc951-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dc951-110">Attribute</span></span>|<span data-ttu-id="dc951-111">Описание</span><span class="sxs-lookup"><span data-stu-id="dc951-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dc951-112">длительность</span><span class="sxs-lookup"><span data-stu-id="dc951-112">duration</span></span>|<span data-ttu-id="dc951-113">Значение Timespan, указывающее максимальное время ожидания ответа от служб в сети.</span><span class="sxs-lookup"><span data-stu-id="dc951-113">A Timespan value that specifies the maximum time to wait for replies from services on the network.</span></span> <span data-ttu-id="dc951-114">Значение времени ожидания по умолчанию - 20 секунд.</span><span class="sxs-lookup"><span data-stu-id="dc951-114">The default duration is 20 seconds.</span></span>|  
|<span data-ttu-id="dc951-115">maxResults</span><span class="sxs-lookup"><span data-stu-id="dc951-115">maxResults</span></span>|<span data-ttu-id="dc951-116">Целочисленное значение, указывающее максимальное количество ответов, ожидаемых от служб по сети или через Интернет.</span><span class="sxs-lookup"><span data-stu-id="dc951-116">An integer that specifies the maximum number of replies to wait for, from services on a network or the Internet.</span></span> <span data-ttu-id="dc951-117">Операция поиска завершается, если максимальное число ответов достигнуто до истечения срока, указанного в атрибуте `duration`.</span><span class="sxs-lookup"><span data-stu-id="dc951-117">If maximum replies are received before the value specified in the `duration` attribute has elapsed, the find operation ends.</span></span>|  
|<span data-ttu-id="dc951-118">scopeMatchBy</span><span class="sxs-lookup"><span data-stu-id="dc951-118">scopeMatchBy</span></span>|<span data-ttu-id="dc951-119">URI, указывающий алгоритм сопоставления, который используется для сопоставления областей из сообщения зонда с областями из конечной точки.</span><span class="sxs-lookup"><span data-stu-id="dc951-119">A URI that specify the matching algorithm to use while matching the scopes in the Probe message with that of the endpoint.</span></span><br /><br /> <span data-ttu-id="dc951-120">Поддерживаются пять правил сопоставления областей.</span><span class="sxs-lookup"><span data-stu-id="dc951-120">There are five supported scope-matching rules.</span></span> <span data-ttu-id="dc951-121">Если правило сопоставления областей не указано, используется `ScopeMatchByPrefix`.</span><span class="sxs-lookup"><span data-stu-id="dc951-121">If you do not specify a scope-matching rule, `ScopeMatchByPrefix` is used.</span></span> <span data-ttu-id="dc951-122">Дополнительные сведения см. в разделе <xref:System.ServiceModel.Discovery.FindCriteria>.</span><span class="sxs-lookup"><span data-stu-id="dc951-122">For more information on this, see <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc951-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dc951-123">Child Elements</span></span>  
  
|<span data-ttu-id="dc951-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="dc951-124">Element</span></span>|<span data-ttu-id="dc951-125">Описание</span><span class="sxs-lookup"><span data-stu-id="dc951-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc951-126">\<Контракттипенамес ></span><span class="sxs-lookup"><span data-stu-id="dc951-126">\<contractTypeNames></span></span>](contracttypenames.md)|<span data-ttu-id="dc951-127">Коллекция элементов конфигурации, содержащих имена типов контрактов службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="dc951-127">A collection of configuration elements that contain the names of workflow service contract types.</span></span>|  
|<span data-ttu-id="dc951-128">\<расширения > \<> findCriteria</span><span class="sxs-lookup"><span data-stu-id="dc951-128">\<extensions> of \<findCriteria></span></span>|<span data-ttu-id="dc951-129">Коллекция объектов элементов XML, предоставляющих расширения.</span><span class="sxs-lookup"><span data-stu-id="dc951-129">A collection of XML element objects that provide extensions.</span></span>|  
|[<span data-ttu-id="dc951-130">\<области ></span><span class="sxs-lookup"><span data-stu-id="dc951-130">\<scopes></span></span>](scopes.md)|<span data-ttu-id="dc951-131">Коллекция объектов, содержащих абсолютные URI, по которым определяется расположение отдельных служб в ходе операции поиска.</span><span class="sxs-lookup"><span data-stu-id="dc951-131">A collection of objects that contain absolute URIs that are used during a find operation to locate a specific service or services.</span></span><br /><br /> <span data-ttu-id="dc951-132">Если найдена определенная служба, URI службы и URI области были успешно сопоставлены, иногда с помощью правил области, предназначенных для преодоления сложностей совпадения.</span><span class="sxs-lookup"><span data-stu-id="dc951-132">If the specific service is found, a successful match has been made between the service URI and the Scope URI, sometimes with the help of scope rules that handle complications of matching.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dc951-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dc951-133">Parent Elements</span></span>  
  
|<span data-ttu-id="dc951-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="dc951-134">Element</span></span>|<span data-ttu-id="dc951-135">Описание</span><span class="sxs-lookup"><span data-stu-id="dc951-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc951-136">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="dc951-136">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="dc951-137">Содержит параметры, необходимые приложению для участия в процессе обнаружения служб в качестве клиента.</span><span class="sxs-lookup"><span data-stu-id="dc951-137">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc951-138">См. также</span><span class="sxs-lookup"><span data-stu-id="dc951-138">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
