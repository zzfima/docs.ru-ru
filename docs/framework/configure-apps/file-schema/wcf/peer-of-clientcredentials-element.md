---
title: <peer> элемента <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 2f1cb5689125e2483a74dcac515beb07abbb7c70
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934039"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="58b63-102">\<Одноранговая \<> >ного элемента ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="58b63-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="58b63-103">Задает учетные данные, используемые при проверке подлинности одноранговых клиентов.</span><span class="sxs-lookup"><span data-stu-id="58b63-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="58b63-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="58b63-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="58b63-105">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="58b63-105">\<behaviors></span></span>  
<span data-ttu-id="58b63-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="58b63-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="58b63-107">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="58b63-107">\<behavior></span></span>  
<span data-ttu-id="58b63-108">\<> clientCredentials</span><span class="sxs-lookup"><span data-stu-id="58b63-108">\<clientCredentials></span></span>  
<span data-ttu-id="58b63-109">\<Одноранговые ></span><span class="sxs-lookup"><span data-stu-id="58b63-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58b63-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="58b63-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58b63-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="58b63-111">Attributes and Elements</span></span>  
 <span data-ttu-id="58b63-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="58b63-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58b63-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="58b63-113">Attributes</span></span>  
 <span data-ttu-id="58b63-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="58b63-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="58b63-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="58b63-115">Child Elements</span></span>  
  
|<span data-ttu-id="58b63-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="58b63-116">Element</span></span>|<span data-ttu-id="58b63-117">Описание</span><span class="sxs-lookup"><span data-stu-id="58b63-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58b63-118">\<> сертификата</span><span class="sxs-lookup"><span data-stu-id="58b63-118">\<certificate></span></span>](certificate-element.md)|<span data-ttu-id="58b63-119">Задает сертификат X.509, используемый для подписи и шифрования сообщений для клиентов одноранговых сетей.</span><span class="sxs-lookup"><span data-stu-id="58b63-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="58b63-120">.</span><span class="sxs-lookup"><span data-stu-id="58b63-120">.</span></span>|  
|[<span data-ttu-id="58b63-121">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="58b63-121">\<peerAuthentication></span></span>](peerauthentication-element.md)|<span data-ttu-id="58b63-122">Задает параметры проверки подлинности для одноранговых клиентов.</span><span class="sxs-lookup"><span data-stu-id="58b63-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="58b63-123">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="58b63-123">\<messageSenderAuthentication></span></span>](messagesenderauthentication-element.md)|<span data-ttu-id="58b63-124">Задает параметры проверки подлинности для отправителей сообщений.</span><span class="sxs-lookup"><span data-stu-id="58b63-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="58b63-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="58b63-125">Parent Elements</span></span>  
  
|<span data-ttu-id="58b63-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="58b63-126">Element</span></span>|<span data-ttu-id="58b63-127">Описание</span><span class="sxs-lookup"><span data-stu-id="58b63-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58b63-128">\<> clientCredentials</span><span class="sxs-lookup"><span data-stu-id="58b63-128">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="58b63-129">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="58b63-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58b63-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="58b63-130">Remarks</span></span>  
 <span data-ttu-id="58b63-131">Этот элемент конфигурации задает учетные данные, используемые одноранговым узлом для подтверждения своей подлинности для других узлов в сетке, а также параметры, используемые одноранговым узлом для проверки подлинности других одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="58b63-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="58b63-132">Дополнительные сведения см. в статье [Проверка подлинности сообщений одноранговых каналов](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) и [Защита приложений одноранговых каналов](../../../wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="58b63-132">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58b63-133">См. также</span><span class="sxs-lookup"><span data-stu-id="58b63-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="58b63-134">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="58b63-134">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="58b63-135">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="58b63-135">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- <span data-ttu-id="58b63-136">[Проверка подлинности сообщений однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="58b63-136">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="58b63-137">[Пользовательская проверка подлинности однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="58b63-137">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="58b63-138">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="58b63-138">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="58b63-139">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="58b63-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
