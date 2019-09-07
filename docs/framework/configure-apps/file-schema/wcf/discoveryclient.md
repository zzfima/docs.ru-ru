---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 5e586437e3b269d361c254744e820ee8e8c0ca0a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400398"
---
# <a name="discoveryclient"></a><span data-ttu-id="1b49e-101">\<Удалено клиентом DiscoveryClient ></span><span class="sxs-lookup"><span data-stu-id="1b49e-101">\<discoveryClient></span></span>
<span data-ttu-id="1b49e-102">Элемент конфигурации для создания пользовательской привязки, которая позволяет клиентскому приложению автоматически выполнять поиск обнаруживаемой службы и определять ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="1b49e-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="1b49e-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1b49e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1b49e-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1b49e-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1b49e-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="1b49e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="1b49e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="1b49e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="1b49e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="1b49e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="1b49e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Удалено клиентом DiscoveryClient >**</span><span class="sxs-lookup"><span data-stu-id="1b49e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClient>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b49e-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b49e-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b49e-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1b49e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1b49e-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1b49e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b49e-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1b49e-112">Attributes</span></span>  
  
|<span data-ttu-id="1b49e-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1b49e-113">Attribute</span></span>|<span data-ttu-id="1b49e-114">Описание</span><span class="sxs-lookup"><span data-stu-id="1b49e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1b49e-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="1b49e-115">discoveryEndpoint</span></span>|<span data-ttu-id="1b49e-116">Строка, содержащая имя конечной точки обнаружения, которая позволяет клиентскому приложению выполнять автоматический поиск необходимой службы и находить ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="1b49e-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1b49e-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1b49e-117">Child Elements</span></span>  
  
|<span data-ttu-id="1b49e-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="1b49e-118">Element</span></span>|<span data-ttu-id="1b49e-119">Описание</span><span class="sxs-lookup"><span data-stu-id="1b49e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b49e-120">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="1b49e-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="1b49e-121">Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="1b49e-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="1b49e-122">Критерии можно сгруппировать в критерии поиска (указав интересующие вас службы) и найти критерии завершения (срок поиска в прошлом).</span><span class="sxs-lookup"><span data-stu-id="1b49e-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1b49e-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1b49e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1b49e-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="1b49e-124">Element</span></span>|<span data-ttu-id="1b49e-125">Описание</span><span class="sxs-lookup"><span data-stu-id="1b49e-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b49e-126">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="1b49e-126">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="1b49e-127">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="1b49e-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1b49e-128">См. также</span><span class="sxs-lookup"><span data-stu-id="1b49e-128">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
