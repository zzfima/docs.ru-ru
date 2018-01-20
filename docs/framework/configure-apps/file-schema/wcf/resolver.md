---
title: '&lt;resolver&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: db95b6f9a988c133a6b4afd55849fc6fb650c24c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="ltresolvergt"></a><span data-ttu-id="64212-102">&lt;resolver&gt;</span><span class="sxs-lookup"><span data-stu-id="64212-102">&lt;resolver&gt;</span></span>
<span data-ttu-id="64212-103">Указывает распознаватель одноранговых узлов, используемый для распознавания идентификатора сетки с IP-адресами в набор адресов одноранговых узлов, которые представляют несколько узлов, входящих в сетку.</span><span class="sxs-lookup"><span data-stu-id="64212-103">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
 <span data-ttu-id="64212-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="64212-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="64212-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="64212-105">\<bindings></span></span>  
<span data-ttu-id="64212-106">\<netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="64212-106">\<netPeerBinding></span></span>  
<span data-ttu-id="64212-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="64212-107">\<binding></span></span>  
<span data-ttu-id="64212-108">\<resolver></span><span class="sxs-lookup"><span data-stu-id="64212-108">\<resolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64212-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64212-109">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"  
   referralPolicy="DoNotShare/Service/Share">  
</resolver>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64212-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="64212-110">Attributes and Elements</span></span>  
 <span data-ttu-id="64212-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="64212-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64212-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="64212-112">Attributes</span></span>  
  
|<span data-ttu-id="64212-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="64212-113">Attribute</span></span>|<span data-ttu-id="64212-114">Описание</span><span class="sxs-lookup"><span data-stu-id="64212-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="64212-115">Строка, которая указывает, зависит ли экземпляр распознавателя одноранговых узлов, связанный с данной службой, от PNRP, является ли он пользовательским распознавателем или определяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="64212-115">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="64212-116">Это атрибут типа <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span><span class="sxs-lookup"><span data-stu-id="64212-116">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="64212-117">Строка, указывающая, каким образом отсылки распределяются между одноранговыми узлами.</span><span class="sxs-lookup"><span data-stu-id="64212-117">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="64212-118">Это атрибут типа <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span><span class="sxs-lookup"><span data-stu-id="64212-118">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64212-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="64212-119">Child Elements</span></span>  
  
|<span data-ttu-id="64212-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="64212-120">Element</span></span>|<span data-ttu-id="64212-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="64212-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64212-122">\<headers></span><span class="sxs-lookup"><span data-stu-id="64212-122">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="64212-123">Задает параметры службы пользовательского распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="64212-123">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="64212-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="64212-124">Parent Elements</span></span>  
  
|<span data-ttu-id="64212-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="64212-125">Element</span></span>|<span data-ttu-id="64212-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="64212-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64212-127">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="64212-127">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="64212-128">Определяет все возможности [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="64212-128">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64212-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="64212-129">Remarks</span></span>  
 <span data-ttu-id="64212-130">Распознаватель одноранговых узлов представляет собой службу обнаружения, используемую одноранговыми каналами для поиска одноранговых узлов, участвующих в сетке с IP-адресами.</span><span class="sxs-lookup"><span data-stu-id="64212-130">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="64212-131">Он также используется для «регистрации» узла в сетке с IP-адресами; с помощью такого механизма одноранговый узел становится известным и доступным из сетки с IP-адресами.</span><span class="sxs-lookup"><span data-stu-id="64212-131">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="64212-132">Дополнительные сведения о распознавателей одноранговых узлов см. в разделе [распознавателей одноранговых узлов](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span><span class="sxs-lookup"><span data-stu-id="64212-132">For more information on peer resolvers, see [Peer Resolvers](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64212-133">См. также</span><span class="sxs-lookup"><span data-stu-id="64212-133">See Also</span></span>  
 <xref:System.ServiceModel.PeerResolver>  
 <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement>  
 [<span data-ttu-id="64212-134">Одноранговые распознаватели</span><span class="sxs-lookup"><span data-stu-id="64212-134">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [<span data-ttu-id="64212-135">Добавление пользовательского арбитра конфликтов в приложении PeerChannel</span><span class="sxs-lookup"><span data-stu-id="64212-135">Adding a Custom Resolver to a PeerChannel Application</span></span>](http://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
