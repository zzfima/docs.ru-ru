---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: 0dc667f392595d895bd4f2773ab69777d7369446
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738739"
---
# <a name="resolver"></a><span data-ttu-id="04096-101">сопоставитель \<</span><span class="sxs-lookup"><span data-stu-id="04096-101">\<resolver></span></span>
<span data-ttu-id="04096-102">Указывает распознаватель одноранговых узлов, используемый для распознавания идентификатора сетки с IP-адресами в набор адресов одноранговых узлов, которые представляют несколько узлов, входящих в сетку.</span><span class="sxs-lookup"><span data-stu-id="04096-102">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
<span data-ttu-id="04096-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="04096-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="04096-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="04096-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="04096-105">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="04096-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="04096-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding >** ](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="04096-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="04096-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="04096-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="04096-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<сопоставитель >**</span><span class="sxs-lookup"><span data-stu-id="04096-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<resolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04096-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04096-109">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04096-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="04096-110">Attributes and Elements</span></span>  
 <span data-ttu-id="04096-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="04096-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04096-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="04096-112">Attributes</span></span>  
  
|<span data-ttu-id="04096-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="04096-113">Attribute</span></span>|<span data-ttu-id="04096-114">Описание</span><span class="sxs-lookup"><span data-stu-id="04096-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="04096-115">Строка, которая указывает, зависит ли экземпляр распознавателя одноранговых узлов, связанный с данной службой, от PNRP, является ли он пользовательским распознавателем или определяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="04096-115">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="04096-116">Это атрибут типа <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span><span class="sxs-lookup"><span data-stu-id="04096-116">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="04096-117">Строка, указывающая, каким образом отсылки распределяются между одноранговыми узлами.</span><span class="sxs-lookup"><span data-stu-id="04096-117">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="04096-118">Это атрибут типа <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span><span class="sxs-lookup"><span data-stu-id="04096-118">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04096-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="04096-119">Child Elements</span></span>  
  
|<span data-ttu-id="04096-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="04096-120">Element</span></span>|<span data-ttu-id="04096-121">Описание</span><span class="sxs-lookup"><span data-stu-id="04096-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04096-122">\<заголовков ></span><span class="sxs-lookup"><span data-stu-id="04096-122">\<headers></span></span>](headers.md)|<span data-ttu-id="04096-123">Задает параметры службы пользовательского распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="04096-123">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="04096-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="04096-124">Parent Elements</span></span>  
  
|<span data-ttu-id="04096-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="04096-125">Element</span></span>|<span data-ttu-id="04096-126">Описание</span><span class="sxs-lookup"><span data-stu-id="04096-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04096-127">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="04096-127">\<binding></span></span>](bindings.md)|<span data-ttu-id="04096-128">Определяет все возможности привязки [\<netPeerTcpBinding >](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="04096-128">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04096-129">Заметки</span><span class="sxs-lookup"><span data-stu-id="04096-129">Remarks</span></span>  
 <span data-ttu-id="04096-130">Распознаватель одноранговых узлов представляет собой службу обнаружения, используемую одноранговыми каналами для поиска одноранговых узлов, участвующих в сетке с IP-адресами.</span><span class="sxs-lookup"><span data-stu-id="04096-130">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="04096-131">Он также используется для «регистрации» узла в сетке с IP-адресами; с помощью такого механизма одноранговый узел становится известным и доступным из сетки с IP-адресами.</span><span class="sxs-lookup"><span data-stu-id="04096-131">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="04096-132">Дополнительные сведения об одноранговых решениях см. в разделе [одноранговые арбитры конфликтов](../../../wcf/feature-details/peer-resolvers.md).</span><span class="sxs-lookup"><span data-stu-id="04096-132">For more information on peer resolvers, see [Peer Resolvers](../../../wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04096-133">См. также</span><span class="sxs-lookup"><span data-stu-id="04096-133">See also</span></span>

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="04096-134">Одноранговые распознаватели</span><span class="sxs-lookup"><span data-stu-id="04096-134">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="04096-135">[Добавление пользовательского сопоставителя в приложение PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="04096-135">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
