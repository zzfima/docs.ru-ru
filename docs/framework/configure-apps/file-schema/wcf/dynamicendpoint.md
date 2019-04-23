---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: e1a53869faa1997d2e79c3d2869a15001ee29626
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187750"
---
# <a name="dynamicendpoint"></a><span data-ttu-id="93b1e-101">\<dynamicEndpoint ></span><span class="sxs-lookup"><span data-stu-id="93b1e-101">\<dynamicEndpoint></span></span>
<span data-ttu-id="93b1e-102">Этот элемент конфигурации определяет стандартную конечную точку, содержащую сведения, позволяющие приложению работать в качестве клиентской программы, которая может найти адрес конечной точки динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="93b1e-102">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="93b1e-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="93b1e-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="93b1e-104">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="93b1e-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93b1e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93b1e-105">Syntax</span></span>  
  
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
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93b1e-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="93b1e-106">Attributes and Elements</span></span>  
 <span data-ttu-id="93b1e-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="93b1e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93b1e-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="93b1e-108">Attributes</span></span>  
 <span data-ttu-id="93b1e-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="93b1e-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="93b1e-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="93b1e-110">Child Elements</span></span>  
  
|<span data-ttu-id="93b1e-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="93b1e-111">Element</span></span>|<span data-ttu-id="93b1e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="93b1e-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93b1e-113">\<discoveryClientSettings ></span><span class="sxs-lookup"><span data-stu-id="93b1e-113">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="93b1e-114">Содержит параметры, необходимые приложению для участия в процессе обнаружения служб в качестве клиента.</span><span class="sxs-lookup"><span data-stu-id="93b1e-114">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="93b1e-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="93b1e-115">Parent Elements</span></span>  
  
|<span data-ttu-id="93b1e-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="93b1e-116">Element</span></span>|<span data-ttu-id="93b1e-117">Описание</span><span class="sxs-lookup"><span data-stu-id="93b1e-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93b1e-118">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="93b1e-118">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="93b1e-119">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="93b1e-119">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="93b1e-120">См. также</span><span class="sxs-lookup"><span data-stu-id="93b1e-120">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
