---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: f9d7e3a4957d2a8f30724f0bfc04e58a57fc5f7d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919271"
---
# <a name="discoveryclient"></a><span data-ttu-id="d705d-101">\<Удалено клиентом DiscoveryClient ></span><span class="sxs-lookup"><span data-stu-id="d705d-101">\<discoveryClient></span></span>
<span data-ttu-id="d705d-102">Элемент конфигурации для создания пользовательской привязки, которая позволяет клиентскому приложению автоматически выполнять поиск обнаруживаемой службы и определять ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d705d-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="d705d-103">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="d705d-103">\<system.serviceModel></span></span>  
<span data-ttu-id="d705d-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="d705d-104">\<bindings></span></span>  
<span data-ttu-id="d705d-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="d705d-105">\<customBinding></span></span>  
<span data-ttu-id="d705d-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="d705d-106">\<binding></span></span>  
<span data-ttu-id="d705d-107">\<Удалено клиентом DiscoveryClient ></span><span class="sxs-lookup"><span data-stu-id="d705d-107">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d705d-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d705d-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d705d-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d705d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d705d-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d705d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d705d-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d705d-111">Attributes</span></span>  
  
|<span data-ttu-id="d705d-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d705d-112">Attribute</span></span>|<span data-ttu-id="d705d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d705d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d705d-114">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="d705d-114">discoveryEndpoint</span></span>|<span data-ttu-id="d705d-115">Строка, содержащая имя конечной точки обнаружения, которая позволяет клиентскому приложению выполнять автоматический поиск необходимой службы и находить ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d705d-115">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d705d-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d705d-116">Child Elements</span></span>  
  
|<span data-ttu-id="d705d-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="d705d-117">Element</span></span>|<span data-ttu-id="d705d-118">Описание</span><span class="sxs-lookup"><span data-stu-id="d705d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d705d-119">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="d705d-119">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="d705d-120">Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="d705d-120">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="d705d-121">Критерии можно сгруппировать в критерии поиска (указав интересующие вас службы) и найти критерии завершения (срок поиска в прошлом).</span><span class="sxs-lookup"><span data-stu-id="d705d-121">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d705d-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d705d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d705d-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="d705d-123">Element</span></span>|<span data-ttu-id="d705d-124">Описание</span><span class="sxs-lookup"><span data-stu-id="d705d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d705d-125">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="d705d-125">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="d705d-126">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="d705d-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d705d-127">См. также</span><span class="sxs-lookup"><span data-stu-id="d705d-127">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
