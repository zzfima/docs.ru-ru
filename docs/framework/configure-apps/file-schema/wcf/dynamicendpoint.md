---
title: '&lt;dynamicEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: 215bc9d8540b2d782a0c63f2f5be96f6fcde6812
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746765"
---
# <a name="ltdynamicendpointgt"></a><span data-ttu-id="ae32d-102">&lt;dynamicEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="ae32d-102">&lt;dynamicEndpoint&gt;</span></span>
<span data-ttu-id="ae32d-103">Этот элемент конфигурации определяет стандартную конечную точку, содержащую сведения, позволяющие приложению работать в качестве клиентской программы, которая может найти адрес конечной точки динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="ae32d-103">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="ae32d-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ae32d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ae32d-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="ae32d-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae32d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ae32d-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae32d-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ae32d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ae32d-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ae32d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae32d-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ae32d-109">Attributes</span></span>  
 <span data-ttu-id="ae32d-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ae32d-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ae32d-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ae32d-111">Child Elements</span></span>  
  
|<span data-ttu-id="ae32d-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="ae32d-112">Element</span></span>|<span data-ttu-id="ae32d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ae32d-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae32d-114">\<discoveryClientSettings ></span><span class="sxs-lookup"><span data-stu-id="ae32d-114">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="ae32d-115">Содержит параметры, необходимые приложению для участия в процессе обнаружения служб в качестве клиента.</span><span class="sxs-lookup"><span data-stu-id="ae32d-115">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ae32d-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ae32d-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ae32d-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="ae32d-117">Element</span></span>|<span data-ttu-id="ae32d-118">Описание</span><span class="sxs-lookup"><span data-stu-id="ae32d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae32d-119">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="ae32d-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="ae32d-120">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="ae32d-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae32d-121">См. также</span><span class="sxs-lookup"><span data-stu-id="ae32d-121">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
