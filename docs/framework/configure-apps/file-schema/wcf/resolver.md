---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: e3a9ee00aab6ab48a1ba891565b63824e62b20fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934215"
---
# <a name="resolver"></a><span data-ttu-id="82a94-101">\<сопоставитель ></span><span class="sxs-lookup"><span data-stu-id="82a94-101">\<resolver></span></span>
<span data-ttu-id="82a94-102">Указывает распознаватель одноранговых узлов, используемый для распознавания идентификатора сетки с IP-адресами в набор адресов одноранговых узлов, которые представляют несколько узлов, входящих в сетку.</span><span class="sxs-lookup"><span data-stu-id="82a94-102">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
 <span data-ttu-id="82a94-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="82a94-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="82a94-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="82a94-104">\<bindings></span></span>  
<span data-ttu-id="82a94-105">\<Нетпирбиндинг ></span><span class="sxs-lookup"><span data-stu-id="82a94-105">\<netPeerBinding></span></span>  
<span data-ttu-id="82a94-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="82a94-106">\<binding></span></span>  
<span data-ttu-id="82a94-107">\<сопоставитель ></span><span class="sxs-lookup"><span data-stu-id="82a94-107">\<resolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82a94-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82a94-108">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82a94-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="82a94-109">Attributes and Elements</span></span>  
 <span data-ttu-id="82a94-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="82a94-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82a94-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="82a94-111">Attributes</span></span>  
  
|<span data-ttu-id="82a94-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="82a94-112">Attribute</span></span>|<span data-ttu-id="82a94-113">Описание</span><span class="sxs-lookup"><span data-stu-id="82a94-113">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="82a94-114">Строка, которая указывает, зависит ли экземпляр распознавателя одноранговых узлов, связанный с данной службой, от PNRP, является ли он пользовательским распознавателем или определяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="82a94-114">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="82a94-115">Это атрибут типа <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span><span class="sxs-lookup"><span data-stu-id="82a94-115">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="82a94-116">Строка, указывающая, каким образом отсылки распределяются между одноранговыми узлами.</span><span class="sxs-lookup"><span data-stu-id="82a94-116">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="82a94-117">Это атрибут типа <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span><span class="sxs-lookup"><span data-stu-id="82a94-117">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="82a94-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="82a94-118">Child Elements</span></span>  
  
|<span data-ttu-id="82a94-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="82a94-119">Element</span></span>|<span data-ttu-id="82a94-120">Описание</span><span class="sxs-lookup"><span data-stu-id="82a94-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82a94-121">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="82a94-121">\<headers></span></span>](headers.md)|<span data-ttu-id="82a94-122">Задает параметры службы пользовательского распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="82a94-122">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="82a94-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="82a94-123">Parent Elements</span></span>  
  
|<span data-ttu-id="82a94-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="82a94-124">Element</span></span>|<span data-ttu-id="82a94-125">Описание</span><span class="sxs-lookup"><span data-stu-id="82a94-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82a94-126">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="82a94-126">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="82a94-127">Определяет все возможности [ \<привязки > netPeerTcpBinding](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="82a94-127">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82a94-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="82a94-128">Remarks</span></span>  
 <span data-ttu-id="82a94-129">Распознаватель одноранговых узлов представляет собой службу обнаружения, используемую одноранговыми каналами для поиска одноранговых узлов, участвующих в сетке с IP-адресами.</span><span class="sxs-lookup"><span data-stu-id="82a94-129">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="82a94-130">Он также используется для «регистрации» узла в сетке с IP-адресами; с помощью такого механизма одноранговый узел становится известным и доступным из сетки с IP-адресами.</span><span class="sxs-lookup"><span data-stu-id="82a94-130">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="82a94-131">Дополнительные сведения об одноранговых решениях см. в разделе одноранговые [арбитры конфликтов](../../../wcf/feature-details/peer-resolvers.md).</span><span class="sxs-lookup"><span data-stu-id="82a94-131">For more information on peer resolvers, see [Peer Resolvers](../../../wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a94-132">См. также</span><span class="sxs-lookup"><span data-stu-id="82a94-132">See also</span></span>

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="82a94-133">Одноранговые распознаватели</span><span class="sxs-lookup"><span data-stu-id="82a94-133">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="82a94-134">[Добавление пользовательского сопоставителя в приложение PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="82a94-134">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
