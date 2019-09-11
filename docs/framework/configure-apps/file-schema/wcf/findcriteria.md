---
title: <findCriteria>
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: 44e068ee205bc5e04382164e7ab00716b2c07dcf
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855167"
---
# <a name="findcriteria"></a><span data-ttu-id="f7077-101">\<findCriteria ></span><span class="sxs-lookup"><span data-stu-id="f7077-101">\<findCriteria></span></span>
<span data-ttu-id="f7077-102">Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="f7077-102">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="f7077-103">Критерии можно сгруппировать в критерии поиска (указав интересующие вас службы) и найти критерии завершения (срок поиска в прошлом).</span><span class="sxs-lookup"><span data-stu-id="f7077-103">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>  
  
<span data-ttu-id="f7077-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f7077-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f7077-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f7077-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f7077-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Стандардендпоинтс >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="f7077-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="f7077-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Динамицендпоинт >** ](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="f7077-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="f7077-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Стандардендпоинт >** </span><span class="sxs-lookup"><span data-stu-id="f7077-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="f7077-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Дисковериклиентсеттингс >** ](discoveryclientsettings.md)</span><span class="sxs-lookup"><span data-stu-id="f7077-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)</span></span>\
<span data-ttu-id="f7077-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<findCriteria >**</span><span class="sxs-lookup"><span data-stu-id="f7077-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<findCriteria>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7077-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7077-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7077-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f7077-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f7077-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f7077-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7077-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f7077-114">Attributes</span></span>  
  
|<span data-ttu-id="f7077-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f7077-115">Attribute</span></span>|<span data-ttu-id="f7077-116">Описание</span><span class="sxs-lookup"><span data-stu-id="f7077-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f7077-117">длительность</span><span class="sxs-lookup"><span data-stu-id="f7077-117">duration</span></span>|<span data-ttu-id="f7077-118">Значение Timespan, указывающее максимальное время ожидания ответа от служб в сети.</span><span class="sxs-lookup"><span data-stu-id="f7077-118">A Timespan value that specifies the maximum time to wait for replies from services on the network.</span></span> <span data-ttu-id="f7077-119">Значение времени ожидания по умолчанию - 20 секунд.</span><span class="sxs-lookup"><span data-stu-id="f7077-119">The default duration is 20 seconds.</span></span>|  
|<span data-ttu-id="f7077-120">maxResults</span><span class="sxs-lookup"><span data-stu-id="f7077-120">maxResults</span></span>|<span data-ttu-id="f7077-121">Целочисленное значение, указывающее максимальное количество ответов, ожидаемых от служб по сети или через Интернет.</span><span class="sxs-lookup"><span data-stu-id="f7077-121">An integer that specifies the maximum number of replies to wait for, from services on a network or the Internet.</span></span> <span data-ttu-id="f7077-122">Операция поиска завершается, если максимальное число ответов достигнуто до истечения срока, указанного в атрибуте `duration`.</span><span class="sxs-lookup"><span data-stu-id="f7077-122">If maximum replies are received before the value specified in the `duration` attribute has elapsed, the find operation ends.</span></span>|  
|<span data-ttu-id="f7077-123">scopeMatchBy</span><span class="sxs-lookup"><span data-stu-id="f7077-123">scopeMatchBy</span></span>|<span data-ttu-id="f7077-124">URI, указывающий алгоритм сопоставления, который используется для сопоставления областей из сообщения зонда с областями из конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f7077-124">A URI that specify the matching algorithm to use while matching the scopes in the Probe message with that of the endpoint.</span></span><br /><br /> <span data-ttu-id="f7077-125">Поддерживаются пять правил сопоставления областей.</span><span class="sxs-lookup"><span data-stu-id="f7077-125">There are five supported scope-matching rules.</span></span> <span data-ttu-id="f7077-126">Если правило сопоставления областей не указано, используется `ScopeMatchByPrefix`.</span><span class="sxs-lookup"><span data-stu-id="f7077-126">If you do not specify a scope-matching rule, `ScopeMatchByPrefix` is used.</span></span> <span data-ttu-id="f7077-127">Дополнительные сведения см. в разделе <xref:System.ServiceModel.Discovery.FindCriteria>.</span><span class="sxs-lookup"><span data-stu-id="f7077-127">For more information on this, see <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7077-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f7077-128">Child Elements</span></span>  
  
|<span data-ttu-id="f7077-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="f7077-129">Element</span></span>|<span data-ttu-id="f7077-130">Описание</span><span class="sxs-lookup"><span data-stu-id="f7077-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7077-131">\<Контракттипенамес ></span><span class="sxs-lookup"><span data-stu-id="f7077-131">\<contractTypeNames></span></span>](contracttypenames.md)|<span data-ttu-id="f7077-132">Коллекция элементов конфигурации, содержащих имена типов контрактов службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f7077-132">A collection of configuration elements that contain the names of workflow service contract types.</span></span>|  
|<span data-ttu-id="f7077-133">\<расширения > \<> findCriteria</span><span class="sxs-lookup"><span data-stu-id="f7077-133">\<extensions> of \<findCriteria></span></span>|<span data-ttu-id="f7077-134">Коллекция объектов элементов XML, предоставляющих расширения.</span><span class="sxs-lookup"><span data-stu-id="f7077-134">A collection of XML element objects that provide extensions.</span></span>|  
|[<span data-ttu-id="f7077-135">\<области ></span><span class="sxs-lookup"><span data-stu-id="f7077-135">\<scopes></span></span>](scopes.md)|<span data-ttu-id="f7077-136">Коллекция объектов, содержащих абсолютные URI, по которым определяется расположение отдельных служб в ходе операции поиска.</span><span class="sxs-lookup"><span data-stu-id="f7077-136">A collection of objects that contain absolute URIs that are used during a find operation to locate a specific service or services.</span></span><br /><br /> <span data-ttu-id="f7077-137">Если найдена определенная служба, URI службы и URI области были успешно сопоставлены, иногда с помощью правил области, предназначенных для преодоления сложностей совпадения.</span><span class="sxs-lookup"><span data-stu-id="f7077-137">If the specific service is found, a successful match has been made between the service URI and the Scope URI, sometimes with the help of scope rules that handle complications of matching.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f7077-138">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f7077-138">Parent Elements</span></span>  
  
|<span data-ttu-id="f7077-139">Элемент</span><span class="sxs-lookup"><span data-stu-id="f7077-139">Element</span></span>|<span data-ttu-id="f7077-140">Описание</span><span class="sxs-lookup"><span data-stu-id="f7077-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7077-141">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="f7077-141">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="f7077-142">Содержит параметры, необходимые приложению для участия в процессе обнаружения служб в качестве клиента.</span><span class="sxs-lookup"><span data-stu-id="f7077-142">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f7077-143">См. также</span><span class="sxs-lookup"><span data-stu-id="f7077-143">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
