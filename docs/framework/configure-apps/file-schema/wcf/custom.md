---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 598b341e8b09acd11ba215e6add3adf9e44b2b81
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400467"
---
# <a name="custom"></a><span data-ttu-id="8c88a-101">\<Пользовательские ></span><span class="sxs-lookup"><span data-stu-id="8c88a-101">\<custom></span></span>
<span data-ttu-id="8c88a-102">Задает параметры службы пользовательского распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="8c88a-102">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="8c88a-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8c88a-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8c88a-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8c88a-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8c88a-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="8c88a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="8c88a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding >** ](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="8c88a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="8c88a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="8c88a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="8c88a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<сопоставитель >** ](resolver.md)</span><span class="sxs-lookup"><span data-stu-id="8c88a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<resolver>**](resolver.md)</span></span>\
<span data-ttu-id="8c88a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Пользовательские >**</span><span class="sxs-lookup"><span data-stu-id="8c88a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<custom>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c88a-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c88a-110">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c88a-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8c88a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8c88a-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8c88a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c88a-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8c88a-113">Attributes</span></span>  
  
|<span data-ttu-id="8c88a-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8c88a-114">Attribute</span></span>|<span data-ttu-id="8c88a-115">Описание</span><span class="sxs-lookup"><span data-stu-id="8c88a-115">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="8c88a-116">URI, указывающий адрес конечной точки однорангового узла, на котором размещается пользовательская служба распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="8c88a-116">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="8c88a-117">Строка, задающая тип пользовательской службы распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="8c88a-117">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c88a-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8c88a-118">Child Elements</span></span>  
  
|<span data-ttu-id="8c88a-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="8c88a-119">Element</span></span>|<span data-ttu-id="8c88a-120">Описание</span><span class="sxs-lookup"><span data-stu-id="8c88a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c88a-121">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="8c88a-121">\<identity></span></span>](identity.md)|<span data-ttu-id="8c88a-122">Задает идентификатор пользовательских распознавателей одноранговых узлов, настроенных для данного элемента.</span><span class="sxs-lookup"><span data-stu-id="8c88a-122">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="8c88a-123">Это элемент типа <xref:System.ServiceModel.Configuration.IdentityElement>.</span><span class="sxs-lookup"><span data-stu-id="8c88a-123">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="8c88a-124">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="8c88a-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="8c88a-125">Коллекция заголовков адреса, используемых для сообщений SOAP, обрабатываемых пользовательским распознавателем одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="8c88a-125">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c88a-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8c88a-126">Parent Elements</span></span>  
  
|<span data-ttu-id="8c88a-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="8c88a-127">Element</span></span>|<span data-ttu-id="8c88a-128">Описание</span><span class="sxs-lookup"><span data-stu-id="8c88a-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c88a-129">\<resolver></span><span class="sxs-lookup"><span data-stu-id="8c88a-129">\<resolver></span></span>](resolver.md)|<span data-ttu-id="8c88a-130">Распознаватель одноранговых узлов, используемый для разрешения идентификатора сетки с IP-адресами в набор адресов одноранговых узлов, представляющих несколько узлов, входящих в сетку.</span><span class="sxs-lookup"><span data-stu-id="8c88a-130">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c88a-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c88a-131">Remarks</span></span>  
 <span data-ttu-id="8c88a-132">Этот элемент определяет основные параметры пользовательской службы распознавателя одноранговых узлов, включая адрес конечной точки однорангового узла, на котором размещена служба, и любые специальные параметры привязки.</span><span class="sxs-lookup"><span data-stu-id="8c88a-132">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="8c88a-133">Дополнительные сведения о создании пользовательского сопоставителя см. в разделе [Добавление пользовательского сопоставителя в приложение PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="8c88a-133">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c88a-134">См. также</span><span class="sxs-lookup"><span data-stu-id="8c88a-134">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="8c88a-135">Одноранговые распознаватели</span><span class="sxs-lookup"><span data-stu-id="8c88a-135">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="8c88a-136">[Добавление пользовательского сопоставителя в приложение PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="8c88a-136">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
