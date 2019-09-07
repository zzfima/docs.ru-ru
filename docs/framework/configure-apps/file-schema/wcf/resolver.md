---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: fb974492dee6b2a4244cedc06e3f5e40334dd02a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399987"
---
# <a name="resolver"></a><span data-ttu-id="734df-101">\<сопоставитель ></span><span class="sxs-lookup"><span data-stu-id="734df-101">\<resolver></span></span>
<span data-ttu-id="734df-102">Указывает распознаватель одноранговых узлов, используемый для распознавания идентификатора сетки с IP-адресами в набор адресов одноранговых узлов, которые представляют несколько узлов, входящих в сетку.</span><span class="sxs-lookup"><span data-stu-id="734df-102">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
<span data-ttu-id="734df-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="734df-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="734df-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="734df-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="734df-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="734df-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="734df-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding >** ](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="734df-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="734df-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="734df-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="734df-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<сопоставитель >**</span><span class="sxs-lookup"><span data-stu-id="734df-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<resolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="734df-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="734df-109">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="734df-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="734df-110">Attributes and Elements</span></span>  
 <span data-ttu-id="734df-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="734df-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="734df-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="734df-112">Attributes</span></span>  
  
|<span data-ttu-id="734df-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="734df-113">Attribute</span></span>|<span data-ttu-id="734df-114">Описание</span><span class="sxs-lookup"><span data-stu-id="734df-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="734df-115">Строка, которая указывает, зависит ли экземпляр распознавателя одноранговых узлов, связанный с данной службой, от PNRP, является ли он пользовательским распознавателем или определяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="734df-115">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="734df-116">Это атрибут типа <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span><span class="sxs-lookup"><span data-stu-id="734df-116">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="734df-117">Строка, указывающая, каким образом отсылки распределяются между одноранговыми узлами.</span><span class="sxs-lookup"><span data-stu-id="734df-117">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="734df-118">Это атрибут типа <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span><span class="sxs-lookup"><span data-stu-id="734df-118">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="734df-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="734df-119">Child Elements</span></span>  
  
|<span data-ttu-id="734df-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="734df-120">Element</span></span>|<span data-ttu-id="734df-121">Описание</span><span class="sxs-lookup"><span data-stu-id="734df-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="734df-122">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="734df-122">\<headers></span></span>](headers.md)|<span data-ttu-id="734df-123">Задает параметры службы пользовательского распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="734df-123">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="734df-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="734df-124">Parent Elements</span></span>  
  
|<span data-ttu-id="734df-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="734df-125">Element</span></span>|<span data-ttu-id="734df-126">Описание</span><span class="sxs-lookup"><span data-stu-id="734df-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="734df-127">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="734df-127">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="734df-128">Определяет все возможности [ \<привязки > netPeerTcpBinding](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="734df-128">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="734df-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="734df-129">Remarks</span></span>  
 <span data-ttu-id="734df-130">Распознаватель одноранговых узлов представляет собой службу обнаружения, используемую одноранговыми каналами для поиска одноранговых узлов, участвующих в сетке с IP-адресами.</span><span class="sxs-lookup"><span data-stu-id="734df-130">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="734df-131">Он также используется для «регистрации» узла в сетке с IP-адресами; с помощью такого механизма одноранговый узел становится известным и доступным из сетки с IP-адресами.</span><span class="sxs-lookup"><span data-stu-id="734df-131">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="734df-132">Дополнительные сведения об одноранговых решениях см. в разделе [одноранговые арбитры конфликтов](../../../wcf/feature-details/peer-resolvers.md).</span><span class="sxs-lookup"><span data-stu-id="734df-132">For more information on peer resolvers, see [Peer Resolvers](../../../wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="734df-133">См. также</span><span class="sxs-lookup"><span data-stu-id="734df-133">See also</span></span>

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="734df-134">Одноранговые распознаватели</span><span class="sxs-lookup"><span data-stu-id="734df-134">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="734df-135">[Добавление пользовательского сопоставителя в приложение PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="734df-135">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
