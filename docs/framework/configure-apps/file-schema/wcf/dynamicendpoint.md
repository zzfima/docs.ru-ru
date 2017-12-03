---
title: '&lt;dynamicEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e780e1975aecc80ea458ec6a86fca61e4ad22448
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltdynamicendpointgt"></a><span data-ttu-id="792f4-102">&lt;dynamicEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="792f4-102">&lt;dynamicEndpoint&gt;</span></span>
<span data-ttu-id="792f4-103">Этот элемент конфигурации определяет стандартную конечную точку, содержащую сведения, позволяющие приложению работать в качестве клиентской программы, которая может найти адрес конечной точки динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="792f4-103">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="792f4-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="792f4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="792f4-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="792f4-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="792f4-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="792f4-106">Syntax</span></span>  
  
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
            <add scope="URI" />
          </scopes>
        </findCriteria>
      </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="792f4-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="792f4-107">Attributes and Elements</span></span>  
 <span data-ttu-id="792f4-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="792f4-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="792f4-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="792f4-109">Attributes</span></span>  
 <span data-ttu-id="792f4-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="792f4-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="792f4-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="792f4-111">Child Elements</span></span>  
  
|<span data-ttu-id="792f4-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="792f4-112">Element</span></span>|<span data-ttu-id="792f4-113">Описание</span><span class="sxs-lookup"><span data-stu-id="792f4-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="792f4-114">\<discoveryClientSettings ></span><span class="sxs-lookup"><span data-stu-id="792f4-114">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="792f4-115">Содержит параметры, необходимые приложению для участия в процессе обнаружения служб в качестве клиента.</span><span class="sxs-lookup"><span data-stu-id="792f4-115">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="792f4-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="792f4-116">Parent Elements</span></span>  
  
|<span data-ttu-id="792f4-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="792f4-117">Element</span></span>|<span data-ttu-id="792f4-118">Описание</span><span class="sxs-lookup"><span data-stu-id="792f4-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="792f4-119">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="792f4-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="792f4-120">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="792f4-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="792f4-121">См. также</span><span class="sxs-lookup"><span data-stu-id="792f4-121">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
