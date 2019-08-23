---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 2783796166d56be3d4983ab09a60d62491699fe3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925861"
---
# <a name="discoveryclientsettings"></a><span data-ttu-id="5ba10-101">\<Дисковериклиентсеттингс ></span><span class="sxs-lookup"><span data-stu-id="5ba10-101">\<discoveryClientSettings></span></span>
<span data-ttu-id="5ba10-102">Содержит параметры, необходимые приложению для участия в процессе обнаружения служб в качестве клиента.</span><span class="sxs-lookup"><span data-stu-id="5ba10-102">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="5ba10-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5ba10-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5ba10-104">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="5ba10-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ba10-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ba10-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ba10-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5ba10-106">Attributes and Elements</span></span>  
 <span data-ttu-id="5ba10-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5ba10-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ba10-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5ba10-108">Attributes</span></span>  
  
|<span data-ttu-id="5ba10-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5ba10-109">Attribute</span></span>|<span data-ttu-id="5ba10-110">Описание</span><span class="sxs-lookup"><span data-stu-id="5ba10-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5ba10-111">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="5ba10-111">discoveryEndpoint</span></span>|<span data-ttu-id="5ba10-112">Строка, содержащая имя конечной точки обнаружения, которая позволяет клиентскому приложению выполнять автоматический поиск необходимой службы и находить ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="5ba10-112">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ba10-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5ba10-113">Child Elements</span></span>  
  
|<span data-ttu-id="5ba10-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="5ba10-114">Element</span></span>|<span data-ttu-id="5ba10-115">Описание</span><span class="sxs-lookup"><span data-stu-id="5ba10-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ba10-116">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="5ba10-116">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="5ba10-117">Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="5ba10-117">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="5ba10-118">Критерии можно сгруппировать в критерии поиска (указав интересующие вас службы) и найти критерии завершения (срок поиска в прошлом).</span><span class="sxs-lookup"><span data-stu-id="5ba10-118">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5ba10-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5ba10-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5ba10-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="5ba10-120">Element</span></span>|<span data-ttu-id="5ba10-121">Описание</span><span class="sxs-lookup"><span data-stu-id="5ba10-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ba10-122">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="5ba10-122">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="5ba10-123">Определяет стандартную конечную точку, сведения которой позволяют приложению работать в качестве клиентской программы, динамически ищущей адрес конечной точки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="5ba10-123">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ba10-124">См. также</span><span class="sxs-lookup"><span data-stu-id="5ba10-124">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
