---
title: '&lt;discoveryClientSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bd2e9f3fd6d2cd0b99c6b63bc8ad0eefc9ff3e01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltdiscoveryclientsettingsgt"></a><span data-ttu-id="7918c-102">&lt;discoveryClientSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="7918c-102">&lt;discoveryClientSettings&gt;</span></span>
<span data-ttu-id="7918c-103">Содержит параметры, необходимые приложению для участия в процессе обнаружения служб в качестве клиента.</span><span class="sxs-lookup"><span data-stu-id="7918c-103">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="7918c-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7918c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7918c-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="7918c-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7918c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7918c-106">Syntax</span></span>  
  
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
              <add name="String" namespace="String" />
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7918c-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7918c-107">Attributes and Elements</span></span>  
 <span data-ttu-id="7918c-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7918c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7918c-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7918c-109">Attributes</span></span>  
  
|<span data-ttu-id="7918c-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7918c-110">Attribute</span></span>|<span data-ttu-id="7918c-111">Описание</span><span class="sxs-lookup"><span data-stu-id="7918c-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7918c-112">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="7918c-112">discoveryEndpoint</span></span>|<span data-ttu-id="7918c-113">Строка, содержащая имя конечной точки обнаружения, которая позволяет клиентскому приложению выполнять автоматический поиск необходимой службы и находить ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7918c-113">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7918c-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7918c-114">Child Elements</span></span>  
  
|<span data-ttu-id="7918c-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="7918c-115">Element</span></span>|<span data-ttu-id="7918c-116">Описание</span><span class="sxs-lookup"><span data-stu-id="7918c-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7918c-117">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="7918c-117">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="7918c-118">Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="7918c-118">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="7918c-119">Критерии могут быть сгруппированы в критерии поиска (с указанием искомых служб, которые вы ищете) и критерии прекращения поиска (как долго поиска должно длиться).</span><span class="sxs-lookup"><span data-stu-id="7918c-119">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7918c-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7918c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7918c-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="7918c-121">Element</span></span>|<span data-ttu-id="7918c-122">Описание</span><span class="sxs-lookup"><span data-stu-id="7918c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7918c-123">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="7918c-123">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="7918c-124">Определяет стандартную конечную точку, сведения которой позволяют приложению работать в качестве клиентской программы, динамически ищущей адрес конечной точки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7918c-124">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7918c-125">См. также</span><span class="sxs-lookup"><span data-stu-id="7918c-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
