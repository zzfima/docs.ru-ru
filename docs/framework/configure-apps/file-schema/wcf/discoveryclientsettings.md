---
title: '&lt;discoveryClientSettings&gt;'
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: bb443334e0713464e64ec9297bbab4ad11eda723
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145059"
---
# <a name="ltdiscoveryclientsettingsgt"></a><span data-ttu-id="2a204-102">&lt;discoveryClientSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="2a204-102">&lt;discoveryClientSettings&gt;</span></span>
<span data-ttu-id="2a204-103">Содержит параметры, необходимые приложению для участия в процессе обнаружения служб в качестве клиента.</span><span class="sxs-lookup"><span data-stu-id="2a204-103">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="2a204-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2a204-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2a204-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="2a204-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a204-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a204-106">Syntax</span></span>  
  
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
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a204-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2a204-107">Attributes and Elements</span></span>  
 <span data-ttu-id="2a204-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2a204-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a204-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2a204-109">Attributes</span></span>  
  
|<span data-ttu-id="2a204-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2a204-110">Attribute</span></span>|<span data-ttu-id="2a204-111">Описание</span><span class="sxs-lookup"><span data-stu-id="2a204-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2a204-112">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="2a204-112">discoveryEndpoint</span></span>|<span data-ttu-id="2a204-113">Строка, содержащая имя конечной точки обнаружения, которая позволяет клиентскому приложению выполнять автоматический поиск необходимой службы и находить ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2a204-113">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a204-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2a204-114">Child Elements</span></span>  
  
|<span data-ttu-id="2a204-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="2a204-115">Element</span></span>|<span data-ttu-id="2a204-116">Описание</span><span class="sxs-lookup"><span data-stu-id="2a204-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a204-117">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="2a204-117">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="2a204-118">Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="2a204-118">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="2a204-119">Критерии могут быть сгруппированы в критерии поиска (с указанием какие службы вы ищете) и (в том, как долго должен длиться поиск данных) критерии прекращения поиска.</span><span class="sxs-lookup"><span data-stu-id="2a204-119">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2a204-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2a204-120">Parent Elements</span></span>  
  
|<span data-ttu-id="2a204-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="2a204-121">Element</span></span>|<span data-ttu-id="2a204-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="2a204-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a204-123">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="2a204-123">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="2a204-124">Определяет стандартную конечную точку, сведения которой позволяют приложению работать в качестве клиентской программы, динамически ищущей адрес конечной точки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2a204-124">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2a204-125">См. также</span><span class="sxs-lookup"><span data-stu-id="2a204-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
