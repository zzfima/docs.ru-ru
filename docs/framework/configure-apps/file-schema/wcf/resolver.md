---
title: '&lt;resolver&gt;'
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: f29c34f53a8bdaee4b30c72bb5d764ae3935fe7a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749027"
---
# <a name="ltresolvergt"></a><span data-ttu-id="56e37-102">&lt;resolver&gt;</span><span class="sxs-lookup"><span data-stu-id="56e37-102">&lt;resolver&gt;</span></span>
<span data-ttu-id="56e37-103">Указывает распознаватель одноранговых узлов, используемый для распознавания идентификатора сетки с IP-адресами в набор адресов одноранговых узлов, которые представляют несколько узлов, входящих в сетку.</span><span class="sxs-lookup"><span data-stu-id="56e37-103">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
 <span data-ttu-id="56e37-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="56e37-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="56e37-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="56e37-105">\<bindings></span></span>  
<span data-ttu-id="56e37-106">\<netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="56e37-106">\<netPeerBinding></span></span>  
<span data-ttu-id="56e37-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="56e37-107">\<binding></span></span>  
<span data-ttu-id="56e37-108">\<Сопоставитель ></span><span class="sxs-lookup"><span data-stu-id="56e37-108">\<resolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56e37-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56e37-109">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"  
   referralPolicy="DoNotShare/Service/Share">  
</resolver>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56e37-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="56e37-110">Attributes and Elements</span></span>  
 <span data-ttu-id="56e37-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="56e37-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56e37-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="56e37-112">Attributes</span></span>  
  
|<span data-ttu-id="56e37-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="56e37-113">Attribute</span></span>|<span data-ttu-id="56e37-114">Описание</span><span class="sxs-lookup"><span data-stu-id="56e37-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="56e37-115">Строка, которая указывает, зависит ли экземпляр распознавателя одноранговых узлов, связанный с данной службой, от PNRP, является ли он пользовательским распознавателем или определяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="56e37-115">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="56e37-116">Это атрибут типа <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span><span class="sxs-lookup"><span data-stu-id="56e37-116">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="56e37-117">Строка, указывающая, каким образом отсылки распределяются между одноранговыми узлами.</span><span class="sxs-lookup"><span data-stu-id="56e37-117">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="56e37-118">Это атрибут типа <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span><span class="sxs-lookup"><span data-stu-id="56e37-118">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56e37-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="56e37-119">Child Elements</span></span>  
  
|<span data-ttu-id="56e37-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="56e37-120">Element</span></span>|<span data-ttu-id="56e37-121">Описание</span><span class="sxs-lookup"><span data-stu-id="56e37-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56e37-122">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="56e37-122">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="56e37-123">Задает параметры службы пользовательского распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="56e37-123">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="56e37-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="56e37-124">Parent Elements</span></span>  
  
|<span data-ttu-id="56e37-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="56e37-125">Element</span></span>|<span data-ttu-id="56e37-126">Описание</span><span class="sxs-lookup"><span data-stu-id="56e37-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56e37-127">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="56e37-127">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="56e37-128">Определяет все возможности [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="56e37-128">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56e37-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="56e37-129">Remarks</span></span>  
 <span data-ttu-id="56e37-130">Распознаватель одноранговых узлов представляет собой службу обнаружения, используемую одноранговыми каналами для поиска одноранговых узлов, участвующих в сетке с IP-адресами.</span><span class="sxs-lookup"><span data-stu-id="56e37-130">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="56e37-131">Он также используется для «регистрации» узла в сетке с IP-адресами; с помощью такого механизма одноранговый узел становится известным и доступным из сетки с IP-адресами.</span><span class="sxs-lookup"><span data-stu-id="56e37-131">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="56e37-132">Дополнительные сведения о распознавателей одноранговых узлов см. в разделе [распознавателей одноранговых узлов](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span><span class="sxs-lookup"><span data-stu-id="56e37-132">For more information on peer resolvers, see [Peer Resolvers](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56e37-133">См. также</span><span class="sxs-lookup"><span data-stu-id="56e37-133">See Also</span></span>  
 <xref:System.ServiceModel.PeerResolver>  
 <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement>  
 [<span data-ttu-id="56e37-134">Одноранговые распознаватели</span><span class="sxs-lookup"><span data-stu-id="56e37-134">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [<span data-ttu-id="56e37-135">Добавление пользовательского арбитра конфликтов в приложении PeerChannel</span><span class="sxs-lookup"><span data-stu-id="56e37-135">Adding a Custom Resolver to a PeerChannel Application</span></span>](http://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
