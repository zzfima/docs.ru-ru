---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 929c5d170bfc27160e3e15b8bd2f9f26e0ed8975
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855410"
---
# <a name="discoveryclientsettings"></a><span data-ttu-id="ec573-101">\<Дисковериклиентсеттингс ></span><span class="sxs-lookup"><span data-stu-id="ec573-101">\<discoveryClientSettings></span></span>
<span data-ttu-id="ec573-102">Содержит параметры, необходимые приложению для участия в процессе обнаружения служб в качестве клиента.</span><span class="sxs-lookup"><span data-stu-id="ec573-102">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="ec573-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ec573-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ec573-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ec573-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ec573-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Стандардендпоинтс >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="ec573-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="ec573-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Динамицендпоинт >** ](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="ec573-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="ec573-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Стандардендпоинт >** </span><span class="sxs-lookup"><span data-stu-id="ec573-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="ec573-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Дисковериклиентсеттингс >**</span><span class="sxs-lookup"><span data-stu-id="ec573-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClientSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec573-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec573-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec573-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ec573-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ec573-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ec573-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec573-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ec573-112">Attributes</span></span>  
  
|<span data-ttu-id="ec573-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ec573-113">Attribute</span></span>|<span data-ttu-id="ec573-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ec573-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ec573-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="ec573-115">discoveryEndpoint</span></span>|<span data-ttu-id="ec573-116">Строка, содержащая имя конечной точки обнаружения, которая позволяет клиентскому приложению выполнять автоматический поиск необходимой службы и находить ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="ec573-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec573-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ec573-117">Child Elements</span></span>  
  
|<span data-ttu-id="ec573-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="ec573-118">Element</span></span>|<span data-ttu-id="ec573-119">Описание</span><span class="sxs-lookup"><span data-stu-id="ec573-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec573-120">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="ec573-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="ec573-121">Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="ec573-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="ec573-122">Критерии можно сгруппировать в критерии поиска (указав интересующие вас службы) и найти критерии завершения (срок поиска в прошлом).</span><span class="sxs-lookup"><span data-stu-id="ec573-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ec573-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ec573-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ec573-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="ec573-124">Element</span></span>|<span data-ttu-id="ec573-125">Описание</span><span class="sxs-lookup"><span data-stu-id="ec573-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec573-126">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="ec573-126">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="ec573-127">Определяет стандартную конечную точку, сведения которой позволяют приложению работать в качестве клиентской программы, динамически ищущей адрес конечной точки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="ec573-127">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec573-128">См. также</span><span class="sxs-lookup"><span data-stu-id="ec573-128">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
