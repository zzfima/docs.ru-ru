---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 71305720cad0206ec3dabb1863e2f1cd72eb85f0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739033"
---
# <a name="discoveryclient"></a><span data-ttu-id="5f8c8-101">\<удалено клиентом DiscoveryClient ></span><span class="sxs-lookup"><span data-stu-id="5f8c8-101">\<discoveryClient></span></span>
<span data-ttu-id="5f8c8-102">Элемент конфигурации для создания пользовательской привязки, которая позволяет клиентскому приложению автоматически выполнять поиск обнаруживаемой службы и определять ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="5f8c8-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5f8c8-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5f8c8-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5f8c8-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5f8c8-105">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="5f8c8-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="5f8c8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="5f8c8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="5f8c8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="5f8c8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="5f8c8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<удалено клиентом discoveryclient >**</span><span class="sxs-lookup"><span data-stu-id="5f8c8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClient>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f8c8-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f8c8-109">Syntax</span></span>  
  
```xml  
<discoveryClient discoveryEndpoint="String">
  <findCriteria duration="TimeSpan"
                maxResults="Integer"
                scopeMatchBy="Uri">
    <contractTypeNames>
      <add name="String"
           namespace="String" />
    </contractTypeNames>
    <extensions />
    <scopes>
      <add scope="URI"/>
    </scopes>
  </findCriteria>
</discoveryClient>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5f8c8-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5f8c8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5f8c8-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5f8c8-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5f8c8-112">Attributes</span></span>  
  
|<span data-ttu-id="5f8c8-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5f8c8-113">Attribute</span></span>|<span data-ttu-id="5f8c8-114">Описание</span><span class="sxs-lookup"><span data-stu-id="5f8c8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5f8c8-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="5f8c8-115">discoveryEndpoint</span></span>|<span data-ttu-id="5f8c8-116">Строка, содержащая имя конечной точки обнаружения, которая позволяет клиентскому приложению выполнять автоматический поиск необходимой службы и находить ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5f8c8-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5f8c8-117">Child Elements</span></span>  
  
|<span data-ttu-id="5f8c8-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="5f8c8-118">Element</span></span>|<span data-ttu-id="5f8c8-119">Описание</span><span class="sxs-lookup"><span data-stu-id="5f8c8-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5f8c8-120">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="5f8c8-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="5f8c8-121">Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="5f8c8-122">Критерии можно сгруппировать в критерии поиска (указав интересующие вас службы) и найти критерии завершения (срок поиска в прошлом).</span><span class="sxs-lookup"><span data-stu-id="5f8c8-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5f8c8-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5f8c8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5f8c8-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="5f8c8-124">Element</span></span>|<span data-ttu-id="5f8c8-125">Описание</span><span class="sxs-lookup"><span data-stu-id="5f8c8-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5f8c8-126">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="5f8c8-126">\<binding></span></span>](bindings.md)|<span data-ttu-id="5f8c8-127">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5f8c8-128">См. также</span><span class="sxs-lookup"><span data-stu-id="5f8c8-128">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
