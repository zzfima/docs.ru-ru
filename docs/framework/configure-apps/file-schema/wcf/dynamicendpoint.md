---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: da57ca3ba3bc0036727a749f1cab9ec3657a4fda
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855340"
---
# <a name="dynamicendpoint"></a><span data-ttu-id="7798f-101">\<Динамицендпоинт ></span><span class="sxs-lookup"><span data-stu-id="7798f-101">\<dynamicEndpoint></span></span>
<span data-ttu-id="7798f-102">Этот элемент конфигурации определяет стандартную конечную точку, содержащую сведения, позволяющие приложению работать в качестве клиентской программы, которая может найти адрес конечной точки динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7798f-102">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="7798f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7798f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7798f-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7798f-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7798f-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Стандардендпоинтс >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="7798f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="7798f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Динамицендпоинт >**</span><span class="sxs-lookup"><span data-stu-id="7798f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dynamicEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7798f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7798f-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7798f-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7798f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7798f-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7798f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7798f-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7798f-110">Attributes</span></span>  
 <span data-ttu-id="7798f-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="7798f-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7798f-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7798f-112">Child Elements</span></span>  
  
|<span data-ttu-id="7798f-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="7798f-113">Element</span></span>|<span data-ttu-id="7798f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="7798f-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7798f-115">\<Дисковериклиентсеттингс ></span><span class="sxs-lookup"><span data-stu-id="7798f-115">\<discoveryClientSettings></span></span>](discoveryclientsettings.md)|<span data-ttu-id="7798f-116">Содержит параметры, необходимые приложению для участия в процессе обнаружения служб в качестве клиента.</span><span class="sxs-lookup"><span data-stu-id="7798f-116">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7798f-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7798f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="7798f-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="7798f-118">Element</span></span>|<span data-ttu-id="7798f-119">Описание</span><span class="sxs-lookup"><span data-stu-id="7798f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7798f-120">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="7798f-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="7798f-121">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="7798f-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7798f-122">См. также</span><span class="sxs-lookup"><span data-stu-id="7798f-122">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
